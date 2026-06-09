# wil_details_PopulateInitialConfiguredFeatureStates

- ea: `0x14008c0fc`
- end: `0x14008c1db`
- name: `wil_details_PopulateInitialConfiguredFeatureStates`
- size: `223`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14008c03c`

## callees

- `0x14003cdc8`
- `0x14005c7d0`
- `0x14008472c`
- `0x14008c0fc`

## import_xrefs

- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14008c15d`
- `ntoskrnl!RtlQueryFeatureConfiguration` at `0x14008c15d`

## pseudocode

```c
__int64 wil_details_PopulateInitialConfiguredFeatureStates()
{
  __int64 **i; // rcx
  __int64 result; // rax
  _QWORD **v2; // rbx
  unsigned int v3; // eax
  __int64 v4; // rdx
  __int64 v5; // [rsp+20h] [rbp-38h] BYREF
  __int64 v6; // [rsp+28h] [rbp-30h] BYREF
  __int64 v7; // [rsp+30h] [rbp-28h] BYREF
  int v8; // [rsp+38h] [rbp-20h]

  for ( i = wil_details_featureDescriptors_a; ; i = v2 + 7 )
  {
    result = wil_details_FeatureDescriptors_SkipPadding(i);
    v2 = (_QWORD **)result;
    if ( !result )
      break;
    v7 = 0;
    v8 = 0;
    v6 = 0;
    v5 = 0;
    if ( *(_BYTE *)(result + 29) || *(_BYTE *)(result + 30) )
    {
      v3 = -1073741275;
    }
    else
    {
      v3 = RtlQueryFeatureConfiguration(
             *(unsigned int *)(result + 24),
             (unsigned __int8)(*(_BYTE *)(result + 28) - 2) > 1u,
             &v6,
             &v7);
      if ( v3 == -2147483614 )
      {
        v5 = 518;
        v4 = 518;
        do
        {
          **v2 = v4;
          result = wil_details_FeatureDescriptors_SkipPadding(v2 + 7);
          v2 = (_QWORD **)result;
        }
        while ( result );
        return result;
      }
    }
    wil_details_BuildFeatureStateCacheFromQueryResults(v3, &v7, &v5);
    **v2 = v5;
  }
  return result;
}

```

## disassembly

```asm
0x14008c0fc  push    rbx
0x14008c0fe  sub     rsp, 50h
0x14008c102  mov     rax, cs:__security_cookie
0x14008c109  xor     rax, rsp
0x14008c10c  mov     [rsp+58h+var_18], rax
0x14008c111  lea     rcx, wil_details_featureDescriptors_a
0x14008c118  call    wil_details_FeatureDescriptors_SkipPadding
0x14008c11d  mov     rbx, rax
0x14008c120  test    rax, rax
0x14008c123  jz      short loc_14008C19D
0x14008c125  xor     eax, eax
0x14008c127  mov     [rsp+58h+var_28], rax
0x14008c12c  mov     [rsp+58h+var_20], eax
0x14008c130  mov     [rsp+58h+var_30], rax
0x14008c135  mov     [rsp+58h+var_38], rax
0x14008c13a  cmp     [rbx+1Dh], al
0x14008c13d  jnz     short loc_14008C1B1
0x14008c13f  cmp     [rbx+1Eh], al
0x14008c142  jnz     short loc_14008C1B1
0x14008c144  mov     al, [rbx+1Ch]
0x14008c147  lea     r9, [rsp+58h+var_28]
0x14008c14c  mov     ecx, [rbx+18h]
0x14008c14f  lea     r8, [rsp+58h+var_30]
0x14008c154  xor     edx, edx
0x14008c156  sub     al, 2
0x14008c158  cmp     al, 1
0x14008c15a  setnbe  dl
0x14008c15d  call    cs:__imp_RtlQueryFeatureConfiguration
0x14008c164  nop     dword ptr [rax+rax+00h]
0x14008c169  cmp     eax, 80000022h
0x14008c16e  jnz     short loc_14008C1B6
0x14008c170  mov     [rsp+58h+var_38], 0
0x14008c179  mov     dword ptr [rsp+58h+var_38], 206h
0x14008c181  mov     rdx, [rsp+58h+var_38]
0x14008c186  mov     rax, [rbx]
0x14008c189  lea     rcx, [rbx+38h]
0x14008c18d  mov     [rax], rdx
0x14008c190  call    wil_details_FeatureDescriptors_SkipPadding
0x14008c195  mov     rbx, rax
0x14008c198  test    rax, rax
0x14008c19b  jnz     short loc_14008C186
0x14008c19d  mov     rcx, [rsp+58h+var_18]
0x14008c1a2  xor     rcx, rsp; StackCookie
0x14008c1a5  call    __security_check_cookie
0x14008c1aa  add     rsp, 50h
0x14008c1ae  pop     rbx
0x14008c1af  retn
0x14008c1b1  mov     eax, 0C0000225h
0x14008c1b6  lea     r8, [rsp+58h+var_38]
0x14008c1bb  mov     ecx, eax
0x14008c1bd  lea     rdx, [rsp+58h+var_28]
0x14008c1c2  call    wil_details_BuildFeatureStateCacheFromQueryResults
0x14008c1c7  mov     rcx, [rbx]
0x14008c1ca  mov     rax, [rsp+58h+var_38]
0x14008c1cf  mov     [rcx], rax
0x14008c1d2  lea     rcx, [rbx+38h]
0x14008c1d6  jmp     loc_14008C118
```
