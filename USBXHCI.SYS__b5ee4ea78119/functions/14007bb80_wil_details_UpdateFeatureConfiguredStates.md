# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14007bb80`
- end: `0x14007bc30`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14007bae0`

## callees

- `0x140046e28`
- `0x140059970`
- `0x14007b84c`
- `0x14007bb80`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14007bbd0`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14007bbd0`

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
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = &wil_details_featureDescriptors_a; ; i = (_UNKNOWN **)(v4 + 7) )
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
0x14007bb80  push    rbx
0x14007bb82  sub     rsp, 50h
0x14007bb86  mov     rax, cs:__security_cookie
0x14007bb8d  xor     rax, rsp
0x14007bb90  mov     [rsp+58h+var_18], rax
0x14007bb95  lea     rcx, wil_details_featureDescriptors_a
0x14007bb9c  jmp     short loc_14007BC0F
0x14007bb9e  cmp     byte ptr [rbx+1Dh], 0
0x14007bba2  jnz     short loc_14007BC0B
0x14007bba4  cmp     byte ptr [rbx+1Eh], 0
0x14007bba8  jnz     short loc_14007BC0B
0x14007bbaa  cmp     byte ptr [rbx+1Ch], 0
0x14007bbae  jnz     short loc_14007BC0B
0x14007bbb0  mov     ecx, [rbx+18h]
0x14007bbb3  lea     r9, [rsp+58h+var_28]
0x14007bbb8  xor     eax, eax
0x14007bbba  lea     r8, [rsp+58h+var_30]
0x14007bbbf  mov     [rsp+58h+var_28], rax
0x14007bbc4  mov     [rsp+58h+var_20], eax
0x14007bbc8  mov     [rsp+58h+var_30], rax
0x14007bbcd  lea     edx, [rax+1]
0x14007bbd0  call    cs:__imp_RtlQueryFeatureConfiguration
0x14007bbd7  nop     dword ptr [rax+rax+00h]
0x14007bbdc  lea     r8, [rsp+58h+var_38]
0x14007bbe1  mov     [rsp+58h+var_38], 0
0x14007bbea  mov     ecx, eax
0x14007bbec  lea     rdx, [rsp+58h+var_28]
0x14007bbf1  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14007bbf6  mov     rcx, [rbx]
0x14007bbf9  mov     edx, [rcx]
0x14007bbfb  xor     edx, dword ptr [rsp+58h+var_38]
0x14007bbff  mov     rax, [rbx]
0x14007bc02  and     edx, 0F80h
0x14007bc08  lock xor [rax], edx
0x14007bc0b  lea     rcx, [rbx+38h]
0x14007bc0f  call    wil_details_FeatureDescriptors_SkipPadding
0x14007bc14  mov     rbx, rax
0x14007bc17  test    rax, rax
0x14007bc1a  jnz     short loc_14007BB9E
0x14007bc1c  mov     rcx, [rsp+58h+var_18]
0x14007bc21  xor     rcx, rsp; StackCookie
0x14007bc24  call    __security_check_cookie
0x14007bc29  add     rsp, 50h
0x14007bc2d  pop     rbx
0x14007bc2e  retn
```
