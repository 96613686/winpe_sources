# wil_details_NtUpdateWnfStateData

- ea: `0x18000b1ec`
- end: `0x18000b272`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180009b68`
- `0x18000ae0c`

## callees

- `0x1800076b0`
- `0x18000b1ec`
- `0x18001c010`

## string_xrefs

- `0x18000b210`: `NtUpdateWnfStateData`

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
0x18000b1ec  mov     [rsp+arg_0], rbx
0x18000b1f1  mov     [rsp+arg_8], rsi
0x18000b1f6  push    rdi
0x18000b1f7  sub     rsp, 40h
0x18000b1fb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000b202  mov     ebx, r8d
0x18000b205  mov     rdi, rdx
0x18000b208  mov     rsi, rcx
0x18000b20b  test    r10, r10
0x18000b20e  jnz     short loc_18000B232
0x18000b210  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000b217  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b21c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000b223  mov     r10, rax
0x18000b226  test    rax, rax
0x18000b229  jnz     short loc_18000B232
0x18000b22b  mov     eax, 0C0000139h
0x18000b230  jmp     short loc_18000B262
0x18000b232  mov     eax, [rsp+48h+arg_30]
0x18000b239  xor     r9d, r9d
0x18000b23c  mov     [rsp+48h+var_18], eax
0x18000b240  mov     r8d, ebx
0x18000b243  mov     eax, [rsp+48h+arg_28]
0x18000b247  mov     rdx, rdi
0x18000b24a  mov     [rsp+48h+var_20], eax
0x18000b24e  mov     rcx, rsi
0x18000b251  mov     rax, r10
0x18000b254  mov     [rsp+48h+var_28], 0
0x18000b25d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b262  mov     rbx, [rsp+48h+arg_0]
0x18000b267  mov     rsi, [rsp+48h+arg_8]
0x18000b26c  add     rsp, 40h
0x18000b270  pop     rdi
0x18000b271  retn
```
