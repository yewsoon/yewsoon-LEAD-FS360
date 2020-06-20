<template>
    <div class="flex flex-col">
        <contentCard class="mt-2 mb-4">
            <template v-slot:title>
                New Bean
            </template>
            <template v-slot:content>
                <form class="flex grid grid-cols-1 md:grid-cols-4">
                    <div class="my-2 mx-2 relative md:col-span-2">
                        <inputElement
                            :labelName="'Bean Name'"
                            :labelId="'beanName'"
                            :inputType="'text'"
                            :model="bean"
                            @input="bean = $event"
                            :disabled="flase"
                            />
                        <i class="fas fa-glove-asia absolute top-0 tex-gray-500 right-0 p-3">                         
                        </i>
                    </div>
                    <div class="my-2 mx-2 relative md:col-span-2">
                        <selectElement
                            :labelName="'ROAST LEVEL'"
                            :model="roastLevel"
                            @select="roastLevel = $event">
                            <template v-slot:select-options>
                                <option
                                    v-for="roast in roastLevelList" :key="roast" :value="roast">
                                        {{roast}}
                                </option>
                            </template>
                        </selectElement>    
                    </div>
                    <div class="my-2 mx-2 relative md:col-span-2">
                        <inputElement
                            :labelName="'WEIGHT PER PACK (GRAM)'"
                            :labelId="'weightPerPack'"
                            :inputType="'text'"
                            :model="weightPerPack"
                            @input="weightPerPack = $event"
                            :disabled="flase"
                            />
                        <i class="fas fa-glove-asia absolute top-0 tex-gray-500 right-0 p-3">                         
                        </i>
                    </div>
                    <div class="my-2 mx-2 relative md:col-span-2">
                        <inputElement
                            :labelName="'WEIGHT BEFORE ROAST (KILOGRAM)'"
                            :labelId="'weightBeforeRoast'"
                            :inputType="'text'"
                            :model="weightBeforeRoast"
                            @input="weightBeforeRoast = $event"
                            :disabled="flase"
                            />
                        <i class="fas fa-glove-asia absolute top-0 tex-gray-500 right-0 p-3">                         
                        </i>
                    </div>
                    <div class="my-2 mx-2 relative md:col-span-2">
                        <inputElement
                            :labelName="'WEIGHT AFTER ROAST (KILOGRAM)'"
                            :labelId="'weightAfterRoast'"
                            :inputType="'text'"
                            :model="weightAfterRoast"
                            @input="weightAfterRoast = $event"
                            :disabled="flase"
                            />
                        <i class="fas fa-glove-asia absolute top-0 tex-gray-500 right-0 p-3">                         
                        </i>
                    </div>
                    <div class="my-2 mx-2 relative md:col-span-2">
                        <inputElement
                            :labelName="'WEIGHT PER PACK (GRAM)'"
                            :labelId="'weightPerPack'"
                            :inputType="'text'"
                            :model="weightPerPack"
                            @input="weightPerPack = $event"
                            :disabled="flase"
                            />
                        <i class="fas fa-glove-asia absolute top-0 tex-gray-500 right-0 p-3">                         
                        </i>
                    </div>
                    <div class="my-2 mx-2 relative md:col-span-2">
                        <inputElement
                            :labelName="'COFFEE PROFILE'"
                            :labelId="'profile'"
                            :inputType="'text'"
                            :model="profile"
                            @input="profile = $event"
                            :disabled="flase"
                            />
                        <i class="fas fa-glove-asia absolute top-0 tex-gray-500 right-0 p-3">                         
                        </i>
                    </div>
                </form>
            </template>
        </contentCard>            
    </div>
</template>
<script>
    import ContentCard from "~/components/items/ContentCard.vue";
    import InputElement from "~/components/items/Input.vue";
    import SelectElement from "~/components/items/Select.vue";

    export default {
        layout:"dashboard",
        components: {
            ContentCard,
            InputElement,
            SelectElement
        },
        data () {
            return {
                bean:'',
                roastLevel: '',
                roastLevelList: ['Light Roast', 'Medium Roast', 'Dark Roast'],
                weightPerPack: '',
                weightBeforeRoast: '',
                profile: '',
                selectedStock: {
                    price: 500,
                    purchasedStock: 15
                }
            }
        }
    }
</script>