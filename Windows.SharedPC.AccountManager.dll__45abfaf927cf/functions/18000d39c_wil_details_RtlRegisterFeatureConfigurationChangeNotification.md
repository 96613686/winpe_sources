# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000d39c`
- end: `0x18000d400`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ca80`

## callees

- `0x180005cd0`
- `0x18000d39c`
- `0x180026010`

## string_xrefs

- `0x18000d3c0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000d39c  mov     [rsp+arg_0], rbx
0x18000d3a1  mov     [rsp+arg_8], rsi
0x18000d3a6  push    rdi
0x18000d3a7  sub     rsp, 30h
0x18000d3ab  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000d3b2  mov     rbx, r9
0x18000d3b5  mov     rdi, rdx
0x18000d3b8  mov     rsi, rcx
0x18000d3bb  test    rax, rax
0x18000d3be  jnz     short loc_18000D3DF
0x18000d3c0  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000d3c7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d3cc  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000d3d3  test    rax, rax
0x18000d3d6  jnz     short loc_18000D3DF
0x18000d3d8  mov     eax, 0C0000139h
0x18000d3dd  jmp     short loc_18000D3F0
0x18000d3df  mov     r9, rbx
0x18000d3e2  xor     r8d, r8d
0x18000d3e5  mov     rdx, rdi
0x18000d3e8  mov     rcx, rsi
0x18000d3eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d3f0  mov     rbx, [rsp+38h+arg_0]
0x18000d3f5  mov     rsi, [rsp+38h+arg_8]
0x18000d3fa  add     rsp, 30h
0x18000d3fe  pop     rdi
0x18000d3ff  retn
```
