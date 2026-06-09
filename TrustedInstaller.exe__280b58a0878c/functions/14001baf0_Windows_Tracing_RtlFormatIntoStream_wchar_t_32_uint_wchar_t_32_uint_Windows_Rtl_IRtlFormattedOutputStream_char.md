# Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,wchar_t [32],uint>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)

- ea: `0x14001baf0`
- end: `0x14001bb6f`
- name: `??$RtlFormatIntoStream@$$BY0CA@_WI$$BY0CA@_WI@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEAY0CA@$$CB_WAEBI23@Z`
- size: `127`
- prototype: `void __fastcall(Windows::WCP::Rtl *, __int64, unsigned __int64, unsigned __int64, unsigned __int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x14001b43c`

## callees

- `0x140026e04`

## string_xrefs

- `0x14001bb56`: `Lock: Error found, inverse lock order, current lock held: {}, level: {}, lock attempted: {},  level: {}. This will lead to a potential deadlock`

## pseudocode

```c
void __fastcall Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,wchar_t [32],unsigned int>(
        Windows::WCP::Rtl *a1,
        __int64 a2,
        unsigned __int64 a3,
        unsigned __int64 a4,
        unsigned __int64 a5,
        unsigned __int64 a6)
{
  unsigned __int64 v6[12]; // [rsp+20h] [rbp-60h] BYREF

  v6[2] = a3;
  v6[1] = (unsigned __int64)`Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
  v6[4] = (unsigned __int64)`Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,wchar_t [32],unsigned int>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
  v6[7] = (unsigned __int64)`Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>'::`2'::_lambda_1_::_lambda_invoker_cdecl_;
  v6[8] = a5;
  v6[10] = (unsigned __int64)`Windows::Tracing::RtlFormatIntoStream<wchar_t [32],unsigned int,wchar_t [32],unsigned int>'::`2'::_lambda_2_::_lambda_invoker_cdecl_;
  v6[3] = 0;
  v6[5] = a4;
  v6[6] = 0;
  v6[9] = 0;
  v6[11] = a6;
  Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(
    a1,
    (struct Windows::Rtl::IRtlFormattedOutputStream *)"Lock: Error found, inverse lock order, current lock held: {}, leve"
                                                      "l: {}, lock attempted: {},  level: {}. This will lead to a potential deadlock",
    (const char *const)4,
    (unsigned __int64)v6,
    0);
}

```

## disassembly

```asm
0x14001baf0  push    rbp
0x14001baf2  mov     rbp, rsp
0x14001baf5  sub     rsp, 80h
0x14001bafc  xor     edx, edx
0x14001bafe  mov     [rbp+var_50], r8
0x14001bb02  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@$$BY0CA@_W$$BY0CA@_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_W2@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],wchar_t const (&)[32])'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bb09  mov     [rbp+var_60], rdx
0x14001bb0d  mov     [rbp+var_58], rax
0x14001bb11  lea     rax, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlFormatIntoStream@$$BY0CA@_WI$$BY0CA@_WI@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_WAEBI23@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,wchar_t [32],uint>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bb18  mov     [rbp+var_40], rax
0x14001bb1c  lea     rax, ?_lambda_invoker_cdecl_@_lambda_1_@?1???$RtlFormatIntoStream@$$BY0CA@_W$$BY0CA@_W@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_W2@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],wchar_t [32]>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],wchar_t const (&)[32])'::`2'::_lambda_1_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bb23  mov     [rbp+var_28], rax
0x14001bb27  lea     r8d, [rdx+4]; char *
0x14001bb2b  mov     rax, [rbp+arg_20]
0x14001bb2f  mov     [rbp+var_20], rax
0x14001bb33  lea     rax, ?_lambda_invoker_cdecl_@_lambda_2_@?1???$RtlFormatIntoStream@$$BY0CA@_WI$$BY0CA@_WI@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@3@QEBDAEAY0CA@$$CB_WAEBI23@Z@SA@0PEBX@Z; `Windows::Tracing::RtlFormatIntoStream<wchar_t [32],uint,wchar_t [32],uint>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,wchar_t const (&)[32],uint const &,wchar_t const (&)[32],uint const &)'::`2'::_lambda_2_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x14001bb3a  mov     [rbp+var_10], rax
0x14001bb3e  mov     rax, [rbp+arg_28]
0x14001bb42  mov     [rbp+var_48], rdx
0x14001bb46  mov     [rbp+var_38], r9
0x14001bb4a  lea     r9, [rbp+var_60]; unsigned __int64
0x14001bb4e  mov     [rbp+var_30], rdx
0x14001bb52  mov     [rbp+var_18], rdx
0x14001bb56  lea     rdx, aLockErrorFound; "Lock: Error found, inverse lock order, "...
0x14001bb5d  mov     [rbp+var_8], rax
0x14001bb61  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x14001bb66  add     rsp, 80h
0x14001bb6d  pop     rbp
0x14001bb6e  retn
```
