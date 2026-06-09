# wil_details_NtUpdateWnfStateData

- ea: `0x180069c14`
- end: `0x180069c9a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180067f70`
- `0x180069414`

## callees

- `0x18004088c`
- `0x180069c14`
- `0x1800b0010`

## string_xrefs

- `0x180069c38`: `NtUpdateWnfStateData`

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
0x180069c14  mov     [rsp+arg_0], rbx
0x180069c19  mov     [rsp+arg_8], rsi
0x180069c1e  push    rdi
0x180069c1f  sub     rsp, 40h
0x180069c23  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180069c2a  mov     ebx, r8d
0x180069c2d  mov     rdi, rdx
0x180069c30  mov     rsi, rcx
0x180069c33  test    r10, r10
0x180069c36  jnz     short loc_180069C5A
0x180069c38  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180069c3f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180069c44  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180069c4b  mov     r10, rax
0x180069c4e  test    rax, rax
0x180069c51  jnz     short loc_180069C5A
0x180069c53  mov     eax, 0C0000139h
0x180069c58  jmp     short loc_180069C8A
0x180069c5a  mov     eax, [rsp+48h+arg_30]
0x180069c61  xor     r9d, r9d
0x180069c64  mov     [rsp+48h+var_18], eax
0x180069c68  mov     r8d, ebx
0x180069c6b  mov     eax, [rsp+48h+arg_28]
0x180069c6f  mov     rdx, rdi
0x180069c72  mov     [rsp+48h+var_20], eax
0x180069c76  mov     rcx, rsi
0x180069c79  mov     rax, r10
0x180069c7c  mov     [rsp+48h+var_28], 0
0x180069c85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069c8a  mov     rbx, [rsp+48h+arg_0]
0x180069c8f  mov     rsi, [rsp+48h+arg_8]
0x180069c94  add     rsp, 40h
0x180069c98  pop     rdi
0x180069c99  retn
```
