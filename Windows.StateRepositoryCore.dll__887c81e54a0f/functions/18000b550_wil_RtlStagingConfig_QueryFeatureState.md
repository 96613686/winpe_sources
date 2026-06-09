# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000b550`
- end: `0x18000b675`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b528`

## callees

- `0x180001ed0`
- `0x18000b160`
- `0x18000b550`
- `0x180011010`

## string_xrefs

- `0x18000b59c`: `RtlQueryFeatureConfiguration`

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
0x18000b550  mov     [rsp+arg_10], rbx
0x18000b555  push    rbp
0x18000b556  push    rsi
0x18000b557  push    rdi
0x18000b558  sub     rsp, 50h
0x18000b55c  mov     rax, cs:__security_cookie
0x18000b563  xor     rax, rsp
0x18000b566  mov     [rsp+68h+var_20], rax
0x18000b56b  xor     esi, esi
0x18000b56d  mov     [rsp+68h+var_38], 0
0x18000b576  test    r8d, r8d
0x18000b579  mov     rdi, r9
0x18000b57c  mov     ebp, edx
0x18000b57e  mov     rbx, rcx
0x18000b581  setz    sil
0x18000b585  xor     eax, eax
0x18000b587  mov     [rsp+68h+var_30], rax
0x18000b58c  mov     [rsp+68h+var_28], eax
0x18000b590  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b597  test    rax, rax
0x18000b59a  jnz     short loc_18000B5F0
0x18000b59c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b5a3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b5a8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b5af  test    rax, rax
0x18000b5b2  jnz     short loc_18000B5F0
0x18000b5b4  mov     r8d, 0C0000139h
0x18000b5ba  xor     r9d, r9d
0x18000b5bd  test    rdi, rdi
0x18000b5c0  jz      short loc_18000B5D0
0x18000b5c2  xor     ecx, ecx
0x18000b5c4  cmp     r8d, 80000022h
0x18000b5cb  setnz   cl
0x18000b5ce  mov     [rdi], ecx
0x18000b5d0  mov     eax, r9d
0x18000b5d3  mov     rcx, [rsp+68h+var_20]
0x18000b5d8  xor     rcx, rsp; StackCookie
0x18000b5db  call    __security_check_cookie
0x18000b5e0  mov     rbx, [rsp+68h+arg_10]
0x18000b5e8  add     rsp, 50h
0x18000b5ec  pop     rdi
0x18000b5ed  pop     rsi
0x18000b5ee  pop     rbp
0x18000b5ef  retn
0x18000b5f0  lea     r9, [rsp+68h+var_30]
0x18000b5f5  mov     edx, esi
0x18000b5f7  lea     r8, [rsp+68h+var_38]
0x18000b5fc  mov     ecx, ebp
0x18000b5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b603  mov     r8d, eax
0x18000b606  test    eax, eax
0x18000b608  jnz     short loc_18000B652
0x18000b60a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b60e  lea     r9d, [r8+1]
0x18000b612  mov     eax, [rsp+68h+var_28]
0x18000b616  mov     ecx, edx
0x18000b618  mov     [rbx+0Ch], eax
0x18000b61b  mov     eax, edx
0x18000b61d  shr     eax, 0Eh
0x18000b620  shr     ecx, 4
0x18000b623  and     eax, 3
0x18000b626  and     ecx, 3
0x18000b629  mov     [rbx+8], eax
0x18000b62c  mov     [rbx], ecx
0x18000b62e  mov     eax, edx
0x18000b630  mov     ecx, edx
0x18000b632  shr     eax, 6
0x18000b635  shr     ecx, 8
0x18000b638  and     eax, r9d
0x18000b63b  and     cl, 3Fh
0x18000b63e  shr     edx, 7
0x18000b641  and     edx, r9d
0x18000b644  mov     [rbx+4], cl
0x18000b647  mov     [rbx+10h], edx
0x18000b64a  mov     [rbx+14h], eax
0x18000b64d  jmp     loc_18000B5BD
0x18000b652  cmp     eax, 117h
0x18000b657  jnz     loc_18000B5BA
0x18000b65d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000b661  mov     r9d, 1
0x18000b667  shr     eax, 7
0x18000b66a  and     eax, r9d
0x18000b66d  mov     [rbx+10h], eax
0x18000b670  jmp     loc_18000B5BD
```
