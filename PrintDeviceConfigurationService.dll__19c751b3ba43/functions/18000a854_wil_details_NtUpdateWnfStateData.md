# wil_details_NtUpdateWnfStateData

- ea: `0x18000a854`
- end: `0x18000a8da`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000808c`
- `0x18000a388`

## callees

- `0x18000a360`
- `0x18000a854`
- `0x180018010`

## string_xrefs

- `0x18000a878`: `NtUpdateWnfStateData`

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
0x18000a854  mov     [rsp+arg_0], rbx
0x18000a859  mov     [rsp+arg_8], rsi
0x18000a85e  push    rdi
0x18000a85f  sub     rsp, 40h
0x18000a863  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000a86a  mov     ebx, r8d
0x18000a86d  mov     rdi, rdx
0x18000a870  mov     rsi, rcx
0x18000a873  test    r10, r10
0x18000a876  jnz     short loc_18000A89A
0x18000a878  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000a87f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a884  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000a88b  mov     r10, rax
0x18000a88e  test    rax, rax
0x18000a891  jnz     short loc_18000A89A
0x18000a893  mov     eax, 0C0000139h
0x18000a898  jmp     short loc_18000A8CA
0x18000a89a  mov     eax, [rsp+48h+arg_30]
0x18000a8a1  xor     r9d, r9d
0x18000a8a4  mov     [rsp+48h+var_18], eax
0x18000a8a8  mov     r8d, ebx
0x18000a8ab  mov     eax, [rsp+48h+arg_28]
0x18000a8af  mov     rdx, rdi
0x18000a8b2  mov     [rsp+48h+var_20], eax
0x18000a8b6  mov     rcx, rsi
0x18000a8b9  mov     rax, r10
0x18000a8bc  mov     [rsp+48h+var_28], 0
0x18000a8c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ca  mov     rbx, [rsp+48h+arg_0]
0x18000a8cf  mov     rsi, [rsp+48h+arg_8]
0x18000a8d4  add     rsp, 40h
0x18000a8d8  pop     rdi
0x18000a8d9  retn
```
