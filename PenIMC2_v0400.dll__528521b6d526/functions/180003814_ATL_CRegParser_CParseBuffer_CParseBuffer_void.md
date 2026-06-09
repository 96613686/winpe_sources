# ATL::CRegParser::CParseBuffer::~CParseBuffer(void)

- ea: `0x180003814`
- end: `0x180003828`
- name: `??1CParseBuffer@CRegParser@ATL@@QEAA@XZ`
- size: `20`
- prototype: `void __fastcall(ATL::CRegParser::CParseBuffer *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x18000e7ba`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18000381c`
- `ole32!CoTaskMemFree` at `0x18000381c`

## pseudocode

```c
void __fastcall ATL::CRegParser::CParseBuffer::~CParseBuffer(LPVOID *this)
{
  CoTaskMemFree(this[1]);
}

```

## disassembly

```asm
0x180003814  sub     rsp, 28h
0x180003818  mov     rcx, [rcx+8]; pv
0x18000381c  call    cs:__imp_CoTaskMemFree
0x180003822  nop
0x180003823  add     rsp, 28h
0x180003827  retn
```
