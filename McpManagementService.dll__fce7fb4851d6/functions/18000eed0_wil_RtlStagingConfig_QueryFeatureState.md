# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000eed0`
- end: `0x18000eff5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000eea8`

## callees

- `0x180003a60`
- `0x18000eb20`
- `0x18000eed0`
- `0x18002b010`

## string_xrefs

- `0x18000ef1c`: `RtlQueryFeatureConfiguration`

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
0x18000eed0  mov     [rsp+arg_10], rbx
0x18000eed5  push    rbp
0x18000eed6  push    rsi
0x18000eed7  push    rdi
0x18000eed8  sub     rsp, 50h
0x18000eedc  mov     rax, cs:__security_cookie
0x18000eee3  xor     rax, rsp
0x18000eee6  mov     [rsp+68h+var_20], rax
0x18000eeeb  xor     esi, esi
0x18000eeed  mov     [rsp+68h+var_38], 0
0x18000eef6  test    r8d, r8d
0x18000eef9  mov     rdi, r9
0x18000eefc  mov     ebp, edx
0x18000eefe  mov     rbx, rcx
0x18000ef01  setz    sil
0x18000ef05  xor     eax, eax
0x18000ef07  mov     [rsp+68h+var_30], rax
0x18000ef0c  mov     [rsp+68h+var_28], eax
0x18000ef10  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ef17  test    rax, rax
0x18000ef1a  jnz     short loc_18000EF70
0x18000ef1c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ef23  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000ef28  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ef2f  test    rax, rax
0x18000ef32  jnz     short loc_18000EF70
0x18000ef34  mov     r8d, 0C0000139h
0x18000ef3a  xor     r9d, r9d
0x18000ef3d  test    rdi, rdi
0x18000ef40  jz      short loc_18000EF50
0x18000ef42  xor     ecx, ecx
0x18000ef44  cmp     r8d, 80000022h
0x18000ef4b  setnz   cl
0x18000ef4e  mov     [rdi], ecx
0x18000ef50  mov     eax, r9d
0x18000ef53  mov     rcx, [rsp+68h+var_20]
0x18000ef58  xor     rcx, rsp; StackCookie
0x18000ef5b  call    __security_check_cookie
0x18000ef60  mov     rbx, [rsp+68h+arg_10]
0x18000ef68  add     rsp, 50h
0x18000ef6c  pop     rdi
0x18000ef6d  pop     rsi
0x18000ef6e  pop     rbp
0x18000ef6f  retn
0x18000ef70  lea     r9, [rsp+68h+var_30]
0x18000ef75  mov     edx, esi
0x18000ef77  lea     r8, [rsp+68h+var_38]
0x18000ef7c  mov     ecx, ebp
0x18000ef7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ef83  mov     r8d, eax
0x18000ef86  test    eax, eax
0x18000ef88  jnz     short loc_18000EFD2
0x18000ef8a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000ef8e  lea     r9d, [r8+1]
0x18000ef92  mov     eax, [rsp+68h+var_28]
0x18000ef96  mov     ecx, edx
0x18000ef98  mov     [rbx+0Ch], eax
0x18000ef9b  mov     eax, edx
0x18000ef9d  shr     eax, 0Eh
0x18000efa0  shr     ecx, 4
0x18000efa3  and     eax, 3
0x18000efa6  and     ecx, 3
0x18000efa9  mov     [rbx+8], eax
0x18000efac  mov     [rbx], ecx
0x18000efae  mov     eax, edx
0x18000efb0  mov     ecx, edx
0x18000efb2  shr     eax, 6
0x18000efb5  shr     ecx, 8
0x18000efb8  and     eax, r9d
0x18000efbb  and     cl, 3Fh
0x18000efbe  shr     edx, 7
0x18000efc1  and     edx, r9d
0x18000efc4  mov     [rbx+4], cl
0x18000efc7  mov     [rbx+10h], edx
0x18000efca  mov     [rbx+14h], eax
0x18000efcd  jmp     loc_18000EF3D
0x18000efd2  cmp     eax, 117h
0x18000efd7  jnz     loc_18000EF3A
0x18000efdd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000efe1  mov     r9d, 1
0x18000efe7  shr     eax, 7
0x18000efea  and     eax, r9d
0x18000efed  mov     [rbx+10h], eax
0x18000eff0  jmp     loc_18000EF3D
```
