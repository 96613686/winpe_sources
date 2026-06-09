# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180039170`
- end: `0x1800391d5`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18003718c`

## callees

- `0x18000c6dc`
- `0x180039170`
- `0x18003f010`

## string_xrefs

- `0x180039194`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180039170  mov     [rsp+arg_0], rbx
0x180039175  mov     [rsp+arg_8], rsi
0x18003917a  push    rdi
0x18003917b  sub     rsp, 30h
0x18003917f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180039186  mov     rbx, r9
0x180039189  mov     rdi, rdx
0x18003918c  mov     rsi, rcx
0x18003918f  test    rax, rax
0x180039192  jnz     short loc_1800391B3
0x180039194  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18003919b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800391a0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800391a7  test    rax, rax
0x1800391aa  jnz     short loc_1800391B3
0x1800391ac  mov     eax, 0C0000139h
0x1800391b1  jmp     short loc_1800391C4
0x1800391b3  mov     r9, rbx
0x1800391b6  xor     r8d, r8d
0x1800391b9  mov     rdx, rdi
0x1800391bc  mov     rcx, rsi
0x1800391bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800391c4  mov     rbx, [rsp+38h+arg_0]
0x1800391c9  mov     rsi, [rsp+38h+arg_8]
0x1800391ce  add     rsp, 30h
0x1800391d2  pop     rdi
0x1800391d3  retn
```
