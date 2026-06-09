# Windows::Tracing::RtlFormatIntoStream<ulong,ulong>(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,ulong const &,ulong const &)

- ea: `0x140015fe4`
- end: `0x140016034`
- name: `??$RtlFormatIntoStream@KK@Tracing@Windows@@YAXPEAUIRtlFormattedOutputStream@Rtl@1@QEBDAEBK2@Z`
- size: `80`
- prototype: `void __fastcall(Windows::WCP::Rtl *, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x140015b78`

## callees

- `0x1400270d4`

## string_xrefs

- `0x140015ffa`: `Lock: Error found, LeaveCriticalSection is called by the wrong thread. Owner thread: {}, current thread: {}`

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
  v4[1] = _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_;
  v4[5] = a4;
  v4[4] = _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_;
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
0x140015fe4  mov     r11, rsp
0x140015fe7  sub     rsp, 58h
0x140015feb  lea     rax, ?_lambda_invoker_cdecl_@_lambda_9c65d09bb3ede0a99c21ac1acdc8028c_@@CA@PEAUIRtlFormattedOutputStream@Rtl@Windows@@PEBX@Z; _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140015ff2  mov     [r11-28h], r8
0x140015ff6  mov     [r11-30h], rax
0x140015ffa  lea     rdx, aLockErrorFound_0; "Lock: Error found, LeaveCriticalSection"...
0x140016001  lea     rax, ?_lambda_invoker_cdecl_@_lambda_9c65d09bb3ede0a99c21ac1acdc8028c_@@CA@PEAUIRtlFormattedOutputStream@Rtl@Windows@@PEBX@Z; _lambda_9c65d09bb3ede0a99c21ac1acdc8028c_::_lambda_invoker_cdecl_(Windows::Rtl::IRtlFormattedOutputStream *,void const *)
0x140016008  mov     [r11-10h], r9
0x14001600c  lea     r9, [r11-38h]; unsigned __int64
0x140016010  mov     [r11-18h], rax
0x140016014  mov     r8d, 2; char *
0x14001601a  mov     qword ptr [r11-38h], 0
0x140016022  mov     qword ptr [r11-20h], 0
0x14001602a  call    ?RtlFormatIntoStreamFromParameterList@Rtl@WCP@Windows@@YAXPEAUIRtlFormattedOutputStream@13@QEBD_KQEBU_RTL_TRACING_PARAMETER@123@@Z; Windows::WCP::Rtl::RtlFormatIntoStreamFromParameterList(Windows::Rtl::IRtlFormattedOutputStream *,char const * const,unsigned __int64,Windows::WCP::Rtl::_RTL_TRACING_PARAMETER const * const)
0x14001602f  add     rsp, 58h
0x140016033  retn
```
