# Windows::Tracing::RtlFormatIntoStream<ulong,ulong>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,ulong const &,ulong const &)

- ea: `0x14001bbe4`
- end: `0x14001bc34`
- name: `??$RtlFormatIntoStream@KK@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBK2@Z`
- size: `80`
- prototype: `void __fastcall(Windows::WCP::Rtl *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b778`

## callees

- `0x140026e04`

## string_xrefs

- `0x14001bbfa`: `Lock: Error found, LeaveCriticalSection is called by the wrong thread. Owner thread: {}, current thread: {}`

## pseudocode

```c
void __fastcall Windows::Tracing::RtlFormatIntoStream<unsigned long,unsigned long>(
        Windows::WCP::Rtl *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4)
{
  _QWORD v4[7]; // [rsp+20h] [rbp-38h] BYREF

  v4[2] = a3;
  v4[1] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,wchar_t [32],unsigned int>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
  v4[5] = a4;
  v4[4] = `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,wchar_t [32],unsigned int>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
  v4[3] = 0;
  Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
    a1,
    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Lock: Error found, LeaveCriticalSection is called by the wrong thr"
                                                      "ead. Owner thread: {}, current thread: {}",
    (const char *const)2,
    (unsigned __int64)v4,
    0);
}

```

## disassembly

```asm
0x14001bbe4  mov     r11, rsp
0x14001bbe7  sub     rsp, 58h
0x14001bbeb  lea     rax, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlFormatIntoStream@$$BY0CA@_WI$$BY0CA@_WI@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_WAEBI23@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,wchar_t [32],uint>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bbf2  mov     [r11-28h], r8
0x14001bbf6  mov     [r11-30h], rax
0x14001bbfa  lea     rdx, aLockErrorFound_0; "Lock: Error found, LeaveCriticalSection"...
0x14001bc01  lea     rax, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlFormatIntoStream@$$BY0CA@_WI$$BY0CA@_WI@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_WAEBI23@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,wchar_t [32],uint>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bc08  mov     [r11-10h], r9
0x14001bc0c  lea     r9, [r11-38h]; unsigned __int64
0x14001bc10  mov     [r11-18h], rax
0x14001bc14  mov     r8d, 2; char *
0x14001bc1a  mov     qword ptr [r11-38h], 0
0x14001bc22  mov     qword ptr [r11-20h], 0
0x14001bc2a  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x14001bc2f  add     rsp, 58h
0x14001bc33  retn
```
