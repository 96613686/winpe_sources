# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180016ef0`
- end: `0x180017015`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001379c`

## callees

- `0x18000d2a0`
- `0x18000f050`
- `0x180016ef0`
- `0x180028010`

## string_xrefs

- `0x180016f3c`: `RtlQueryFeatureConfiguration`

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
  int v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF

  v17 = 0;
  v7 = a3 == 0;
  v15 = 0;
  v16 = 0;
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
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v17, &v15);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v15) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v15);
    v10 = 1;
    v14 = HIDWORD(v15);
    *(_DWORD *)(a1 + 12) = v16;
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
0x180016ef0  mov     [rsp+arg_10], rbx
0x180016ef5  push    rbp
0x180016ef6  push    rsi
0x180016ef7  push    rdi
0x180016ef8  sub     rsp, 50h
0x180016efc  mov     rax, cs:__security_cookie
0x180016f03  xor     rax, rsp
0x180016f06  mov     [rsp+68h+var_20], rax
0x180016f0b  xor     esi, esi
0x180016f0d  mov     [rsp+68h+var_28], 0
0x180016f16  test    r8d, r8d
0x180016f19  mov     rdi, r9
0x180016f1c  mov     ebp, edx
0x180016f1e  mov     rbx, rcx
0x180016f21  setz    sil
0x180016f25  xor     eax, eax
0x180016f27  mov     [rsp+68h+var_38], rax
0x180016f2c  mov     [rsp+68h+var_30], eax
0x180016f30  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180016f37  test    rax, rax
0x180016f3a  jnz     short loc_180016F90
0x180016f3c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180016f43  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180016f48  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180016f4f  test    rax, rax
0x180016f52  jnz     short loc_180016F90
0x180016f54  mov     r8d, 0C0000139h
0x180016f5a  xor     r9d, r9d
0x180016f5d  test    rdi, rdi
0x180016f60  jz      short loc_180016F70
0x180016f62  xor     ecx, ecx
0x180016f64  cmp     r8d, 80000022h
0x180016f6b  setnz   cl
0x180016f6e  mov     [rdi], ecx
0x180016f70  mov     eax, r9d
0x180016f73  mov     rcx, [rsp+68h+var_20]
0x180016f78  xor     rcx, rsp; StackCookie
0x180016f7b  call    __security_check_cookie
0x180016f80  mov     rbx, [rsp+68h+arg_10]
0x180016f88  add     rsp, 50h
0x180016f8c  pop     rdi
0x180016f8d  pop     rsi
0x180016f8e  pop     rbp
0x180016f8f  retn
0x180016f90  lea     r9, [rsp+68h+var_38]
0x180016f95  mov     edx, esi
0x180016f97  lea     r8, [rsp+68h+var_28]
0x180016f9c  mov     ecx, ebp
0x180016f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016fa3  mov     r8d, eax
0x180016fa6  test    eax, eax
0x180016fa8  jnz     short loc_180016FF2
0x180016faa  mov     edx, dword ptr [rsp+68h+var_38+4]
0x180016fae  lea     r9d, [r8+1]
0x180016fb2  mov     eax, [rsp+68h+var_30]
0x180016fb6  mov     ecx, edx
0x180016fb8  mov     [rbx+0Ch], eax
0x180016fbb  mov     eax, edx
0x180016fbd  shr     eax, 0Eh
0x180016fc0  shr     ecx, 4
0x180016fc3  and     eax, 3
0x180016fc6  and     ecx, 3
0x180016fc9  mov     [rbx+8], eax
0x180016fcc  mov     [rbx], ecx
0x180016fce  mov     eax, edx
0x180016fd0  mov     ecx, edx
0x180016fd2  shr     eax, 6
0x180016fd5  shr     ecx, 8
0x180016fd8  and     eax, r9d
0x180016fdb  and     cl, 3Fh
0x180016fde  shr     edx, 7
0x180016fe1  and     edx, r9d
0x180016fe4  mov     [rbx+4], cl
0x180016fe7  mov     [rbx+10h], edx
0x180016fea  mov     [rbx+14h], eax
0x180016fed  jmp     loc_180016F5D
0x180016ff2  cmp     eax, 117h
0x180016ff7  jnz     loc_180016F5A
0x180016ffd  mov     eax, dword ptr [rsp+68h+var_38+4]
0x180017001  mov     r9d, 1
0x180017007  shr     eax, 7
0x18001700a  and     eax, r9d
0x18001700d  mov     [rbx+10h], eax
0x180017010  jmp     loc_180016F5D
```
