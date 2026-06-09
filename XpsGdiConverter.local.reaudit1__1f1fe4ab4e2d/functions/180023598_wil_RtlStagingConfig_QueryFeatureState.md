# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180023598`
- end: `0x1800236bd`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18001eed4`

## callees

- `0x180008830`
- `0x18000d180`
- `0x180023598`
- `0x18004a010`

## string_xrefs

- `0x1800235e4`: `RtlQueryFeatureConfiguration`

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
0x180023598  mov     [rsp+arg_10], rbx
0x18002359d  push    rbp
0x18002359e  push    rsi
0x18002359f  push    rdi
0x1800235a0  sub     rsp, 50h
0x1800235a4  mov     rax, cs:__security_cookie
0x1800235ab  xor     rax, rsp
0x1800235ae  mov     [rsp+68h+var_20], rax
0x1800235b3  xor     esi, esi
0x1800235b5  mov     [rsp+68h+var_38], 0
0x1800235be  test    r8d, r8d
0x1800235c1  mov     rdi, r9
0x1800235c4  mov     ebp, edx
0x1800235c6  mov     rbx, rcx
0x1800235c9  setz    sil
0x1800235cd  xor     eax, eax
0x1800235cf  mov     [rsp+68h+var_30], rax
0x1800235d4  mov     [rsp+68h+var_28], eax
0x1800235d8  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800235df  test    rax, rax
0x1800235e2  jnz     short loc_180023638
0x1800235e4  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800235eb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800235f0  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800235f7  test    rax, rax
0x1800235fa  jnz     short loc_180023638
0x1800235fc  mov     r8d, 0C0000139h
0x180023602  xor     r9d, r9d
0x180023605  test    rdi, rdi
0x180023608  jz      short loc_180023618
0x18002360a  xor     ecx, ecx
0x18002360c  cmp     r8d, 80000022h
0x180023613  setnz   cl
0x180023616  mov     [rdi], ecx
0x180023618  mov     eax, r9d
0x18002361b  mov     rcx, [rsp+68h+var_20]
0x180023620  xor     rcx, rsp; StackCookie
0x180023623  call    __security_check_cookie
0x180023628  mov     rbx, [rsp+68h+arg_10]
0x180023630  add     rsp, 50h
0x180023634  pop     rdi
0x180023635  pop     rsi
0x180023636  pop     rbp
0x180023637  retn
0x180023638  lea     r9, [rsp+68h+var_30]
0x18002363d  mov     edx, esi
0x18002363f  lea     r8, [rsp+68h+var_38]
0x180023644  mov     ecx, ebp
0x180023646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002364b  mov     r8d, eax
0x18002364e  test    eax, eax
0x180023650  jnz     short loc_18002369A
0x180023652  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180023656  lea     r9d, [r8+1]
0x18002365a  mov     eax, [rsp+68h+var_28]
0x18002365e  mov     ecx, edx
0x180023660  mov     [rbx+0Ch], eax
0x180023663  mov     eax, edx
0x180023665  shr     eax, 0Eh
0x180023668  shr     ecx, 4
0x18002366b  and     eax, 3
0x18002366e  and     ecx, 3
0x180023671  mov     [rbx+8], eax
0x180023674  mov     [rbx], ecx
0x180023676  mov     eax, edx
0x180023678  mov     ecx, edx
0x18002367a  shr     eax, 6
0x18002367d  shr     ecx, 8
0x180023680  and     eax, r9d
0x180023683  and     cl, 3Fh
0x180023686  shr     edx, 7
0x180023689  and     edx, r9d
0x18002368c  mov     [rbx+4], cl
0x18002368f  mov     [rbx+10h], edx
0x180023692  mov     [rbx+14h], eax
0x180023695  jmp     loc_180023605
0x18002369a  cmp     eax, 117h
0x18002369f  jnz     loc_180023602
0x1800236a5  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800236a9  mov     r9d, 1
0x1800236af  shr     eax, 7
0x1800236b2  and     eax, r9d
0x1800236b5  mov     [rbx+10h], eax
0x1800236b8  jmp     loc_180023605
```
