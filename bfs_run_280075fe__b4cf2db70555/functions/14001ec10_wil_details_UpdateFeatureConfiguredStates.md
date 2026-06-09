# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14001ec10`
- end: `0x14001ecc0`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14001eb70`

## callees

- `0x1400045b4`
- `0x140013730`
- `0x14001e8e4`
- `0x14001ec10`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001ec60`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14001ec60`

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
0x14001ec10  push    rbx
0x14001ec12  sub     rsp, 50h
0x14001ec16  mov     rax, cs:__security_cookie
0x14001ec1d  xor     rax, rsp
0x14001ec20  mov     [rsp+58h+var_18], rax
0x14001ec25  lea     rcx, wil_details_featureDescriptors_a
0x14001ec2c  jmp     short loc_14001EC9F
0x14001ec2e  cmp     byte ptr [rbx+1Dh], 0
0x14001ec32  jnz     short loc_14001EC9B
0x14001ec34  cmp     byte ptr [rbx+1Eh], 0
0x14001ec38  jnz     short loc_14001EC9B
0x14001ec3a  cmp     byte ptr [rbx+1Ch], 0
0x14001ec3e  jnz     short loc_14001EC9B
0x14001ec40  mov     ecx, [rbx+18h]
0x14001ec43  lea     r9, [rsp+58h+var_28]
0x14001ec48  xor     eax, eax
0x14001ec4a  lea     r8, [rsp+58h+var_30]
0x14001ec4f  mov     [rsp+58h+var_28], rax
0x14001ec54  mov     [rsp+58h+var_20], eax
0x14001ec58  mov     [rsp+58h+var_30], rax
0x14001ec5d  lea     edx, [rax+1]
0x14001ec60  call    cs:__imp_RtlQueryFeatureConfiguration
0x14001ec67  nop     dword ptr [rax+rax+00h]
0x14001ec6c  lea     r8, [rsp+58h+var_38]
0x14001ec71  mov     [rsp+58h+var_38], 0
0x14001ec7a  mov     ecx, eax
0x14001ec7c  lea     rdx, [rsp+58h+var_28]
0x14001ec81  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14001ec86  mov     rcx, [rbx]
0x14001ec89  mov     edx, [rcx]
0x14001ec8b  xor     edx, dword ptr [rsp+58h+var_38]
0x14001ec8f  mov     rax, [rbx]
0x14001ec92  and     edx, 0F80h
0x14001ec98  lock xor [rax], edx
0x14001ec9b  lea     rcx, [rbx+38h]
0x14001ec9f  call    wil_details_FeatureDescriptors_SkipPadding
0x14001eca4  mov     rbx, rax
0x14001eca7  test    rax, rax
0x14001ecaa  jnz     short loc_14001EC2E
0x14001ecac  mov     rcx, [rsp+58h+var_18]
0x14001ecb1  xor     rcx, rsp; StackCookie
0x14001ecb4  call    __security_check_cookie
0x14001ecb9  add     rsp, 50h
0x14001ecbd  pop     rbx
0x14001ecbe  retn
```
