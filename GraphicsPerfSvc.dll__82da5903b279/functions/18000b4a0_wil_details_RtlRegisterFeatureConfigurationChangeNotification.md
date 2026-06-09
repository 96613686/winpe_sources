# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000b4a0`
- end: `0x18000b504`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a270`

## callees

- `0x18000adb0`
- `0x18000b4a0`
- `0x180031010`

## string_xrefs

- `0x18000b4c4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b4a0  mov     [rsp+arg_0], rbx
0x18000b4a5  mov     [rsp+arg_8], rsi
0x18000b4aa  push    rdi
0x18000b4ab  sub     rsp, 30h
0x18000b4af  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b4b6  mov     rbx, r9
0x18000b4b9  mov     rdi, rdx
0x18000b4bc  mov     rsi, rcx
0x18000b4bf  test    rax, rax
0x18000b4c2  jnz     short loc_18000B4E3
0x18000b4c4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b4cb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b4d0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b4d7  test    rax, rax
0x18000b4da  jnz     short loc_18000B4E3
0x18000b4dc  mov     eax, 0C0000139h
0x18000b4e1  jmp     short loc_18000B4F4
0x18000b4e3  mov     r9, rbx
0x18000b4e6  xor     r8d, r8d
0x18000b4e9  mov     rdx, rdi
0x18000b4ec  mov     rcx, rsi
0x18000b4ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4f4  mov     rbx, [rsp+38h+arg_0]
0x18000b4f9  mov     rsi, [rsp+38h+arg_8]
0x18000b4fe  add     rsp, 30h
0x18000b502  pop     rdi
0x18000b503  retn
```
