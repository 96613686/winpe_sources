# wil_details_UpdateFeatureConfiguredStates

- ea: `0x14000b8c0`
- end: `0x14000b970`
- name: `wil_details_UpdateFeatureConfiguredStates`
- size: `176`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x14000b820`

## callees

- `0x1400018fc`
- `0x1400026d0`
- `0x14000b534`
- `0x14000b8c0`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b910`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14000b910`

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
0x14000b8c0  push    rbx
0x14000b8c2  sub     rsp, 50h
0x14000b8c6  mov     rax, cs:__security_cookie
0x14000b8cd  xor     rax, rsp
0x14000b8d0  mov     [rsp+58h+var_18], rax
0x14000b8d5  lea     rcx, wil_details_featureDescriptors_a
0x14000b8dc  jmp     short loc_14000B94F
0x14000b8de  cmp     byte ptr [rbx+1Dh], 0
0x14000b8e2  jnz     short loc_14000B94B
0x14000b8e4  cmp     byte ptr [rbx+1Eh], 0
0x14000b8e8  jnz     short loc_14000B94B
0x14000b8ea  cmp     byte ptr [rbx+1Ch], 0
0x14000b8ee  jnz     short loc_14000B94B
0x14000b8f0  mov     ecx, [rbx+18h]
0x14000b8f3  lea     r9, [rsp+58h+var_28]
0x14000b8f8  xor     eax, eax
0x14000b8fa  lea     r8, [rsp+58h+var_30]
0x14000b8ff  mov     [rsp+58h+var_28], rax
0x14000b904  mov     [rsp+58h+var_20], eax
0x14000b908  mov     [rsp+58h+var_30], rax
0x14000b90d  lea     edx, [rax+1]
0x14000b910  call    cs:__imp_RtlQueryFeatureConfiguration
0x14000b917  nop     dword ptr [rax+rax+00h]
0x14000b91c  lea     r8, [rsp+58h+var_38]
0x14000b921  mov     [rsp+58h+var_38], 0
0x14000b92a  mov     ecx, eax
0x14000b92c  lea     rdx, [rsp+58h+var_28]
0x14000b931  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14000b936  mov     rcx, [rbx]
0x14000b939  mov     edx, [rcx]
0x14000b93b  xor     edx, dword ptr [rsp+58h+var_38]
0x14000b93f  mov     rax, [rbx]
0x14000b942  and     edx, 0F80h
0x14000b948  lock xor [rax], edx
0x14000b94b  lea     rcx, [rbx+38h]
0x14000b94f  call    wil_details_FeatureDescriptors_SkipPadding
0x14000b954  mov     rbx, rax
0x14000b957  test    rax, rax
0x14000b95a  jnz     short loc_14000B8DE
0x14000b95c  mov     rcx, [rsp+58h+var_18]
0x14000b961  xor     rcx, rsp; StackCookie
0x14000b964  call    __security_check_cookie
0x14000b969  add     rsp, 50h
0x14000b96d  pop     rbx
0x14000b96e  retn
```
