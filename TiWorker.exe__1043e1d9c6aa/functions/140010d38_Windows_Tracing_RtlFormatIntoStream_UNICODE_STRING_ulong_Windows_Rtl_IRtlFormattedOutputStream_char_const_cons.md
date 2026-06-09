# Windows::Tracing::RtlFormatIntoStream<_UNICODE_STRING,ulong>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,_UNICODE_STRING const &,ulong const &)

- ea: `0x140010d38`
- end: `0x140010d88`
- name: `??$RtlFormatIntoStream@U_UNICODE_STRING@@K@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBU_UNICODE_STRING@@AEBK@Z`
- size: `80`
- prototype: `void __fastcall(Windows::WCP::Rtl *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140010acc`

## callees

- `0x1400270d4`

## string_xrefs

- `0x140010d4e`: `  Key Handle for: {}, has Access: {}`

## pseudocode

```c
void __fastcall Windows::Tracing::RtlFormatIntoStream<_UNICODE_STRING,unsigned long>(
        Windows::WCP::Rtl *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD v4[7]; // [rsp+20h] [rbp-38h] BYREF

  v4[2] = a3;
  v4[1] = `Windows::Tracing::RtlFormatIntoStream<_UNICODE_STRING,unsigned long>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
  v4[5] = a4;
  v4[4] = _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_;
  v4[3] = 0;
  Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
    a1,
    (struct Windows::Rtl::IRtlFormattedOutputStream *)"  Key Handle for: {}, has Access: {}",
    (const char *const)2,
    (unsigned __int64)v4,
    0);
}

```

## disassembly

```asm
0x140010d38  mov     r11, rsp
0x140010d3b  sub     rsp, 58h
0x140010d3f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@U_UNICODE_STRING@@K@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEBU_UNICODE_STRING@@AEBK@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<_UNICODE_STRING,ulong>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,_UNICODE_STRING const &,ulong const &)'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140010d46  mov     [r11-28h], r8
0x140010d4a  mov     [r11-30h], rax
0x140010d4e  lea     rdx, aKeyHandleForHa; "  Key Handle for: {}, has Access: {}"
0x140010d55  lea     rax, ?_lambda_invoker_cdecl_@_lambda_9c65d09bb3ede0a99c21ac1acdc8028c_@@CA@PEAUIRtlFormattedOutputStream@Rtl@Windows@@PEBX@Z; _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140010d5c  mov     [r11-10h], r9
0x140010d60  lea     r9, [r11-38h]; unsigned __int64
0x140010d64  mov     [r11-18h], rax
0x140010d68  mov     r8d, 2; char *
0x140010d6e  mov     qword ptr [r11-38h], 0
0x140010d76  mov     qword ptr [r11-20h], 0
0x140010d7e  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140010d83  add     rsp, 58h
0x140010d87  retn
```
