# wil_details_NtUpdateWnfStateData

- ea: `0x180013814`
- end: `0x18001389a`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f4a8`
- `0x180013018`

## callees

- `0x180012ff0`
- `0x180013814`
- `0x180027010`

## string_xrefs

- `0x180013838`: `NtUpdateWnfStateData`

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
0x180013814  mov     [rsp+arg_0], rbx
0x180013819  mov     [rsp+arg_8], rsi
0x18001381e  push    rdi
0x18001381f  sub     rsp, 40h
0x180013823  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001382a  mov     ebx, r8d
0x18001382d  mov     rdi, rdx
0x180013830  mov     rsi, rcx
0x180013833  test    r10, r10
0x180013836  jnz     short loc_18001385A
0x180013838  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001383f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013844  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001384b  mov     r10, rax
0x18001384e  test    rax, rax
0x180013851  jnz     short loc_18001385A
0x180013853  mov     eax, 0C0000139h
0x180013858  jmp     short loc_18001388A
0x18001385a  mov     eax, [rsp+48h+arg_30]
0x180013861  xor     r9d, r9d
0x180013864  mov     [rsp+48h+var_18], eax
0x180013868  mov     r8d, ebx
0x18001386b  mov     eax, [rsp+48h+arg_28]
0x18001386f  mov     rdx, rdi
0x180013872  mov     [rsp+48h+var_20], eax
0x180013876  mov     rcx, rsi
0x180013879  mov     rax, r10
0x18001387c  mov     [rsp+48h+var_28], 0
0x180013885  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001388a  mov     rbx, [rsp+48h+arg_0]
0x18001388f  mov     rsi, [rsp+48h+arg_8]
0x180013894  add     rsp, 40h
0x180013898  pop     rdi
0x180013899  retn
```
