# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800131f4`
- end: `0x180013319`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d930`

## callees

- `0x180003fc0`
- `0x180012ff0`
- `0x1800131f4`
- `0x180027010`

## string_xrefs

- `0x180013240`: `RtlQueryFeatureConfiguration`

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
0x1800131f4  mov     [rsp+arg_10], rbx
0x1800131f9  push    rbp
0x1800131fa  push    rsi
0x1800131fb  push    rdi
0x1800131fc  sub     rsp, 50h
0x180013200  mov     rax, cs:__security_cookie
0x180013207  xor     rax, rsp
0x18001320a  mov     [rsp+68h+var_20], rax
0x18001320f  xor     esi, esi
0x180013211  mov     [rsp+68h+var_38], 0
0x18001321a  test    r8d, r8d
0x18001321d  mov     rdi, r9
0x180013220  mov     ebp, edx
0x180013222  mov     rbx, rcx
0x180013225  setz    sil
0x180013229  xor     eax, eax
0x18001322b  mov     [rsp+68h+var_30], rax
0x180013230  mov     [rsp+68h+var_28], eax
0x180013234  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001323b  test    rax, rax
0x18001323e  jnz     short loc_180013294
0x180013240  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180013247  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001324c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180013253  test    rax, rax
0x180013256  jnz     short loc_180013294
0x180013258  mov     r8d, 0C0000139h
0x18001325e  xor     r9d, r9d
0x180013261  test    rdi, rdi
0x180013264  jz      short loc_180013274
0x180013266  xor     ecx, ecx
0x180013268  cmp     r8d, 80000022h
0x18001326f  setnz   cl
0x180013272  mov     [rdi], ecx
0x180013274  mov     eax, r9d
0x180013277  mov     rcx, [rsp+68h+var_20]
0x18001327c  xor     rcx, rsp; StackCookie
0x18001327f  call    __security_check_cookie
0x180013284  mov     rbx, [rsp+68h+arg_10]
0x18001328c  add     rsp, 50h
0x180013290  pop     rdi
0x180013291  pop     rsi
0x180013292  pop     rbp
0x180013293  retn
0x180013294  lea     r9, [rsp+68h+var_30]
0x180013299  mov     edx, esi
0x18001329b  lea     r8, [rsp+68h+var_38]
0x1800132a0  mov     ecx, ebp
0x1800132a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800132a7  mov     r8d, eax
0x1800132aa  test    eax, eax
0x1800132ac  jnz     short loc_1800132F6
0x1800132ae  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800132b2  lea     r9d, [r8+1]
0x1800132b6  mov     eax, [rsp+68h+var_28]
0x1800132ba  mov     ecx, edx
0x1800132bc  mov     [rbx+0Ch], eax
0x1800132bf  mov     eax, edx
0x1800132c1  shr     eax, 0Eh
0x1800132c4  shr     ecx, 4
0x1800132c7  and     eax, 3
0x1800132ca  and     ecx, 3
0x1800132cd  mov     [rbx+8], eax
0x1800132d0  mov     [rbx], ecx
0x1800132d2  mov     eax, edx
0x1800132d4  mov     ecx, edx
0x1800132d6  shr     eax, 6
0x1800132d9  shr     ecx, 8
0x1800132dc  and     eax, r9d
0x1800132df  and     cl, 3Fh
0x1800132e2  shr     edx, 7
0x1800132e5  and     edx, r9d
0x1800132e8  mov     [rbx+4], cl
0x1800132eb  mov     [rbx+10h], edx
0x1800132ee  mov     [rbx+14h], eax
0x1800132f1  jmp     loc_180013261
0x1800132f6  cmp     eax, 117h
0x1800132fb  jnz     loc_18001325E
0x180013301  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180013305  mov     r9d, 1
0x18001330b  shr     eax, 7
0x18001330e  and     eax, r9d
0x180013311  mov     [rbx+10h], eax
0x180013314  jmp     loc_180013261
```
