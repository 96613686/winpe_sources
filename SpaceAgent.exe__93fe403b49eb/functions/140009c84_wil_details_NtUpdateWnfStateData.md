# wil_details_NtUpdateWnfStateData

- ea: `0x140009c84`
- end: `0x140009d0a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400076d4`
- `0x140009754`

## callees

- `0x14000972c`
- `0x140009c84`
- `0x140020010`

## string_xrefs

- `0x140009ca8`: `NtUpdateWnfStateData`

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
0x140009c84  mov     [rsp+arg_0], rbx
0x140009c89  mov     [rsp+arg_8], rsi
0x140009c8e  push    rdi
0x140009c8f  sub     rsp, 40h
0x140009c93  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140009c9a  mov     ebx, r8d
0x140009c9d  mov     rdi, rdx
0x140009ca0  mov     rsi, rcx
0x140009ca3  test    r10, r10
0x140009ca6  jnz     short loc_140009CCA
0x140009ca8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140009caf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140009cb4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140009cbb  mov     r10, rax
0x140009cbe  test    rax, rax
0x140009cc1  jnz     short loc_140009CCA
0x140009cc3  mov     eax, 0C0000139h
0x140009cc8  jmp     short loc_140009CFA
0x140009cca  mov     eax, [rsp+48h+arg_30]
0x140009cd1  xor     r9d, r9d
0x140009cd4  mov     [rsp+48h+var_18], eax
0x140009cd8  mov     r8d, ebx
0x140009cdb  mov     eax, [rsp+48h+arg_28]
0x140009cdf  mov     rdx, rdi
0x140009ce2  mov     [rsp+48h+var_20], eax
0x140009ce6  mov     rcx, rsi
0x140009ce9  mov     rax, r10
0x140009cec  mov     [rsp+48h+var_28], 0
0x140009cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009cfa  mov     rbx, [rsp+48h+arg_0]
0x140009cff  mov     rsi, [rsp+48h+arg_8]
0x140009d04  add     rsp, 40h
0x140009d08  pop     rdi
0x140009d09  retn
```
