# wil_details_NtUpdateWnfStateData

- ea: `0x180017a58`
- end: `0x180017ade`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180006bf8`
- `0x180017600`

## callees

- `0x18001307c`
- `0x180017a58`
- `0x18001c010`

## string_xrefs

- `0x180017a7c`: `NtUpdateWnfStateData`

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
0x180017a58  mov     [rsp+arg_0], rbx
0x180017a5d  mov     [rsp+arg_8], rsi
0x180017a62  push    rdi
0x180017a63  sub     rsp, 40h
0x180017a67  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180017a6e  mov     ebx, r8d
0x180017a71  mov     rdi, rdx
0x180017a74  mov     rsi, rcx
0x180017a77  test    r10, r10
0x180017a7a  jnz     short loc_180017A9E
0x180017a7c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180017a83  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180017a88  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180017a8f  mov     r10, rax
0x180017a92  test    rax, rax
0x180017a95  jnz     short loc_180017A9E
0x180017a97  mov     eax, 0C0000139h
0x180017a9c  jmp     short loc_180017ACE
0x180017a9e  mov     eax, [rsp+48h+arg_30]
0x180017aa5  xor     r9d, r9d
0x180017aa8  mov     [rsp+48h+var_18], eax
0x180017aac  mov     r8d, ebx
0x180017aaf  mov     eax, [rsp+48h+arg_28]
0x180017ab3  mov     rdx, rdi
0x180017ab6  mov     [rsp+48h+var_20], eax
0x180017aba  mov     rcx, rsi
0x180017abd  mov     rax, r10
0x180017ac0  mov     [rsp+48h+var_28], 0
0x180017ac9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017ace  mov     rbx, [rsp+48h+arg_0]
0x180017ad3  mov     rsi, [rsp+48h+arg_8]
0x180017ad8  add     rsp, 40h
0x180017adc  pop     rdi
0x180017add  retn
```
