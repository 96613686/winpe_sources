# OpenQihoo360SEBookmarksFile(void * *)

- ea: `0x18001f5b4`
- end: `0x18001f683`
- name: `?OpenQihoo360SEBookmarksFile@@YAJPEAPEAX@Z`
- size: `207`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, loader_planting`

## callers

- `0x18000b280`

## callees

- `0x180002ce0`
- `0x18001ed58`
- `0x18001ef24`
- `0x18001f5b4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f644`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f644`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f5eb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f5eb`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f635`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f635`

## pseudocode

```c
__int64 __fastcall OpenQihoo360SEBookmarksFile(void **a1)
{
  int Qihoo360SESqliteDllPath; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  WCHAR FileName[264]; // [rsp+40h] [rbp-438h] BYREF
  WCHAR v7[264]; // [rsp+250h] [rbp-228h] BYREF

  Qihoo360SESqliteDllPath = GetQihoo360SESqliteDllPath(FileName);
  if ( Qihoo360SESqliteDllPath >= 0 )
  {
    if ( GetFileAttributesW(FileName) == -1 )
    {
      return (unsigned int)-2147024894;
    }
    else
    {
      Qihoo360SESqliteDllPath = GetQihoo360SEBookmarksFilePath(v7);
      if ( Qihoo360SESqliteDllPath >= 0 )
      {
        FileW = CreateFileW(v7, 0x120089u, 3u, 0, 3u, 0x80u, 0);
        *a1 = FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          LastError = GetLastError();
          Qihoo360SESqliteDllPath = LastError;
          if ( LastError > 0 )
            return (unsigned __int16)LastError | 0x80070000;
        }
      }
    }
  }
  return (unsigned int)Qihoo360SESqliteDllPath;
}

```

## disassembly

```asm
0x18001f5b4  mov     [rsp+arg_8], rbx
0x18001f5b9  push    rdi
0x18001f5ba  sub     rsp, 470h
0x18001f5c1  mov     rax, cs:__security_cookie
0x18001f5c8  xor     rax, rsp
0x18001f5cb  mov     [rsp+478h+var_18], rax
0x18001f5d3  mov     rdi, rcx
0x18001f5d6  lea     rcx, [rsp+478h+FileName]; pszPath
0x18001f5db  call    ?GetQihoo360SESqliteDllPath@@YAJPEAGK@Z; GetQihoo360SESqliteDllPath(ushort *,ulong)
0x18001f5e0  mov     ebx, eax
0x18001f5e2  test    eax, eax
0x18001f5e4  js      short loc_18001F660
0x18001f5e6  lea     rcx, [rsp+478h+FileName]; lpFileName
0x18001f5eb  call    cs:__imp_GetFileAttributesW
0x18001f5f1  cmp     eax, 0FFFFFFFFh
0x18001f5f4  jz      short loc_18001F65B
0x18001f5f6  lea     rcx, [rsp+478h+var_228]; unsigned __int16 *
0x18001f5fe  call    ?GetQihoo360SEBookmarksFilePath@@YAJPEAGK@Z; GetQihoo360SEBookmarksFilePath(ushort *,ulong)
0x18001f603  mov     ebx, eax
0x18001f605  test    eax, eax
0x18001f607  js      short loc_18001F660
0x18001f609  mov     [rsp+478h+hTemplateFile], 0; hTemplateFile
0x18001f612  lea     rcx, [rsp+478h+var_228]; lpFileName
0x18001f61a  mov     r8d, 3; dwShareMode
0x18001f620  mov     [rsp+478h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001f628  xor     r9d, r9d; lpSecurityAttributes
0x18001f62b  mov     [rsp+478h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001f630  mov     edx, 120089h; dwDesiredAccess
0x18001f635  call    cs:__imp_CreateFileW
0x18001f63b  mov     [rdi], rax
0x18001f63e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f642  jnz     short loc_18001F660
0x18001f644  call    cs:__imp_GetLastError
0x18001f64a  mov     ebx, eax
0x18001f64c  test    eax, eax
0x18001f64e  jle     short loc_18001F660
0x18001f650  movzx   ebx, ax
0x18001f653  or      ebx, 80070000h
0x18001f659  jmp     short loc_18001F660
0x18001f65b  mov     ebx, 80070002h
0x18001f660  mov     eax, ebx
0x18001f662  mov     rcx, [rsp+478h+var_18]
0x18001f66a  xor     rcx, rsp; StackCookie
0x18001f66d  call    __security_check_cookie
0x18001f672  mov     rbx, [rsp+478h+arg_8]
0x18001f67a  add     rsp, 470h
0x18001f681  pop     rdi
0x18001f682  retn
```
