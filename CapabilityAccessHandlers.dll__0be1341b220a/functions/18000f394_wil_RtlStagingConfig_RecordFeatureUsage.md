# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000f394`
- end: `0x18000f3ee`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000cec0`

## callees

- `0x18000a010`
- `0x18000f394`
- `0x180014010`

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
0x18000f394  mov     rax, rsp
0x18000f397  sub     rsp, 28h
0x18000f39b  mov     qword ptr [rax+20h], 0
0x18000f3a3  mov     [rax+20h], ecx
0x18000f3a6  mov     [rax+24h], dx
0x18000f3aa  test    r8d, r8d
0x18000f3ad  jz      short loc_18000F3B4
0x18000f3af  or      word ptr [rax+26h], 1
0x18000f3b4  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000f3bb  test    rax, rax
0x18000f3be  jnz     short loc_18000F3DF
0x18000f3c0  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000f3c7  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000f3cc  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000f3d3  test    rax, rax
0x18000f3d6  jnz     short loc_18000F3DF
0x18000f3d8  mov     eax, 0C0000139h
0x18000f3dd  jmp     short loc_18000F3E9
0x18000f3df  lea     rcx, [rsp+28h+arg_18]
0x18000f3e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f3e9  add     rsp, 28h
0x18000f3ed  retn
```
