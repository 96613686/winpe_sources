# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000d568`
- end: `0x18000d5cc`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c154`

## callees

- `0x18000d170`
- `0x18000d568`
- `0x18001f010`

## string_xrefs

- `0x18000d58c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000d568  mov     [rsp+arg_0], rbx
0x18000d56d  mov     [rsp+arg_8], rsi
0x18000d572  push    rdi
0x18000d573  sub     rsp, 30h
0x18000d577  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000d57e  mov     rbx, r9
0x18000d581  mov     rdi, rdx
0x18000d584  mov     rsi, rcx
0x18000d587  test    rax, rax
0x18000d58a  jnz     short loc_18000D5AB
0x18000d58c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000d593  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000d598  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000d59f  test    rax, rax
0x18000d5a2  jnz     short loc_18000D5AB
0x18000d5a4  mov     eax, 0C0000139h
0x18000d5a9  jmp     short loc_18000D5BC
0x18000d5ab  mov     r9, rbx
0x18000d5ae  xor     r8d, r8d
0x18000d5b1  mov     rdx, rdi
0x18000d5b4  mov     rcx, rsi
0x18000d5b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d5bc  mov     rbx, [rsp+38h+arg_0]
0x18000d5c1  mov     rsi, [rsp+38h+arg_8]
0x18000d5c6  add     rsp, 30h
0x18000d5ca  pop     rdi
0x18000d5cb  retn
```
