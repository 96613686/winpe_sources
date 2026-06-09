# wil_details_NtUpdateWnfStateData

- ea: `0x180056f04`
- end: `0x180056f8a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180054ce0`
- `0x1800569c4`

## callees

- `0x18005699c`
- `0x180056f04`
- `0x180075010`

## string_xrefs

- `0x180056f28`: `NtUpdateWnfStateData`

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
0x180056f04  mov     [rsp+arg_0], rbx
0x180056f09  mov     [rsp+arg_8], rsi
0x180056f0e  push    rdi
0x180056f0f  sub     rsp, 40h
0x180056f13  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180056f1a  mov     ebx, r8d
0x180056f1d  mov     rdi, rdx
0x180056f20  mov     rsi, rcx
0x180056f23  test    r10, r10
0x180056f26  jnz     short loc_180056F4A
0x180056f28  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180056f2f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180056f34  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180056f3b  mov     r10, rax
0x180056f3e  test    rax, rax
0x180056f41  jnz     short loc_180056F4A
0x180056f43  mov     eax, 0C0000139h
0x180056f48  jmp     short loc_180056F7A
0x180056f4a  mov     eax, [rsp+48h+arg_30]
0x180056f51  xor     r9d, r9d
0x180056f54  mov     [rsp+48h+var_18], eax
0x180056f58  mov     r8d, ebx
0x180056f5b  mov     eax, [rsp+48h+arg_28]
0x180056f5f  mov     rdx, rdi
0x180056f62  mov     [rsp+48h+var_20], eax
0x180056f66  mov     rcx, rsi
0x180056f69  mov     rax, r10
0x180056f6c  mov     [rsp+48h+var_28], 0
0x180056f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056f7a  mov     rbx, [rsp+48h+arg_0]
0x180056f7f  mov     rsi, [rsp+48h+arg_8]
0x180056f84  add     rsp, 40h
0x180056f88  pop     rdi
0x180056f89  retn
```
