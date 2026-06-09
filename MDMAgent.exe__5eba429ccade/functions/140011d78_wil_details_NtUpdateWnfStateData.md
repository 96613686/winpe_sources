# wil_details_NtUpdateWnfStateData

- ea: `0x140011d78`
- end: `0x140011dfe`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000ce98`
- `0x14001162c`

## callees

- `0x140007e70`
- `0x140011d78`
- `0x140019010`

## string_xrefs

- `0x140011d9c`: `NtUpdateWnfStateData`

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
0x140011d78  mov     [rsp+arg_0], rbx
0x140011d7d  mov     [rsp+arg_8], rsi
0x140011d82  push    rdi
0x140011d83  sub     rsp, 40h
0x140011d87  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140011d8e  mov     ebx, r8d
0x140011d91  mov     rdi, rdx
0x140011d94  mov     rsi, rcx
0x140011d97  test    r10, r10
0x140011d9a  jnz     short loc_140011DBE
0x140011d9c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140011da3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140011da8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140011daf  mov     r10, rax
0x140011db2  test    rax, rax
0x140011db5  jnz     short loc_140011DBE
0x140011db7  mov     eax, 0C0000139h
0x140011dbc  jmp     short loc_140011DEE
0x140011dbe  mov     eax, [rsp+48h+arg_30]
0x140011dc5  xor     r9d, r9d
0x140011dc8  mov     [rsp+48h+var_18], eax
0x140011dcc  mov     r8d, ebx
0x140011dcf  mov     eax, [rsp+48h+arg_28]
0x140011dd3  mov     rdx, rdi
0x140011dd6  mov     [rsp+48h+var_20], eax
0x140011dda  mov     rcx, rsi
0x140011ddd  mov     rax, r10
0x140011de0  mov     [rsp+48h+var_28], 0
0x140011de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011dee  mov     rbx, [rsp+48h+arg_0]
0x140011df3  mov     rsi, [rsp+48h+arg_8]
0x140011df8  add     rsp, 40h
0x140011dfc  pop     rdi
0x140011dfd  retn
```
