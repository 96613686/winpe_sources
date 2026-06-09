# wil_details_NtUpdateWnfStateData

- ea: `0x180011918`
- end: `0x18001199e`
- name: `wil_details_NtUpdateWnfStateData`
- size: `134`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callers

- `0x18000e148`
- `0x180011568`

## callees

- `0x180011540`
- `0x180011918`
- `0x180015010`

## string_xrefs

- `0x18001193c`: `NtUpdateWnfStateData`

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
0x180011918  mov     [rsp+arg_0], rbx
0x18001191d  mov     [rsp+arg_8], rsi
0x180011922  push    rdi
0x180011923  sub     rsp, 40h
0x180011927  mov     r10, cs:g_wil_details_pfnNtUpdateWnfStateData
0x18001192e  mov     ebx, r8d
0x180011931  mov     rdi, rdx
0x180011934  mov     rsi, rcx
0x180011937  test    r10, r10
0x18001193a  jnz     short loc_18001195E
0x18001193c  lea     rcx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180011943  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180011948  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x18001194f  mov     r10, rax
0x180011952  test    rax, rax
0x180011955  jnz     short loc_18001195E
0x180011957  mov     eax, 0C0000139h
0x18001195c  jmp     short loc_18001198E
0x18001195e  mov     eax, [rsp+48h+arg_30]
0x180011965  xor     r9d, r9d
0x180011968  mov     [rsp+48h+var_18], eax
0x18001196c  mov     r8d, ebx
0x18001196f  mov     eax, [rsp+48h+arg_28]
0x180011973  mov     rdx, rdi
0x180011976  mov     [rsp+48h+var_20], eax
0x18001197a  mov     rcx, rsi
0x18001197d  mov     rax, r10
0x180011980  mov     [rsp+48h+var_28], 0
0x180011989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001198e  mov     rbx, [rsp+48h+arg_0]
0x180011993  mov     rsi, [rsp+48h+arg_8]
0x180011998  add     rsp, 40h
0x18001199c  pop     rdi
0x18001199d  retn
```
