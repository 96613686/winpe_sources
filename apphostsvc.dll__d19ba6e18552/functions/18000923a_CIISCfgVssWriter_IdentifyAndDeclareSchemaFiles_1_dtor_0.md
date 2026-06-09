# _CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor$0

- ea: `0x18000923a`
- end: `0x180009248`
- name: `_CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor$0`
- size: `14`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: ``

## import_xrefs

- `iisutil!??1STRU_PATH@@QEAA@XZ` at `0x180009241`

## pseudocode

```c
void __fastcall CIISCfgVssWriter::IdentifyAndDeclareSchemaFiles_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  STRU_PATH::~STRU_PATH((STRU_PATH *)(a2 + 192));
}

```

## disassembly

```asm
0x18000923a  lea     rcx, [rdx+0C0h]
0x180009241  jmp     cs:__imp_??1STRU_PATH@@QEAA@XZ; STRU_PATH::~STRU_PATH(void)
```
