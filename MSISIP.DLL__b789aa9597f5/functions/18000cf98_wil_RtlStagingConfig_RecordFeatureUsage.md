# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000cf98`
- end: `0x18000cff2`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000cb80`

## callees

- `0x18000cdec`
- `0x18000cf98`
- `0x18000e010`

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
0x18000cf98  mov     rax, rsp
0x18000cf9b  sub     rsp, 28h
0x18000cf9f  mov     qword ptr [rax+20h], 0
0x18000cfa7  mov     [rax+20h], ecx
0x18000cfaa  mov     [rax+24h], dx
0x18000cfae  test    r8d, r8d
0x18000cfb1  jz      short loc_18000CFB8
0x18000cfb3  or      word ptr [rax+26h], 1
0x18000cfb8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000cfbf  test    rax, rax
0x18000cfc2  jnz     short loc_18000CFE3
0x18000cfc4  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000cfcb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000cfd0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000cfd7  test    rax, rax
0x18000cfda  jnz     short loc_18000CFE3
0x18000cfdc  mov     eax, 0C0000139h
0x18000cfe1  jmp     short loc_18000CFED
0x18000cfe3  lea     rcx, [rsp+28h+arg_18]
0x18000cfe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfed  add     rsp, 28h
0x18000cff1  retn
```
