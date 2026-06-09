# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x140007a90`
- end: `0x140007aea`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140006e30`

## callees

- `0x1400077f0`
- `0x140007a90`
- `0x140009010`

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
0x140007a90  mov     rax, rsp
0x140007a93  sub     rsp, 28h
0x140007a97  mov     qword ptr [rax+20h], 0
0x140007a9f  mov     [rax+20h], ecx
0x140007aa2  mov     [rax+24h], dx
0x140007aa6  test    r8d, r8d
0x140007aa9  jz      short loc_140007AB0
0x140007aab  or      word ptr [rax+26h], 1
0x140007ab0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140007ab7  test    rax, rax
0x140007aba  jnz     short loc_140007ADB
0x140007abc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140007ac3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140007ac8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140007acf  test    rax, rax
0x140007ad2  jnz     short loc_140007ADB
0x140007ad4  mov     eax, 0C0000139h
0x140007ad9  jmp     short loc_140007AE5
0x140007adb  lea     rcx, [rsp+28h+arg_18]
0x140007ae0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007ae5  add     rsp, 28h
0x140007ae9  retn
```
