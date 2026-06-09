# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800a76e0`
- end: `0x1800a7805`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800a7e9c`
- `0x1800aad04`

## callees

- `0x1800789c0`
- `0x1800a76e0`
- `0x1800a7fb4`
- `0x1800b0010`

## string_xrefs

- `0x1800a772c`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
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
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress;
    if ( !NtDllProcedureAddress )
    {
      v9 = -1073741511;
LABEL_4:
      v10 = 0;
      goto LABEL_5;
    }
  }
  v12 = NtDllProcedureAddress(a2, v7, &v15, &v16);
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
0x1800a76e0  mov     [rsp+arg_10], rbx
0x1800a76e5  push    rbp
0x1800a76e6  push    rsi
0x1800a76e7  push    rdi
0x1800a76e8  sub     rsp, 50h
0x1800a76ec  mov     rax, cs:__security_cookie
0x1800a76f3  xor     rax, rsp
0x1800a76f6  mov     [rsp+68h+var_20], rax
0x1800a76fb  xor     esi, esi
0x1800a76fd  mov     [rsp+68h+var_38], 0
0x1800a7706  test    r8d, r8d
0x1800a7709  mov     rdi, r9
0x1800a770c  mov     ebp, edx
0x1800a770e  mov     rbx, rcx
0x1800a7711  setz    sil
0x1800a7715  xor     eax, eax
0x1800a7717  mov     [rsp+68h+var_30], rax
0x1800a771c  mov     [rsp+68h+var_28], eax
0x1800a7720  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800a7727  test    rax, rax
0x1800a772a  jnz     short loc_1800A7780
0x1800a772c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800a7733  call    wil_details_GetNtDllProcedureAddress
0x1800a7738  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800a773f  test    rax, rax
0x1800a7742  jnz     short loc_1800A7780
0x1800a7744  mov     r8d, 0C0000139h
0x1800a774a  xor     r9d, r9d
0x1800a774d  test    rdi, rdi
0x1800a7750  jz      short loc_1800A7760
0x1800a7752  xor     ecx, ecx
0x1800a7754  cmp     r8d, 80000022h
0x1800a775b  setnz   cl
0x1800a775e  mov     [rdi], ecx
0x1800a7760  mov     eax, r9d
0x1800a7763  mov     rcx, [rsp+68h+var_20]
0x1800a7768  xor     rcx, rsp; StackCookie
0x1800a776b  call    __security_check_cookie
0x1800a7770  mov     rbx, [rsp+68h+arg_10]
0x1800a7778  add     rsp, 50h
0x1800a777c  pop     rdi
0x1800a777d  pop     rsi
0x1800a777e  pop     rbp
0x1800a777f  retn
0x1800a7780  lea     r9, [rsp+68h+var_30]
0x1800a7785  mov     edx, esi
0x1800a7787  lea     r8, [rsp+68h+var_38]
0x1800a778c  mov     ecx, ebp
0x1800a778e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a7793  mov     r8d, eax
0x1800a7796  test    eax, eax
0x1800a7798  jnz     short loc_1800A77E2
0x1800a779a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800a779e  lea     r9d, [r8+1]
0x1800a77a2  mov     eax, [rsp+68h+var_28]
0x1800a77a6  mov     ecx, edx
0x1800a77a8  mov     [rbx+0Ch], eax
0x1800a77ab  mov     eax, edx
0x1800a77ad  shr     eax, 0Eh
0x1800a77b0  shr     ecx, 4
0x1800a77b3  and     eax, 3
0x1800a77b6  and     ecx, 3
0x1800a77b9  mov     [rbx+8], eax
0x1800a77bc  mov     [rbx], ecx
0x1800a77be  mov     eax, edx
0x1800a77c0  mov     ecx, edx
0x1800a77c2  shr     eax, 6
0x1800a77c5  shr     ecx, 8
0x1800a77c8  and     eax, r9d
0x1800a77cb  and     cl, 3Fh
0x1800a77ce  shr     edx, 7
0x1800a77d1  and     edx, r9d
0x1800a77d4  mov     [rbx+4], cl
0x1800a77d7  mov     [rbx+10h], edx
0x1800a77da  mov     [rbx+14h], eax
0x1800a77dd  jmp     loc_1800A774D
0x1800a77e2  cmp     eax, 117h
0x1800a77e7  jnz     loc_1800A774A
0x1800a77ed  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800a77f1  mov     r9d, 1
0x1800a77f7  shr     eax, 7
0x1800a77fa  and     eax, r9d
0x1800a77fd  mov     [rbx+10h], eax
0x1800a7800  jmp     loc_1800A774D
```
