# Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],wchar_t const (&)[32])

- ea: `0x140015e98`
- end: `0x140015ee8`
- name: `??$RtlFormatIntoStream@$$BY0CA@_W$$BY0CA@_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEAY0CA@$$CB_W2@Z`
- size: `80`
- prototype: `void __fastcall(Windows::WCP::Rtl *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1400156ac`

## callees

- `0x1400270d4`

## string_xrefs

- `0x140015eae`: `Lock: Warning: Current thread already holds lock: '{}', and is trying to acquire lock: '{}'`

## pseudocode

```c
void __fastcall Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>(
        Windows::WCP::Rtl *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD v4[7]; // [rsp+20h] [rbp-38h] BYREF

  v4[2] = a3;
  v4[1] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [260]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
  v4[5] = a4;
  v4[4] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [260]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
  v4[3] = 0;
  Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
    a1,
    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Lock: Warning: Current thread already holds lock: '{}', and is try"
                                                      "ing to acquire lock: '{}'",
    (const char *const)2,
    (unsigned __int64)v4,
    0);
}

```

## disassembly

```asm
0x140015e98  mov     r11, rsp
0x140015e9b  sub     rsp, 58h
0x140015e9f  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@$$BY0BAE@_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0BAE@$$CB_W@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [260]>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[260])'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140015ea6  mov     [r11-28h], r8
0x140015eaa  mov     [r11-30h], rax
0x140015eae  lea     rdx, aLockWarningCur; "Lock: Warning: Current thread already h"...
0x140015eb5  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@$$BY0BAE@_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0BAE@$$CB_W@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [260]>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[260])'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140015ebc  mov     [r11-10h], r9
0x140015ec0  lea     r9, [r11-38h]; unsigned __int64
0x140015ec4  mov     [r11-18h], rax
0x140015ec8  mov     r8d, 2; char *
0x140015ece  mov     qword ptr [r11-38h], 0
0x140015ed6  mov     qword ptr [r11-20h], 0
0x140015ede  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x140015ee3  add     rsp, 58h
0x140015ee7  retn
```
