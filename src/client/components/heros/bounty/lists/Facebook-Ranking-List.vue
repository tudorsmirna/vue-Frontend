<template>

    <div>

        <loading-spinner class="bountySpinner" v-if="fetchingList" />

        <div v-if="!fetchingList" class="list">

            <div class="listHead listElement facebookElement">
                <div>No.</div>
                <div class="title">Post description</div>
                <div>Likes</div>
                <div>Shares</div>
                <div>Comments</div>
                <div>Score</div>
                <div>Reward</div>
            </div>

            <div class="listElement facebookElement" v-for="(element, index) in list" :key="'FacebookRankingListElement '+index">

                <div>{{index+1}}</div>
                <div class="title">{{element.description !== undefined ? element.description.substring(0, 50) : ''}}</div>
                <div>{{element.likes}}</div>
                <div>{{element.shares}}</div>
                <div>{{element.comments}}</div>
                <div>{{element.score !== undefined ? element.score.toFixed(2) : 'na'}}</div>
                <div class="score">{{element.reward !== undefined ? element.reward.toFixed(2) : 'na'}}</div>
            </div>

        </div>

    </div>

</template>

<script>

    import LoadingSpinner from "client/components/UI/elements/Loading-Spinner.vue"

    export default{

        components:{ LoadingSpinner },

        props:{
            fetchingList: {default: true},
            list: {default: function (){ return { } }},
        },

        methods:{
        },

        computed(){

            console.log(element);

        },

    }

</script>