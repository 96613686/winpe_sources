# OpenFirefoxBookmarksFile(void * *)

- ea: `0x18001f30c`
- end: `0x18001f404`
- name: `?OpenFirefoxBookmarksFile@@YAJPEAPEAX@Z`
- size: `248`
- prototype: `__int64 __fastcall(void **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting, installer_update`

## callers

- `0x18000b280`

## callees

- `0x180002ce0`
- `0x18001ead0`
- `0x18001eb88`
- `0x18001ed08`
- `0x18001f30c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3c5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f3c5`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f36c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18001f36c`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f3b6`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18001f3b6`

## pseudocode

```c
__int64 __fastcall OpenFirefoxBookmarksFile(void **a1, __int64 a2)
{
  int DefaultFirefoxInstallPath; // ebx
  HANDLE FileW; // rax
  signed int LastError; // eax
  bool v7; // [rsp+40h] [rbp-658h] BYREF
  wchar_t Str[264]; // [rsp+50h] [rbp-648h] BYREF
  WCHAR FileName[264]; // [rsp+260h] [rbp-438h] BYREF
  WCHAR v10[264]; // [rsp+470h] [rbp-228h] BYREF

  v7 = 0;
  DefaultFirefoxInstallPath = GetDefaultFirefoxInstallPath(Str, a2, &v7);
  if ( DefaultFirefoxInstallPath >= 0 )
  {
    DefaultFirefoxInstallPath = GetFirefoxSqliteDllPath(Str, FileName);
    if ( DefaultFirefoxInstallPath >= 0 )
    {
      if ( GetFileAttributesW(FileName) == -1 )
      {
        return (unsigned int)-2147024894;
      }
      else
      {
        DefaultFirefoxInstallPath = GetFirefoxBookmarksFilePath(v10);
        if ( DefaultFirefoxInstallPath >= 0 )
        {
          FileW = CreateFileW(v10, 0x120089u, 3u, 0, 3u, 0x80u, 0);
          *a1 = FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            DefaultFirefoxInstallPath = LastError;
            if ( LastError > 0 )
              return (unsigned __int16)LastError | 0x80070000;
          }
        }
      }
    }
  }
  return (unsigned int)DefaultFirefoxInstallPath;
}

```

## disassembly

```asm
0x18001f30c  mov     [rsp+arg_8], rbx
0x18001f311  push    rdi
0x18001f312  sub     rsp, 690h
0x18001f319  mov     rax, cs:__security_cookie
0x18001f320  xor     rax, rsp
0x18001f323  mov     [rsp+698h+var_18], rax
0x18001f32b  mov     rdi, rcx
0x18001f32e  mov     [rsp+698h+var_658], 0
0x18001f333  lea     rcx, [rsp+698h+Str]; Str
0x18001f338  lea     r8, [rsp+698h+var_658]; bool *
0x18001f33d  call    ?GetDefaultFirefoxInstallPath@@YAJPEAGKPEA_N@Z; GetDefaultFirefoxInstallPath(ushort *,ulong,bool *)
0x18001f342  mov     ebx, eax
0x18001f344  test    eax, eax
0x18001f346  js      loc_18001F3E1
0x18001f34c  lea     rdx, [rsp+698h+FileName]; unsigned __int16 *
0x18001f354  lea     rcx, [rsp+698h+Str]; unsigned __int16 *
0x18001f359  call    ?GetFirefoxSqliteDllPath@@YAJPEAG0K@Z; GetFirefoxSqliteDllPath(ushort *,ushort *,ulong)
0x18001f35e  mov     ebx, eax
0x18001f360  test    eax, eax
0x18001f362  js      short loc_18001F3E1
0x18001f364  lea     rcx, [rsp+698h+FileName]; lpFileName
0x18001f36c  call    cs:__imp_GetFileAttributesW
0x18001f372  cmp     eax, 0FFFFFFFFh
0x18001f375  jz      short loc_18001F3DC
0x18001f377  lea     rcx, [rsp+698h+var_228]; unsigned __int16 *
0x18001f37f  call    ?GetFirefoxBookmarksFilePath@@YAJPEAGK@Z; GetFirefoxBookmarksFilePath(ushort *,ulong)
0x18001f384  mov     ebx, eax
0x18001f386  test    eax, eax
0x18001f388  js      short loc_18001F3E1
0x18001f38a  mov     [rsp+698h+hTemplateFile], 0; hTemplateFile
0x18001f393  lea     rcx, [rsp+698h+var_228]; lpFileName
0x18001f39b  mov     r8d, 3; dwShareMode
0x18001f3a1  mov     [rsp+698h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18001f3a9  xor     r9d, r9d; lpSecurityAttributes
0x18001f3ac  mov     [rsp+698h+dwCreationDisposition], r8d; dwCreationDisposition
0x18001f3b1  mov     edx, 120089h; dwDesiredAccess
0x18001f3b6  call    cs:__imp_CreateFileW
0x18001f3bc  mov     [rdi], rax
0x18001f3bf  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001f3c3  jnz     short loc_18001F3E1
0x18001f3c5  call    cs:__imp_GetLastError
0x18001f3cb  mov     ebx, eax
0x18001f3cd  test    eax, eax
0x18001f3cf  jle     short loc_18001F3E1
0x18001f3d1  movzx   ebx, ax
0x18001f3d4  or      ebx, 80070000h
0x18001f3da  jmp     short loc_18001F3E1
0x18001f3dc  mov     ebx, 80070002h
0x18001f3e1  mov     eax, ebx
0x18001f3e3  mov     rcx, [rsp+698h+var_18]
0x18001f3eb  xor     rcx, rsp; StackCookie
0x18001f3ee  call    __security_check_cookie
0x18001f3f3  mov     rbx, [rsp+698h+arg_8]
0x18001f3fb  add     rsp, 690h
0x18001f402  pop     rdi
0x18001f403  retn
```
