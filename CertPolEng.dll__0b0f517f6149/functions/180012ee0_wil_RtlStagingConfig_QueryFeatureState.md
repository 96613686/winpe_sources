# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180012ee0`
- end: `0x180013005`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180009220`

## callees

- `0x18000dc44`
- `0x180012ee0`
- `0x18001a380`
- `0x18001b010`

## string_xrefs

- `0x180012f2c`: `RtlQueryFeatureConfiguration`

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
0x180012ee0  mov     [rsp+arg_10], rbx
0x180012ee5  push    rbp
0x180012ee6  push    rsi
0x180012ee7  push    rdi
0x180012ee8  sub     rsp, 50h
0x180012eec  mov     rax, cs:__security_cookie
0x180012ef3  xor     rax, rsp
0x180012ef6  mov     [rsp+68h+var_20], rax
0x180012efb  xor     esi, esi
0x180012efd  mov     [rsp+68h+var_38], 0
0x180012f06  test    r8d, r8d
0x180012f09  mov     rdi, r9
0x180012f0c  mov     ebp, edx
0x180012f0e  mov     rbx, rcx
0x180012f11  setz    sil
0x180012f15  xor     eax, eax
0x180012f17  mov     [rsp+68h+var_30], rax
0x180012f1c  mov     [rsp+68h+var_28], eax
0x180012f20  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180012f27  test    rax, rax
0x180012f2a  jnz     short loc_180012F80
0x180012f2c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180012f33  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012f38  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180012f3f  test    rax, rax
0x180012f42  jnz     short loc_180012F80
0x180012f44  mov     r8d, 0C0000139h
0x180012f4a  xor     r9d, r9d
0x180012f4d  test    rdi, rdi
0x180012f50  jz      short loc_180012F60
0x180012f52  xor     ecx, ecx
0x180012f54  cmp     r8d, 80000022h
0x180012f5b  setnz   cl
0x180012f5e  mov     [rdi], ecx
0x180012f60  mov     eax, r9d
0x180012f63  mov     rcx, [rsp+68h+var_20]
0x180012f68  xor     rcx, rsp; StackCookie
0x180012f6b  call    __security_check_cookie
0x180012f70  mov     rbx, [rsp+68h+arg_10]
0x180012f78  add     rsp, 50h
0x180012f7c  pop     rdi
0x180012f7d  pop     rsi
0x180012f7e  pop     rbp
0x180012f7f  retn
0x180012f80  lea     r9, [rsp+68h+var_30]
0x180012f85  mov     edx, esi
0x180012f87  lea     r8, [rsp+68h+var_38]
0x180012f8c  mov     ecx, ebp
0x180012f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f93  mov     r8d, eax
0x180012f96  test    eax, eax
0x180012f98  jnz     short loc_180012FE2
0x180012f9a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180012f9e  lea     r9d, [r8+1]
0x180012fa2  mov     eax, [rsp+68h+var_28]
0x180012fa6  mov     ecx, edx
0x180012fa8  mov     [rbx+0Ch], eax
0x180012fab  mov     eax, edx
0x180012fad  shr     eax, 0Eh
0x180012fb0  shr     ecx, 4
0x180012fb3  and     eax, 3
0x180012fb6  and     ecx, 3
0x180012fb9  mov     [rbx+8], eax
0x180012fbc  mov     [rbx], ecx
0x180012fbe  mov     eax, edx
0x180012fc0  mov     ecx, edx
0x180012fc2  shr     eax, 6
0x180012fc5  shr     ecx, 8
0x180012fc8  and     eax, r9d
0x180012fcb  and     cl, 3Fh
0x180012fce  shr     edx, 7
0x180012fd1  and     edx, r9d
0x180012fd4  mov     [rbx+4], cl
0x180012fd7  mov     [rbx+10h], edx
0x180012fda  mov     [rbx+14h], eax
0x180012fdd  jmp     loc_180012F4D
0x180012fe2  cmp     eax, 117h
0x180012fe7  jnz     loc_180012F4A
0x180012fed  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180012ff1  mov     r9d, 1
0x180012ff7  shr     eax, 7
0x180012ffa  and     eax, r9d
0x180012ffd  mov     [rbx+10h], eax
0x180013000  jmp     loc_180012F4D
```
