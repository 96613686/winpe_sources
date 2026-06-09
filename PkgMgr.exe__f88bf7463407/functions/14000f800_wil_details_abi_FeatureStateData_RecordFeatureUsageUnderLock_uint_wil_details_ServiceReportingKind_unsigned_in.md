# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000f800`
- end: `0x14000f855`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000f730`

## callees

- `0x14000f800`
- `0x14000f85c`
- `0x14000f8b0`

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
0x14000f800  push    rbx
0x14000f802  sub     rsp, 20h
0x14000f806  lea     rbx, [rcx+8]
0x14000f80a  mov     r10d, r8d
0x14000f80d  cmp     r8d, 7
0x14000f811  ja      short loc_14000F81E
0x14000f813  mov     eax, 0CCh
0x14000f818  bt      eax, r8d
0x14000f81c  jb      short loc_14000F83E
0x14000f81e  lea     eax, [r8-100h]
0x14000f825  cmp     eax, 7Fh
0x14000f828  jbe     short loc_14000F83E
0x14000f82a  mov     r8d, edx
0x14000f82d  lea     rcx, [rbx+40h]
0x14000f831  mov     edx, r10d
0x14000f834  add     rsp, 20h
0x14000f838  pop     rbx
0x14000f839  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000f83e  mov     r8d, edx
0x14000f841  mov     rcx, rbx
0x14000f844  mov     edx, r10d
0x14000f847  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000f84c  mov     al, [rbx+38h]
0x14000f84f  add     rsp, 20h
0x14000f853  pop     rbx
0x14000f854  retn
```
