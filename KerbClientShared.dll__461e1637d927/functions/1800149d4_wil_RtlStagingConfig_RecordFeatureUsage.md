# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800149d4`
- end: `0x180014a2e`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013e00`

## callees

- `0x1800144cc`
- `0x1800149d4`
- `0x180029010`

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
0x1800149d4  mov     rax, rsp
0x1800149d7  sub     rsp, 28h
0x1800149db  mov     qword ptr [rax+20h], 0
0x1800149e3  mov     [rax+20h], ecx
0x1800149e6  mov     [rax+24h], dx
0x1800149ea  test    r8d, r8d
0x1800149ed  jz      short loc_1800149F4
0x1800149ef  or      word ptr [rax+26h], 1
0x1800149f4  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800149fb  test    rax, rax
0x1800149fe  jnz     short loc_180014A1F
0x180014a00  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x180014a07  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x180014a0c  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180014a13  test    rax, rax
0x180014a16  jnz     short loc_180014A1F
0x180014a18  mov     eax, 0C0000139h
0x180014a1d  jmp     short loc_180014A29
0x180014a1f  lea     rcx, [rsp+28h+arg_18]
0x180014a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a29  add     rsp, 28h
0x180014a2d  retn
```
