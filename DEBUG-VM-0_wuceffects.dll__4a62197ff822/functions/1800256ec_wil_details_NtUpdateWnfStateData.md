# wil_details_NtUpdateWnfStateData

- ea: `0x1800256ec`
- end: `0x180025772`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x1800242bc`
- `0x1800253d8`

## callees

- `0x180018154`
- `0x1800256ec`
- `0x18002e010`

## string_xrefs

- `0x180025710`: `NtUpdateWnfStateData`

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
0x1800256ec  mov     [rsp+arg_0], rbx
0x1800256f1  mov     [rsp+arg_8], rsi
0x1800256f6  push    rdi
0x1800256f7  sub     rsp, 40h
0x1800256fb  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180025702  mov     ebx, r8d
0x180025705  mov     rdi, rdx
0x180025708  mov     rsi, rcx
0x18002570b  test    r10, r10
0x18002570e  jnz     short loc_180025732
0x180025710  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180025717  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002571c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180025723  mov     r10, rax
0x180025726  test    rax, rax
0x180025729  jnz     short loc_180025732
0x18002572b  mov     eax, 0C0000139h
0x180025730  jmp     short loc_180025762
0x180025732  mov     eax, [rsp+48h+arg_30]
0x180025739  xor     r9d, r9d
0x18002573c  mov     [rsp+48h+var_18], eax
0x180025740  mov     r8d, ebx
0x180025743  mov     eax, [rsp+48h+arg_28]
0x180025747  mov     rdx, rdi
0x18002574a  mov     [rsp+48h+var_20], eax
0x18002574e  mov     rcx, rsi
0x180025751  mov     rax, r10
0x180025754  mov     [rsp+48h+var_28], 0
0x18002575d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025762  mov     rbx, [rsp+48h+arg_0]
0x180025767  mov     rsi, [rsp+48h+arg_8]
0x18002576c  add     rsp, 40h
0x180025770  pop     rdi
0x180025771  retn
```
