# ComScope::~ComScope(void)

- ea: `0x18000b364`
- end: `0x18000b36b`
- name: `??1ComScope@@QEAA@XZ`
- size: `7`
- prototype: `void __stdcall()`
- caller_count: `1`
- callee_count: `0`
- tags: `broker_com_uri`

## callers

- `0x180017b4a`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18000b364`

## pseudocode

```c
// attributes: thunk
void __stdcall ComScope::~ComScope()
{
  CoUninitialize();
}

```

## disassembly

```asm
0x18000b364  jmp     cs:__imp_CoUninitialize
```
