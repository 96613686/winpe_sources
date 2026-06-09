# wil_details_NtUpdateWnfStateData

- ea: `0x18002bac4`
- end: `0x18002bb4a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180024b8c`
- `0x18002aec0`

## callees

- `0x180018e1c`
- `0x18002bac4`
- `0x180031010`

## string_xrefs

- `0x18002bae8`: `NtUpdateWnfStateData`

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
0x18002bac4  mov     [rsp+arg_0], rbx
0x18002bac9  mov     [rsp+arg_8], rsi
0x18002bace  push    rdi
0x18002bacf  sub     rsp, 40h
0x18002bad3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002bada  mov     ebx, r8d
0x18002badd  mov     rdi, rdx
0x18002bae0  mov     rsi, rcx
0x18002bae3  test    r10, r10
0x18002bae6  jnz     short loc_18002BB0A
0x18002bae8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002baef  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002baf4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002bafb  mov     r10, rax
0x18002bafe  test    rax, rax
0x18002bb01  jnz     short loc_18002BB0A
0x18002bb03  mov     eax, 0C0000139h
0x18002bb08  jmp     short loc_18002BB3A
0x18002bb0a  mov     eax, [rsp+48h+arg_30]
0x18002bb11  xor     r9d, r9d
0x18002bb14  mov     [rsp+48h+var_18], eax
0x18002bb18  mov     r8d, ebx
0x18002bb1b  mov     eax, [rsp+48h+arg_28]
0x18002bb1f  mov     rdx, rdi
0x18002bb22  mov     [rsp+48h+var_20], eax
0x18002bb26  mov     rcx, rsi
0x18002bb29  mov     rax, r10
0x18002bb2c  mov     [rsp+48h+var_28], 0
0x18002bb35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002bb3a  mov     rbx, [rsp+48h+arg_0]
0x18002bb3f  mov     rsi, [rsp+48h+arg_8]
0x18002bb44  add     rsp, 40h
0x18002bb48  pop     rdi
0x18002bb49  retn
```
