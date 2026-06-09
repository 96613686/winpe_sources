# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x18000ab10`
- end: `0x18000ac02`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: `__int64 __fastcall(__int64, unsigned int, int)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000b350`

## callees

- `0x1800014b0`
- `0x18000ab10`
- `0x18000b464`
- `0x180018010`

## string_xrefs

- `0x18000ab5b`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  BOOL v5; // edi
  FARPROC NtDllProcedureAddress; // rax
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  int v12; // [rsp+38h] [rbp-20h]
  __int64 v13; // [rsp+40h] [rbp-18h] BYREF

  v13 = 0;
  v5 = a3 == 0;
  v11 = 0;
  v12 = 0;
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlQueryFeatureConfiguration"),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress) != 0) )
  {
    v8 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))NtDllProcedureAddress)(a2, v5, &v13, &v11);
    if ( v8 )
    {
      v7 = 0;
      if ( v8 != 279 )
        return v7;
      v9 = HIDWORD(v11);
      v7 = 1;
    }
    else
    {
      v9 = HIDWORD(v11);
      v7 = 1;
      *(_DWORD *)a1 = (HIDWORD(v11) >> 4) & 3;
      *(_BYTE *)(a1 + 4) = BYTE1(v9) & 0x3F;
      *(_DWORD *)(a1 + 12) = v12;
      *(_DWORD *)(a1 + 8) = (unsigned __int16)v9 >> 14;
      *(_DWORD *)(a1 + 20) = (v9 >> 6) & 1;
    }
    *(_DWORD *)(a1 + 16) = (v9 >> 7) & 1;
    return v7;
  }
  return 0;
}

```

## disassembly

```asm
0x18000ab10  mov     r11, rsp
0x18000ab13  mov     [r11+18h], rbx
0x18000ab17  mov     [r11+20h], rsi
0x18000ab1b  push    rdi
0x18000ab1c  sub     rsp, 50h
0x18000ab20  mov     rax, cs:__security_cookie
0x18000ab27  xor     rax, rsp
0x18000ab2a  mov     [rsp+58h+var_10], rax
0x18000ab2f  xor     edi, edi
0x18000ab31  mov     qword ptr [r11-18h], 0
0x18000ab39  test    r8d, r8d
0x18000ab3c  mov     esi, edx
0x18000ab3e  mov     rbx, rcx
0x18000ab41  setz    dil
0x18000ab45  xor     eax, eax
0x18000ab47  mov     [r11-28h], rax
0x18000ab4b  mov     [rsp+58h+var_20], eax
0x18000ab4f  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ab56  test    rax, rax
0x18000ab59  jnz     short loc_18000AB77
0x18000ab5b  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ab62  call    wil_details_GetNtDllProcedureAddress
0x18000ab67  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ab6e  test    rax, rax
0x18000ab71  jnz     short loc_18000AB77
0x18000ab73  xor     edx, edx
0x18000ab75  jmp     short loc_18000ABE3
0x18000ab77  lea     r9, [rsp+58h+var_28]
0x18000ab7c  mov     edx, edi
0x18000ab7e  lea     r8, [rsp+58h+var_18]
0x18000ab83  mov     ecx, esi
0x18000ab85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ab8a  test    eax, eax
0x18000ab8c  jnz     short loc_18000ABC9
0x18000ab8e  mov     ecx, [rsp+58h+var_24]
0x18000ab92  mov     edx, 1
0x18000ab97  mov     eax, ecx
0x18000ab99  shr     eax, 4
0x18000ab9c  and     eax, 3
0x18000ab9f  mov     [rbx], eax
0x18000aba1  mov     eax, ecx
0x18000aba3  shr     eax, 8
0x18000aba6  and     al, 3Fh
0x18000aba8  mov     [rbx+4], al
0x18000abab  mov     eax, [rsp+58h+var_20]
0x18000abaf  mov     [rbx+0Ch], eax
0x18000abb2  mov     eax, ecx
0x18000abb4  shr     eax, 0Eh
0x18000abb7  and     eax, 3
0x18000abba  mov     [rbx+8], eax
0x18000abbd  mov     eax, ecx
0x18000abbf  shr     eax, 6
0x18000abc2  and     eax, edx
0x18000abc4  mov     [rbx+14h], eax
0x18000abc7  jmp     short loc_18000ABDB
0x18000abc9  xor     edx, edx
0x18000abcb  cmp     eax, 117h
0x18000abd0  jnz     short loc_18000ABE3
0x18000abd2  mov     ecx, [rsp+58h+var_24]
0x18000abd6  mov     edx, 1
0x18000abdb  shr     ecx, 7
0x18000abde  and     ecx, edx
0x18000abe0  mov     [rbx+10h], ecx
0x18000abe3  mov     eax, edx
0x18000abe5  mov     rcx, [rsp+58h+var_10]
0x18000abea  xor     rcx, rsp; StackCookie
0x18000abed  call    __security_check_cookie
0x18000abf2  mov     rbx, [rsp+58h+arg_10]
0x18000abf7  mov     rsi, [rsp+58h+arg_18]
0x18000abfc  add     rsp, 50h
0x18000ac00  pop     rdi
0x18000ac01  retn
```
