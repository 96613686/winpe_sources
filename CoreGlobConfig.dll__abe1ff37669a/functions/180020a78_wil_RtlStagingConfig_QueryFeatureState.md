# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180020a78`
- end: `0x180020b9d`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180020a50`

## callees

- `0x180002380`
- `0x1800092d0`
- `0x180020a78`
- `0x180025010`

## string_xrefs

- `0x180020ac4`: `RtlQueryFeatureConfiguration`

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
0x180020a78  mov     [rsp+arg_10], rbx
0x180020a7d  push    rbp
0x180020a7e  push    rsi
0x180020a7f  push    rdi
0x180020a80  sub     rsp, 50h
0x180020a84  mov     rax, cs:__security_cookie
0x180020a8b  xor     rax, rsp
0x180020a8e  mov     [rsp+68h+var_20], rax
0x180020a93  xor     esi, esi
0x180020a95  mov     [rsp+68h+var_38], 0
0x180020a9e  test    r8d, r8d
0x180020aa1  mov     rdi, r9
0x180020aa4  mov     ebp, edx
0x180020aa6  mov     rbx, rcx
0x180020aa9  setz    sil
0x180020aad  xor     eax, eax
0x180020aaf  mov     [rsp+68h+var_30], rax
0x180020ab4  mov     [rsp+68h+var_28], eax
0x180020ab8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180020abf  test    rax, rax
0x180020ac2  jnz     short loc_180020B18
0x180020ac4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180020acb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180020ad0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180020ad7  test    rax, rax
0x180020ada  jnz     short loc_180020B18
0x180020adc  mov     r8d, 0C0000139h
0x180020ae2  xor     r9d, r9d
0x180020ae5  test    rdi, rdi
0x180020ae8  jz      short loc_180020AF8
0x180020aea  xor     ecx, ecx
0x180020aec  cmp     r8d, 80000022h
0x180020af3  setnz   cl
0x180020af6  mov     [rdi], ecx
0x180020af8  mov     eax, r9d
0x180020afb  mov     rcx, [rsp+68h+var_20]
0x180020b00  xor     rcx, rsp; StackCookie
0x180020b03  call    __security_check_cookie
0x180020b08  mov     rbx, [rsp+68h+arg_10]
0x180020b10  add     rsp, 50h
0x180020b14  pop     rdi
0x180020b15  pop     rsi
0x180020b16  pop     rbp
0x180020b17  retn
0x180020b18  lea     r9, [rsp+68h+var_30]
0x180020b1d  mov     edx, esi
0x180020b1f  lea     r8, [rsp+68h+var_38]
0x180020b24  mov     ecx, ebp
0x180020b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020b2b  mov     r8d, eax
0x180020b2e  test    eax, eax
0x180020b30  jnz     short loc_180020B7A
0x180020b32  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180020b36  lea     r9d, [r8+1]
0x180020b3a  mov     eax, [rsp+68h+var_28]
0x180020b3e  mov     ecx, edx
0x180020b40  mov     [rbx+0Ch], eax
0x180020b43  mov     eax, edx
0x180020b45  shr     eax, 0Eh
0x180020b48  shr     ecx, 4
0x180020b4b  and     eax, 3
0x180020b4e  and     ecx, 3
0x180020b51  mov     [rbx+8], eax
0x180020b54  mov     [rbx], ecx
0x180020b56  mov     eax, edx
0x180020b58  mov     ecx, edx
0x180020b5a  shr     eax, 6
0x180020b5d  shr     ecx, 8
0x180020b60  and     eax, r9d
0x180020b63  and     cl, 3Fh
0x180020b66  shr     edx, 7
0x180020b69  and     edx, r9d
0x180020b6c  mov     [rbx+4], cl
0x180020b6f  mov     [rbx+10h], edx
0x180020b72  mov     [rbx+14h], eax
0x180020b75  jmp     loc_180020AE5
0x180020b7a  cmp     eax, 117h
0x180020b7f  jnz     loc_180020AE2
0x180020b85  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180020b89  mov     r9d, 1
0x180020b8f  shr     eax, 7
0x180020b92  and     eax, r9d
0x180020b95  mov     [rbx+10h], eax
0x180020b98  jmp     loc_180020AE5
```
