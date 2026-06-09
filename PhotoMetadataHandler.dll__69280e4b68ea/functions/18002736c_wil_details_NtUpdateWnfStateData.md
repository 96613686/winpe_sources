# wil_details_NtUpdateWnfStateData

- ea: `0x18002736c`
- end: `0x1800273f3`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180025b9c`
- `0x1800270bc`

## callees

- `0x180027098`
- `0x18002736c`
- `0x180029010`

## string_xrefs

- `0x180027390`: `NtUpdateWnfStateData`

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
0x18002736c  mov     [rsp+arg_0], rbx
0x180027371  mov     [rsp+arg_8], rsi
0x180027376  push    rdi
0x180027377  sub     rsp, 40h
0x18002737b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180027382  mov     ebx, r8d
0x180027385  mov     rdi, rdx
0x180027388  mov     rsi, rcx
0x18002738b  test    r10, r10
0x18002738e  jnz     short loc_1800273B2
0x180027390  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180027397  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002739c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800273a3  mov     r10, rax
0x1800273a6  test    rax, rax
0x1800273a9  jnz     short loc_1800273B2
0x1800273ab  mov     eax, 0C0000139h
0x1800273b0  jmp     short loc_1800273E2
0x1800273b2  mov     eax, [rsp+48h+arg_30]
0x1800273b9  xor     r9d, r9d
0x1800273bc  mov     [rsp+48h+var_18], eax
0x1800273c0  mov     r8d, ebx
0x1800273c3  mov     eax, [rsp+48h+arg_28]
0x1800273c7  mov     rdx, rdi
0x1800273ca  mov     [rsp+48h+var_20], eax
0x1800273ce  mov     rcx, rsi
0x1800273d1  mov     rax, r10
0x1800273d4  mov     [rsp+48h+var_28], 0
0x1800273dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800273e2  mov     rbx, [rsp+48h+arg_0]
0x1800273e7  mov     rsi, [rsp+48h+arg_8]
0x1800273ec  add     rsp, 40h
0x1800273f0  pop     rdi
0x1800273f1  retn
```
