<template>
	<view class="content">
		<image class="logo" src="/static/logo.png"></image>
		<view class="text-area">
			<text class="title" @click="onclick">{{title}}</text>
		</view>
	</view>
</template>

<script>

	export default {
		data() {
			return {
				title: 'Hello Uniapp Android12333'
			}
		},
		onLoad() {

		},
		methods: {
			onclick() {
				const testModule = uni.requireNativePlugin('Test-Plugin');
				console.log(testModule)
				uni.showToast({
					title: '点击了'
				})
				// testModule.open(res =>{
				// 	console.log(res)
				// 	this.title = JSON.stringify(res)
				// })
				console.log(1)
				// console.log(testModule.backInt())
				// testModule.backInt()
				testModule.backInt(res =>{
					console.log(2)
					console.log(res)
					this.title = JSON.stringify(res)
				})
			},
		}
	}
</script>

<style>
	.content {
		display: flex;
		flex-direction: column;
		align-items: center;
		justify-content: center;
	}

	.logo {
		height: 200rpx;
		width: 200rpx;
		margin-top: 200rpx;
		margin-left: auto;
		margin-right: auto;
		margin-bottom: 50rpx;
	}

	.text-area {
		display: flex;
		justify-content: center;
	}

	.title {
		font-size: 36rpx;
		color: #8f8f94;
	}
</style>
