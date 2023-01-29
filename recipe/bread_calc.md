# Bread Calculator

Bread recipes usually define a flour weight and remaining ingredients
are calculated as a percentage.

<div id="calculator">
    <div>
        <label>Flour
            <input v-model="flour_g" type="number">
        </label>
    </div>
    <h2>Remaining Ingredients</h2>
    <table>
        <tr>
            <th>Ingredient</th>
            <th>%</th>
            <th>Qty</th>
        </tr>
        <tr v-for="ingr in recipe">
            <td>{{ingr.desc}}</td>
            <td><input v-model="ingr.pc" type="number"></td>
            <td>{{ingr.qty}}</td>
        </tr>
    </table>
    <button @click="recalc">Calc</button>
</div>

<script>
Vue.createApp({
    data() {
        return {
            flour_g: 600,
            recipe2: [
                {desc: 'Flour - Plain', pc: 40, qty: 0},
                {desc: 'Flour - Wholemeal', pc: 50, qty: 0},
                {desc: 'Flour - Tangzhong', pc: 10, qty: 0},
                {desc: 'Water - Tangzhong', pc: 50, qty: 0},
                {desc: 'Water - Yeast', pc: 20, qty: 0},
                {desc: 'Sugar', pc: 5, qty: 0},
                {desc: 'Instant Yeast', pc: 1, qty: 0},
                {desc: 'Salt', pc: 2, qty: 0},
                {desc: 'Sunflower Oil', pc: 0, qty: 0},
            ],
            recipe: [
                {desc: 'Flour - Plain', pc: 67, qty: 400},
                {desc: 'Flour - Wholemeal', pc: 33, qty: 0},
                {desc: 'Water', pc: 67, qty: 0},
                {desc: 'Sugar', pc: 3, qty: 0},
                {desc: 'Instant Yeast', pc: 1, qty: 0},
                {desc: 'Salt', pc: 1, qty: 0},
                {desc: 'Sunflower Oil', pc: 5, qty: 0},
            ],
        }
    },
    methods: {
        recalc(event) {
            //this.water_g = this.flour_g * 0.67
            console.log("recalc()")

            for (let i = 0; i < this.recipe.length; i++) {
                console.log('ingr', this.recipe[i])
                this.recipe[i].qty = this.flour_g * this.recipe[i].pc / 100
            }

            console.log(this.recipe)
        },
    }
}).mount('#calculator');
</script>

```javascript
const
```
