# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000a514`
- end: `0x18000a639`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x1800066fc`

## callees

- `0x180002300`
- `0x18000a280`
- `0x18000a514`
- `0x18003f010`

## string_xrefs

- `0x18000a560`: `RtlQueryFeatureConfiguration`

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
0x18000a514  mov     [rsp+arg_10], rbx
0x18000a519  push    rbp
0x18000a51a  push    rsi
0x18000a51b  push    rdi
0x18000a51c  sub     rsp, 50h
0x18000a520  mov     rax, cs:__security_cookie
0x18000a527  xor     rax, rsp
0x18000a52a  mov     [rsp+68h+var_20], rax
0x18000a52f  xor     esi, esi
0x18000a531  mov     [rsp+68h+var_38], 0
0x18000a53a  test    r8d, r8d
0x18000a53d  mov     rdi, r9
0x18000a540  mov     ebp, edx
0x18000a542  mov     rbx, rcx
0x18000a545  setz    sil
0x18000a549  xor     eax, eax
0x18000a54b  mov     [rsp+68h+var_30], rax
0x18000a550  mov     [rsp+68h+var_28], eax
0x18000a554  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000a55b  test    rax, rax
0x18000a55e  jnz     short loc_18000A5B4
0x18000a560  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000a567  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a56c  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000a573  test    rax, rax
0x18000a576  jnz     short loc_18000A5B4
0x18000a578  mov     r8d, 0C0000139h
0x18000a57e  xor     r9d, r9d
0x18000a581  test    rdi, rdi
0x18000a584  jz      short loc_18000A594
0x18000a586  xor     ecx, ecx
0x18000a588  cmp     r8d, 80000022h
0x18000a58f  setnz   cl
0x18000a592  mov     [rdi], ecx
0x18000a594  mov     eax, r9d
0x18000a597  mov     rcx, [rsp+68h+var_20]
0x18000a59c  xor     rcx, rsp; StackCookie
0x18000a59f  call    __security_check_cookie
0x18000a5a4  mov     rbx, [rsp+68h+arg_10]
0x18000a5ac  add     rsp, 50h
0x18000a5b0  pop     rdi
0x18000a5b1  pop     rsi
0x18000a5b2  pop     rbp
0x18000a5b3  retn
0x18000a5b4  lea     r9, [rsp+68h+var_30]
0x18000a5b9  mov     edx, esi
0x18000a5bb  lea     r8, [rsp+68h+var_38]
0x18000a5c0  mov     ecx, ebp
0x18000a5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5c7  mov     r8d, eax
0x18000a5ca  test    eax, eax
0x18000a5cc  jnz     short loc_18000A616
0x18000a5ce  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000a5d2  lea     r9d, [r8+1]
0x18000a5d6  mov     eax, [rsp+68h+var_28]
0x18000a5da  mov     ecx, edx
0x18000a5dc  mov     [rbx+0Ch], eax
0x18000a5df  mov     eax, edx
0x18000a5e1  shr     eax, 0Eh
0x18000a5e4  shr     ecx, 4
0x18000a5e7  and     eax, 3
0x18000a5ea  and     ecx, 3
0x18000a5ed  mov     [rbx+8], eax
0x18000a5f0  mov     [rbx], ecx
0x18000a5f2  mov     eax, edx
0x18000a5f4  mov     ecx, edx
0x18000a5f6  shr     eax, 6
0x18000a5f9  shr     ecx, 8
0x18000a5fc  and     eax, r9d
0x18000a5ff  and     cl, 3Fh
0x18000a602  shr     edx, 7
0x18000a605  and     edx, r9d
0x18000a608  mov     [rbx+4], cl
0x18000a60b  mov     [rbx+10h], edx
0x18000a60e  mov     [rbx+14h], eax
0x18000a611  jmp     loc_18000A581
0x18000a616  cmp     eax, 117h
0x18000a61b  jnz     loc_18000A57E
0x18000a621  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000a625  mov     r9d, 1
0x18000a62b  shr     eax, 7
0x18000a62e  and     eax, r9d
0x18000a631  mov     [rbx+10h], eax
0x18000a634  jmp     loc_18000A581
```
