# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000d76c`
- end: `0x14000d7d0`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000cf50`

## callees

- `0x140005ed0`
- `0x14000d76c`
- `0x14002b010`

## string_xrefs

- `0x14000d790`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000d76c  mov     [rsp+arg_0], rbx
0x14000d771  mov     [rsp+arg_8], rsi
0x14000d776  push    rdi
0x14000d777  sub     rsp, 30h
0x14000d77b  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000d782  mov     rbx, r9
0x14000d785  mov     rdi, rdx
0x14000d788  mov     rsi, rcx
0x14000d78b  test    rax, rax
0x14000d78e  jnz     short loc_14000D7AF
0x14000d790  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000d797  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000d79c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000d7a3  test    rax, rax
0x14000d7a6  jnz     short loc_14000D7AF
0x14000d7a8  mov     eax, 0C0000139h
0x14000d7ad  jmp     short loc_14000D7C0
0x14000d7af  mov     r9, rbx
0x14000d7b2  xor     r8d, r8d
0x14000d7b5  mov     rdx, rdi
0x14000d7b8  mov     rcx, rsi
0x14000d7bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d7c0  mov     rbx, [rsp+38h+arg_0]
0x14000d7c5  mov     rsi, [rsp+38h+arg_8]
0x14000d7ca  add     rsp, 30h
0x14000d7ce  pop     rdi
0x14000d7cf  retn
```
