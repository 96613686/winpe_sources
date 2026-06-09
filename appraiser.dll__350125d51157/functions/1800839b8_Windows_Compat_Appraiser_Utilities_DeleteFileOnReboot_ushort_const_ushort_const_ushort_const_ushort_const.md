# Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot(ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800839b8`
- end: `0x180083f1b`
- name: `?DeleteFileOnReboot@Utilities@Appraiser@Compat@Windows@@SAJPEBG000@Z`
- size: `1379`
- prototype: `__int64 __fastcall(wchar_t *String1, LPCWSTR lpExistingFileName, char *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, reparse_path, installer_update, broker_com_uri`

## callers

- `0x180083f24`

## callees

- `0x180008570`
- `0x1800092dc`
- `0x180011d94`
- `0x18002ebb8`
- `0x1800301d0`
- `0x180052d0c`
- `0x1800839b8`
- `0x1801abfd8`
- `0x1802174d8`

## import_xrefs

- `KERNEL32!GetFileInformationByHandleEx` at `0x180083b39`
- `KERNEL32!GetFileInformationByHandleEx` at `0x180083b39`
- `KERNEL32!MoveFileExW` at `0x180083df9`
- `KERNEL32!MoveFileExW` at `0x180083e78`
- `KERNEL32!MoveFileExW` at `0x180083df9`
- `KERNEL32!MoveFileExW` at `0x180083e78`
- `KERNEL32!CreateFileW` at `0x180083a82`
- `KERNEL32!CreateFileW` at `0x180083a82`
- `KERNEL32!GetLastError` at `0x180083a98`
- `KERNEL32!GetLastError` at `0x180083b47`
- `KERNEL32!GetLastError` at `0x180083e03`
- `KERNEL32!GetLastError` at `0x180083e82`
- `KERNEL32!GetLastError` at `0x180083a98`
- `KERNEL32!GetLastError` at `0x180083b47`
- `KERNEL32!GetLastError` at `0x180083e03`
- `KERNEL32!GetLastError` at `0x180083e82`

## string_xrefs

