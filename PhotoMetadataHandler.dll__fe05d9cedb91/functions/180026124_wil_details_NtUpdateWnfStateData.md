# wil_details_NtUpdateWnfStateData

- ea: `0x180026124`
- end: `0x1800261aa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180024998`
- `0x180025e7c`

## callees

- `0x180025e58`
- `0x180026124`
- `0x180028010`

## string_xrefs

- `0x180026148`: `NtUpdateWnfStateData`

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
0x180026124  mov     [rsp+arg_0], rbx
0x180026129  mov     [rsp+arg_8], rsi
0x18002612e  push    rdi
0x18002612f  sub     rsp, 40h
0x180026133  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002613a  mov     ebx, r8d
0x18002613d  mov     rdi, rdx
0x180026140  mov     rsi, rcx
0x180026143  test    r10, r10
0x180026146  jnz     short loc_18002616A
0x180026148  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002614f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180026154  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002615b  mov     r10, rax
0x18002615e  test    rax, rax
0x180026161  jnz     short loc_18002616A
0x180026163  mov     eax, 0C0000139h
0x180026168  jmp     short loc_18002619A
0x18002616a  mov     eax, [rsp+48h+arg_30]
0x180026171  xor     r9d, r9d
0x180026174  mov     [rsp+48h+var_18], eax
0x180026178  mov     r8d, ebx
0x18002617b  mov     eax, [rsp+48h+arg_28]
0x18002617f  mov     rdx, rdi
0x180026182  mov     [rsp+48h+var_20], eax
0x180026186  mov     rcx, rsi
0x180026189  mov     rax, r10
0x18002618c  mov     [rsp+48h+var_28], 0
0x180026195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002619a  mov     rbx, [rsp+48h+arg_0]
0x18002619f  mov     rsi, [rsp+48h+arg_8]
0x1800261a4  add     rsp, 40h
0x1800261a8  pop     rdi
0x1800261a9  retn
```
