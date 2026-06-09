# wil_details_NtUpdateWnfStateData

- ea: `0x180015760`
- end: `0x1800157e6`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180013dd4`
- `0x180014ffc`

## callees

- `0x1800057f0`
- `0x180015760`
- `0x180018010`

## string_xrefs

- `0x180015784`: `NtUpdateWnfStateData`

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
0x180015760  mov     [rsp+arg_0], rbx
0x180015765  mov     [rsp+arg_8], rsi
0x18001576a  push    rdi
0x18001576b  sub     rsp, 40h
0x18001576f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180015776  mov     ebx, r8d
0x180015779  mov     rdi, rdx
0x18001577c  mov     rsi, rcx
0x18001577f  test    r10, r10
0x180015782  jnz     short loc_1800157A6
0x180015784  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001578b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015790  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180015797  mov     r10, rax
0x18001579a  test    rax, rax
0x18001579d  jnz     short loc_1800157A6
0x18001579f  mov     eax, 0C0000139h
0x1800157a4  jmp     short loc_1800157D6
0x1800157a6  mov     eax, [rsp+48h+arg_30]
0x1800157ad  xor     r9d, r9d
0x1800157b0  mov     [rsp+48h+var_18], eax
0x1800157b4  mov     r8d, ebx
0x1800157b7  mov     eax, [rsp+48h+arg_28]
0x1800157bb  mov     rdx, rdi
0x1800157be  mov     [rsp+48h+var_20], eax
0x1800157c2  mov     rcx, rsi
0x1800157c5  mov     rax, r10
0x1800157c8  mov     [rsp+48h+var_28], 0
0x1800157d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800157d6  mov     rbx, [rsp+48h+arg_0]
0x1800157db  mov     rsi, [rsp+48h+arg_8]
0x1800157e0  add     rsp, 40h
0x1800157e4  pop     rdi
0x1800157e5  retn
```
