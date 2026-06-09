# wil::details_abi::FeatureStateData::RecordFeatureUsageUnderLock(uint,wil_details_ServiceReportingKind,unsigned __int64)

- ea: `0x140007824`
- end: `0x140007879`
- name: `?RecordFeatureUsageUnderLock@FeatureStateData@details_abi@wil@@QEAA_NIW4wil_details_ServiceReportingKind@@_K@Z`
- size: `85`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task`

## callers

- `0x140007744`

## callees

- `0x140007824`
- `0x1400078b8`
- `0x1400078ec`

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
0x140007824  push    rbx
0x140007826  sub     rsp, 20h
0x14000782a  lea     rbx, [rcx+8]
0x14000782e  mov     r10d, r8d
0x140007831  cmp     r8d, 7
0x140007835  ja      short loc_140007842
0x140007837  mov     eax, 0CCh
0x14000783c  bt      eax, r8d
0x140007840  jb      short loc_140007862
0x140007842  lea     eax, [r8-100h]
0x140007849  cmp     eax, 7Fh
0x14000784c  jbe     short loc_140007862
0x14000784e  mov     r8d, edx
0x140007851  lea     rcx, [rbx+40h]
0x140007855  mov     edx, r10d
0x140007858  add     rsp, 20h
0x14000785c  pop     rbx
0x14000785d  jmp     ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140007862  mov     r8d, edx
0x140007865  mov     rcx, rbx
0x140007868  mov     edx, r10d
0x14000786b  call    ?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z; wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)
0x140007870  mov     al, [rbx+38h]
0x140007873  add     rsp, 20h
0x140007877  pop     rbx
0x140007878  retn
```
