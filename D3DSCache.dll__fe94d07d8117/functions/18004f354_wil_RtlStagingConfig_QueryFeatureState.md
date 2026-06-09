# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18004f354`
- end: `0x18004f479`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18004b054`

## callees

- `0x1800449f0`
- `0x180046ad0`
- `0x18004f354`
- `0x1800a8010`

## string_xrefs

- `0x18004f3a0`: `RtlQueryFeatureConfiguration`

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
0x18004f354  mov     [rsp+arg_10], rbx
0x18004f359  push    rbp
0x18004f35a  push    rsi
0x18004f35b  push    rdi
0x18004f35c  sub     rsp, 50h
0x18004f360  mov     rax, cs:__security_cookie
0x18004f367  xor     rax, rsp
0x18004f36a  mov     [rsp+68h+var_20], rax
0x18004f36f  xor     esi, esi
0x18004f371  mov     [rsp+68h+var_38], 0
0x18004f37a  test    r8d, r8d
0x18004f37d  mov     rdi, r9
0x18004f380  mov     ebp, edx
0x18004f382  mov     rbx, rcx
0x18004f385  setz    sil
0x18004f389  xor     eax, eax
0x18004f38b  mov     [rsp+68h+var_30], rax
0x18004f390  mov     [rsp+68h+var_28], eax
0x18004f394  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18004f39b  test    rax, rax
0x18004f39e  jnz     short loc_18004F3F4
0x18004f3a0  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18004f3a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18004f3ac  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18004f3b3  test    rax, rax
0x18004f3b6  jnz     short loc_18004F3F4
0x18004f3b8  mov     r8d, 0C0000139h
0x18004f3be  xor     r9d, r9d
0x18004f3c1  test    rdi, rdi
0x18004f3c4  jz      short loc_18004F3D4
0x18004f3c6  xor     ecx, ecx
0x18004f3c8  cmp     r8d, 80000022h
0x18004f3cf  setnz   cl
0x18004f3d2  mov     [rdi], ecx
0x18004f3d4  mov     eax, r9d
0x18004f3d7  mov     rcx, [rsp+68h+var_20]
0x18004f3dc  xor     rcx, rsp; StackCookie
0x18004f3df  call    __security_check_cookie
0x18004f3e4  mov     rbx, [rsp+68h+arg_10]
0x18004f3ec  add     rsp, 50h
0x18004f3f0  pop     rdi
0x18004f3f1  pop     rsi
0x18004f3f2  pop     rbp
0x18004f3f3  retn
0x18004f3f4  lea     r9, [rsp+68h+var_30]
0x18004f3f9  mov     edx, esi
0x18004f3fb  lea     r8, [rsp+68h+var_38]
0x18004f400  mov     ecx, ebp
0x18004f402  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f407  mov     r8d, eax
0x18004f40a  test    eax, eax
0x18004f40c  jnz     short loc_18004F456
0x18004f40e  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18004f412  lea     r9d, [r8+1]
0x18004f416  mov     eax, [rsp+68h+var_28]
0x18004f41a  mov     ecx, edx
0x18004f41c  mov     [rbx+0Ch], eax
0x18004f41f  mov     eax, edx
0x18004f421  shr     eax, 0Eh
0x18004f424  shr     ecx, 4
0x18004f427  and     eax, 3
0x18004f42a  and     ecx, 3
0x18004f42d  mov     [rbx+8], eax
0x18004f430  mov     [rbx], ecx
0x18004f432  mov     eax, edx
0x18004f434  mov     ecx, edx
0x18004f436  shr     eax, 6
0x18004f439  shr     ecx, 8
0x18004f43c  and     eax, r9d
0x18004f43f  and     cl, 3Fh
0x18004f442  shr     edx, 7
0x18004f445  and     edx, r9d
0x18004f448  mov     [rbx+4], cl
0x18004f44b  mov     [rbx+10h], edx
0x18004f44e  mov     [rbx+14h], eax
0x18004f451  jmp     loc_18004F3C1
0x18004f456  cmp     eax, 117h
0x18004f45b  jnz     loc_18004F3BE
0x18004f461  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18004f465  mov     r9d, 1
0x18004f46b  shr     eax, 7
0x18004f46e  and     eax, r9d
0x18004f471  mov     [rbx+10h], eax
0x18004f474  jmp     loc_18004F3C1
```
