# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000c9bc`
- end: `0x14000ca20`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b5c0`

## callees

- `0x14000c630`
- `0x14000c9bc`
- `0x140017010`

## string_xrefs

- `0x14000c9e0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000c9bc  mov     [rsp+arg_0], rbx
0x14000c9c1  mov     [rsp+arg_8], rsi
0x14000c9c6  push    rdi
0x14000c9c7  sub     rsp, 30h
0x14000c9cb  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000c9d2  mov     rbx, r9
0x14000c9d5  mov     rdi, rdx
0x14000c9d8  mov     rsi, rcx
0x14000c9db  test    rax, rax
0x14000c9de  jnz     short loc_14000C9FF
0x14000c9e0  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000c9e7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000c9ec  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000c9f3  test    rax, rax
0x14000c9f6  jnz     short loc_14000C9FF
0x14000c9f8  mov     eax, 0C0000139h
0x14000c9fd  jmp     short loc_14000CA10
0x14000c9ff  mov     r9, rbx
0x14000ca02  xor     r8d, r8d
0x14000ca05  mov     rdx, rdi
0x14000ca08  mov     rcx, rsi
0x14000ca0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ca10  mov     rbx, [rsp+38h+arg_0]
0x14000ca15  mov     rsi, [rsp+38h+arg_8]
0x14000ca1a  add     rsp, 30h
0x14000ca1e  pop     rdi
0x14000ca1f  retn
```
