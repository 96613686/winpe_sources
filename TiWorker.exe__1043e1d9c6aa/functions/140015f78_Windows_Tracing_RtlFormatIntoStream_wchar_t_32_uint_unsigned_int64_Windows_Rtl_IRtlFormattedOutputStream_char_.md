# Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,unsigned __int64>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,unsigned __int64 const &)

- ea: `0x140015f78`
- end: `0x140015fdb`
- name: `??$RtlFormatIntoStream@$$BY0CA@_WI_K@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEAY0CA@$$CB_WAEBIAEB_K@Z`
- size: `99`
- prototype: `void __fastcall(Windows::WCP::Rtl *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400159e8`

## callees

- `0x1400270d4`

## string_xrefs

- `0x140015fc6`: `Lock: Lock removed: {}, level: {}, total lock:{}`

## pseudocode

```c
void __fastcall Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,unsigned __int64>(
        Windows::WCP::Rtl *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        __int64 a5)
{
  _QWORD v5[11]; // [rsp+20h] [rbp-58h] BYREF

  v5[2] = a3;
  v5[1] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [260]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
  v5[4] = _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_;
  v5[7] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,unsigned __int64>'::`2'::_lambda_3_::_lambda_invoker_cdecl_;
  v5[3] = 0;
  v5[5] = a4;
  v5[6] = 0;
  v5[8] = a5;
  Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
    a1,
    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Lock: Lock removed: {}, level: {}, total lock:{}",
    (const char *const)3,
    (unsigned __int64)v5,
    0);
}

```

## disassembly

```asm
0x140015f78  mov     r11, rsp
0x140015f7b  sub     rsp, 78h
0x140015f7f  xor     edx, edx
0x140015f81  mov     [r11-48h], r8
0x140015f85  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@$$BY0BAE@_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0BAE@$$CB_W@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [260]>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[260])'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140015f8c  mov     [r11-58h], rdx
0x140015f90  mov     [r11-50h], rax
0x140015f94  lea     rax, ?_lambda_invoker_cdecl_@_lambda_9c65d09bb3ede0a99c21ac1acdc8028c_@@CA@PEAUIRtlFormattedOutputStream@Rtl@Windows@@PEBX@Z; _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140015f9b  mov     [r11-38h], rax
0x140015f9f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_3_@?1???$RtlFormatIntoStream@$$BY0CA@_WI_K@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_WAEBIAEB_K@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,unsigned __int64>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,unsigned __int64 const &)'::`2'::_lambda_3_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140015fa6  mov     [r11-20h], rax
0x140015faa  lea     r8d, [rdx+3]; char *
0x140015fae  mov     rax, [rsp+78h+arg_20]
0x140015fb6  mov     [r11-40h], rdx
0x140015fba  mov     [r11-30h], r9
0x140015fbe  lea     r9, [r11-58h]; unsigned __int64
0x140015fc2  mov     [r11-28h], rdx
0x140015fc6  lea     rdx, aLockLockRemove; "Lock: Lock removed: {}, level: {}, tota"...
0x140015fcd  mov     [r11-18h], rax
0x140015fd1  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140015fd6  add     rsp, 78h
0x140015fda  retn
```
