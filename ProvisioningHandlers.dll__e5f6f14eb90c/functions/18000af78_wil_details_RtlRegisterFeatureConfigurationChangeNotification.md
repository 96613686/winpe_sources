# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000af78`
- end: `0x18000afdd`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800090c4`

## callees

- `0x18000a920`
- `0x18000af78`
- `0x18002c010`

## string_xrefs

- `0x18000af9c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000af78  mov     [rsp+arg_0], rbx
0x18000af7d  mov     [rsp+arg_8], rsi
0x18000af82  push    rdi
0x18000af83  sub     rsp, 30h
0x18000af87  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000af8e  mov     rbx, r9
0x18000af91  mov     rdi, rdx
0x18000af94  mov     rsi, rcx
0x18000af97  test    rax, rax
0x18000af9a  jnz     short loc_18000AFBB
0x18000af9c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000afa3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000afa8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000afaf  test    rax, rax
0x18000afb2  jnz     short loc_18000AFBB
0x18000afb4  mov     eax, 0C0000139h
0x18000afb9  jmp     short loc_18000AFCC
0x18000afbb  mov     r9, rbx
0x18000afbe  xor     r8d, r8d
0x18000afc1  mov     rdx, rdi
0x18000afc4  mov     rcx, rsi
0x18000afc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afcc  mov     rbx, [rsp+38h+arg_0]
0x18000afd1  mov     rsi, [rsp+38h+arg_8]
0x18000afd6  add     rsp, 30h
0x18000afda  pop     rdi
0x18000afdb  retn
```
