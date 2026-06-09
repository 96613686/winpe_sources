# Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::OpenDevice(void)

- ea: `0x140007d90`
- end: `0x140007dcb`
- name: `?OpenDevice@Bfs@FileDialogBrokerCommon@Isolation@Security@Windows@@YAPEAXXZ`
- size: `59`
- prototype: `HANDLE __fastcall(Windows::Security::Isolation::FileDialogBrokerCommon::Bfs *this)`
- caller_count: `1`
- callee_count: `0`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1400105c4`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140007dc0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x140007dc0`

## pseudocode

```c
HANDLE __fastcall Windows::Security::Isolation::FileDialogBrokerCommon::Bfs::OpenDevice(
        Windows::Security::Isolation::FileDialogBrokerCommon::Bfs *this)
{
  return CreateFileW(L"\\\\.\\GLOBALROOT\\Device\\Bfs", 0xC0000000, 7u, 0, 3u, 0, 0);
}

```

## disassembly

```asm
0x140007d90  sub     rsp, 48h
0x140007d94  xor     r9d, r9d; lpSecurityAttributes
0x140007d97  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x140007da0  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x140007da8  lea     rcx, FileName; "\\\\.\\GLOBALROOT\\Device\\Bfs"
0x140007daf  mov     edx, 0C0000000h; dwDesiredAccess
0x140007db4  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x140007dbc  lea     r8d, [r9+7]; dwShareMode
0x140007dc0  call    cs:__imp_CreateFileW
0x140007dc6  add     rsp, 48h
0x140007dca  retn
```
