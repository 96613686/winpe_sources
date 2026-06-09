# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14001ec70`
- end: `0x14001ed20`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: `__int64 *()`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14001ebd0`

## callees

- `0x140004784`
- `0x140013860`
- `0x14001e8e4`
- `0x14001ec70`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001ecc0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001ecc0`

## pseudocode

```c
__int64 *wil_details_UpdateFeatureConfiguredStates()
{
  __int64 *i; // rcx
  __int64 v1; // rcx
  int v2; // eax
  __int64 *result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = (__int64 *)wil_details_featureDescriptors_a; ; i = (__int64 *)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*((_BYTE *)result + 29) && !*((_BYTE *)result + 30) && !*((_BYTE *)result + 28) )
    {
      v1 = *((unsigned int *)result + 6);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, (__int64)&v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001ec70  push    rbx
0x14001ec72  sub     rsp, 50h
0x14001ec76  mov     rax, cs:__security_cookie
0x14001ec7d  xor     rax, rsp
0x14001ec80  mov     [rsp+58h+var_18], rax
0x14001ec85  lea     rcx, wil_details_featureDescriptors_a
0x14001ec8c  jmp     short loc_14001ECFF
0x14001ec8e  cmp     byte ptr [rbx+1Dh], 0
0x14001ec92  jnz     short loc_14001ECFB
0x14001ec94  cmp     byte ptr [rbx+1Eh], 0
0x14001ec98  jnz     short loc_14001ECFB
0x14001ec9a  cmp     byte ptr [rbx+1Ch], 0
0x14001ec9e  jnz     short loc_14001ECFB
0x14001eca0  mov     ecx, [rbx+18h]
0x14001eca3  lea     r9, [rsp+58h+var_28]
0x14001eca8  xor     eax, eax
0x14001ecaa  lea     r8, [rsp+58h+var_30]
0x14001ecaf  mov     [rsp+58h+var_28], rax
0x14001ecb4  mov     [rsp+58h+var_20], eax
0x14001ecb8  mov     [rsp+58h+var_30], rax
0x14001ecbd  lea     edx, [rax+1]
0x14001ecc0  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001ecc7  nop     dword ptr [rax+rax+00h]
0x14001eccc  lea     r8, [rsp+58h+var_38]
0x14001ecd1  mov     [rsp+58h+var_38], 0
0x14001ecda  mov     ecx, eax
0x14001ecdc  lea     rdx, [rsp+58h+var_28]
0x14001ece1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14001ece6  mov     rcx, [rbx]
0x14001ece9  mov     edx, [rcx]
0x14001eceb  xor     edx, dword ptr [rsp+58h+var_38]
0x14001ecef  mov     rax, [rbx]
0x14001ecf2  and     edx, 0F80h
0x14001ecf8  lock xor [rax], edx
0x14001ecfb  lea     rcx, [rbx+38h]
0x14001ecff  call    wil_details_FeatureDescriptors_SkipPadding
0x14001ed04  mov     rbx, rax
0x14001ed07  test    rax, rax
0x14001ed0a  jnz     short loc_14001EC8E
0x14001ed0c  mov     rcx, [rsp+58h+var_18]
0x14001ed11  xor     rcx, rsp; StackCookie
0x14001ed14  call    __security_check_cookie
0x14001ed19  add     rsp, 50h
0x14001ed1d  pop     rbx
0x14001ed1e  retn
```
