# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000b86c`
- end: `0x18000b8c6`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000af90`

## callees

- `0x180007920`
- `0x18000b86c`
- `0x180018010`

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
0x18000b86c  mov     rax, rsp
0x18000b86f  sub     rsp, 28h
0x18000b873  mov     qword ptr [rax+20h], 0
0x18000b87b  mov     [rax+20h], ecx
0x18000b87e  mov     [rax+24h], dx
0x18000b882  test    r8d, r8d
0x18000b885  jz      short loc_18000B88C
0x18000b887  or      word ptr [rax+26h], 1
0x18000b88c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b893  test    rax, rax
0x18000b896  jnz     short loc_18000B8B7
0x18000b898  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b89f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b8a4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b8ab  test    rax, rax
0x18000b8ae  jnz     short loc_18000B8B7
0x18000b8b0  mov     eax, 0C0000139h
0x18000b8b5  jmp     short loc_18000B8C1
0x18000b8b7  lea     rcx, [rsp+28h+arg_18]
0x18000b8bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b8c1  add     rsp, 28h
0x18000b8c5  retn
```
