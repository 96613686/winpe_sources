# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18004fb50`
- end: `0x18004fbb4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18004dcd8`

## callees

- `0x180046ad0`
- `0x18004fb50`
- `0x1800a8010`

## string_xrefs

- `0x18004fb74`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18004fb50  mov     [rsp+arg_0], rbx
0x18004fb55  mov     [rsp+arg_8], rsi
0x18004fb5a  push    rdi
0x18004fb5b  sub     rsp, 30h
0x18004fb5f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18004fb66  mov     rbx, r9
0x18004fb69  mov     rdi, rdx
0x18004fb6c  mov     rsi, rcx
0x18004fb6f  test    rax, rax
0x18004fb72  jnz     short loc_18004FB93
0x18004fb74  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18004fb7b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18004fb80  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18004fb87  test    rax, rax
0x18004fb8a  jnz     short loc_18004FB93
0x18004fb8c  mov     eax, 0C0000139h
0x18004fb91  jmp     short loc_18004FBA4
0x18004fb93  mov     r9, rbx
0x18004fb96  xor     r8d, r8d
0x18004fb99  mov     rdx, rdi
0x18004fb9c  mov     rcx, rsi
0x18004fb9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004fba4  mov     rbx, [rsp+38h+arg_0]
0x18004fba9  mov     rsi, [rsp+38h+arg_8]
0x18004fbae  add     rsp, 30h
0x18004fbb2  pop     rdi
0x18004fbb3  retn
```
