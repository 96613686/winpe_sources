# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18000b67c`
- end: `0x18000b6d6`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000a3b0`

## callees

- `0x18000b160`
- `0x18000b67c`
- `0x180011010`

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
0x18000b67c  mov     rax, rsp
0x18000b67f  sub     rsp, 28h
0x18000b683  mov     qword ptr [rax+20h], 0
0x18000b68b  mov     [rax+20h], ecx
0x18000b68e  mov     [rax+24h], dx
0x18000b692  test    r8d, r8d
0x18000b695  jz      short loc_18000B69C
0x18000b697  or      word ptr [rax+26h], 1
0x18000b69c  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18000b6a3  test    rax, rax
0x18000b6a6  jnz     short loc_18000B6C7
0x18000b6a8  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18000b6af  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18000b6b4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18000b6bb  test    rax, rax
0x18000b6be  jnz     short loc_18000B6C7
0x18000b6c0  mov     eax, 0C0000139h
0x18000b6c5  jmp     short loc_18000B6D1
0x18000b6c7  lea     rcx, [rsp+28h+arg_18]
0x18000b6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b6d1  add     rsp, 28h
0x18000b6d5  retn
```
