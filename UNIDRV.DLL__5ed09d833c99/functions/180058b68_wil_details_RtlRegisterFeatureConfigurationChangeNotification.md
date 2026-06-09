# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180058b68`
- end: `0x180058bcd`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: `__int64 __fastcall(__int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180057474`

## callees

- `0x18005840c`
- `0x180058b68`
- `0x180077010`

## string_xrefs

- `0x180058b8c`: `RtlRegisterFeatureConfigurationChangeNotification`

## pseudocode

```c
__int64 __fastcall wil_details_RtlRegisterFeatureConfigurationChangeNotification(
        __int64 a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  FARPROC NtDllProcedureAddress; // rax

  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification;
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
0x180058b68  mov     [rsp+arg_0], rbx
0x180058b6d  mov     [rsp+arg_8], rsi
0x180058b72  push    rdi
0x180058b73  sub     rsp, 30h
0x180058b77  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x180058b7e  mov     rbx, r9
0x180058b81  mov     rdi, rdx
0x180058b84  mov     rsi, rcx
0x180058b87  test    rax, rax
0x180058b8a  jnz     short loc_180058BAB
0x180058b8c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180058b93  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180058b98  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x180058b9f  test    rax, rax
0x180058ba2  jnz     short loc_180058BAB
0x180058ba4  mov     eax, 0C0000139h
0x180058ba9  jmp     short loc_180058BBC
0x180058bab  mov     r9, rbx
0x180058bae  xor     r8d, r8d
0x180058bb1  mov     rdx, rdi
0x180058bb4  mov     rcx, rsi
0x180058bb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bbc  mov     rbx, [rsp+38h+arg_0]
0x180058bc1  mov     rsi, [rsp+38h+arg_8]
0x180058bc6  add     rsp, 30h
0x180058bca  pop     rdi
0x180058bcb  retn
```
