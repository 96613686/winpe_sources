# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000f4e0`
- end: `0x14000f535`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: `char __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000f400`

## callees

- `0x14000f4e0`
- `0x14000f550`
- `0x14000f584`

## pseudocode

```c
char __fastcall wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(
        __int64 a1,
        unsigned int a2,
        unsigned int a3)
{
  __int64 v3; // rbx
  int v4; // eax

  v3 = a1 + 8;
  if ( a3 > 7 || (v4 = 204, !_bittest(&v4, a3)) )
  {
    if ( a3 - 256 > 0x7F )
      return wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
               a1 + 72,
               a3,
               a2);
  }
  wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(a1 + 8, a3, a2);
  return *(_BYTE *)(v3 + 56);
}

```

## disassembly

```asm
0x14000f4e0  push    rbx
0x14000f4e2  sub     rsp, 20h
0x14000f4e6  lea     rbx, [rcx+8]
0x14000f4ea  mov     r10d, r8d
0x14000f4ed  cmp     r8d, 7
0x14000f4f1  ja      short loc_14000F4FE
0x14000f4f3  mov     eax, 0CCh
0x14000f4f8  bt      eax, r8d
0x14000f4fc  jb      short loc_14000F51E
0x14000f4fe  lea     eax, [r8-100h]
0x14000f505  cmp     eax, 7Fh
0x14000f508  jbe     short loc_14000F51E
0x14000f50a  mov     r8d, edx
0x14000f50d  lea     rcx, [rbx+40h]
0x14000f511  mov     edx, r10d
0x14000f514  add     rsp, 20h
0x14000f518  pop     rbx
0x14000f519  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000f51e  mov     r8d, edx
0x14000f521  mov     rcx, rbx
0x14000f524  mov     edx, r10d
0x14000f527  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000f52c  mov     al, [rbx+38h]
0x14000f52f  add     rsp, 20h
0x14000f533  pop     rbx
0x14000f534  retn
```
