# wil_details_NtUpdateWnfStateData

- ea: `0x18000d8c4`
- end: `0x18000d94a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000bb6c`
- `0x18000d460`

## callees

- `0x18000d438`
- `0x18000d8c4`
- `0x180035010`

## string_xrefs

- `0x18000d8e8`: `NtUpdateWnfStateData`

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
0x18000d8c4  mov     [rsp+arg_0], rbx
0x18000d8c9  mov     [rsp+arg_8], rsi
0x18000d8ce  push    rdi
0x18000d8cf  sub     rsp, 40h
0x18000d8d3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d8da  mov     ebx, r8d
0x18000d8dd  mov     rdi, rdx
0x18000d8e0  mov     rsi, rcx
0x18000d8e3  test    r10, r10
0x18000d8e6  jnz     short loc_18000D90A
0x18000d8e8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d8ef  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d8f4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d8fb  mov     r10, rax
0x18000d8fe  test    rax, rax
0x18000d901  jnz     short loc_18000D90A
0x18000d903  mov     eax, 0C0000139h
0x18000d908  jmp     short loc_18000D93A
0x18000d90a  mov     eax, [rsp+48h+arg_30]
0x18000d911  xor     r9d, r9d
0x18000d914  mov     [rsp+48h+var_18], eax
0x18000d918  mov     r8d, ebx
0x18000d91b  mov     eax, [rsp+48h+arg_28]
0x18000d91f  mov     rdx, rdi
0x18000d922  mov     [rsp+48h+var_20], eax
0x18000d926  mov     rcx, rsi
0x18000d929  mov     rax, r10
0x18000d92c  mov     [rsp+48h+var_28], 0
0x18000d935  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d93a  mov     rbx, [rsp+48h+arg_0]
0x18000d93f  mov     rsi, [rsp+48h+arg_8]
0x18000d944  add     rsp, 40h
0x18000d948  pop     rdi
0x18000d949  retn
```
