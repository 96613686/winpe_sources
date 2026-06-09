# ReadClassStorePath(void *,ushort * *)

- ea: `0x180029324`
- end: `0x1800294cd`
- name: `?ReadClassStorePath@@YAJPEAXPEAPEAG@Z`
- size: `425`
- prototype: `signed int __fastcall(void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops`

## callers

- `0x180028a3c`

## callees

- `0x1800290cc`
- `0x180029324`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029430`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029394`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800293cd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180029430`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002948f`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002948f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800294a1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180029481`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800294a1`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800293f6`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800293f6`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800293c0`
- `api-ms-win-core-file-l1-1-0!GetFileSize` at `0x1800293c0`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002937f`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002937f`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029426`
- `api-ms-win-core-file-l1-1-0!ReadFile` at `0x180029426`

## pseudocode

```c
signed int __fastcall ReadClassStorePath(void *a1, unsigned __int16 **a2)
{
  signed int result; // eax
  _WORD *v4; // rsi
  HANDLE FileW; // rdi
  signed int LastError; // ebx
  DWORD v7; // ebp
  DWORD FileSize; // eax
  unsigned __int64 v9; // rcx
  SIZE_T v10; // rax
  _WORD *v11; // rax
  DWORD FileSizeHigh; // [rsp+80h] [rbp+18h] BYREF
  LPCWSTR lpFileName; // [rsp+88h] [rbp+20h] BYREF

  lpFileName = 0;
  result = GetAppmgmtIniFilePath(a1, (unsigned __int16 **)&lpFileName);
  if ( result < 0 )
    return result;
  v4 = 0;
  FileW = CreateFileW(lpFileName, 0x80000000, 1u, 0, 3u, 0, 0);
  if ( FileW != (HANDLE)-1LL || (FileW = 0, LastError = GetLastError(), LastError == 2) )
  {
    v7 = 0;
    if ( !FileW )
      goto LABEL_7;
    FileSizeHigh = 0;
    FileSize = GetFileSize(FileW, &FileSizeHigh);
    v7 = FileSize;
    if ( FileSize != -1 )
    {
      if ( FileSizeHigh || FileSize > 0x50000000 )
      {
        LastError = 122;
        goto LABEL_21;
      }
LABEL_7:
      v9 = ((unsigned __int64)v7 >> 1) + 1;
      v10 = 2 * v9;
      if ( !is_mul_ok(v9, 2u) )
        v10 = -1;
      v11 = LocalAlloc(0, v10);
      v4 = v11;
      if ( !v11 )
      {
        LastError = 8;
        goto LABEL_21;
      }
      FileSizeHigh = 0;
      if ( v7 )
      {
        if ( !ReadFile(FileW, v11, v7, &FileSizeHigh, 0) )
        {
          LastError = GetLastError();
          goto LABEL_21;
        }
        if ( v4[((unsigned __int64)FileSizeHigh >> 1) - 1] )
        {
          LastError = 1392;
          goto LABEL_21;
        }
      }
      else
      {
        *v11 = 0;
      }
      LastError = 0;
      goto LABEL_21;
    }
    LastError = GetLastError();
    if ( !LastError )
      goto LABEL_7;
  }
LABEL_21:
  LocalFree((HLOCAL)lpFileName);
  if ( FileW )
    CloseHandle(FileW);
  if ( LastError )
  {
    LocalFree(v4);
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  else
  {
    *a2 = v4;
  }
  return LastError;
}

```

## disassembly

