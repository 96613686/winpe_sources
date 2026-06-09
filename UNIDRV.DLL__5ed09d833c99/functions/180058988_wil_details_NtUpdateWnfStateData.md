# wil_details_NtUpdateWnfStateData

- ea: `0x180058988`
- end: `0x180058a0f`
- name: `wil_details_NtUpdateWnfStateData`
- size: `135`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int, __int64, int, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x180056844`
- `0x180058438`

## callees

- `0x18005840c`
- `0x180058988`
- `0x180077010`

## string_xrefs

- `0x1800589ac`: `NtUpdateWnfStateData`

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
0x180058988  mov     [rsp+arg_0], rbx
0x18005898d  mov     [rsp+arg_8], rsi
0x180058992  push    rdi
0x180058993  sub     rsp, 40h
0x180058997  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18005899e  mov     ebx, r8d
0x1800589a1  mov     rdi, rdx
0x1800589a4  mov     rsi, rcx
0x1800589a7  test    r10, r10
0x1800589aa  jnz     short loc_1800589CE
0x1800589ac  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x1800589b3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800589b8  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x1800589bf  mov     r10, rax
0x1800589c2  test    rax, rax
0x1800589c5  jnz     short loc_1800589CE
0x1800589c7  mov     eax, 0C0000139h
0x1800589cc  jmp     short loc_1800589FE
0x1800589ce  mov     eax, [rsp+48h+arg_30]
0x1800589d5  xor     r9d, r9d
0x1800589d8  mov     [rsp+48h+var_18], eax
0x1800589dc  mov     r8d, ebx
0x1800589df  mov     eax, [rsp+48h+arg_28]
0x1800589e3  mov     rdx, rdi
0x1800589e6  mov     [rsp+48h+var_20], eax
0x1800589ea  mov     rcx, rsi
0x1800589ed  mov     rax, r10
0x1800589f0  mov     [rsp+48h+var_28], 0
0x1800589f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800589fe  mov     rbx, [rsp+48h+arg_0]
0x180058a03  mov     rsi, [rsp+48h+arg_8]
0x180058a08  add     rsp, 40h
0x180058a0c  pop     rdi
0x180058a0d  retn
```
