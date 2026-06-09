# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180069df8`
- end: `0x180069e5c`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800686b4`

## callees

- `0x18004088c`
- `0x180069df8`
- `0x1800b0010`

## string_xrefs

- `0x180069e1c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180069df8  mov     [rsp+arg_0], rbx
0x180069dfd  mov     [rsp+arg_8], rsi
0x180069e02  push    rdi
0x180069e03  sub     rsp, 30h
0x180069e07  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180069e0e  mov     rbx, r9
0x180069e11  mov     rdi, rdx
0x180069e14  mov     rsi, rcx
0x180069e17  test    rax, rax
0x180069e1a  jnz     short loc_180069E3B
0x180069e1c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180069e23  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180069e28  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180069e2f  test    rax, rax
0x180069e32  jnz     short loc_180069E3B
0x180069e34  mov     eax, 0C0000139h
0x180069e39  jmp     short loc_180069E4C
0x180069e3b  mov     r9, rbx
0x180069e3e  xor     r8d, r8d
0x180069e41  mov     rdx, rdi
0x180069e44  mov     rcx, rsi
0x180069e47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180069e4c  mov     rbx, [rsp+38h+arg_0]
0x180069e51  mov     rsi, [rsp+38h+arg_8]
0x180069e56  add     rsp, 30h
0x180069e5a  pop     rdi
0x180069e5b  retn
```
