# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001e4f0`
- end: `0x18001e554`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001d9b8`

## callees

- `0x180016490`
- `0x18001e4f0`
- `0x180025010`

## string_xrefs

- `0x18001e514`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001e4f0  mov     [rsp+arg_0], rbx
0x18001e4f5  mov     [rsp+arg_8], rsi
0x18001e4fa  push    rdi
0x18001e4fb  sub     rsp, 30h
0x18001e4ff  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001e506  mov     rbx, r9
0x18001e509  mov     rdi, rdx
0x18001e50c  mov     rsi, rcx
0x18001e50f  test    rax, rax
0x18001e512  jnz     short loc_18001E533
0x18001e514  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001e51b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e520  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001e527  test    rax, rax
0x18001e52a  jnz     short loc_18001E533
0x18001e52c  mov     eax, 0C0000139h
0x18001e531  jmp     short loc_18001E544
0x18001e533  mov     r9, rbx
0x18001e536  xor     r8d, r8d
0x18001e539  mov     rdx, rdi
0x18001e53c  mov     rcx, rsi
0x18001e53f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e544  mov     rbx, [rsp+38h+arg_0]
0x18001e549  mov     rsi, [rsp+38h+arg_8]
0x18001e54e  add     rsp, 30h
0x18001e552  pop     rdi
0x18001e553  retn
```
