# Microsoft::Windows::Performance::CNGenEventTraceExtender::FileExists(ushort const *)

- ea: `0x180029a94`
- end: `0x180029ae9`
- name: `?FileExists@CNGenEventTraceExtender@Performance@Windows@Microsoft@@AEBA_NPEBG@Z`
- size: `85`
- prototype: `bool(Microsoft::Windows::Performance::CNGenEventTraceExtender *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18002954c`

## callees

- `0x180029a94`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ad1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180029ad1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029abc`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180029abc`

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
0x180029a94  sub     rsp, 48h
0x180029a98  mov     rcx, rdx; lpFileName
0x180029a9b  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x180029aa4  mov     r8d, 3; dwShareMode
0x180029aaa  mov     [rsp+48h+dwFlagsAndAttributes], 0; dwFlagsAndAttributes
0x180029ab2  xor     edx, edx; dwDesiredAccess
0x180029ab4  mov     [rsp+48h+dwCreationDisposition], r8d; dwCreationDisposition
0x180029ab9  xor     r9d, r9d; lpSecurityAttributes
0x180029abc  call    cs:__imp_CreateFileW
0x180029ac3  nop     dword ptr [rax+rax+00h]
0x180029ac8  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180029acc  jz      short loc_180029AE1
0x180029ace  mov     rcx, rax; hObject
0x180029ad1  call    cs:__imp_CloseHandle
0x180029ad8  nop     dword ptr [rax+rax+00h]
0x180029add  mov     al, 1
0x180029adf  jmp     short loc_180029AE3
0x180029ae1  xor     al, al
0x180029ae3  add     rsp, 48h
0x180029ae7  retn
```
