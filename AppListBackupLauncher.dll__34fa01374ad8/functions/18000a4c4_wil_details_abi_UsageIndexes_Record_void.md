# wil::details_abi::UsageIndexes::Record(void)

- ea: `0x18000a4c4`
- end: `0x18000a5c9`
- name: `?Record@UsageIndexes@details_abi@wil@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180005fc4`
- `0x18000a9c0`
- `0x18000b50c`

## callees

- `0x180002300`
- `0x18000a4c4`
- `0x18000afdc`

## pseudocode

```c
void __fastcall wil::details_abi::UsageIndexes::Record(
        wil::details_abi::UsageIndexes *this,
        __int64 a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  __int64 v5; // [rsp+20h] [rbp-40h] BYREF
  __int64 v6; // [rsp+28h] [rbp-38h]
  __int64 v7; // [rsp+30h] [rbp-30h]
  __int64 v8; // [rsp+38h] [rbp-28h]
  __int64 v9; // [rsp+40h] [rbp-20h]
  __int64 v10; // [rsp+48h] [rbp-18h]

  if ( *((_BYTE *)this + 56) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)3,
      (unsigned __int64)this,
      a4);
  }
  if ( *((_BYTE *)this + 120) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)3,
      (unsigned __int64)this + 64,
      a4);
  }
  if ( *((_BYTE *)this + 184) )
  {
    v5 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1;
    v6 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2;
    v7 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3;
    v8 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4;
    v9 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5;
    v10 = __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6;
    wil::details_abi::RecordWnfUsageIndex(
      (wil::details_abi *)&v5,
      (const struct __WIL__WNF_STATE_NAME *)6,
      (unsigned __int64)this + 128,
      a4);
  }
}

```

## disassembly

```asm
0x18000a4c4  mov     [rsp-8+arg_8], rbx
0x18000a4c9  push    rbp
0x18000a4ca  mov     rbp, rsp
0x18000a4cd  sub     rsp, 60h
0x18000a4d1  mov     rax, cs:__security_cookie
0x18000a4d8  xor     rax, rsp
0x18000a4db  mov     [rbp+var_10], rax
0x18000a4df  cmp     byte ptr [rcx+38h], 0
0x18000a4e3  mov     rbx, rcx
0x18000a4e6  jz      short loc_18000A51A
0x18000a4e8  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1
0x18000a4ef  mov     r8, rcx; unsigned __int64
0x18000a4f2  mov     [rbp+var_40], rax
0x18000a4f6  lea     rcx, [rbp+var_40]; this
0x18000a4fa  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2
0x18000a501  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x18000a506  mov     [rbp+var_38], rax
0x18000a50a  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3
0x18000a511  mov     [rbp+var_30], rax
0x18000a515  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18000a51a  lea     r8, [rbx+40h]; unsigned __int64
0x18000a51e  cmp     byte ptr [r8+38h], 0
0x18000a523  jz      short loc_18000A554
0x18000a525  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1
0x18000a52c  lea     rcx, [rbp+var_40]; this
0x18000a530  mov     [rbp+var_40], rax
0x18000a534  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x18000a539  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2
0x18000a540  mov     [rbp+var_38], rax
0x18000a544  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3
0x18000a54b  mov     [rbp+var_30], rax
0x18000a54f  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18000a554  lea     r8, [rbx+80h]; unsigned __int64
0x18000a55b  cmp     byte ptr [r8+38h], 0
0x18000a560  jz      short loc_18000A5B2
0x18000a562  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1
0x18000a569  lea     rcx, [rbp+var_40]; this
0x18000a56d  mov     [rbp+var_40], rax
0x18000a571  mov     edx, 6; struct __WIL__WNF_STATE_NAME *
0x18000a576  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2
0x18000a57d  mov     [rbp+var_38], rax
0x18000a581  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3
0x18000a588  mov     [rbp+var_30], rax
0x18000a58c  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4
0x18000a593  mov     [rbp+var_28], rax
0x18000a597  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5
0x18000a59e  mov     [rbp+var_20], rax
0x18000a5a2  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6
0x18000a5a9  mov     [rbp+var_18], rax
0x18000a5ad  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18000a5b2  mov     rcx, [rbp+var_10]
0x18000a5b6  xor     rcx, rsp; StackCookie
0x18000a5b9  call    __security_check_cookie
0x18000a5be  mov     rbx, [rsp+60h+arg_8]
0x18000a5c3  add     rsp, 60h
0x18000a5c7  pop     rbp
0x18000a5c8  retn
```
