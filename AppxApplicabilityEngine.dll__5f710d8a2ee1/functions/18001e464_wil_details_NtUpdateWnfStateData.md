# wil_details_NtUpdateWnfStateData

- ea: `0x18001e464`
- end: `0x18001e4ea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18001d50c`
- `0x18001e1b0`

## callees

- `0x180016490`
- `0x18001e464`
- `0x180025010`

## string_xrefs

- `0x18001e488`: `NtUpdateWnfStateData`

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
0x18001e464  mov     [rsp+arg_0], rbx
0x18001e469  mov     [rsp+arg_8], rsi
0x18001e46e  push    rdi
0x18001e46f  sub     rsp, 40h
0x18001e473  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001e47a  mov     ebx, r8d
0x18001e47d  mov     rdi, rdx
0x18001e480  mov     rsi, rcx
0x18001e483  test    r10, r10
0x18001e486  jnz     short loc_18001E4AA
0x18001e488  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001e48f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e494  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001e49b  mov     r10, rax
0x18001e49e  test    rax, rax
0x18001e4a1  jnz     short loc_18001E4AA
0x18001e4a3  mov     eax, 0C0000139h
0x18001e4a8  jmp     short loc_18001E4DA
0x18001e4aa  mov     eax, [rsp+48h+arg_30]
0x18001e4b1  xor     r9d, r9d
0x18001e4b4  mov     [rsp+48h+var_18], eax
0x18001e4b8  mov     r8d, ebx
0x18001e4bb  mov     eax, [rsp+48h+arg_28]
0x18001e4bf  mov     rdx, rdi
0x18001e4c2  mov     [rsp+48h+var_20], eax
0x18001e4c6  mov     rcx, rsi
0x18001e4c9  mov     rax, r10
0x18001e4cc  mov     [rsp+48h+var_28], 0
0x18001e4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4da  mov     rbx, [rsp+48h+arg_0]
0x18001e4df  mov     rsi, [rsp+48h+arg_8]
0x18001e4e4  add     rsp, 40h
0x18001e4e8  pop     rdi
0x18001e4e9  retn
```
