# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18002b07c`
- end: `0x18002b1a1`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180016540`

## callees

- `0x1800209c4`
- `0x180026200`
- `0x18002b07c`
- `0x180037010`

## string_xrefs

- `0x18002b0c8`: `RtlQueryFeatureConfiguration`

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
0x18002b07c  mov     [rsp+arg_10], rbx
0x18002b081  push    rbp
0x18002b082  push    rsi
0x18002b083  push    rdi
0x18002b084  sub     rsp, 50h
0x18002b088  mov     rax, cs:__security_cookie
0x18002b08f  xor     rax, rsp
0x18002b092  mov     [rsp+68h+var_20], rax
0x18002b097  xor     esi, esi
0x18002b099  mov     [rsp+68h+var_38], 0
0x18002b0a2  test    r8d, r8d
0x18002b0a5  mov     rdi, r9
0x18002b0a8  mov     ebp, edx
0x18002b0aa  mov     rbx, rcx
0x18002b0ad  setz    sil
0x18002b0b1  xor     eax, eax
0x18002b0b3  mov     [rsp+68h+var_30], rax
0x18002b0b8  mov     [rsp+68h+var_28], eax
0x18002b0bc  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002b0c3  test    rax, rax
0x18002b0c6  jnz     short loc_18002B11C
0x18002b0c8  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18002b0cf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002b0d4  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18002b0db  test    rax, rax
0x18002b0de  jnz     short loc_18002B11C
0x18002b0e0  mov     r8d, 0C0000139h
0x18002b0e6  xor     r9d, r9d
0x18002b0e9  test    rdi, rdi
0x18002b0ec  jz      short loc_18002B0FC
0x18002b0ee  xor     ecx, ecx
0x18002b0f0  cmp     r8d, 80000022h
0x18002b0f7  setnz   cl
0x18002b0fa  mov     [rdi], ecx
0x18002b0fc  mov     eax, r9d
0x18002b0ff  mov     rcx, [rsp+68h+var_20]
0x18002b104  xor     rcx, rsp; StackCookie
0x18002b107  call    __security_check_cookie
0x18002b10c  mov     rbx, [rsp+68h+arg_10]
0x18002b114  add     rsp, 50h
0x18002b118  pop     rdi
0x18002b119  pop     rsi
0x18002b11a  pop     rbp
0x18002b11b  retn
0x18002b11c  lea     r9, [rsp+68h+var_30]
0x18002b121  mov     edx, esi
0x18002b123  lea     r8, [rsp+68h+var_38]
0x18002b128  mov     ecx, ebp
0x18002b12a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b12f  mov     r8d, eax
0x18002b132  test    eax, eax
0x18002b134  jnz     short loc_18002B17E
0x18002b136  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18002b13a  lea     r9d, [r8+1]
0x18002b13e  mov     eax, [rsp+68h+var_28]
0x18002b142  mov     ecx, edx
0x18002b144  mov     [rbx+0Ch], eax
0x18002b147  mov     eax, edx
0x18002b149  shr     eax, 0Eh
0x18002b14c  shr     ecx, 4
0x18002b14f  and     eax, 3
0x18002b152  and     ecx, 3
0x18002b155  mov     [rbx+8], eax
0x18002b158  mov     [rbx], ecx
0x18002b15a  mov     eax, edx
0x18002b15c  mov     ecx, edx
0x18002b15e  shr     eax, 6
0x18002b161  shr     ecx, 8
0x18002b164  and     eax, r9d
0x18002b167  and     cl, 3Fh
0x18002b16a  shr     edx, 7
0x18002b16d  and     edx, r9d
0x18002b170  mov     [rbx+4], cl
0x18002b173  mov     [rbx+10h], edx
0x18002b176  mov     [rbx+14h], eax
0x18002b179  jmp     loc_18002B0E9
0x18002b17e  cmp     eax, 117h
0x18002b183  jnz     loc_18002B0E6
0x18002b189  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18002b18d  mov     r9d, 1
0x18002b193  shr     eax, 7
0x18002b196  and     eax, r9d
0x18002b199  mov     [rbx+10h], eax
0x18002b19c  jmp     loc_18002B0E9
```
