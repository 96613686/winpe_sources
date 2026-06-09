# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1800077d8`
- end: `0x180007832`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007d34`

## callees

- `0x1800077d8`
- `0x180008020`
- `0x18000d010`

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
0x1800077d8  mov     rax, rsp
0x1800077db  sub     rsp, 28h
0x1800077df  mov     qword ptr [rax+20h], 0
0x1800077e7  mov     [rax+20h], ecx
0x1800077ea  mov     [rax+24h], dx
0x1800077ee  test    r8d, r8d
0x1800077f1  jz      short loc_1800077F8
0x1800077f3  or      word ptr [rax+26h], 1
0x1800077f8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800077ff  test    rax, rax
0x180007802  jnz     short loc_180007823
0x180007804  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000780b  call    wil_details_GetNtDllProcedureAddress
0x180007810  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x180007817  test    rax, rax
0x18000781a  jnz     short loc_180007823
0x18000781c  mov     eax, 0C0000139h
0x180007821  jmp     short loc_18000782D
0x180007823  lea     rcx, [rsp+28h+arg_18]
0x180007828  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000782d  add     rsp, 28h
0x180007831  retn
```
