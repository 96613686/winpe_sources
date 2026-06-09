# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::~CLocalNtImagePathDecoder(void)

- ea: `0x180009e6c`
- end: `0x180009e71`
- name: `??1CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CLocalNtImagePathDecoder *__hidden this)`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x180027ee8`
- `0x180028373`
- `0x180028ccb`

## callees

- `0x1800134a8`

## pseudocode

```c
// attributes: thunk
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::~CLocalNtImagePathDecoder(void **this)
{
  Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(this);
}

```

## disassembly

```asm
0x180009e6c  jmp     ??1CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ; Performance::NtImagePathDecoder::CNtImagePathDecoderBase::~CNtImagePathDecoderBase(void)
```
