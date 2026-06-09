# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x14000b6ec`
- end: `0x14000b750`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000aaa0`

## callees

- `0x140005fd0`
- `0x14000b6ec`
- `0x14002b010`

## string_xrefs

- `0x14000b710`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x14000b6ec  mov     [rsp+arg_0], rbx
0x14000b6f1  mov     [rsp+arg_8], rsi
0x14000b6f6  push    rdi
0x14000b6f7  sub     rsp, 30h
0x14000b6fb  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14000b702  mov     rbx, r9
0x14000b705  mov     rdi, rdx
0x14000b708  mov     rsi, rcx
0x14000b70b  test    rax, rax
0x14000b70e  jnz     short loc_14000B72F
0x14000b710  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14000b717  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000b71c  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14000b723  test    rax, rax
0x14000b726  jnz     short loc_14000B72F
0x14000b728  mov     eax, 0C0000139h
0x14000b72d  jmp     short loc_14000B740
0x14000b72f  mov     r9, rbx
0x14000b732  xor     r8d, r8d
0x14000b735  mov     rdx, rdi
0x14000b738  mov     rcx, rsi
0x14000b73b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b740  mov     rbx, [rsp+38h+arg_0]
0x14000b745  mov     rsi, [rsp+38h+arg_8]
0x14000b74a  add     rsp, 30h
0x14000b74e  pop     rdi
0x14000b74f  retn
```
