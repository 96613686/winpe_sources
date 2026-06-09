# _SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$0

- ea: `0x1800106a8`
- end: `0x1800106c6`
- name: `_SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor$0`
- size: `30`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180002ce0`

## pseudocode

```c
void __fastcall SpeechMicDiagnostic::CSpeechMicDiagnostic::CreateInstance_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  operator delete(*(void **)(a2 + 48));
}

```

## disassembly

```asm
0x1800106a8  push    rbp
0x1800106aa  sub     rsp, 20h
0x1800106ae  mov     rbp, rdx
0x1800106b1  mov     edx, 38h ; '8'; unsigned __int64
0x1800106b6  mov     rcx, [rbp+30h]; void *
0x1800106ba  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1800106bf  add     rsp, 20h
0x1800106c3  pop     rbp
0x1800106c4  retn
```
