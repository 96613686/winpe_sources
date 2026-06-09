# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180058718`
- end: `0x18005883e`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180054b78`

## callees

- `0x180049d00`
- `0x18005840c`
- `0x180058718`
- `0x180077010`

## string_xrefs

- `0x180058764`: `RtlQueryFeatureConfiguration`

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
0x180058718  mov     [rsp+arg_10], rbx
0x18005871d  push    rbp
0x18005871e  push    rsi
0x18005871f  push    rdi
0x180058720  sub     rsp, 50h
0x180058724  mov     rax, cs:__security_cookie
0x18005872b  xor     rax, rsp
0x18005872e  mov     [rsp+68h+var_20], rax
0x180058733  xor     esi, esi
0x180058735  mov     [rsp+68h+var_38], 0
0x18005873e  test    r8d, r8d
0x180058741  mov     rdi, r9
0x180058744  mov     ebp, edx
0x180058746  mov     rbx, rcx
0x180058749  setz    sil
0x18005874d  xor     eax, eax
0x18005874f  mov     [rsp+68h+var_30], rax
0x180058754  mov     [rsp+68h+var_28], eax
0x180058758  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18005875f  test    rax, rax
0x180058762  jnz     short loc_1800587B9
0x180058764  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18005876b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180058770  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180058777  test    rax, rax
0x18005877a  jnz     short loc_1800587B9
0x18005877c  mov     r8d, 0C0000139h
0x180058782  xor     r9d, r9d
0x180058785  test    rdi, rdi
0x180058788  jz      short loc_180058798
0x18005878a  xor     ecx, ecx
0x18005878c  cmp     r8d, 80000022h
0x180058793  setnz   cl
0x180058796  mov     [rdi], ecx
0x180058798  mov     eax, r9d
0x18005879b  mov     rcx, [rsp+68h+var_20]
0x1800587a0  xor     rcx, rsp; StackCookie
0x1800587a3  call    __security_check_cookie
0x1800587a8  mov     rbx, [rsp+68h+arg_10]
0x1800587b0  add     rsp, 50h
0x1800587b4  pop     rdi
0x1800587b5  pop     rsi
0x1800587b6  pop     rbp
0x1800587b7  retn
0x1800587b9  lea     r9, [rsp+68h+var_30]
0x1800587be  mov     edx, esi
0x1800587c0  lea     r8, [rsp+68h+var_38]
0x1800587c5  mov     ecx, ebp
0x1800587c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800587cc  mov     r8d, eax
0x1800587cf  test    eax, eax
0x1800587d1  jnz     short loc_18005881B
0x1800587d3  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800587d7  lea     r9d, [r8+1]
0x1800587db  mov     eax, [rsp+68h+var_28]
0x1800587df  mov     ecx, edx
0x1800587e1  mov     [rbx+0Ch], eax
0x1800587e4  mov     eax, edx
0x1800587e6  shr     eax, 0Eh
0x1800587e9  shr     ecx, 4
0x1800587ec  and     eax, 3
0x1800587ef  and     ecx, 3
0x1800587f2  mov     [rbx+8], eax
0x1800587f5  mov     [rbx], ecx
0x1800587f7  mov     eax, edx
0x1800587f9  mov     ecx, edx
0x1800587fb  shr     eax, 6
0x1800587fe  shr     ecx, 8
0x180058801  and     eax, r9d
0x180058804  and     cl, 3Fh
0x180058807  shr     edx, 7
0x18005880a  and     edx, r9d
0x18005880d  mov     [rbx+4], cl
0x180058810  mov     [rbx+10h], edx
0x180058813  mov     [rbx+14h], eax
0x180058816  jmp     loc_180058785
0x18005881b  cmp     eax, 117h
0x180058820  jnz     loc_180058782
0x180058826  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18005882a  mov     r9d, 1
0x180058830  shr     eax, 7
0x180058833  and     eax, r9d
0x180058836  mov     [rbx+10h], eax
0x180058839  jmp     loc_180058785
```
