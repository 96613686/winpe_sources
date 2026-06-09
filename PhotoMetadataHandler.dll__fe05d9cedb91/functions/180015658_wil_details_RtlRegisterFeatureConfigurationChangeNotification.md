# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x180015658`
- end: `0x1800156bc`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `100`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180025770`

## callees

- `0x180015658`
- `0x180025e58`
- `0x180028010`

## string_xrefs

- `0x18001567c`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x180015658  mov     [rsp+arg_0], rbx
0x18001565d  mov     [rsp+arg_8], rsi
0x180015662  push    rdi
0x180015663  sub     rsp, 30h
0x180015667  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x18001566e  mov     rbx, r9
0x180015671  mov     rdi, rdx
0x180015674  mov     rsi, rcx
0x180015677  test    rax, rax
0x18001567a  jnz     short loc_18001569B
0x18001567c  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x180015683  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180015688  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x18001568f  test    rax, rax
0x180015692  jnz     short loc_18001569B
0x180015694  mov     eax, 0C0000139h
0x180015699  jmp     short loc_1800156AC
0x18001569b  mov     r9, rbx
0x18001569e  xor     r8d, r8d
0x1800156a1  mov     rdx, rdi
0x1800156a4  mov     rcx, rsi
0x1800156a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156ac  mov     rbx, [rsp+38h+arg_0]
0x1800156b1  mov     rsi, [rsp+38h+arg_8]
0x1800156b6  add     rsp, 30h
0x1800156ba  pop     rdi
0x1800156bb  retn
```
