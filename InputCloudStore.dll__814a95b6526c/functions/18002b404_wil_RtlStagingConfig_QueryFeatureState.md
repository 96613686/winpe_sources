# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002b404`
- end: `0x18002b529`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002b3dc`

## callees

- `0x180003560`
- `0x180007aa0`
- `0x18002b404`
- `0x180031010`

## string_xrefs

- `0x18002b450`: `RtlQueryFeatureConfiguration`

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
0x18002b404  mov     [rsp+arg_10], rbx
0x18002b409  push    rbp
0x18002b40a  push    rsi
0x18002b40b  push    rdi
0x18002b40c  sub     rsp, 50h
0x18002b410  mov     rax, cs:__security_cookie
0x18002b417  xor     rax, rsp
0x18002b41a  mov     [rsp+68h+var_20], rax
0x18002b41f  xor     esi, esi
0x18002b421  mov     [rsp+68h+var_38], 0
0x18002b42a  test    r8d, r8d
0x18002b42d  mov     rdi, r9
0x18002b430  mov     ebp, edx
0x18002b432  mov     rbx, rcx
0x18002b435  setz    sil
0x18002b439  xor     eax, eax
0x18002b43b  mov     [rsp+68h+var_30], rax
0x18002b440  mov     [rsp+68h+var_28], eax
0x18002b444  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002b44b  test    rax, rax
0x18002b44e  jnz     short loc_18002B4A4
0x18002b450  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002b457  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002b45c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002b463  test    rax, rax
0x18002b466  jnz     short loc_18002B4A4
0x18002b468  mov     r8d, 0C0000139h
0x18002b46e  xor     r9d, r9d
0x18002b471  test    rdi, rdi
0x18002b474  jz      short loc_18002B484
0x18002b476  xor     ecx, ecx
0x18002b478  cmp     r8d, 80000022h
0x18002b47f  setnz   cl
0x18002b482  mov     [rdi], ecx
0x18002b484  mov     eax, r9d
0x18002b487  mov     rcx, [rsp+68h+var_20]
0x18002b48c  xor     rcx, rsp; StackCookie
0x18002b48f  call    __security_check_cookie
0x18002b494  mov     rbx, [rsp+68h+arg_10]
0x18002b49c  add     rsp, 50h
0x18002b4a0  pop     rdi
0x18002b4a1  pop     rsi
0x18002b4a2  pop     rbp
0x18002b4a3  retn
0x18002b4a4  lea     r9, [rsp+68h+var_30]
0x18002b4a9  mov     edx, esi
0x18002b4ab  lea     r8, [rsp+68h+var_38]
0x18002b4b0  mov     ecx, ebp
0x18002b4b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b4b7  mov     r8d, eax
0x18002b4ba  test    eax, eax
0x18002b4bc  jnz     short loc_18002B506
0x18002b4be  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002b4c2  lea     r9d, [r8+1]
0x18002b4c6  mov     eax, [rsp+68h+var_28]
0x18002b4ca  mov     ecx, edx
0x18002b4cc  mov     [rbx+0Ch], eax
0x18002b4cf  mov     eax, edx
0x18002b4d1  shr     eax, 0Eh
0x18002b4d4  shr     ecx, 4
0x18002b4d7  and     eax, 3
0x18002b4da  and     ecx, 3
0x18002b4dd  mov     [rbx+8], eax
0x18002b4e0  mov     [rbx], ecx
0x18002b4e2  mov     eax, edx
0x18002b4e4  mov     ecx, edx
0x18002b4e6  shr     eax, 6
0x18002b4e9  shr     ecx, 8
0x18002b4ec  and     eax, r9d
0x18002b4ef  and     cl, 3Fh
0x18002b4f2  shr     edx, 7
0x18002b4f5  and     edx, r9d
0x18002b4f8  mov     [rbx+4], cl
0x18002b4fb  mov     [rbx+10h], edx
0x18002b4fe  mov     [rbx+14h], eax
0x18002b501  jmp     loc_18002B471
0x18002b506  cmp     eax, 117h
0x18002b50b  jnz     loc_18002B46E
0x18002b511  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002b515  mov     r9d, 1
0x18002b51b  shr     eax, 7
0x18002b51e  and     eax, r9d
0x18002b521  mov     [rbx+10h], eax
0x18002b524  jmp     loc_18002B471
```
