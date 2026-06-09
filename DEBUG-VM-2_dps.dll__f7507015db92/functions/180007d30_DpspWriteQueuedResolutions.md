# DpspWriteQueuedResolutions

- ea: `0x180007d30`
- end: `0x180007e8a`
- name: `DpspWriteQueuedResolutions`
- size: `346`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x18000f774`

## callees

- `0x180007d30`
- `0x180008dd8`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x1800141a4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007df6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180007df6`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e5d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180007e5d`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007de0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180007de0`

## string_xrefs

- `0x180007d6f`: `%systemroot%\system32\wdi\ERCQueuedResolutions.dat`
- `0x180007d99`: `DpspWriteQueuedResolutions`
- `0x180007e3c`: `DpspWriteQueuedResolutions`

## pseudocode

```c
__int64 DpspWriteQueuedResolutions()
{
  int v0; // eax
  unsigned int v1; // ebx
  HANDLE FileW; // rdi
  signed int LastError; // eax
  int v4; // eax
  int v5; // r8d
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x208u);
  if ( !g_fQueuedResolutionsRead )
    return 0;
  v0 = WdipExpandVariables(FileName, 0x104u, L"%systemroot%\\system32\\wdi\\ERCQueuedResolutions.dat");
  v1 = v0;
  if ( v0 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspWriteQueuedResolutions",
      1833,
      (int)L"Error = %d",
      v0);
    return v1;
  }
  FileW = CreateFileW(FileName, 0x40000000u, 0, 0, 2u, 0x8000000u, 0);
  if ( (((unsigned __int64)FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
  {
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( (v1 & 0x80000000) != 0 )
    {
      LOBYTE(v4) = v1;
      v5 = 1843;
LABEL_11:
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspWriteQueuedResolutions",
        v5,
        (int)L"Error = %d",
        v4);
      goto LABEL_12;
    }
  }
  v4 = DpspWriteQueuedResolutionsToFile(FileW);
  v1 = v4;
  if ( v4 < 0 )
  {
    v5 = 1846;
    goto LABEL_11;
  }
LABEL_12:
  if ( FileW && FileW != (HANDLE)-1LL )
    CloseHandle(FileW);
  return v1;
}

```

## disassembly

```asm
0x180007d30  mov     [rsp+arg_0], rbx
0x180007d35  push    rdi
0x180007d36  sub     rsp, 260h
0x180007d3d  mov     rax, cs:__security_cookie
0x180007d44  xor     rax, rsp
0x180007d47  mov     [rsp+268h+var_18], rax
0x180007d4f  xor     edx, edx; Val
0x180007d51  lea     rcx, [rsp+268h+FileName]; void *
0x180007d56  mov     r8d, 208h; Size
0x180007d5c  call    memset_0
0x180007d61  mov     eax, cs:g_fQueuedResolutionsRead
0x180007d67  test    eax, eax
0x180007d69  jz      loc_180007E65
0x180007d6f  lea     r8, Src; "%systemroot%\\system32\\wdi\\ERCQueuedR"...
0x180007d76  mov     edx, 104h; unsigned __int64
0x180007d7b  lea     rcx, [rsp+268h+FileName]; unsigned __int16 *
0x180007d80  call    WdipExpandVariables
0x180007d85  mov     ebx, eax
0x180007d87  test    eax, eax
0x180007d89  jns     short loc_180007DB7
0x180007d8b  movzx   ecx, ax
0x180007d8e  lea     r9, aErrorD; "Error = %d"
0x180007d95  mov     [rsp+268h+dwCreationDisposition], ecx; Args
0x180007d99  lea     rdx, aDpspwritequeue_2; "DpspWriteQueuedResolutions"
0x180007da0  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007da7  mov     r8d, 729h; int
0x180007dad  call    WdipTraceError
0x180007db2  jmp     loc_180007E67
0x180007db7  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x180007dc0  lea     rcx, [rsp+268h+FileName]; lpFileName
0x180007dc5  mov     [rsp+268h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180007dcd  xor     r9d, r9d; lpSecurityAttributes
0x180007dd0  xor     r8d, r8d; dwShareMode
0x180007dd3  mov     [rsp+268h+dwCreationDisposition], 2; dwCreationDisposition
0x180007ddb  mov     edx, 40000000h; dwDesiredAccess
0x180007de0  call    cs:__imp_CreateFileW
0x180007de6  mov     rdi, rax
0x180007de9  lea     rcx, [rax+1]
0x180007ded  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180007df4  jnz     short loc_180007E1A
0x180007df6  call    cs:__imp_GetLastError
0x180007dfc  mov     ebx, eax
0x180007dfe  test    eax, eax
0x180007e00  jle     short loc_180007E0B
0x180007e02  movzx   ebx, ax
0x180007e05  or      ebx, 80070000h
0x180007e0b  test    ebx, ebx
0x180007e0d  jns     short loc_180007E1A
0x180007e0f  movzx   eax, bx
0x180007e12  mov     r8d, 733h
0x180007e18  jmp     short loc_180007E31
0x180007e1a  mov     rcx, rdi; hFile
0x180007e1d  call    ?DpspWriteQueuedResolutionsToFile@@YAJPEAX@Z; DpspWriteQueuedResolutionsToFile(void *)
0x180007e22  mov     ebx, eax
0x180007e24  test    eax, eax
0x180007e26  jns     short loc_180007E4F
0x180007e28  movzx   eax, ax
0x180007e2b  mov     r8d, 736h; int
0x180007e31  lea     r9, aErrorD; "Error = %d"
0x180007e38  mov     [rsp+268h+dwCreationDisposition], eax; Args
0x180007e3c  lea     rdx, aDpspwritequeue_2; "DpspWriteQueuedResolutions"
0x180007e43  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180007e4a  call    WdipTraceError
0x180007e4f  test    rdi, rdi
0x180007e52  jz      short loc_180007E67
0x180007e54  cmp     rdi, 0FFFFFFFFFFFFFFFFh
0x180007e58  jz      short loc_180007E67
0x180007e5a  mov     rcx, rdi; hObject
0x180007e5d  call    cs:__imp_CloseHandle
0x180007e63  jmp     short loc_180007E67
0x180007e65  xor     ebx, ebx
0x180007e67  mov     eax, ebx
0x180007e69  mov     rcx, [rsp+268h+var_18]
0x180007e71  xor     rcx, rsp; StackCookie
0x180007e74  call    __security_check_cookie
0x180007e79  mov     rbx, [rsp+268h+arg_0]
0x180007e81  add     rsp, 260h
0x180007e88  pop     rdi
0x180007e89  retn
```
