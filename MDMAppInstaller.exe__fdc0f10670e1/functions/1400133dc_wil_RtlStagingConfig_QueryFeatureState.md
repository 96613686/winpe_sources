# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1400133dc`
- end: `0x140013501`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1400133b4`

## callees

- `0x140006bd0`
- `0x1400133dc`
- `0x14001a8d0`
- `0x14001c010`

## string_xrefs

- `0x140013428`: `RtlQueryFeatureConfiguration`

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
0x1400133dc  mov     [rsp+arg_10], rbx
0x1400133e1  push    rbp
0x1400133e2  push    rsi
0x1400133e3  push    rdi
0x1400133e4  sub     rsp, 50h
0x1400133e8  mov     rax, cs:__security_cookie
0x1400133ef  xor     rax, rsp
0x1400133f2  mov     [rsp+68h+var_20], rax
0x1400133f7  xor     esi, esi
0x1400133f9  mov     [rsp+68h+var_38], 0
0x140013402  test    r8d, r8d
0x140013405  mov     rdi, r9
0x140013408  mov     ebp, edx
0x14001340a  mov     rbx, rcx
0x14001340d  setz    sil
0x140013411  xor     eax, eax
0x140013413  mov     [rsp+68h+var_30], rax
0x140013418  mov     [rsp+68h+var_28], eax
0x14001341c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140013423  test    rax, rax
0x140013426  jnz     short loc_14001347C
0x140013428  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14001342f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140013434  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14001343b  test    rax, rax
0x14001343e  jnz     short loc_14001347C
0x140013440  mov     r8d, 0C0000139h
0x140013446  xor     r9d, r9d
0x140013449  test    rdi, rdi
0x14001344c  jz      short loc_14001345C
0x14001344e  xor     ecx, ecx
0x140013450  cmp     r8d, 80000022h
0x140013457  setnz   cl
0x14001345a  mov     [rdi], ecx
0x14001345c  mov     eax, r9d
0x14001345f  mov     rcx, [rsp+68h+var_20]
0x140013464  xor     rcx, rsp; StackCookie
0x140013467  call    __security_check_cookie
0x14001346c  mov     rbx, [rsp+68h+arg_10]
0x140013474  add     rsp, 50h
0x140013478  pop     rdi
0x140013479  pop     rsi
0x14001347a  pop     rbp
0x14001347b  retn
0x14001347c  lea     r9, [rsp+68h+var_30]
0x140013481  mov     edx, esi
0x140013483  lea     r8, [rsp+68h+var_38]
0x140013488  mov     ecx, ebp
0x14001348a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001348f  mov     r8d, eax
0x140013492  test    eax, eax
0x140013494  jnz     short loc_1400134DE
0x140013496  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14001349a  lea     r9d, [r8+1]
0x14001349e  mov     eax, [rsp+68h+var_28]
0x1400134a2  mov     ecx, edx
0x1400134a4  mov     [rbx+0Ch], eax
0x1400134a7  mov     eax, edx
0x1400134a9  shr     eax, 0Eh
0x1400134ac  shr     ecx, 4
0x1400134af  and     eax, 3
0x1400134b2  and     ecx, 3
0x1400134b5  mov     [rbx+8], eax
0x1400134b8  mov     [rbx], ecx
0x1400134ba  mov     eax, edx
0x1400134bc  mov     ecx, edx
0x1400134be  shr     eax, 6
0x1400134c1  shr     ecx, 8
0x1400134c4  and     eax, r9d
0x1400134c7  and     cl, 3Fh
0x1400134ca  shr     edx, 7
0x1400134cd  and     edx, r9d
0x1400134d0  mov     [rbx+4], cl
0x1400134d3  mov     [rbx+10h], edx
0x1400134d6  mov     [rbx+14h], eax
0x1400134d9  jmp     loc_140013449
0x1400134de  cmp     eax, 117h
0x1400134e3  jnz     loc_140013446
0x1400134e9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1400134ed  mov     r9d, 1
0x1400134f3  shr     eax, 7
0x1400134f6  and     eax, r9d
0x1400134f9  mov     [rbx+10h], eax
0x1400134fc  jmp     loc_140013449
```
