# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x140009a1c`
- end: `0x140009b41`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140006100`

## callees

- `0x14000972c`
- `0x140009a1c`
- `0x14001edc0`
- `0x140020010`

## string_xrefs

- `0x140009a68`: `RtlQueryFeatureConfiguration`

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
0x140009a1c  mov     [rsp+arg_10], rbx
0x140009a21  push    rbp
0x140009a22  push    rsi
0x140009a23  push    rdi
0x140009a24  sub     rsp, 50h
0x140009a28  mov     rax, cs:__security_cookie
0x140009a2f  xor     rax, rsp
0x140009a32  mov     [rsp+68h+var_20], rax
0x140009a37  xor     esi, esi
0x140009a39  mov     [rsp+68h+var_38], 0
0x140009a42  test    r8d, r8d
0x140009a45  mov     rdi, r9
0x140009a48  mov     ebp, edx
0x140009a4a  mov     rbx, rcx
0x140009a4d  setz    sil
0x140009a51  xor     eax, eax
0x140009a53  mov     [rsp+68h+var_30], rax
0x140009a58  mov     [rsp+68h+var_28], eax
0x140009a5c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140009a63  test    rax, rax
0x140009a66  jnz     short loc_140009ABC
0x140009a68  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x140009a6f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140009a74  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x140009a7b  test    rax, rax
0x140009a7e  jnz     short loc_140009ABC
0x140009a80  mov     r8d, 0C0000139h
0x140009a86  xor     r9d, r9d
0x140009a89  test    rdi, rdi
0x140009a8c  jz      short loc_140009A9C
0x140009a8e  xor     ecx, ecx
0x140009a90  cmp     r8d, 80000022h
0x140009a97  setnz   cl
0x140009a9a  mov     [rdi], ecx
0x140009a9c  mov     eax, r9d
0x140009a9f  mov     rcx, [rsp+68h+var_20]
0x140009aa4  xor     rcx, rsp; StackCookie
0x140009aa7  call    __security_check_cookie
0x140009aac  mov     rbx, [rsp+68h+arg_10]
0x140009ab4  add     rsp, 50h
0x140009ab8  pop     rdi
0x140009ab9  pop     rsi
0x140009aba  pop     rbp
0x140009abb  retn
0x140009abc  lea     r9, [rsp+68h+var_30]
0x140009ac1  mov     edx, esi
0x140009ac3  lea     r8, [rsp+68h+var_38]
0x140009ac8  mov     ecx, ebp
0x140009aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009acf  mov     r8d, eax
0x140009ad2  test    eax, eax
0x140009ad4  jnz     short loc_140009B1E
0x140009ad6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x140009ada  lea     r9d, [r8+1]
0x140009ade  mov     eax, [rsp+68h+var_28]
0x140009ae2  mov     ecx, edx
0x140009ae4  mov     [rbx+0Ch], eax
0x140009ae7  mov     eax, edx
0x140009ae9  shr     eax, 0Eh
0x140009aec  shr     ecx, 4
0x140009aef  and     eax, 3
0x140009af2  and     ecx, 3
0x140009af5  mov     [rbx+8], eax
0x140009af8  mov     [rbx], ecx
0x140009afa  mov     eax, edx
0x140009afc  mov     ecx, edx
0x140009afe  shr     eax, 6
0x140009b01  shr     ecx, 8
0x140009b04  and     eax, r9d
0x140009b07  and     cl, 3Fh
0x140009b0a  shr     edx, 7
0x140009b0d  and     edx, r9d
0x140009b10  mov     [rbx+4], cl
0x140009b13  mov     [rbx+10h], edx
0x140009b16  mov     [rbx+14h], eax
0x140009b19  jmp     loc_140009A89
0x140009b1e  cmp     eax, 117h
0x140009b23  jnz     loc_140009A86
0x140009b29  mov     eax, dword ptr [rsp+68h+var_30+4]
0x140009b2d  mov     r9d, 1
0x140009b33  shr     eax, 7
0x140009b36  and     eax, r9d
0x140009b39  mov     [rbx+10h], eax
0x140009b3c  jmp     loc_140009A89
```
