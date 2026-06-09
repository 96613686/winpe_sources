# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180023b74`
- end: `0x180023c99`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001f528`

## callees

- `0x18001be10`
- `0x180022af0`
- `0x180023b74`
- `0x180033010`

## string_xrefs

- `0x180023bc0`: `RtlQueryFeatureConfiguration`

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
0x180023b74  mov     [rsp+arg_10], rbx
0x180023b79  push    rbp
0x180023b7a  push    rsi
0x180023b7b  push    rdi
0x180023b7c  sub     rsp, 50h
0x180023b80  mov     rax, cs:__security_cookie
0x180023b87  xor     rax, rsp
0x180023b8a  mov     [rsp+68h+var_20], rax
0x180023b8f  xor     esi, esi
0x180023b91  mov     [rsp+68h+var_38], 0
0x180023b9a  test    r8d, r8d
0x180023b9d  mov     rdi, r9
0x180023ba0  mov     ebp, edx
0x180023ba2  mov     rbx, rcx
0x180023ba5  setz    sil
0x180023ba9  xor     eax, eax
0x180023bab  mov     [rsp+68h+var_30], rax
0x180023bb0  mov     [rsp+68h+var_28], eax
0x180023bb4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180023bbb  test    rax, rax
0x180023bbe  jnz     short loc_180023C14
0x180023bc0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180023bc7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180023bcc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180023bd3  test    rax, rax
0x180023bd6  jnz     short loc_180023C14
0x180023bd8  mov     r8d, 0C0000139h
0x180023bde  xor     r9d, r9d
0x180023be1  test    rdi, rdi
0x180023be4  jz      short loc_180023BF4
0x180023be6  xor     ecx, ecx
0x180023be8  cmp     r8d, 80000022h
0x180023bef  setnz   cl
0x180023bf2  mov     [rdi], ecx
0x180023bf4  mov     eax, r9d
0x180023bf7  mov     rcx, [rsp+68h+var_20]
0x180023bfc  xor     rcx, rsp; StackCookie
0x180023bff  call    __security_check_cookie
0x180023c04  mov     rbx, [rsp+68h+arg_10]
0x180023c0c  add     rsp, 50h
0x180023c10  pop     rdi
0x180023c11  pop     rsi
0x180023c12  pop     rbp
0x180023c13  retn
0x180023c14  lea     r9, [rsp+68h+var_30]
0x180023c19  mov     edx, esi
0x180023c1b  lea     r8, [rsp+68h+var_38]
0x180023c20  mov     ecx, ebp
0x180023c22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c27  mov     r8d, eax
0x180023c2a  test    eax, eax
0x180023c2c  jnz     short loc_180023C76
0x180023c2e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180023c32  lea     r9d, [r8+1]
0x180023c36  mov     eax, [rsp+68h+var_28]
0x180023c3a  mov     ecx, edx
0x180023c3c  mov     [rbx+0Ch], eax
0x180023c3f  mov     eax, edx
0x180023c41  shr     eax, 0Eh
0x180023c44  shr     ecx, 4
0x180023c47  and     eax, 3
0x180023c4a  and     ecx, 3
0x180023c4d  mov     [rbx+8], eax
0x180023c50  mov     [rbx], ecx
0x180023c52  mov     eax, edx
0x180023c54  mov     ecx, edx
0x180023c56  shr     eax, 6
0x180023c59  shr     ecx, 8
0x180023c5c  and     eax, r9d
0x180023c5f  and     cl, 3Fh
0x180023c62  shr     edx, 7
0x180023c65  and     edx, r9d
0x180023c68  mov     [rbx+4], cl
0x180023c6b  mov     [rbx+10h], edx
0x180023c6e  mov     [rbx+14h], eax
0x180023c71  jmp     loc_180023BE1
0x180023c76  cmp     eax, 117h
0x180023c7b  jnz     loc_180023BDE
0x180023c81  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180023c85  mov     r9d, 1
0x180023c8b  shr     eax, 7
0x180023c8e  and     eax, r9d
0x180023c91  mov     [rbx+10h], eax
0x180023c94  jmp     loc_180023BE1
```
