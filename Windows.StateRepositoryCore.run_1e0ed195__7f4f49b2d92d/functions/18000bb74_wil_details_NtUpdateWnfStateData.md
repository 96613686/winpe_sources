# wil_details_NtUpdateWnfStateData

- ea: `0x18000bb74`
- end: `0x18000bbfa`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180008618`
- `0x18000b188`

## callees

- `0x18000b160`
- `0x18000bb74`
- `0x180011010`

## string_xrefs

- `0x18000bb98`: `NtUpdateWnfStateData`

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
0x18000bb74  mov     [rsp+arg_0], rbx
0x18000bb79  mov     [rsp+arg_8], rsi
0x18000bb7e  push    rdi
0x18000bb7f  sub     rsp, 40h
0x18000bb83  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000bb8a  mov     ebx, r8d
0x18000bb8d  mov     rdi, rdx
0x18000bb90  mov     rsi, rcx
0x18000bb93  test    r10, r10
0x18000bb96  jnz     short loc_18000BBBA
0x18000bb98  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000bb9f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000bba4  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000bbab  mov     r10, rax
0x18000bbae  test    rax, rax
0x18000bbb1  jnz     short loc_18000BBBA
0x18000bbb3  mov     eax, 0C0000139h
0x18000bbb8  jmp     short loc_18000BBEA
0x18000bbba  mov     eax, [rsp+48h+arg_30]
0x18000bbc1  xor     r9d, r9d
0x18000bbc4  mov     [rsp+48h+var_18], eax
0x18000bbc8  mov     r8d, ebx
0x18000bbcb  mov     eax, [rsp+48h+arg_28]
0x18000bbcf  mov     rdx, rdi
0x18000bbd2  mov     [rsp+48h+var_20], eax
0x18000bbd6  mov     rcx, rsi
0x18000bbd9  mov     rax, r10
0x18000bbdc  mov     [rsp+48h+var_28], 0
0x18000bbe5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbea  mov     rbx, [rsp+48h+arg_0]
0x18000bbef  mov     rsi, [rsp+48h+arg_8]
0x18000bbf4  add     rsp, 40h
0x18000bbf8  pop     rdi
0x18000bbf9  retn
```
