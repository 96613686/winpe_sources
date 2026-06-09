# wil_details_NtUpdateWnfStateData

- ea: `0x140007b68`
- end: `0x140007bee`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x140005c24`
- `0x140007818`

## callees

- `0x1400077f0`
- `0x140007b68`
- `0x140009010`

## string_xrefs

- `0x140007b8c`: `NtUpdateWnfStateData`

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
0x140007b68  mov     [rsp+arg_0], rbx
0x140007b6d  mov     [rsp+arg_8], rsi
0x140007b72  push    rdi
0x140007b73  sub     rsp, 40h
0x140007b77  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x140007b7e  mov     ebx, r8d
0x140007b81  mov     rdi, rdx
0x140007b84  mov     rsi, rcx
0x140007b87  test    r10, r10
0x140007b8a  jnz     short loc_140007BAE
0x140007b8c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140007b93  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140007b98  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x140007b9f  mov     r10, rax
0x140007ba2  test    rax, rax
0x140007ba5  jnz     short loc_140007BAE
0x140007ba7  mov     eax, 0C0000139h
0x140007bac  jmp     short loc_140007BDE
0x140007bae  mov     eax, [rsp+48h+arg_30]
0x140007bb5  xor     r9d, r9d
0x140007bb8  mov     [rsp+48h+var_18], eax
0x140007bbc  mov     r8d, ebx
0x140007bbf  mov     eax, [rsp+48h+arg_28]
0x140007bc3  mov     rdx, rdi
0x140007bc6  mov     [rsp+48h+var_20], eax
0x140007bca  mov     rcx, rsi
0x140007bcd  mov     rax, r10
0x140007bd0  mov     [rsp+48h+var_28], 0
0x140007bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bde  mov     rbx, [rsp+48h+arg_0]
0x140007be3  mov     rsi, [rsp+48h+arg_8]
0x140007be8  add     rsp, 40h
0x140007bec  pop     rdi
0x140007bed  retn
```