- `0x180083ac6`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083b08`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083b70`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083bbe`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083bff`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083c2b`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083cc8`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083cec`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x180083ab1`: `Failed to open directory handle: [0x%x].`
- `0x180083af1`: `Failed to open directory handle: [0x%x].`
- `0x180083b77`: `Windows::Compat::Appraiser::IsDirectoryReparsePoint`
- `0x180083bb2`: `Windows::Compat::Appraiser::IsDirectoryReparsePoint`
- `0x180083be7`: `Failed to query directory attributes: [0x%x].`
- `0x180083c51`: `Failed to query directory attributes: [0x%x].`
- `0x180083a1b`: `DELETE_`
- `0x180083d1d`: `DELETE_`
- `0x180083cbc`: `Failed to copy expanded path to RenamedFilePath: [0x%x].`
- `0x180083cf9`: `Failed to copy expanded path to RenamedFilePath: [0x%x].`
- `0x180083ad2`: `Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot`
- `0x180083afc`: `Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot`
- `0x180083bf3`: `Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot`
- `0x180083c1f`: `Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot`
- `0x180083cd8`: `Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot`
- `0x180083d04`: `Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot`
- `0x180083d65`: `Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot`
- `0x180083c14`: `Directory is a reparse point; refusing to continue processing: %ls [0x%x].`
- `0x180083d4b`: `Failed to create renamed file: [0x%x].`
- `0x180083d72`: `Failed to create renamed file: [0x%x].`
- `0x180083da7`: `Failed to combine renamed filename to delete: [0x%x].`
- `0x180083dd3`: `Failed to combine renamed filename to delete: [0x%x].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot(
        wchar_t *String1,
        WCHAR *lpExistingFileName,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  signed int v8; // ebx
  char *FileW; // rdi
  signed int LastError; // eax
  char v11; // dl
  signed int v12; // eax
  bool v13; // bl
  char v14; // dl
  __int64 v15; // rax
  WCHAR *v16; // r8
  __int64 v17; // rdx
  WCHAR *v18; // rcx
  const char *v19; // r9
  HRESULT v20; // eax
  signed int v21; // eax
  signed int v22; // eax
  const char *dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  const char *dwFlagsAndAttributes; // [rsp+28h] [rbp-D8h]
  const char *dwFlagsAndAttributesa; // [rsp+28h] [rbp-D8h]
  const char *hTemplateFile; // [rsp+30h] [rbp-D0h]
  WCHAR *hTemplateFilea; // [rsp+30h] [rbp-D0h]
  int v29; // [rsp+38h] [rbp-C8h]
  __int64 FileInformation; // [rsp+40h] [rbp-C0h] BYREF
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR pszMore[264]; // [rsp+260h] [rbp+160h] BYREF

  memset_0(pszPath, 0, 0x208u);
  memset_0(pszMore, 0, 0x208u);
  if ( !wcsncmp_0(String1, L"DELETE_", 7u) )
    return 0;
  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_MSRC105182>::GetImpl'::`2'::impl) )
    goto LABEL_29;
  if ( a3 )
  {
    FileW = (char *)CreateFileW(a3, 0xA0u, 7u, 0, 3u, 0x2200000u, 0);
    if ( ((unsigned __int64)(FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0 )
      goto LABEL_14;
  }
  else
  {
    FileW = 0;
  }
  LastError = GetLastError();
  v8 = LastError;
  if ( LastError > 0 )
    v8 = (unsigned __int16)LastError | 0x80070000;
  if ( v8 < 0 )
  {
    LODWORD(hTemplateFile) = v8;
    dwFlagsAndAttributes = "Failed to open directory handle: [0x%x].";
    v11 = 114;
LABEL_11:
    LODWORD(dwCreationDisposition) = v8;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v11,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      dwCreationDisposition,
      (int)dwFlagsAndAttributes,
      hTemplateFile);
    return (unsigned int)v8;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x272u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      "Failed to open directory handle: [0x%x].",
      v8);
LABEL_14:
  FileInformation = 0;
  if ( (unsigned __int64)(FileW - 1) > 0xFFFFFFFFFFFFFFFDuLL )
  {
    v8 = -2147024890;
    goto LABEL_28;
  }
  if ( !GetFileInformationByHandleEx(FileW, FileAttributeTagInfo, &FileInformation, 8u) )
  {
    v12 = GetLastError();
    v8 = v12;
    if ( v12 > 0 )
      v8 = (unsigned __int16)v12 | 0x80070000;
    if ( v8 < 0 )
    {
      LODWORD(hTemplateFile) = v8;
      LODWORD(dwCreationDisposition) = v8;
      Windows::Compat::Appraiser::WriteLog(
        (Windows::Compat::Appraiser *)1,
        8,
        (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::IsDirectoryReparsePoint",
        dwCreationDisposition,
        (int)"GetFileInformationByHandleEx Failed: [0x%x].",
        hTemplateFile);
LABEL_28:
      LODWORD(hTemplateFile) = v8;
      dwFlagsAndAttributes = "Failed to query directory attributes: [0x%x].";
      v11 = 118;
      goto LABEL_11;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x108u,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::IsDirectoryReparsePoint",
        "GetFileInformationByHandleEx Failed: [0x%x].",
        v8);
  }
  v13 = (FileInformation & 0x400) != 0;
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x276u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      "Failed to query directory attributes: [0x%x].",
      0);
  if ( v13 )
  {
    v8 = -2147020501;
    v29 = -2147020501;
    hTemplateFilea = (WCHAR *)a3;
    dwFlagsAndAttributesa = "Directory is a reparse point; refusing to continue processing: %ls [0x%x].";
    v14 = 123;
LABEL_26:
    LODWORD(dwCreationDisposition) = v8;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v14,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      dwCreationDisposition,
      (int)dwFlagsAndAttributesa,
      (const char *)hTemplateFilea,
      v29);
    return (unsigned int)v8;
  }
