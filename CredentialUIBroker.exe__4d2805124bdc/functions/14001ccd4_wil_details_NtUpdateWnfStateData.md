# wil_details_NtUpdateWnfStateData

- ea: `0x14001ccd4`
- end: `0x14001cd5a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140012754`
- `0x14001bd0c`

## callees

- `0x14001bce4`
- `0x14001ccd4`
- `0x14001f010`

## string_xrefs

- `0x14001ccf8`: `NtUpdateWnfStateData`

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
0x14001ccd4  mov     [rsp+arg_0], rbx
0x14001ccd9  mov     [rsp+arg_8], rsi
0x14001ccde  push    rdi
0x14001ccdf  sub     rsp, 40h
0x14001cce3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14001ccea  mov     ebx, r8d
0x14001cced  mov     rdi, rdx
0x14001ccf0  mov     rsi, rcx
0x14001ccf3  test    r10, r10
0x14001ccf6  jnz     short loc_14001CD1A
0x14001ccf8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14001ccff  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001cd04  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14001cd0b  mov     r10, rax
0x14001cd0e  test    rax, rax
0x14001cd11  jnz     short loc_14001CD1A
0x14001cd13  mov     eax, 0C0000139h
0x14001cd18  jmp     short loc_14001CD4A
0x14001cd1a  mov     eax, [rsp+48h+arg_30]
0x14001cd21  xor     r9d, r9d
0x14001cd24  mov     [rsp+48h+var_18], eax
0x14001cd28  mov     r8d, ebx
0x14001cd2b  mov     eax, [rsp+48h+arg_28]
0x14001cd2f  mov     rdx, rdi
0x14001cd32  mov     [rsp+48h+var_20], eax
0x14001cd36  mov     rcx, rsi
0x14001cd39  mov     rax, r10
0x14001cd3c  mov     [rsp+48h+var_28], 0
0x14001cd45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cd4a  mov     rbx, [rsp+48h+arg_0]
0x14001cd4f  mov     rsi, [rsp+48h+arg_8]
0x14001cd54  add     rsp, 40h
0x14001cd58  pop     rdi
0x14001cd59  retn
```
