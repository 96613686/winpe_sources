# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002d908`
- end: `0x18002da2d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18002afa4`

## callees

- `0x1800249f0`
- `0x18002d710`
- `0x18002d908`
- `0x18003c010`

## string_xrefs

- `0x18002d954`: `RtlQueryFeatureConfiguration`

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
0x18002d908  mov     [rsp+arg_10], rbx
0x18002d90d  push    rbp
0x18002d90e  push    rsi
0x18002d90f  push    rdi
0x18002d910  sub     rsp, 50h
0x18002d914  mov     rax, cs:__security_cookie
0x18002d91b  xor     rax, rsp
0x18002d91e  mov     [rsp+68h+var_20], rax
0x18002d923  xor     esi, esi
0x18002d925  mov     [rsp+68h+var_38], 0
0x18002d92e  test    r8d, r8d
0x18002d931  mov     rdi, r9
0x18002d934  mov     ebp, edx
0x18002d936  mov     rbx, rcx
0x18002d939  setz    sil
0x18002d93d  xor     eax, eax
0x18002d93f  mov     [rsp+68h+var_30], rax
0x18002d944  mov     [rsp+68h+var_28], eax
0x18002d948  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002d94f  test    rax, rax
0x18002d952  jnz     short loc_18002D9A8
0x18002d954  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002d95b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002d960  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002d967  test    rax, rax
0x18002d96a  jnz     short loc_18002D9A8
0x18002d96c  mov     r8d, 0C0000139h
0x18002d972  xor     r9d, r9d
0x18002d975  test    rdi, rdi
0x18002d978  jz      short loc_18002D988
0x18002d97a  xor     ecx, ecx
0x18002d97c  cmp     r8d, 80000022h
0x18002d983  setnz   cl
0x18002d986  mov     [rdi], ecx
0x18002d988  mov     eax, r9d
0x18002d98b  mov     rcx, [rsp+68h+var_20]
0x18002d990  xor     rcx, rsp; StackCookie
0x18002d993  call    __security_check_cookie
0x18002d998  mov     rbx, [rsp+68h+arg_10]
0x18002d9a0  add     rsp, 50h
0x18002d9a4  pop     rdi
0x18002d9a5  pop     rsi
0x18002d9a6  pop     rbp
0x18002d9a7  retn
0x18002d9a8  lea     r9, [rsp+68h+var_30]
0x18002d9ad  mov     edx, esi
0x18002d9af  lea     r8, [rsp+68h+var_38]
0x18002d9b4  mov     ecx, ebp
0x18002d9b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d9bb  mov     r8d, eax
0x18002d9be  test    eax, eax
0x18002d9c0  jnz     short loc_18002DA0A
0x18002d9c2  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002d9c6  lea     r9d, [r8+1]
0x18002d9ca  mov     eax, [rsp+68h+var_28]
0x18002d9ce  mov     ecx, edx
0x18002d9d0  mov     [rbx+0Ch], eax
0x18002d9d3  mov     eax, edx
0x18002d9d5  shr     eax, 0Eh
0x18002d9d8  shr     ecx, 4
0x18002d9db  and     eax, 3
0x18002d9de  and     ecx, 3
0x18002d9e1  mov     [rbx+8], eax
0x18002d9e4  mov     [rbx], ecx
0x18002d9e6  mov     eax, edx
0x18002d9e8  mov     ecx, edx
0x18002d9ea  shr     eax, 6
0x18002d9ed  shr     ecx, 8
0x18002d9f0  and     eax, r9d
0x18002d9f3  and     cl, 3Fh
0x18002d9f6  shr     edx, 7
0x18002d9f9  and     edx, r9d
0x18002d9fc  mov     [rbx+4], cl
0x18002d9ff  mov     [rbx+10h], edx
0x18002da02  mov     [rbx+14h], eax
0x18002da05  jmp     loc_18002D975
0x18002da0a  cmp     eax, 117h
0x18002da0f  jnz     loc_18002D972
0x18002da15  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002da19  mov     r9d, 1
0x18002da1f  shr     eax, 7
0x18002da22  and     eax, r9d
0x18002da25  mov     [rbx+10h], eax
0x18002da28  jmp     loc_18002D975
```
