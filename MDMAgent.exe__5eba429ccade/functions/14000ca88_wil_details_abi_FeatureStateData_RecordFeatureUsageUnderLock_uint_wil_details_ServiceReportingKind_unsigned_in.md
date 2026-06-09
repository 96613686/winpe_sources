# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x14000ca88`
- end: `0x14000cadd`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: `char __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x14000c9a8`

## callees

- `0x14000ca88`
- `0x14000cae4`
- `0x14000cb18`

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
0x14000ca88  push    rbx
0x14000ca8a  sub     rsp, 20h
0x14000ca8e  lea     rbx, [rcx+8]
0x14000ca92  mov     r10d, r8d
0x14000ca95  cmp     r8d, 7
0x14000ca99  ja      short loc_14000CAA6
0x14000ca9b  mov     eax, 0CCh
0x14000caa0  bt      eax, r8d
0x14000caa4  jb      short loc_14000CAC6
0x14000caa6  lea     eax, [r8-100h]
0x14000caad  cmp     eax, 7Fh
0x14000cab0  jbe     short loc_14000CAC6
0x14000cab2  mov     r8d, edx
0x14000cab5  lea     rcx, [rbx+40h]
0x14000cab9  mov     edx, r10d
0x14000cabc  add     rsp, 20h
0x14000cac0  pop     rbx
0x14000cac1  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000cac6  mov     r8d, edx
0x14000cac9  mov     rcx, rbx
0x14000cacc  mov     edx, r10d
0x14000cacf  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x14000cad4  mov     al, [rbx+38h]
0x14000cad7  add     rsp, 20h
0x14000cadb  pop     rbx
0x14000cadc  retn
```
