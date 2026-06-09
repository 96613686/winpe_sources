# wil_RtlStagingConfig_RecordFeatureUsage

- ea: `0x1400120a0`
- end: `0x140012117`
- name: `wil_RtlStagingConfig_RecordFeatureUsage`
- size: `119`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x140010430`

## callees

- `0x140002360`
- `0x1400066b0`
- `0x1400120a0`
- `0x14002a010`

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
0x1400120a0  sub     rsp, 38h
0x1400120a4  mov     rax, cs:__security_cookie
0x1400120ab  xor     rax, rsp
0x1400120ae  mov     [rsp+38h+var_10], rax
0x1400120b3  mov     [rsp+38h+var_18], 0
0x1400120bc  mov     dword ptr [rsp+38h+var_18], ecx
0x1400120c0  mov     word ptr [rsp+38h+var_18+4], dx
0x1400120c5  test    r8d, r8d
0x1400120c8  jz      short loc_1400120D0
0x1400120ca  or      word ptr [rsp+38h+var_18+6], 1
0x1400120d0  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x1400120d7  test    rax, rax
0x1400120da  jnz     short loc_1400120FB
0x1400120dc  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x1400120e3  call    ?wil_details_GetNtDllProcedureAddress@@YAP6A_JXZPEBD@Z; wil_details_GetNtDllProcedureAddress(char const *)
0x1400120e8  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x1400120ef  test    rax, rax
0x1400120f2  jnz     short loc_1400120FB
0x1400120f4  mov     eax, 0C0000139h
0x1400120f9  jmp     short loc_140012105
0x1400120fb  lea     rcx, [rsp+38h+var_18]
0x140012100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012105  mov     rcx, [rsp+38h+var_10]
0x14001210a  xor     rcx, rsp; StackCookie
0x14001210d  call    __security_check_cookie
0x140012112  add     rsp, 38h
0x140012116  retn
```
