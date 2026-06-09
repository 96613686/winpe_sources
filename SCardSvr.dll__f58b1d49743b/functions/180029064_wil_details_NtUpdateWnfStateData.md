# wil_details_NtUpdateWnfStateData

- ea: `0x180029064`
- end: `0x1800290ea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180026a94`
- `0x1800288c8`

## callees

- `0x1800288a0`
- `0x180029064`
- `0x180037010`

## string_xrefs

- `0x180029088`: `NtUpdateWnfStateData`

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
0x180029064  mov     [rsp+arg_0], rbx
0x180029069  mov     [rsp+arg_8], rsi
0x18002906e  push    rdi
0x18002906f  sub     rsp, 40h
0x180029073  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002907a  mov     ebx, r8d
0x18002907d  mov     rdi, rdx
0x180029080  mov     rsi, rcx
0x180029083  test    r10, r10
0x180029086  jnz     short loc_1800290AA
0x180029088  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002908f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180029094  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002909b  mov     r10, rax
0x18002909e  test    rax, rax
0x1800290a1  jnz     short loc_1800290AA
0x1800290a3  mov     eax, 0C0000139h
0x1800290a8  jmp     short loc_1800290DA
0x1800290aa  mov     eax, [rsp+48h+arg_30]
0x1800290b1  xor     r9d, r9d
0x1800290b4  mov     [rsp+48h+var_18], eax
0x1800290b8  mov     r8d, ebx
0x1800290bb  mov     eax, [rsp+48h+arg_28]
0x1800290bf  mov     rdx, rdi
0x1800290c2  mov     [rsp+48h+var_20], eax
0x1800290c6  mov     rcx, rsi
0x1800290c9  mov     rax, r10
0x1800290cc  mov     [rsp+48h+var_28], 0
0x1800290d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800290da  mov     rbx, [rsp+48h+arg_0]
0x1800290df  mov     rsi, [rsp+48h+arg_8]
0x1800290e4  add     rsp, 40h
0x1800290e8  pop     rdi
0x1800290e9  retn
```
