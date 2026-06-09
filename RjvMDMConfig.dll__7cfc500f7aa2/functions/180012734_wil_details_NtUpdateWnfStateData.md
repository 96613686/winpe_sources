# wil_details_NtUpdateWnfStateData

- ea: `0x180012734`
- end: `0x1800127bb`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c3e0`
- `0x180011980`

## callees

- `0x180005940`
- `0x180012734`
- `0x18001e010`

## string_xrefs

- `0x180012758`: `NtUpdateWnfStateData`

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
0x180012734  mov     [rsp+arg_0], rbx
0x180012739  mov     [rsp+arg_8], rsi
0x18001273e  push    rdi
0x18001273f  sub     rsp, 40h
0x180012743  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001274a  mov     ebx, r8d
0x18001274d  mov     rdi, rdx
0x180012750  mov     rsi, rcx
0x180012753  test    r10, r10
0x180012756  jnz     short loc_18001277A
0x180012758  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001275f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012764  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001276b  mov     r10, rax
0x18001276e  test    rax, rax
0x180012771  jnz     short loc_18001277A
0x180012773  mov     eax, 0C0000139h
0x180012778  jmp     short loc_1800127AA
0x18001277a  mov     eax, [rsp+48h+arg_30]
0x180012781  xor     r9d, r9d
0x180012784  mov     [rsp+48h+var_18], eax
0x180012788  mov     r8d, ebx
0x18001278b  mov     eax, [rsp+48h+arg_28]
0x18001278f  mov     rdx, rdi
0x180012792  mov     [rsp+48h+var_20], eax
0x180012796  mov     rcx, rsi
0x180012799  mov     rax, r10
0x18001279c  mov     [rsp+48h+var_28], 0
0x1800127a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800127aa  mov     rbx, [rsp+48h+arg_0]
0x1800127af  mov     rsi, [rsp+48h+arg_8]
0x1800127b4  add     rsp, 40h
0x1800127b8  pop     rdi
0x1800127b9  retn
```
