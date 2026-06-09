# Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::~CLocalNtImagePathDecoder(void)

- ea: `0x18000e8b4`
- end: `0x18000e8e5`
- name: `??1CLocalNtImagePathDecoder@NtImagePathDecoder@Performance@@QEAA@XZ`
- size: `49`
- prototype: `void __fastcall(char **this)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x18002803a`
- `0x180028112`
- `0x18002887d`

## callees

- `0x18000b534`
- `0x18000e3d0`
- `0x18000e474`

## pseudocode

```c
void __fastcall Performance::NtImagePathDecoder::CLocalNtImagePathDecoder::~CLocalNtImagePathDecoder(char **this)
{
  std::wstring::~wstring(this + 10);
  std::wstring::~wstring(this + 6);
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>((__int64)(this + 3));
  std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>((__int64)this);
}

```

## disassembly

```asm
0x18000e8b4  push    rbx
0x18000e8b6  sub     rsp, 20h
0x18000e8ba  mov     rbx, rcx
0x18000e8bd  add     rcx, 50h ; 'P'
0x18000e8c1  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e8c6  lea     rcx, [rbx+30h]
0x18000e8ca  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18000e8cf  lea     rcx, [rbx+18h]
0x18000e8d3  call    ??1?$vector@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCSkip@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CSkip>(void)
0x18000e8d8  mov     rcx, rbx
0x18000e8db  add     rsp, 20h
0x18000e8df  pop     rbx
0x18000e8e0  jmp     ??1?$vector@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@V?$allocator@UCMapping@CNtImagePathDecoderBase@NtImagePathDecoder@Performance@@@std@@@std@@QEAA@XZ; std::vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>::~vector<Performance::NtImagePathDecoder::CNtImagePathDecoderBase::CMapping>(void)
```
