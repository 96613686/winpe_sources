# std::unique_ptr<SpeechMicDiagnostic::CaptureStream,std::default_delete<SpeechMicDiagnostic::CaptureStream>>::~unique_ptr<SpeechMicDiagnostic::CaptureStream,std::default_delete<SpeechMicDiagnostic::CaptureStream>>(void)

- ea: `0x1800076cc`
- end: `0x1800076f6`
- name: `??1?$unique_ptr@VCaptureStream@SpeechMicDiagnostic@@U?$default_delete@VCaptureStream@SpeechMicDiagnostic@@@std@@@std@@QEAA@XZ`
- size: `42`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800106de`

## callees

- `0x180002ce0`
- `0x1800076cc`
- `0x18000dc0c`

## pseudocode

```c
void __fastcall std::unique_ptr<SpeechMicDiagnostic::CaptureStream>::~unique_ptr<SpeechMicDiagnostic::CaptureStream>(
        SpeechMicDiagnostic::CaptureStream **a1)
{
  SpeechMicDiagnostic::CaptureStream *v1; // rbx

  v1 = *a1;
  if ( *a1 )
  {
    SpeechMicDiagnostic::CaptureStream::~CaptureStream(*a1);
    operator delete(v1);
  }
}

```

## disassembly

```asm
0x1800076cc  push    rbx
0x1800076ce  sub     rsp, 20h
0x1800076d2  mov     rbx, [rcx]
0x1800076d5  test    rbx, rbx
0x1800076d8  jz      short loc_1800076EF
0x1800076da  mov     rcx, rbx; this
0x1800076dd  call    ??1CaptureStream@SpeechMicDiagnostic@@QEAA@XZ; SpeechMicDiagnostic::CaptureStream::~CaptureStream(void)
0x1800076e2  mov     edx, 0D0h; unsigned __int64
0x1800076e7  mov     rcx, rbx; void *
0x1800076ea  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800076ef  add     rsp, 20h
0x1800076f3  pop     rbx
0x1800076f4  retn
```
