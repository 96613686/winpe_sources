# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180019a58`
- end: `0x180019ab2`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180017880`

## callees

- `0x180019230`
- `0x180019a58`
- `0x18002e010`

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
0x180019a58  mov     rax, rsp
0x180019a5b  sub     rsp, 28h
0x180019a5f  mov     qword ptr [rax+20h], 0
0x180019a67  mov     [rax+20h], ecx
0x180019a6a  mov     [rax+24h], dx
0x180019a6e  test    r8d, r8d
0x180019a71  jz      short loc_180019A78
0x180019a73  or      word ptr [rax+26h], 1
0x180019a78  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180019a7f  test    rax, rax
0x180019a82  jnz     short loc_180019AA3
0x180019a84  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180019a8b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180019a90  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180019a97  test    rax, rax
0x180019a9a  jnz     short loc_180019AA3
0x180019a9c  mov     eax, 0C0000139h
0x180019aa1  jmp     short loc_180019AAD
0x180019aa3  lea     rcx, [rsp+28h+arg_18]
0x180019aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aad  add     rsp, 28h
0x180019ab1  retn
```
