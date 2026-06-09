# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x140009e28`
- end: `0x140009e82`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140009150`

## callees

- `0x140009ba0`
- `0x140009e28`
- `0x14000b010`

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
0x140009e28  mov     rax, rsp
0x140009e2b  sub     rsp, 28h
0x140009e2f  mov     qword ptr [rax+20h], 0
0x140009e37  mov     [rax+20h], ecx
0x140009e3a  mov     [rax+24h], dx
0x140009e3e  test    r8d, r8d
0x140009e41  jz      short loc_140009E48
0x140009e43  or      word ptr [rax+26h], 1
0x140009e48  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140009e4f  test    rax, rax
0x140009e52  jnz     short loc_140009E73
0x140009e54  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140009e5b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140009e60  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140009e67  test    rax, rax
0x140009e6a  jnz     short loc_140009E73
0x140009e6c  mov     eax, 0C0000139h
0x140009e71  jmp     short loc_140009E7D
0x140009e73  lea     rcx, [rsp+28h+arg_18]
0x140009e78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009e7d  add     rsp, 28h
0x140009e81  retn
```
