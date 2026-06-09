# wil_details_NtUpdateWnfStateData

- ea: `0x18000eff4`
- end: `0x18000f07a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000be38`
- `0x18000eb48`

## callees

- `0x18000eb20`
- `0x18000eff4`
- `0x18002a010`

## string_xrefs

- `0x18000f018`: `NtUpdateWnfStateData`

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
0x18000eff4  mov     [rsp+arg_0], rbx
0x18000eff9  mov     [rsp+arg_8], rsi
0x18000effe  push    rdi
0x18000efff  sub     rsp, 40h
0x18000f003  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000f00a  mov     ebx, r8d
0x18000f00d  mov     rdi, rdx
0x18000f010  mov     rsi, rcx
0x18000f013  test    r10, r10
0x18000f016  jnz     short loc_18000F03A
0x18000f018  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000f01f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f024  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000f02b  mov     r10, rax
0x18000f02e  test    rax, rax
0x18000f031  jnz     short loc_18000F03A
0x18000f033  mov     eax, 0C0000139h
0x18000f038  jmp     short loc_18000F06A
0x18000f03a  mov     eax, [rsp+48h+arg_30]
0x18000f041  xor     r9d, r9d
0x18000f044  mov     [rsp+48h+var_18], eax
0x18000f048  mov     r8d, ebx
0x18000f04b  mov     eax, [rsp+48h+arg_28]
0x18000f04f  mov     rdx, rdi
0x18000f052  mov     [rsp+48h+var_20], eax
0x18000f056  mov     rcx, rsi
0x18000f059  mov     rax, r10
0x18000f05c  mov     [rsp+48h+var_28], 0
0x18000f065  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f06a  mov     rbx, [rsp+48h+arg_0]
0x18000f06f  mov     rsi, [rsp+48h+arg_8]
0x18000f074  add     rsp, 40h
0x18000f078  pop     rdi
0x18000f079  retn
```
