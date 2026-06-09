# IsHandleToNonEmptyDirectory(void *,bool *)

- ea: `0x180019da8`
- end: `0x18001a10a`
- name: `?IsHandleToNonEmptyDirectory@@YAJPEAXPEA_N@Z`
- size: `866`
- prototype: `__int64 __fastcall(HANDLE hFile, bool *)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, installer_update`

## callers

- `0x18001ac20`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x180008140`
- `0x18000ab70`
- `0x18000fafc`
- `0x180019da8`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a03a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0e4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e57`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e68`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fa7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019fb9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a03a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a049`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a05e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001a0e4`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180019e01`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x180019e01`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180019f31`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180019f31`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180019f76`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180019f76`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180019e4d`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180019e4d`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180019f99`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001a02c`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180019f99`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x18001a02c`

## string_xrefs

- `0x180019e78`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019eac`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019fcc`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x18001a06d`: `onecore\base\servicing\updatereservemanager\lib\updatereservemanager.cpp`
- `0x180019e84`: `IsHandleToNonEmptyDirectory`
- `0x180019eb8`: `IsHandleToNonEmptyDirectory`
- `0x180019fd8`: `IsHandleToNonEmptyDirectory`
- `0x18001a079`: `IsHandleToNonEmptyDirectory`

## pseudocode

```c
__int64 __fastcall IsHandleToNonEmptyDirectory(HANDLE hFile, bool *a2)
{
  __int64 result; // rax
  DWORD FinalPathNameByHandleW; // eax
  unsigned __int64 v6; // rdx
  DWORD LastError; // edi
  const char *v8; // rax
  char *FirstFileW; // rbx
  bool v10; // di
  const char *v11; // [rsp+28h] [rbp-E0h] BYREF
  const char *v12; // [rsp+30h] [rbp-D8h]
  __int64 v13; // [rsp+38h] [rbp-D0h]
  const char *v14; // [rsp+40h] [rbp-C8h]
  __int64 v15; // [rsp+48h] [rbp-C0h]
  _BYTE FileInformation[60]; // [rsp+50h] [rbp-B8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+98h] [rbp-70h] BYREF
  WCHAR szFilePath[264]; // [rsp+2E8h] [rbp+1E0h] BYREF

  v15 = -2;
  memset(&FileInformation[8], 0, 52);
  if ( !GetFileInformationByHandle(hFile, (LPBY_HANDLE_FILE_INFORMATION)&FileInformation[8]) )
  {
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        goto LABEL_42;
    }
    else
    {
      LastError = 14077;
    }
    v11 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v12 = "IsHandleToNonEmptyDirectory";
    v13 = 4801;
    v8 = "::GetFileInformationByHandle(FileHandle, &FileInformation)";
    goto LABEL_36;
  }
  if ( (FileInformation[8] & 0x10) == 0 )
  {
    *a2 = 0;
    return 0;
  }
  memset_0(szFilePath, 0, 0x208u);
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(hFile, szFilePath, 0x103u, 1u);
  if ( !FinalPathNameByHandleW )
  {
    if ( !GetLastError() )
    {
      LastError = 14077;
LABEL_9:
      v11 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
      v12 = "IsHandleToNonEmptyDirectory";
      v13 = 4818;
      v8 = "GetLastError";
LABEL_36:
      v14 = v8;
      if ( (int)LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      RtlReportErrorOrigination(&v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
      return LastError;
    }
    LastError = GetLastError();
    if ( LastError )
      goto LABEL_9;
LABEL_42:
    INTERNAL_ERROR_ACTION(-1073741595);
  }
  if ( FinalPathNameByHandleW > 0x104 )
  {
    v11 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v12 = "IsHandleToNonEmptyDirectory";
    v13 = 4822;
    v14 = "static_cast<DWORD>(122L)";
    RtlReportErrorOrigination(&v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, 2147942522LL);
    return 2147942522LL;
  }
  result = StringCchCatW(szFilePath, v6, L"\\*");
  if ( (int)result >= 0 )
  {
    memset_0(&FindFileData, 0, sizeof(FindFileData));
    FirstFileW = (char *)FindFirstFileW(szFilePath, &FindFileData);
    *(_QWORD *)FileInformation = FirstFileW;
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      while ( FindFileData.cFileName[0] == 46
           && (!FindFileData.cFileName[1] || FindFileData.cFileName[1] == 46 && !FindFileData.cFileName[2]) )
      {
        v10 = 0;
        if ( !FindNextFileW(FirstFileW, &FindFileData) )
          goto LABEL_21;
      }
      v10 = 1;
LABEL_21:
      *a2 = v10;
      if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !FindClose(FirstFileW) )
      {
        GetLastError();
        __fastfail(7u);
      }
      return 0;
    }
    if ( GetLastError() )
    {
      LastError = GetLastError();
      if ( !LastError )
        INTERNAL_ERROR_ACTION(-1073741595);
    }
    else
    {
      LastError = 14077;
    }
    v11 = "onecore\\base\\servicing\\updatereservemanager\\lib\\updatereservemanager.cpp";
    v12 = "IsHandleToNonEmptyDirectory";
    v13 = 4832;
    v14 = "FindHandle.IsValid()";
    if ( (int)LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    RtlReportErrorOrigination(&v11, &GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627, LastError);
    if ( (unsigned __int64)(FirstFileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL && !FindClose(FirstFileW) )
    {
      GetLastError();
      __fastfail(7u);
    }
    return LastError;
  }
  return result;
}

```

