# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000bef0`
- end: `0x18000bf45`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000be04`

## callees

- `0x180004b60`
- `0x18000bef0`
- `0x18000bf4c`

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
  wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
    (wil::details_abi::RawUsageIndex *)(a1 + 8),
    a3,
    a2);
  return *(_BYTE *)(v3 + 56);
}

```

## disassembly

```asm
0x18000bef0  push    rbx
0x18000bef2  sub     rsp, 20h
0x18000bef6  lea     rbx, [rcx+8]
0x18000befa  mov     r10d, r8d
0x18000befd  cmp     r8d, 7
0x18000bf01  ja      short loc_18000BF0E
0x18000bf03  mov     eax, 0CCh
0x18000bf08  bt      eax, r8d
0x18000bf0c  jb      short loc_18000BF2E
0x18000bf0e  lea     eax, [r8-100h]
0x18000bf15  cmp     eax, 7Fh
0x18000bf18  jbe     short loc_18000BF2E
0x18000bf1a  mov     r8d, edx
0x18000bf1d  lea     rcx, [rbx+40h]
0x18000bf21  mov     edx, r10d
0x18000bf24  add     rsp, 20h
0x18000bf28  pop     rbx
0x18000bf29  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bf2e  mov     r8d, edx
0x18000bf31  mov     rcx, rbx; this
0x18000bf34  mov     edx, r10d
0x18000bf37  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bf3c  mov     al, [rbx+38h]
0x18000bf3f  add     rsp, 20h
0x18000bf43  pop     rbx
0x18000bf44  retn
```
