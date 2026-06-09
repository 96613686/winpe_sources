# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180012914`
- end: `0x180012979`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010f80`

## callees

- `0x180005940`
- `0x180012914`
- `0x18001e010`

## string_xrefs

- `0x180012938`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180012914  mov     [rsp+arg_0], rbx
0x180012919  mov     [rsp+arg_8], rsi
0x18001291e  push    rdi
0x18001291f  sub     rsp, 30h
0x180012923  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001292a  mov     rbx, r9
0x18001292d  mov     rdi, rdx
0x180012930  mov     rsi, rcx
0x180012933  test    rax, rax
0x180012936  jnz     short loc_180012957
0x180012938  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001293f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180012944  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001294b  test    rax, rax
0x18001294e  jnz     short loc_180012957
0x180012950  mov     eax, 0C0000139h
0x180012955  jmp     short loc_180012968
0x180012957  mov     r9, rbx
0x18001295a  xor     r8d, r8d
0x18001295d  mov     rdx, rdi
0x180012960  mov     rcx, rsi
0x180012963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012968  mov     rbx, [rsp+38h+arg_0]
0x18001296d  mov     rsi, [rsp+38h+arg_8]
0x180012972  add     rsp, 30h
0x180012976  pop     rdi
0x180012977  retn
```
