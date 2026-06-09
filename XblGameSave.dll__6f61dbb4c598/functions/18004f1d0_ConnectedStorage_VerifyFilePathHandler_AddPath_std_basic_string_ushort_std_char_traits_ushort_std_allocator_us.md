# ConnectedStorage::VerifyFilePathHandler::AddPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x18004f1d0`
- end: `0x18004f469`
- name: `?AddPath@VerifyFilePathHandler@ConnectedStorage@@QEAAXAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `665`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `14`
- callee_count: `12`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x18004e144`
- `0x18004e240`
- `0x18004e30c`
- `0x18004e3e0`
- `0x18004e4b4`
- `0x18004e5ac`
- `0x18004e6bc`
- `0x18004ef4c`
- `0x18004f0fc`
- `0x18004f554`
- `0x18004f948`
- `0x18004ff08`
- `0x1800500a4`
- `0x1800508b4`

## callees

- `0x180003c70`
- `0x18000aae4`
- `0x18001265c`
- `0x18001c090`
- `0x1800296a4`
- `0x18004df84`
- `0x18004ed6c`
- `0x18004f1d0`
- `0x18004f7c8`
- `0x18004f7f4`
- `0x180050704`
- `0x180050cc0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f28c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f2fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f28c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004f2fa`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004f2a9`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x18004f2a9`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004f362`
- `api-ms-win-core-file-l1-1-0!GetFileInformationByHandle` at `0x18004f362`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f275`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f2de`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f275`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18004f2de`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004f321`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18004f321`

## string_xrefs

- `0x18004f40c`: `AddPath-Sharing`
- `0x18004f436`: `AddPath-CreateFile`
- `0x18004f445`: `AddPath-GetFileInformationByHandle`
- `0x18004f457`: `AddPath-LinkCount`
- `0x18004f41e`: `AddPath-ReparseDir`
- `0x18004f3ff`: `AddPath-ReparseFile`

## pseudocode

```c
__int64 __fastcall ConnectedStorage::VerifyFilePathHandler::AddPath(_QWORD *a1, __int64 a2)
{
  const WCHAR *v3; // rcx
  HANDLE FileW; // rbx
  signed int LastError; // edi
  const unsigned __int16 *v6; // r8
  int v7; // esi
  const WCHAR *v8; // rcx
  const WCHAR *v9; // rcx
  DWORD FileAttributesW; // eax
  const unsigned __int16 *v11; // r8
  const unsigned __int16 *v12; // r8
  __int64 v14; // [rsp+40h] [rbp-59h] BYREF
  _BYTE v15[16]; // [rsp+48h] [rbp-51h] BYREF
  LPCWSTR lpFileName[3]; // [rsp+58h] [rbp-41h] BYREF
  unsigned __int64 v17; // [rsp+70h] [rbp-29h]
  _BY_HANDLE_FILE_INFORMATION FileInformation; // [rsp+78h] [rbp-21h] BYREF
  _BYTE v19[32]; // [rsp+B0h] [rbp+17h] BYREF
  HANDLE v20; // [rsp+D0h] [rbp+37h]

  ConnectedStorage::VerifyFilePathHandler::_SanitizePath(a1, lpFileName, a2);
  if ( *(_QWORD *)std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::find(
                    a1,
                    &v14,
                    lpFileName) == *a1
    && ((unsigned __int8)ConnectedStorage::VerifyFilePathHandler::IsDirectory(lpFileName)
     || (unsigned __int8)ConnectedStorage::VerifyFilePathHandler::IsFile(lpFileName)) )
  {
    v3 = (const WCHAR *)lpFileName;
    if ( v17 > 7 )
      v3 = lpFileName[0];
    FileW = CreateFileW(v3, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
    v14 = (__int64)FileW;
    if ( FileW == (HANDLE)-1LL )
    {
      LastError = GetLastError();
      if ( LastError == 32 )
      {
        v7 = 0;
        while ( 1 )
        {
          LastError = 0;
          Sleep(10 * (v7 + 1));
          v8 = (const WCHAR *)lpFileName;
          if ( v17 > 7 )
            v8 = lpFileName[0];
          FileW = CreateFileW(v8, 0x80010000, 1u, 0, 3u, 0x2200000u, 0);
          ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&v14);
          v14 = (__int64)FileW;
          if ( FileW == (HANDLE)-1LL )
          {
            LastError = GetLastError();
            if ( LastError != 32 )
              break;
          }
          if ( ++v7 >= 5 )
          {
            if ( LastError != 32 )
              break;
            v9 = (const WCHAR *)lpFileName;
            if ( v17 > 7 )
              v9 = lpFileName[0];
            FileAttributesW = GetFileAttributesW(v9);
            if ( FileAttributesW != -1 && (FileAttributesW & 0x400) != 0 )
              ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x800700A1LL, (int)L"AddPath-Sharing", v11);
            goto LABEL_27;
          }
        }
      }
      if ( LastError )
      {
        if ( LastError > 0 )
          LastError = (unsigned __int16)LastError | 0x80070000;
        ConnectedStorage::ReportErrorAndThrow(
          (ConnectedStorage *)(unsigned int)LastError,
          (int)L"AddPath-CreateFile",
          v6);
      }
    }
    memset(&FileInformation, 0, sizeof(FileInformation));
    if ( !GetFileInformationByHandle(FileW, &FileInformation) )
      ConnectedStorage::ReportErrorAndThrow(
        (ConnectedStorage *)0x800700A1LL,
        (int)L"AddPath-GetFileInformationByHandle",
        v12);
    if ( FileInformation.nNumberOfLinks > 1 )
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x800700A1LL, (int)L"AddPath-LinkCount", v12);
    if ( (FileInformation.dwFileAttributes & 0x400) != 0 )
    {
      if ( (FileInformation.dwFileAttributes & 0x10) == 0 )
        ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x800700A1LL, (int)L"AddPath-ReparseFile", v12);
      ConnectedStorage::ReportErrorAndThrow((ConnectedStorage *)0x800700A1LL, (int)L"AddPath-ReparseDir", v12);
    }
    std::wstring::wstring(v19, lpFileName);
    v20 = FileW;
    v14 = -1;
    std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Emplace<std::pair<std::wstring,ConnectedStorage::Handle>>(
      a1,
      v15,
      v19);
    std::pair<std::wstring,ConnectedStorage::Handle>::~pair<std::wstring,ConnectedStorage::Handle>(v19);
