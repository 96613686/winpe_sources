# wil_details_NtUpdateWnfStateData

- ea: `0x1800210a4`
- end: `0x18002112a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001804c`
- `0x18001edf4`

## callees

- `0x1800092d0`
- `0x1800210a4`
- `0x180025010`

## string_xrefs

- `0x1800210c8`: `NtUpdateWnfStateData`

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
0x1800210a4  mov     [rsp+arg_0], rbx
0x1800210a9  mov     [rsp+arg_8], rsi
0x1800210ae  push    rdi
0x1800210af  sub     rsp, 40h
0x1800210b3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800210ba  mov     ebx, r8d
0x1800210bd  mov     rdi, rdx
0x1800210c0  mov     rsi, rcx
0x1800210c3  test    r10, r10
0x1800210c6  jnz     short loc_1800210EA
0x1800210c8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800210cf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800210d4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800210db  mov     r10, rax
0x1800210de  test    rax, rax
0x1800210e1  jnz     short loc_1800210EA
0x1800210e3  mov     eax, 0C0000139h
0x1800210e8  jmp     short loc_18002111A
0x1800210ea  mov     eax, [rsp+48h+arg_30]
0x1800210f1  xor     r9d, r9d
0x1800210f4  mov     [rsp+48h+var_18], eax
0x1800210f8  mov     r8d, ebx
0x1800210fb  mov     eax, [rsp+48h+arg_28]
0x1800210ff  mov     rdx, rdi
0x180021102  mov     [rsp+48h+var_20], eax
0x180021106  mov     rcx, rsi
0x180021109  mov     rax, r10
0x18002110c  mov     [rsp+48h+var_28], 0
0x180021115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002111a  mov     rbx, [rsp+48h+arg_0]
0x18002111f  mov     rsi, [rsp+48h+arg_8]
0x180021124  add     rsp, 40h
0x180021128  pop     rdi
0x180021129  retn
```
