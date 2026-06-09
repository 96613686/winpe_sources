# pSetupGetPathFromNtPath

- ea: `0x14000bd44`
- end: `0x14000be72`
- name: `pSetupGetPathFromNtPath`
- size: `302`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, reparse_path, installer_update`

## callers

- `0x1400210c0`

## callees

- `0x1400070bc`
- `0x14000bb4c`
- `0x14000bd44`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdd9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000bdfe`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be42`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x14000be42`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000be33`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000be33`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000bdf4`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x14000bdf4`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000bdca`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x14000bdca`

## pseudocode

```c
_BOOL8 __fastcall pSetupGetPathFromNtPath(__int64 a1, unsigned __int16 *a2)
{
  __int64 v3; // r11
  HANDLE FileW; // rax
  void *v5; // rdi
  DWORD LastError; // ebx
  DWORD FinalPathNameByHandleW; // eax
  WCHAR FileName[264]; // [rsp+40h] [rbp-448h] BYREF
  WCHAR szFilePath; // [rsp+250h] [rbp-238h] BYREF
  size_t v11[65]; // [rsp+258h] [rbp-230h] BYREF

  if ( (int)StringCchCopyW(FileName, 0x104u, (size_t *)L"\\\\?\\GLOBALROOT") >= 0
    && (unsigned int)pSetupConcatenatePaths(FileName, v3, 260) )
  {
    FileW = CreateFileW(FileName, 0, 7u, 0, 3u, 0x2000000u, 0);
    v5 = FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
    }
    else
    {
      FinalPathNameByHandleW = GetFinalPathNameByHandleW(FileW, &szFilePath, 0x104u, 0);
      if ( FinalPathNameByHandleW )
      {
        if ( FinalPathNameByHandleW - 4 > 0xFF || (LastError = 0, (int)StringCchCopyW(a2, 0x104u, v11) < 0) )
          LastError = 13;
      }
      else
      {
        LastError = GetLastError();
      }
      CloseHandle(v5);
    }
  }
  else
  {
    LastError = 13;
  }
  SetLastError(LastError);
  return LastError == 0;
}

```

## disassembly

```asm
0x14000bd44  mov     [rsp+arg_10], rbx
0x14000bd49  push    rbp
0x14000bd4a  push    rsi
0x14000bd4b  push    rdi
0x14000bd4c  sub     rsp, 470h
0x14000bd53  mov     rax, cs:__security_cookie
0x14000bd5a  xor     rax, rsp
0x14000bd5d  mov     [rsp+488h+var_28], rax
0x14000bd65  mov     rsi, rdx
0x14000bd68  lea     r8, aGlobalroot; "\\\\?\\GLOBALROOT"
0x14000bd6f  mov     r11, rcx
0x14000bd72  mov     ebp, 104h
0x14000bd77  mov     edx, ebp; unsigned __int64
0x14000bd79  lea     rcx, [rsp+488h+FileName]; unsigned __int16 *
0x14000bd7e  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000bd83  test    eax, eax
0x14000bd85  js      loc_14000BE3B
0x14000bd8b  mov     r8d, ebp
0x14000bd8e  lea     rcx, [rsp+488h+FileName]
0x14000bd93  mov     rdx, r11
0x14000bd96  call    pSetupConcatenatePaths
0x14000bd9b  test    eax, eax
0x14000bd9d  jz      loc_14000BE3B
0x14000bda3  xor     r9d, r9d; lpSecurityAttributes
0x14000bda6  mov     [rsp+488h+hTemplateFile], 0; hTemplateFile
0x14000bdaf  mov     [rsp+488h+dwFlagsAndAttributes], 2000000h; dwFlagsAndAttributes
0x14000bdb7  lea     rcx, [rsp+488h+FileName]; lpFileName
0x14000bdbc  xor     edx, edx; dwDesiredAccess
0x14000bdbe  mov     [rsp+488h+dwCreationDisposition], 3; dwCreationDisposition
0x14000bdc6  lea     r8d, [r9+7]; dwShareMode
0x14000bdca  call    cs:__imp_CreateFileW
0x14000bdd0  mov     rdi, rax
0x14000bdd3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000bdd7  jnz     short loc_14000BDE3
0x14000bdd9  call    cs:__imp_GetLastError
0x14000bddf  mov     ebx, eax
0x14000bde1  jmp     short loc_14000BE40
0x14000bde3  xor     r9d, r9d; dwFlags
0x14000bde6  lea     rdx, [rsp+488h+szFilePath]; lpszFilePath
0x14000bdee  mov     r8d, ebp; cchFilePath
0x14000bdf1  mov     rcx, rdi; hFile
0x14000bdf4  call    cs:__imp_GetFinalPathNameByHandleW
0x14000bdfa  test    eax, eax
0x14000bdfc  jnz     short loc_14000BE08
0x14000bdfe  call    cs:__imp_GetLastError
0x14000be04  mov     ebx, eax
0x14000be06  jmp     short loc_14000BE30
0x14000be08  add     eax, 0FFFFFFFCh
0x14000be0b  cmp     eax, 0FFh
0x14000be10  ja      short loc_14000BE2B
0x14000be12  lea     r8, [rsp+488h+var_230]; unsigned __int16 *
0x14000be1a  mov     rdx, rbp; unsigned __int64
0x14000be1d  mov     rcx, rsi; unsigned __int16 *
0x14000be20  xor     ebx, ebx
0x14000be22  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x14000be27  test    eax, eax
0x14000be29  jns     short loc_14000BE30
0x14000be2b  mov     ebx, 0Dh
0x14000be30  mov     rcx, rdi; hObject
0x14000be33  call    cs:__imp_CloseHandle
0x14000be39  jmp     short loc_14000BE40
0x14000be3b  mov     ebx, 0Dh
0x14000be40  mov     ecx, ebx; dwErrCode
0x14000be42  call    cs:__imp_SetLastError
0x14000be48  xor     eax, eax
0x14000be4a  test    ebx, ebx
0x14000be4c  setz    al
0x14000be4f  mov     rcx, [rsp+488h+var_28]
0x14000be57  xor     rcx, rsp; StackCookie
0x14000be5a  call    __security_check_cookie
0x14000be5f  mov     rbx, [rsp+488h+arg_10]
0x14000be67  add     rsp, 470h
0x14000be6e  pop     rdi
0x14000be6f  pop     rsi
0x14000be70  pop     rbp
0x14000be71  retn
```
