# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800148a8`
- end: `0x1800149cd`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180011b40`

## callees

- `0x18000eb70`
- `0x1800144cc`
- `0x1800148a8`
- `0x180029010`

## string_xrefs

- `0x1800148f4`: `RtlQueryFeatureConfiguration`

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
0x1800148a8  mov     [rsp+arg_10], rbx
0x1800148ad  push    rbp
0x1800148ae  push    rsi
0x1800148af  push    rdi
0x1800148b0  sub     rsp, 50h
0x1800148b4  mov     rax, cs:__security_cookie
0x1800148bb  xor     rax, rsp
0x1800148be  mov     [rsp+68h+var_20], rax
0x1800148c3  xor     esi, esi
0x1800148c5  mov     [rsp+68h+var_38], 0
0x1800148ce  test    r8d, r8d
0x1800148d1  mov     rdi, r9
0x1800148d4  mov     ebp, edx
0x1800148d6  mov     rbx, rcx
0x1800148d9  setz    sil
0x1800148dd  xor     eax, eax
0x1800148df  mov     [rsp+68h+var_30], rax
0x1800148e4  mov     [rsp+68h+var_28], eax
0x1800148e8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800148ef  test    rax, rax
0x1800148f2  jnz     short loc_180014948
0x1800148f4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800148fb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180014900  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180014907  test    rax, rax
0x18001490a  jnz     short loc_180014948
0x18001490c  mov     r8d, 0C0000139h
0x180014912  xor     r9d, r9d
0x180014915  test    rdi, rdi
0x180014918  jz      short loc_180014928
0x18001491a  xor     ecx, ecx
0x18001491c  cmp     r8d, 80000022h
0x180014923  setnz   cl
0x180014926  mov     [rdi], ecx
0x180014928  mov     eax, r9d
0x18001492b  mov     rcx, [rsp+68h+var_20]
0x180014930  xor     rcx, rsp; StackCookie
0x180014933  call    __security_check_cookie
0x180014938  mov     rbx, [rsp+68h+arg_10]
0x180014940  add     rsp, 50h
0x180014944  pop     rdi
0x180014945  pop     rsi
0x180014946  pop     rbp
0x180014947  retn
0x180014948  lea     r9, [rsp+68h+var_30]
0x18001494d  mov     edx, esi
0x18001494f  lea     r8, [rsp+68h+var_38]
0x180014954  mov     ecx, ebp
0x180014956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001495b  mov     r8d, eax
0x18001495e  test    eax, eax
0x180014960  jnz     short loc_1800149AA
0x180014962  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180014966  lea     r9d, [r8+1]
0x18001496a  mov     eax, [rsp+68h+var_28]
0x18001496e  mov     ecx, edx
0x180014970  mov     [rbx+0Ch], eax
0x180014973  mov     eax, edx
0x180014975  shr     eax, 0Eh
0x180014978  shr     ecx, 4
0x18001497b  and     eax, 3
0x18001497e  and     ecx, 3
0x180014981  mov     [rbx+8], eax
0x180014984  mov     [rbx], ecx
0x180014986  mov     eax, edx
0x180014988  mov     ecx, edx
0x18001498a  shr     eax, 6
0x18001498d  shr     ecx, 8
0x180014990  and     eax, r9d
0x180014993  and     cl, 3Fh
0x180014996  shr     edx, 7
0x180014999  and     edx, r9d
0x18001499c  mov     [rbx+4], cl
0x18001499f  mov     [rbx+10h], edx
0x1800149a2  mov     [rbx+14h], eax
0x1800149a5  jmp     loc_180014915
0x1800149aa  cmp     eax, 117h
0x1800149af  jnz     loc_180014912
0x1800149b5  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800149b9  mov     r9d, 1
0x1800149bf  shr     eax, 7
0x1800149c2  and     eax, r9d
0x1800149c5  mov     [rbx+10h], eax
0x1800149c8  jmp     loc_180014915
```
