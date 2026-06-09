# wil_details_NtUpdateWnfStateData

- ea: `0x18001b9b8`
- end: `0x18001ba3e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180019f4c`
- `0x18001b6a4`

## callees

- `0x18001b67c`
- `0x18001b9b8`
- `0x18001d010`

## string_xrefs

- `0x18001b9dc`: `NtUpdateWnfStateData`

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
0x18001b9b8  mov     [rsp+arg_0], rbx
0x18001b9bd  mov     [rsp+arg_8], rsi
0x18001b9c2  push    rdi
0x18001b9c3  sub     rsp, 40h
0x18001b9c7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001b9ce  mov     ebx, r8d
0x18001b9d1  mov     rdi, rdx
0x18001b9d4  mov     rsi, rcx
0x18001b9d7  test    r10, r10
0x18001b9da  jnz     short loc_18001B9FE
0x18001b9dc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001b9e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001b9e8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001b9ef  mov     r10, rax
0x18001b9f2  test    rax, rax
0x18001b9f5  jnz     short loc_18001B9FE
0x18001b9f7  mov     eax, 0C0000139h
0x18001b9fc  jmp     short loc_18001BA2E
0x18001b9fe  mov     eax, [rsp+48h+arg_30]
0x18001ba05  xor     r9d, r9d
0x18001ba08  mov     [rsp+48h+var_18], eax
0x18001ba0c  mov     r8d, ebx
0x18001ba0f  mov     eax, [rsp+48h+arg_28]
0x18001ba13  mov     rdx, rdi
0x18001ba16  mov     [rsp+48h+var_20], eax
0x18001ba1a  mov     rcx, rsi
0x18001ba1d  mov     rax, r10
0x18001ba20  mov     [rsp+48h+var_28], 0
0x18001ba29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ba2e  mov     rbx, [rsp+48h+arg_0]
0x18001ba33  mov     rsi, [rsp+48h+arg_8]
0x18001ba38  add     rsp, 40h
0x18001ba3c  pop     rdi
0x18001ba3d  retn
```
