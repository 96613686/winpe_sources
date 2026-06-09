# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18001300c`
- end: `0x180013066`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011de0`

## callees

- `0x18000dc44`
- `0x18001300c`
- `0x18001b010`

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
0x18001300c  mov     rax, rsp
0x18001300f  sub     rsp, 28h
0x180013013  mov     qword ptr [rax+20h], 0
0x18001301b  mov     [rax+20h], ecx
0x18001301e  mov     [rax+24h], dx
0x180013022  test    r8d, r8d
0x180013025  jz      short loc_18001302C
0x180013027  or      word ptr [rax+26h], 1
0x18001302c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180013033  test    rax, rax
0x180013036  jnz     short loc_180013057
0x180013038  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001303f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180013044  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001304b  test    rax, rax
0x18001304e  jnz     short loc_180013057
0x180013050  mov     eax, 0C0000139h
0x180013055  jmp     short loc_180013061
0x180013057  lea     rcx, [rsp+28h+arg_18]
0x18001305c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013061  add     rsp, 28h
0x180013065  retn
```
