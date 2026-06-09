# std::filesystem::path::~path(void)

- ea: `0x180002850`
- end: `0x180002855`
- name: `??1path@filesystem@std@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(std::filesystem::path *__hidden this)`
- caller_count: `64`
- callee_count: `1`
- tags: ``

## callers

- `0x18001eb00`
- `0x18003ca70`
- `0x18003d118`
- `0x18003d124`
- `0x18003d130`
- `0x18003d154`
- `0x18003d160`
- `0x18003d16c`
- `0x18003d178`
- `0x18003d1a1`
- `0x18003d2a2`
- `0x18003d2e0`
- `0x18003d2ec`
- `0x18003d360`
- `0x18003d4de`
- `0x18003d51a`
- `0x18003d570`
- `0x18003d5ec`
- `0x18003d750`
- `0x18003e2bd`
- `0x18003e2c9`
- `0x18003e2d5`
- `0x18003e330`
- `0x18003e35c`
- `0x18003e368`
- `0x18003e374`
- `0x18003e380`
- `0x18003e3a0`
- `0x18003e3b0`
- `0x18003e3e0`
- `0x18003e880`
- `0x18003e8a6`
- `0x18003e8d0`
- `0x18003e920`
- `0x18003e9fc`
- `0x18003ea68`
- `0x18003ea74`
- `0x18003ea80`
- `0x18003eaa0`
- `0x18003eaac`
- `0x18003eab8`
- `0x18003eb48`
- `0x18003eca0`
- `0x18003ed5c`
- `0x18003f0b4`
- `0x18003f0c0`
- `0x18003f0cc`
- `0x18003f0d8`
- `0x18003f220`
- `0x18003f249`

## callees

- `0x1800027d0`

## pseudocode

```c
// attributes: thunk
void __fastcall std::filesystem::path::~path(std::filesystem::path *this)
{
  std::wstring::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x180002850  jmp     ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
```
