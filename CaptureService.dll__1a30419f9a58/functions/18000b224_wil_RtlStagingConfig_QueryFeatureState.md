# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000b224`
- end: `0x18000b349`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000765c`

## callees

- `0x180002e60`
- `0x18000af90`
- `0x18000b224`
- `0x180022010`

## string_xrefs

- `0x18000b270`: `RtlQueryFeatureConfiguration`

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
0x18000b224  mov     [rsp+arg_10], rbx
0x18000b229  push    rbp
0x18000b22a  push    rsi
0x18000b22b  push    rdi
0x18000b22c  sub     rsp, 50h
0x18000b230  mov     rax, cs:__security_cookie
0x18000b237  xor     rax, rsp
0x18000b23a  mov     [rsp+68h+var_20], rax
0x18000b23f  xor     esi, esi
0x18000b241  mov     [rsp+68h+var_38], 0
0x18000b24a  test    r8d, r8d
0x18000b24d  mov     rdi, r9
0x18000b250  mov     ebp, edx
0x18000b252  mov     rbx, rcx
0x18000b255  setz    sil
0x18000b259  xor     eax, eax
0x18000b25b  mov     [rsp+68h+var_30], rax
0x18000b260  mov     [rsp+68h+var_28], eax
0x18000b264  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b26b  test    rax, rax
0x18000b26e  jnz     short loc_18000B2C4
0x18000b270  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b277  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b27c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b283  test    rax, rax
0x18000b286  jnz     short loc_18000B2C4
0x18000b288  mov     r8d, 0C0000139h
0x18000b28e  xor     r9d, r9d
0x18000b291  test    rdi, rdi
0x18000b294  jz      short loc_18000B2A4
0x18000b296  xor     ecx, ecx
0x18000b298  cmp     r8d, 80000022h
0x18000b29f  setnz   cl
0x18000b2a2  mov     [rdi], ecx
0x18000b2a4  mov     eax, r9d
0x18000b2a7  mov     rcx, [rsp+68h+var_20]
0x18000b2ac  xor     rcx, rsp; StackCookie
0x18000b2af  call    __security_check_cookie
0x18000b2b4  mov     rbx, [rsp+68h+arg_10]
0x18000b2bc  add     rsp, 50h
0x18000b2c0  pop     rdi
0x18000b2c1  pop     rsi
0x18000b2c2  pop     rbp
0x18000b2c3  retn
0x18000b2c4  lea     r9, [rsp+68h+var_30]
0x18000b2c9  mov     edx, esi
0x18000b2cb  lea     r8, [rsp+68h+var_38]
0x18000b2d0  mov     ecx, ebp
0x18000b2d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2d7  mov     r8d, eax
0x18000b2da  test    eax, eax
0x18000b2dc  jnz     short loc_18000B326
0x18000b2de  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b2e2  lea     r9d, [r8+1]
0x18000b2e6  mov     eax, [rsp+68h+var_28]
0x18000b2ea  mov     ecx, edx
0x18000b2ec  mov     [rbx+0Ch], eax
0x18000b2ef  mov     eax, edx
0x18000b2f1  shr     eax, 0Eh
0x18000b2f4  shr     ecx, 4
0x18000b2f7  and     eax, 3
0x18000b2fa  and     ecx, 3
0x18000b2fd  mov     [rbx+8], eax
0x18000b300  mov     [rbx], ecx
0x18000b302  mov     eax, edx
0x18000b304  mov     ecx, edx
0x18000b306  shr     eax, 6
0x18000b309  shr     ecx, 8
0x18000b30c  and     eax, r9d
0x18000b30f  and     cl, 3Fh
0x18000b312  shr     edx, 7
0x18000b315  and     edx, r9d
0x18000b318  mov     [rbx+4], cl
0x18000b31b  mov     [rbx+10h], edx
0x18000b31e  mov     [rbx+14h], eax
0x18000b321  jmp     loc_18000B291
0x18000b326  cmp     eax, 117h
0x18000b32b  jnz     loc_18000B28E
0x18000b331  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000b335  mov     r9d, 1
0x18000b33b  shr     eax, 7
0x18000b33e  and     eax, r9d
0x18000b341  mov     [rbx+10h], eax
0x18000b344  jmp     loc_18000B291
```
