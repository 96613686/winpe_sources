# wil_details_NtUpdateWnfStateData

- ea: `0x18004f974`
- end: `0x18004f9fa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18004c8a8`
- `0x18004f0f8`

## callees

- `0x180046ad0`
- `0x18004f974`
- `0x1800a8010`

## string_xrefs

- `0x18004f998`: `NtUpdateWnfStateData`

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
0x18004f974  mov     [rsp+arg_0], rbx
0x18004f979  mov     [rsp+arg_8], rsi
0x18004f97e  push    rdi
0x18004f97f  sub     rsp, 40h
0x18004f983  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18004f98a  mov     ebx, r8d
0x18004f98d  mov     rdi, rdx
0x18004f990  mov     rsi, rcx
0x18004f993  test    r10, r10
0x18004f996  jnz     short loc_18004F9BA
0x18004f998  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18004f99f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18004f9a4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18004f9ab  mov     r10, rax
0x18004f9ae  test    rax, rax
0x18004f9b1  jnz     short loc_18004F9BA
0x18004f9b3  mov     eax, 0C0000139h
0x18004f9b8  jmp     short loc_18004F9EA
0x18004f9ba  mov     eax, [rsp+48h+arg_30]
0x18004f9c1  xor     r9d, r9d
0x18004f9c4  mov     [rsp+48h+var_18], eax
0x18004f9c8  mov     r8d, ebx
0x18004f9cb  mov     eax, [rsp+48h+arg_28]
0x18004f9cf  mov     rdx, rdi
0x18004f9d2  mov     [rsp+48h+var_20], eax
0x18004f9d6  mov     rcx, rsi
0x18004f9d9  mov     rax, r10
0x18004f9dc  mov     [rsp+48h+var_28], 0
0x18004f9e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004f9ea  mov     rbx, [rsp+48h+arg_0]
0x18004f9ef  mov     rsi, [rsp+48h+arg_8]
0x18004f9f4  add     rsp, 40h
0x18004f9f8  pop     rdi
0x18004f9f9  retn
```
