# wil_details_NtUpdateWnfStateData

- ea: `0x18002b664`
- end: `0x18002b6ea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002a4f8`
- `0x18002b1b0`

## callees

- `0x180007aa0`
- `0x18002b664`
- `0x180031010`

## string_xrefs

- `0x18002b688`: `NtUpdateWnfStateData`

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
0x18002b664  mov     [rsp+arg_0], rbx
0x18002b669  mov     [rsp+arg_8], rsi
0x18002b66e  push    rdi
0x18002b66f  sub     rsp, 40h
0x18002b673  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002b67a  mov     ebx, r8d
0x18002b67d  mov     rdi, rdx
0x18002b680  mov     rsi, rcx
0x18002b683  test    r10, r10
0x18002b686  jnz     short loc_18002B6AA
0x18002b688  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002b68f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002b694  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002b69b  mov     r10, rax
0x18002b69e  test    rax, rax
0x18002b6a1  jnz     short loc_18002B6AA
0x18002b6a3  mov     eax, 0C0000139h
0x18002b6a8  jmp     short loc_18002B6DA
0x18002b6aa  mov     eax, [rsp+48h+arg_30]
0x18002b6b1  xor     r9d, r9d
0x18002b6b4  mov     [rsp+48h+var_18], eax
0x18002b6b8  mov     r8d, ebx
0x18002b6bb  mov     eax, [rsp+48h+arg_28]
0x18002b6bf  mov     rdx, rdi
0x18002b6c2  mov     [rsp+48h+var_20], eax
0x18002b6c6  mov     rcx, rsi
0x18002b6c9  mov     rax, r10
0x18002b6cc  mov     [rsp+48h+var_28], 0
0x18002b6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b6da  mov     rbx, [rsp+48h+arg_0]
0x18002b6df  mov     rsi, [rsp+48h+arg_8]
0x18002b6e4  add     rsp, 40h
0x18002b6e8  pop     rdi
0x18002b6e9  retn
```
