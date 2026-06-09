# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1800570dc`
- end: `0x180057140`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180055984`

## callees

- `0x18005699c`
- `0x1800570dc`
- `0x180075010`

## string_xrefs

- `0x180057100`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800570dc  mov     [rsp+arg_0], rbx
0x1800570e1  mov     [rsp+arg_8], rsi
0x1800570e6  push    rdi
0x1800570e7  sub     rsp, 30h
0x1800570eb  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x1800570f2  mov     rbx, r9
0x1800570f5  mov     rdi, rdx
0x1800570f8  mov     rsi, rcx
0x1800570fb  test    rax, rax
0x1800570fe  jnz     short loc_18005711F
0x180057100  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180057107  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18005710c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180057113  test    rax, rax
0x180057116  jnz     short loc_18005711F
0x180057118  mov     eax, 0C0000139h
0x18005711d  jmp     short loc_180057130
0x18005711f  mov     r9, rbx
0x180057122  xor     r8d, r8d
0x180057125  mov     rdx, rdi
0x180057128  mov     rcx, rsi
0x18005712b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180057130  mov     rbx, [rsp+38h+arg_0]
0x180057135  mov     rsi, [rsp+38h+arg_8]
0x18005713a  add     rsp, 30h
0x18005713e  pop     rdi
0x18005713f  retn
```
