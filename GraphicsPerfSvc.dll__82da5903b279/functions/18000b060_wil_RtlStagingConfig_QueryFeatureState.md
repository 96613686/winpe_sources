# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000b060`
- end: `0x18000b185`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b038`

## callees

- `0x180003ab0`
- `0x18000adb0`
- `0x18000b060`
- `0x180031010`

## string_xrefs

- `0x18000b0ac`: `RtlQueryFeatureConfiguration`

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
0x18000b060  mov     [rsp+arg_10], rbx
0x18000b065  push    rbp
0x18000b066  push    rsi
0x18000b067  push    rdi
0x18000b068  sub     rsp, 50h
0x18000b06c  mov     rax, cs:__security_cookie
0x18000b073  xor     rax, rsp
0x18000b076  mov     [rsp+68h+var_20], rax
0x18000b07b  xor     esi, esi
0x18000b07d  mov     [rsp+68h+var_38], 0
0x18000b086  test    r8d, r8d
0x18000b089  mov     rdi, r9
0x18000b08c  mov     ebp, edx
0x18000b08e  mov     rbx, rcx
0x18000b091  setz    sil
0x18000b095  xor     eax, eax
0x18000b097  mov     [rsp+68h+var_30], rax
0x18000b09c  mov     [rsp+68h+var_28], eax
0x18000b0a0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b0a7  test    rax, rax
0x18000b0aa  jnz     short loc_18000B100
0x18000b0ac  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b0b3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b0b8  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b0bf  test    rax, rax
0x18000b0c2  jnz     short loc_18000B100
0x18000b0c4  mov     r8d, 0C0000139h
0x18000b0ca  xor     r9d, r9d
0x18000b0cd  test    rdi, rdi
0x18000b0d0  jz      short loc_18000B0E0
0x18000b0d2  xor     ecx, ecx
0x18000b0d4  cmp     r8d, 80000022h
0x18000b0db  setnz   cl
0x18000b0de  mov     [rdi], ecx
0x18000b0e0  mov     eax, r9d
0x18000b0e3  mov     rcx, [rsp+68h+var_20]
0x18000b0e8  xor     rcx, rsp; StackCookie
0x18000b0eb  call    __security_check_cookie
0x18000b0f0  mov     rbx, [rsp+68h+arg_10]
0x18000b0f8  add     rsp, 50h
0x18000b0fc  pop     rdi
0x18000b0fd  pop     rsi
0x18000b0fe  pop     rbp
0x18000b0ff  retn
0x18000b100  lea     r9, [rsp+68h+var_30]
0x18000b105  mov     edx, esi
0x18000b107  lea     r8, [rsp+68h+var_38]
0x18000b10c  mov     ecx, ebp
0x18000b10e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b113  mov     r8d, eax
0x18000b116  test    eax, eax
0x18000b118  jnz     short loc_18000B162
0x18000b11a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b11e  lea     r9d, [r8+1]
0x18000b122  mov     eax, [rsp+68h+var_28]
0x18000b126  mov     ecx, edx
0x18000b128  mov     [rbx+0Ch], eax
0x18000b12b  mov     eax, edx
0x18000b12d  shr     eax, 0Eh
0x18000b130  shr     ecx, 4
0x18000b133  and     eax, 3
0x18000b136  and     ecx, 3
0x18000b139  mov     [rbx+8], eax
0x18000b13c  mov     [rbx], ecx
0x18000b13e  mov     eax, edx
0x18000b140  mov     ecx, edx
0x18000b142  shr     eax, 6
0x18000b145  shr     ecx, 8
0x18000b148  and     eax, r9d
0x18000b14b  and     cl, 3Fh
0x18000b14e  shr     edx, 7
0x18000b151  and     edx, r9d
0x18000b154  mov     [rbx+4], cl
0x18000b157  mov     [rbx+10h], edx
0x18000b15a  mov     [rbx+14h], eax
0x18000b15d  jmp     loc_18000B0CD
0x18000b162  cmp     eax, 117h
0x18000b167  jnz     loc_18000B0CA
0x18000b16d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000b171  mov     r9d, 1
0x18000b177  shr     eax, 7
0x18000b17a  and     eax, r9d
0x18000b17d  mov     [rbx+10h], eax
0x18000b180  jmp     loc_18000B0CD
```
