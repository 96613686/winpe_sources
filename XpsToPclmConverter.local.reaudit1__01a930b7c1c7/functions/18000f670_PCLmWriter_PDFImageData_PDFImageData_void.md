# PCLmWriter::PDFImageData::~PDFImageData(void)

- ea: `0x18000f670`
- end: `0x18000f675`
- name: `??1PDFImageData@PCLmWriter@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(PCLmWriter::PDFImageData *__hidden this)`
- caller_count: `49`
- callee_count: `1`
- tags: ``

## callers

- `0x18001d416`
- `0x18001d43a`
- `0x18001d5ea`
- `0x18001d730`
- `0x18001d754`
- `0x18001d87d`
- `0x18001d8a1`
- `0x18001da1b`
- `0x18001da2d`
- `0x18001dacf`
- `0x18001db5f`
- `0x18001dbb9`
- `0x18001dc54`
- `0x18001dc66`
- `0x18001dc78`
- `0x18001dc8a`
- `0x18001dc9c`
- `0x18001dcae`
- `0x18001dcc0`
- `0x18001dcd2`
- `0x18001dce4`
- `0x18001dcf6`
- `0x18001dd08`
- `0x18001dd1a`
- `0x18001dd2c`
- `0x18001dd3e`
- `0x18001dd50`
- `0x18001dd62`
- `0x18001dd74`
- `0x18001dd86`
- `0x18001dd98`
- `0x18001ddaa`
- `0x18001ddbc`
- `0x18001ddce`
- `0x18001dde0`
- `0x18001ddf2`
- `0x18001de04`
- `0x18001de16`
- `0x18001de28`
- `0x18001de3a`
- `0x18001de4c`
- `0x18001de5e`
- `0x18001de70`
- `0x18001dea6`
- `0x18001df4a`
- `0x18001df5c`
- `0x18001df6e`
- `0x18001e063`
- `0x18001e087`

## callees

- `0x180010718`

## pseudocode

```c
// attributes: thunk
void __fastcall PCLmWriter::PDFImageData::~PDFImageData(PCLmWriter::PDFImageData *this)
{
  std::string::_Tidy_deallocate(this);
}

```

## disassembly

```asm
0x18000f670  jmp     ?_Tidy_deallocate@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEAAXXZ; std::string::_Tidy_deallocate(void)
```
