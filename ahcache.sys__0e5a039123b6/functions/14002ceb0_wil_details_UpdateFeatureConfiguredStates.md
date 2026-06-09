# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14002ceb0`
- end: `0x14002cf60`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14002ce10`

## callees

- `0x1400050d8`
- `0x1400079f0`
- `0x14002cb34`
- `0x14002ceb0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002cf00`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14002cf00`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  __int64 **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (__int64 **)(v4 + 7) )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v4 = (volatile signed __int32 **)result;
    if ( !result )
      break;
    if ( !*(_BYTE *)(result + 29) && !*(_BYTE *)(result + 30) && !*(_BYTE *)(result + 28) )
    {
      v1 = *(unsigned int *)(result + 24);
      v7 = 0;
      v8 = 0;
      v6 = 0;
      v2 = RtlQueryFeatureConfiguration(v1, 1, &v6, &v7);
      v5 = 0;
      wil_details_BuildFeatureStateCacheFromQueryResults(v2, &v7, &v5);
      _InterlockedXor(*v4, ((unsigned __int16)v5 ^ (unsigned __int16)**v4) & 0xF80);
    }
  }
  return result;
}

```

## disassembly

```asm
0x14002ceb0  push    rbx
0x14002ceb2  sub     rsp, 50h
0x14002ceb6  mov     rax, cs:__security_cookie
0x14002cebd  xor     rax, rsp
0x14002cec0  mov     [rsp+58h+var_18], rax
0x14002cec5  lea     rcx, wil_details_featureDescriptors_a
0x14002cecc  jmp     short loc_14002CF3F
0x14002cece  cmp     byte ptr [rbx+1Dh], 0
0x14002ced2  jnz     short loc_14002CF3B
0x14002ced4  cmp     byte ptr [rbx+1Eh], 0
0x14002ced8  jnz     short loc_14002CF3B
0x14002ceda  cmp     byte ptr [rbx+1Ch], 0
0x14002cede  jnz     short loc_14002CF3B
0x14002cee0  mov     ecx, [rbx+18h]
0x14002cee3  lea     r9, [rsp+58h+var_28]
0x14002cee8  xor     eax, eax
0x14002ceea  lea     r8, [rsp+58h+var_30]
0x14002ceef  mov     [rsp+58h+var_28], rax
0x14002cef4  mov     [rsp+58h+var_20], eax
0x14002cef8  mov     [rsp+58h+var_30], rax
0x14002cefd  lea     edx, [rax+1]
0x14002cf00  call    cs:__imp_RtlQueryFeatureConfiguration
0x14002cf07  nop     dword ptr [rax+rax+00h]
0x14002cf0c  lea     r8, [rsp+58h+var_38]
0x14002cf11  mov     [rsp+58h+var_38], 0
0x14002cf1a  mov     ecx, eax
0x14002cf1c  lea     rdx, [rsp+58h+var_28]
0x14002cf21  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14002cf26  mov     rcx, [rbx]
0x14002cf29  mov     edx, [rcx]
0x14002cf2b  xor     edx, dword ptr [rsp+58h+var_38]
0x14002cf2f  mov     rax, [rbx]
0x14002cf32  and     edx, 0F80h
0x14002cf38  lock xor [rax], edx
0x14002cf3b  lea     rcx, [rbx+38h]
0x14002cf3f  call    wil_details_FeatureDescriptors_SkipPadding
0x14002cf44  mov     rbx, rax
0x14002cf47  test    rax, rax
0x14002cf4a  jnz     short loc_14002CECE
0x14002cf4c  mov     rcx, [rsp+58h+var_18]
0x14002cf51  xor     rcx, rsp; StackCookie
0x14002cf54  call    __security_check_cookie
0x14002cf59  add     rsp, 50h
0x14002cf5d  pop     rbx
0x14002cf5e  retn
```
