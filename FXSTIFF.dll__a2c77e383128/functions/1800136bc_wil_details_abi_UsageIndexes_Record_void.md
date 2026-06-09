# wil::details_abi::UsageIndexes::Record(void)

- ea: `0x1800136bc`
- end: `0x1800137c1`
- name: `?Record@UsageIndexes@details_abi@wil@@QEAAXXZ`
- size: `261`
- prototype: `void __fastcall(wil::details_abi::UsageIndexes *this, __int64, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180010920`
- `0x1800139c0`
- `0x180014484`

## callees

- `0x1800136bc`
- `0x180013f90`
- `0x180017c00`

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
0x1800136bc  mov     [rsp-8+arg_8], rbx
0x1800136c1  push    rbp
0x1800136c2  mov     rbp, rsp
0x1800136c5  sub     rsp, 60h
0x1800136c9  mov     rax, cs:__security_cookie
0x1800136d0  xor     rax, rsp
0x1800136d3  mov     [rbp+var_10], rax
0x1800136d7  cmp     byte ptr [rcx+38h], 0
0x1800136db  mov     rbx, rcx
0x1800136de  jz      short loc_180013712
0x1800136e0  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_1
0x1800136e7  mov     r8, rcx; unsigned __int64
0x1800136ea  mov     [rbp+var_40], rax
0x1800136ee  lea     rcx, [rbp+var_40]; this
0x1800136f2  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_2
0x1800136f9  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x1800136fe  mov     [rbp+var_38], rax
0x180013702  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_DEVICE_USAGE_TRACKING_3
0x180013709  mov     [rbp+var_30], rax
0x18001370d  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x180013712  lea     r8, [rbx+40h]; unsigned __int64
0x180013716  cmp     byte ptr [r8+38h], 0
0x18001371b  jz      short loc_18001374C
0x18001371d  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_1
0x180013724  lea     rcx, [rbp+var_40]; this
0x180013728  mov     [rbp+var_40], rax
0x18001372c  mov     edx, 3; struct __WIL__WNF_STATE_NAME *
0x180013731  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_2
0x180013738  mov     [rbp+var_38], rax
0x18001373c  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_TRACKING_3
0x180013743  mov     [rbp+var_30], rax
0x180013747  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x18001374c  lea     r8, [rbx+80h]; unsigned __int64
0x180013753  cmp     byte ptr [r8+38h], 0
0x180013758  jz      short loc_1800137AA
0x18001375a  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_1
0x180013761  lea     rcx, [rbp+var_40]; this
0x180013765  mov     [rbp+var_40], rax
0x180013769  mov     edx, 6; struct __WIL__WNF_STATE_NAME *
0x18001376e  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_2
0x180013775  mov     [rbp+var_38], rax
0x180013779  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_3
0x180013780  mov     [rbp+var_30], rax
0x180013784  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_4
0x18001378b  mov     [rbp+var_28], rax
0x18001378f  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_5
0x180013796  mov     [rbp+var_20], rax
0x18001379a  mov     rax, cs:?__WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_HEALTH_TRACKING_6
0x1800137a1  mov     [rbp+var_18], rax
0x1800137a5  call    ?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z; wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)
0x1800137aa  mov     rcx, [rbp+var_10]
0x1800137ae  xor     rcx, rsp; StackCookie
0x1800137b1  call    __security_check_cookie
0x1800137b6  mov     rbx, [rsp+60h+arg_8]
0x1800137bb  add     rsp, 60h
0x1800137bf  pop     rbp
0x1800137c0  retn
```
