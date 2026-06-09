# wil_details_NtUpdateWnfStateData

- ea: `0x18000f134`
- end: `0x18000f1ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bb98`
- `0x18000eb48`

## callees

- `0x18000eb20`
- `0x18000f134`
- `0x18002b010`

## string_xrefs

- `0x18000f158`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_NtUpdateWnfStateData(
        __int64 a1,
        __int64 a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        int a6,
        int a7)
{
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int); // r10

  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  g_wil_details_pfnNtUpdateWnfStateData = (__int64)wil_details_GetNtDllProcedureAddress("NtUpdateWnfStateData");
  v7 = (__int64 (__fastcall *)(__int64, __int64, _QWORD, _QWORD, _QWORD, int, int))g_wil_details_pfnNtUpdateWnfStateData;
  if ( g_wil_details_pfnNtUpdateWnfStateData )
    return v7(a1, a2, a3, 0, 0, a6, a7);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x18000f134  mov     [rsp+arg_0], rbx
0x18000f139  mov     [rsp+arg_8], rsi
0x18000f13e  push    rdi
0x18000f13f  sub     rsp, 40h
0x18000f143  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000f14a  mov     ebx, r8d
0x18000f14d  mov     rdi, rdx
0x18000f150  mov     rsi, rcx
0x18000f153  test    r10, r10
0x18000f156  jnz     short loc_18000F17A
0x18000f158  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000f15f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f164  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000f16b  mov     r10, rax
0x18000f16e  test    rax, rax
0x18000f171  jnz     short loc_18000F17A
0x18000f173  mov     eax, 0C0000139h
0x18000f178  jmp     short loc_18000F1AA
0x18000f17a  mov     eax, [rsp+48h+arg_30]
0x18000f181  xor     r9d, r9d
0x18000f184  mov     [rsp+48h+var_18], eax
0x18000f188  mov     r8d, ebx
0x18000f18b  mov     eax, [rsp+48h+arg_28]
0x18000f18f  mov     rdx, rdi
0x18000f192  mov     [rsp+48h+var_20], eax
0x18000f196  mov     rcx, rsi
0x18000f199  mov     rax, r10
0x18000f19c  mov     [rsp+48h+var_28], 0
0x18000f1a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f1aa  mov     rbx, [rsp+48h+arg_0]
0x18000f1af  mov     rsi, [rsp+48h+arg_8]
0x18000f1b4  add     rsp, 40h
0x18000f1b8  pop     rdi
0x18000f1b9  retn
```
