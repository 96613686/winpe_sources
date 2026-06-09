# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000dbc8`
- end: `0x18000dc2c`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ccb0`

## callees

- `0x1800089f0`
- `0x18000dbc8`
- `0x18002c010`

## string_xrefs

- `0x18000dbec`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000dbc8  mov     [rsp+arg_0], rbx
0x18000dbcd  mov     [rsp+arg_8], rsi
0x18000dbd2  push    rdi
0x18000dbd3  sub     rsp, 30h
0x18000dbd7  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000dbde  mov     rbx, r9
0x18000dbe1  mov     rdi, rdx
0x18000dbe4  mov     rsi, rcx
0x18000dbe7  test    rax, rax
0x18000dbea  jnz     short loc_18000DC0B
0x18000dbec  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000dbf3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000dbf8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000dbff  test    rax, rax
0x18000dc02  jnz     short loc_18000DC0B
0x18000dc04  mov     eax, 0C0000139h
0x18000dc09  jmp     short loc_18000DC1C
0x18000dc0b  mov     r9, rbx
0x18000dc0e  xor     r8d, r8d
0x18000dc11  mov     rdx, rdi
0x18000dc14  mov     rcx, rsi
0x18000dc17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc1c  mov     rbx, [rsp+38h+arg_0]
0x18000dc21  mov     rsi, [rsp+38h+arg_8]
0x18000dc26  add     rsp, 30h
0x18000dc2a  pop     rdi
0x18000dc2b  retn
```
