# wil_details_NtUpdateWnfStateData

- ea: `0x180017534`
- end: `0x1800175ba`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180014cc0`
- `0x180016d14`

## callees

- `0x18000f050`
- `0x180017534`
- `0x180028010`

## string_xrefs

- `0x180017558`: `NtUpdateWnfStateData`

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
0x180017534  mov     [rsp+arg_0], rbx
0x180017539  mov     [rsp+arg_8], rsi
0x18001753e  push    rdi
0x18001753f  sub     rsp, 40h
0x180017543  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001754a  mov     ebx, r8d
0x18001754d  mov     rdi, rdx
0x180017550  mov     rsi, rcx
0x180017553  test    r10, r10
0x180017556  jnz     short loc_18001757A
0x180017558  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001755f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180017564  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001756b  mov     r10, rax
0x18001756e  test    rax, rax
0x180017571  jnz     short loc_18001757A
0x180017573  mov     eax, 0C0000139h
0x180017578  jmp     short loc_1800175AA
0x18001757a  mov     eax, [rsp+48h+arg_30]
0x180017581  xor     r9d, r9d
0x180017584  mov     [rsp+48h+var_18], eax
0x180017588  mov     r8d, ebx
0x18001758b  mov     eax, [rsp+48h+arg_28]
0x18001758f  mov     rdx, rdi
0x180017592  mov     [rsp+48h+var_20], eax
0x180017596  mov     rcx, rsi
0x180017599  mov     rax, r10
0x18001759c  mov     [rsp+48h+var_28], 0
0x1800175a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800175aa  mov     rbx, [rsp+48h+arg_0]
0x1800175af  mov     rsi, [rsp+48h+arg_8]
0x1800175b4  add     rsp, 40h
0x1800175b8  pop     rdi
0x1800175b9  retn
```
