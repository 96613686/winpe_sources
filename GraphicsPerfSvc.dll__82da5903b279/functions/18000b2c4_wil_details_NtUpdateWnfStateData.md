# wil_details_NtUpdateWnfStateData

- ea: `0x18000b2c4`
- end: `0x18000b34a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180008d5c`
- `0x18000add8`

## callees

- `0x18000adb0`
- `0x18000b2c4`
- `0x180031010`

## string_xrefs

- `0x18000b2e8`: `NtUpdateWnfStateData`

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
0x18000b2c4  mov     [rsp+arg_0], rbx
0x18000b2c9  mov     [rsp+arg_8], rsi
0x18000b2ce  push    rdi
0x18000b2cf  sub     rsp, 40h
0x18000b2d3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b2da  mov     ebx, r8d
0x18000b2dd  mov     rdi, rdx
0x18000b2e0  mov     rsi, rcx
0x18000b2e3  test    r10, r10
0x18000b2e6  jnz     short loc_18000B30A
0x18000b2e8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b2ef  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b2f4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b2fb  mov     r10, rax
0x18000b2fe  test    rax, rax
0x18000b301  jnz     short loc_18000B30A
0x18000b303  mov     eax, 0C0000139h
0x18000b308  jmp     short loc_18000B33A
0x18000b30a  mov     eax, [rsp+48h+arg_30]
0x18000b311  xor     r9d, r9d
0x18000b314  mov     [rsp+48h+var_18], eax
0x18000b318  mov     r8d, ebx
0x18000b31b  mov     eax, [rsp+48h+arg_28]
0x18000b31f  mov     rdx, rdi
0x18000b322  mov     [rsp+48h+var_20], eax
0x18000b326  mov     rcx, rsi
0x18000b329  mov     rax, r10
0x18000b32c  mov     [rsp+48h+var_28], 0
0x18000b335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b33a  mov     rbx, [rsp+48h+arg_0]
0x18000b33f  mov     rsi, [rsp+48h+arg_8]
0x18000b344  add     rsp, 40h
0x18000b348  pop     rdi
0x18000b349  retn
```
