# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000ed94`
- end: `0x18000eeb9`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a5ac`

## callees

- `0x1800024c0`
- `0x18000eb20`
- `0x18000ed94`
- `0x18002a010`

## string_xrefs

- `0x18000ede0`: `RtlQueryFeatureConfiguration`

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
0x18000ed94  mov     [rsp+arg_10], rbx
0x18000ed99  push    rbp
0x18000ed9a  push    rsi
0x18000ed9b  push    rdi
0x18000ed9c  sub     rsp, 50h
0x18000eda0  mov     rax, cs:__security_cookie
0x18000eda7  xor     rax, rsp
0x18000edaa  mov     [rsp+68h+var_20], rax
0x18000edaf  xor     esi, esi
0x18000edb1  mov     [rsp+68h+var_38], 0
0x18000edba  test    r8d, r8d
0x18000edbd  mov     rdi, r9
0x18000edc0  mov     ebp, edx
0x18000edc2  mov     rbx, rcx
0x18000edc5  setz    sil
0x18000edc9  xor     eax, eax
0x18000edcb  mov     [rsp+68h+var_30], rax
0x18000edd0  mov     [rsp+68h+var_28], eax
0x18000edd4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000eddb  test    rax, rax
0x18000edde  jnz     short loc_18000EE34
0x18000ede0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ede7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000edec  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000edf3  test    rax, rax
0x18000edf6  jnz     short loc_18000EE34
0x18000edf8  mov     r8d, 0C0000139h
0x18000edfe  xor     r9d, r9d
0x18000ee01  test    rdi, rdi
0x18000ee04  jz      short loc_18000EE14
0x18000ee06  xor     ecx, ecx
0x18000ee08  cmp     r8d, 80000022h
0x18000ee0f  setnz   cl
0x18000ee12  mov     [rdi], ecx
0x18000ee14  mov     eax, r9d
0x18000ee17  mov     rcx, [rsp+68h+var_20]
0x18000ee1c  xor     rcx, rsp; StackCookie
0x18000ee1f  call    __security_check_cookie
0x18000ee24  mov     rbx, [rsp+68h+arg_10]
0x18000ee2c  add     rsp, 50h
0x18000ee30  pop     rdi
0x18000ee31  pop     rsi
0x18000ee32  pop     rbp
0x18000ee33  retn
0x18000ee34  lea     r9, [rsp+68h+var_30]
0x18000ee39  mov     edx, esi
0x18000ee3b  lea     r8, [rsp+68h+var_38]
0x18000ee40  mov     ecx, ebp
0x18000ee42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ee47  mov     r8d, eax
0x18000ee4a  test    eax, eax
0x18000ee4c  jnz     short loc_18000EE96
0x18000ee4e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000ee52  lea     r9d, [r8+1]
0x18000ee56  mov     eax, [rsp+68h+var_28]
0x18000ee5a  mov     ecx, edx
0x18000ee5c  mov     [rbx+0Ch], eax
0x18000ee5f  mov     eax, edx
0x18000ee61  shr     eax, 0Eh
0x18000ee64  shr     ecx, 4
0x18000ee67  and     eax, 3
0x18000ee6a  and     ecx, 3
0x18000ee6d  mov     [rbx+8], eax
0x18000ee70  mov     [rbx], ecx
0x18000ee72  mov     eax, edx
0x18000ee74  mov     ecx, edx
0x18000ee76  shr     eax, 6
0x18000ee79  shr     ecx, 8
0x18000ee7c  and     eax, r9d
0x18000ee7f  and     cl, 3Fh
0x18000ee82  shr     edx, 7
0x18000ee85  and     edx, r9d
0x18000ee88  mov     [rbx+4], cl
0x18000ee8b  mov     [rbx+10h], edx
0x18000ee8e  mov     [rbx+14h], eax
0x18000ee91  jmp     loc_18000EE01
0x18000ee96  cmp     eax, 117h
0x18000ee9b  jnz     loc_18000EDFE
0x18000eea1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000eea5  mov     r9d, 1
0x18000eeab  shr     eax, 7
0x18000eeae  and     eax, r9d
0x18000eeb1  mov     [rbx+10h], eax
0x18000eeb4  jmp     loc_18000EE01
```