```asm
0x180029324  mov     rax, rsp
0x180029327  mov     [rax+8], rbx
0x18002932b  mov     [rax+10h], rbp
0x18002932f  push    rsi
0x180029330  push    rdi
0x180029331  push    r12
0x180029333  push    r14
0x180029335  push    r15
0x180029337  sub     rsp, 40h
0x18002933b  mov     r14, rdx
0x18002933e  xor     r15d, r15d
0x180029341  lea     rdx, [rax+20h]; unsigned __int16 **
0x180029345  mov     [rax+20h], r15
0x180029349  call    ?GetAppmgmtIniFilePath@@YAJPEAXPEAPEAG@Z; GetAppmgmtIniFilePath(void *,ushort * *)
0x18002934e  test    eax, eax
0x180029350  js      loc_1800294B6
0x180029356  mov     rcx, [rsp+68h+lpFileName]; lpFileName
0x18002935e  lea     r8d, [r15+1]; dwShareMode
0x180029362  mov     [rsp+68h+hTemplateFile], r15; hTemplateFile
0x180029367  xor     r9d, r9d; lpSecurityAttributes
0x18002936a  mov     [rsp+68h+dwFlagsAndAttributes], r15d; dwFlagsAndAttributes
0x18002936f  mov     edx, 80000000h; dwDesiredAccess
0x180029374  mov     [rsp+68h+dwCreationDisposition], 3; dwCreationDisposition
0x18002937c  mov     esi, r15d
0x18002937f  call    cs:__imp_CreateFileW
0x180029385  or      r12, 0FFFFFFFFFFFFFFFFh
0x180029389  mov     rdi, rax
0x18002938c  cmp     rax, r12
0x18002938f  jnz     short loc_1800293A5
0x180029391  mov     edi, r15d
0x180029394  call    cs:__imp_GetLastError
0x18002939a  mov     ebx, eax
0x18002939c  cmp     eax, 2
0x18002939f  jnz     loc_180029479
0x1800293a5  mov     ebp, r15d
0x1800293a8  test    rdi, rdi
0x1800293ab  jz      short loc_1800293DD
0x1800293ad  lea     rdx, [rsp+68h+FileSizeHigh]; lpFileSizeHigh
0x1800293b5  mov     [rsp+68h+FileSizeHigh], r15d
0x1800293bd  mov     rcx, rdi; hFile
0x1800293c0  call    cs:__imp_GetFileSize
0x1800293c6  mov     ebp, eax
0x1800293c8  cmp     eax, 0FFFFFFFFh
0x1800293cb  jnz     short loc_18002943A
0x1800293cd  call    cs:__imp_GetLastError
0x1800293d3  mov     ebx, eax
0x1800293d5  test    eax, eax
0x1800293d7  jnz     loc_180029479
0x1800293dd  mov     ecx, ebp
0x1800293df  mov     eax, 2
0x1800293e4  shr     rcx, 1
0x1800293e7  inc     rcx
0x1800293ea  mul     rcx
0x1800293ed  cmovb   rax, r12
0x1800293f1  xor     ecx, ecx; uFlags
0x1800293f3  mov     rdx, rax; uBytes
0x1800293f6  call    cs:__imp_LocalAlloc
0x1800293fc  mov     rsi, rax
0x1800293ff  test    rax, rax
0x180029402  jz      short loc_180029474
0x180029404  mov     [rsp+68h+FileSizeHigh], r15d
0x18002940c  test    ebp, ebp
0x18002940e  jz      short loc_18002946B
0x180029410  lea     r9, [rsp+68h+FileSizeHigh]; lpNumberOfBytesRead
0x180029418  mov     qword ptr [rsp+68h+dwCreationDisposition], r15; lpOverlapped
0x18002941d  mov     r8d, ebp; nNumberOfBytesToRead
0x180029420  mov     rdx, rax; lpBuffer
0x180029423  mov     rcx, rdi; hFile
0x180029426  call    cs:__imp_ReadFile
0x18002942c  test    eax, eax
0x18002942e  jnz     short loc_180029452
0x180029430  call    cs:__imp_GetLastError
0x180029436  mov     ebx, eax
0x180029438  jmp     short loc_180029479
0x18002943a  cmp     [rsp+68h+FileSizeHigh], r15d
0x180029442  jnz     short loc_18002944B
0x180029444  cmp     eax, 50000000h
0x180029449  jbe     short loc_1800293DD
0x18002944b  mov     ebx, 7Ah ; 'z'
0x180029450  jmp     short loc_180029479
0x180029452  mov     eax, [rsp+68h+FileSizeHigh]
0x180029459  shr     rax, 1
0x18002945c  cmp     [rsi+rax*2-2], r15w
0x180029462  jz      short loc_18002946F
0x180029464  mov     ebx, 570h
0x180029469  jmp     short loc_180029479
0x18002946b  mov     [rax], r15w
0x18002946f  mov     ebx, r15d
0x180029472  jmp     short loc_180029479
0x180029474  mov     ebx, 8
0x180029479  mov     rcx, [rsp+68h+lpFileName]; hMem
0x180029481  call    cs:__imp_LocalFree
0x180029487  test    rdi, rdi
0x18002948a  jz      short loc_180029495
0x18002948c  mov     rcx, rdi; hObject
0x18002948f  call    cs:__imp_CloseHandle
0x180029495  test    ebx, ebx
0x180029497  jnz     short loc_18002949E
0x180029499  mov     [r14], rsi
0x18002949c  jmp     short loc_1800294B4
0x18002949e  mov     rcx, rsi; hMem
0x1800294a1  call    cs:__imp_LocalFree
0x1800294a7  test    ebx, ebx
0x1800294a9  jle     short loc_1800294B4
0x1800294ab  movzx   ebx, bx
0x1800294ae  or      ebx, 80070000h
0x1800294b4  mov     eax, ebx
0x1800294b6  mov     rbx, [rsp+68h+arg_0]
0x1800294bb  mov     rbp, [rsp+68h+arg_8]
0x1800294c0  add     rsp, 40h
0x1800294c4  pop     r15
0x1800294c6  pop     r14
0x1800294c8  pop     r12
0x1800294ca  pop     rdi
0x1800294cb  pop     rsi
0x1800294cc  retn
```
