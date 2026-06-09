# wil_details_NtUpdateWnfStateData

- ea: `0x1800131bc`
- end: `0x180013242`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180011f5c`
- `0x180012eb8`

## callees

- `0x180009b20`
- `0x1800131bc`
- `0x18002b010`

## string_xrefs

- `0x1800131e0`: `NtUpdateWnfStateData`

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
0x1800131bc  mov     [rsp+arg_0], rbx
0x1800131c1  mov     [rsp+arg_8], rsi
0x1800131c6  push    rdi
0x1800131c7  sub     rsp, 40h
0x1800131cb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x1800131d2  mov     ebx, r8d
0x1800131d5  mov     rdi, rdx
0x1800131d8  mov     rsi, rcx
0x1800131db  test    r10, r10
0x1800131de  jnz     short loc_180013202
0x1800131e0  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800131e7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800131ec  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800131f3  mov     r10, rax
0x1800131f6  test    rax, rax
0x1800131f9  jnz     short loc_180013202
0x1800131fb  mov     eax, 0C0000139h
0x180013200  jmp     short loc_180013232
0x180013202  mov     eax, [rsp+48h+arg_30]
0x180013209  xor     r9d, r9d
0x18001320c  mov     [rsp+48h+var_18], eax
0x180013210  mov     r8d, ebx
0x180013213  mov     eax, [rsp+48h+arg_28]
0x180013217  mov     rdx, rdi
0x18001321a  mov     [rsp+48h+var_20], eax
0x18001321e  mov     rcx, rsi
0x180013221  mov     rax, r10
0x180013224  mov     [rsp+48h+var_28], 0
0x18001322d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013232  mov     rbx, [rsp+48h+arg_0]
0x180013237  mov     rsi, [rsp+48h+arg_8]
0x18001323c  add     rsp, 40h
0x180013240  pop     rdi
0x180013241  retn
```
