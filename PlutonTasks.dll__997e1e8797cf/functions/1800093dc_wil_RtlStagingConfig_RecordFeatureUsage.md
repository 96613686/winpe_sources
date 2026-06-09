# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800093dc`
- end: `0x180009436`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: `__int64 __fastcall(int, __int16, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180008530`

## callees

- `0x1800090d0`
- `0x1800093dc`
- `0x18000a010`

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
0x1800093dc  mov     rax, rsp
0x1800093df  sub     rsp, 28h
0x1800093e3  mov     qword ptr [rax+20h], 0
0x1800093eb  mov     [rax+20h], ecx
0x1800093ee  mov     [rax+24h], dx
0x1800093f2  test    r8d, r8d
0x1800093f5  jz      short loc_1800093FC
0x1800093f7  or      word ptr [rax+26h], 1
0x1800093fc  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x180009403  test    rax, rax
0x180009406  jnz     short loc_180009427
0x180009408  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000940f  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180009414  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000941b  test    rax, rax
0x18000941e  jnz     short loc_180009427
0x180009420  mov     eax, 0C0000139h
0x180009425  jmp     short loc_180009431
0x180009427  lea     rcx, [rsp+28h+arg_18]
0x18000942c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009431  add     rsp, 28h
0x180009435  retn
```
