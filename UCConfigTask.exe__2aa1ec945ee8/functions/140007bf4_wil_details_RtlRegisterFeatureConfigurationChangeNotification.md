# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x140007bf4`
- end: `0x140007c58`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000681c`

## callees

- `0x1400077f0`
- `0x140007bf4`
- `0x140009010`

## string_xrefs

- `0x140007c18`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC NtDllProcedureAddress; // rax

  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
  if ( g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlRegisterFeatureConfigurationChangeNotification");
  g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(__int64, __int64, _QWORD, __int64))NtDllProcedureAddress)(a1, a2, 0, a4);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x140007bf4  mov     [rsp+arg_0], rbx
0x140007bf9  mov     [rsp+arg_8], rsi
0x140007bfe  push    rdi
0x140007bff  sub     rsp, 30h
0x140007c03  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140007c0a  mov     rbx, r9
0x140007c0d  mov     rdi, rdx
0x140007c10  mov     rsi, rcx
0x140007c13  test    rax, rax
0x140007c16  jnz     short loc_140007C37
0x140007c18  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140007c1f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140007c24  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140007c2b  test    rax, rax
0x140007c2e  jnz     short loc_140007C37
0x140007c30  mov     eax, 0C0000139h
0x140007c35  jmp     short loc_140007C48
0x140007c37  mov     r9, rbx
0x140007c3a  xor     r8d, r8d
0x140007c3d  mov     rdx, rdi
0x140007c40  mov     rcx, rsi
0x140007c43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c48  mov     rbx, [rsp+38h+arg_0]
0x140007c4d  mov     rsi, [rsp+38h+arg_8]
0x140007c52  add     rsp, 30h
0x140007c56  pop     rdi
0x140007c57  retn
```
