# _CBitsDownloader::DeleteJob_::_1_::dtor$1

- ea: `0x18002068e`
- end: `0x18002069a`
- name: `_CBitsDownloader::DeleteJob_::_1_::dtor$1`
- size: `12`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task`

## callees

- `0x1800132a0`

## pseudocode

```c
void __fastcall CBitsDownloader::DeleteJob_::_1_::dtor_1(__int64 a1, __int64 a2)
{
  CDownloadService::~CDownloadService((CDownloadService *)(a2 + 80), a2);
}

```

## disassembly

```asm
0x18002068e  lea     rcx, [rdx+50h]; this
0x180020695  jmp     ??1CDownloadService@@UEAA@XZ; CDownloadService::~CDownloadService(void)
```
