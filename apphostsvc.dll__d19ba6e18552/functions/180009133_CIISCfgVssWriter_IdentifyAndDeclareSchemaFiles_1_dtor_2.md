# _CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor$2

- ea: `0x180009133`
- end: `0x180009141`
- name: `_CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor$2`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU@@QEAA@XZ` at `0x18000913a`

## pseudocode

```c
void __fastcall CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor_2(__int64 a1, __int64 a2)
{
  STRU::~STRU((STRU *)(a2 + 80));
}

```

## disassembly

```asm
0x180009133  lea     rcx, [rdx+50h]
0x18000913a  jmp     cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
```
