# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180038e74`
- end: `0x180038f9a`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180038e4c`
- `0x180039708`

## callees

- `0x180006f60`
- `0x18000c6dc`
- `0x180038e74`
- `0x18003f010`

## string_xrefs

- `0x180038ec0`: `RtlQueryFeatureConfiguration`

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
0x180038e74  mov     [rsp+arg_10], rbx
0x180038e79  push    rbp
0x180038e7a  push    rsi
0x180038e7b  push    rdi
0x180038e7c  sub     rsp, 50h
0x180038e80  mov     rax, cs:__security_cookie
0x180038e87  xor     rax, rsp
0x180038e8a  mov     [rsp+68h+var_20], rax
0x180038e8f  xor     esi, esi
0x180038e91  mov     [rsp+68h+var_38], 0
0x180038e9a  test    r8d, r8d
0x180038e9d  mov     rdi, r9
0x180038ea0  mov     ebp, edx
0x180038ea2  mov     rbx, rcx
0x180038ea5  setz    sil
0x180038ea9  xor     eax, eax
0x180038eab  mov     [rsp+68h+var_30], rax
0x180038eb0  mov     [rsp+68h+var_28], eax
0x180038eb4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180038ebb  test    rax, rax
0x180038ebe  jnz     short loc_180038F15
0x180038ec0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180038ec7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180038ecc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180038ed3  test    rax, rax
0x180038ed6  jnz     short loc_180038F15
0x180038ed8  mov     r8d, 0C0000139h
0x180038ede  xor     r9d, r9d
0x180038ee1  test    rdi, rdi
0x180038ee4  jz      short loc_180038EF4
0x180038ee6  xor     ecx, ecx
0x180038ee8  cmp     r8d, 80000022h
0x180038eef  setnz   cl
0x180038ef2  mov     [rdi], ecx
0x180038ef4  mov     eax, r9d
0x180038ef7  mov     rcx, [rsp+68h+var_20]
0x180038efc  xor     rcx, rsp; StackCookie
0x180038eff  call    __security_check_cookie
0x180038f04  mov     rbx, [rsp+68h+arg_10]
0x180038f0c  add     rsp, 50h
0x180038f10  pop     rdi
0x180038f11  pop     rsi
0x180038f12  pop     rbp
0x180038f13  retn
0x180038f15  lea     r9, [rsp+68h+var_30]
0x180038f1a  mov     edx, esi
0x180038f1c  lea     r8, [rsp+68h+var_38]
0x180038f21  mov     ecx, ebp
0x180038f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180038f28  mov     r8d, eax
0x180038f2b  test    eax, eax
0x180038f2d  jnz     short loc_180038F77
0x180038f2f  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180038f33  lea     r9d, [r8+1]
0x180038f37  mov     eax, [rsp+68h+var_28]
0x180038f3b  mov     ecx, edx
0x180038f3d  mov     [rbx+0Ch], eax
0x180038f40  mov     eax, edx
0x180038f42  shr     eax, 0Eh
0x180038f45  shr     ecx, 4
0x180038f48  and     eax, 3
0x180038f4b  and     ecx, 3
0x180038f4e  mov     [rbx+8], eax
0x180038f51  mov     [rbx], ecx
0x180038f53  mov     eax, edx
0x180038f55  mov     ecx, edx
0x180038f57  shr     eax, 6
0x180038f5a  shr     ecx, 8
0x180038f5d  and     eax, r9d
0x180038f60  and     cl, 3Fh
0x180038f63  shr     edx, 7
0x180038f66  and     edx, r9d
0x180038f69  mov     [rbx+4], cl
0x180038f6c  mov     [rbx+10h], edx
0x180038f6f  mov     [rbx+14h], eax
0x180038f72  jmp     loc_180038EE1
0x180038f77  cmp     eax, 117h
0x180038f7c  jnz     loc_180038EDE
0x180038f82  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180038f86  mov     r9d, 1
0x180038f8c  shr     eax, 7
0x180038f8f  and     eax, r9d
0x180038f92  mov     [rbx+10h], eax
0x180038f95  jmp     loc_180038EE1
```
