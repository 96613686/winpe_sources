# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14000bf74`
- end: `0x14000c099`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000bf4c`

## callees

- `0x140005530`
- `0x14000bcc4`
- `0x14000bf74`
- `0x140010010`

## string_xrefs

- `0x14000bfc0`: `RtlQueryFeatureConfiguration`

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
0x14000bf74  mov     [rsp+arg_10], rbx
0x14000bf79  push    rbp
0x14000bf7a  push    rsi
0x14000bf7b  push    rdi
0x14000bf7c  sub     rsp, 50h
0x14000bf80  mov     rax, cs:__security_cookie
0x14000bf87  xor     rax, rsp
0x14000bf8a  mov     [rsp+68h+var_20], rax
0x14000bf8f  xor     esi, esi
0x14000bf91  mov     [rsp+68h+var_38], 0
0x14000bf9a  test    r8d, r8d
0x14000bf9d  mov     rdi, r9
0x14000bfa0  mov     ebp, edx
0x14000bfa2  mov     rbx, rcx
0x14000bfa5  setz    sil
0x14000bfa9  xor     eax, eax
0x14000bfab  mov     [rsp+68h+var_30], rax
0x14000bfb0  mov     [rsp+68h+var_28], eax
0x14000bfb4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000bfbb  test    rax, rax
0x14000bfbe  jnz     short loc_14000C014
0x14000bfc0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000bfc7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000bfcc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000bfd3  test    rax, rax
0x14000bfd6  jnz     short loc_14000C014
0x14000bfd8  mov     r8d, 0C0000139h
0x14000bfde  xor     r9d, r9d
0x14000bfe1  test    rdi, rdi
0x14000bfe4  jz      short loc_14000BFF4
0x14000bfe6  xor     ecx, ecx
0x14000bfe8  cmp     r8d, 80000022h
0x14000bfef  setnz   cl
0x14000bff2  mov     [rdi], ecx
0x14000bff4  mov     eax, r9d
0x14000bff7  mov     rcx, [rsp+68h+var_20]
0x14000bffc  xor     rcx, rsp; StackCookie
0x14000bfff  call    __security_check_cookie
0x14000c004  mov     rbx, [rsp+68h+arg_10]
0x14000c00c  add     rsp, 50h
0x14000c010  pop     rdi
0x14000c011  pop     rsi
0x14000c012  pop     rbp
0x14000c013  retn
0x14000c014  lea     r9, [rsp+68h+var_30]
0x14000c019  mov     edx, esi
0x14000c01b  lea     r8, [rsp+68h+var_38]
0x14000c020  mov     ecx, ebp
0x14000c022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c027  mov     r8d, eax
0x14000c02a  test    eax, eax
0x14000c02c  jnz     short loc_14000C076
0x14000c02e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000c032  lea     r9d, [r8+1]
0x14000c036  mov     eax, [rsp+68h+var_28]
0x14000c03a  mov     ecx, edx
0x14000c03c  mov     [rbx+0Ch], eax
0x14000c03f  mov     eax, edx
0x14000c041  shr     eax, 0Eh
0x14000c044  shr     ecx, 4
0x14000c047  and     eax, 3
0x14000c04a  and     ecx, 3
0x14000c04d  mov     [rbx+8], eax
0x14000c050  mov     [rbx], ecx
0x14000c052  mov     eax, edx
0x14000c054  mov     ecx, edx
0x14000c056  shr     eax, 6
0x14000c059  shr     ecx, 8
0x14000c05c  and     eax, r9d
0x14000c05f  and     cl, 3Fh
0x14000c062  shr     edx, 7
0x14000c065  and     edx, r9d
0x14000c068  mov     [rbx+4], cl
0x14000c06b  mov     [rbx+10h], edx
0x14000c06e  mov     [rbx+14h], eax
0x14000c071  jmp     loc_14000BFE1
0x14000c076  cmp     eax, 117h
0x14000c07b  jnz     loc_14000BFDE
0x14000c081  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000c085  mov     r9d, 1
0x14000c08b  shr     eax, 7
0x14000c08e  and     eax, r9d
0x14000c091  mov     [rbx+10h], eax
0x14000c094  jmp     loc_14000BFE1
```
