# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x18001e38c`
- end: `0x18001e3e6`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001dd40`

## callees

- `0x180016490`
- `0x18001e38c`
- `0x180025010`

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
0x18001e38c  mov     rax, rsp
0x18001e38f  sub     rsp, 28h
0x18001e393  mov     qword ptr [rax+20h], 0
0x18001e39b  mov     [rax+20h], ecx
0x18001e39e  mov     [rax+24h], dx
0x18001e3a2  test    r8d, r8d
0x18001e3a5  jz      short loc_18001E3AC
0x18001e3a7  or      word ptr [rax+26h], 1
0x18001e3ac  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18001e3b3  test    rax, rax
0x18001e3b6  jnz     short loc_18001E3D7
0x18001e3b8  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18001e3bf  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x18001e3c4  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18001e3cb  test    rax, rax
0x18001e3ce  jnz     short loc_18001E3D7
0x18001e3d0  mov     eax, 0C0000139h
0x18001e3d5  jmp     short loc_18001E3E1
0x18001e3d7  lea     rcx, [rsp+28h+arg_18]
0x18001e3dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e3e1  add     rsp, 28h
0x18001e3e5  retn
```
