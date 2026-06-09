# wil_details_NtUpdateWnfStateData

- ea: `0x14000b514`
- end: `0x14000b59a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140008af8`
- `0x14000b03c`

## callees

- `0x140005fd0`
- `0x14000b514`
- `0x14002b010`

## string_xrefs

- `0x14000b538`: `NtUpdateWnfStateData`

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
0x14000b514  mov     [rsp+arg_0], rbx
0x14000b519  mov     [rsp+arg_8], rsi
0x14000b51e  push    rdi
0x14000b51f  sub     rsp, 40h
0x14000b523  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000b52a  mov     ebx, r8d
0x14000b52d  mov     rdi, rdx
0x14000b530  mov     rsi, rcx
0x14000b533  test    r10, r10
0x14000b536  jnz     short loc_14000B55A
0x14000b538  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000b53f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000b544  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000b54b  mov     r10, rax
0x14000b54e  test    rax, rax
0x14000b551  jnz     short loc_14000B55A
0x14000b553  mov     eax, 0C0000139h
0x14000b558  jmp     short loc_14000B58A
0x14000b55a  mov     eax, [rsp+48h+arg_30]
0x14000b561  xor     r9d, r9d
0x14000b564  mov     [rsp+48h+var_18], eax
0x14000b568  mov     r8d, ebx
0x14000b56b  mov     eax, [rsp+48h+arg_28]
0x14000b56f  mov     rdx, rdi
0x14000b572  mov     [rsp+48h+var_20], eax
0x14000b576  mov     rcx, rsi
0x14000b579  mov     rax, r10
0x14000b57c  mov     [rsp+48h+var_28], 0
0x14000b585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b58a  mov     rbx, [rsp+48h+arg_0]
0x14000b58f  mov     rsi, [rsp+48h+arg_8]
0x14000b594  add     rsp, 40h
0x14000b598  pop     rdi
0x14000b599  retn
```
