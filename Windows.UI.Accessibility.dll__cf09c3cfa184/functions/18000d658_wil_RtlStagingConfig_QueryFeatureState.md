# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000d658`
- end: `0x18000d77d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d630`

## callees

- `0x180003980`
- `0x18000d438`
- `0x18000d658`
- `0x180035010`

## string_xrefs

- `0x18000d6a4`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v9; // r8d
  unsigned int v10; // r9d
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+40h] [rbp-28h]

  v15 = 0;
  v7 = a3 == 0;
  v16 = 0;
  v17 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v15, &v16);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v16) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v16);
    v10 = 1;
    v14 = HIDWORD(v16);
    *(_DWORD *)(a1 + 12) = v17;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)a1 = (v14 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v13) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v13 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v13 >> 6) & 1;
  }
LABEL_5:
  if ( a4 )
    *a4 = v9 != -2147483614;
  return v10;
}

```

## disassembly

```asm
0x18000d658  mov     [rsp+arg_10], rbx
0x18000d65d  push    rbp
0x18000d65e  push    rsi
0x18000d65f  push    rdi
0x18000d660  sub     rsp, 50h
0x18000d664  mov     rax, cs:__security_cookie
0x18000d66b  xor     rax, rsp
0x18000d66e  mov     [rsp+68h+var_20], rax
0x18000d673  xor     esi, esi
0x18000d675  mov     [rsp+68h+var_38], 0
0x18000d67e  test    r8d, r8d
0x18000d681  mov     rdi, r9
0x18000d684  mov     ebp, edx
0x18000d686  mov     rbx, rcx
0x18000d689  setz    sil
0x18000d68d  xor     eax, eax
0x18000d68f  mov     [rsp+68h+var_30], rax
0x18000d694  mov     [rsp+68h+var_28], eax
0x18000d698  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000d69f  test    rax, rax
0x18000d6a2  jnz     short loc_18000D6F8
0x18000d6a4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000d6ab  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d6b0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000d6b7  test    rax, rax
0x18000d6ba  jnz     short loc_18000D6F8
0x18000d6bc  mov     r8d, 0C0000139h
0x18000d6c2  xor     r9d, r9d
0x18000d6c5  test    rdi, rdi
0x18000d6c8  jz      short loc_18000D6D8
0x18000d6ca  xor     ecx, ecx
0x18000d6cc  cmp     r8d, 80000022h
0x18000d6d3  setnz   cl
0x18000d6d6  mov     [rdi], ecx
0x18000d6d8  mov     eax, r9d
0x18000d6db  mov     rcx, [rsp+68h+var_20]
0x18000d6e0  xor     rcx, rsp; StackCookie
0x18000d6e3  call    __security_check_cookie
0x18000d6e8  mov     rbx, [rsp+68h+arg_10]
0x18000d6f0  add     rsp, 50h
0x18000d6f4  pop     rdi
0x18000d6f5  pop     rsi
0x18000d6f6  pop     rbp
0x18000d6f7  retn
0x18000d6f8  lea     r9, [rsp+68h+var_30]
0x18000d6fd  mov     edx, esi
0x18000d6ff  lea     r8, [rsp+68h+var_38]
0x18000d704  mov     ecx, ebp
0x18000d706  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d70b  mov     r8d, eax
0x18000d70e  test    eax, eax
0x18000d710  jnz     short loc_18000D75A
0x18000d712  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000d716  lea     r9d, [r8+1]
0x18000d71a  mov     eax, [rsp+68h+var_28]
0x18000d71e  mov     ecx, edx
0x18000d720  mov     [rbx+0Ch], eax
0x18000d723  mov     eax, edx
0x18000d725  shr     eax, 0Eh
0x18000d728  shr     ecx, 4
0x18000d72b  and     eax, 3
0x18000d72e  and     ecx, 3
0x18000d731  mov     [rbx+8], eax
0x18000d734  mov     [rbx], ecx
0x18000d736  mov     eax, edx
0x18000d738  mov     ecx, edx
0x18000d73a  shr     eax, 6
0x18000d73d  shr     ecx, 8
0x18000d740  and     eax, r9d
0x18000d743  and     cl, 3Fh
0x18000d746  shr     edx, 7
0x18000d749  and     edx, r9d
0x18000d74c  mov     [rbx+4], cl
0x18000d74f  mov     [rbx+10h], edx
0x18000d752  mov     [rbx+14h], eax
0x18000d755  jmp     loc_18000D6C5
0x18000d75a  cmp     eax, 117h
0x18000d75f  jnz     loc_18000D6C2
0x18000d765  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000d769  mov     r9d, 1
0x18000d76f  shr     eax, 7
0x18000d772  and     eax, r9d
0x18000d775  mov     [rbx+10h], eax
0x18000d778  jmp     loc_18000D6C5
```
