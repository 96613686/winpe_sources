# wil_details_NtUpdateWnfStateData

- ea: `0x180023bc4`
- end: `0x180023c4a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180020988`
- `0x180023240`

## callees

- `0x18000d180`
- `0x180023bc4`
- `0x18004a010`

## string_xrefs

- `0x180023be8`: `NtUpdateWnfStateData`

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
0x180023bc4  mov     [rsp+arg_0], rbx
0x180023bc9  mov     [rsp+arg_8], rsi
0x180023bce  push    rdi
0x180023bcf  sub     rsp, 40h
0x180023bd3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180023bda  mov     ebx, r8d
0x180023bdd  mov     rdi, rdx
0x180023be0  mov     rsi, rcx
0x180023be3  test    r10, r10
0x180023be6  jnz     short loc_180023C0A
0x180023be8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180023bef  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180023bf4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180023bfb  mov     r10, rax
0x180023bfe  test    rax, rax
0x180023c01  jnz     short loc_180023C0A
0x180023c03  mov     eax, 0C0000139h
0x180023c08  jmp     short loc_180023C3A
0x180023c0a  mov     eax, [rsp+48h+arg_30]
0x180023c11  xor     r9d, r9d
0x180023c14  mov     [rsp+48h+var_18], eax
0x180023c18  mov     r8d, ebx
0x180023c1b  mov     eax, [rsp+48h+arg_28]
0x180023c1f  mov     rdx, rdi
0x180023c22  mov     [rsp+48h+var_20], eax
0x180023c26  mov     rcx, rsi
0x180023c29  mov     rax, r10
0x180023c2c  mov     [rsp+48h+var_28], 0
0x180023c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023c3a  mov     rbx, [rsp+48h+arg_0]
0x180023c3f  mov     rsi, [rsp+48h+arg_8]
0x180023c44  add     rsp, 40h
0x180023c48  pop     rdi
0x180023c49  retn
```
