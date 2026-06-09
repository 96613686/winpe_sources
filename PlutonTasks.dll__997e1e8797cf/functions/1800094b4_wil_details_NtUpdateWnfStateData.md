# wil_details_NtUpdateWnfStateData

- ea: `0x1800094b4`
- end: `0x18000953a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180006d98`
- `0x1800090f8`

## callees

- `0x1800090d0`
- `0x1800094b4`
- `0x18000a010`

## string_xrefs

- `0x1800094d8`: `NtUpdateWnfStateData`

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
0x1800094b4  mov     [rsp+arg_0], rbx
0x1800094b9  mov     [rsp+arg_8], rsi
0x1800094be  push    rdi
0x1800094bf  sub     rsp, 40h
0x1800094c3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800094ca  mov     ebx, r8d
0x1800094cd  mov     rdi, rdx
0x1800094d0  mov     rsi, rcx
0x1800094d3  test    r10, r10
0x1800094d6  jnz     short loc_1800094FA
0x1800094d8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800094df  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800094e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800094eb  mov     r10, rax
0x1800094ee  test    rax, rax
0x1800094f1  jnz     short loc_1800094FA
0x1800094f3  mov     eax, 0C0000139h
0x1800094f8  jmp     short loc_18000952A
0x1800094fa  mov     eax, [rsp+48h+arg_30]
0x180009501  xor     r9d, r9d
0x180009504  mov     [rsp+48h+var_18], eax
0x180009508  mov     r8d, ebx
0x18000950b  mov     eax, [rsp+48h+arg_28]
0x18000950f  mov     rdx, rdi
0x180009512  mov     [rsp+48h+var_20], eax
0x180009516  mov     rcx, rsi
0x180009519  mov     rax, r10
0x18000951c  mov     [rsp+48h+var_28], 0
0x180009525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000952a  mov     rbx, [rsp+48h+arg_0]
0x18000952f  mov     rsi, [rsp+48h+arg_8]
0x180009534  add     rsp, 40h
0x180009538  pop     rdi
0x180009539  retn
```
