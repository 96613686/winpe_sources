# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x140009b48`
- end: `0x140009ba2`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140008ec0`

## callees

- `0x14000972c`
- `0x140009b48`
- `0x140020010`

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
0x140009b48  mov     rax, rsp
0x140009b4b  sub     rsp, 28h
0x140009b4f  mov     qword ptr [rax+20h], 0
0x140009b57  mov     [rax+20h], ecx
0x140009b5a  mov     [rax+24h], dx
0x140009b5e  test    r8d, r8d
0x140009b61  jz      short loc_140009B68
0x140009b63  or      word ptr [rax+26h], 1
0x140009b68  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140009b6f  test    rax, rax
0x140009b72  jnz     short loc_140009B93
0x140009b74  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140009b7b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140009b80  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140009b87  test    rax, rax
0x140009b8a  jnz     short loc_140009B93
0x140009b8c  mov     eax, 0C0000139h
0x140009b91  jmp     short loc_140009B9D
0x140009b93  lea     rcx, [rsp+28h+arg_18]
0x140009b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009b9d  add     rsp, 28h
0x140009ba1  retn
```
