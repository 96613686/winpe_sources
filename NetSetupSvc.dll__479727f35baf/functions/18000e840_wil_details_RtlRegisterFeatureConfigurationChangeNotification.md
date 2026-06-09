# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000e840`
- end: `0x18000e8a4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d180`

## callees

- `0x180006c50`
- `0x18000e840`
- `0x180031010`

## string_xrefs

- `0x18000e864`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000e840  mov     [rsp+arg_0], rbx
0x18000e845  mov     [rsp+arg_8], rsi
0x18000e84a  push    rdi
0x18000e84b  sub     rsp, 30h
0x18000e84f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000e856  mov     rbx, r9
0x18000e859  mov     rdi, rdx
0x18000e85c  mov     rsi, rcx
0x18000e85f  test    rax, rax
0x18000e862  jnz     short loc_18000E883
0x18000e864  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000e86b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000e870  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000e877  test    rax, rax
0x18000e87a  jnz     short loc_18000E883
0x18000e87c  mov     eax, 0C0000139h
0x18000e881  jmp     short loc_18000E894
0x18000e883  mov     r9, rbx
0x18000e886  xor     r8d, r8d
0x18000e889  mov     rdx, rdi
0x18000e88c  mov     rcx, rsi
0x18000e88f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e894  mov     rbx, [rsp+38h+arg_0]
0x18000e899  mov     rsi, [rsp+38h+arg_8]
0x18000e89e  add     rsp, 30h
0x18000e8a2  pop     rdi
0x18000e8a3  retn
```
