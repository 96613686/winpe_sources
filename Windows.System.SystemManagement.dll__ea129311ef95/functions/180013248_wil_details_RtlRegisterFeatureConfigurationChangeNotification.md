# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180013248`
- end: `0x1800132ac`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180012860`

## callees

- `0x180009b20`
- `0x180013248`
- `0x18002b010`

## string_xrefs

- `0x18001326c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180013248  mov     [rsp+arg_0], rbx
0x18001324d  mov     [rsp+arg_8], rsi
0x180013252  push    rdi
0x180013253  sub     rsp, 30h
0x180013257  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001325e  mov     rbx, r9
0x180013261  mov     rdi, rdx
0x180013264  mov     rsi, rcx
0x180013267  test    rax, rax
0x18001326a  jnz     short loc_18001328B
0x18001326c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180013273  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013278  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001327f  test    rax, rax
0x180013282  jnz     short loc_18001328B
0x180013284  mov     eax, 0C0000139h
0x180013289  jmp     short loc_18001329C
0x18001328b  mov     r9, rbx
0x18001328e  xor     r8d, r8d
0x180013291  mov     rdx, rdi
0x180013294  mov     rcx, rsi
0x180013297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001329c  mov     rbx, [rsp+38h+arg_0]
0x1800132a1  mov     rsi, [rsp+38h+arg_8]
0x1800132a6  add     rsp, 30h
0x1800132aa  pop     rdi
0x1800132ab  retn
```
