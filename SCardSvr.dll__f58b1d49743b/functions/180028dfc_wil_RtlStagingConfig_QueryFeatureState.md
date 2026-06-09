# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180028dfc`
- end: `0x180028f21`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180028dd4`

## callees

- `0x1800288a0`
- `0x180028dfc`
- `0x1800326d0`
- `0x180037010`

## string_xrefs

- `0x180028e48`: `RtlQueryFeatureConfiguration`

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
0x180028dfc  mov     [rsp+arg_10], rbx
0x180028e01  push    rbp
0x180028e02  push    rsi
0x180028e03  push    rdi
0x180028e04  sub     rsp, 50h
0x180028e08  mov     rax, cs:__security_cookie
0x180028e0f  xor     rax, rsp
0x180028e12  mov     [rsp+68h+var_20], rax
0x180028e17  xor     esi, esi
0x180028e19  mov     [rsp+68h+var_38], 0
0x180028e22  test    r8d, r8d
0x180028e25  mov     rdi, r9
0x180028e28  mov     ebp, edx
0x180028e2a  mov     rbx, rcx
0x180028e2d  setz    sil
0x180028e31  xor     eax, eax
0x180028e33  mov     [rsp+68h+var_30], rax
0x180028e38  mov     [rsp+68h+var_28], eax
0x180028e3c  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180028e43  test    rax, rax
0x180028e46  jnz     short loc_180028E9C
0x180028e48  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180028e4f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180028e54  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180028e5b  test    rax, rax
0x180028e5e  jnz     short loc_180028E9C
0x180028e60  mov     r8d, 0C0000139h
0x180028e66  xor     r9d, r9d
0x180028e69  test    rdi, rdi
0x180028e6c  jz      short loc_180028E7C
0x180028e6e  xor     ecx, ecx
0x180028e70  cmp     r8d, 80000022h
0x180028e77  setnz   cl
0x180028e7a  mov     [rdi], ecx
0x180028e7c  mov     eax, r9d
0x180028e7f  mov     rcx, [rsp+68h+var_20]
0x180028e84  xor     rcx, rsp; StackCookie
0x180028e87  call    __security_check_cookie
0x180028e8c  mov     rbx, [rsp+68h+arg_10]
0x180028e94  add     rsp, 50h
0x180028e98  pop     rdi
0x180028e99  pop     rsi
0x180028e9a  pop     rbp
0x180028e9b  retn
0x180028e9c  lea     r9, [rsp+68h+var_30]
0x180028ea1  mov     edx, esi
0x180028ea3  lea     r8, [rsp+68h+var_38]
0x180028ea8  mov     ecx, ebp
0x180028eaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028eaf  mov     r8d, eax
0x180028eb2  test    eax, eax
0x180028eb4  jnz     short loc_180028EFE
0x180028eb6  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180028eba  lea     r9d, [r8+1]
0x180028ebe  mov     eax, [rsp+68h+var_28]
0x180028ec2  mov     ecx, edx
0x180028ec4  mov     [rbx+0Ch], eax
0x180028ec7  mov     eax, edx
0x180028ec9  shr     eax, 0Eh
0x180028ecc  shr     ecx, 4
0x180028ecf  and     eax, 3
0x180028ed2  and     ecx, 3
0x180028ed5  mov     [rbx+8], eax
0x180028ed8  mov     [rbx], ecx
0x180028eda  mov     eax, edx
0x180028edc  mov     ecx, edx
0x180028ede  shr     eax, 6
0x180028ee1  shr     ecx, 8
0x180028ee4  and     eax, r9d
0x180028ee7  and     cl, 3Fh
0x180028eea  shr     edx, 7
0x180028eed  and     edx, r9d
0x180028ef0  mov     [rbx+4], cl
0x180028ef3  mov     [rbx+10h], edx
0x180028ef6  mov     [rbx+14h], eax
0x180028ef9  jmp     loc_180028E69
0x180028efe  cmp     eax, 117h
0x180028f03  jnz     loc_180028E66
0x180028f09  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180028f0d  mov     r9d, 1
0x180028f13  shr     eax, 7
0x180028f16  and     eax, r9d
0x180028f19  mov     [rbx+10h], eax
0x180028f1c  jmp     loc_180028E69
```
