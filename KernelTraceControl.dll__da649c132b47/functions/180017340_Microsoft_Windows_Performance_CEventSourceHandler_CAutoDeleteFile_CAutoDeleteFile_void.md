# Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(void)

- ea: `0x180017340`
- end: `0x18001734a`
- name: `??1CAutoDeleteFile@CEventSourceHandler@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800291f6`

## import_xrefs

- `KERNEL32!DeleteFileW` at `0x180017343`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(LPCWSTR *this)
{
  DeleteFileW(*this);
}

```

## disassembly

```asm
0x180017340  mov     rcx, [rcx]
0x180017343  jmp     cs:__imp_DeleteFileW
```
