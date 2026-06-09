# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180017a08`
- end: `0x180017a6c`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180015084`

## callees

- `0x180016fd0`
- `0x180017a08`
- `0x180022010`

## string_xrefs

- `0x180017a2c`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC NtDllProcedureAddress; // rax

  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
0x180017a08  mov     [rsp+arg_0], rbx
0x180017a0d  mov     [rsp+arg_8], rsi
0x180017a12  push    rdi
0x180017a13  sub     rsp, 30h
0x180017a17  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180017a1e  mov     rbx, r9
0x180017a21  mov     rdi, rdx
0x180017a24  mov     rsi, rcx
0x180017a27  test    rax, rax
0x180017a2a  jnz     short loc_180017A4B
0x180017a2c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180017a33  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180017a38  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180017a3f  test    rax, rax
0x180017a42  jnz     short loc_180017A4B
0x180017a44  mov     eax, 0C0000139h
0x180017a49  jmp     short loc_180017A5C
0x180017a4b  mov     r9, rbx
0x180017a4e  xor     r8d, r8d
0x180017a51  mov     rdx, rdi
0x180017a54  mov     rcx, rsi
0x180017a57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017a5c  mov     rbx, [rsp+38h+arg_0]
0x180017a61  mov     rsi, [rsp+38h+arg_8]
0x180017a66  add     rsp, 30h
0x180017a6a  pop     rdi
0x180017a6b  retn
```
