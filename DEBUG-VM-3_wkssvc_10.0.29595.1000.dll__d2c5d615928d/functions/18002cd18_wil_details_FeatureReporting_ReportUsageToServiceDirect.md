# wil_details_FeatureReporting_ReportUsageToServiceDirect

- ea: `0x18002cd18`
- end: `0x18002cdbd`
- name: `wil_details_FeatureReporting_ReportUsageToServiceDirect`
- size: `165`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting, service_task, installer_update`

## callers

- `0x18002cbfc`

## callees

- `0x18002ca78`
- `0x18002cd18`
- `0x18002d030`
- `0x180034010`

## pseudocode

```c
_BOOL8 __fastcall wil_details_FeatureReporting_ReportUsageToServiceDirect(__int64 a1, __int64 a2, unsigned int a3)
{
  __int16 v3; // bx
  int v5; // esi
  FARPROC NtDllProcedureAddress; // rax
  __int64 v8; // [rsp+30h] [rbp-28h] BYREF
  _BYTE v9[32]; // [rsp+38h] [rbp-20h] BYREF

  v3 = a2;
  v5 = wil_details_FeatureReporting_RecordUsageInCache(
         (__int64)v9,
         (volatile signed __int32 *)&Feature_Servicing_WkssvcAllocationPrimitive__private_reporting,
         a3,
         SHIDWORD(a2))[4];
  if ( (v3 & 0x400) != 0 && a3 != 254 )
  {
    v8 = 57079295;
    WORD2(v8) = a3;
    if ( (v3 & 0x800) != 0 )
      HIWORD(v8) |= 1u;
    NtDllProcedureAddress = (FARPROC)g_wil_details_pfnRtlNotifyFeatureUsage;
    if ( g_wil_details_pfnRtlNotifyFeatureUsage
      || (NtDllProcedureAddress = wil_details_GetNtDllProcedureAddress("RtlNotifyFeatureUsage"),
          (g_wil_details_pfnRtlNotifyFeatureUsage = (__int64)NtDllProcedureAddress) != 0) )
    {
      ((void (__fastcall *)(__int64 *))NtDllProcedureAddress)(&v8);
    }
  }
  return v5 == 0;
}

```

## disassembly

```asm
0x18002cd18  mov     [rsp+arg_0], rbx
0x18002cd1d  mov     [rsp+arg_18], rsi
0x18002cd22  push    rdi
0x18002cd23  sub     rsp, 50h
0x18002cd27  mov     r9, rdx
0x18002cd2a  lea     rcx, [rsp+58h+var_20]
0x18002cd2f  mov     rbx, rdx
0x18002cd32  shr     r9, 20h
0x18002cd36  mov     rdx, cs:off_180048E18
0x18002cd3d  mov     edi, r8d
0x18002cd40  call    wil_details_FeatureReporting_RecordUsageInCache
0x18002cd45  mov     esi, [rax+10h]
0x18002cd48  bt      ebx, 0Ah
0x18002cd4c  jnb     short loc_18002CDA6
0x18002cd4e  cmp     edi, 0FEh
0x18002cd54  jz      short loc_18002CDA6
0x18002cd56  mov     [rsp+58h+var_28], 0
0x18002cd5f  mov     dword ptr [rsp+58h+var_28], 366F5FFh
0x18002cd67  mov     word ptr [rsp+58h+var_28+4], di
0x18002cd6c  bt      ebx, 0Bh
0x18002cd70  jnb     short loc_18002CD78
0x18002cd72  or      word ptr [rsp+58h+var_28+6], 1
0x18002cd78  mov     rax, cs:g_wil_details_pfnRtlNotifyFeatureUsage
0x18002cd7f  test    rax, rax
0x18002cd82  jnz     short loc_18002CD9C
0x18002cd84  lea     rcx, aRtlnotifyfeatu; "RtlNotifyFeatureUsage"
0x18002cd8b  call    wil_details_GetNtDllProcedureAddress
0x18002cd90  mov     cs:g_wil_details_pfnRtlNotifyFeatureUsage, rax
0x18002cd97  test    rax, rax
0x18002cd9a  jz      short loc_18002CDA6
0x18002cd9c  lea     rcx, [rsp+58h+var_28]
0x18002cda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002cda6  mov     rbx, [rsp+58h+arg_0]
0x18002cdab  xor     eax, eax
0x18002cdad  test    esi, esi
0x18002cdaf  mov     rsi, [rsp+58h+arg_18]
0x18002cdb4  setz    al
0x18002cdb7  add     rsp, 50h
0x18002cdbb  pop     rdi
0x18002cdbc  retn
```
