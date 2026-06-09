# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000c2c4`
- end: `0x14000c319`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000464c`

## callees

- `0x14000c2c4`
- `0x14000c350`
- `0x14000c384`

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
0x14000c2c4  push    rbx
0x14000c2c6  sub     rsp, 20h
0x14000c2ca  lea     rbx, [rcx+8]
0x14000c2ce  mov     r10d, r8d
0x14000c2d1  cmp     r8d, 7
0x14000c2d5  ja      short loc_14000C2E2
0x14000c2d7  mov     eax, 0CCh
0x14000c2dc  bt      eax, r8d
0x14000c2e0  jb      short loc_14000C302
0x14000c2e2  lea     eax, [r8-100h]
0x14000c2e9  cmp     eax, 7Fh
0x14000c2ec  jbe     short loc_14000C302
0x14000c2ee  mov     r8d, edx
0x14000c2f1  lea     rcx, [rbx+40h]
0x14000c2f5  mov     edx, r10d
0x14000c2f8  add     rsp, 20h
0x14000c2fc  pop     rbx
0x14000c2fd  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000c302  mov     r8d, edx
0x14000c305  mov     rcx, rbx
0x14000c308  mov     edx, r10d
0x14000c30b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000c310  mov     al, [rbx+38h]
0x14000c313  add     rsp, 20h
0x14000c317  pop     rbx
0x14000c318  retn
```
