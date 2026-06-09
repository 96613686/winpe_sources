# GPEnableLogToFile(void)

- ea: `0x18000704c`
- end: `0x18000714f`
- name: `?GPEnableLogToFile@@YAKXZ`
- size: `259`
- prototype: `int(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, registry_config`

## callers

- `0x180002c70`

## callees

- `0x180002fa0`
- `0x18000704c`
- `0x1800097d0`
- `0x18000a192`
- `0x18000d32c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000710e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007131`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000710e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007131`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180007081`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180007081`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180007104`
- `api-ms-win-core-file-l1-1-0!SetFilePointerEx` at `0x180007104`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800070d7`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x1800070d7`

## string_xrefs

- `0x180007121`: `GP: SetFilePointerEx on %ws failed %d\n`

## pseudocode

```c
int GPEnableLogToFile(void)
{
  int result; // eax
  HANDLE FileW; // rax
  DWORD LastError; // eax
  WCHAR Buffer[264]; // [rsp+50h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x20Au);
  if ( !GetWindowsDirectoryW(Buffer, 0x104u) )
    return GetLastError();
  result = StringCchCatW(Buffer, 0x104u, L"\\logs\\StorGroupPolicy.log");
  if ( result )
    return result;
  FileW = CreateFileW(Buffer, 0x40000000u, 1u, 0, 4u, 0x80u, 0);
  GPLogFileHandle = FileW;
  if ( FileW == (HANDLE)-1LL )
    return GetLastError();
  if ( !SetFilePointerEx(FileW, 0, 0, 2u) )
  {
    LastError = GetLastError();
    GPDebugPrintX(4u, "GP: SetFilePointerEx on %ws failed %d\n", Buffer, LastError);
  }
  return 0;
}

```

## disassembly

```asm
0x18000704c  sub     rsp, 278h
0x180007053  mov     rax, cs:__security_cookie
0x18000705a  xor     rax, rsp
0x18000705d  mov     [rsp+278h+var_18], rax
0x180007065  xor     edx, edx; Val
0x180007067  lea     rcx, [rsp+278h+Buffer]; void *
0x18000706c  mov     r8d, 20Ah; Size
0x180007072  call    memset_0
0x180007077  mov     edx, 104h; uSize
0x18000707c  lea     rcx, [rsp+278h+Buffer]; lpBuffer
0x180007081  call    cs:__imp_GetWindowsDirectoryW
0x180007087  test    eax, eax
0x180007089  jz      loc_180007131
0x18000708f  lea     r8, aLogsStorgroupp; "\\logs\\StorGroupPolicy.log"
0x180007096  mov     edx, 104h; unsigned __int64
0x18000709b  lea     rcx, [rsp+278h+Buffer]; unsigned __int16 *
0x1800070a0  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800070a5  test    eax, eax
0x1800070a7  jnz     loc_180007137
0x1800070ad  mov     [rsp+278h+hTemplateFile], 0; hTemplateFile
0x1800070b6  lea     r8d, [rax+1]; dwShareMode
0x1800070ba  mov     [rsp+278h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x1800070c2  lea     rcx, [rsp+278h+Buffer]; lpFileName
0x1800070c7  xor     r9d, r9d; lpSecurityAttributes
0x1800070ca  mov     [rsp+278h+dwCreationDisposition], 4; dwCreationDisposition
0x1800070d2  mov     edx, 40000000h; dwDesiredAccess
0x1800070d7  call    cs:__imp_CreateFileW
0x1800070dd  mov     cs:?GPLogFileHandle@@3PEAXEA, rax; void * GPLogFileHandle
0x1800070e4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800070e8  jz      short loc_180007131
0x1800070ea  mov     qword ptr [rsp+278h+liDistanceToMove], 0
0x1800070f3  mov     r9d, 2; dwMoveMethod
0x1800070f9  mov     rdx, qword ptr [rsp+278h+liDistanceToMove]; liDistanceToMove
0x1800070fe  xor     r8d, r8d; lpNewFilePointer
0x180007101  mov     rcx, rax; hFile
0x180007104  call    cs:__imp_SetFilePointerEx
0x18000710a  test    eax, eax
0x18000710c  jnz     short loc_18000712D
0x18000710e  call    cs:__imp_GetLastError
0x180007114  lea     r8, [rsp+278h+Buffer]
0x180007119  mov     ecx, 4; unsigned int
0x18000711e  mov     r9d, eax
0x180007121  lea     rdx, aGpSetfilepoint; "GP: SetFilePointerEx on %ws failed %d\n"
0x180007128  call    ?GPDebugPrintX@@YAXKPEADZZ; GPDebugPrintX(ulong,char *,...)
0x18000712d  xor     eax, eax
0x18000712f  jmp     short loc_180007137
0x180007131  call    cs:__imp_GetLastError
0x180007137  mov     rcx, [rsp+278h+var_18]
0x18000713f  xor     rcx, rsp; StackCookie
0x180007142  call    __security_check_cookie
0x180007147  add     rsp, 278h
0x18000714e  retn
```
