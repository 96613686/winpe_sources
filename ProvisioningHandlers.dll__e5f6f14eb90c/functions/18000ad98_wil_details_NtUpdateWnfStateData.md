# wil_details_NtUpdateWnfStateData

- ea: `0x18000ad98`
- end: `0x18000ae1f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180008008`
- `0x18000a94c`

## callees

- `0x18000a920`
- `0x18000ad98`
- `0x18002c010`

## string_xrefs

- `0x18000adbc`: `NtUpdateWnfStateData`

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
0x18000ad98  mov     [rsp+arg_0], rbx
0x18000ad9d  mov     [rsp+arg_8], rsi
0x18000ada2  push    rdi
0x18000ada3  sub     rsp, 40h
0x18000ada7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000adae  mov     ebx, r8d
0x18000adb1  mov     rdi, rdx
0x18000adb4  mov     rsi, rcx
0x18000adb7  test    r10, r10
0x18000adba  jnz     short loc_18000ADDE
0x18000adbc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000adc3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000adc8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000adcf  mov     r10, rax
0x18000add2  test    rax, rax
0x18000add5  jnz     short loc_18000ADDE
0x18000add7  mov     eax, 0C0000139h
0x18000addc  jmp     short loc_18000AE0E
0x18000adde  mov     eax, [rsp+48h+arg_30]
0x18000ade5  xor     r9d, r9d
0x18000ade8  mov     [rsp+48h+var_18], eax
0x18000adec  mov     r8d, ebx
0x18000adef  mov     eax, [rsp+48h+arg_28]
0x18000adf3  mov     rdx, rdi
0x18000adf6  mov     [rsp+48h+var_20], eax
0x18000adfa  mov     rcx, rsi
0x18000adfd  mov     rax, r10
0x18000ae00  mov     [rsp+48h+var_28], 0
0x18000ae09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae0e  mov     rbx, [rsp+48h+arg_0]
0x18000ae13  mov     rsi, [rsp+48h+arg_8]
0x18000ae18  add     rsp, 40h
0x18000ae1c  pop     rdi
0x18000ae1d  retn
```
