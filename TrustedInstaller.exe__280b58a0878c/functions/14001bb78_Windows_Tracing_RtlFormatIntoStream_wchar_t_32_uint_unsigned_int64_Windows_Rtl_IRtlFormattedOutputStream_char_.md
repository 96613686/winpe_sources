# Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,unsigned __int64>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,unsigned __int64 const &)

- ea: `0x14001bb78`
- end: `0x14001bbdb`
- name: `??$RtlFormatIntoStream@$$BY0CA@_WI_K@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEAY0CA@$$CB_WAEBIAEB_K@Z`
- size: `99`
- prototype: `void __fastcall(Windows::WCP::Rtl *, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b5e8`

## callees

- `0x140026e04`

## string_xrefs

- `0x14001bbc6`: `Lock: Lock removed: {}, level: {}, total lock:{}`

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
  v5[1] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
  v5[4] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,wchar_t [32],unsigned int>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
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
0x14001bb78  mov     r11, rsp
0x14001bb7b  sub     rsp, 78h
0x14001bb7f  xor     edx, edx
0x14001bb81  mov     [r11-48h], r8
0x14001bb85  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@$$BY0CA@_W$$BY0CA@_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_W2@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],wchar_t const (&)[32])'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bb8c  mov     [r11-58h], rdx
0x14001bb90  mov     [r11-50h], rax
0x14001bb94  lea     rax, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlFormatIntoStream@$$BY0CA@_WI$$BY0CA@_WI@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_WAEBI23@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,wchar_t [32],uint>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bb9b  mov     [r11-38h], rax
0x14001bb9f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_3_@?1???$RtlFormatIntoStream@$$BY0CA@_WI_K@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_WAEBIAEB_K@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,unsigned __int64>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,unsigned __int64 const &)'::`2'::_lambda_3_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bba6  mov     [r11-20h], rax
0x14001bbaa  lea     r8d, [rdx+3]; char *
0x14001bbae  mov     rax, [rsp+78h+arg_20]
0x14001bbb6  mov     [r11-40h], rdx
0x14001bbba  mov     [r11-30h], r9
0x14001bbbe  lea     r9, [r11-58h]; unsigned __int64
0x14001bbc2  mov     [r11-28h], rdx
0x14001bbc6  lea     rdx, aLockLockRemove; "Lock: Lock removed: {}, level: {}, tota"...
0x14001bbcd  mov     [r11-18h], rax
0x14001bbd1  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x14001bbd6  add     rsp, 78h
0x14001bbda  retn
```
