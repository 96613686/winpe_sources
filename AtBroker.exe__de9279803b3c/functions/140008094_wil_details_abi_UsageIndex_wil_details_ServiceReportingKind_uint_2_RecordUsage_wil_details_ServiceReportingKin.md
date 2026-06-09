# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x140008094`
- end: `0x1400080c2`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `46`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int, unsigned int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140007f14`

## callees

- `0x140008194`

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
0x140008094  mov     rax, rsp
0x140008097  mov     [rax+18h], r8d
0x14000809b  mov     [rax+10h], edx
0x14000809e  sub     rsp, 38h
0x1400080a2  mov     [rax-10h], r9d
0x1400080a6  lea     rdx, [rax+10h]; void *
0x1400080aa  mov     r8d, 4; unsigned __int64
0x1400080b0  lea     r9, [rax+18h]; void *
0x1400080b4  mov     [rax-18h], r8
0x1400080b8  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400080bd  add     rsp, 38h
0x1400080c1  retn
```
