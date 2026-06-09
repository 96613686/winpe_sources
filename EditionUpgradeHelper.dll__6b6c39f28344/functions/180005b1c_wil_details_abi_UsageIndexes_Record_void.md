# wil::details_abi::UsageIndexes::Record(void)

- ea: `0x180005b1c`
- end: `0x180005c21`
- name: `?Record@UsageIndexes@details_abi@wil@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003224`
- `0x180005e1c`
- `0x180006920`

## callees

- `0x1800018e0`
- `0x180005b1c`
- `0x180006434`

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
0x180005b1c  mov     [rsp-8+arg_8], rbx
0x180005b21  push    rbp
0x180005b22  mov     rbp, rsp
0x180005b25  sub     rsp, 60h
0x180005b29  mov     rax, cs:__security_cookie
0x180005b30  xor     rax, rsp
0x180005b33  mov     [rbp+var_10], rax
0x180005b37  cmp     byte ptr [rcx+38h], 0
0x180005b3b  mov     rbx, rcx
0x180005b3e  jz      short loc_180005B72
0x180005b40  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1
0x180005b47  mov     r8, rcx; unsigned __int64
0x180005b4a  mov     [rbp+var_40], rax
0x180005b4e  lea     rcx, [rbp+var_40]; this
0x180005b52  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2
0x180005b59  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x180005b5e  mov     [rbp+var_38], rax
0x180005b62  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3
0x180005b69  mov     [rbp+var_30], rax
0x180005b6d  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x180005b72  lea     r8, [rbx+40h]; unsigned __int64
0x180005b76  cmp     byte ptr [r8+38h], 0
0x180005b7b  jz      short loc_180005BAC
0x180005b7d  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1
0x180005b84  lea     rcx, [rbp+var_40]; this
0x180005b88  mov     [rbp+var_40], rax
0x180005b8c  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x180005b91  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2
0x180005b98  mov     [rbp+var_38], rax
0x180005b9c  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3
0x180005ba3  mov     [rbp+var_30], rax
0x180005ba7  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x180005bac  lea     r8, [rbx+80h]; unsigned __int64
0x180005bb3  cmp     byte ptr [r8+38h], 0
0x180005bb8  jz      short loc_180005C0A
0x180005bba  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1
0x180005bc1  lea     rcx, [rbp+var_40]; this
0x180005bc5  mov     [rbp+var_40], rax
0x180005bc9  mov     edx, 6; struct __WIL__WNF_STATE_NAME *
0x180005bce  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2
0x180005bd5  mov     [rbp+var_38], rax
0x180005bd9  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3
0x180005be0  mov     [rbp+var_30], rax
0x180005be4  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4
0x180005beb  mov     [rbp+var_28], rax
0x180005bef  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5
0x180005bf6  mov     [rbp+var_20], rax
0x180005bfa  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6
0x180005c01  mov     [rbp+var_18], rax
0x180005c05  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x180005c0a  mov     rcx, [rbp+var_10]
0x180005c0e  xor     rcx, rsp; StackCookie
0x180005c11  call    __security_check_cookie
0x180005c16  mov     rbx, [rsp+60h+arg_8]
0x180005c1b  add     rsp, 60h
0x180005c1f  pop     rbp
0x180005c20  retn
```
