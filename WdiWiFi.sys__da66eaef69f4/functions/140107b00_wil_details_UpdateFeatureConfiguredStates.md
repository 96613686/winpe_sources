# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140107b00`
- end: `0x140107bb0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140107a60`

## callees

- `0x1400c6138`
- `0x1400da4f0`
- `0x14010777c`
- `0x140107b00`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140107b50`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140107b50`

## pseudocode

```c
__int64 wil_details_UpdateFeatureConfiguredStates()
{
  int **i; // rcx
  __int64 v1; // rcx
  unsigned int v2; // eax
  __int64 result; // rax
  volatile signed __int32 **v4; // rbx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = (int **)(v4 + 7) )
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
0x140107b00  push    rbx
0x140107b02  sub     rsp, 50h
0x140107b06  mov     rax, cs:__security_cookie
0x140107b0d  xor     rax, rsp
0x140107b10  mov     [rsp+58h+var_18], rax
0x140107b15  lea     rcx, wil_details_featureDescriptors_a
0x140107b1c  jmp     short loc_140107B8F
0x140107b1e  cmp     byte ptr [rbx+1Dh], 0
0x140107b22  jnz     short loc_140107B8B
0x140107b24  cmp     byte ptr [rbx+1Eh], 0
0x140107b28  jnz     short loc_140107B8B
0x140107b2a  cmp     byte ptr [rbx+1Ch], 0
0x140107b2e  jnz     short loc_140107B8B
0x140107b30  mov     ecx, [rbx+18h]
0x140107b33  lea     r9, [rsp+58h+var_28]
0x140107b38  xor     eax, eax
0x140107b3a  lea     r8, [rsp+58h+var_30]
0x140107b3f  mov     [rsp+58h+var_28], rax
0x140107b44  mov     [rsp+58h+var_20], eax
0x140107b48  mov     [rsp+58h+var_30], rax
0x140107b4d  lea     edx, [rax+1]
0x140107b50  call    cs:__imp_RtlQueryFeatureConfiguration
0x140107b57  nop     dword ptr [rax+rax+00h]
0x140107b5c  lea     r8, [rsp+58h+var_38]
0x140107b61  mov     [rsp+58h+var_38], 0
0x140107b6a  mov     ecx, eax
0x140107b6c  lea     rdx, [rsp+58h+var_28]
0x140107b71  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140107b76  mov     rcx, [rbx]
0x140107b79  mov     edx, [rcx]
0x140107b7b  xor     edx, dword ptr [rsp+58h+var_38]
0x140107b7f  mov     rax, [rbx]
0x140107b82  and     edx, 0F80h
0x140107b88  lock xor [rax], edx
0x140107b8b  lea     rcx, [rbx+38h]
0x140107b8f  call    wil_details_FeatureDescriptors_SkipPadding
0x140107b94  mov     rbx, rax
0x140107b97  test    rax, rax
0x140107b9a  jnz     short loc_140107B1E
0x140107b9c  mov     rcx, [rsp+58h+var_18]
0x140107ba1  xor     rcx, rsp; StackCookie
0x140107ba4  call    __security_check_cookie
0x140107ba9  add     rsp, 50h
0x140107bad  pop     rbx
0x140107bae  retn
```
