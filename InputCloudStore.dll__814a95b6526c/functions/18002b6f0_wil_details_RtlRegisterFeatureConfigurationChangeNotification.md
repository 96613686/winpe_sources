# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18002b6f0`
- end: `0x18002b754`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18002af00`

## callees

- `0x180007aa0`
- `0x18002b6f0`
- `0x180031010`

## string_xrefs

- `0x18002b714`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18002b6f0  mov     [rsp+arg_0], rbx
0x18002b6f5  mov     [rsp+arg_8], rsi
0x18002b6fa  push    rdi
0x18002b6fb  sub     rsp, 30h
0x18002b6ff  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18002b706  mov     rbx, r9
0x18002b709  mov     rdi, rdx
0x18002b70c  mov     rsi, rcx
0x18002b70f  test    rax, rax
0x18002b712  jnz     short loc_18002B733
0x18002b714  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18002b71b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18002b720  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18002b727  test    rax, rax
0x18002b72a  jnz     short loc_18002B733
0x18002b72c  mov     eax, 0C0000139h
0x18002b731  jmp     short loc_18002B744
0x18002b733  mov     r9, rbx
0x18002b736  xor     r8d, r8d
0x18002b739  mov     rdx, rdi
0x18002b73c  mov     rcx, rsi
0x18002b73f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b744  mov     rbx, [rsp+38h+arg_0]
0x18002b749  mov     rsi, [rsp+38h+arg_8]
0x18002b74e  add     rsp, 30h
0x18002b752  pop     rdi
0x18002b753  retn
```
