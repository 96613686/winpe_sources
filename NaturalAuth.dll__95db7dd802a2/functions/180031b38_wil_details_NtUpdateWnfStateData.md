# wil_details_NtUpdateWnfStateData

- ea: `0x180031b38`
- end: `0x180031bbe`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180030b00`
- `0x180031890`

## callees

- `0x18000a780`
- `0x180031b38`
- `0x180046010`

## string_xrefs

- `0x180031b5c`: `NtUpdateWnfStateData`

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
0x180031b38  mov     [rsp+arg_0], rbx
0x180031b3d  mov     [rsp+arg_8], rsi
0x180031b42  push    rdi
0x180031b43  sub     rsp, 40h
0x180031b47  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180031b4e  mov     ebx, r8d
0x180031b51  mov     rdi, rdx
0x180031b54  mov     rsi, rcx
0x180031b57  test    r10, r10
0x180031b5a  jnz     short loc_180031B7E
0x180031b5c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180031b63  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180031b68  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180031b6f  mov     r10, rax
0x180031b72  test    rax, rax
0x180031b75  jnz     short loc_180031B7E
0x180031b77  mov     eax, 0C0000139h
0x180031b7c  jmp     short loc_180031BAE
0x180031b7e  mov     eax, [rsp+48h+arg_30]
0x180031b85  xor     r9d, r9d
0x180031b88  mov     [rsp+48h+var_18], eax
0x180031b8c  mov     r8d, ebx
0x180031b8f  mov     eax, [rsp+48h+arg_28]
0x180031b93  mov     rdx, rdi
0x180031b96  mov     [rsp+48h+var_20], eax
0x180031b9a  mov     rcx, rsi
0x180031b9d  mov     rax, r10
0x180031ba0  mov     [rsp+48h+var_28], 0
0x180031ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180031bae  mov     rbx, [rsp+48h+arg_0]
0x180031bb3  mov     rsi, [rsp+48h+arg_8]
0x180031bb8  add     rsp, 40h
0x180031bbc  pop     rdi
0x180031bbd  retn
```
