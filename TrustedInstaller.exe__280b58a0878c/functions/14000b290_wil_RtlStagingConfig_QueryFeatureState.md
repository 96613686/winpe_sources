# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x14000b290`
- end: `0x14000b3b5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b268`

## callees

- `0x1400023e0`
- `0x140005fd0`
- `0x14000b290`
- `0x14002b010`

## string_xrefs

- `0x14000b2dc`: `RtlQueryFeatureConfiguration`

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
  int v16; // [rsp+38h] [rbp-30h]
  __int64 v17; // [rsp+40h] [rbp-28h] BYREF

  v17 = 0;
  v7 = a3 == 0;
  v15 = 0;
  v16 = 0;
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
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v7, &v17, &v15);
  v9 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_4;
    v10 = 1;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v15) >> 7) & 1;
  }
  else
  {
    v13 = HIDWORD(v15);
    v10 = 1;
    v14 = HIDWORD(v15);
    *(_DWORD *)(a1 + 12) = v16;
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
0x14000b290  mov     [rsp+arg_10], rbx
0x14000b295  push    rbp
0x14000b296  push    rsi
0x14000b297  push    rdi
0x14000b298  sub     rsp, 50h
0x14000b29c  mov     rax, cs:__security_cookie
0x14000b2a3  xor     rax, rsp
0x14000b2a6  mov     [rsp+68h+var_20], rax
0x14000b2ab  xor     esi, esi
0x14000b2ad  mov     [rsp+68h+var_28], 0
0x14000b2b6  test    r8d, r8d
0x14000b2b9  mov     rdi, r9
0x14000b2bc  mov     ebp, edx
0x14000b2be  mov     rbx, rcx
0x14000b2c1  setz    sil
0x14000b2c5  xor     eax, eax
0x14000b2c7  mov     [rsp+68h+var_38], rax
0x14000b2cc  mov     [rsp+68h+var_30], eax
0x14000b2d0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000b2d7  test    rax, rax
0x14000b2da  jnz     short loc_14000B330
0x14000b2dc  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000b2e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000b2e8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000b2ef  test    rax, rax
0x14000b2f2  jnz     short loc_14000B330
0x14000b2f4  mov     r8d, 0C0000139h
0x14000b2fa  xor     r9d, r9d
0x14000b2fd  test    rdi, rdi
0x14000b300  jz      short loc_14000B310
0x14000b302  xor     ecx, ecx
0x14000b304  cmp     r8d, 80000022h
0x14000b30b  setnz   cl
0x14000b30e  mov     [rdi], ecx
0x14000b310  mov     eax, r9d
0x14000b313  mov     rcx, [rsp+68h+var_20]
0x14000b318  xor     rcx, rsp; StackCookie
0x14000b31b  call    __security_check_cookie
0x14000b320  mov     rbx, [rsp+68h+arg_10]
0x14000b328  add     rsp, 50h
0x14000b32c  pop     rdi
0x14000b32d  pop     rsi
0x14000b32e  pop     rbp
0x14000b32f  retn
0x14000b330  lea     r9, [rsp+68h+var_38]
0x14000b335  mov     edx, esi
0x14000b337  lea     r8, [rsp+68h+var_28]
0x14000b33c  mov     ecx, ebp
0x14000b33e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b343  mov     r8d, eax
0x14000b346  test    eax, eax
0x14000b348  jnz     short loc_14000B392
0x14000b34a  mov     edx, dword ptr [rsp+68h+var_38+4]
0x14000b34e  lea     r9d, [r8+1]
0x14000b352  mov     eax, [rsp+68h+var_30]
0x14000b356  mov     ecx, edx
0x14000b358  mov     [rbx+0Ch], eax
0x14000b35b  mov     eax, edx
0x14000b35d  shr     eax, 0Eh
0x14000b360  shr     ecx, 4
0x14000b363  and     eax, 3
0x14000b366  and     ecx, 3
0x14000b369  mov     [rbx+8], eax
0x14000b36c  mov     [rbx], ecx
0x14000b36e  mov     eax, edx
0x14000b370  mov     ecx, edx
0x14000b372  shr     eax, 6
0x14000b375  shr     ecx, 8
0x14000b378  and     eax, r9d
0x14000b37b  and     cl, 3Fh
0x14000b37e  shr     edx, 7
0x14000b381  and     edx, r9d
0x14000b384  mov     [rbx+4], cl
0x14000b387  mov     [rbx+10h], edx
0x14000b38a  mov     [rbx+14h], eax
0x14000b38d  jmp     loc_14000B2FD
0x14000b392  cmp     eax, 117h
0x14000b397  jnz     loc_14000B2FA
0x14000b39d  mov     eax, dword ptr [rsp+68h+var_38+4]
0x14000b3a1  mov     r9d, 1
0x14000b3a7  shr     eax, 7
0x14000b3aa  and     eax, r9d
0x14000b3ad  mov     [rbx+10h], eax
0x14000b3b0  jmp     loc_14000B2FD
```
