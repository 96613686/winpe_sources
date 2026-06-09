# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x14000c858`
- end: `0x14000c8b2`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b540`

## callees

- `0x14000c630`
- `0x14000c858`
- `0x140017010`

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
0x14000c858  mov     rax, rsp
0x14000c85b  sub     rsp, 28h
0x14000c85f  mov     qword ptr [rax+20h], 0
0x14000c867  mov     [rax+20h], ecx
0x14000c86a  mov     [rax+24h], dx
0x14000c86e  test    r8d, r8d
0x14000c871  jz      short loc_14000C878
0x14000c873  or      word ptr [rax+26h], 1
0x14000c878  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000c87f  test    rax, rax
0x14000c882  jnz     short loc_14000C8A3
0x14000c884  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000c88b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000c890  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000c897  test    rax, rax
0x14000c89a  jnz     short loc_14000C8A3
0x14000c89c  mov     eax, 0C0000139h
0x14000c8a1  jmp     short loc_14000C8AD
0x14000c8a3  lea     rcx, [rsp+28h+arg_18]
0x14000c8a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c8ad  add     rsp, 28h
0x14000c8b1  retn
```
