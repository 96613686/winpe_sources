# wil::details_abi::UsageIndex<wil_details_ServiceReportingKind,uint,2>::RecordUsage(wil_details_ServiceReportingKind,uint,uint)

- ea: `0x180007954`
- end: `0x18000799f`
- name: `?RecordUsage@?$UsageIndex@W4wil_details_ServiceReportingKind@@I$01@details_abi@wil@@QEAA_NW4wil_details_ServiceReportingKind@@II@Z`
- size: `75`
- prototype: `bool __fastcall(wil::details_abi::RawUsageIndex *, int, int, unsigned int)`
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
0x180007954  mov     r11, rsp
0x180007957  sub     rsp, 58h
0x18000795b  mov     rax, cs:__security_cookie
0x180007962  xor     rax, rsp
0x180007965  mov     [rsp+58h+var_18], rax
0x18000796a  mov     [rsp+58h+var_20], edx
0x18000796e  lea     rdx, [r11-20h]; Buf1
0x180007972  mov     [r11-30h], r9d
0x180007976  lea     r9, [r11-28h]; void *
0x18000797a  mov     [r11-28h], r8d
0x18000797e  mov     r8d, 4; Size
0x180007984  mov     [r11-38h], r8
0x180007988  call    ?RecordUsage@RawUsageIndex@details_abi@wil@@QEAA_NPEAX_K01I@Z; wil::details_abi::RawUsageIndex::RecordUsage(void *,unsigned __int64,void *,unsigned __int64,uint)
0x18000798d  mov     rcx, [rsp+58h+var_18]
0x180007992  xor     rcx, rsp; StackCookie
0x180007995  call    __security_check_cookie
0x18000799a  add     rsp, 58h
0x18000799e  retn
```
