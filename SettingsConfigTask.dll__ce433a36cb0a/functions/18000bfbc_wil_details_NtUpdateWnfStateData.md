# wil_details_NtUpdateWnfStateData

- ea: `0x18000bfbc`
- end: `0x18000c042`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180008b0c`
- `0x18000b698`

## callees

- `0x18000b670`
- `0x18000bfbc`
- `0x180024010`

## string_xrefs

- `0x18000bfe0`: `NtUpdateWnfStateData`

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
0x18000bfbc  mov     [rsp+arg_0], rbx
0x18000bfc1  mov     [rsp+arg_8], rsi
0x18000bfc6  push    rdi
0x18000bfc7  sub     rsp, 40h
0x18000bfcb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000bfd2  mov     ebx, r8d
0x18000bfd5  mov     rdi, rdx
0x18000bfd8  mov     rsi, rcx
0x18000bfdb  test    r10, r10
0x18000bfde  jnz     short loc_18000C002
0x18000bfe0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000bfe7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000bfec  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000bff3  mov     r10, rax
0x18000bff6  test    rax, rax
0x18000bff9  jnz     short loc_18000C002
0x18000bffb  mov     eax, 0C0000139h
0x18000c000  jmp     short loc_18000C032
0x18000c002  mov     eax, [rsp+48h+arg_30]
0x18000c009  xor     r9d, r9d
0x18000c00c  mov     [rsp+48h+var_18], eax
0x18000c010  mov     r8d, ebx
0x18000c013  mov     eax, [rsp+48h+arg_28]
0x18000c017  mov     rdx, rdi
0x18000c01a  mov     [rsp+48h+var_20], eax
0x18000c01e  mov     rcx, rsi
0x18000c021  mov     rax, r10
0x18000c024  mov     [rsp+48h+var_28], 0
0x18000c02d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c032  mov     rbx, [rsp+48h+arg_0]
0x18000c037  mov     rsi, [rsp+48h+arg_8]
0x18000c03c  add     rsp, 40h
0x18000c040  pop     rdi
0x18000c041  retn
```
