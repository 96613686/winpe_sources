# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x14000d5e8`
- end: `0x14000d65f`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000ced0`

## callees

- `0x140002310`
- `0x140005ed0`
- `0x14000d5e8`
- `0x14002b010`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_RecordFeatureUsage(int a1, unsigned __int16 a2, int a3)
{
  FARPROC NtDllProcedureAddress; // rax
  int v5; // [rsp+20h] [rbp-18h] BYREF
  int v6; // [rsp+24h] [rbp-14h]

  v5 = a1;
  v6 = a2;
  if ( a3 )
    HIWORD(v6) |= 1u;
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
0x14000d5e8  sub     rsp, 38h
0x14000d5ec  mov     rax, cs:__security_cookie
0x14000d5f3  xor     rax, rsp
0x14000d5f6  mov     [rsp+38h+var_10], rax
0x14000d5fb  mov     [rsp+38h+var_18], 0
0x14000d604  mov     dword ptr [rsp+38h+var_18], ecx
0x14000d608  mov     word ptr [rsp+38h+var_18+4], dx
0x14000d60d  test    r8d, r8d
0x14000d610  jz      short loc_14000D618
0x14000d612  or      word ptr [rsp+38h+var_18+6], 1
0x14000d618  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x14000d61f  test    rax, rax
0x14000d622  jnz     short loc_14000D643
0x14000d624  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x14000d62b  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x14000d630  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x14000d637  test    rax, rax
0x14000d63a  jnz     short loc_14000D643
0x14000d63c  mov     eax, 0C0000139h
0x14000d641  jmp     short loc_14000D64D
0x14000d643  lea     rcx, [rsp+38h+var_18]
0x14000d648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d64d  mov     rcx, [rsp+38h+var_10]
0x14000d652  xor     rcx, rsp; StackCookie
0x14000d655  call    __security_check_cookie
0x14000d65a  add     rsp, 38h
0x14000d65e  retn
```
