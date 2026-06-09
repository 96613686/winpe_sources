# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x140011450`
- end: `0x14001149b`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `75`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int, unsigned int)`
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
bool __fastcall wil::details_abi::UsageIndex<enum wil_details_ServiceReportingKind,unsigned int,2>::RecordUsage(
        wil::details_abi::RawUsageIndex *a1,
        int a2,
        int a3,
        unsigned int a4)
{
  int v5; // [rsp+30h] [rbp-28h] BYREF
  int v6; // [rsp+38h] [rbp-20h] BYREF

  v6 = a2;
  v5 = a3;
  return wil::details_abi::RawUsageIndex::RecordUsage(a1, &v6, 4u, &v5, 4u, a4);
}

```

## disassembly

```asm
0x140011450  mov     r11, rsp
0x140011453  sub     rsp, 58h
0x140011457  mov     rax, cs:__security_cookie
0x14001145e  xor     rax, rsp
0x140011461  mov     [rsp+58h+var_18], rax
0x140011466  mov     [rsp+58h+var_20], edx
0x14001146a  lea     rdx, [r11-20h]; Buf1
0x14001146e  mov     [r11-30h], r9d
0x140011472  lea     r9, [r11-28h]; void *
0x140011476  mov     [r11-28h], r8d
0x14001147a  mov     r8d, 4; Size
0x140011480  mov     [r11-38h], r8
0x140011484  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x140011489  mov     rcx, [rsp+58h+var_18]
0x14001148e  xor     rcx, rsp; StackCookie
0x140011491  call    __security_check_cookie
0x140011496  add     rsp, 58h
0x14001149a  retn
```
