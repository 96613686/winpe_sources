# wil_details_NtUpdateWnfStateData

- ea: `0x18000e664`
- end: `0x18000e6ea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c230`
- `0x18000dca8`

## callees

- `0x180006c50`
- `0x18000e664`
- `0x180031010`

## string_xrefs

- `0x18000e688`: `NtUpdateWnfStateData`

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
0x18000e664  mov     [rsp+arg_0], rbx
0x18000e669  mov     [rsp+arg_8], rsi
0x18000e66e  push    rdi
0x18000e66f  sub     rsp, 40h
0x18000e673  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000e67a  mov     ebx, r8d
0x18000e67d  mov     rdi, rdx
0x18000e680  mov     rsi, rcx
0x18000e683  test    r10, r10
0x18000e686  jnz     short loc_18000E6AA
0x18000e688  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000e68f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e694  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000e69b  mov     r10, rax
0x18000e69e  test    rax, rax
0x18000e6a1  jnz     short loc_18000E6AA
0x18000e6a3  mov     eax, 0C0000139h
0x18000e6a8  jmp     short loc_18000E6DA
0x18000e6aa  mov     eax, [rsp+48h+arg_30]
0x18000e6b1  xor     r9d, r9d
0x18000e6b4  mov     [rsp+48h+var_18], eax
0x18000e6b8  mov     r8d, ebx
0x18000e6bb  mov     eax, [rsp+48h+arg_28]
0x18000e6bf  mov     rdx, rdi
0x18000e6c2  mov     [rsp+48h+var_20], eax
0x18000e6c6  mov     rcx, rsi
0x18000e6c9  mov     rax, r10
0x18000e6cc  mov     [rsp+48h+var_28], 0
0x18000e6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6da  mov     rbx, [rsp+48h+arg_0]
0x18000e6df  mov     rsi, [rsp+48h+arg_8]
0x18000e6e4  add     rsp, 40h
0x18000e6e8  pop     rdi
0x18000e6e9  retn
```
