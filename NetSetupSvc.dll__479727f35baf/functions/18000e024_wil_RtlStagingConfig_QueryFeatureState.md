# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000e024`
- end: `0x18000e149`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a87c`

## callees

- `0x1800027c0`
- `0x180006c50`
- `0x18000e024`
- `0x180031010`

## string_xrefs

- `0x18000e070`: `RtlQueryFeatureConfiguration`

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
  int v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF

  v17 = 0;
  v7 = a3 == 0;
  v15 = 0;
  v16 = 0;
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
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v17, &v15);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v15) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v15);
    v10 = 1;
    v14 = HIDWORD(v15);
    *(_DWORD *)(a1 + 12) = v16;
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
0x18000e024  mov     [rsp+arg_10], rbx
0x18000e029  push    rbp
0x18000e02a  push    rsi
0x18000e02b  push    rdi
0x18000e02c  sub     rsp, 50h
0x18000e030  mov     rax, cs:__security_cookie
0x18000e037  xor     rax, rsp
0x18000e03a  mov     [rsp+68h+var_20], rax
0x18000e03f  xor     esi, esi
0x18000e041  mov     [rsp+68h+var_28], 0
0x18000e04a  test    r8d, r8d
0x18000e04d  mov     rdi, r9
0x18000e050  mov     ebp, edx
0x18000e052  mov     rbx, rcx
0x18000e055  setz    sil
0x18000e059  xor     eax, eax
0x18000e05b  mov     [rsp+68h+var_38], rax
0x18000e060  mov     [rsp+68h+var_30], eax
0x18000e064  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000e06b  test    rax, rax
0x18000e06e  jnz     short loc_18000E0C4
0x18000e070  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000e077  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e07c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000e083  test    rax, rax
0x18000e086  jnz     short loc_18000E0C4
0x18000e088  mov     r8d, 0C0000139h
0x18000e08e  xor     r9d, r9d
0x18000e091  test    rdi, rdi
0x18000e094  jz      short loc_18000E0A4
0x18000e096  xor     ecx, ecx
0x18000e098  cmp     r8d, 80000022h
0x18000e09f  setnz   cl
0x18000e0a2  mov     [rdi], ecx
0x18000e0a4  mov     eax, r9d
0x18000e0a7  mov     rcx, [rsp+68h+var_20]
0x18000e0ac  xor     rcx, rsp; StackCookie
0x18000e0af  call    __security_check_cookie
0x18000e0b4  mov     rbx, [rsp+68h+arg_10]
0x18000e0bc  add     rsp, 50h
0x18000e0c0  pop     rdi
0x18000e0c1  pop     rsi
0x18000e0c2  pop     rbp
0x18000e0c3  retn
0x18000e0c4  lea     r9, [rsp+68h+var_38]
0x18000e0c9  mov     edx, esi
0x18000e0cb  lea     r8, [rsp+68h+var_28]
0x18000e0d0  mov     ecx, ebp
0x18000e0d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e0d7  mov     r8d, eax
0x18000e0da  test    eax, eax
0x18000e0dc  jnz     short loc_18000E126
0x18000e0de  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18000e0e2  lea     r9d, [r8+1]
0x18000e0e6  mov     eax, [rsp+68h+var_30]
0x18000e0ea  mov     ecx, edx
0x18000e0ec  mov     [rbx+0Ch], eax
0x18000e0ef  mov     eax, edx
0x18000e0f1  shr     eax, 0Eh
0x18000e0f4  shr     ecx, 4
0x18000e0f7  and     eax, 3
0x18000e0fa  and     ecx, 3
0x18000e0fd  mov     [rbx+8], eax
0x18000e100  mov     [rbx], ecx
0x18000e102  mov     eax, edx
0x18000e104  mov     ecx, edx
0x18000e106  shr     eax, 6
0x18000e109  shr     ecx, 8
0x18000e10c  and     eax, r9d
0x18000e10f  and     cl, 3Fh
0x18000e112  shr     edx, 7
0x18000e115  and     edx, r9d
0x18000e118  mov     [rbx+4], cl
0x18000e11b  mov     [rbx+10h], edx
0x18000e11e  mov     [rbx+14h], eax
0x18000e121  jmp     loc_18000E091
0x18000e126  cmp     eax, 117h
0x18000e12b  jnz     loc_18000E08E
0x18000e131  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18000e135  mov     r9d, 1
0x18000e13b  shr     eax, 7
0x18000e13e  and     eax, r9d
0x18000e141  mov     [rbx+10h], eax
0x18000e144  jmp     loc_18000E091
```
