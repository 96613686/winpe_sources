# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180006594`
- end: `0x1800065c2`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `46`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180006414`

## callees

- `0x180006694`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3,
        unsigned int a4)
{
  int v5; // [rsp+48h] [rbp+10h] BYREF
  int v6; // [rsp+50h] [rbp+18h] BYREF

  v6 = a3;
  v5 = a2;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v5, 4u, &v6, 4u, a4);
}

```

## disassembly

```asm
0x180006594  mov     rax, rsp
0x180006597  mov     [rax+18h], r8d
0x18000659b  mov     [rax+10h], edx
0x18000659e  sub     rsp, 38h
0x1800065a2  mov     [rax-10h], r9d
0x1800065a6  lea     rdx, [rax+10h]; void *
0x1800065aa  mov     r8d, 4; unsigned __int64
0x1800065b0  lea     r9, [rax+18h]; void *
0x1800065b4  mov     [rax-18h], r8
0x1800065b8  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800065bd  add     rsp, 38h
0x1800065c1  retn
```
