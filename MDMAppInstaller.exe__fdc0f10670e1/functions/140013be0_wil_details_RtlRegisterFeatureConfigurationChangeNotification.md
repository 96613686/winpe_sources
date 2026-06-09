# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x140013be0`
- end: `0x140013c44`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140011340`

## callees

- `0x140006bd0`
- `0x140013be0`
- `0x14001c010`

## string_xrefs

- `0x140013c04`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140013be0  mov     [rsp+arg_0], rbx
0x140013be5  mov     [rsp+arg_8], rsi
0x140013bea  push    rdi
0x140013beb  sub     rsp, 30h
0x140013bef  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x140013bf6  mov     rbx, r9
0x140013bf9  mov     rdi, rdx
0x140013bfc  mov     rsi, rcx
0x140013bff  test    rax, rax
0x140013c02  jnz     short loc_140013C23
0x140013c04  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x140013c0b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140013c10  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x140013c17  test    rax, rax
0x140013c1a  jnz     short loc_140013C23
0x140013c1c  mov     eax, 0C0000139h
0x140013c21  jmp     short loc_140013C34
0x140013c23  mov     r9, rbx
0x140013c26  xor     r8d, r8d
0x140013c29  mov     rdx, rdi
0x140013c2c  mov     rcx, rsi
0x140013c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013c34  mov     rbx, [rsp+38h+arg_0]
0x140013c39  mov     rsi, [rsp+38h+arg_8]
0x140013c3e  add     rsp, 30h
0x140013c42  pop     rdi
0x140013c43  retn
```