## disassembly

```asm
0x180019da8  mov     rax, rsp
0x180019dab  push    rbp
0x180019dac  push    rdi
0x180019dad  push    r14
0x180019daf  lea     rbp, [rax-418h]
0x180019db6  sub     rsp, 500h
0x180019dbd  mov     [rsp+510h+var_4D0], 0FFFFFFFFFFFFFFFEh
0x180019dc6  mov     [rax+18h], rbx
0x180019dca  mov     [rax+20h], rsi
0x180019dce  mov     rax, cs:__security_cookie
0x180019dd5  xor     rax, rsp
0x180019dd8  mov     [rbp+410h+var_20], rax
0x180019ddf  mov     rsi, rdx
0x180019de2  mov     rbx, rcx
0x180019de5  xorps   xmm0, xmm0
0x180019de8  xor     eax, eax
0x180019dea  movups  xmmword ptr [rsp+510h+FileInformation.ftCreationTime.dwHighDateTime], xmm0
0x180019def  movups  xmmword ptr [rsp+510h+FileInformation.ftLastWriteTime.dwHighDateTime], xmm0
0x180019df4  movups  xmmword ptr [rsp+510h+FileInformation.nNumberOfLinks], xmm0
0x180019df9  mov     [rbp+410h+var_490], eax
0x180019dfc  lea     rdx, [rsp+510h+FileInformation.ftCreationTime.dwHighDateTime]; lpFileInformation
0x180019e01  call    cs:__imp_GetFileInformationByHandle
0x180019e07  xor     r14d, r14d
0x180019e0a  test    eax, eax
0x180019e0c  jz      loc_18001A05E
0x180019e12  test    byte ptr [rsp+510h+FileInformation.ftCreationTime.dwHighDateTime], 10h
0x180019e17  jnz     short loc_180019E23
0x180019e19  mov     [rsi], r14b
0x180019e1c  xor     eax, eax
0x180019e1e  jmp     loc_18001A0BD
0x180019e23  xor     edx, edx; Val
0x180019e25  mov     r8d, 208h; Size
0x180019e2b  lea     rcx, [rbp+410h+szFilePath]; void *
0x180019e32  call    memset_0
0x180019e37  mov     r9d, 1; dwFlags
0x180019e3d  mov     r8d, 103h; cchFilePath
0x180019e43  lea     rdx, [rbp+410h+szFilePath]; lpszFilePath
0x180019e4a  mov     rcx, rbx; hFile
0x180019e4d  call    cs:__imp_GetFinalPathNameByHandleW
0x180019e53  test    eax, eax
0x180019e55  jnz     short loc_180019EA5
0x180019e57  call    cs:__imp_GetLastError
0x180019e5d  test    eax, eax
0x180019e5f  jnz     short loc_180019E68
0x180019e61  mov     edi, 36FDh
0x180019e66  jmp     short loc_180019E78
0x180019e68  call    cs:__imp_GetLastError
0x180019e6e  mov     edi, eax
0x180019e70  test    eax, eax
0x180019e72  jz      loc_18001A0F4
0x180019e78  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019e7f  mov     [rsp+510h+var_4F0], rax
0x180019e84  lea     rax, aIshandletonone; "IsHandleToNonEmptyDirectory"
0x180019e8b  mov     [rsp+510h+var_4E8], rax
0x180019e90  mov     [rsp+510h+var_4E0], 12D2h
0x180019e99  lea     rax, aGetlasterror; "GetLastError"
0x180019ea0  jmp     loc_18001A095
0x180019ea5  cmp     eax, 104h
0x180019eaa  jbe     short loc_180019EFA
0x180019eac  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019eb3  mov     [rsp+510h+var_4F0], rax
0x180019eb8  lea     rax, aIshandletonone; "IsHandleToNonEmptyDirectory"
0x180019ebf  mov     [rsp+510h+var_4E8], rax
0x180019ec4  mov     [rsp+510h+var_4E0], 12D6h
0x180019ecd  lea     rax, aStaticCastDwor_0; "static_cast<DWORD>(122L)"
0x180019ed4  mov     [rsp+510h+var_4D8], rax
0x180019ed9  mov     r8d, 8007007Ah
0x180019edf  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x180019ee6  lea     rcx, [rsp+510h+var_4F0]
0x180019eeb  call    RtlReportErrorOrigination
0x180019ef0  mov     eax, 8007007Ah
0x180019ef5  jmp     loc_18001A0BD
0x180019efa  lea     r8, asc_18003E9CC; "\\*"
0x180019f01  lea     rcx, [rbp+410h+szFilePath]; wchar_t *
0x180019f08  call    ?StringCchCatW@@YAJPEA_W_KPEB_W@Z; StringCchCatW(wchar_t *,unsigned __int64,wchar_t const *)
0x180019f0d  test    eax, eax
0x180019f0f  js      loc_18001A0BD
0x180019f15  xor     edx, edx; Val
0x180019f17  mov     r8d, 250h; Size
0x180019f1d  lea     rcx, [rbp+410h+FindFileData]; void *
0x180019f21  call    memset_0
0x180019f26  lea     rdx, [rbp+410h+FindFileData]; lpFindFileData
0x180019f2a  lea     rcx, [rbp+410h+szFilePath]; lpFileName
0x180019f31  call    cs:__imp_FindFirstFileW
0x180019f37  mov     rbx, rax
0x180019f3a  mov     qword ptr [rsp+510h+FileInformation.dwFileAttributes], rax
0x180019f3f  dec     rax
0x180019f42  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019f46  ja      short loc_180019FB9
0x180019f48  movzx   eax, [rbp+410h+FindFileData.cFileName+2]
0x180019f4c  cmp     [rbp+410h+FindFileData.cFileName], 2Eh ; '.'
0x180019f51  jnz     short loc_180019F82
0x180019f53  test    ax, ax
0x180019f56  jz      short loc_180019F6C
0x180019f58  cmp     [rbp+410h+FindFileData.cFileName], 2Eh ; '.'
0x180019f5d  jnz     short loc_180019F82
0x180019f5f  cmp     ax, 2Eh ; '.'
0x180019f63  jnz     short loc_180019F82
0x180019f65  cmp     [rbp+410h+FindFileData.cFileName+4], r14w
0x180019f6a  jnz     short loc_180019F82
0x180019f6c  mov     dil, r14b
0x180019f6f  lea     rdx, [rbp+410h+FindFileData]; lpFindFileData
0x180019f73  mov     rcx, rbx; hFindFile
0x180019f76  call    cs:__imp_FindNextFileW
0x180019f7c  test    eax, eax
0x180019f7e  jnz     short loc_180019F48
0x180019f80  jmp     short loc_180019F85
0x180019f82  mov     dil, 1
0x180019f85  mov     [rsi], dil
0x180019f88  lea     rax, [rbx-1]
0x180019f8c  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180019f90  ja      loc_180019E1C
0x180019f96  mov     rcx, rbx; hFindFile
0x180019f99  call    cs:__imp_FindClose
0x180019f9f  test    eax, eax
0x180019fa1  jnz     loc_180019E1C
0x180019fa7  call    cs:__imp_GetLastError
0x180019fad  mov     ecx, 7
0x180019fb2  int     29h; Win8: RtlFailFast(ecx)
0x180019fb4  jmp     loc_180019E1C
0x180019fb9  call    cs:__imp_GetLastError
0x180019fbf  test    eax, eax
0x180019fc1  jnz     loc_18001A049
0x180019fc7  mov     edi, 36FDh
0x180019fcc  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x180019fd3  mov     [rsp+510h+var_4F0], rax
0x180019fd8  lea     rax, aIshandletonone; "IsHandleToNonEmptyDirectory"
0x180019fdf  mov     [rsp+510h+var_4E8], rax
0x180019fe4  mov     [rsp+510h+var_4E0], 12E0h
0x180019fed  lea     rax, aFindhandleIsva; "FindHandle.IsValid()"
0x180019ff4  mov     [rsp+510h+var_4D8], rax
0x180019ff9  test    edi, edi
0x180019ffb  jle     short loc_18001A006
0x180019ffd  movzx   edi, di
0x18001a000  or      edi, 80070000h
0x18001a006  mov     r8d, edi
0x18001a009  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001a010  lea     rcx, [rsp+510h+var_4F0]
0x18001a015  call    RtlReportErrorOrigination
0x18001a01a  nop
0x18001a01b  lea     rax, [rbx-1]
0x18001a01f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18001a023  ja      loc_18001A0BB
0x18001a029  mov     rcx, rbx; hFindFile
0x18001a02c  call    cs:__imp_FindClose
0x18001a032  test    eax, eax
0x18001a034  jnz     loc_18001A0BB
0x18001a03a  call    cs:__imp_GetLastError
0x18001a040  mov     ecx, 7
0x18001a045  int     29h; Win8: RtlFailFast(ecx)
0x18001a047  jmp     short loc_18001A0BB
0x18001a049  call    cs:__imp_GetLastError
0x18001a04f  mov     edi, eax
0x18001a051  test    eax, eax
0x18001a053  jz      loc_18001A0FF
0x18001a059  jmp     loc_180019FCC
0x18001a05e  call    cs:__imp_GetLastError
0x18001a064  test    eax, eax
0x18001a066  jnz     short loc_18001A0E4
0x18001a068  mov     edi, 36FDh
0x18001a06d  lea     rax, aOnecoreBaseSer_1; "onecore\\base\\servicing\\updatereserve"...
0x18001a074  mov     [rsp+510h+var_4F0], rax
0x18001a079  lea     rax, aIshandletonone; "IsHandleToNonEmptyDirectory"
0x18001a080  mov     [rsp+510h+var_4E8], rax
0x18001a085  mov     [rsp+510h+var_4E0], 12C1h
0x18001a08e  lea     rax, aGetfileinforma; "::GetFileInformationByHandle(FileHandle"...
0x18001a095  test    edi, edi
0x18001a097  mov     [rsp+510h+var_4D8], rax
0x18001a09c  jle     short loc_18001A0A7
0x18001a09e  movzx   edi, di
0x18001a0a1  or      edi, 80070000h
0x18001a0a7  mov     r8d, edi
0x18001a0aa  lea     rdx, _GUID_e323b7c4_7a1a_4e06_bf6d_56ccd7377627
0x18001a0b1  lea     rcx, [rsp+510h+var_4F0]
0x18001a0b6  call    RtlReportErrorOrigination
0x18001a0bb  mov     eax, edi
0x18001a0bd  mov     rcx, [rbp+410h+var_20]
0x18001a0c4  xor     rcx, rsp; StackCookie
0x18001a0c7  call    __security_check_cookie
0x18001a0cc  lea     r11, [rsp+510h+var_10]
0x18001a0d4  mov     rbx, [r11+30h]
0x18001a0d8  mov     rsi, [r11+38h]
0x18001a0dc  mov     rsp, r11
0x18001a0df  pop     r14
0x18001a0e1  pop     rdi
0x18001a0e2  pop     rbp
0x18001a0e3  retn
0x18001a0e4  call    cs:__imp_GetLastError
0x18001a0ea  mov     edi, eax
0x18001a0ec  test    eax, eax
0x18001a0ee  jnz     loc_18001A06D
0x18001a0f4  mov     ecx, 0C00000E5h; int
0x18001a0f9  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
0x18001a0ff  mov     ecx, 0C00000E5h; int
0x18001a104  call    ?INTERNAL_ERROR_ACTION@@YAXJ@Z; INTERNAL_ERROR_ACTION(long)
```
