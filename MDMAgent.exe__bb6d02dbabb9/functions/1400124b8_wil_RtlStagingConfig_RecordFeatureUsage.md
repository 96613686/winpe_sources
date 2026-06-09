# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1400124b8`
- end: `0x140012513`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `91`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140011740`

## callees

- `0x1400081c8`
- `0x1400124b8`
- `0x14001a010`

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
0x1400124b8  mov     rax, rsp
0x1400124bb  sub     rsp, 28h
0x1400124bf  mov     qword ptr [rax+20h], 0
0x1400124c7  mov     [rax+20h], ecx
0x1400124ca  mov     [rax+24h], dx
0x1400124ce  test    r8d, r8d
0x1400124d1  jz      short loc_1400124D8
0x1400124d3  or      word ptr [rax+26h], 1
0x1400124d8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400124df  test    rax, rax
0x1400124e2  jnz     short loc_140012503
0x1400124e4  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1400124eb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400124f0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1400124f7  test    rax, rax
0x1400124fa  jnz     short loc_140012503
0x1400124fc  mov     eax, 0C0000139h
0x140012501  jmp     short loc_14001250D
0x140012503  lea     rcx, [rsp+28h+arg_18]
0x140012508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001250d  add     rsp, 28h
0x140012511  retn
```
