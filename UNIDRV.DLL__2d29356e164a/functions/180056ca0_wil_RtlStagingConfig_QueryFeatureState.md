# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180056ca0`
- end: `0x180056dc5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180053190`
- `0x180059408`

## callees

- `0x1800487e0`
- `0x18005699c`
- `0x180056ca0`
- `0x180075010`

## string_xrefs

- `0x180056cec`: `RtlQueryFeatureConfiguration`

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
0x180056ca0  mov     [rsp+arg_10], rbx
0x180056ca5  push    rbp
0x180056ca6  push    rsi
0x180056ca7  push    rdi
0x180056ca8  sub     rsp, 50h
0x180056cac  mov     rax, cs:__security_cookie
0x180056cb3  xor     rax, rsp
0x180056cb6  mov     [rsp+68h+var_20], rax
0x180056cbb  xor     esi, esi
0x180056cbd  mov     [rsp+68h+var_38], 0
0x180056cc6  test    r8d, r8d
0x180056cc9  mov     rdi, r9
0x180056ccc  mov     ebp, edx
0x180056cce  mov     rbx, rcx
0x180056cd1  setz    sil
0x180056cd5  xor     eax, eax
0x180056cd7  mov     [rsp+68h+var_30], rax
0x180056cdc  mov     [rsp+68h+var_28], eax
0x180056ce0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180056ce7  test    rax, rax
0x180056cea  jnz     short loc_180056D40
0x180056cec  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180056cf3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180056cf8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180056cff  test    rax, rax
0x180056d02  jnz     short loc_180056D40
0x180056d04  mov     r8d, 0C0000139h
0x180056d0a  xor     r9d, r9d
0x180056d0d  test    rdi, rdi
0x180056d10  jz      short loc_180056D20
0x180056d12  xor     ecx, ecx
0x180056d14  cmp     r8d, 80000022h
0x180056d1b  setnz   cl
0x180056d1e  mov     [rdi], ecx
0x180056d20  mov     eax, r9d
0x180056d23  mov     rcx, [rsp+68h+var_20]
0x180056d28  xor     rcx, rsp; StackCookie
0x180056d2b  call    __security_check_cookie
0x180056d30  mov     rbx, [rsp+68h+arg_10]
0x180056d38  add     rsp, 50h
0x180056d3c  pop     rdi
0x180056d3d  pop     rsi
0x180056d3e  pop     rbp
0x180056d3f  retn
0x180056d40  lea     r9, [rsp+68h+var_30]
0x180056d45  mov     edx, esi
0x180056d47  lea     r8, [rsp+68h+var_38]
0x180056d4c  mov     ecx, ebp
0x180056d4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d53  mov     r8d, eax
0x180056d56  test    eax, eax
0x180056d58  jnz     short loc_180056DA2
0x180056d5a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180056d5e  lea     r9d, [r8+1]
0x180056d62  mov     eax, [rsp+68h+var_28]
0x180056d66  mov     ecx, edx
0x180056d68  mov     [rbx+0Ch], eax
0x180056d6b  mov     eax, edx
0x180056d6d  shr     eax, 0Eh
0x180056d70  shr     ecx, 4
0x180056d73  and     eax, 3
0x180056d76  and     ecx, 3
0x180056d79  mov     [rbx+8], eax
0x180056d7c  mov     [rbx], ecx
0x180056d7e  mov     eax, edx
0x180056d80  mov     ecx, edx
0x180056d82  shr     eax, 6
0x180056d85  shr     ecx, 8
0x180056d88  and     eax, r9d
0x180056d8b  and     cl, 3Fh
0x180056d8e  shr     edx, 7
0x180056d91  and     edx, r9d
0x180056d94  mov     [rbx+4], cl
0x180056d97  mov     [rbx+10h], edx
0x180056d9a  mov     [rbx+14h], eax
0x180056d9d  jmp     loc_180056D0D
0x180056da2  cmp     eax, 117h
0x180056da7  jnz     loc_180056D0A
0x180056dad  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180056db1  mov     r9d, 1
0x180056db7  shr     eax, 7
0x180056dba  and     eax, r9d
0x180056dbd  mov     [rbx+10h], eax
0x180056dc0  jmp     loc_180056D0D
```
