# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000b740`
- end: `0x18000b865`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800090fc`

## callees

- `0x1800033d0`
- `0x180007920`
- `0x18000b740`
- `0x180018010`

## string_xrefs

- `0x18000b78c`: `RtlQueryFeatureConfiguration`

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
0x18000b740  mov     [rsp+arg_10], rbx
0x18000b745  push    rbp
0x18000b746  push    rsi
0x18000b747  push    rdi
0x18000b748  sub     rsp, 50h
0x18000b74c  mov     rax, cs:__security_cookie
0x18000b753  xor     rax, rsp
0x18000b756  mov     [rsp+68h+var_20], rax
0x18000b75b  xor     esi, esi
0x18000b75d  mov     [rsp+68h+var_38], 0
0x18000b766  test    r8d, r8d
0x18000b769  mov     rdi, r9
0x18000b76c  mov     ebp, edx
0x18000b76e  mov     rbx, rcx
0x18000b771  setz    sil
0x18000b775  xor     eax, eax
0x18000b777  mov     [rsp+68h+var_30], rax
0x18000b77c  mov     [rsp+68h+var_28], eax
0x18000b780  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b787  test    rax, rax
0x18000b78a  jnz     short loc_18000B7E0
0x18000b78c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b793  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b798  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b79f  test    rax, rax
0x18000b7a2  jnz     short loc_18000B7E0
0x18000b7a4  mov     r8d, 0C0000139h
0x18000b7aa  xor     r9d, r9d
0x18000b7ad  test    rdi, rdi
0x18000b7b0  jz      short loc_18000B7C0
0x18000b7b2  xor     ecx, ecx
0x18000b7b4  cmp     r8d, 80000022h
0x18000b7bb  setnz   cl
0x18000b7be  mov     [rdi], ecx
0x18000b7c0  mov     eax, r9d
0x18000b7c3  mov     rcx, [rsp+68h+var_20]
0x18000b7c8  xor     rcx, rsp; StackCookie
0x18000b7cb  call    __security_check_cookie
0x18000b7d0  mov     rbx, [rsp+68h+arg_10]
0x18000b7d8  add     rsp, 50h
0x18000b7dc  pop     rdi
0x18000b7dd  pop     rsi
0x18000b7de  pop     rbp
0x18000b7df  retn
0x18000b7e0  lea     r9, [rsp+68h+var_30]
0x18000b7e5  mov     edx, esi
0x18000b7e7  lea     r8, [rsp+68h+var_38]
0x18000b7ec  mov     ecx, ebp
0x18000b7ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f3  mov     r8d, eax
0x18000b7f6  test    eax, eax
0x18000b7f8  jnz     short loc_18000B842
0x18000b7fa  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b7fe  lea     r9d, [r8+1]
0x18000b802  mov     eax, [rsp+68h+var_28]
0x18000b806  mov     ecx, edx
0x18000b808  mov     [rbx+0Ch], eax
0x18000b80b  mov     eax, edx
0x18000b80d  shr     eax, 0Eh
0x18000b810  shr     ecx, 4
0x18000b813  and     eax, 3
0x18000b816  and     ecx, 3
0x18000b819  mov     [rbx+8], eax
0x18000b81c  mov     [rbx], ecx
0x18000b81e  mov     eax, edx
0x18000b820  mov     ecx, edx
0x18000b822  shr     eax, 6
0x18000b825  shr     ecx, 8
0x18000b828  and     eax, r9d
0x18000b82b  and     cl, 3Fh
0x18000b82e  shr     edx, 7
0x18000b831  and     edx, r9d
0x18000b834  mov     [rbx+4], cl
0x18000b837  mov     [rbx+10h], edx
0x18000b83a  mov     [rbx+14h], eax
0x18000b83d  jmp     loc_18000B7AD
0x18000b842  cmp     eax, 117h
0x18000b847  jnz     loc_18000B7AA
0x18000b84d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000b851  mov     r9d, 1
0x18000b857  shr     eax, 7
0x18000b85a  and     eax, r9d
0x18000b85d  mov     [rbx+10h], eax
0x18000b860  jmp     loc_18000B7AD
```
