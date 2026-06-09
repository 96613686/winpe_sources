# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x14000cb18`
- end: `0x14000cb49`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `49`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x14000ca88`

## callees

- `0x14000cbb4`

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
0x14000cb18  mov     rax, rsp
0x14000cb1b  mov     [rax+18h], r8d
0x14000cb1f  mov     [rax+10h], edx
0x14000cb22  sub     rsp, 38h
0x14000cb26  mov     r8d, 4; unsigned __int64
0x14000cb2c  mov     dword ptr [rax-10h], 1
0x14000cb33  lea     r9, [rax+18h]; void *
0x14000cb37  mov     [rax-18h], r8
0x14000cb3b  lea     rdx, [rax+10h]; void *
0x14000cb3f  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x14000cb44  add     rsp, 38h
0x14000cb48  retn
```
