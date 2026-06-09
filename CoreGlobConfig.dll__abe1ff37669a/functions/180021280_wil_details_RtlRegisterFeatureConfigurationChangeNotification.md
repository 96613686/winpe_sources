# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180021280`
- end: `0x1800212e4`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001ba60`

## callees

- `0x1800092d0`
- `0x180021280`
- `0x180025010`

## string_xrefs

- `0x1800212a4`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180021280  mov     [rsp+arg_0], rbx
0x180021285  mov     [rsp+arg_8], rsi
0x18002128a  push    rdi
0x18002128b  sub     rsp, 30h
0x18002128f  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180021296  mov     rbx, r9
0x180021299  mov     rdi, rdx
0x18002129c  mov     rsi, rcx
0x18002129f  test    rax, rax
0x1800212a2  jnz     short loc_1800212C3
0x1800212a4  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x1800212ab  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800212b0  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x1800212b7  test    rax, rax
0x1800212ba  jnz     short loc_1800212C3
0x1800212bc  mov     eax, 0C0000139h
0x1800212c1  jmp     short loc_1800212D4
0x1800212c3  mov     r9, rbx
0x1800212c6  xor     r8d, r8d
0x1800212c9  mov     rdx, rdi
0x1800212cc  mov     rcx, rsi
0x1800212cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800212d4  mov     rbx, [rsp+38h+arg_0]
0x1800212d9  mov     rsi, [rsp+38h+arg_8]
0x1800212de  add     rsp, 30h
0x1800212e2  pop     rdi
0x1800212e3  retn
```
