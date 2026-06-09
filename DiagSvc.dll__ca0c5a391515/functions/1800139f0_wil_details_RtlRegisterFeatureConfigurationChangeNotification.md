# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x1800139f0`
- end: `0x180013a54`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011534`

## callees

- `0x180012ff0`
- `0x1800139f0`
- `0x180027010`

## string_xrefs

- `0x180013a14`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x1800139f0  mov     [rsp+arg_0], rbx
0x1800139f5  mov     [rsp+arg_8], rsi
0x1800139fa  push    rdi
0x1800139fb  sub     rsp, 30h
0x1800139ff  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180013a06  mov     rbx, r9
0x180013a09  mov     rdi, rdx
0x180013a0c  mov     rsi, rcx
0x180013a0f  test    rax, rax
0x180013a12  jnz     short loc_180013A33
0x180013a14  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180013a1b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013a20  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180013a27  test    rax, rax
0x180013a2a  jnz     short loc_180013A33
0x180013a2c  mov     eax, 0C0000139h
0x180013a31  jmp     short loc_180013A44
0x180013a33  mov     r9, rbx
0x180013a36  xor     r8d, r8d
0x180013a39  mov     rdx, rdi
0x180013a3c  mov     rcx, rsi
0x180013a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a44  mov     rbx, [rsp+38h+arg_0]
0x180013a49  mov     rsi, [rsp+38h+arg_8]
0x180013a4e  add     rsp, 30h
0x180013a52  pop     rdi
0x180013a53  retn
```
