# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x18001c1b8`
- end: `0x18001c21c`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180027ee0`

## callees

- `0x18001c1b8`
- `0x1800288a0`
- `0x180037010`

## string_xrefs

- `0x18001c1dc`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x18001c1b8  mov     [rsp+arg_0], rbx
0x18001c1bd  mov     [rsp+arg_8], rsi
0x18001c1c2  push    rdi
0x18001c1c3  sub     rsp, 30h
0x18001c1c7  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001c1ce  mov     rbx, r9
0x18001c1d1  mov     rdi, rdx
0x18001c1d4  mov     rsi, rcx
0x18001c1d7  test    rax, rax
0x18001c1da  jnz     short loc_18001C1FB
0x18001c1dc  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x18001c1e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001c1e8  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001c1ef  test    rax, rax
0x18001c1f2  jnz     short loc_18001C1FB
0x18001c1f4  mov     eax, 0C0000139h
0x18001c1f9  jmp     short loc_18001C20C
0x18001c1fb  mov     r9, rbx
0x18001c1fe  xor     r8d, r8d
0x18001c201  mov     rdx, rdi
0x18001c204  mov     rcx, rsi
0x18001c207  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c20c  mov     rbx, [rsp+38h+arg_0]
0x18001c211  mov     rsi, [rsp+38h+arg_8]
0x18001c216  add     rsp, 30h
0x18001c21a  pop     rdi
0x18001c21b  retn
```
