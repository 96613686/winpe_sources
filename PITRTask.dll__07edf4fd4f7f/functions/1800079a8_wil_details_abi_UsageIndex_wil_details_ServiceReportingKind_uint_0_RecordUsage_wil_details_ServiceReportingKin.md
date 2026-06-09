# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x1800079a8`
- end: `0x1800079f7`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `79`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x1800077c4`

## callees

- `0x180007ab8`
- `0x1800107c0`

## pseudocode

```c
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,0>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3)
{
  int v4; // [rsp+30h] [rbp-28h] BYREF
  int v5; // [rsp+38h] [rbp-20h] BYREF

  v5 = a2;
  v4 = a3;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v5, 4u, &v4, 4u, 1u);
}

```

## disassembly

```asm
0x1800079a8  mov     r11, rsp
0x1800079ab  sub     rsp, 58h
0x1800079af  mov     rax, cs:__security_cookie
0x1800079b6  xor     rax, rsp
0x1800079b9  mov     [rsp+58h+var_18], rax
0x1800079be  mov     [rsp+58h+var_20], edx
0x1800079c2  lea     r9, [r11-28h]; void *
0x1800079c6  mov     [r11-28h], r8d
0x1800079ca  lea     rdx, [r11-20h]; Buf1
0x1800079ce  mov     r8d, 4; Size
0x1800079d4  mov     [rsp+58h+var_30], 1; unsigned int
0x1800079dc  mov     [r11-38h], r8
0x1800079e0  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1800079e5  mov     rcx, [rsp+58h+var_18]
0x1800079ea  xor     rcx, rsp; StackCookie
0x1800079ed  call    __security_check_cookie
0x1800079f2  add     rsp, 58h
0x1800079f6  retn
```
