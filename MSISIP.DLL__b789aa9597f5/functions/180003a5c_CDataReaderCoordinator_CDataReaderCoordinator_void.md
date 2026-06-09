# CDataReaderCoordinator::~CDataReaderCoordinator(void)

- ea: `0x180003a5c`
- end: `0x180003a61`
- name: `??1CDataReaderCoordinator@@QEAA@XZ`
- size: `5`
- prototype: `void __fastcall(CDataReaderCoordinator *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x18000d4f0`

## callees

- `0x1800044b0`

## pseudocode

```c
// attributes: thunk
void __fastcall CDataReaderCoordinator::~CDataReaderCoordinator(CDataReaderCoordinator *this)
{
  CDataReaderCoordinator::ReleaseResources(this);
}

```

## disassembly

```asm
0x180003a5c  jmp     ?ReleaseResources@CDataReaderCoordinator@@QEAAXXZ; CDataReaderCoordinator::ReleaseResources(void)
```
