# wil_details_NtUpdateWnfStateData

- ea: `0x18000f46c`
- end: `0x18000f4f2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c630`
- `0x18000ef98`

## callees

- `0x18000a010`
- `0x18000f46c`
- `0x180014010`

## string_xrefs

- `0x18000f490`: `NtUpdateWnfStateData`

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
0x18000f46c  mov     [rsp+arg_0], rbx
0x18000f471  mov     [rsp+arg_8], rsi
0x18000f476  push    rdi
0x18000f477  sub     rsp, 40h
0x18000f47b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000f482  mov     ebx, r8d
0x18000f485  mov     rdi, rdx
0x18000f488  mov     rsi, rcx
0x18000f48b  test    r10, r10
0x18000f48e  jnz     short loc_18000F4B2
0x18000f490  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000f497  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f49c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000f4a3  mov     r10, rax
0x18000f4a6  test    rax, rax
0x18000f4a9  jnz     short loc_18000F4B2
0x18000f4ab  mov     eax, 0C0000139h
0x18000f4b0  jmp     short loc_18000F4E2
0x18000f4b2  mov     eax, [rsp+48h+arg_30]
0x18000f4b9  xor     r9d, r9d
0x18000f4bc  mov     [rsp+48h+var_18], eax
0x18000f4c0  mov     r8d, ebx
0x18000f4c3  mov     eax, [rsp+48h+arg_28]
0x18000f4c7  mov     rdx, rdi
0x18000f4ca  mov     [rsp+48h+var_20], eax
0x18000f4ce  mov     rcx, rsi
0x18000f4d1  mov     rax, r10
0x18000f4d4  mov     [rsp+48h+var_28], 0
0x18000f4dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f4e2  mov     rbx, [rsp+48h+arg_0]
0x18000f4e7  mov     rsi, [rsp+48h+arg_8]
0x18000f4ec  add     rsp, 40h
0x18000f4f0  pop     rdi
0x18000f4f1  retn
```
