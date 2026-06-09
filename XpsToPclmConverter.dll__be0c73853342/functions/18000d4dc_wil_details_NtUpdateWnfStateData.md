# wil_details_NtUpdateWnfStateData

- ea: `0x18000d4dc`
- end: `0x18000d562`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000b3d4`
- `0x18000d198`

## callees

- `0x18000d170`
- `0x18000d4dc`
- `0x18001f010`

## string_xrefs

- `0x18000d500`: `NtUpdateWnfStateData`

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
0x18000d4dc  mov     [rsp+arg_0], rbx
0x18000d4e1  mov     [rsp+arg_8], rsi
0x18000d4e6  push    rdi
0x18000d4e7  sub     rsp, 40h
0x18000d4eb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000d4f2  mov     ebx, r8d
0x18000d4f5  mov     rdi, rdx
0x18000d4f8  mov     rsi, rcx
0x18000d4fb  test    r10, r10
0x18000d4fe  jnz     short loc_18000D522
0x18000d500  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000d507  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d50c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000d513  mov     r10, rax
0x18000d516  test    rax, rax
0x18000d519  jnz     short loc_18000D522
0x18000d51b  mov     eax, 0C0000139h
0x18000d520  jmp     short loc_18000D552
0x18000d522  mov     eax, [rsp+48h+arg_30]
0x18000d529  xor     r9d, r9d
0x18000d52c  mov     [rsp+48h+var_18], eax
0x18000d530  mov     r8d, ebx
0x18000d533  mov     eax, [rsp+48h+arg_28]
0x18000d537  mov     rdx, rdi
0x18000d53a  mov     [rsp+48h+var_20], eax
0x18000d53e  mov     rcx, rsi
0x18000d541  mov     rax, r10
0x18000d544  mov     [rsp+48h+var_28], 0
0x18000d54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d552  mov     rbx, [rsp+48h+arg_0]
0x18000d557  mov     rsi, [rsp+48h+arg_8]
0x18000d55c  add     rsp, 40h
0x18000d560  pop     rdi
0x18000d561  retn
```