LABEL_27:
    ConnectedStorage::Handle::CloseHandle((ConnectedStorage::Handle *)&v14);
  }
  return std::wstring::_Tidy_deallocate(lpFileName);
}

```

## disassembly

```asm
0x18004f1d0  mov     [rsp-8+arg_10], rbx
0x18004f1d5  mov     [rsp-8+arg_18], rsi
0x18004f1da  push    rbp
0x18004f1db  push    rdi
0x18004f1dc  push    r14
0x18004f1de  lea     rbp, [rsp-47h]
0x18004f1e3  sub     rsp, 0E0h
0x18004f1ea  mov     rax, cs:__security_cookie
0x18004f1f1  xor     rax, rsp
0x18004f1f4  mov     [rbp+57h+var_18], rax
0x18004f1f8  mov     r14, rcx
0x18004f1fb  mov     r8, rdx
0x18004f1fe  lea     rdx, [rbp+57h+lpFileName]
0x18004f202  call    ?_SanitizePath@VerifyFilePathHandler@ConnectedStorage@@AEAA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEBV34@@Z; ConnectedStorage::VerifyFilePathHandler::_SanitizePath(std::wstring const &)
0x18004f207  nop
0x18004f208  lea     r8, [rbp+57h+lpFileName]
0x18004f20c  lea     rdx, [rbp+57h+var_B0]
0x18004f210  mov     rcx, r14
0x18004f213  call    ?find@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@std@@@std@@@2@AEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@2@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::find(std::wstring const &)
0x18004f218  mov     rcx, [r14]
0x18004f21b  cmp     [rax], rcx
0x18004f21e  jnz     loc_18004F3D2
0x18004f224  lea     rcx, [rbp+57h+lpFileName]
0x18004f228  call    ?IsDirectory@VerifyFilePathHandler@ConnectedStorage@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::IsDirectory(std::wstring const &)
0x18004f22d  test    al, al
0x18004f22f  jnz     short loc_18004F242
0x18004f231  lea     rcx, [rbp+57h+lpFileName]
0x18004f235  call    ?IsFile@VerifyFilePathHandler@ConnectedStorage@@SA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; ConnectedStorage::VerifyFilePathHandler::IsFile(std::wstring const &)
0x18004f23a  test    al, al
0x18004f23c  jz      loc_18004F3D2
0x18004f242  lea     rcx, [rbp+57h+lpFileName]
0x18004f246  cmp     [rbp+57h+var_80], 7
0x18004f24b  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18004f250  mov     [rsp+0F0h+hTemplateFile], 0; hTemplateFile
0x18004f259  mov     [rsp+0F0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18004f261  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004f269  xor     r9d, r9d; lpSecurityAttributes
0x18004f26c  mov     edx, 80010000h; dwDesiredAccess
0x18004f271  lea     r8d, [r9+1]; dwShareMode
0x18004f275  call    cs:__imp_CreateFileW
0x18004f27b  mov     rbx, rax
0x18004f27e  mov     [rbp+57h+var_B0], rax
0x18004f282  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18004f286  jnz     loc_18004F347
0x18004f28c  call    cs:__imp_GetLastError
0x18004f292  mov     edi, eax
0x18004f294  cmp     eax, 20h ; ' '
0x18004f297  jnz     loc_18004F33F
0x18004f29d  xor     esi, esi
0x18004f29f  xor     edi, edi
0x18004f2a1  lea     eax, [rsi+1]
0x18004f2a4  lea     ecx, [rax+rax*4]
0x18004f2a7  add     ecx, ecx; dwMilliseconds
0x18004f2a9  call    cs:__imp_Sleep
0x18004f2af  lea     rcx, [rbp+57h+lpFileName]
0x18004f2b3  cmp     [rbp+57h+var_80], 7
0x18004f2b8  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18004f2bd  mov     [rsp+0F0h+hTemplateFile], rdi; hTemplateFile
0x18004f2c2  mov     [rsp+0F0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x18004f2ca  mov     [rsp+0F0h+dwCreationDisposition], 3; dwCreationDisposition
0x18004f2d2  xor     r9d, r9d; lpSecurityAttributes
0x18004f2d5  mov     edx, 80010000h; dwDesiredAccess
0x18004f2da  lea     r8d, [rdi+1]; dwShareMode
0x18004f2de  call    cs:__imp_CreateFileW
0x18004f2e4  mov     rbx, rax
0x18004f2e7  lea     rcx, [rbp+57h+var_B0]; this
0x18004f2eb  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x18004f2f0  mov     [rbp+57h+var_B0], rbx
0x18004f2f4  cmp     rbx, 0FFFFFFFFFFFFFFFFh
0x18004f2f8  jnz     short loc_18004F307
0x18004f2fa  call    cs:__imp_GetLastError
0x18004f300  mov     edi, eax
0x18004f302  cmp     eax, 20h ; ' '
0x18004f305  jnz     short loc_18004F33F
0x18004f307  inc     esi
0x18004f309  cmp     esi, 5
0x18004f30c  jl      short loc_18004F29F
0x18004f30e  cmp     edi, 20h ; ' '
0x18004f311  jnz     short loc_18004F33F
0x18004f313  lea     rcx, [rbp+57h+lpFileName]
0x18004f317  cmp     [rbp+57h+var_80], 7
0x18004f31c  cmova   rcx, [rbp+57h+lpFileName]; lpFileName
0x18004f321  call    cs:__imp_GetFileAttributesW
0x18004f327  cmp     eax, 0FFFFFFFFh
0x18004f32a  jz      loc_18004F3C8
0x18004f330  bt      eax, 0Ah
0x18004f334  jb      loc_18004F40C
0x18004f33a  jmp     loc_18004F3C8
0x18004f33f  test    edi, edi
0x18004f341  jnz     loc_18004F42B
0x18004f347  xorps   xmm0, xmm0
0x18004f34a  xor     eax, eax
0x18004f34c  movups  xmmword ptr [rbp+57h+FileInformation.dwFileAttributes], xmm0
0x18004f350  movups  xmmword ptr [rbp+57h+FileInformation.ftLastAccessTime.dwHighDateTime], xmm0
0x18004f354  movups  xmmword ptr [rbp+57h+FileInformation.nFileSizeHigh], xmm0
0x18004f358  mov     [rbp+57h+FileInformation.nFileIndexLow], eax
0x18004f35b  lea     rdx, [rbp+57h+FileInformation]; lpFileInformation
0x18004f35f  mov     rcx, rbx; hFile
0x18004f362  call    cs:__imp_GetFileInformationByHandle
0x18004f368  test    eax, eax
0x18004f36a  jz      loc_18004F445
0x18004f370  cmp     [rbp+57h+FileInformation.nNumberOfLinks], 1
0x18004f374  ja      loc_18004F457
0x18004f37a  test    [rbp+57h+FileInformation.dwFileAttributes], 400h
0x18004f381  jz      short loc_18004F394
0x18004f383  mov     ecx, 800700A1h; this
0x18004f388  test    byte ptr [rbp+57h+FileInformation.dwFileAttributes], 10h
0x18004f38c  jnz     loc_18004F41E
0x18004f392  jmp     short loc_18004F3FF
0x18004f394  lea     rdx, [rbp+57h+lpFileName]
0x18004f398  lea     rcx, [rbp+57h+var_40]
0x18004f39c  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x18004f3a1  mov     [rbp+57h+var_20], rbx
0x18004f3a5  mov     [rbp+57h+var_B0], 0FFFFFFFFFFFFFFFFh
0x18004f3ad  lea     r8, [rbp+57h+var_40]
0x18004f3b1  lea     rdx, [rbp+57h+var_A8]
0x18004f3b5  mov     rcx, r14
0x18004f3b8  call    ??$_Emplace@U?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@?$_Tree@V?$_Tmap_traits@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@1@@Z; std::_Tree<std::_Tmap_traits<std::wstring,ConnectedStorage::Handle,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,ConnectedStorage::Handle>>,0>>::_Emplace<std::pair<std::wstring,ConnectedStorage::Handle>>(std::pair<std::wstring,ConnectedStorage::Handle> &&)
0x18004f3bd  nop
0x18004f3be  lea     rcx, [rbp+57h+var_40]
0x18004f3c2  call    ??1?$pair@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@VHandle@ConnectedStorage@@@std@@QEAA@XZ; std::pair<std::wstring,ConnectedStorage::Handle>::~pair<std::wstring,ConnectedStorage::Handle>(void)
0x18004f3c7  nop
0x18004f3c8  lea     rcx, [rbp+57h+var_B0]; this
0x18004f3cc  call    ?CloseHandle@Handle@ConnectedStorage@@AEAAXXZ; ConnectedStorage::Handle::CloseHandle(void)
0x18004f3d1  nop
0x18004f3d2  lea     rcx, [rbp+57h+lpFileName]
0x18004f3d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18004f3db  mov     rcx, [rbp+57h+var_18]
0x18004f3df  xor     rcx, rsp; StackCookie
0x18004f3e2  call    __security_check_cookie
0x18004f3e7  lea     r11, [rsp+0F0h+var_10]
0x18004f3ef  mov     rbx, [r11+30h]
0x18004f3f3  mov     rsi, [r11+38h]
0x18004f3f7  mov     rsp, r11
0x18004f3fa  pop     r14
0x18004f3fc  pop     rdi
0x18004f3fd  pop     rbp
0x18004f3fe  retn
0x18004f3ff  lea     rdx, aAddpathReparse; "AddPath-ReparseFile"
0x18004f406  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004f40c  lea     rdx, aAddpathSharing; "AddPath-Sharing"
0x18004f413  mov     ecx, 800700A1h; this
0x18004f418  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004f41e  lea     rdx, aAddpathReparse_0; "AddPath-ReparseDir"
0x18004f425  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004f42b  jle     short loc_18004F436
0x18004f42d  movzx   edi, di
0x18004f430  or      edi, 80070000h
0x18004f436  lea     rdx, aAddpathCreatef; "AddPath-CreateFile"
0x18004f43d  mov     ecx, edi; this
0x18004f43f  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004f445  lea     rdx, aAddpathGetfile; "AddPath-GetFileInformationByHandle"
0x18004f44c  mov     ecx, 800700A1h; this
0x18004f451  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
0x18004f457  lea     rdx, aAddpathLinkcou; "AddPath-LinkCount"
0x18004f45e  mov     ecx, 800700A1h; this
0x18004f463  call    ?ReportErrorAndThrow@ConnectedStorage@@YAXJPEBG@Z; ConnectedStorage::ReportErrorAndThrow(long,ushort const *)
```
