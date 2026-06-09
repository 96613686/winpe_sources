# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14001ceac`
- end: `0x14001cf10`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140017680`

## callees

- `0x14001bce4`
- `0x14001ceac`
- `0x14001f010`

## string_xrefs

- `0x14001ced0`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14001ceac  mov     [rsp+arg_0], rbx
0x14001ceb1  mov     [rsp+arg_8], rsi
0x14001ceb6  push    rdi
0x14001ceb7  sub     rsp, 30h
0x14001cebb  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14001cec2  mov     rbx, r9
0x14001cec5  mov     rdi, rdx
0x14001cec8  mov     rsi, rcx
0x14001cecb  test    rax, rax
0x14001cece  jnz     short loc_14001CEEF
0x14001ced0  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001ced7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14001cedc  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14001cee3  test    rax, rax
0x14001cee6  jnz     short loc_14001CEEF
0x14001cee8  mov     eax, 0C0000139h
0x14001ceed  jmp     short loc_14001CF00
0x14001ceef  mov     r9, rbx
0x14001cef2  xor     r8d, r8d
0x14001cef5  mov     rdx, rdi
0x14001cef8  mov     rcx, rsi
0x14001cefb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cf00  mov     rbx, [rsp+38h+arg_0]
0x14001cf05  mov     rsi, [rsp+38h+arg_8]
0x14001cf0a  add     rsp, 30h
0x14001cf0e  pop     rdi
0x14001cf0f  retn
```
