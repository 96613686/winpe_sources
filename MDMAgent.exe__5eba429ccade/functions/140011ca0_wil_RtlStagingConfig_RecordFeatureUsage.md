# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x140011ca0`
- end: `0x140011cfa`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140010ec0`

## callees

- `0x140007e70`
- `0x140011ca0`
- `0x140019010`

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
0x140011ca0  mov     rax, rsp
0x140011ca3  sub     rsp, 28h
0x140011ca7  mov     qword ptr [rax+20h], 0
0x140011caf  mov     [rax+20h], ecx
0x140011cb2  mov     [rax+24h], dx
0x140011cb6  test    r8d, r8d
0x140011cb9  jz      short loc_140011CC0
0x140011cbb  or      word ptr [rax+26h], 1
0x140011cc0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x140011cc7  test    rax, rax
0x140011cca  jnz     short loc_140011CEB
0x140011ccc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x140011cd3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x140011cd8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x140011cdf  test    rax, rax
0x140011ce2  jnz     short loc_140011CEB
0x140011ce4  mov     eax, 0C0000139h
0x140011ce9  jmp     short loc_140011CF5
0x140011ceb  lea     rcx, [rsp+28h+arg_18]
0x140011cf0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011cf5  add     rsp, 28h
0x140011cf9  retn
```
