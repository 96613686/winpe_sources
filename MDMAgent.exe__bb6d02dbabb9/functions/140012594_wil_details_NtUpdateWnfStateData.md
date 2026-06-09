# wil_details_NtUpdateWnfStateData

- ea: `0x140012594`
- end: `0x14001261b`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000d480`
- `0x140011e28`

## callees

- `0x1400081c8`
- `0x140012594`
- `0x14001a010`

## string_xrefs

- `0x1400125b8`: `NtUpdateWnfStateData`

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
0x140012594  mov     [rsp+arg_0], rbx
0x140012599  mov     [rsp+arg_8], rsi
0x14001259e  push    rdi
0x14001259f  sub     rsp, 40h
0x1400125a3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400125aa  mov     ebx, r8d
0x1400125ad  mov     rdi, rdx
0x1400125b0  mov     rsi, rcx
0x1400125b3  test    r10, r10
0x1400125b6  jnz     short loc_1400125DA
0x1400125b8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1400125bf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400125c4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1400125cb  mov     r10, rax
0x1400125ce  test    rax, rax
0x1400125d1  jnz     short loc_1400125DA
0x1400125d3  mov     eax, 0C0000139h
0x1400125d8  jmp     short loc_14001260A
0x1400125da  mov     eax, [rsp+48h+arg_30]
0x1400125e1  xor     r9d, r9d
0x1400125e4  mov     [rsp+48h+var_18], eax
0x1400125e8  mov     r8d, ebx
0x1400125eb  mov     eax, [rsp+48h+arg_28]
0x1400125ef  mov     rdx, rdi
0x1400125f2  mov     [rsp+48h+var_20], eax
0x1400125f6  mov     rcx, rsi
0x1400125f9  mov     rax, r10
0x1400125fc  mov     [rsp+48h+var_28], 0
0x140012605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001260a  mov     rbx, [rsp+48h+arg_0]
0x14001260f  mov     rsi, [rsp+48h+arg_8]
0x140012614  add     rsp, 40h
0x140012618  pop     rdi
0x140012619  retn
```
