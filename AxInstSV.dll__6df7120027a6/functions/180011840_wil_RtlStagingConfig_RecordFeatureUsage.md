# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180011840`
- end: `0x18001189a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180010ae0`

## callees

- `0x180011540`
- `0x180011840`
- `0x180015010`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, __int16 a2, int a3)
{
  FARPROC NtDllProcedureAddress; // rax
  int v5; // [rsp+48h] [rbp+20h] BYREF
  __int16 v6; // [rsp+4Ch] [rbp+24h]
  __int16 v7; // [rsp+4Eh] [rbp+26h]

  v7 = 0;
  v5 = a1;
  v6 = a2;
  if ( a3 )
    v7 |= 1u;
  NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
  if ( g_wil_details_pfnRtlNotifyFeatureUsage )
    return ((__int64 (__fastcall *)(int *))NtDllProcedureAddress)(&v5);
  NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage");
  g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress;
  if ( NtDllProcedureAddress )
    return ((__int64 (__fastcall *)(int *))NtDllProcedureAddress)(&v5);
  else
    return 3221225785LL;
}

```

## disassembly

```asm
0x180011840  mov     rax, rsp
0x180011843  sub     rsp, 28h
0x180011847  mov     qword ptr [rax+20h], 0
0x18001184f  mov     [rax+20h], ecx
0x180011852  mov     [rax+24h], dx
0x180011856  test    r8d, r8d
0x180011859  jz      short loc_180011860
0x18001185b  or      word ptr [rax+26h], 1
0x180011860  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180011867  test    rax, rax
0x18001186a  jnz     short loc_18001188B
0x18001186c  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180011873  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180011878  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001187f  test    rax, rax
0x180011882  jnz     short loc_18001188B
0x180011884  mov     eax, 0C0000139h
0x180011889  jmp     short loc_180011895
0x18001188b  lea     rcx, [rsp+28h+arg_18]
0x180011890  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011895  add     rsp, 28h
0x180011899  retn
```
