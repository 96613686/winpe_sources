# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000f310`
- end: `0x18000f374`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000da80`

## callees

- `0x18000eb20`
- `0x18000f310`
- `0x18002b010`

## string_xrefs

- `0x18000f334`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000f310  mov     [rsp+arg_0], rbx
0x18000f315  mov     [rsp+arg_8], rsi
0x18000f31a  push    rdi
0x18000f31b  sub     rsp, 30h
0x18000f31f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000f326  mov     rbx, r9
0x18000f329  mov     rdi, rdx
0x18000f32c  mov     rsi, rcx
0x18000f32f  test    rax, rax
0x18000f332  jnz     short loc_18000F353
0x18000f334  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000f33b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f340  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000f347  test    rax, rax
0x18000f34a  jnz     short loc_18000F353
0x18000f34c  mov     eax, 0C0000139h
0x18000f351  jmp     short loc_18000F364
0x18000f353  mov     r9, rbx
0x18000f356  xor     r8d, r8d
0x18000f359  mov     rdx, rdi
0x18000f35c  mov     rcx, rsi
0x18000f35f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f364  mov     rbx, [rsp+38h+arg_0]
0x18000f369  mov     rsi, [rsp+38h+arg_8]
0x18000f36e  add     rsp, 30h
0x18000f372  pop     rdi
0x18000f373  retn
```
