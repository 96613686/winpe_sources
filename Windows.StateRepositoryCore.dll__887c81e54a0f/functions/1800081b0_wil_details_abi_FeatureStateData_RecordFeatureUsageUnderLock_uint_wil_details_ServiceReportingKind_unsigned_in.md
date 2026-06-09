# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x1800081b0`
- end: `0x180008205`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: `char __fastcall(__int64, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x1800080d4`

## callees

- `0x1800081b0`
- `0x180008260`
- `0x180008294`

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
0x1800081b0  push    rbx
0x1800081b2  sub     rsp, 20h
0x1800081b6  lea     rbx, [rcx+8]
0x1800081ba  mov     r10d, r8d
0x1800081bd  cmp     r8d, 7
0x1800081c1  ja      short loc_1800081CE
0x1800081c3  mov     eax, 0CCh
0x1800081c8  bt      eax, r8d
0x1800081cc  jb      short loc_1800081EE
0x1800081ce  lea     eax, [r8-100h]
0x1800081d5  cmp     eax, 7Fh
0x1800081d8  jbe     short loc_1800081EE
0x1800081da  mov     r8d, edx
0x1800081dd  lea     rcx, [rbx+40h]
0x1800081e1  mov     edx, r10d
0x1800081e4  add     rsp, 20h
0x1800081e8  pop     rbx
0x1800081e9  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800081ee  mov     r8d, edx
0x1800081f1  mov     rcx, rbx
0x1800081f4  mov     edx, r10d
0x1800081f7  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x1800081fc  mov     al, [rbx+38h]
0x1800081ff  add     rsp, 20h
0x180008203  pop     rbx
0x180008204  retn
```
