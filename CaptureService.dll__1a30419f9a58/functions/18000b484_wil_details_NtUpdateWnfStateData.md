# wil_details_NtUpdateWnfStateData

- ea: `0x18000b484`
- end: `0x18000b50a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180008c58`
- `0x18000afb8`

## callees

- `0x18000af90`
- `0x18000b484`
- `0x180022010`

## string_xrefs

- `0x18000b4a8`: `NtUpdateWnfStateData`

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
0x18000b484  mov     [rsp+arg_0], rbx
0x18000b489  mov     [rsp+arg_8], rsi
0x18000b48e  push    rdi
0x18000b48f  sub     rsp, 40h
0x18000b493  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b49a  mov     ebx, r8d
0x18000b49d  mov     rdi, rdx
0x18000b4a0  mov     rsi, rcx
0x18000b4a3  test    r10, r10
0x18000b4a6  jnz     short loc_18000B4CA
0x18000b4a8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b4af  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b4b4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b4bb  mov     r10, rax
0x18000b4be  test    rax, rax
0x18000b4c1  jnz     short loc_18000B4CA
0x18000b4c3  mov     eax, 0C0000139h
0x18000b4c8  jmp     short loc_18000B4FA
0x18000b4ca  mov     eax, [rsp+48h+arg_30]
0x18000b4d1  xor     r9d, r9d
0x18000b4d4  mov     [rsp+48h+var_18], eax
0x18000b4d8  mov     r8d, ebx
0x18000b4db  mov     eax, [rsp+48h+arg_28]
0x18000b4df  mov     rdx, rdi
0x18000b4e2  mov     [rsp+48h+var_20], eax
0x18000b4e6  mov     rcx, rsi
0x18000b4e9  mov     rax, r10
0x18000b4ec  mov     [rsp+48h+var_28], 0
0x18000b4f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4fa  mov     rbx, [rsp+48h+arg_0]
0x18000b4ff  mov     rsi, [rsp+48h+arg_8]
0x18000b504  add     rsp, 40h
0x18000b508  pop     rdi
0x18000b509  retn
```
