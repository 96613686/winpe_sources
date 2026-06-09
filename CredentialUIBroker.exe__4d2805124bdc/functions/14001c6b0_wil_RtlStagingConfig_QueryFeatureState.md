# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14001c6b0`
- end: `0x14001c7d5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14001c688`

## callees

- `0x140003620`
- `0x14001bce4`
- `0x14001c6b0`
- `0x14001f010`

## string_xrefs

- `0x14001c6fc`: `RtlQueryFeatureConfiguration`

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
0x14001c6b0  mov     [rsp+arg_10], rbx
0x14001c6b5  push    rbp
0x14001c6b6  push    rsi
0x14001c6b7  push    rdi
0x14001c6b8  sub     rsp, 50h
0x14001c6bc  mov     rax, cs:__security_cookie
0x14001c6c3  xor     rax, rsp
0x14001c6c6  mov     [rsp+68h+var_20], rax
0x14001c6cb  xor     esi, esi
0x14001c6cd  mov     [rsp+68h+var_38], 0
0x14001c6d6  test    r8d, r8d
0x14001c6d9  mov     rdi, r9
0x14001c6dc  mov     ebp, edx
0x14001c6de  mov     rbx, rcx
0x14001c6e1  setz    sil
0x14001c6e5  xor     eax, eax
0x14001c6e7  mov     [rsp+68h+var_30], rax
0x14001c6ec  mov     [rsp+68h+var_28], eax
0x14001c6f0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14001c6f7  test    rax, rax
0x14001c6fa  jnz     short loc_14001C750
0x14001c6fc  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14001c703  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001c708  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14001c70f  test    rax, rax
0x14001c712  jnz     short loc_14001C750
0x14001c714  mov     r8d, 0C0000139h
0x14001c71a  xor     r9d, r9d
0x14001c71d  test    rdi, rdi
0x14001c720  jz      short loc_14001C730
0x14001c722  xor     ecx, ecx
0x14001c724  cmp     r8d, 80000022h
0x14001c72b  setnz   cl
0x14001c72e  mov     [rdi], ecx
0x14001c730  mov     eax, r9d
0x14001c733  mov     rcx, [rsp+68h+var_20]
0x14001c738  xor     rcx, rsp; StackCookie
0x14001c73b  call    __security_check_cookie
0x14001c740  mov     rbx, [rsp+68h+arg_10]
0x14001c748  add     rsp, 50h
0x14001c74c  pop     rdi
0x14001c74d  pop     rsi
0x14001c74e  pop     rbp
0x14001c74f  retn
0x14001c750  lea     r9, [rsp+68h+var_30]
0x14001c755  mov     edx, esi
0x14001c757  lea     r8, [rsp+68h+var_38]
0x14001c75c  mov     ecx, ebp
0x14001c75e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001c763  mov     r8d, eax
0x14001c766  test    eax, eax
0x14001c768  jnz     short loc_14001C7B2
0x14001c76a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14001c76e  lea     r9d, [r8+1]
0x14001c772  mov     eax, [rsp+68h+var_28]
0x14001c776  mov     ecx, edx
0x14001c778  mov     [rbx+0Ch], eax
0x14001c77b  mov     eax, edx
0x14001c77d  shr     eax, 0Eh
0x14001c780  shr     ecx, 4
0x14001c783  and     eax, 3
0x14001c786  and     ecx, 3
0x14001c789  mov     [rbx+8], eax
0x14001c78c  mov     [rbx], ecx
0x14001c78e  mov     eax, edx
0x14001c790  mov     ecx, edx
0x14001c792  shr     eax, 6
0x14001c795  shr     ecx, 8
0x14001c798  and     eax, r9d
0x14001c79b  and     cl, 3Fh
0x14001c79e  shr     edx, 7
0x14001c7a1  and     edx, r9d
0x14001c7a4  mov     [rbx+4], cl
0x14001c7a7  mov     [rbx+10h], edx
0x14001c7aa  mov     [rbx+14h], eax
0x14001c7ad  jmp     loc_14001C71D
0x14001c7b2  cmp     eax, 117h
0x14001c7b7  jnz     loc_14001C71A
0x14001c7bd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14001c7c1  mov     r9d, 1
0x14001c7c7  shr     eax, 7
0x14001c7ca  and     eax, r9d
0x14001c7cd  mov     [rbx+10h], eax
0x14001c7d0  jmp     loc_14001C71D
```
