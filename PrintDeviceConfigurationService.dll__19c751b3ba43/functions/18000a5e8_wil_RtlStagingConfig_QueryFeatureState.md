# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000a5e8`
- end: `0x18000a70d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000697c`

## callees

- `0x1800020c0`
- `0x18000a360`
- `0x18000a5e8`
- `0x180018010`

## string_xrefs

- `0x18000a634`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  FARPROC NtDllProcedureAddress; // rax
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
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
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
0x18000a5e8  mov     [rsp+arg_10], rbx
0x18000a5ed  push    rbp
0x18000a5ee  push    rsi
0x18000a5ef  push    rdi
0x18000a5f0  sub     rsp, 50h
0x18000a5f4  mov     rax, cs:__security_cookie
0x18000a5fb  xor     rax, rsp
0x18000a5fe  mov     [rsp+68h+var_20], rax
0x18000a603  xor     esi, esi
0x18000a605  mov     [rsp+68h+var_38], 0
0x18000a60e  test    r8d, r8d
0x18000a611  mov     rdi, r9
0x18000a614  mov     ebp, edx
0x18000a616  mov     rbx, rcx
0x18000a619  setz    sil
0x18000a61d  xor     eax, eax
0x18000a61f  mov     [rsp+68h+var_30], rax
0x18000a624  mov     [rsp+68h+var_28], eax
0x18000a628  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000a62f  test    rax, rax
0x18000a632  jnz     short loc_18000A688
0x18000a634  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000a63b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a640  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000a647  test    rax, rax
0x18000a64a  jnz     short loc_18000A688
0x18000a64c  mov     r8d, 0C0000139h
0x18000a652  xor     r9d, r9d
0x18000a655  test    rdi, rdi
0x18000a658  jz      short loc_18000A668
0x18000a65a  xor     ecx, ecx
0x18000a65c  cmp     r8d, 80000022h
0x18000a663  setnz   cl
0x18000a666  mov     [rdi], ecx
0x18000a668  mov     eax, r9d
0x18000a66b  mov     rcx, [rsp+68h+var_20]
0x18000a670  xor     rcx, rsp; StackCookie
0x18000a673  call    __security_check_cookie
0x18000a678  mov     rbx, [rsp+68h+arg_10]
0x18000a680  add     rsp, 50h
0x18000a684  pop     rdi
0x18000a685  pop     rsi
0x18000a686  pop     rbp
0x18000a687  retn
0x18000a688  lea     r9, [rsp+68h+var_30]
0x18000a68d  mov     edx, esi
0x18000a68f  lea     r8, [rsp+68h+var_38]
0x18000a694  mov     ecx, ebp
0x18000a696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a69b  mov     r8d, eax
0x18000a69e  test    eax, eax
0x18000a6a0  jnz     short loc_18000A6EA
0x18000a6a2  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000a6a6  lea     r9d, [r8+1]
0x18000a6aa  mov     eax, [rsp+68h+var_28]
0x18000a6ae  mov     ecx, edx
0x18000a6b0  mov     [rbx+0Ch], eax
0x18000a6b3  mov     eax, edx
0x18000a6b5  shr     eax, 0Eh
0x18000a6b8  shr     ecx, 4
0x18000a6bb  and     eax, 3
0x18000a6be  and     ecx, 3
0x18000a6c1  mov     [rbx+8], eax
0x18000a6c4  mov     [rbx], ecx
0x18000a6c6  mov     eax, edx
0x18000a6c8  mov     ecx, edx
0x18000a6ca  shr     eax, 6
0x18000a6cd  shr     ecx, 8
0x18000a6d0  and     eax, r9d
0x18000a6d3  and     cl, 3Fh
0x18000a6d6  shr     edx, 7
0x18000a6d9  and     edx, r9d
0x18000a6dc  mov     [rbx+4], cl
0x18000a6df  mov     [rbx+10h], edx
0x18000a6e2  mov     [rbx+14h], eax
0x18000a6e5  jmp     loc_18000A655
0x18000a6ea  cmp     eax, 117h
0x18000a6ef  jnz     loc_18000A652
0x18000a6f5  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000a6f9  mov     r9d, 1
0x18000a6ff  shr     eax, 7
0x18000a702  and     eax, r9d
0x18000a705  mov     [rbx+10h], eax
0x18000a708  jmp     loc_18000A655
```
