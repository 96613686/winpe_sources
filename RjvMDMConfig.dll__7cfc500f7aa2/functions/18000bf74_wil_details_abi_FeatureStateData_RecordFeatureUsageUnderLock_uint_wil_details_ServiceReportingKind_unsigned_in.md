# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x18000bf74`
- end: `0x18000bfca`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `86`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x18000be84`

## callees

- `0x18000bf74`
- `0x18000c020`
- `0x18000c058`

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
0x18000bf74  push    rbx
0x18000bf76  sub     rsp, 20h
0x18000bf7a  lea     rbx, [rcx+8]
0x18000bf7e  mov     r10d, r8d
0x18000bf81  cmp     r8d, 7
0x18000bf85  ja      short loc_18000BF92
0x18000bf87  mov     eax, 0CCh
0x18000bf8c  bt      eax, r8d
0x18000bf90  jb      short loc_18000BFB2
0x18000bf92  lea     eax, [r8-100h]
0x18000bf99  cmp     eax, 7Fh
0x18000bf9c  jbe     short loc_18000BFB2
0x18000bf9e  mov     r8d, edx
0x18000bfa1  lea     rcx, [rbx+40h]
0x18000bfa5  mov     edx, r10d
0x18000bfa8  add     rsp, 20h
0x18000bfac  pop     rbx
0x18000bfad  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bfb2  mov     r8d, edx
0x18000bfb5  mov     rcx, rbx
0x18000bfb8  mov     edx, r10d
0x18000bfbb  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x18000bfc0  mov     al, [rbx+38h]
0x18000bfc3  add     rsp, 20h
0x18000bfc7  pop     rbx
0x18000bfc8  retn
```
