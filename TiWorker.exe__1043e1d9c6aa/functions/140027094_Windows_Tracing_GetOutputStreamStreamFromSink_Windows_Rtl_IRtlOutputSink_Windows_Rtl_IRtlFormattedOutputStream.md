# Windows::Tracing::GetOutputStreamStreamFromSink(Windows::Rtl::IRtlOutputSink *,Windows::Rtl::IRtlFormattedOutputStream * *)

- ea: `0x140027094`
- end: `0x1400270cc`
- name: `?GetOutputStreamStreamFromSink@Tracing@Windows@@YAXPEAUIRtlOutputSink@Rtl@2@PEAPEAUIRtlFormattedOutputStream@42@@Z`
- size: `56`
- prototype: `void __fastcall(Windows::Tracing *__hidden this, struct Windows::Rtl::IRtlOutputSink *, struct Windows::Rtl::IRtlFormattedOutputStream **)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x140006810`

## callees

- `0x140001fa0`
- `0x140026f28`
- `0x140027094`

## pseudocode

```c
void __fastcall Windows::Tracing::GetOutputStreamStreamFromSink(
        Windows::Tracing *this,
        struct Windows::Rtl::IRtlOutputSink *a2,
        struct Windows::Rtl::IRtlFormattedOutputStream **a3)
{
  Windows::WCP::Implementation::Rtl::CBaseTracingStream *v5; // rax
  bool v6; // r8

  v5 = (Windows::WCP::Implementation::Rtl::CBaseTracingStream *)operator new(0x890u);
  if ( v5 )
    v5 = (Windows::WCP::Implementation::Rtl::CBaseTracingStream *)Windows::WCP::Implementation::Rtl::CBaseTracingStream::CBaseTracingStream(
                                                                    v5,
                                                                    this,
                                                                    v6);
  *(_QWORD *)a2 = v5;
}

```

## disassembly

```asm
0x140027094  mov     [rsp+arg_0], rbx
0x140027099  push    rdi
0x14002709a  sub     rsp, 20h
0x14002709e  mov     rdi, rcx
0x1400270a1  mov     rbx, rdx
0x1400270a4  mov     ecx, 890h; Size
0x1400270a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400270ae  test    rax, rax
0x1400270b1  jz      short loc_1400270BE
0x1400270b3  mov     rdx, rdi; struct Windows::Rtl::IRtlOutputSink *
0x1400270b6  mov     rcx, rax; this
0x1400270b9  call    ??0CBaseTracingStream@Rtl@Implementation@WCP@Windows@@QEAA@PEAUIRtlOutputSink@14@_N@Z; Windows::WCP::Implementation::Rtl::CBaseTracingStream::CBaseTracingStream(Windows::Rtl::IRtlOutputSink *,bool)
0x1400270be  mov     [rbx], rax
0x1400270c1  mov     rbx, [rsp+28h+arg_0]
0x1400270c6  add     rsp, 20h
0x1400270ca  pop     rdi
0x1400270cb  retn
```
