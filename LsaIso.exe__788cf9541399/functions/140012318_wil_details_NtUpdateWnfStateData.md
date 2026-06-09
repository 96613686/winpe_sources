# wil_details_NtUpdateWnfStateData

- ea: `0x140012318`
- end: `0x14001239e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x14000bb58`
- `0x14000dea0`

## callees

- `0x140002d0c`
- `0x140012318`
- `0x14003a010`

## string_xrefs

- `0x14001233c`: `NtUpdateWnfStateData`

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
0x140012318  mov     [rsp+arg_0], rbx
0x14001231d  mov     [rsp+arg_8], rsi
0x140012322  push    rdi
0x140012323  sub     rsp, 40h
0x140012327  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x14001232e  mov     ebx, r8d
0x140012331  mov     rdi, rdx
0x140012334  mov     rsi, rcx
0x140012337  test    r10, r10
0x14001233a  jnz     short loc_14001235E
0x14001233c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x140012343  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140012348  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x14001234f  mov     r10, rax
0x140012352  test    rax, rax
0x140012355  jnz     short loc_14001235E
0x140012357  mov     eax, 0C0000139h
0x14001235c  jmp     short loc_14001238E
0x14001235e  mov     eax, [rsp+48h+arg_30]
0x140012365  xor     r9d, r9d
0x140012368  mov     [rsp+48h+var_18], eax
0x14001236c  mov     r8d, ebx
0x14001236f  mov     eax, [rsp+48h+arg_28]
0x140012373  mov     rdx, rdi
0x140012376  mov     [rsp+48h+var_20], eax
0x14001237a  mov     rcx, rsi
0x14001237d  mov     rax, r10
0x140012380  mov     [rsp+48h+var_28], 0
0x140012389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001238e  mov     rbx, [rsp+48h+arg_0]
0x140012393  mov     rsi, [rsp+48h+arg_8]
0x140012398  add     rsp, 40h
0x14001239c  pop     rdi
0x14001239d  retn
```
