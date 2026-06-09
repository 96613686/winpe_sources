# Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(void)

- ea: `0x18002c920`
- end: `0x18002c92a`
- name: `??1CAutoDeleteFile@CEventSourceHandler@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile *__hidden this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1800380a3`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002c923`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(LPCWSTR *this)
{
  DeleteFileW(*this);
}

```

## disassembly

```asm
0x18002c920  mov     rcx, [rcx]
0x18002c923  jmp     cs:__imp_DeleteFileW
```
