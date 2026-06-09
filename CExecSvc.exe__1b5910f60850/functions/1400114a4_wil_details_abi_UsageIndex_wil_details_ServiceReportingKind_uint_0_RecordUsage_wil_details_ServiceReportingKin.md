# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,0>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x1400114a4`
- end: `0x1400114f3`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$0A@@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `79`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x140011334`

## callees

- `0x140002310`
- `0x1400115b4`

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
0x1400114a4  mov     r11, rsp
0x1400114a7  sub     rsp, 58h
0x1400114ab  mov     rax, cs:__security_cookie
0x1400114b2  xor     rax, rsp
0x1400114b5  mov     [rsp+58h+var_18], rax
0x1400114ba  mov     [rsp+58h+var_20], edx
0x1400114be  lea     r9, [r11-28h]; void *
0x1400114c2  mov     [r11-28h], r8d
0x1400114c6  lea     rdx, [r11-20h]; Buf1
0x1400114ca  mov     r8d, 4; Size
0x1400114d0  mov     [rsp+58h+var_30], 1; unsigned int
0x1400114d8  mov     [r11-38h], r8
0x1400114dc  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x1400114e1  mov     rcx, [rsp+58h+var_18]
0x1400114e6  xor     rcx, rsp; StackCookie
0x1400114e9  call    __security_check_cookie
0x1400114ee  add     rsp, 58h
0x1400114f2  retn
```
