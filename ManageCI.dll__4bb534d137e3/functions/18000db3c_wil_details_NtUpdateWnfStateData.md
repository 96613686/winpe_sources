# wil_details_NtUpdateWnfStateData

- ea: `0x18000db3c`
- end: `0x18000dbc2`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000c520`
- `0x18000d790`

## callees

- `0x1800089f0`
- `0x18000db3c`
- `0x18002c010`

## string_xrefs

- `0x18000db60`: `NtUpdateWnfStateData`

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
0x18000db3c  mov     [rsp+arg_0], rbx
0x18000db41  mov     [rsp+arg_8], rsi
0x18000db46  push    rdi
0x18000db47  sub     rsp, 40h
0x18000db4b  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18000db52  mov     ebx, r8d
0x18000db55  mov     rdi, rdx
0x18000db58  mov     rsi, rcx
0x18000db5b  test    r10, r10
0x18000db5e  jnz     short loc_18000DB82
0x18000db60  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x18000db67  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000db6c  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18000db73  mov     r10, rax
0x18000db76  test    rax, rax
0x18000db79  jnz     short loc_18000DB82
0x18000db7b  mov     eax, 0C0000139h
0x18000db80  jmp     short loc_18000DBB2
0x18000db82  mov     eax, [rsp+48h+arg_30]
0x18000db89  xor     r9d, r9d
0x18000db8c  mov     [rsp+48h+var_18], eax
0x18000db90  mov     r8d, ebx
0x18000db93  mov     eax, [rsp+48h+arg_28]
0x18000db97  mov     rdx, rdi
0x18000db9a  mov     [rsp+48h+var_20], eax
0x18000db9e  mov     rcx, rsi
0x18000dba1  mov     rax, r10
0x18000dba4  mov     [rsp+48h+var_28], 0
0x18000dbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dbb2  mov     rbx, [rsp+48h+arg_0]
0x18000dbb7  mov     rsi, [rsp+48h+arg_8]
0x18000dbbc  add     rsp, 40h
0x18000dbc0  pop     rdi
0x18000dbc1  retn
```
