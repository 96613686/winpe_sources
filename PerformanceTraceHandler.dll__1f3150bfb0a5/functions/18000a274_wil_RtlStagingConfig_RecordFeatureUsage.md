# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000a274`
- end: `0x18000a2ce`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180008f30`

## callees

- `0x180009e80`
- `0x18000a274`
- `0x18001c010`

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
0x18000a274  mov     rax, rsp
0x18000a277  sub     rsp, 28h
0x18000a27b  mov     qword ptr [rax+20h], 0
0x18000a283  mov     [rax+20h], ecx
0x18000a286  mov     [rax+24h], dx
0x18000a28a  test    r8d, r8d
0x18000a28d  jz      short loc_18000A294
0x18000a28f  or      word ptr [rax+26h], 1
0x18000a294  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000a29b  test    rax, rax
0x18000a29e  jnz     short loc_18000A2BF
0x18000a2a0  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000a2a7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000a2ac  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000a2b3  test    rax, rax
0x18000a2b6  jnz     short loc_18000A2BF
0x18000a2b8  mov     eax, 0C0000139h
0x18000a2bd  jmp     short loc_18000A2C9
0x18000a2bf  lea     rcx, [rsp+28h+arg_18]
0x18000a2c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2c9  add     rsp, 28h
0x18000a2cd  retn
```
