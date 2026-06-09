# wil_details_NtUpdateWnfStateData

- ea: `0x18000bd64`
- end: `0x18000bdea`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a198`
- `0x18000b564`

## callees

- `0x180007920`
- `0x18000bd64`
- `0x180018010`

## string_xrefs

- `0x18000bd88`: `NtUpdateWnfStateData`

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
0x18000bd64  mov     [rsp+arg_0], rbx
0x18000bd69  mov     [rsp+arg_8], rsi
0x18000bd6e  push    rdi
0x18000bd6f  sub     rsp, 40h
0x18000bd73  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000bd7a  mov     ebx, r8d
0x18000bd7d  mov     rdi, rdx
0x18000bd80  mov     rsi, rcx
0x18000bd83  test    r10, r10
0x18000bd86  jnz     short loc_18000BDAA
0x18000bd88  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000bd8f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000bd94  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000bd9b  mov     r10, rax
0x18000bd9e  test    rax, rax
0x18000bda1  jnz     short loc_18000BDAA
0x18000bda3  mov     eax, 0C0000139h
0x18000bda8  jmp     short loc_18000BDDA
0x18000bdaa  mov     eax, [rsp+48h+arg_30]
0x18000bdb1  xor     r9d, r9d
0x18000bdb4  mov     [rsp+48h+var_18], eax
0x18000bdb8  mov     r8d, ebx
0x18000bdbb  mov     eax, [rsp+48h+arg_28]
0x18000bdbf  mov     rdx, rdi
0x18000bdc2  mov     [rsp+48h+var_20], eax
0x18000bdc6  mov     rcx, rsi
0x18000bdc9  mov     rax, r10
0x18000bdcc  mov     [rsp+48h+var_28], 0
0x18000bdd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bdda  mov     rbx, [rsp+48h+arg_0]
0x18000bddf  mov     rsi, [rsp+48h+arg_8]
0x18000bde4  add     rsp, 40h
0x18000bde8  pop     rdi
0x18000bde9  retn
```
