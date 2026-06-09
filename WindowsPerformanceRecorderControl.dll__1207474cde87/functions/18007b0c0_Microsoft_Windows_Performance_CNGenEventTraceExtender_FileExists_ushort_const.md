# Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)

- ea: `0x18007b0c0`
- end: `0x18007b108`
- name: `?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z`
- size: `72`
- prototype: `bool(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18007acb0`

## callees

- `0x18007b0c0`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b0f7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18007b0f7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b0e8`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18007b0e8`

## pseudocode

```c
char __fastcall Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(
        Microsoft::Windows::Performance::CNGenEventTraceExtender *this,
        const unsigned __int16 *a2)
{
  HANDLE FileW; // rax

  FileW = CreateFileW(a2, 0, 3u, 0, 3u, 0, 0);
  if ( FileW == (HANDLE)-1LL )
    return 0;
  CloseHandle(FileW);
  return 1;
}

```

## disassembly

```asm
0x18007b0c0  sub     rsp, 48h
0x18007b0c4  mov     rcx, rdx; lpFileName
0x18007b0c7  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18007b0d0  mov     r8d, 3; dwShareMode
0x18007b0d6  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x18007b0de  xor     edx, edx; dwDesiredAccess
0x18007b0e0  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x18007b0e5  xor     r9d, r9d; lpSecurityAttributes
0x18007b0e8  call    cs:__imp_CreateFileW
0x18007b0ee  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18007b0f2  jz      short loc_18007B101
0x18007b0f4  mov     rcx, rax; hObject
0x18007b0f7  call    cs:__imp_CloseHandle
0x18007b0fd  mov     al, 1
0x18007b0ff  jmp     short loc_18007B103
0x18007b101  xor     al, al
0x18007b103  add     rsp, 48h
0x18007b107  retn
```
