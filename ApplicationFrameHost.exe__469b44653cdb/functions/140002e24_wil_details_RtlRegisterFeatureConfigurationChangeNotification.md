# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x140002e24`
- end: `0x140002e88`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400091d0`

## callees

- `0x140002e24`
- `0x140009ba0`
- `0x14000b010`

## string_xrefs

- `0x140002e48`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140002e24  mov     [rsp+arg_0], rbx
0x140002e29  mov     [rsp+arg_8], rsi
0x140002e2e  push    rdi
0x140002e2f  sub     rsp, 30h
0x140002e33  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140002e3a  mov     rbx, r9
0x140002e3d  mov     rdi, rdx
0x140002e40  mov     rsi, rcx
0x140002e43  test    rax, rax
0x140002e46  jnz     short loc_140002E67
0x140002e48  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140002e4f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140002e54  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140002e5b  test    rax, rax
0x140002e5e  jnz     short loc_140002E67
0x140002e60  mov     eax, 0C0000139h
0x140002e65  jmp     short loc_140002E78
0x140002e67  mov     r9, rbx
0x140002e6a  xor     r8d, r8d
0x140002e6d  mov     rdx, rdi
0x140002e70  mov     rcx, rsi
0x140002e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002e78  mov     rbx, [rsp+38h+arg_0]
0x140002e7d  mov     rsi, [rsp+38h+arg_8]
0x140002e82  add     rsp, 30h
0x140002e86  pop     rdi
0x140002e87  retn
```
