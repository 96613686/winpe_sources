# _lambda_5a7d2997223d1a4f03f0747b99dabd30_::operator()(Windows::Internal::CHSTRINGResult &)

- ea: `0x18009f404`
- end: `0x18009f6d6`
- name: `??R_lambda_5a7d2997223d1a4f03f0747b99dabd30_@@QEBAJAEAVCHSTRINGResult@Internal@Windows@@@Z`
- size: `722`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `reparse_path, registry_config, service_task, broker_com_uri`

## callers

- `0x1800b89b0`

## callees

- `0x180010810`
- `0x1800124a8`
- `0x1800128a4`
- `0x180013c14`
- `0x180015310`
- `0x1800153f8`
- `0x18001a540`
- `0x18002327c`
- `0x180023634`
- `0x18009f404`
- `0x1800a1540`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f435`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x18009f435`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x18009f563`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x18009f613`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x18009f563`
- `api-ms-win-core-localization-l1-2-0!GetFileMUIPath` at `0x18009f613`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009f4f3`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18009f4f3`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18009f48c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18009f48c`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall _lambda_5a7d2997223d1a4f03f0747b99dabd30_::operator()(__int64 a1, __int64 a2)
{
  __int64 v4; // rcx
  const WCHAR *StringRawBuffer; // rdi
  HRESULT v6; // eax
  const char *v7; // r9
  unsigned int LastError; // ebx
  __int64 v9; // rdx
  __int64 v10; // rax
  __int64 v11; // rcx
  __int64 v12; // rbx
  const WCHAR *v13; // r8
  PWSTR *p_ppszPath; // rcx
  const char *v15; // r9
  __int64 v16; // rdx
  __int64 v17; // rdx
  PWSTR v18; // rbx
  int HtmlFileWideCharContent; // eax
  char v20; // r8
  int pwszFileMUIPath; // [rsp+20h] [rbp-59h]
  int pwszFileMUIPatha; // [rsp+20h] [rbp-59h]
  HSTRING v24; // [rsp+40h] [rbp-39h] BYREF
  PWSTR v25; // [rsp+48h] [rbp-31h] BYREF
  ULONG pcchFileMUIPath; // [rsp+50h] [rbp-29h] BYREF
  PWSTR ppszPath; // [rsp+58h] [rbp-21h] BYREF
  PWSTR pszPath; // [rsp+60h] [rbp-19h] BYREF
  HSTRING Reserved1; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int64 pululEnumerator; // [rsp+70h] [rbp-9h] BYREF
  KNOWNFOLDERID rfid; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER v32; // [rsp+88h] [rbp+Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)a1, 0);
  pszPath = 0;
  if ( !*(_DWORD *)(a1 + 20) )
    goto LABEL_13;
  rfid = FOLDERID_System;
  if ( *(_DWORD *)(a1 + 20) == 1 )
    rfid = FOLDERID_Windows;
  ppszPath = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &ppszPath,
    0);
  v6 = SHGetKnownFolderPath(&rfid, 0x5000u, 0, &ppszPath);
  LastError = v6;
  if ( v6 >= 0 )
  {
    v10 = -1;
    v11 = -1;
    do
      ++v11;
    while ( StringRawBuffer[v11] );
    do
      ++v10;
    while ( ppszPath[v10] );
    v12 = v11 + v10;
    wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
      &v24,
      (char *)ppszPath,
      v11 + v10 + 2,
      v7);
    wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
      &pszPath,
      &v24);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
    v13 = StringRawBuffer;
    StringRawBuffer = pszPath;
    v6 = PathCchAppend(pszPath, v12 + 2, v13);
    LastError = v6;
    if ( v6 < 0 )
    {
      v9 = 536;
      goto LABEL_11;
    }
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&ppszPath);
LABEL_13:
    v25 = 0;
    if ( (*(_BYTE *)(a1 + 16) & 1) != 0 )
    {
      pcchFileMUIPath = 0;
      pululEnumerator = 0;
      if ( !GetFileMUIPath(0x408u, StringRawBuffer, 0, 0, 0, &pcchFileMUIPath, &pululEnumerator) )
      {
        v16 = 555;
LABEL_16:
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)v16,
                      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
                      v15);
