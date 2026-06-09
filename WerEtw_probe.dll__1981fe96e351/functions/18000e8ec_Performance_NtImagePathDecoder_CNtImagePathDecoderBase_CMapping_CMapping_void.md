# Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(void)

- ea: `0x18000e8ec`
- end: `0x18000e90b`
- name: `??1CMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18002848c`

## callees

- `0x18000b534`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping::~CMapping(char **this)
{
  std::wstring::~wstring(this + 4);
  std::wstring::~wstring(this);
}

```

## disassembly

```asm
0x18000e8ec  push    rbx
0x18000e8ee  sub     rsp, 20h
0x18000e8f2  mov     rbx, rcx
0x18000e8f5  add     rcx, 20h ; ' '
0x18000e8f9  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e8fe  mov     rcx, rbx
0x18000e901  add     rsp, 20h
0x18000e905  pop     rbx
0x18000e906  jmp     ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
```
