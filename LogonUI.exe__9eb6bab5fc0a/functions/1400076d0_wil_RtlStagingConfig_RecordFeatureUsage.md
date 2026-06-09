# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1400076d0`
- end: `0x14000772a`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140006c20`

## callees

- `0x1400072ec`
- `0x1400076d0`
- `0x140008010`

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
0x1400076d0  mov     rax, rsp
0x1400076d3  sub     rsp, 28h
0x1400076d7  mov     qword ptr [rax+20h], 0
0x1400076df  mov     [rax+20h], ecx
0x1400076e2  mov     [rax+24h], dx
0x1400076e6  test    r8d, r8d
0x1400076e9  jz      short loc_1400076F0
0x1400076eb  or      word ptr [rax+26h], 1
0x1400076f0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400076f7  test    rax, rax
0x1400076fa  jnz     short loc_14000771B
0x1400076fc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140007703  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140007708  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000770f  test    rax, rax
0x140007712  jnz     short loc_14000771B
0x140007714  mov     eax, 0C0000139h
0x140007719  jmp     short loc_140007725
0x14000771b  lea     rcx, [rsp+28h+arg_18]
0x140007720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007725  add     rsp, 28h
0x140007729  retn
```
