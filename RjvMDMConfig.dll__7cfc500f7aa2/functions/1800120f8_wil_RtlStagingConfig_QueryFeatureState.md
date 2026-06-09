# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800120f8`
- end: `0x18001221e`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `294`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800120d0`

## callees

- `0x180001c60`
- `0x180005940`
- `0x1800120f8`
- `0x18001e010`

## string_xrefs

- `0x180012144`: `RtlQueryFeatureConfiguration`

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
0x1800120f8  mov     [rsp+arg_10], rbx
0x1800120fd  push    rbp
0x1800120fe  push    rsi
0x1800120ff  push    rdi
0x180012100  sub     rsp, 50h
0x180012104  mov     rax, cs:__security_cookie
0x18001210b  xor     rax, rsp
0x18001210e  mov     [rsp+68h+var_20], rax
0x180012113  xor     esi, esi
0x180012115  mov     [rsp+68h+var_38], 0
0x18001211e  test    r8d, r8d
0x180012121  mov     rdi, r9
0x180012124  mov     ebp, edx
0x180012126  mov     rbx, rcx
0x180012129  setz    sil
0x18001212d  xor     eax, eax
0x18001212f  mov     [rsp+68h+var_30], rax
0x180012134  mov     [rsp+68h+var_28], eax
0x180012138  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001213f  test    rax, rax
0x180012142  jnz     short loc_180012199
0x180012144  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18001214b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012150  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180012157  test    rax, rax
0x18001215a  jnz     short loc_180012199
0x18001215c  mov     r8d, 0C0000139h
0x180012162  xor     r9d, r9d
0x180012165  test    rdi, rdi
0x180012168  jz      short loc_180012178
0x18001216a  xor     ecx, ecx
0x18001216c  cmp     r8d, 80000022h
0x180012173  setnz   cl
0x180012176  mov     [rdi], ecx
0x180012178  mov     eax, r9d
0x18001217b  mov     rcx, [rsp+68h+var_20]
0x180012180  xor     rcx, rsp; StackCookie
0x180012183  call    __security_check_cookie
0x180012188  mov     rbx, [rsp+68h+arg_10]
0x180012190  add     rsp, 50h
0x180012194  pop     rdi
0x180012195  pop     rsi
0x180012196  pop     rbp
0x180012197  retn
0x180012199  lea     r9, [rsp+68h+var_30]
0x18001219e  mov     edx, esi
0x1800121a0  lea     r8, [rsp+68h+var_38]
0x1800121a5  mov     ecx, ebp
0x1800121a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121ac  mov     r8d, eax
0x1800121af  test    eax, eax
0x1800121b1  jnz     short loc_1800121FB
0x1800121b3  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800121b7  lea     r9d, [r8+1]
0x1800121bb  mov     eax, [rsp+68h+var_28]
0x1800121bf  mov     ecx, edx
0x1800121c1  mov     [rbx+0Ch], eax
0x1800121c4  mov     eax, edx
0x1800121c6  shr     eax, 0Eh
0x1800121c9  shr     ecx, 4
0x1800121cc  and     eax, 3
0x1800121cf  and     ecx, 3
0x1800121d2  mov     [rbx+8], eax
0x1800121d5  mov     [rbx], ecx
0x1800121d7  mov     eax, edx
0x1800121d9  mov     ecx, edx
0x1800121db  shr     eax, 6
0x1800121de  shr     ecx, 8
0x1800121e1  and     eax, r9d
0x1800121e4  and     cl, 3Fh
0x1800121e7  shr     edx, 7
0x1800121ea  and     edx, r9d
0x1800121ed  mov     [rbx+4], cl
0x1800121f0  mov     [rbx+10h], edx
0x1800121f3  mov     [rbx+14h], eax
0x1800121f6  jmp     loc_180012165
0x1800121fb  cmp     eax, 117h
0x180012200  jnz     loc_180012162
0x180012206  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001220a  mov     r9d, 1
0x180012210  shr     eax, 7
0x180012213  and     eax, r9d
0x180012216  mov     [rbx+10h], eax
0x180012219  jmp     loc_180012165
```
