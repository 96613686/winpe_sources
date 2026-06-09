# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x140010498`
- end: `0x1400104c9`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `49`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int)`
- caller_count: `1`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x140010314`

## callees

- `0x140010564`

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
0x140010498  mov     rax, rsp
0x14001049b  mov     [rax+18h], r8d
0x14001049f  mov     [rax+10h], edx
0x1400104a2  sub     rsp, 38h
0x1400104a6  mov     r8d, 4; unsigned __int64
0x1400104ac  mov     dword ptr [rax-10h], 1
0x1400104b3  lea     r9, [rax+18h]; void *
0x1400104b7  mov     [rax-18h], r8
0x1400104bb  lea     rdx, [rax+10h]; void *
0x1400104bf  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400104c4  add     rsp, 38h
0x1400104c8  retn
```
