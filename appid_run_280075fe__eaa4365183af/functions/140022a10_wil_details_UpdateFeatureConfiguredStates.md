# wil_details_UpdateFeatureConfiguredStates

- ea: `0x140022a10`
- end: `0x140022ac0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x140022970`

## callees

- `0x140001760`
- `0x140006a20`
- `0x140022680`
- `0x140022a10`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140022a60`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x140022a60`

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
0x140022a10  push    rbx
0x140022a12  sub     rsp, 50h
0x140022a16  mov     rax, cs:__security_cookie
0x140022a1d  xor     rax, rsp
0x140022a20  mov     [rsp+58h+var_18], rax
0x140022a25  lea     rcx, wil_details_featureDescriptors_a
0x140022a2c  jmp     short loc_140022A9F
0x140022a2e  cmp     byte ptr [rbx+1Dh], 0
0x140022a32  jnz     short loc_140022A9B
0x140022a34  cmp     byte ptr [rbx+1Eh], 0
0x140022a38  jnz     short loc_140022A9B
0x140022a3a  cmp     byte ptr [rbx+1Ch], 0
0x140022a3e  jnz     short loc_140022A9B
0x140022a40  mov     ecx, [rbx+18h]
0x140022a43  lea     r9, [rsp+58h+var_28]
0x140022a48  xor     eax, eax
0x140022a4a  lea     r8, [rsp+58h+var_30]
0x140022a4f  mov     [rsp+58h+var_28], rax
0x140022a54  mov     [rsp+58h+var_20], eax
0x140022a58  mov     [rsp+58h+var_30], rax
0x140022a5d  lea     edx, [rax+1]
0x140022a60  call    cs:__imp_RtlQueryFeatureConfiguration
0x140022a67  nop     dword ptr [rax+rax+00h]
0x140022a6c  lea     r8, [rsp+58h+var_38]
0x140022a71  mov     [rsp+58h+var_38], 0
0x140022a7a  mov     ecx, eax
0x140022a7c  lea     rdx, [rsp+58h+var_28]
0x140022a81  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x140022a86  mov     rcx, [rbx]
0x140022a89  mov     edx, [rcx]
0x140022a8b  xor     edx, dword ptr [rsp+58h+var_38]
0x140022a8f  mov     rax, [rbx]
0x140022a92  and     edx, 0F80h
0x140022a98  lock xor [rax], edx
0x140022a9b  lea     rcx, [rbx+38h]
0x140022a9f  call    wil_details_FeatureDescriptors_SkipPadding
0x140022aa4  mov     rbx, rax
0x140022aa7  test    rax, rax
0x140022aaa  jnz     short loc_140022A2E
0x140022aac  mov     rcx, [rsp+58h+var_18]
0x140022ab1  xor     rcx, rsp; StackCookie
0x140022ab4  call    __security_check_cookie
0x140022ab9  add     rsp, 50h
0x140022abd  pop     rbx
0x140022abe  retn
```
