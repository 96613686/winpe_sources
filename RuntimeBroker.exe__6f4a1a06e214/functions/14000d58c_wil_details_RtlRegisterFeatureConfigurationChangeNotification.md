# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000d58c`
- end: `0x14000d5f0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140003890`

## callees

- `0x14000cf28`
- `0x14000d58c`
- `0x140010010`

## string_xrefs

- `0x14000d5b0`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  __int64 (*NtDllProcedureAddress)(void); // rax

  NtDllProcedureAddress = (__int64 (*)(void))g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
0x14000d58c  mov     [rsp+arg_0], rbx
0x14000d591  mov     [rsp+arg_8], rsi
0x14000d596  push    rdi
0x14000d597  sub     rsp, 30h
0x14000d59b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000d5a2  mov     rbx, r9
0x14000d5a5  mov     rdi, rdx
0x14000d5a8  mov     rsi, rcx
0x14000d5ab  test    rax, rax
0x14000d5ae  jnz     short loc_14000D5CF
0x14000d5b0  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000d5b7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000d5bc  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000d5c3  test    rax, rax
0x14000d5c6  jnz     short loc_14000D5CF
0x14000d5c8  mov     eax, 0C0000139h
0x14000d5cd  jmp     short loc_14000D5E0
0x14000d5cf  mov     r9, rbx
0x14000d5d2  xor     r8d, r8d
0x14000d5d5  mov     rdx, rdi
0x14000d5d8  mov     rcx, rsi
0x14000d5db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5e0  mov     rbx, [rsp+38h+arg_0]
0x14000d5e5  mov     rsi, [rsp+38h+arg_8]
0x14000d5ea  add     rsp, 30h
0x14000d5ee  pop     rdi
0x14000d5ef  retn
```
