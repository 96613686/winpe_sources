# wil_details_UpdateFeatureConfiguredStates

- ea: `0x180052f1c`
- end: `0x180052fcc`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x180052e60`

## callees

- `0x18000cec4`
- `0x1800203c0`
- `0x180052bcc`
- `0x180052f1c`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180052f6c`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x180052f6c`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  _UNKNOWN **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  int v7; // [rsp+30h] [rbp-28h]
  __int64 v8; // [rsp+38h] [rbp-20h] BYREF

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*(_BYTE *)(result + 29) && !*(_BYTE *)(result + 30) && !*(_BYTE *)(result + 28) )
    {
      v1 = *(unsigned int *)(result + 24);
      v6 = 0;
      v7 = 0;
      v8 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v8, &v6);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, &v6, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180052f1c  push    rbx
0x180052f1e  sub     rsp, 50h
0x180052f22  mov     rax, cs:__security_cookie
0x180052f29  xor     rax, rsp
0x180052f2c  mov     [rsp+58h+var_18], rax
0x180052f31  lea     rcx, wil_details_featureDescriptors_a
0x180052f38  jmp     short loc_180052FAB
0x180052f3a  cmp     byte ptr [rbx+1Dh], 0
0x180052f3e  jnz     short loc_180052FA7
0x180052f40  cmp     byte ptr [rbx+1Eh], 0
0x180052f44  jnz     short loc_180052FA7
0x180052f46  cmp     byte ptr [rbx+1Ch], 0
0x180052f4a  jnz     short loc_180052FA7
0x180052f4c  mov     ecx, [rbx+18h]
0x180052f4f  lea     r9, [rsp+58h+var_30]
0x180052f54  xor     eax, eax
0x180052f56  lea     r8, [rsp+58h+var_20]
0x180052f5b  mov     [rsp+58h+var_30], rax
0x180052f60  mov     [rsp+58h+var_28], eax
0x180052f64  mov     [rsp+58h+var_20], rax
0x180052f69  lea     edx, [rax+1]
0x180052f6c  call    cs:__imp_RtlQueryFeatureConfiguration
0x180052f73  nop     dword ptr [rax+rax+00h]
0x180052f78  lea     r8, [rsp+58h+var_38]
0x180052f7d  mov     [rsp+58h+var_38], 0
0x180052f86  mov     ecx, eax
0x180052f88  lea     rdx, [rsp+58h+var_30]
0x180052f8d  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x180052f92  mov     rcx, [rbx]
0x180052f95  mov     edx, [rcx]
0x180052f97  xor     edx, dword ptr [rsp+58h+var_38]
0x180052f9b  mov     rax, [rbx]
0x180052f9e  and     edx, 0F80h
0x180052fa4  lock xor [rax], edx
0x180052fa7  lea     rcx, [rbx+38h]
0x180052fab  call    wil_details_FeatureDescriptors_SkipPadding
0x180052fb0  mov     rbx, rax
0x180052fb3  test    rax, rax
0x180052fb6  jnz     short loc_180052F3A
0x180052fb8  mov     rcx, [rsp+58h+var_18]
0x180052fbd  xor     rcx, rsp; StackCookie
0x180052fc0  call    __security_check_cookie
0x180052fc5  add     rsp, 50h
0x180052fc9  pop     rbx
0x180052fca  retn
```
