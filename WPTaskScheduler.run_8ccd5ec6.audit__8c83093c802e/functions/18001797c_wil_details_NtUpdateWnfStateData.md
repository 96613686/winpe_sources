# wil_details_NtUpdateWnfStateData

- ea: `0x18001797c`
- end: `0x180017a02`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180014390`
- `0x180016ff8`

## callees

- `0x180016fd0`
- `0x18001797c`
- `0x180022010`

## string_xrefs

- `0x1800179a0`: `NtUpdateWnfStateData`

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
0x18001797c  mov     [rsp+arg_0], rbx
0x180017981  mov     [rsp+arg_8], rsi
0x180017986  push    rdi
0x180017987  sub     rsp, 40h
0x18001798b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180017992  mov     ebx, r8d
0x180017995  mov     rdi, rdx
0x180017998  mov     rsi, rcx
0x18001799b  test    r10, r10
0x18001799e  jnz     short loc_1800179C2
0x1800179a0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800179a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800179ac  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800179b3  mov     r10, rax
0x1800179b6  test    rax, rax
0x1800179b9  jnz     short loc_1800179C2
0x1800179bb  mov     eax, 0C0000139h
0x1800179c0  jmp     short loc_1800179F2
0x1800179c2  mov     eax, [rsp+48h+arg_30]
0x1800179c9  xor     r9d, r9d
0x1800179cc  mov     [rsp+48h+var_18], eax
0x1800179d0  mov     r8d, ebx
0x1800179d3  mov     eax, [rsp+48h+arg_28]
0x1800179d7  mov     rdx, rdi
0x1800179da  mov     [rsp+48h+var_20], eax
0x1800179de  mov     rcx, rsi
0x1800179e1  mov     rax, r10
0x1800179e4  mov     [rsp+48h+var_28], 0
0x1800179ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800179f2  mov     rbx, [rsp+48h+arg_0]
0x1800179f7  mov     rsi, [rsp+48h+arg_8]
0x1800179fc  add     rsp, 40h
0x180017a00  pop     rdi
0x180017a01  retn
```
