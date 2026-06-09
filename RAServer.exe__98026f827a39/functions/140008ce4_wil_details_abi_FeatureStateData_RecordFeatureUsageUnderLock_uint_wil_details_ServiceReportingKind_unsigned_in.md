# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140008ce4`
- end: `0x140008d39`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: `char __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140008c04`

## callees

- `0x140008ce4`
- `0x140008d78`
- `0x140008dac`

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
0x140008ce4  push    rbx
0x140008ce6  sub     rsp, 20h
0x140008cea  lea     rbx, [rcx+8]
0x140008cee  mov     r10d, r8d
0x140008cf1  cmp     r8d, 7
0x140008cf5  ja      short loc_140008D02
0x140008cf7  mov     eax, 0CCh
0x140008cfc  bt      eax, r8d
0x140008d00  jb      short loc_140008D22
0x140008d02  lea     eax, [r8-100h]
0x140008d09  cmp     eax, 7Fh
0x140008d0c  jbe     short loc_140008D22
0x140008d0e  mov     r8d, edx
0x140008d11  lea     rcx, [rbx+40h]
0x140008d15  mov     edx, r10d
0x140008d18  add     rsp, 20h
0x140008d1c  pop     rbx
0x140008d1d  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140008d22  mov     r8d, edx
0x140008d25  mov     rcx, rbx
0x140008d28  mov     edx, r10d
0x140008d2b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140008d30  mov     al, [rbx+38h]
0x140008d33  add     rsp, 20h
0x140008d37  pop     rbx
0x140008d38  retn
```
