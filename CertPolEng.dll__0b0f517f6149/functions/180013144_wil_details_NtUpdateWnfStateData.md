# wil_details_NtUpdateWnfStateData

- ea: `0x180013144`
- end: `0x1800131ca`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800110fc`
- `0x180012d10`

## callees

- `0x18000dc44`
- `0x180013144`
- `0x18001b010`

## string_xrefs

- `0x180013168`: `NtUpdateWnfStateData`

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
0x180013144  mov     [rsp+arg_0], rbx
0x180013149  mov     [rsp+arg_8], rsi
0x18001314e  push    rdi
0x18001314f  sub     rsp, 40h
0x180013153  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001315a  mov     ebx, r8d
0x18001315d  mov     rdi, rdx
0x180013160  mov     rsi, rcx
0x180013163  test    r10, r10
0x180013166  jnz     short loc_18001318A
0x180013168  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18001316f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013174  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001317b  mov     r10, rax
0x18001317e  test    rax, rax
0x180013181  jnz     short loc_18001318A
0x180013183  mov     eax, 0C0000139h
0x180013188  jmp     short loc_1800131BA
0x18001318a  mov     eax, [rsp+48h+arg_30]
0x180013191  xor     r9d, r9d
0x180013194  mov     [rsp+48h+var_18], eax
0x180013198  mov     r8d, ebx
0x18001319b  mov     eax, [rsp+48h+arg_28]
0x18001319f  mov     rdx, rdi
0x1800131a2  mov     [rsp+48h+var_20], eax
0x1800131a6  mov     rcx, rsi
0x1800131a9  mov     rax, r10
0x1800131ac  mov     [rsp+48h+var_28], 0
0x1800131b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800131ba  mov     rbx, [rsp+48h+arg_0]
0x1800131bf  mov     rsi, [rsp+48h+arg_8]
0x1800131c4  add     rsp, 40h
0x1800131c8  pop     rdi
0x1800131c9  retn
```
