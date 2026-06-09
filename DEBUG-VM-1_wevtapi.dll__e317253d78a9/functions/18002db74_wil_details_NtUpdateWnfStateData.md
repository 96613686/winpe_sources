# wil_details_NtUpdateWnfStateData

- ea: `0x18002db74`
- end: `0x18002dbfa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18002bfa4`
- `0x18002d738`

## callees

- `0x18002d710`
- `0x18002db74`
- `0x18003c010`

## string_xrefs

- `0x18002db98`: `NtUpdateWnfStateData`

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
0x18002db74  mov     [rsp+arg_0], rbx
0x18002db79  mov     [rsp+arg_8], rsi
0x18002db7e  push    rdi
0x18002db7f  sub     rsp, 40h
0x18002db83  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18002db8a  mov     ebx, r8d
0x18002db8d  mov     rdi, rdx
0x18002db90  mov     rsi, rcx
0x18002db93  test    r10, r10
0x18002db96  jnz     short loc_18002DBBA
0x18002db98  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18002db9f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002dba4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18002dbab  mov     r10, rax
0x18002dbae  test    rax, rax
0x18002dbb1  jnz     short loc_18002DBBA
0x18002dbb3  mov     eax, 0C0000139h
0x18002dbb8  jmp     short loc_18002DBEA
0x18002dbba  mov     eax, [rsp+48h+arg_30]
0x18002dbc1  xor     r9d, r9d
0x18002dbc4  mov     [rsp+48h+var_18], eax
0x18002dbc8  mov     r8d, ebx
0x18002dbcb  mov     eax, [rsp+48h+arg_28]
0x18002dbcf  mov     rdx, rdi
0x18002dbd2  mov     [rsp+48h+var_20], eax
0x18002dbd6  mov     rcx, rsi
0x18002dbd9  mov     rax, r10
0x18002dbdc  mov     [rsp+48h+var_28], 0
0x18002dbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002dbea  mov     rbx, [rsp+48h+arg_0]
0x18002dbef  mov     rsi, [rsp+48h+arg_8]
0x18002dbf4  add     rsp, 40h
0x18002dbf8  pop     rdi
0x18002dbf9  retn
```
