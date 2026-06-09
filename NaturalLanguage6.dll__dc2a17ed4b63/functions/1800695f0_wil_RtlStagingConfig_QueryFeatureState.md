# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800695f0`
- end: `0x180069715`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180066ca0`

## callees

- `0x18004088c`
- `0x1800695f0`
- `0x18009e300`
- `0x1800b0010`

## string_xrefs

- `0x18006963c`: `RtlQueryFeatureConfiguration`

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
0x1800695f0  mov     [rsp+arg_10], rbx
0x1800695f5  push    rbp
0x1800695f6  push    rsi
0x1800695f7  push    rdi
0x1800695f8  sub     rsp, 50h
0x1800695fc  mov     rax, cs:__security_cookie
0x180069603  xor     rax, rsp
0x180069606  mov     [rsp+68h+var_20], rax
0x18006960b  xor     esi, esi
0x18006960d  mov     [rsp+68h+var_38], 0
0x180069616  test    r8d, r8d
0x180069619  mov     rdi, r9
0x18006961c  mov     ebp, edx
0x18006961e  mov     rbx, rcx
0x180069621  setz    sil
0x180069625  xor     eax, eax
0x180069627  mov     [rsp+68h+var_30], rax
0x18006962c  mov     [rsp+68h+var_28], eax
0x180069630  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180069637  test    rax, rax
0x18006963a  jnz     short loc_180069690
0x18006963c  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180069643  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180069648  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18006964f  test    rax, rax
0x180069652  jnz     short loc_180069690
0x180069654  mov     r8d, 0C0000139h
0x18006965a  xor     r9d, r9d
0x18006965d  test    rdi, rdi
0x180069660  jz      short loc_180069670
0x180069662  xor     ecx, ecx
0x180069664  cmp     r8d, 80000022h
0x18006966b  setnz   cl
0x18006966e  mov     [rdi], ecx
0x180069670  mov     eax, r9d
0x180069673  mov     rcx, [rsp+68h+var_20]
0x180069678  xor     rcx, rsp; StackCookie
0x18006967b  call    __security_check_cookie
0x180069680  mov     rbx, [rsp+68h+arg_10]
0x180069688  add     rsp, 50h
0x18006968c  pop     rdi
0x18006968d  pop     rsi
0x18006968e  pop     rbp
0x18006968f  retn
0x180069690  lea     r9, [rsp+68h+var_30]
0x180069695  mov     edx, esi
0x180069697  lea     r8, [rsp+68h+var_38]
0x18006969c  mov     ecx, ebp
0x18006969e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800696a3  mov     r8d, eax
0x1800696a6  test    eax, eax
0x1800696a8  jnz     short loc_1800696F2
0x1800696aa  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800696ae  lea     r9d, [r8+1]
0x1800696b2  mov     eax, [rsp+68h+var_28]
0x1800696b6  mov     ecx, edx
0x1800696b8  mov     [rbx+0Ch], eax
0x1800696bb  mov     eax, edx
0x1800696bd  shr     eax, 0Eh
0x1800696c0  shr     ecx, 4
0x1800696c3  and     eax, 3
0x1800696c6  and     ecx, 3
0x1800696c9  mov     [rbx+8], eax
0x1800696cc  mov     [rbx], ecx
0x1800696ce  mov     eax, edx
0x1800696d0  mov     ecx, edx
0x1800696d2  shr     eax, 6
0x1800696d5  shr     ecx, 8
0x1800696d8  and     eax, r9d
0x1800696db  and     cl, 3Fh
0x1800696de  shr     edx, 7
0x1800696e1  and     edx, r9d
0x1800696e4  mov     [rbx+4], cl
0x1800696e7  mov     [rbx+10h], edx
0x1800696ea  mov     [rbx+14h], eax
0x1800696ed  jmp     loc_18006965D
0x1800696f2  cmp     eax, 117h
0x1800696f7  jnz     loc_18006965A
0x1800696fd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180069701  mov     r9d, 1
0x180069707  shr     eax, 7
0x18006970a  and     eax, r9d
0x18006970d  mov     [rbx+10h], eax
0x180069710  jmp     loc_18006965D
```
