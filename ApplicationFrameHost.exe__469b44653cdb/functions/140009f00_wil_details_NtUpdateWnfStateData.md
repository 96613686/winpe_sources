# wil_details_NtUpdateWnfStateData

- ea: `0x140009f00`
- end: `0x140009f86`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140007ca0`
- `0x140009bc8`

## callees

- `0x140009ba0`
- `0x140009f00`
- `0x14000b010`

## string_xrefs

- `0x140009f24`: `NtUpdateWnfStateData`

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
0x140009f00  mov     [rsp+arg_0], rbx
0x140009f05  mov     [rsp+arg_8], rsi
0x140009f0a  push    rdi
0x140009f0b  sub     rsp, 40h
0x140009f0f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140009f16  mov     ebx, r8d
0x140009f19  mov     rdi, rdx
0x140009f1c  mov     rsi, rcx
0x140009f1f  test    r10, r10
0x140009f22  jnz     short loc_140009F46
0x140009f24  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140009f2b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140009f30  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140009f37  mov     r10, rax
0x140009f3a  test    rax, rax
0x140009f3d  jnz     short loc_140009F46
0x140009f3f  mov     eax, 0C0000139h
0x140009f44  jmp     short loc_140009F76
0x140009f46  mov     eax, [rsp+48h+arg_30]
0x140009f4d  xor     r9d, r9d
0x140009f50  mov     [rsp+48h+var_18], eax
0x140009f54  mov     r8d, ebx
0x140009f57  mov     eax, [rsp+48h+arg_28]
0x140009f5b  mov     rdx, rdi
0x140009f5e  mov     [rsp+48h+var_20], eax
0x140009f62  mov     rcx, rsi
0x140009f65  mov     rax, r10
0x140009f68  mov     [rsp+48h+var_28], 0
0x140009f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009f76  mov     rbx, [rsp+48h+arg_0]
0x140009f7b  mov     rsi, [rsp+48h+arg_8]
0x140009f80  add     rsp, 40h
0x140009f84  pop     rdi
0x140009f85  retn
```
