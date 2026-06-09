# wil_details_NtUpdateWnfStateData

- ea: `0x1800390e0`
- end: `0x180039167`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180038120`
- `0x180038c10`

## callees

- `0x18000c6dc`
- `0x1800390e0`
- `0x18003f010`

## string_xrefs

- `0x180039104`: `NtUpdateWnfStateData`

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
0x1800390e0  mov     [rsp+arg_0], rbx
0x1800390e5  mov     [rsp+arg_8], rsi
0x1800390ea  push    rdi
0x1800390eb  sub     rsp, 40h
0x1800390ef  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800390f6  mov     ebx, r8d
0x1800390f9  mov     rdi, rdx
0x1800390fc  mov     rsi, rcx
0x1800390ff  test    r10, r10
0x180039102  jnz     short loc_180039126
0x180039104  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18003910b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180039110  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180039117  mov     r10, rax
0x18003911a  test    rax, rax
0x18003911d  jnz     short loc_180039126
0x18003911f  mov     eax, 0C0000139h
0x180039124  jmp     short loc_180039156
0x180039126  mov     eax, [rsp+48h+arg_30]
0x18003912d  xor     r9d, r9d
0x180039130  mov     [rsp+48h+var_18], eax
0x180039134  mov     r8d, ebx
0x180039137  mov     eax, [rsp+48h+arg_28]
0x18003913b  mov     rdx, rdi
0x18003913e  mov     [rsp+48h+var_20], eax
0x180039142  mov     rcx, rsi
0x180039145  mov     rax, r10
0x180039148  mov     [rsp+48h+var_28], 0
0x180039151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180039156  mov     rbx, [rsp+48h+arg_0]
0x18003915b  mov     rsi, [rsp+48h+arg_8]
0x180039160  add     rsp, 40h
0x180039164  pop     rdi
0x180039165  retn
```
