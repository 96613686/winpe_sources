# wil_details_NtUpdateWnfStateData

- ea: `0x14000d6e0`
- end: `0x14000d766`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000c304`
- `0x14000d3bc`

## callees

- `0x140005ed0`
- `0x14000d6e0`
- `0x14002b010`

## string_xrefs

- `0x14000d704`: `NtUpdateWnfStateData`

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
0x14000d6e0  mov     [rsp+arg_0], rbx
0x14000d6e5  mov     [rsp+arg_8], rsi
0x14000d6ea  push    rdi
0x14000d6eb  sub     rsp, 40h
0x14000d6ef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000d6f6  mov     ebx, r8d
0x14000d6f9  mov     rdi, rdx
0x14000d6fc  mov     rsi, rcx
0x14000d6ff  test    r10, r10
0x14000d702  jnz     short loc_14000D726
0x14000d704  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000d70b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000d710  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000d717  mov     r10, rax
0x14000d71a  test    rax, rax
0x14000d71d  jnz     short loc_14000D726
0x14000d71f  mov     eax, 0C0000139h
0x14000d724  jmp     short loc_14000D756
0x14000d726  mov     eax, [rsp+48h+arg_30]
0x14000d72d  xor     r9d, r9d
0x14000d730  mov     [rsp+48h+var_18], eax
0x14000d734  mov     r8d, ebx
0x14000d737  mov     eax, [rsp+48h+arg_28]
0x14000d73b  mov     rdx, rdi
0x14000d73e  mov     [rsp+48h+var_20], eax
0x14000d742  mov     rcx, rsi
0x14000d745  mov     rax, r10
0x14000d748  mov     [rsp+48h+var_28], 0
0x14000d751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d756  mov     rbx, [rsp+48h+arg_0]
0x14000d75b  mov     rsi, [rsp+48h+arg_8]
0x14000d760  add     rsp, 40h
0x14000d764  pop     rdi
0x14000d765  retn
```
