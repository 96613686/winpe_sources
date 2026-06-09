# wil_details_NtUpdateWnfStateData

- ea: `0x140013a04`
- end: `0x140013a8a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000f8f8`
- `0x140012cc8`

## callees

- `0x140006bd0`
- `0x140013a04`
- `0x14001c010`

## string_xrefs

- `0x140013a28`: `NtUpdateWnfStateData`

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
0x140013a04  mov     [rsp+arg_0], rbx
0x140013a09  mov     [rsp+arg_8], rsi
0x140013a0e  push    rdi
0x140013a0f  sub     rsp, 40h
0x140013a13  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140013a1a  mov     ebx, r8d
0x140013a1d  mov     rdi, rdx
0x140013a20  mov     rsi, rcx
0x140013a23  test    r10, r10
0x140013a26  jnz     short loc_140013A4A
0x140013a28  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140013a2f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140013a34  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140013a3b  mov     r10, rax
0x140013a3e  test    rax, rax
0x140013a41  jnz     short loc_140013A4A
0x140013a43  mov     eax, 0C0000139h
0x140013a48  jmp     short loc_140013A7A
0x140013a4a  mov     eax, [rsp+48h+arg_30]
0x140013a51  xor     r9d, r9d
0x140013a54  mov     [rsp+48h+var_18], eax
0x140013a58  mov     r8d, ebx
0x140013a5b  mov     eax, [rsp+48h+arg_28]
0x140013a5f  mov     rdx, rdi
0x140013a62  mov     [rsp+48h+var_20], eax
0x140013a66  mov     rcx, rsi
0x140013a69  mov     rax, r10
0x140013a6c  mov     [rsp+48h+var_28], 0
0x140013a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013a7a  mov     rbx, [rsp+48h+arg_0]
0x140013a7f  mov     rsi, [rsp+48h+arg_8]
0x140013a84  add     rsp, 40h
0x140013a88  pop     rdi
0x140013a89  retn
```
