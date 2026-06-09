# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::~UsageIndex<wil_details_ServiceReportingKind,uint,0>(void)

- ea: `0x18001d728`
- end: `0x18001d73a`
- name: `??1?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA@XZ`
- size: `18`
- prototype: ``
- caller_count: `6`
- callee_count: `1`
- tags: `service_task`

## callers

- `0x180031af9`
- `0x180031b0b`
- `0x180031b21`
- `0x180031d11`
- `0x180031d23`
- `0x180031d39`

## callees

- `0x18001d958`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::~UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>(
        wil::details_abi::RawUsageIndex *a1)
{
  wil::details_abi::RawUsageIndex::~RawUsageIndex(a1);
}

```

## disassembly

```asm
0x18001d728  mov     [rsp+arg_0], rcx
0x18001d72d  sub     rsp, 28h
0x18001d731  add     rsp, 28h
0x18001d735  jmp     ??1RawUsageIndex@details_abi@wil@@QEAA@XZ; wil::details_abi::RawUsageIndex::~RawUsageIndex(void)
```
