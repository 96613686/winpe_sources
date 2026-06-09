# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000a148`
- end: `0x18000a26d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180006350`

## callees

- `0x180002c00`
- `0x180009e80`
- `0x18000a148`
- `0x18001c010`

## string_xrefs

- `0x18000a194`: `RtlQueryFeatureConfiguration`

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
0x18000a148  mov     [rsp+arg_10], rbx
0x18000a14d  push    rbp
0x18000a14e  push    rsi
0x18000a14f  push    rdi
0x18000a150  sub     rsp, 50h
0x18000a154  mov     rax, cs:__security_cookie
0x18000a15b  xor     rax, rsp
0x18000a15e  mov     [rsp+68h+var_20], rax
0x18000a163  xor     esi, esi
0x18000a165  mov     [rsp+68h+var_38], 0
0x18000a16e  test    r8d, r8d
0x18000a171  mov     rdi, r9
0x18000a174  mov     ebp, edx
0x18000a176  mov     rbx, rcx
0x18000a179  setz    sil
0x18000a17d  xor     eax, eax
0x18000a17f  mov     [rsp+68h+var_30], rax
0x18000a184  mov     [rsp+68h+var_28], eax
0x18000a188  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000a18f  test    rax, rax
0x18000a192  jnz     short loc_18000A1E8
0x18000a194  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000a19b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a1a0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000a1a7  test    rax, rax
0x18000a1aa  jnz     short loc_18000A1E8
0x18000a1ac  mov     r8d, 0C0000139h
0x18000a1b2  xor     r9d, r9d
0x18000a1b5  test    rdi, rdi
0x18000a1b8  jz      short loc_18000A1C8
0x18000a1ba  xor     ecx, ecx
0x18000a1bc  cmp     r8d, 80000022h
0x18000a1c3  setnz   cl
0x18000a1c6  mov     [rdi], ecx
0x18000a1c8  mov     eax, r9d
0x18000a1cb  mov     rcx, [rsp+68h+var_20]
0x18000a1d0  xor     rcx, rsp; StackCookie
0x18000a1d3  call    __security_check_cookie
0x18000a1d8  mov     rbx, [rsp+68h+arg_10]
0x18000a1e0  add     rsp, 50h
0x18000a1e4  pop     rdi
0x18000a1e5  pop     rsi
0x18000a1e6  pop     rbp
0x18000a1e7  retn
0x18000a1e8  lea     r9, [rsp+68h+var_30]
0x18000a1ed  mov     edx, esi
0x18000a1ef  lea     r8, [rsp+68h+var_38]
0x18000a1f4  mov     ecx, ebp
0x18000a1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1fb  mov     r8d, eax
0x18000a1fe  test    eax, eax
0x18000a200  jnz     short loc_18000A24A
0x18000a202  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000a206  lea     r9d, [r8+1]
0x18000a20a  mov     eax, [rsp+68h+var_28]
0x18000a20e  mov     ecx, edx
0x18000a210  mov     [rbx+0Ch], eax
0x18000a213  mov     eax, edx
0x18000a215  shr     eax, 0Eh
0x18000a218  shr     ecx, 4
0x18000a21b  and     eax, 3
0x18000a21e  and     ecx, 3
0x18000a221  mov     [rbx+8], eax
0x18000a224  mov     [rbx], ecx
0x18000a226  mov     eax, edx
0x18000a228  mov     ecx, edx
0x18000a22a  shr     eax, 6
0x18000a22d  shr     ecx, 8
0x18000a230  and     eax, r9d
0x18000a233  and     cl, 3Fh
0x18000a236  shr     edx, 7
0x18000a239  and     edx, r9d
0x18000a23c  mov     [rbx+4], cl
0x18000a23f  mov     [rbx+10h], edx
0x18000a242  mov     [rbx+14h], eax
0x18000a245  jmp     loc_18000A1B5
0x18000a24a  cmp     eax, 117h
0x18000a24f  jnz     loc_18000A1B2
0x18000a255  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000a259  mov     r9d, 1
0x18000a25f  shr     eax, 7
0x18000a262  and     eax, r9d
0x18000a265  mov     [rbx+10h], eax
0x18000a268  jmp     loc_18000A1B5
```
