# wil_details_NtUpdateWnfStateData

- ea: `0x1400077a8`
- end: `0x14000782e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140005da4`
- `0x140007314`

## callees

- `0x1400072ec`
- `0x1400077a8`
- `0x140008010`

## string_xrefs

- `0x1400077cc`: `NtUpdateWnfStateData`

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
0x1400077a8  mov     [rsp+arg_0], rbx
0x1400077ad  mov     [rsp+arg_8], rsi
0x1400077b2  push    rdi
0x1400077b3  sub     rsp, 40h
0x1400077b7  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1400077be  mov     ebx, r8d
0x1400077c1  mov     rdi, rdx
0x1400077c4  mov     rsi, rcx
0x1400077c7  test    r10, r10
0x1400077ca  jnz     short loc_1400077EE
0x1400077cc  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1400077d3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400077d8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1400077df  mov     r10, rax
0x1400077e2  test    rax, rax
0x1400077e5  jnz     short loc_1400077EE
0x1400077e7  mov     eax, 0C0000139h
0x1400077ec  jmp     short loc_14000781E
0x1400077ee  mov     eax, [rsp+48h+arg_30]
0x1400077f5  xor     r9d, r9d
0x1400077f8  mov     [rsp+48h+var_18], eax
0x1400077fc  mov     r8d, ebx
0x1400077ff  mov     eax, [rsp+48h+arg_28]
0x140007803  mov     rdx, rdi
0x140007806  mov     [rsp+48h+var_20], eax
0x14000780a  mov     rcx, rsi
0x14000780d  mov     rax, r10
0x140007810  mov     [rsp+48h+var_28], 0
0x140007819  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000781e  mov     rbx, [rsp+48h+arg_0]
0x140007823  mov     rsi, [rsp+48h+arg_8]
0x140007828  add     rsp, 40h
0x14000782c  pop     rdi
0x14000782d  retn
```
