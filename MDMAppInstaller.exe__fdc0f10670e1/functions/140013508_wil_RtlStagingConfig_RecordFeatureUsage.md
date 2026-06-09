# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x140013508`
- end: `0x140013562`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400112c0`

## callees

- `0x140006bd0`
- `0x140013508`
- `0x14001c010`

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
0x140013508  mov     rax, rsp
0x14001350b  sub     rsp, 28h
0x14001350f  mov     qword ptr [rax+20h], 0
0x140013517  mov     [rax+20h], ecx
0x14001351a  mov     [rax+24h], dx
0x14001351e  test    r8d, r8d
0x140013521  jz      short loc_140013528
0x140013523  or      word ptr [rax+26h], 1
0x140013528  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14001352f  test    rax, rax
0x140013532  jnz     short loc_140013553
0x140013534  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14001353b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140013540  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140013547  test    rax, rax
0x14001354a  jnz     short loc_140013553
0x14001354c  mov     eax, 0C0000139h
0x140013551  jmp     short loc_14001355D
0x140013553  lea     rcx, [rsp+28h+arg_18]
0x140013558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001355d  add     rsp, 28h
0x140013561  retn
```
