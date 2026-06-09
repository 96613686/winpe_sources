# wil_details_RtlRegisterFeatureConfigurationChangeNotification

- ea: `0x140012624`
- end: `0x140012689`
- name: `wil_details_RtlRegisterFeatureConfigurationChangeNotification`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400117b0`

## callees

- `0x1400081c8`
- `0x140012624`
- `0x14001a010`

## string_xrefs

- `0x140012648`: `RtlRegisterFeatureConfigurationChangeNotification`

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
0x140012624  mov     [rsp+arg_0], rbx
0x140012629  mov     [rsp+arg_8], rsi
0x14001262e  push    rdi
0x14001262f  sub     rsp, 30h
0x140012633  mov     rax, cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification
0x14001263a  mov     rbx, r9
0x14001263d  mov     rdi, rdx
0x140012640  mov     rsi, rcx
0x140012643  test    rax, rax
0x140012646  jnz     short loc_140012667
0x140012648  lea     rcx, aRtlregisterfea; "RtlRegisterFeatureConfigurationChangeNo"...
0x14001264f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140012654  mov     cs:g_wil_details_pfnRtlRegisterFeatureConfigurationChangeNotification, rax
0x14001265b  test    rax, rax
0x14001265e  jnz     short loc_140012667
0x140012660  mov     eax, 0C0000139h
0x140012665  jmp     short loc_140012678
0x140012667  mov     r9, rbx
0x14001266a  xor     r8d, r8d
0x14001266d  mov     rdx, rdi
0x140012670  mov     rcx, rsi
0x140012673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012678  mov     rbx, [rsp+38h+arg_0]
0x14001267d  mov     rsi, [rsp+38h+arg_8]
0x140012682  add     rsp, 30h
0x140012686  pop     rdi
0x140012687  retn
```
