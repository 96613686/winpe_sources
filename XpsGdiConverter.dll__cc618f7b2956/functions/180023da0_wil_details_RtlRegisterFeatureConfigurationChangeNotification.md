# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180023da0`
- end: `0x180023e04`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180021c44`

## callees

- `0x18000d180`
- `0x180023da0`
- `0x18004a010`

## string_xrefs

- `0x180023dc4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180023da0  mov     [rsp+arg_0], rbx
0x180023da5  mov     [rsp+arg_8], rsi
0x180023daa  push    rdi
0x180023dab  sub     rsp, 30h
0x180023daf  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180023db6  mov     rbx, r9
0x180023db9  mov     rdi, rdx
0x180023dbc  mov     rsi, rcx
0x180023dbf  test    rax, rax
0x180023dc2  jnz     short loc_180023DE3
0x180023dc4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180023dcb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180023dd0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180023dd7  test    rax, rax
0x180023dda  jnz     short loc_180023DE3
0x180023ddc  mov     eax, 0C0000139h
0x180023de1  jmp     short loc_180023DF4
0x180023de3  mov     r9, rbx
0x180023de6  xor     r8d, r8d
0x180023de9  mov     rdx, rdi
0x180023dec  mov     rcx, rsi
0x180023def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023df4  mov     rbx, [rsp+38h+arg_0]
0x180023df9  mov     rsi, [rsp+38h+arg_8]
0x180023dfe  add     rsp, 30h
0x180023e02  pop     rdi
0x180023e03  retn
```