LABEL_17:
        p_ppszPath = &v25;
        goto LABEL_18;
      }
      if ( !pcchFileMUIPath )
      {
        LastError = -2147418113;
        v17 = 556;
LABEL_21:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
          (const char *)LastError,
          pwszFileMUIPatha);
        goto LABEL_17;
      }
      wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
        &v24,
        0,
        pcchFileMUIPath,
        v15);
      wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>::operator=(
        &v25,
        &v24);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
      v18 = v25;
      if ( !v25 )
      {
        LastError = -2147024882;
        v17 = 558;
        goto LABEL_21;
      }
      if ( !GetFileMUIPath(0x408u, StringRawBuffer, 0, 0, v25, &pcchFileMUIPath, &pululEnumerator) )
      {
        v16 = 559;
        goto LABEL_16;
      }
    }
    else
    {
      v18 = (PWSTR)StringRawBuffer;
    }
    v24 = 0;
    HtmlFileWideCharContent = GetHtmlFileWideCharContent(v4, v18, &v24);
    LastError = HtmlFileWideCharContent;
    if ( HtmlFileWideCharContent >= 0 )
    {
      Reserved1 = v24;
      Reserved1 = (HSTRING)Microsoft::WRL::Wrappers::HStringReference::HStringReference(
                             &v32,
                             (const WCHAR **)&Reserved1,
                             v20)[1].Reserved.Reserved1;
      Microsoft::WRL::Wrappers::HString::Set((HSTRING *)(a2 + 16), &Reserved1);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v25);
      LastError = 0;
      goto LABEL_30;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x23D,
      (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
      (const char *)(unsigned int)HtmlFileWideCharContent,
      pwszFileMUIPath);
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v24);
    goto LABEL_17;
  }
  v9 = 533;
LABEL_11:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"onecoreuap\\shell\\cloudexperiencehost\\onecore\\winrtapi\\utilstaticscore.cpp",
    (const char *)(unsigned int)v6,
    pwszFileMUIPath);
  p_ppszPath = &ppszPath;
LABEL_18:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(p_ppszPath);
LABEL_30:
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&pszPath);
  return LastError;
}

