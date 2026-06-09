# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000f1d0`
- end: `0x18000f234`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000d988`

## callees

- `0x18000eb20`
- `0x18000f1d0`
- `0x18002a010`

## string_xrefs

- `0x18000f1f4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000f1d0  mov     [rsp+arg_0], rbx
0x18000f1d5  mov     [rsp+arg_8], rsi
0x18000f1da  push    rdi
0x18000f1db  sub     rsp, 30h
0x18000f1df  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000f1e6  mov     rbx, r9
0x18000f1e9  mov     rdi, rdx
0x18000f1ec  mov     rsi, rcx
0x18000f1ef  test    rax, rax
0x18000f1f2  jnz     short loc_18000F213
0x18000f1f4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000f1fb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f200  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000f207  test    rax, rax
0x18000f20a  jnz     short loc_18000F213
0x18000f20c  mov     eax, 0C0000139h
0x18000f211  jmp     short loc_18000F224
0x18000f213  mov     r9, rbx
0x18000f216  xor     r8d, r8d
0x18000f219  mov     rdx, rdi
0x18000f21c  mov     rcx, rsi
0x18000f21f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f224  mov     rbx, [rsp+38h+arg_0]
0x18000f229  mov     rsi, [rsp+38h+arg_8]
0x18000f22e  add     rsp, 30h
0x18000f232  pop     rdi
0x18000f233  retn
```
