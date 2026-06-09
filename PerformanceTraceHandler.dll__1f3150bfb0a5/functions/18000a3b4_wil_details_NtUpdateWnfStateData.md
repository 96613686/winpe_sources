# wil_details_NtUpdateWnfStateData

- ea: `0x18000a3b4`
- end: `0x18000a43a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180007a5c`
- `0x180009ea8`

## callees

- `0x180009e80`
- `0x18000a3b4`
- `0x18001c010`

## string_xrefs

- `0x18000a3d8`: `NtUpdateWnfStateData`

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
0x18000a3b4  mov     [rsp+arg_0], rbx
0x18000a3b9  mov     [rsp+arg_8], rsi
0x18000a3be  push    rdi
0x18000a3bf  sub     rsp, 40h
0x18000a3c3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a3ca  mov     ebx, r8d
0x18000a3cd  mov     rdi, rdx
0x18000a3d0  mov     rsi, rcx
0x18000a3d3  test    r10, r10
0x18000a3d6  jnz     short loc_18000A3FA
0x18000a3d8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a3df  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a3e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a3eb  mov     r10, rax
0x18000a3ee  test    rax, rax
0x18000a3f1  jnz     short loc_18000A3FA
0x18000a3f3  mov     eax, 0C0000139h
0x18000a3f8  jmp     short loc_18000A42A
0x18000a3fa  mov     eax, [rsp+48h+arg_30]
0x18000a401  xor     r9d, r9d
0x18000a404  mov     [rsp+48h+var_18], eax
0x18000a408  mov     r8d, ebx
0x18000a40b  mov     eax, [rsp+48h+arg_28]
0x18000a40f  mov     rdx, rdi
0x18000a412  mov     [rsp+48h+var_20], eax
0x18000a416  mov     rcx, rsi
0x18000a419  mov     rax, r10
0x18000a41c  mov     [rsp+48h+var_28], 0
0x18000a425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a42a  mov     rbx, [rsp+48h+arg_0]
0x18000a42f  mov     rsi, [rsp+48h+arg_8]
0x18000a434  add     rsp, 40h
0x18000a438  pop     rdi
0x18000a439  retn
```
