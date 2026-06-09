# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x180015688`
- end: `0x1800156e2`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `90`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180014a50`

## callees

- `0x1800057f0`
- `0x180015688`
- `0x180018010`

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
0x180015688  mov     rax, rsp
0x18001568b  sub     rsp, 28h
0x18001568f  mov     qword ptr [rax+20h], 0
0x180015697  mov     [rax+20h], ecx
0x18001569a  mov     [rax+24h], dx
0x18001569e  test    r8d, r8d
0x1800156a1  jz      short loc_1800156A8
0x1800156a3  or      word ptr [rax+26h], 1
0x1800156a8  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1800156af  test    rax, rax
0x1800156b2  jnz     short loc_1800156D3
0x1800156b4  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1800156bb  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1800156c0  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1800156c7  test    rax, rax
0x1800156ca  jnz     short loc_1800156D3
0x1800156cc  mov     eax, 0C0000139h
0x1800156d1  jmp     short loc_1800156DD
0x1800156d3  lea     rcx, [rsp+28h+arg_18]
0x1800156d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800156dd  add     rsp, 28h
0x1800156e1  retn
```
