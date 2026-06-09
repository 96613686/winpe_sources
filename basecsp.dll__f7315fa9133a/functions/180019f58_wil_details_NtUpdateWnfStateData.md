# wil_details_NtUpdateWnfStateData

- ea: `0x180019f58`
- end: `0x180019fde`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180015878`
- `0x180019258`

## callees

- `0x180019230`
- `0x180019f58`
- `0x18002e010`

## string_xrefs

- `0x180019f7c`: `NtUpdateWnfStateData`

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
0x180019f58  mov     [rsp+arg_0], rbx
0x180019f5d  mov     [rsp+arg_8], rsi
0x180019f62  push    rdi
0x180019f63  sub     rsp, 40h
0x180019f67  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180019f6e  mov     ebx, r8d
0x180019f71  mov     rdi, rdx
0x180019f74  mov     rsi, rcx
0x180019f77  test    r10, r10
0x180019f7a  jnz     short loc_180019F9E
0x180019f7c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180019f83  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180019f88  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180019f8f  mov     r10, rax
0x180019f92  test    rax, rax
0x180019f95  jnz     short loc_180019F9E
0x180019f97  mov     eax, 0C0000139h
0x180019f9c  jmp     short loc_180019FCE
0x180019f9e  mov     eax, [rsp+48h+arg_30]
0x180019fa5  xor     r9d, r9d
0x180019fa8  mov     [rsp+48h+var_18], eax
0x180019fac  mov     r8d, ebx
0x180019faf  mov     eax, [rsp+48h+arg_28]
0x180019fb3  mov     rdx, rdi
0x180019fb6  mov     [rsp+48h+var_20], eax
0x180019fba  mov     rcx, rsi
0x180019fbd  mov     rax, r10
0x180019fc0  mov     [rsp+48h+var_28], 0
0x180019fc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fce  mov     rbx, [rsp+48h+arg_0]
0x180019fd3  mov     rsi, [rsp+48h+arg_8]
0x180019fd8  add     rsp, 40h
0x180019fdc  pop     rdi
0x180019fdd  retn
```
