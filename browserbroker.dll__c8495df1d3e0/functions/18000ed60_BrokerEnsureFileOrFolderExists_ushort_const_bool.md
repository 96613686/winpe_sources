# BrokerEnsureFileOrFolderExists(ushort const *,bool)

- ea: `0x18000ed60`
- end: `0x18000ee3c`
- name: `?BrokerEnsureFileOrFolderExists@@YAJPEBG_N@Z`
- size: `220`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName)`
- caller_count: `1`
- callee_count: `1`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18000ebd8`

## callees

- `0x18000ed60`

## import_xrefs

- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee2c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18000ee2c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee0b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ed9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ee0b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ed8e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000edff`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000ed8e`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000edff`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18000edb6`
- `api-ms-win-shell-shellfolders-l1-1-0!SHCreateDirectoryExW` at `0x18000edb6`

## pseudocode

```c
__int64 __fastcall BrokerEnsureFileOrFolderExists(LPCWSTR lpFileName)
{
  HANDLE FileW; // rax
  DWORD LastError; // ecx
  int v4; // eax

  FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
  if ( FileW != (HANDLE)-1LL )
  {
LABEL_14:
    CloseHandle(FileW);
    return 0;
  }
  LastError = GetLastError();
  if ( LastError - 2 <= 1 )
  {
    v4 = SHCreateDirectoryExW(0, lpFileName, 0);
    LastError = v4;
    if ( v4 && v4 != 80 && v4 != 183 )
    {
LABEL_6:
      if ( v4 > 0 )
      {
        LastError = (unsigned __int16)v4;
LABEL_13:
        LastError |= 0x80070000;
        return LastError;
      }
      return LastError;
    }
    FileW = CreateFileW(lpFileName, 0x80000000, 7u, 0, 3u, 0x2000000u, 0);
    if ( FileW == (HANDLE)-1LL )
    {
      v4 = GetLastError();
      LastError = v4;
      goto LABEL_6;
    }
    goto LABEL_14;
  }
  if ( LastError == 32 )
    return 0;
  if ( (int)LastError > 0 )
  {
    LastError = (unsigned __int16)LastError;
    goto LABEL_13;
  }
  return LastError;
}

```

## disassembly

```asm
0x18000ed60  push    rbx
0x18000ed62  sub     rsp, 40h
0x18000ed66  xor     r9d, r9d; lpSecurityAttributes
0x18000ed69  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000ed72  mov     [rsp+48h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000ed7a  mov     edx, 80000000h; dwDesiredAccess
0x18000ed7f  mov     rbx, rcx
0x18000ed82  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000ed8a  lea     r8d, [r9+7]; dwShareMode
0x18000ed8e  call    cs:__imp_CreateFileW
0x18000ed94  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ed98  jnz     loc_18000EE29
0x18000ed9e  call    cs:__imp_GetLastError
0x18000eda4  mov     ecx, eax
0x18000eda6  add     eax, 0FFFFFFFEh
0x18000eda9  cmp     eax, 1
0x18000edac  ja      short loc_18000EE15
0x18000edae  xor     r8d, r8d; psa
0x18000edb1  mov     rdx, rbx; pszPath
0x18000edb4  xor     ecx, ecx; hwnd
0x18000edb6  call    cs:__imp_SHCreateDirectoryExW
0x18000edbc  mov     ecx, eax
0x18000edbe  test    eax, eax
0x18000edc0  jz      short loc_18000EDD7
0x18000edc2  cmp     eax, 50h ; 'P'
0x18000edc5  jz      short loc_18000EDD7
0x18000edc7  cmp     eax, 0B7h
0x18000edcc  jz      short loc_18000EDD7
0x18000edce  test    eax, eax
0x18000edd0  jle     short loc_18000EE34
0x18000edd2  movzx   ecx, ax
0x18000edd5  jmp     short loc_18000EE21
0x18000edd7  xor     r9d, r9d; lpSecurityAttributes
0x18000edda  mov     [rsp+48h+hTemplateFile], 0; hTemplateFile
0x18000ede3  mov     [rsp+48h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x18000edeb  mov     edx, 80000000h; dwDesiredAccess
0x18000edf0  mov     rcx, rbx; lpFileName
0x18000edf3  mov     [rsp+48h+dwCreationDisposition], 3; dwCreationDisposition
0x18000edfb  lea     r8d, [r9+7]; dwShareMode
0x18000edff  call    cs:__imp_CreateFileW
0x18000ee05  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ee09  jnz     short loc_18000EE29
0x18000ee0b  call    cs:__imp_GetLastError
0x18000ee11  mov     ecx, eax
0x18000ee13  jmp     short loc_18000EDCE
0x18000ee15  cmp     ecx, 20h ; ' '
0x18000ee18  jz      short loc_18000EE32
0x18000ee1a  test    ecx, ecx
0x18000ee1c  jle     short loc_18000EE34
0x18000ee1e  movzx   ecx, cx
0x18000ee21  or      ecx, 80070000h
0x18000ee27  jmp     short loc_18000EE34
0x18000ee29  mov     rcx, rax; hObject
0x18000ee2c  call    cs:__imp_CloseHandle
0x18000ee32  xor     ecx, ecx
0x18000ee34  mov     eax, ecx
0x18000ee36  add     rsp, 40h
0x18000ee3a  pop     rbx
0x18000ee3b  retn
```
