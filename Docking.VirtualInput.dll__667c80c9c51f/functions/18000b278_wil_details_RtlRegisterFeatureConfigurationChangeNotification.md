# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18000b278`
- end: `0x18000b2dc`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a34c`

## callees

- `0x1800076b0`
- `0x18000b278`
- `0x18001c010`

## string_xrefs

- `0x18000b29c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18000b278  mov     [rsp+arg_0], rbx
0x18000b27d  mov     [rsp+arg_8], rsi
0x18000b282  push    rdi
0x18000b283  sub     rsp, 30h
0x18000b287  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18000b28e  mov     rbx, r9
0x18000b291  mov     rdi, rdx
0x18000b294  mov     rsi, rcx
0x18000b297  test    rax, rax
0x18000b29a  jnz     short loc_18000B2BB
0x18000b29c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18000b2a3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b2a8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18000b2af  test    rax, rax
0x18000b2b2  jnz     short loc_18000B2BB
0x18000b2b4  mov     eax, 0C0000139h
0x18000b2b9  jmp     short loc_18000B2CC
0x18000b2bb  mov     r9, rbx
0x18000b2be  xor     r8d, r8d
0x18000b2c1  mov     rdx, rdi
0x18000b2c4  mov     rcx, rsi
0x18000b2c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2cc  mov     rbx, [rsp+38h+arg_0]
0x18000b2d1  mov     rsi, [rsp+38h+arg_8]
0x18000b2d6  add     rsp, 30h
0x18000b2da  pop     rdi
0x18000b2db  retn
```
