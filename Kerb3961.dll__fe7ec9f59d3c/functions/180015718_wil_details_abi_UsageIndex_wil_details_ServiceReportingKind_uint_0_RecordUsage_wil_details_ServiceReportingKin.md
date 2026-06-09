# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180015718`
- end: `0x180015749`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180015598`

## callees

- `0x1800157e4`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3)
{
  int v4; // [rsp+48h] [rbp+10h] BYREF
  int v5; // [rsp+50h] [rbp+18h] BYREF

  v5 = a3;
  v4 = a2;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v4, 4u, &v5, 4u, 1u);
}

```

## disassembly

```asm
0x180015718  mov     rax, rsp
0x18001571b  mov     [rax+18h], r8d
0x18001571f  mov     [rax+10h], edx
0x180015722  sub     rsp, 38h
0x180015726  mov     r8d, 4; unsigned __int64
0x18001572c  mov     dword ptr [rax-10h], 1
0x180015733  lea     r9, [rax+18h]; void *
0x180015737  mov     [rax-18h], r8
0x18001573b  lea     rdx, [rax+10h]; void *
0x18001573f  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x180015744  add     rsp, 38h
0x180015748  retn
```
