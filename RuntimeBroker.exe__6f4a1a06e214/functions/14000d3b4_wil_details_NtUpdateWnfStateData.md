# wil_details_NtUpdateWnfStateData

- ea: `0x14000d3b4`
- end: `0x14000d43a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1400049f0`
- `0x14000cf50`

## callees

- `0x14000cf28`
- `0x14000d3b4`
- `0x140010010`

## string_xrefs

- `0x14000d3d8`: `NtUpdateWnfStateData`

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
0x14000d3b4  mov     [rsp+arg_0], rbx
0x14000d3b9  mov     [rsp+arg_8], rsi
0x14000d3be  push    rdi
0x14000d3bf  sub     rsp, 40h
0x14000d3c3  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14000d3ca  mov     ebx, r8d
0x14000d3cd  mov     rdi, rdx
0x14000d3d0  mov     rsi, rcx
0x14000d3d3  test    r10, r10
0x14000d3d6  jnz     short loc_14000D3FA
0x14000d3d8  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x14000d3df  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000d3e4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14000d3eb  mov     r10, rax
0x14000d3ee  test    rax, rax
0x14000d3f1  jnz     short loc_14000D3FA
0x14000d3f3  mov     eax, 0C0000139h
0x14000d3f8  jmp     short loc_14000D42A
0x14000d3fa  mov     eax, [rsp+48h+arg_30]
0x14000d401  xor     r9d, r9d
0x14000d404  mov     [rsp+48h+var_18], eax
0x14000d408  mov     r8d, ebx
0x14000d40b  mov     eax, [rsp+48h+arg_28]
0x14000d40f  mov     rdx, rdi
0x14000d412  mov     [rsp+48h+var_20], eax
0x14000d416  mov     rcx, rsi
0x14000d419  mov     rax, r10
0x14000d41c  mov     [rsp+48h+var_28], 0
0x14000d425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d42a  mov     rbx, [rsp+48h+arg_0]
0x14000d42f  mov     rsi, [rsp+48h+arg_8]
0x14000d434  add     rsp, 40h
0x14000d438  pop     rdi
0x14000d439  retn
```
