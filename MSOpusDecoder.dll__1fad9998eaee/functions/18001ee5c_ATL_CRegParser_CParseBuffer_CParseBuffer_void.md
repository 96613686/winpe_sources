# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x18001ee5c`
- end: `0x18001ee67`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(ATL::CRegParser::CParseBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18002312d`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001ee60`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x18001ee5c  mov     rcx, [rcx+8]
0x18001ee60  jmp     cs:__imp_CoTaskMemFree
```
