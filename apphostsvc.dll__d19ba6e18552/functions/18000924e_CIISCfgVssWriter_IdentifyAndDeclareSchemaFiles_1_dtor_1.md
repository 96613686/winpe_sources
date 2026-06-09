# _CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor$1

- ea: `0x18000924e`
- end: `0x18000925c`
- name: `_CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor$1`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x180009255`

## pseudocode

```c
void __fastcall CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 136));
}

```

## disassembly

```asm
0x18000924e  lea     rcx, [rdx+88h]
0x180009255  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
