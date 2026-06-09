# wil_details_NtUpdateWnfStateData

- ea: `0x18000d310`
- end: `0x18000d396`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000be6c`
- `0x18000d068`

## callees

- `0x180005cd0`
- `0x18000d310`
- `0x180026010`

## string_xrefs

- `0x18000d334`: `NtUpdateWnfStateData`

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
0x18000d310  mov     [rsp+arg_0], rbx
0x18000d315  mov     [rsp+arg_8], rsi
0x18000d31a  push    rdi
0x18000d31b  sub     rsp, 40h
0x18000d31f  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d326  mov     ebx, r8d
0x18000d329  mov     rdi, rdx
0x18000d32c  mov     rsi, rcx
0x18000d32f  test    r10, r10
0x18000d332  jnz     short loc_18000D356
0x18000d334  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d33b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d340  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d347  mov     r10, rax
0x18000d34a  test    rax, rax
0x18000d34d  jnz     short loc_18000D356
0x18000d34f  mov     eax, 0C0000139h
0x18000d354  jmp     short loc_18000D386
0x18000d356  mov     eax, [rsp+48h+arg_30]
0x18000d35d  xor     r9d, r9d
0x18000d360  mov     [rsp+48h+var_18], eax
0x18000d364  mov     r8d, ebx
0x18000d367  mov     eax, [rsp+48h+arg_28]
0x18000d36b  mov     rdx, rdi
0x18000d36e  mov     [rsp+48h+var_20], eax
0x18000d372  mov     rcx, rsi
0x18000d375  mov     rax, r10
0x18000d378  mov     [rsp+48h+var_28], 0
0x18000d381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d386  mov     rbx, [rsp+48h+arg_0]
0x18000d38b  mov     rsi, [rsp+48h+arg_8]
0x18000d390  add     rsp, 40h
0x18000d394  pop     rdi
0x18000d395  retn
```
