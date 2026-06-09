# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x180012434`
- end: `0x18001243f`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x1800334d2`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x180012438`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x180012434  mov     rcx, [rcx+8]
0x180012438  jmp     cs:__imp_CoTaskMemFree
```
