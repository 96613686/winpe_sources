# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x18000ad9c`
- end: `0x18000ada7`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `11`
- prototype: `void __fastcall(LPVOID *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003a91a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000ada0`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x18000ad9c  mov     rcx, [rcx+8]
0x18000ada0  jmp     cs:__imp_CoTaskMemFree
```
