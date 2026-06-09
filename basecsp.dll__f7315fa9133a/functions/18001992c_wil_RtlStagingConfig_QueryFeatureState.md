# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18001992c`
- end: `0x180019a51`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001054c`

## callees

- `0x180019230`
- `0x18001992c`
- `0x18002cfa0`
- `0x18002e010`

## string_xrefs

- `0x180019978`: `RtlQueryFeatureConfiguration`

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
0x18001992c  mov     [rsp+arg_10], rbx
0x180019931  push    rbp
0x180019932  push    rsi
0x180019933  push    rdi
0x180019934  sub     rsp, 50h
0x180019938  mov     rax, cs:__security_cookie
0x18001993f  xor     rax, rsp
0x180019942  mov     [rsp+68h+var_20], rax
0x180019947  xor     esi, esi
0x180019949  mov     [rsp+68h+var_38], 0
0x180019952  test    r8d, r8d
0x180019955  mov     rdi, r9
0x180019958  mov     ebp, edx
0x18001995a  mov     rbx, rcx
0x18001995d  setz    sil
0x180019961  xor     eax, eax
0x180019963  mov     [rsp+68h+var_30], rax
0x180019968  mov     [rsp+68h+var_28], eax
0x18001996c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180019973  test    rax, rax
0x180019976  jnz     short loc_1800199CC
0x180019978  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001997f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180019984  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18001998b  test    rax, rax
0x18001998e  jnz     short loc_1800199CC
0x180019990  mov     r8d, 0C0000139h
0x180019996  xor     r9d, r9d
0x180019999  test    rdi, rdi
0x18001999c  jz      short loc_1800199AC
0x18001999e  xor     ecx, ecx
0x1800199a0  cmp     r8d, 80000022h
0x1800199a7  setnz   cl
0x1800199aa  mov     [rdi], ecx
0x1800199ac  mov     eax, r9d
0x1800199af  mov     rcx, [rsp+68h+var_20]
0x1800199b4  xor     rcx, rsp; StackCookie
0x1800199b7  call    __security_check_cookie
0x1800199bc  mov     rbx, [rsp+68h+arg_10]
0x1800199c4  add     rsp, 50h
0x1800199c8  pop     rdi
0x1800199c9  pop     rsi
0x1800199ca  pop     rbp
0x1800199cb  retn
0x1800199cc  lea     r9, [rsp+68h+var_30]
0x1800199d1  mov     edx, esi
0x1800199d3  lea     r8, [rsp+68h+var_38]
0x1800199d8  mov     ecx, ebp
0x1800199da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800199df  mov     r8d, eax
0x1800199e2  test    eax, eax
0x1800199e4  jnz     short loc_180019A2E
0x1800199e6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800199ea  lea     r9d, [r8+1]
0x1800199ee  mov     eax, [rsp+68h+var_28]
0x1800199f2  mov     ecx, edx
0x1800199f4  mov     [rbx+0Ch], eax
0x1800199f7  mov     eax, edx
0x1800199f9  shr     eax, 0Eh
0x1800199fc  shr     ecx, 4
0x1800199ff  and     eax, 3
0x180019a02  and     ecx, 3
0x180019a05  mov     [rbx+8], eax
0x180019a08  mov     [rbx], ecx
0x180019a0a  mov     eax, edx
0x180019a0c  mov     ecx, edx
0x180019a0e  shr     eax, 6
0x180019a11  shr     ecx, 8
0x180019a14  and     eax, r9d
0x180019a17  and     cl, 3Fh
0x180019a1a  shr     edx, 7
0x180019a1d  and     edx, r9d
0x180019a20  mov     [rbx+4], cl
0x180019a23  mov     [rbx+10h], edx
0x180019a26  mov     [rbx+14h], eax
0x180019a29  jmp     loc_180019999
0x180019a2e  cmp     eax, 117h
0x180019a33  jnz     loc_180019996
0x180019a39  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180019a3d  mov     r9d, 1
0x180019a43  shr     eax, 7
0x180019a46  and     eax, r9d
0x180019a49  mov     [rbx+10h], eax
0x180019a4c  jmp     loc_180019999
```
