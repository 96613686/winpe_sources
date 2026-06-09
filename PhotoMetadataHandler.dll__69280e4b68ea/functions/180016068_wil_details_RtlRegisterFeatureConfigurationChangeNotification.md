# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180016068`
- end: `0x1800160cd`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800269a0`

## callees

- `0x180016068`
- `0x180027098`
- `0x180029010`

## string_xrefs

- `0x18001608c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180016068  mov     [rsp+arg_0], rbx
0x18001606d  mov     [rsp+arg_8], rsi
0x180016072  push    rdi
0x180016073  sub     rsp, 30h
0x180016077  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001607e  mov     rbx, r9
0x180016081  mov     rdi, rdx
0x180016084  mov     rsi, rcx
0x180016087  test    rax, rax
0x18001608a  jnz     short loc_1800160AB
0x18001608c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180016093  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180016098  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001609f  test    rax, rax
0x1800160a2  jnz     short loc_1800160AB
0x1800160a4  mov     eax, 0C0000139h
0x1800160a9  jmp     short loc_1800160BC
0x1800160ab  mov     r9, rbx
0x1800160ae  xor     r8d, r8d
0x1800160b1  mov     rdx, rdi
0x1800160b4  mov     rcx, rsi
0x1800160b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800160bc  mov     rbx, [rsp+38h+arg_0]
0x1800160c1  mov     rsi, [rsp+38h+arg_8]
0x1800160c6  add     rsp, 30h
0x1800160ca  pop     rdi
0x1800160cb  retn
```
