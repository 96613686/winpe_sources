# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000b660`
- end: `0x18000b6c4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180009a48`

## callees

- `0x18000af90`
- `0x18000b660`
- `0x180022010`

## string_xrefs

- `0x18000b684`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b660  mov     [rsp+arg_0], rbx
0x18000b665  mov     [rsp+arg_8], rsi
0x18000b66a  push    rdi
0x18000b66b  sub     rsp, 30h
0x18000b66f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b676  mov     rbx, r9
0x18000b679  mov     rdi, rdx
0x18000b67c  mov     rsi, rcx
0x18000b67f  test    rax, rax
0x18000b682  jnz     short loc_18000B6A3
0x18000b684  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b68b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b690  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b697  test    rax, rax
0x18000b69a  jnz     short loc_18000B6A3
0x18000b69c  mov     eax, 0C0000139h
0x18000b6a1  jmp     short loc_18000B6B4
0x18000b6a3  mov     r9, rbx
0x18000b6a6  xor     r8d, r8d
0x18000b6a9  mov     rdx, rdi
0x18000b6ac  mov     rcx, rsi
0x18000b6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6b4  mov     rbx, [rsp+38h+arg_0]
0x18000b6b9  mov     rsi, [rsp+38h+arg_8]
0x18000b6be  add     rsp, 30h
0x18000b6c2  pop     rdi
0x18000b6c3  retn
```
