# wil_QueryFeatureState

- ea: `0x180018cd4`
- end: `0x180018e16`
- name: `wil_QueryFeatureState`
- size: `322`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180013240`
- `0x18002f704`

## callees

- `0x180018cd4`
- `0x180018e1c`
- `0x18001bbe0`
- `0x180031010`

## string_xrefs

- `0x180018d46`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  __int64 (*NtDllProcedureAddress)(void); // rax
  int v11; // r8d
  int v13; // eax
  unsigned int v14; // edx
  unsigned int v15; // ecx
  __int64 v16; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h] BYREF
  int v18; // [rsp+40h] [rbp-28h]

  if ( a5 )
    *a5 = 0;
  v16 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v17 = 0;
  v18 = 0;
  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v11 = -1073741511;
LABEL_6:
      v8 = 0;
      goto LABEL_7;
    }
  }
  v13 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v9, &v16, &v17);
  v11 = v13;
  if ( v13 )
  {
    if ( v13 != 279 )
      goto LABEL_6;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v17) >> 7) & 1;
  }
  else
  {
    v14 = HIDWORD(v17);
    v15 = HIDWORD(v17);
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v15 >> 14;
    *(_DWORD *)a1 = (v15 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v14) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v14 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v14 >> 6) & 1;
  }
LABEL_7:
  if ( a5 )
    *a5 = v11 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x180018cd4  mov     [rsp+arg_10], rbx
0x180018cd9  mov     [rsp+arg_18], rbp
0x180018cde  push    rsi
0x180018cdf  push    rdi
0x180018ce0  push    r14
0x180018ce2  sub     rsp, 50h
0x180018ce6  mov     rax, cs:__security_cookie
0x180018ced  xor     rax, rsp
0x180018cf0  mov     [rsp+68h+var_20], rax
0x180018cf5  mov     rdi, [rsp+68h+arg_20]
0x180018cfd  mov     r14d, edx
0x180018d00  mov     rax, [rsp+68h+arg_28]
0x180018d08  mov     rsi, rcx
0x180018d0b  test    rdi, rdi
0x180018d0e  jz      short loc_180018D16
0x180018d10  mov     dword ptr [rdi], 0
0x180018d16  xor     ebp, ebp
0x180018d18  mov     [rsp+68h+var_38], 0
0x180018d21  test    r8d, r8d
0x180018d24  mov     ebx, 1
0x180018d29  mov     [rax], ebx
0x180018d2b  setz    bpl
0x180018d2f  xor     eax, eax
0x180018d31  mov     [rsp+68h+var_30], rax
0x180018d36  mov     [rsp+68h+var_28], eax
0x180018d3a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180018d41  test    rax, rax
0x180018d44  jnz     short loc_180018D9D
0x180018d46  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180018d4d  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180018d52  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180018d59  test    rax, rax
0x180018d5c  jnz     short loc_180018D9D
0x180018d5e  mov     r8d, 0C0000139h
0x180018d64  xor     ebx, ebx
0x180018d66  test    rdi, rdi
0x180018d69  jz      short loc_180018D79
0x180018d6b  xor     ecx, ecx
0x180018d6d  cmp     r8d, 80000022h
0x180018d74  setnz   cl
0x180018d77  mov     [rdi], ecx
0x180018d79  mov     eax, ebx
0x180018d7b  mov     rcx, [rsp+68h+var_20]
0x180018d80  xor     rcx, rsp; StackCookie
0x180018d83  call    __security_check_cookie
0x180018d88  lea     r11, [rsp+68h+var_18]
0x180018d8d  mov     rbx, [r11+30h]
0x180018d91  mov     rbp, [r11+38h]
0x180018d95  mov     rsp, r11
0x180018d98  pop     r14
0x180018d9a  pop     rdi
0x180018d9b  pop     rsi
0x180018d9c  retn
0x180018d9d  lea     r9, [rsp+68h+var_30]
0x180018da2  mov     edx, ebp
0x180018da4  lea     r8, [rsp+68h+var_38]
0x180018da9  mov     ecx, r14d
0x180018dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018db1  mov     r8d, eax
0x180018db4  test    eax, eax
0x180018db6  jnz     short loc_180018DFA
0x180018db8  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180018dbc  mov     ecx, edx
0x180018dbe  mov     eax, [rsp+68h+var_28]
0x180018dc2  mov     [rsi+0Ch], eax
0x180018dc5  mov     eax, edx
0x180018dc7  shr     eax, 0Eh
0x180018dca  shr     ecx, 4
0x180018dcd  and     eax, 3
0x180018dd0  and     ecx, 3
0x180018dd3  mov     [rsi+8], eax
0x180018dd6  mov     [rsi], ecx
0x180018dd8  mov     eax, edx
0x180018dda  mov     ecx, edx
0x180018ddc  shr     eax, 6
0x180018ddf  shr     ecx, 8
0x180018de2  and     eax, ebx
0x180018de4  and     cl, 3Fh
0x180018de7  shr     edx, 7
0x180018dea  and     edx, ebx
0x180018dec  mov     [rsi+4], cl
0x180018def  mov     [rsi+10h], edx
0x180018df2  mov     [rsi+14h], eax
0x180018df5  jmp     loc_180018D66
0x180018dfa  cmp     eax, 117h
0x180018dff  jnz     loc_180018D64
0x180018e05  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180018e09  shr     eax, 7
0x180018e0c  and     eax, ebx
0x180018e0e  mov     [rsi+10h], eax
0x180018e11  jmp     loc_180018D66
```
