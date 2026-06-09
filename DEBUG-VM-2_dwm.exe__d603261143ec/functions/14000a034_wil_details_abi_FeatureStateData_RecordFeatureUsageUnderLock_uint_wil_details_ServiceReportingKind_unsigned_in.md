# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000a034`
- end: `0x14000a089`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140009f54`

## callees

- `0x14000a034`
- `0x14000a0e0`
- `0x14000a114`

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
0x14000a034  push    rbx
0x14000a036  sub     rsp, 20h
0x14000a03a  lea     rbx, [rcx+8]
0x14000a03e  mov     r10d, r8d
0x14000a041  cmp     r8d, 7
0x14000a045  ja      short loc_14000A052
0x14000a047  mov     eax, 0CCh
0x14000a04c  bt      eax, r8d
0x14000a050  jb      short loc_14000A072
0x14000a052  lea     eax, [r8-100h]
0x14000a059  cmp     eax, 7Fh
0x14000a05c  jbe     short loc_14000A072
0x14000a05e  mov     r8d, edx
0x14000a061  lea     rcx, [rbx+40h]
0x14000a065  mov     edx, r10d
0x14000a068  add     rsp, 20h
0x14000a06c  pop     rbx
0x14000a06d  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000a072  mov     r8d, edx
0x14000a075  mov     rcx, rbx
0x14000a078  mov     edx, r10d
0x14000a07b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000a080  mov     al, [rbx+38h]
0x14000a083  add     rsp, 20h
0x14000a087  pop     rbx
0x14000a088  retn
```
