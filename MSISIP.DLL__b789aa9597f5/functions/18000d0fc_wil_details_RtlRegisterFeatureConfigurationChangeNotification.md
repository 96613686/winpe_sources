# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000d0fc`
- end: `0x18000d160`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800067b4`

## callees

- `0x18000cdec`
- `0x18000d0fc`
- `0x18000e010`

## string_xrefs

- `0x18000d120`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000d0fc  mov     [rsp+arg_0], rbx
0x18000d101  mov     [rsp+arg_8], rsi
0x18000d106  push    rdi
0x18000d107  sub     rsp, 30h
0x18000d10b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000d112  mov     rbx, r9
0x18000d115  mov     rdi, rdx
0x18000d118  mov     rsi, rcx
0x18000d11b  test    rax, rax
0x18000d11e  jnz     short loc_18000D13F
0x18000d120  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000d127  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d12c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000d133  test    rax, rax
0x18000d136  jnz     short loc_18000D13F
0x18000d138  mov     eax, 0C0000139h
0x18000d13d  jmp     short loc_18000D150
0x18000d13f  mov     r9, rbx
0x18000d142  xor     r8d, r8d
0x18000d145  mov     rdx, rdi
0x18000d148  mov     rcx, rsi
0x18000d14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d150  mov     rbx, [rsp+38h+arg_0]
0x18000d155  mov     rsi, [rsp+38h+arg_8]
0x18000d15a  add     rsp, 30h
0x18000d15e  pop     rdi
0x18000d15f  retn
```