LABEL_29:
  v15 = 2147483646;
  v16 = pszPath;
  v17 = 260;
  do
  {
    if ( !v15 )
      break;
    if ( !*a3 )
      break;
    *v16++ = *a3++;
    --v15;
    --v17;
  }
  while ( v17 );
  v18 = v16 - 1;
  v8 = v17 == 0 ? 0x8007007A : 0;
  if ( v17 )
    v18 = v16;
  *v18 = 0;
  if ( !v17 )
  {
    v19 = "Failed to copy expanded path to RenamedFilePath: [0x%x].";
    v11 = -125;
LABEL_37:
    LODWORD(hTemplateFile) = v8;
    LODWORD(dwFlagsAndAttributes) = (_DWORD)v19;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x283u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      "Failed to copy expanded path to RenamedFilePath: [0x%x].",
      v17 == 0 ? 0x8007007A : 0);
  v8 = StringCchPrintfW(pszMore, 0x104u, L"%ls%ls_%ls", L"DELETE_", a4, String1);
  if ( v8 < 0 )
  {
    v19 = "Failed to create renamed file: [0x%x].";
    v11 = -122;
    goto LABEL_37;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x286u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      "Failed to create renamed file: [0x%x].",
      v8);
  v20 = PathCchAppend(pszPath, 0x104u, pszMore);
  v8 = v20;
  if ( v20 < 0 )
  {
    LODWORD(hTemplateFile) = v20;
    dwFlagsAndAttributes = "Failed to combine renamed filename to delete: [0x%x].";
    v11 = -119;
    goto LABEL_11;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x289u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      "Failed to combine renamed filename to delete: [0x%x].",
      v20);
  if ( !MoveFileExW(lpExistingFileName, pszPath, 1u) )
  {
    v21 = GetLastError();
    v8 = v21;
    if ( v21 > 0 )
      v8 = (unsigned __int16)v21 | 0x80070000;
    if ( v8 < 0 )
    {
      v29 = v8;
      hTemplateFilea = lpExistingFileName;
      dwFlagsAndAttributesa = "Error renaming %ls: [0x%x].";
      v14 = -114;
      goto LABEL_26;
    }
    if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
      Windows::Compat::Appraiser::WicaFactory::RunPrintf(
        0x28Eu,
        "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
        "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
        "Error renaming %ls: [0x%x].",
        lpExistingFileName,
        v8);
  }
  if ( MoveFileExW(pszPath, 0, 4u) )
    return (unsigned int)v8;
  v22 = GetLastError();
  v8 = v22;
  if ( v22 > 0 )
    v8 = (unsigned __int16)v22 | 0x80070000;
  if ( v8 < 0 )
  {
    v29 = v8;
    hTemplateFilea = pszPath;
    v14 = -108;
    dwFlagsAndAttributesa = "Error marking %ls for deletion on reboot: [0x%x].";
    goto LABEL_26;
  }
  if ( (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x294u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::DeleteFileOnReboot",
      "Error marking %ls for deletion on reboot: [0x%x].",
      pszPath,
      v8);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x1800839b8  push    rbp
0x1800839ba  push    rbx
0x1800839bb  push    rsi
0x1800839bc  push    rdi
0x1800839bd  push    r12
0x1800839bf  push    r13
0x1800839c1  push    r14
0x1800839c3  push    r15
0x1800839c5  lea     rbp, [rsp-388h]
0x1800839cd  sub     rsp, 488h
0x1800839d4  mov     rax, cs:__security_cookie
0x1800839db  xor     rax, rsp
0x1800839de  mov     [rbp+3C0h+var_50], rax
0x1800839e5  mov     rsi, r8
0x1800839e8  mov     r14, rdx
0x1800839eb  mov     r15, rcx
0x1800839ee  mov     ebx, 208h
0x1800839f3  mov     r8d, ebx; Size
0x1800839f6  lea     rcx, [rsp+4C0h+pszPath]; void *
0x1800839fb  xor     edx, edx; Val
0x1800839fd  mov     r12, r9
0x180083a00  call    memset_0
0x180083a05  mov     r8d, ebx; Size
0x180083a08  lea     rcx, [rbp+3C0h+pszMore]; void *
0x180083a0f  xor     edx, edx; Val
0x180083a11  call    memset_0
0x180083a16  mov     ebx, 7
0x180083a1b  lea     rdx, aDelete_0; "DELETE_"
0x180083a22  mov     r8d, ebx; MaxCount
0x180083a25  mov     rcx, r15; String1
0x180083a28  call    wcsncmp_0
0x180083a2d  xor     r13d, r13d
0x180083a30  test    eax, eax
0x180083a32  jnz     short loc_180083A3C
0x180083a34  mov     ebx, r13d
0x180083a37  jmp     loc_180083EF6
0x180083a3c  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_MSRC105182@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MSRC105182@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182> `wil::Feature<__WilFeatureTraits_Feature_Servicing_MSRC105182>::GetImpl(void)'::`2'::impl
0x180083a43  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_MSRC105182@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_MSRC105182>::__private_IsEnabled(void)
0x180083a48  mov     edi, 1
0x180083a4d  test    al, al
0x180083a4f  jz      loc_180083C6B
0x180083a55  test    rsi, rsi
0x180083a58  jnz     short loc_180083A5F
0x180083a5a  mov     rdi, r13
0x180083a5d  jmp     short loc_180083A98
0x180083a5f  mov     [rsp+4C0h+hTemplateFile], r13; hTemplateFile
0x180083a64  xor     r9d, r9d; lpSecurityAttributes
0x180083a67  mov     [rsp+4C0h+dwFlagsAndAttributes], 2200000h; dwFlagsAndAttributes
0x180083a6f  mov     r8d, ebx; dwShareMode
0x180083a72  mov     edx, 0A0h; dwDesiredAccess
0x180083a77  mov     [rsp+4C0h+dwCreationDisposition], 3; dwCreationDisposition
0x180083a7f  mov     rcx, rsi; lpFileName
0x180083a82  call    cs:__imp_CreateFileW
0x180083a88  mov     rdi, rax
0x180083a8b  lea     rcx, [rax+1]
0x180083a8f  test    rcx, 0FFFFFFFFFFFFFFFEh
0x180083a96  jnz     short loc_180083B14
0x180083a98  call    cs:__imp_GetLastError
0x180083a9e  mov     ebx, eax
0x180083aa0  test    eax, eax
0x180083aa2  jle     short loc_180083AAD
0x180083aa4  movzx   ebx, ax
0x180083aa7  or      ebx, 80070000h
0x180083aad  test    ebx, ebx
0x180083aaf  jns     short loc_180083AE7
0x180083ab1  lea     r9, aFailedToOpenDi; "Failed to open directory handle: [0x%x]"...
0x180083ab8  mov     dword ptr [rsp+4C0h+hTemplateFile], ebx; char *
0x180083abc  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], r9; int
0x180083ac1  mov     edx, 272h; bool
0x180083ac6  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083acd  mov     ecx, 1; this
0x180083ad2  lea     r9, aWindowsCompatA_819; "Windows::Compat::Appraiser::Utilities::"...
0x180083ad9  mov     [rsp+4C0h+dwCreationDisposition], ebx; char *
0x180083add  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180083ae2  jmp     loc_180083EF6
0x180083ae7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083aed  test    al, 1
0x180083aef  jz      short loc_180083B14
0x180083af1  lea     r9, aFailedToOpenDi; "Failed to open directory handle: [0x%x]"...
0x180083af8  mov     [rsp+4C0h+dwCreationDisposition], ebx
0x180083afc  lea     r8, aWindowsCompatA_819; "Windows::Compat::Appraiser::Utilities::"...
0x180083b03  mov     ecx, 272h; unsigned int
0x180083b08  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083b0f  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180083b14  lea     rax, [rdi-1]
0x180083b18  mov     [rsp+4C0h+FileInformation], r13
0x180083b1d  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180083b21  ja      loc_180083C4C
0x180083b27  mov     r9d, 8; dwBufferSize
0x180083b2d  lea     r8, [rsp+4C0h+FileInformation]; lpFileInformation
0x180083b32  mov     rcx, rdi; hFile
0x180083b35  lea     edx, [r9+1]; FileInformationClass
0x180083b39  call    cs:__imp_GetFileInformationByHandleEx
0x180083b3f  test    eax, eax
0x180083b41  jnz     loc_180083BCC
0x180083b47  call    cs:__imp_GetLastError
0x180083b4d  mov     ebx, eax
0x180083b4f  test    eax, eax
0x180083b51  jle     short loc_180083B5C
0x180083b53  movzx   ebx, ax
0x180083b56  or      ebx, 80070000h
0x180083b5c  test    ebx, ebx
0x180083b5e  jns     short loc_180083B96
0x180083b60  lea     r9, aGetfileinforma_0; "GetFileInformationByHandleEx Failed: [0"...
0x180083b67  mov     dword ptr [rsp+4C0h+hTemplateFile], ebx; char *
0x180083b6b  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], r9; int
0x180083b70  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083b77  lea     r9, aWindowsCompatA_829; "Windows::Compat::Appraiser::IsDirectory"...
0x180083b7e  mov     [rsp+4C0h+dwCreationDisposition], ebx; char *
0x180083b82  mov     edx, 108h; bool
0x180083b87  mov     ecx, 1; this
0x180083b8c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180083b91  jmp     loc_180083C51
0x180083b96  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083b9c  mov     edi, 1
0x180083ba1  and     eax, edi
0x180083ba3  test    al, al
0x180083ba5  jz      short loc_180083BD1
0x180083ba7  lea     r9, aGetfileinforma_0; "GetFileInformationByHandleEx Failed: [0"...
0x180083bae  mov     [rsp+4C0h+dwCreationDisposition], ebx
0x180083bb2  lea     r8, aWindowsCompatA_829; "Windows::Compat::Appraiser::IsDirectory"...
0x180083bb9  mov     ecx, 108h; unsigned int
0x180083bbe  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083bc5  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180083bca  jmp     short loc_180083BD1
0x180083bcc  mov     edi, 1
0x180083bd1  mov     ebx, dword ptr [rsp+4C0h+FileInformation]
0x180083bd5  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083bdb  shr     ebx, 0Ah
0x180083bde  and     eax, edi
0x180083be0  and     bl, dil
0x180083be3  test    al, al
0x180083be5  jz      short loc_180083C0B
0x180083be7  lea     r9, aFailedToQueryD; "Failed to query directory attributes: ["...
0x180083bee  mov     [rsp+4C0h+dwCreationDisposition], r13d
0x180083bf3  lea     r8, aWindowsCompatA_819; "Windows::Compat::Appraiser::Utilities::"...
0x180083bfa  mov     ecx, 276h; unsigned int
0x180083bff  lea     rdx, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083c06  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180083c0b  test    bl, bl
0x180083c0d  jz      short loc_180083C6B
0x180083c0f  mov     ebx, 8007112Bh
0x180083c14  lea     rax, aDirectoryIsARe; "Directory is a reparse point; refusing "...
0x180083c1b  mov     [rsp+4C0h+var_488], ebx
0x180083c1f  lea     r9, aWindowsCompatA_819; "Windows::Compat::Appraiser::Utilities::"...
0x180083c26  mov     [rsp+4C0h+hTemplateFile], rsi; char *
0x180083c2b  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083c32  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax; int
0x180083c37  mov     edx, 27Bh; bool
0x180083c3c  mov     ecx, edi; this
0x180083c3e  mov     [rsp+4C0h+dwCreationDisposition], ebx; char *
0x180083c42  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180083c47  jmp     loc_180083EF6
0x180083c4c  mov     ebx, 80070006h
0x180083c51  lea     rax, aFailedToQueryD; "Failed to query directory attributes: ["...
0x180083c58  mov     dword ptr [rsp+4C0h+hTemplateFile], ebx
0x180083c5c  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], rax
0x180083c61  mov     edx, 276h
0x180083c66  jmp     loc_180083AC6
0x180083c6b  mov     eax, 7FFFFFFEh
0x180083c70  lea     r8, [rsp+4C0h+pszPath]
0x180083c75  mov     edx, 104h
0x180083c7a  test    rax, rax
0x180083c7d  jz      short loc_180083C9B
0x180083c7f  movzx   ecx, word ptr [rsi]
0x180083c82  test    cx, cx
0x180083c85  jz      short loc_180083C9B
0x180083c87  mov     [r8], cx
0x180083c8b  add     rsi, 2
0x180083c8f  add     r8, 2
0x180083c93  sub     rax, rdi
0x180083c96  sub     rdx, rdi
0x180083c99  jnz     short loc_180083C7A
0x180083c9b  mov     rax, rdx
0x180083c9e  lea     rcx, [r8-2]
0x180083ca2  neg     rax
0x180083ca5  sbb     ebx, ebx
0x180083ca7  not     ebx
0x180083ca9  and     ebx, 8007007Ah
0x180083caf  test    rdx, rdx
0x180083cb2  cmovnz  rcx, r8
0x180083cb6  mov     [rcx], r13w
0x180083cba  jnz     short loc_180083CE6
0x180083cbc  lea     r9, aFailedToCopyEx; "Failed to copy expanded path to Renamed"...
0x180083cc3  mov     edx, 283h
0x180083cc8  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083ccf  mov     dword ptr [rsp+4C0h+hTemplateFile], ebx
0x180083cd3  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], r9
0x180083cd8  lea     r9, aWindowsCompatA_819; "Windows::Compat::Appraiser::Utilities::"...
0x180083cdf  mov     ecx, edi
0x180083ce1  jmp     loc_180083AD9
0x180083ce6  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083cec  lea     rsi, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x180083cf3  and     eax, edi
0x180083cf5  test    al, al
0x180083cf7  jz      short loc_180083D18
0x180083cf9  lea     r9, aFailedToCopyEx; "Failed to copy expanded path to Renamed"...
0x180083d00  mov     [rsp+4C0h+dwCreationDisposition], ebx
0x180083d04  lea     r8, aWindowsCompatA_819; "Windows::Compat::Appraiser::Utilities::"...
0x180083d0b  mov     rdx, rsi; char *
0x180083d0e  mov     ecx, 283h; unsigned int
0x180083d13  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180083d18  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], r15
0x180083d1d  lea     r9, aDelete_0; "DELETE_"
0x180083d24  mov     qword ptr [rsp+4C0h+dwCreationDisposition], r12
0x180083d29  lea     r8, aLsLsLs_1; "%ls%ls_%ls"
0x180083d30  mov     r12d, 104h
0x180083d36  lea     rcx, [rbp+3C0h+pszMore]; unsigned __int16 *
0x180083d3d  mov     edx, r12d; unsigned __int64
0x180083d40  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180083d45  mov     ebx, eax
0x180083d47  test    eax, eax
0x180083d49  jns     short loc_180083D5F
0x180083d4b  lea     r9, aFailedToCreate_24; "Failed to create renamed file: [0x%x]."
0x180083d52  mov     r8, rsi
0x180083d55  mov     edx, 286h
0x180083d5a  jmp     loc_180083CCF
0x180083d5f  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083d65  lea     r15, aWindowsCompatA_819; "Windows::Compat::Appraiser::Utilities::"...
0x180083d6c  and     eax, edi
0x180083d6e  test    al, al
0x180083d70  jz      short loc_180083D8D
0x180083d72  lea     r9, aFailedToCreate_24; "Failed to create renamed file: [0x%x]."
0x180083d79  mov     [rsp+4C0h+dwCreationDisposition], ebx
0x180083d7d  mov     r8, r15; char *
0x180083d80  mov     rdx, rsi; char *
0x180083d83  mov     ecx, 286h; unsigned int
0x180083d88  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180083d8d  lea     r8, [rbp+3C0h+pszMore]; pszMore
0x180083d94  mov     rdx, r12; cchPath
0x180083d97  lea     rcx, [rsp+4C0h+pszPath]; pszPath
0x180083d9c  call    PathCchAppend
0x180083da1  mov     ebx, eax
0x180083da3  test    eax, eax
0x180083da5  jns     short loc_180083DC7
0x180083da7  lea     r9, aFailedToCombin; "Failed to combine renamed filename to d"...
0x180083dae  mov     dword ptr [rsp+4C0h+hTemplateFile], eax
0x180083db2  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], r9
0x180083db7  mov     r8, rsi
0x180083dba  mov     r9, r15
0x180083dbd  mov     edx, 289h
0x180083dc2  jmp     loc_180083CDF
0x180083dc7  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083dcd  and     eax, edi
0x180083dcf  test    al, al
0x180083dd1  jz      short loc_180083DEE
0x180083dd3  lea     r9, aFailedToCombin; "Failed to combine renamed filename to d"...
0x180083dda  mov     [rsp+4C0h+dwCreationDisposition], ebx
0x180083dde  mov     r8, r15; char *
0x180083de1  mov     rdx, rsi; char *
0x180083de4  mov     ecx, 289h; unsigned int
0x180083de9  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180083dee  mov     r8d, edi; dwFlags
0x180083df1  lea     rdx, [rsp+4C0h+pszPath]; lpNewFileName
0x180083df6  mov     rcx, r14; lpExistingFileName
0x180083df9  call    cs:__imp_MoveFileExW
0x180083dff  test    eax, eax
0x180083e01  jnz     short loc_180083E6D
0x180083e03  call    cs:__imp_GetLastError
0x180083e09  mov     ebx, eax
0x180083e0b  test    eax, eax
0x180083e0d  jle     short loc_180083E18
0x180083e0f  movzx   ebx, ax
0x180083e12  or      ebx, 80070000h
0x180083e18  test    ebx, ebx
0x180083e1a  jns     short loc_180083E41
0x180083e1c  mov     [rsp+4C0h+var_488], ebx
0x180083e20  lea     r9, aErrorRenamingL; "Error renaming %ls: [0x%x]."
0x180083e27  mov     [rsp+4C0h+hTemplateFile], r14
0x180083e2c  mov     r8, rsi
0x180083e2f  mov     qword ptr [rsp+4C0h+dwFlagsAndAttributes], r9
0x180083e34  mov     edx, 28Eh
0x180083e39  mov     r9, r15
0x180083e3c  jmp     loc_180083C3C
0x180083e41  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x180083e47  and     eax, edi
0x180083e49  test    al, al
0x180083e4b  jz      short loc_180083E6D
0x180083e4d  mov     [rsp+4C0h+dwFlagsAndAttributes], ebx
0x180083e51  lea     r9, aErrorRenamingL; "Error renaming %ls: [0x%x]."
0x180083e58  mov     r8, r15; char *
0x180083e5b  mov     qword ptr [rsp+4C0h+dwCreationDisposition], r14
0x180083e60  mov     rdx, rsi; char *
0x180083e63  mov     ecx, 28Eh; unsigned int
0x180083e68  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x180083e6d  xor     edx, edx; lpNewFileName
0x180083e6f  lea     rcx, [rsp+4C0h+pszPath]; lpExistingFileName
0x180083e74  lea     r8d, [rdx+4]; dwFlags
0x180083e78  call    cs:__imp_MoveFileExW
0x180083e7e  test    eax, eax
0x180083e80  jnz     short loc_180083EF6
0x180083e82  call    cs:__imp_GetLastError
0x180083e88  mov     ebx, eax
0x180083e8a  test    eax, eax
0x180083e8c  jle     short loc_180083E97
0x180083e8e  movzx   ebx, ax
0x180083e91  or      ebx, 80070000h
0x180083e97  test    ebx, ebx
0x180083e99  jns     short loc_180083EC5
0x180083e9b  mov     [rsp+4C0h+var_488], ebx
  ... truncated ...
```
