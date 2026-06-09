# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x1800076e0`
- end: `0x1800077d2`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `242`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x180007f0c`

## callees

- `0x1800076e0`
- `0x180008020`
- `0x18000a5f0`
- `0x18000d010`

## string_xrefs

- `0x18000772b`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3)
{
  BOOL v5; // edi
  __int64 (__fastcall *NtDllProcedureAddress)(_QWORD, BOOL, __int64 *, __int64 *); // rax
  unsigned int v7; // edx
  int v8; // eax
  unsigned int v9; // ecx
  __int64 v11; // [rsp+30h] [rbp-28h] BYREF
  __int64 v12; // [rsp+38h] [rbp-20h] BYREF
  int v13; // [rsp+40h] [rbp-18h]

  v11 = 0;
  v5 = a3 == 0;
  v12 = 0;
  v13 = 0;
  NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( g_wil_details_pfnRtlQueryFeatureConfiguration
    || (NtDllProcedureAddress = (__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))wil_details_GetNtDllProcedureAddress(
                                                                                              "RtlQueryFeatureConfiguration"),
        (g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)NtDllProcedureAddress) != 0) )
  {
    v8 = NtDllProcedureAddress(a2, v5, &v11, &v12);
    if ( v8 )
    {
      v7 = 0;
      if ( v8 != 279 )
        return v7;
      v9 = HIDWORD(v12);
      v7 = 1;
    }
    else
    {
      v9 = HIDWORD(v12);
      v7 = 1;
      *(_DWORD *)a1 = (HIDWORD(v12) >> 4) & 3;
      *(_BYTE *)(a1 + 4) = BYTE1(v9) & 0x3F;
      *(_DWORD *)(a1 + 12) = v13;
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
0x1800076e0  mov     r11, rsp
0x1800076e3  mov     [r11+18h], rbx
0x1800076e7  mov     [r11+20h], rsi
0x1800076eb  push    rdi
0x1800076ec  sub     rsp, 50h
0x1800076f0  mov     rax, cs:__security_cookie
0x1800076f7  xor     rax, rsp
0x1800076fa  mov     [rsp+58h+var_10], rax
0x1800076ff  xor     edi, edi
0x180007701  mov     qword ptr [r11-28h], 0
0x180007709  test    r8d, r8d
0x18000770c  mov     esi, edx
0x18000770e  mov     rbx, rcx
0x180007711  setz    dil
0x180007715  xor     eax, eax
0x180007717  mov     [r11-20h], rax
0x18000771b  mov     [rsp+58h+var_18], eax
0x18000771f  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180007726  test    rax, rax
0x180007729  jnz     short loc_180007747
0x18000772b  lea     rcx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180007732  call    wil_details_GetNtDllProcedureAddress
0x180007737  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000773e  test    rax, rax
0x180007741  jnz     short loc_180007747
0x180007743  xor     edx, edx
0x180007745  jmp     short loc_1800077B3
0x180007747  lea     r9, [rsp+58h+var_20]
0x18000774c  mov     edx, edi
0x18000774e  lea     r8, [rsp+58h+var_28]
0x180007753  mov     ecx, esi
0x180007755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000775a  test    eax, eax
0x18000775c  jnz     short loc_180007799
0x18000775e  mov     ecx, [rsp+58h+var_1C]
0x180007762  mov     edx, 1
0x180007767  mov     eax, ecx
0x180007769  shr     eax, 4
0x18000776c  and     eax, 3
0x18000776f  mov     [rbx], eax
0x180007771  mov     eax, ecx
0x180007773  shr     eax, 8
0x180007776  and     al, 3Fh
0x180007778  mov     [rbx+4], al
0x18000777b  mov     eax, [rsp+58h+var_18]
0x18000777f  mov     [rbx+0Ch], eax
0x180007782  mov     eax, ecx
0x180007784  shr     eax, 0Eh
0x180007787  and     eax, 3
0x18000778a  mov     [rbx+8], eax
0x18000778d  mov     eax, ecx
0x18000778f  shr     eax, 6
0x180007792  and     eax, edx
0x180007794  mov     [rbx+14h], eax
0x180007797  jmp     short loc_1800077AB
0x180007799  xor     edx, edx
0x18000779b  cmp     eax, 117h
0x1800077a0  jnz     short loc_1800077B3
0x1800077a2  mov     ecx, [rsp+58h+var_1C]
0x1800077a6  mov     edx, 1
0x1800077ab  shr     ecx, 7
0x1800077ae  and     ecx, edx
0x1800077b0  mov     [rbx+10h], ecx
0x1800077b3  mov     eax, edx
0x1800077b5  mov     rcx, [rsp+58h+var_10]
0x1800077ba  xor     rcx, rsp; StackCookie
0x1800077bd  call    __security_check_cookie
0x1800077c2  mov     rbx, [rsp+58h+arg_10]
0x1800077c7  mov     rsi, [rsp+58h+arg_18]
0x1800077cc  add     rsp, 50h
0x1800077d0  pop     rdi
0x1800077d1  retn
```
