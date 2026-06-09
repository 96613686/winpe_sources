# wil_details_NtUpdateWnfStateData

- ea: `0x1800ae6a4`
- end: `0x1800ae72a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800abed4`
- `0x1800ae328`

## callees

- `0x1800ae300`
- `0x1800ae6a4`
- `0x1800b0010`

## string_xrefs

- `0x1800ae6c8`: `NtUpdateWnfStateData`

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
0x1800ae6a4  mov     [rsp+arg_0], rbx
0x1800ae6a9  mov     [rsp+arg_8], rsi
0x1800ae6ae  push    rdi
0x1800ae6af  sub     rsp, 40h
0x1800ae6b3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800ae6ba  mov     ebx, r8d
0x1800ae6bd  mov     rdi, rdx
0x1800ae6c0  mov     rsi, rcx
0x1800ae6c3  test    r10, r10
0x1800ae6c6  jnz     short loc_1800AE6EA
0x1800ae6c8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800ae6cf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800ae6d4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800ae6db  mov     r10, rax
0x1800ae6de  test    rax, rax
0x1800ae6e1  jnz     short loc_1800AE6EA
0x1800ae6e3  mov     eax, 0C0000139h
0x1800ae6e8  jmp     short loc_1800AE71A
0x1800ae6ea  mov     eax, [rsp+48h+arg_30]
0x1800ae6f1  xor     r9d, r9d
0x1800ae6f4  mov     [rsp+48h+var_18], eax
0x1800ae6f8  mov     r8d, ebx
0x1800ae6fb  mov     eax, [rsp+48h+arg_28]
0x1800ae6ff  mov     rdx, rdi
0x1800ae702  mov     [rsp+48h+var_20], eax
0x1800ae706  mov     rcx, rsi
0x1800ae709  mov     rax, r10
0x1800ae70c  mov     [rsp+48h+var_28], 0
0x1800ae715  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ae71a  mov     rbx, [rsp+48h+arg_0]
0x1800ae71f  mov     rsi, [rsp+48h+arg_8]
0x1800ae724  add     rsp, 40h
0x1800ae728  pop     rdi
0x1800ae729  retn
```
