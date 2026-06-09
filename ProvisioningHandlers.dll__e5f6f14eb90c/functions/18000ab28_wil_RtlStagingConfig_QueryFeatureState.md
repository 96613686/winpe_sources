# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000ab28`
- end: `0x18000ac4e`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000682c`

## callees

- `0x18000a920`
- `0x18000ab28`
- `0x180028860`
- `0x18002c010`

## string_xrefs

- `0x18000ab74`: `RtlQueryFeatureConfiguration`

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
0x18000ab28  mov     [rsp+arg_10], rbx
0x18000ab2d  push    rbp
0x18000ab2e  push    rsi
0x18000ab2f  push    rdi
0x18000ab30  sub     rsp, 50h
0x18000ab34  mov     rax, cs:__security_cookie
0x18000ab3b  xor     rax, rsp
0x18000ab3e  mov     [rsp+68h+var_20], rax
0x18000ab43  xor     esi, esi
0x18000ab45  mov     [rsp+68h+var_38], 0
0x18000ab4e  test    r8d, r8d
0x18000ab51  mov     rdi, r9
0x18000ab54  mov     ebp, edx
0x18000ab56  mov     rbx, rcx
0x18000ab59  setz    sil
0x18000ab5d  xor     eax, eax
0x18000ab5f  mov     [rsp+68h+var_30], rax
0x18000ab64  mov     [rsp+68h+var_28], eax
0x18000ab68  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ab6f  test    rax, rax
0x18000ab72  jnz     short loc_18000ABC9
0x18000ab74  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ab7b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ab80  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ab87  test    rax, rax
0x18000ab8a  jnz     short loc_18000ABC9
0x18000ab8c  mov     r8d, 0C0000139h
0x18000ab92  xor     r9d, r9d
0x18000ab95  test    rdi, rdi
0x18000ab98  jz      short loc_18000ABA8
0x18000ab9a  xor     ecx, ecx
0x18000ab9c  cmp     r8d, 80000022h
0x18000aba3  setnz   cl
0x18000aba6  mov     [rdi], ecx
0x18000aba8  mov     eax, r9d
0x18000abab  mov     rcx, [rsp+68h+var_20]
0x18000abb0  xor     rcx, rsp; StackCookie
0x18000abb3  call    __security_check_cookie
0x18000abb8  mov     rbx, [rsp+68h+arg_10]
0x18000abc0  add     rsp, 50h
0x18000abc4  pop     rdi
0x18000abc5  pop     rsi
0x18000abc6  pop     rbp
0x18000abc7  retn
0x18000abc9  lea     r9, [rsp+68h+var_30]
0x18000abce  mov     edx, esi
0x18000abd0  lea     r8, [rsp+68h+var_38]
0x18000abd5  mov     ecx, ebp
0x18000abd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abdc  mov     r8d, eax
0x18000abdf  test    eax, eax
0x18000abe1  jnz     short loc_18000AC2B
0x18000abe3  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000abe7  lea     r9d, [r8+1]
0x18000abeb  mov     eax, [rsp+68h+var_28]
0x18000abef  mov     ecx, edx
0x18000abf1  mov     [rbx+0Ch], eax
0x18000abf4  mov     eax, edx
0x18000abf6  shr     eax, 0Eh
0x18000abf9  shr     ecx, 4
0x18000abfc  and     eax, 3
0x18000abff  and     ecx, 3
0x18000ac02  mov     [rbx+8], eax
0x18000ac05  mov     [rbx], ecx
0x18000ac07  mov     eax, edx
0x18000ac09  mov     ecx, edx
0x18000ac0b  shr     eax, 6
0x18000ac0e  shr     ecx, 8
0x18000ac11  and     eax, r9d
0x18000ac14  and     cl, 3Fh
0x18000ac17  shr     edx, 7
0x18000ac1a  and     edx, r9d
0x18000ac1d  mov     [rbx+4], cl
0x18000ac20  mov     [rbx+10h], edx
0x18000ac23  mov     [rbx+14h], eax
0x18000ac26  jmp     loc_18000AB95
0x18000ac2b  cmp     eax, 117h
0x18000ac30  jnz     loc_18000AB92
0x18000ac36  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000ac3a  mov     r9d, 1
0x18000ac40  shr     eax, 7
0x18000ac43  and     eax, r9d
0x18000ac46  mov     [rbx+10h], eax
0x18000ac49  jmp     loc_18000AB95
```
