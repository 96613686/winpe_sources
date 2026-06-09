# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip::~CSkip(void)

- ea: `0x18000e914`
- end: `0x18000e919`
- name: `??1CSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(char **this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800284c2`

## callees

- `0x18000b534`

## pseudocode

```c
// attributes: thunk
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip::~CSkip(char **this)
{
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x18000e914  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
