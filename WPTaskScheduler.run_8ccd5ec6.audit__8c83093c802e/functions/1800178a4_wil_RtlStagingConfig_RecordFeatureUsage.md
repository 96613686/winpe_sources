# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800178a4`
- end: `0x1800178fe`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180015ec0`

## callees

- `0x180016fd0`
- `0x1800178a4`
- `0x180022010`

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
0x1800178a4  mov     rax, rsp
0x1800178a7  sub     rsp, 28h
0x1800178ab  mov     qword ptr [rax+20h], 0
0x1800178b3  mov     [rax+20h], ecx
0x1800178b6  mov     [rax+24h], dx
0x1800178ba  test    r8d, r8d
0x1800178bd  jz      short loc_1800178C4
0x1800178bf  or      word ptr [rax+26h], 1
0x1800178c4  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800178cb  test    rax, rax
0x1800178ce  jnz     short loc_1800178EF
0x1800178d0  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800178d7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800178dc  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800178e3  test    rax, rax
0x1800178e6  jnz     short loc_1800178EF
0x1800178e8  mov     eax, 0C0000139h
0x1800178ed  jmp     short loc_1800178F9
0x1800178ef  lea     rcx, [rsp+28h+arg_18]
0x1800178f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800178f9  add     rsp, 28h
0x1800178fd  retn
```
