# wil_details_NtUpdateWnfStateData

- ea: `0x18000d070`
- end: `0x18000d0f6`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180008fc4`
- `0x18000bff0`

## callees

- `0x18000cdec`
- `0x18000d070`
- `0x18000e010`

## string_xrefs

- `0x18000d094`: `NtUpdateWnfStateData`

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
0x18000d070  mov     [rsp+arg_0], rbx
0x18000d075  mov     [rsp+arg_8], rsi
0x18000d07a  push    rdi
0x18000d07b  sub     rsp, 40h
0x18000d07f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d086  mov     ebx, r8d
0x18000d089  mov     rdi, rdx
0x18000d08c  mov     rsi, rcx
0x18000d08f  test    r10, r10
0x18000d092  jnz     short loc_18000D0B6
0x18000d094  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d09b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d0a0  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d0a7  mov     r10, rax
0x18000d0aa  test    rax, rax
0x18000d0ad  jnz     short loc_18000D0B6
0x18000d0af  mov     eax, 0C0000139h
0x18000d0b4  jmp     short loc_18000D0E6
0x18000d0b6  mov     eax, [rsp+48h+arg_30]
0x18000d0bd  xor     r9d, r9d
0x18000d0c0  mov     [rsp+48h+var_18], eax
0x18000d0c4  mov     r8d, ebx
0x18000d0c7  mov     eax, [rsp+48h+arg_28]
0x18000d0cb  mov     rdx, rdi
0x18000d0ce  mov     [rsp+48h+var_20], eax
0x18000d0d2  mov     rcx, rsi
0x18000d0d5  mov     rax, r10
0x18000d0d8  mov     [rsp+48h+var_28], 0
0x18000d0e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0e6  mov     rbx, [rsp+48h+arg_0]
0x18000d0eb  mov     rsi, [rsp+48h+arg_8]
0x18000d0f0  add     rsp, 40h
0x18000d0f4  pop     rdi
0x18000d0f5  retn
```
