# Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(void)

- ea: `0x18001b6f8`
- end: `0x18001b702`
- name: `??1CAutoDeleteFile@CEventSourceHandler@Performance@Windows@Microsoft@@QEAA@XZ`
- size: `10`
- prototype: `void __fastcall(LPCWSTR *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180028904`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18001b6fb`

## pseudocode

```c
void __fastcall Microsoft::Windows::Performance::CEventSourceHandler::CAutoDeleteFile::~CAutoDeleteFile(LPCWSTR *this)
{
  DeleteFileW(*this);
}

```

## disassembly

```asm
0x18001b6f8  mov     rcx, [rcx]
0x18001b6fb  jmp     cs:__imp_DeleteFileW
```
