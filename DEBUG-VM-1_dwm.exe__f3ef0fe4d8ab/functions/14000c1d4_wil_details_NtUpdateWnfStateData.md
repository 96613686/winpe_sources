# wil_details_NtUpdateWnfStateData

- ea: `0x14000c1d4`
- end: `0x14000c25a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000a1b0`
- `0x14000bcec`

## callees

- `0x14000bcc4`
- `0x14000c1d4`
- `0x140010010`

## string_xrefs

- `0x14000c1f8`: `NtUpdateWnfStateData`

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
0x14000c1d4  mov     [rsp+arg_0], rbx
0x14000c1d9  mov     [rsp+arg_8], rsi
0x14000c1de  push    rdi
0x14000c1df  sub     rsp, 40h
0x14000c1e3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000c1ea  mov     ebx, r8d
0x14000c1ed  mov     rdi, rdx
0x14000c1f0  mov     rsi, rcx
0x14000c1f3  test    r10, r10
0x14000c1f6  jnz     short loc_14000C21A
0x14000c1f8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000c1ff  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000c204  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000c20b  mov     r10, rax
0x14000c20e  test    rax, rax
0x14000c211  jnz     short loc_14000C21A
0x14000c213  mov     eax, 0C0000139h
0x14000c218  jmp     short loc_14000C24A
0x14000c21a  mov     eax, [rsp+48h+arg_30]
0x14000c221  xor     r9d, r9d
0x14000c224  mov     [rsp+48h+var_18], eax
0x14000c228  mov     r8d, ebx
0x14000c22b  mov     eax, [rsp+48h+arg_28]
0x14000c22f  mov     rdx, rdi
0x14000c232  mov     [rsp+48h+var_20], eax
0x14000c236  mov     rcx, rsi
0x14000c239  mov     rax, r10
0x14000c23c  mov     [rsp+48h+var_28], 0
0x14000c245  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c24a  mov     rbx, [rsp+48h+arg_0]
0x14000c24f  mov     rsi, [rsp+48h+arg_8]
0x14000c254  add     rsp, 40h
0x14000c258  pop     rdi
0x14000c259  retn
```
