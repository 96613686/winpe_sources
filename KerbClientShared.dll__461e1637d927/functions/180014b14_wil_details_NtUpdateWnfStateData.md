# wil_details_NtUpdateWnfStateData

- ea: `0x180014b14`
- end: `0x180014b9a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180012cf0`
- `0x1800144f4`

## callees

- `0x1800144cc`
- `0x180014b14`
- `0x180029010`

## string_xrefs

- `0x180014b38`: `NtUpdateWnfStateData`

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
0x180014b14  mov     [rsp+arg_0], rbx
0x180014b19  mov     [rsp+arg_8], rsi
0x180014b1e  push    rdi
0x180014b1f  sub     rsp, 40h
0x180014b23  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180014b2a  mov     ebx, r8d
0x180014b2d  mov     rdi, rdx
0x180014b30  mov     rsi, rcx
0x180014b33  test    r10, r10
0x180014b36  jnz     short loc_180014B5A
0x180014b38  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180014b3f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180014b44  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180014b4b  mov     r10, rax
0x180014b4e  test    rax, rax
0x180014b51  jnz     short loc_180014B5A
0x180014b53  mov     eax, 0C0000139h
0x180014b58  jmp     short loc_180014B8A
0x180014b5a  mov     eax, [rsp+48h+arg_30]
0x180014b61  xor     r9d, r9d
0x180014b64  mov     [rsp+48h+var_18], eax
0x180014b68  mov     r8d, ebx
0x180014b6b  mov     eax, [rsp+48h+arg_28]
0x180014b6f  mov     rdx, rdi
0x180014b72  mov     [rsp+48h+var_20], eax
0x180014b76  mov     rcx, rsi
0x180014b79  mov     rax, r10
0x180014b7c  mov     [rsp+48h+var_28], 0
0x180014b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014b8a  mov     rbx, [rsp+48h+arg_0]
0x180014b8f  mov     rsi, [rsp+48h+arg_8]
0x180014b94  add     rsp, 40h
0x180014b98  pop     rdi
0x180014b99  retn
```
