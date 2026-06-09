# DpspReadQueuedResolutions

- ea: `0x1800152c4`
- end: `0x180015422`
- name: `DpspReadQueuedResolutions`
- size: `350`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops`

## callers

- `0x180007adc`
- `0x1800149dc`

## callees

- `0x180008dd8`
- `0x180009090`
- `0x180009fb0`
- `0x18000a856`
- `0x1800137a8`
- `0x1800152c4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001538c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015376`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180015381`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001538c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153f9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800153f9`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015367`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180015367`

## string_xrefs

- `0x1800152f5`: `%systemroot%\system32\wdi\ERCQueuedResolutions.dat`
- `0x180015325`: `DpspReadQueuedResolutions`
- `0x1800153d9`: `DpspReadQueuedResolutions`

## pseudocode

```c
__int64 DpspReadQueuedResolutions()
{
  int v0; // eax
  unsigned int v1; // ebx
  char *FileW; // rdi
  signed int LastError; // eax
  int QueuedResolutionsFromFile; // eax
  WCHAR FileName[264]; // [rsp+40h] [rbp-228h] BYREF

  memset_0(FileName, 0, 0x208u);
  v0 = WdipExpandVariables(FileName, 0x104u, L"%systemroot%\\system32\\wdi\\ERCQueuedResolutions.dat");
  v1 = v0;
  if ( v0 < 0 )
  {
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutions",
      1772,
      (int)L"Error = %d",
      v0);
    return v1;
  }
  FileW = (char *)CreateFileW(FileName, 0x80000000, 1u, 0, 3u, 0x8000000u, 0);
  if ( FileW == (char *)-1LL )
  {
    if ( GetLastError() == 2 || GetLastError() == 3 )
      return v1;
    LastError = GetLastError();
    v1 = LastError;
    if ( LastError > 0 )
      v1 = (unsigned __int16)LastError | 0x80070000;
    if ( (v1 & 0x80000000) != 0 )
    {
      WdipTraceError(
        (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
        (int)L"DpspReadQueuedResolutions",
        1788,
        (int)L"Error = %d",
        v1);
      return v1;
    }
  }
  QueuedResolutionsFromFile = DpspReadQueuedResolutionsFromFile(FileW);
  v1 = QueuedResolutionsFromFile;
  if ( QueuedResolutionsFromFile < 0 )
    WdipTraceError(
      (int)L"clientcore\\base\\diagnosis\\pdi\\wdi\\framework\\dps\\dpserc.cpp",
      (int)L"DpspReadQueuedResolutions",
      1793,
      (int)L"Error = %d",
      QueuedResolutionsFromFile);
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(FileW);
  return v1;
}

```

## disassembly

```asm
0x1800152c4  mov     [rsp+arg_0], rbx
0x1800152c9  push    rdi
0x1800152ca  sub     rsp, 260h
0x1800152d1  mov     rax, cs:__security_cookie
0x1800152d8  xor     rax, rsp
0x1800152db  mov     [rsp+268h+var_18], rax
0x1800152e3  xor     edx, edx; Val
0x1800152e5  lea     rcx, [rsp+268h+FileName]; void *
0x1800152ea  mov     r8d, 208h; Size
0x1800152f0  call    memset_0
0x1800152f5  lea     r8, Src; "%systemroot%\\system32\\wdi\\ERCQueuedR"...
0x1800152fc  mov     edx, 104h; unsigned __int64
0x180015301  lea     rcx, [rsp+268h+FileName]; unsigned __int16 *
0x180015306  call    WdipExpandVariables
0x18001530b  mov     ebx, eax
0x18001530d  test    eax, eax
0x18001530f  jns     short loc_18001533D
0x180015311  movzx   ecx, ax
0x180015314  mov     r8d, 6ECh; int
0x18001531a  mov     [rsp+268h+dwCreationDisposition], ecx; Args
0x18001531e  lea     r9, aErrorD; "Error = %d"
0x180015325  lea     rdx, aDpspreadqueued_1; "DpspReadQueuedResolutions"
0x18001532c  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x180015333  call    WdipTraceError
0x180015338  jmp     loc_1800153FF
0x18001533d  xor     r9d, r9d; lpSecurityAttributes
0x180015340  mov     [rsp+268h+hTemplateFile], 0; hTemplateFile
0x180015349  mov     [rsp+268h+dwFlagsAndAttributes], 8000000h; dwFlagsAndAttributes
0x180015351  lea     rcx, [rsp+268h+FileName]; lpFileName
0x180015356  mov     edx, 80000000h; dwDesiredAccess
0x18001535b  mov     [rsp+268h+dwCreationDisposition], 3; dwCreationDisposition
0x180015363  lea     r8d, [r9+1]; dwShareMode
0x180015367  call    cs:__imp_CreateFileW
0x18001536d  mov     rdi, rax
0x180015370  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180015374  jnz     short loc_1800153B7
0x180015376  call    cs:__imp_GetLastError
0x18001537c  cmp     eax, 2
0x18001537f  jz      short loc_1800153FF
0x180015381  call    cs:__imp_GetLastError
0x180015387  cmp     eax, 3
0x18001538a  jz      short loc_1800153FF
0x18001538c  call    cs:__imp_GetLastError
0x180015392  mov     ebx, eax
0x180015394  test    eax, eax
0x180015396  jle     short loc_1800153A1
0x180015398  movzx   ebx, ax
0x18001539b  or      ebx, 80070000h
0x1800153a1  test    ebx, ebx
0x1800153a3  jns     short loc_1800153B7
0x1800153a5  movzx   eax, bx
0x1800153a8  mov     r8d, 6FCh
0x1800153ae  mov     [rsp+268h+dwCreationDisposition], eax
0x1800153b2  jmp     loc_18001531E
0x1800153b7  mov     rcx, rdi; hFile
0x1800153ba  call    ?DpspReadQueuedResolutionsFromFile@@YAJPEAX@Z; DpspReadQueuedResolutionsFromFile(void *)
0x1800153bf  mov     ebx, eax
0x1800153c1  test    eax, eax
0x1800153c3  jns     short loc_1800153EC
0x1800153c5  movzx   eax, ax
0x1800153c8  lea     r9, aErrorD; "Error = %d"
0x1800153cf  mov     r8d, 701h; int
0x1800153d5  mov     [rsp+268h+dwCreationDisposition], eax; Args
0x1800153d9  lea     rdx, aDpspreadqueued_1; "DpspReadQueuedResolutions"
0x1800153e0  lea     rcx, aClientcoreBase_2; "clientcore\\base\\diagnosis\\pdi\\wdi\\"...
0x1800153e7  call    WdipTraceError
0x1800153ec  lea     rax, [rdi-1]
0x1800153f0  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800153f4  ja      short loc_1800153FF
0x1800153f6  mov     rcx, rdi; hObject
0x1800153f9  call    cs:__imp_CloseHandle
0x1800153ff  mov     eax, ebx
0x180015401  mov     rcx, [rsp+268h+var_18]
0x180015409  xor     rcx, rsp; StackCookie
0x18001540c  call    __security_check_cookie
0x180015411  mov     rbx, [rsp+268h+arg_0]
0x180015419  add     rsp, 260h
0x180015420  pop     rdi
0x180015421  retn
```