```

## disassembly

```asm
0x18009f404  mov     [rsp-8+arg_10], rbx
0x18009f409  push    rbp
0x18009f40a  push    rsi
0x18009f40b  push    rdi
0x18009f40c  push    r14
0x18009f40e  push    r15
0x18009f410  lea     rbp, [rsp-37h]
0x18009f415  sub     rsp, 0B0h
0x18009f41c  mov     rax, cs:__security_cookie
0x18009f423  xor     rax, rsp
0x18009f426  mov     [rbp+57h+var_28], rax
0x18009f42a  mov     r14, rdx
0x18009f42d  mov     rsi, rcx
0x18009f430  xor     edx, edx; length
0x18009f432  mov     rcx, [rcx]; string
0x18009f435  call    cs:__imp_WindowsGetStringRawBuffer
0x18009f43b  mov     rdi, rax
0x18009f43e  xor     r15d, r15d
0x18009f441  mov     [rbp+57h+pszPath], r15
0x18009f445  cmp     [rsi+14h], r15d
0x18009f449  jz      loc_18009F526
0x18009f44f  movups  xmm0, xmmword ptr cs:FOLDERID_System.Data1
0x18009f456  movdqu  xmmword ptr [rbp+57h+rfid.Data1], xmm0
0x18009f45b  cmp     dword ptr [rsi+14h], 1
0x18009f45f  jnz     short loc_18009F46D
0x18009f461  movups  xmm0, xmmword ptr cs:FOLDERID_Windows.Data1
0x18009f468  movdqu  xmmword ptr [rbp+57h+rfid.Data1], xmm0
0x18009f46d  mov     [rbp+57h+ppszPath], r15
0x18009f471  xor     edx, edx
0x18009f473  lea     rcx, [rbp+57h+ppszPath]
0x18009f477  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18009f47c  lea     r9, [rbp+57h+ppszPath]; ppszPath
0x18009f480  xor     r8d, r8d; hToken
0x18009f483  mov     edx, 5000h; dwFlags
0x18009f488  lea     rcx, [rbp+57h+rfid]; rfid
0x18009f48c  call    cs:__imp_SHGetKnownFolderPath
0x18009f492  mov     ebx, eax
0x18009f494  test    eax, eax
0x18009f496  jns     short loc_18009F49F
0x18009f498  mov     edx, 215h
0x18009f49d  jmp     short loc_18009F504
0x18009f49f  or      rax, 0FFFFFFFFFFFFFFFFh
0x18009f4a3  mov     rcx, rax
0x18009f4a6  inc     rcx
0x18009f4a9  cmp     [rdi+rcx*2], r15w
0x18009f4ae  jnz     short loc_18009F4A6
0x18009f4b0  mov     rdx, [rbp+57h+ppszPath]
0x18009f4b4  inc     rax
0x18009f4b7  cmp     [rdx+rax*2], r15w
0x18009f4bc  jnz     short loc_18009F4B4
0x18009f4be  lea     rbx, [rcx+rax]
0x18009f4c2  lea     r8, [rbx+2]
0x18009f4c6  lea     rcx, [rbp+57h+var_90]
0x18009f4ca  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18009f4cf  lea     rdx, [rbp+57h+var_90]
0x18009f4d3  lea     rcx, [rbp+57h+pszPath]
0x18009f4d7  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18009f4dc  lea     rcx, [rbp+57h+var_90]
0x18009f4e0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f4e5  mov     r8, rdi; pszMore
0x18009f4e8  lea     rdx, [rbx+2]; cchPath
0x18009f4ec  mov     rdi, [rbp+57h+pszPath]
0x18009f4f0  mov     rcx, rdi; pszPath
0x18009f4f3  call    cs:__imp_PathCchAppend
0x18009f4f9  mov     ebx, eax
0x18009f4fb  test    eax, eax
0x18009f4fd  jns     short loc_18009F51D
0x18009f4ff  mov     edx, 218h; void *
0x18009f504  mov     r9d, eax; char *
0x18009f507  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x18009f50e  mov     rcx, [rbp+5Fh]; this
0x18009f512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f517  lea     rcx, [rbp+57h+ppszPath]
0x18009f51b  jmp     short loc_18009F588
0x18009f51d  lea     rcx, [rbp+57h+ppszPath]
0x18009f521  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f526  mov     [rbp+57h+var_88], r15
0x18009f52a  test    byte ptr [rsi+10h], 1
0x18009f52e  jz      loc_18009F627
0x18009f534  mov     [rbp+57h+var_80], r15d
0x18009f538  mov     [rbp+57h+var_60], r15
0x18009f53c  lea     rax, [rbp+57h+var_60]
0x18009f540  mov     [rsp+0D0h+pululEnumerator], rax; pululEnumerator
0x18009f545  lea     rax, [rbp+57h+var_80]
0x18009f549  mov     [rsp+0D0h+pcchFileMUIPath], rax; pcchFileMUIPath
0x18009f54e  mov     [rsp+0D0h+pwszFileMUIPath], r15; int
0x18009f553  xor     r9d, r9d; pcchLanguage
0x18009f556  xor     r8d, r8d; pwszLanguage
0x18009f559  mov     rdx, rdi; pcwszFilePath
0x18009f55c  mov     esi, 408h
0x18009f561  mov     ecx, esi; dwFlags
0x18009f563  call    cs:__imp_GetFileMUIPath
0x18009f569  test    eax, eax
0x18009f56b  jnz     short loc_18009F592
0x18009f56d  mov     edx, 22Bh; void *
0x18009f572  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x18009f579  mov     rcx, [rbp+5Fh]; this
0x18009f57d  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18009f582  mov     ebx, eax
0x18009f584  lea     rcx, [rbp+57h+var_88]
0x18009f588  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f58d  jmp     loc_18009F6A8
0x18009f592  mov     eax, [rbp+57h+var_80]
0x18009f595  test    eax, eax
0x18009f597  jnz     short loc_18009F5B8
0x18009f599  mov     ebx, 8000FFFFh
0x18009f59e  mov     edx, 22Ch; void *
0x18009f5a3  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x18009f5aa  mov     r9d, ebx; char *
0x18009f5ad  mov     rcx, [rbp+5Fh]; this
0x18009f5b1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f5b6  jmp     short loc_18009F584
0x18009f5b8  mov     r8, rax
0x18009f5bb  xor     edx, edx
0x18009f5bd  lea     rcx, [rbp+57h+var_90]
0x18009f5c1  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x18009f5c6  lea     rdx, [rbp+57h+var_90]
0x18009f5ca  lea     rcx, [rbp+57h+var_88]
0x18009f5ce  call    ??4?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@QEAAAEAV01@$$QEAV01@@Z; wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>::operator=(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &&)
0x18009f5d3  lea     rcx, [rbp+57h+var_90]
0x18009f5d7  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f5dc  mov     rbx, [rbp+57h+var_88]
0x18009f5e0  test    rbx, rbx
0x18009f5e3  jnz     short loc_18009F5F1
0x18009f5e5  mov     ebx, 8007000Eh
0x18009f5ea  mov     edx, 22Eh
0x18009f5ef  jmp     short loc_18009F5A3
0x18009f5f1  lea     rax, [rbp+57h+var_60]
0x18009f5f5  mov     [rsp+0D0h+pululEnumerator], rax; pululEnumerator
0x18009f5fa  lea     rax, [rbp+57h+var_80]
0x18009f5fe  mov     [rsp+0D0h+pcchFileMUIPath], rax; pcchFileMUIPath
0x18009f603  mov     [rsp+0D0h+pwszFileMUIPath], rbx; pwszFileMUIPath
0x18009f608  xor     r9d, r9d; pcchLanguage
0x18009f60b  xor     r8d, r8d; pwszLanguage
0x18009f60e  mov     rdx, rdi; pcwszFilePath
0x18009f611  mov     ecx, esi; dwFlags
0x18009f613  call    cs:__imp_GetFileMUIPath
0x18009f619  test    eax, eax
0x18009f61b  jnz     short loc_18009F62A
0x18009f61d  mov     edx, 22Fh
0x18009f622  jmp     loc_18009F572
0x18009f627  mov     rbx, rdi
0x18009f62a  mov     [rbp+57h+var_90], r15
0x18009f62e  lea     r8, [rbp+57h+var_90]
0x18009f632  mov     rdx, rbx
0x18009f635  call    ?GetHtmlFileWideCharContent@@YAJIPEBGAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; GetHtmlFileWideCharContent(uint,ushort const *,wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &)
0x18009f63a  mov     ebx, eax
0x18009f63c  test    eax, eax
0x18009f63e  jns     short loc_18009F667
0x18009f640  mov     rcx, [rbp+5Fh]; this
0x18009f644  mov     r9d, eax; char *
0x18009f647  lea     r8, aOnecoreuapShel_9; "onecoreuap\\shell\\cloudexperiencehost"...
0x18009f64e  mov     edx, 23Dh; void *
0x18009f653  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18009f658  nop
0x18009f659  lea     rcx, [rbp+57h+var_90]
0x18009f65d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f662  jmp     loc_18009F584
0x18009f667  mov     rax, [rbp+57h+var_90]
0x18009f66b  mov     [rbp+57h+var_68], rax
0x18009f66f  lea     rdx, [rbp+57h+var_68]
0x18009f673  lea     rcx, [rbp+57h+var_48]
0x18009f677  call    ??$?0PEBG@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBQEBGUDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(ushort const * const &,Microsoft::WRL::Details::Dummy)
0x18009f67c  mov     rcx, [rax+18h]
0x18009f680  mov     [rbp+57h+var_68], rcx
0x18009f684  lea     rcx, [r14+10h]; newString
0x18009f688  lea     rdx, [rbp+57h+var_68]; HSTRING *
0x18009f68c  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18009f691  nop
0x18009f692  lea     rcx, [rbp+57h+var_90]
0x18009f696  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f69b  nop
0x18009f69c  lea     rcx, [rbp+57h+var_88]
0x18009f6a0  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f6a5  mov     ebx, r15d
0x18009f6a8  lea     rcx, [rbp+57h+pszPath]
0x18009f6ac  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18009f6b1  mov     eax, ebx
0x18009f6b3  mov     rcx, [rbp+57h+var_28]
0x18009f6b7  xor     rcx, rsp; StackCookie
0x18009f6ba  call    __security_check_cookie
0x18009f6bf  mov     rbx, [rsp+0D0h+arg_10]
0x18009f6c7  add     rsp, 0B0h
0x18009f6ce  pop     r15
0x18009f6d0  pop     r14
0x18009f6d2  pop     rdi
0x18009f6d3  pop     rsi
0x18009f6d4  pop     rbp
0x18009f6d5  retn
```
