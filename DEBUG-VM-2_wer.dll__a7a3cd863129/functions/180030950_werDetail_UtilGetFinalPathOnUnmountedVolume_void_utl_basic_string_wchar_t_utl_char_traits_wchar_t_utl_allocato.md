# _werDetail::UtilGetFinalPathOnUnmountedVolume(void *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &)

- ea: `0x180030950`
- end: `0x180030e36`
- name: `?UtilGetFinalPathOnUnmountedVolume@_werDetail@@YAJPEAXAEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@@Z`
- size: `1254`
- prototype: ``
- caller_count: `1`
- callee_count: `17`
- tags: `file_ops, reparse_path, broker_com_uri`

## callers

- `0x1800306e4`

## callees

- `0x18000716c`
- `0x180007e10`
- `0x180007e34`
- `0x180008174`
- `0x18000c390`
- `0x18000dad0`
- `0x18000ea64`
- `0x180013a20`
- `0x180019808`
- `0x180023dc4`
- `0x180023e8c`
- `0x180027480`
- `0x1800303dc`
- `0x180030950`
- `0x18004ac4c`
- `0x180050db0`
- `0x18005ff78`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030c13`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x180030c13`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030da7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030d6b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180030da7`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800309c5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180030bbe`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x1800309c5`
- `api-ms-win-core-file-l1-1-0!GetFinalPathNameByHandleW` at `0x180030bbe`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030b28`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x180030b28`

## string_xrefs

- `0x180030a84`: `StorePath`

## pseudocode

```c
__int64 __fastcall _werDetail::UtilGetFinalPathOnUnmountedVolume(void *a1, __int64 a2)
{
  DWORD FinalPathNameByHandleW; // eax
  int v4; // ecx
  int v5; // r8d
  int v6; // r9d
  int String; // ebx
  int v8; // ecx
  int v9; // r8d
  int v10; // r9d
  char *v11; // rdx
  HANDLE FileW; // rax
  DWORD v13; // eax
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int16 *v17; // rdx
  DWORD v18; // eax
  unsigned __int64 v19; // rbx
  __int64 v20; // rdx
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  int v24; // ecx
  int v25; // r8d
  int v26; // r9d
  int v27; // ecx
  int v28; // r8d
  int v29; // r9d
  DWORD v30; // eax
  DWORD LastError; // eax
  void *v33; // [rsp+40h] [rbp-C0h] BYREF
  LPCWSTR v34; // [rsp+48h] [rbp-B8h] BYREF
  HANDLE hFile; // [rsp+50h] [rbp-B0h] BYREF
  LPCWCH lpString1; // [rsp+58h] [rbp-A8h] BYREF
  _WORD *v37; // [rsp+60h] [rbp-A0h]
  _WORD v38[8]; // [rsp+68h] [rbp-98h] BYREF
  LPCWSTR lpFileName[2]; // [rsp+78h] [rbp-88h] BYREF
  _WORD v40[12]; // [rsp+88h] [rbp-78h] BYREF
  WCHAR szFilePath[264]; // [rsp+A0h] [rbp-60h] BYREF

  lpFileName[0] = v40;
  hFile = 0;
  lpFileName[1] = v40;
  v40[0] = 0;
  lpString1 = v38;
  v38[0] = 0;
  v37 = v38;
  FinalPathNameByHandleW = GetFinalPathNameByHandleW(a1, szFilePath, 0x104u, 2u);
  if ( !FinalPathNameByHandleW )
  {
    LastError = GetLastError();
LABEL_49:
    String = ERROR_HR_FROM_WIN32(LastError);
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_54;
    v11 = byte_1800C5EDD;
LABEL_52:
    LODWORD(v33) = String;
    goto LABEL_53;
  }
  if ( FinalPathNameByHandleW >= 0x104 )
  {
    LastError = 111;
    goto LABEL_49;
  }
  if ( (unsigned int)dword_1800D8000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
  {
    v33 = szFilePath;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
      v4,
      (unsigned int)byte_1800C5F19,
      v5,
      v6,
      (__int64)&v33);
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(
                           &lpString1,
                           szFilePath) )
  {
    String = -2147024882;
    if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      LODWORD(v33) = -2147024882;
      v11 = byte_1800C5F5B;
LABEL_53:
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        v8,
        (_DWORD)v11,
        v9,
        v10,
        (__int64)&v33);
      goto LABEL_54;
    }
    goto LABEL_54;
  }
  String = UtilRegGetString(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows\\Windows Error Reporting",
             L"StorePath",
             (__int64)lpFileName,
             0,
             1);
  if ( String < 0 )
  {
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_54;
    v11 = &byte_1800C5F97;
    goto LABEL_52;
  }
  if ( !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(lpFileName)
    && !(unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(
                           lpFileName,
                           92) )
  {
    String = -2147024882;
    goto LABEL_54;
  }
  FileW = CreateFileW(lpFileName[0], 0x80u, 1u, 0, 3u, 0x2000080u, 0);
  tlx::unique_any<tlx::file_handle_traits>::reset(&hFile, FileW);
  if ( (unsigned __int64)hFile + 1 <= 1 )
  {
    v13 = GetLastError();
    String = ERROR_HR_FROM_WIN32(v13);
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_54;
    v17 = word_1800C5FDA;
    goto LABEL_21;
  }
  v18 = GetFinalPathNameByHandleW(hFile, szFilePath, 0x104u, 2u);
  if ( !v18 )
  {
    v30 = GetLastError();
LABEL_44:
    String = ERROR_HR_FROM_WIN32(v30);
    if ( (unsigned int)dword_1800D8000 <= 2 || !(unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      goto LABEL_54;
    v17 = (__int16 *)byte_1800C6029;
LABEL_21:
    v34 = lpFileName[0];
    LODWORD(v33) = String;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(
      v14,
      (_DWORD)v17,
      v15,
      v16,
      (__int64)&v34,
      (__int64)&v33);
    goto LABEL_54;
  }
  if ( v18 >= 0x104 )
  {
    v30 = 111;
    goto LABEL_44;
  }
  v19 = -1;
  do
    ++v19;
  while ( szFilePath[v19] );
  if ( v37 - lpString1 >= v19 && CompareStringOrdinal(lpString1, v19, szFilePath, v19, 1) == 2 )
  {
    if ( (unsigned int)dword_1800D8000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      v34 = lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
        v21,
        (unsigned int)&unk_1800C6078,
        v22,
        v23,
        (__int64)&v34);
    }
    if ( (unsigned __int8)utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(
                            &lpString1,
                            v20,
                            v19) )
    {
      if ( (unsigned int)dword_1800D8000 > 4 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        v34 = lpString1;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(
          v24,
          (unsigned int)&dword_1800C60FC,
          v25,
          v26,
          (__int64)&v34);
      }
      utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(a2, &lpString1);
      String = 0;
    }
    else
    {
      String = -2147024882;
      if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
      {
        LODWORD(v33) = -2147024882;
        v11 = (char *)&word_1800C60BE;
        goto LABEL_53;
      }
    }
  }
  else
  {
    String = -2147024735;
    if ( (unsigned int)dword_1800D8000 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800D8000, 8) )
    {
      v34 = szFilePath;
      v33 = (void *)lpString1;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(
        v27,
        (unsigned int)byte_1800C6141,
        v28,
        v29,
        (__int64)&v33,
        (__int64)&v34);
    }
  }
LABEL_54:
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(&lpString1);
  utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(lpFileName);
  tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(&hFile);
  return (unsigned int)String;
}

```

## disassembly

```asm
0x180030950  mov     [rsp-8+arg_10], rbx
0x180030955  push    rbp
0x180030956  push    rsi
0x180030957  push    rdi
0x180030958  push    r14
0x18003095a  push    r15
0x18003095c  lea     rbp, [rsp-1C0h]
0x180030964  sub     rsp, 2C0h
0x18003096b  mov     rax, cs:__security_cookie
0x180030972  xor     rax, rsp
0x180030975  mov     [rbp+1E0h+var_30], rax
0x18003097c  xor     r15d, r15d
0x18003097f  lea     rax, [rbp+1E0h+var_258]
0x180030983  mov     [rsp+2E0h+lpFileName], rax
0x180030988  mov     r14, rdx
0x18003098b  lea     rax, [rbp+1E0h+var_258]
0x18003098f  mov     [rsp+2E0h+hFile], r15
0x180030994  mov     [rbp+1E0h+var_260], rax
0x180030998  lea     rdx, [rbp+1E0h+szFilePath]; lpszFilePath
0x18003099c  lea     rax, [rsp+2E0h+var_278]
0x1800309a1  mov     [rbp+1E0h+var_258], r15w
0x1800309a6  mov     [rsp+2E0h+lpString1], rax
0x1800309ab  lea     r9d, [r15+2]; dwFlags
0x1800309af  lea     rax, [rsp+2E0h+var_278]
0x1800309b4  mov     [rsp+2E0h+var_278], r15w
0x1800309ba  mov     r8d, 104h; cchFilePath
0x1800309c0  mov     [rsp+2E0h+var_280], rax
0x1800309c5  call    cs:__imp_GetFinalPathNameByHandleW
0x1800309cb  test    eax, eax
0x1800309cd  jz      loc_180030DA7
0x1800309d3  cmp     eax, 104h
0x1800309d8  jnb     loc_180030DA0
0x1800309de  mov     eax, cs:dword_1800D8000
0x1800309e4  lea     edi, [r15+8]
0x1800309e8  lea     rsi, dword_1800D8000
0x1800309ef  cmp     eax, 4
0x1800309f2  jbe     short loc_180030A21
0x1800309f4  mov     edx, edi
0x1800309f6  mov     rcx, rsi
0x1800309f9  call    _tlgKeywordOn
0x1800309fe  test    al, al
0x180030a00  jz      short loc_180030A21
0x180030a02  lea     rax, [rbp+1E0h+szFilePath]
0x180030a06  mov     [rsp+2E0h+var_2A0], rax
0x180030a0b  lea     rdx, byte_1800C5F19
0x180030a12  lea     rax, [rsp+2E0h+var_2A0]
0x180030a17  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180030a1c  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180030a21  lea     rdx, [rbp+1E0h+szFilePath]
0x180030a25  lea     rcx, [rsp+2E0h+lpString1]
0x180030a2a  call    ?assign@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_NPEB_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::assign(wchar_t const *)
0x180030a2f  test    al, al
0x180030a31  jnz     short loc_180030A6E
0x180030a33  mov     eax, cs:dword_1800D8000
0x180030a39  mov     ebx, 8007000Eh
0x180030a3e  cmp     eax, 2
0x180030a41  jbe     loc_180030DF0
0x180030a47  mov     rdx, rdi
0x180030a4a  mov     rcx, rsi
0x180030a4d  call    _tlgKeywordOn
0x180030a52  test    al, al
0x180030a54  jz      loc_180030DF0
0x180030a5a  mov     dword ptr [rsp+2E0h+var_2A0], 8007000Eh
0x180030a62  lea     rdx, byte_1800C5F5B
0x180030a69  jmp     loc_180030DE1
0x180030a6e  mov     byte ptr [rsp+2E0h+hTemplateFile], 1; char
0x180030a73  lea     rax, [rsp+2E0h+lpFileName]
0x180030a78  mov     byte ptr [rsp+2E0h+dwFlagsAndAttributes], r15b; char
0x180030a7d  lea     r9, Src
0x180030a84  lea     r8, aStorepath; "StorePath"
0x180030a8b  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax; __int64
0x180030a90  lea     rdx, aSoftwareMicros_24; "Software\\Microsoft\\Windows\\Windows E"...
0x180030a97  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180030a9e  call    ?UtilRegGetString@@YAJPEAUHKEY__@@PEB_W11PEAV?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@_N3@Z; UtilRegGetString(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t const *,utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> *,bool,bool)
0x180030aa3  mov     ebx, eax
0x180030aa5  test    eax, eax
0x180030aa7  jns     short loc_180030AD7
0x180030aa9  mov     ecx, cs:dword_1800D8000
0x180030aaf  cmp     ecx, 2
0x180030ab2  jbe     loc_180030DF0
0x180030ab8  mov     rdx, rdi
0x180030abb  mov     rcx, rsi
0x180030abe  call    _tlgKeywordOn
0x180030ac3  test    al, al
0x180030ac5  jz      loc_180030DF0
0x180030acb  lea     rdx, byte_1800C5F97
0x180030ad2  jmp     loc_180030DDD
0x180030ad7  lea     rcx, [rsp+2E0h+lpFileName]
0x180030adc  call    ?ends_with@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEBA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::ends_with(wchar_t)
0x180030ae1  test    al, al
0x180030ae3  jnz     short loc_180030B02
0x180030ae5  mov     edx, 5Ch ; '\'
0x180030aea  lea     rcx, [rsp+2E0h+lpFileName]
0x180030aef  call    ?push_back@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_W@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::push_back(wchar_t)
0x180030af4  test    al, al
0x180030af6  jnz     short loc_180030B02
0x180030af8  mov     ebx, 8007000Eh
0x180030afd  jmp     loc_180030DF0
0x180030b02  mov     rcx, [rsp+2E0h+lpFileName]; lpFileName
0x180030b07  xor     r9d, r9d; lpSecurityAttributes
0x180030b0a  mov     [rsp+2E0h+hTemplateFile], r15; hTemplateFile
0x180030b0f  mov     edx, 80h; dwDesiredAccess
0x180030b14  mov     [rsp+2E0h+dwFlagsAndAttributes], 2000080h; dwFlagsAndAttributes
0x180030b1c  mov     [rsp+2E0h+dwCreationDisposition], 3; dwCreationDisposition
0x180030b24  lea     r8d, [r9+1]; dwShareMode
0x180030b28  call    cs:__imp_CreateFileW
0x180030b2e  mov     rdx, rax
0x180030b31  lea     rcx, [rsp+2E0h+hFile]
0x180030b36  call    ?reset@?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAAXPEAX@Z; tlx::unique_any<tlx::file_handle_traits>::reset(void *)
0x180030b3b  mov     rcx, [rsp+2E0h+hFile]; hFile
0x180030b40  lea     rax, [rcx+1]
0x180030b44  cmp     rax, 1
0x180030b48  ja      short loc_180030BAE
0x180030b4a  call    cs:__imp_GetLastError
0x180030b50  mov     ecx, eax; unsigned int
0x180030b52  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180030b57  mov     ebx, eax
0x180030b59  mov     eax, cs:dword_1800D8000
0x180030b5f  cmp     eax, 2
0x180030b62  jbe     loc_180030DF0
0x180030b68  mov     rdx, rdi
0x180030b6b  mov     rcx, rsi
0x180030b6e  call    _tlgKeywordOn
0x180030b73  test    al, al
0x180030b75  jz      loc_180030DF0
0x180030b7b  lea     rdx, word_1800C5FDA
0x180030b82  mov     rax, [rsp+2E0h+lpFileName]
0x180030b87  mov     [rsp+2E0h+var_298], rax
0x180030b8c  lea     rax, [rsp+2E0h+var_2A0]
0x180030b91  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax
0x180030b96  lea     rax, [rsp+2E0h+var_298]
0x180030b9b  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180030ba0  mov     dword ptr [rsp+2E0h+var_2A0], ebx
0x180030ba4  call    ??$Write@U?$_tlgWrapSz@_W@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapperByVal<4> const &)
0x180030ba9  jmp     loc_180030DF0
0x180030bae  mov     r9d, 2; dwFlags
0x180030bb4  lea     rdx, [rbp+1E0h+szFilePath]; lpszFilePath
0x180030bb8  mov     r8d, 104h; cchFilePath
0x180030bbe  call    cs:__imp_GetFinalPathNameByHandleW
0x180030bc4  test    eax, eax
0x180030bc6  jz      loc_180030D6B
0x180030bcc  cmp     eax, 104h
0x180030bd1  jnb     loc_180030D64
0x180030bd7  lea     rax, [rbp+1E0h+szFilePath]
0x180030bdb  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180030bdf  inc     rbx
0x180030be2  cmp     [rax+rbx*2], r15w
0x180030be7  jnz     short loc_180030BDF
0x180030be9  mov     rax, [rsp+2E0h+var_280]
0x180030bee  mov     rcx, [rsp+2E0h+lpString1]; lpString1
0x180030bf3  sub     rax, rcx
0x180030bf6  sar     rax, 1
0x180030bf9  cmp     rax, rbx
0x180030bfc  jb      loc_180030D05
0x180030c02  mov     r9d, ebx; cchCount2
0x180030c05  mov     [rsp+2E0h+dwCreationDisposition], 1; bIgnoreCase
0x180030c0d  lea     r8, [rbp+1E0h+szFilePath]; lpString2
0x180030c11  mov     edx, ebx; cchCount1
0x180030c13  call    cs:__imp_CompareStringOrdinal
0x180030c19  cmp     eax, 2
0x180030c1c  jnz     loc_180030D05
0x180030c22  mov     eax, cs:dword_1800D8000
0x180030c28  cmp     eax, 4
0x180030c2b  jbe     short loc_180030C5C
0x180030c2d  mov     rdx, rdi
0x180030c30  mov     rcx, rsi
0x180030c33  call    _tlgKeywordOn
0x180030c38  test    al, al
0x180030c3a  jz      short loc_180030C5C
0x180030c3c  mov     rax, [rsp+2E0h+lpString1]
0x180030c41  lea     rdx, unk_1800C6078
0x180030c48  mov     [rsp+2E0h+var_298], rax
0x180030c4d  lea     rax, [rsp+2E0h+var_298]
0x180030c52  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180030c57  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180030c5c  mov     rax, [rbp+1E0h+var_260]
0x180030c60  lea     rcx, [rsp+2E0h+lpString1]
0x180030c65  mov     r9, [rsp+2E0h+lpFileName]
0x180030c6a  mov     r8, rbx
0x180030c6d  sub     rax, r9
0x180030c70  sar     rax, 1
0x180030c73  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180030c78  call    ?replace@?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAA_N_K0PEB_W0@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::replace(unsigned __int64,unsigned __int64,wchar_t const *,unsigned __int64)
0x180030c7d  test    al, al
0x180030c7f  mov     eax, cs:dword_1800D8000
0x180030c85  jnz     short loc_180030CBC
0x180030c87  mov     ebx, 8007000Eh
0x180030c8c  cmp     eax, 2
0x180030c8f  jbe     loc_180030DF0
0x180030c95  mov     rdx, rdi
0x180030c98  mov     rcx, rsi
0x180030c9b  call    _tlgKeywordOn
0x180030ca0  test    al, al
0x180030ca2  jz      loc_180030DF0
0x180030ca8  mov     dword ptr [rsp+2E0h+var_2A0], 8007000Eh
0x180030cb0  lea     rdx, word_1800C60BE
0x180030cb7  jmp     loc_180030DE1
0x180030cbc  cmp     eax, 4
0x180030cbf  jbe     short loc_180030CF0
0x180030cc1  mov     rdx, rdi
0x180030cc4  mov     rcx, rsi
0x180030cc7  call    _tlgKeywordOn
0x180030ccc  test    al, al
0x180030cce  jz      short loc_180030CF0
0x180030cd0  mov     rax, [rsp+2E0h+lpString1]
0x180030cd5  lea     rdx, dword_1800C60FC
0x180030cdc  mov     [rsp+2E0h+var_298], rax
0x180030ce1  lea     rax, [rsp+2E0h+var_298]
0x180030ce6  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180030ceb  call    ??$Write@U?$_tlgWrapSz@_W@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &)
0x180030cf0  lea     rdx, [rsp+2E0h+lpString1]
0x180030cf5  mov     rcx, r14
0x180030cf8  call    ??4?$basic_string@_WU?$char_traits@_W@utl@@V?$allocator@_W@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>>::operator=(utl::basic_string<wchar_t,utl::char_traits<wchar_t>,utl::allocator<wchar_t>> &&)
0x180030cfd  mov     ebx, r15d
0x180030d00  jmp     loc_180030DF0
0x180030d05  mov     eax, cs:dword_1800D8000
0x180030d0b  mov     ebx, 800700A1h
0x180030d10  cmp     eax, 2
0x180030d13  jbe     loc_180030DF0
0x180030d19  mov     rdx, rdi
0x180030d1c  mov     rcx, rsi
0x180030d1f  call    _tlgKeywordOn
0x180030d24  test    al, al
0x180030d26  jz      loc_180030DF0
0x180030d2c  lea     rax, [rbp+1E0h+szFilePath]
0x180030d30  mov     [rsp+2E0h+var_298], rax
0x180030d35  lea     rdx, byte_1800C6141
0x180030d3c  mov     rax, [rsp+2E0h+lpString1]
0x180030d41  mov     [rsp+2E0h+var_2A0], rax
0x180030d46  lea     rax, [rsp+2E0h+var_298]
0x180030d4b  mov     qword ptr [rsp+2E0h+dwFlagsAndAttributes], rax
0x180030d50  lea     rax, [rsp+2E0h+var_2A0]
0x180030d55  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180030d5a  call    ??$Write@U?$_tlgWrapSz@_W@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@_W@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<wchar_t>,_tlgWrapSz<wchar_t>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<wchar_t> const &,_tlgWrapSz<wchar_t> const &)
0x180030d5f  jmp     loc_180030DF0
0x180030d64  mov     eax, 6Fh ; 'o'
0x180030d69  jmp     short loc_180030D71
0x180030d6b  call    cs:__imp_GetLastError
0x180030d71  mov     ecx, eax; unsigned int
0x180030d73  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180030d78  mov     ebx, eax
0x180030d7a  mov     eax, cs:dword_1800D8000
0x180030d80  cmp     eax, 2
0x180030d83  jbe     short loc_180030DF0
0x180030d85  mov     rdx, rdi
0x180030d88  mov     rcx, rsi
0x180030d8b  call    _tlgKeywordOn
0x180030d90  test    al, al
0x180030d92  jz      short loc_180030DF0
0x180030d94  lea     rdx, byte_1800C6029
0x180030d9b  jmp     loc_180030B82
0x180030da0  mov     eax, 6Fh ; 'o'
0x180030da5  jmp     short loc_180030DAD
0x180030da7  call    cs:__imp_GetLastError
0x180030dad  mov     ecx, eax; unsigned int
0x180030daf  call    ?ERROR_HR_FROM_WIN32@@YAJK@Z; ERROR_HR_FROM_WIN32(ulong)
0x180030db4  mov     ebx, eax
0x180030db6  mov     eax, cs:dword_1800D8000
0x180030dbc  cmp     eax, 2
0x180030dbf  jbe     short loc_180030DF0
0x180030dc1  mov     edx, 8
0x180030dc6  lea     rcx, dword_1800D8000
0x180030dcd  call    _tlgKeywordOn
0x180030dd2  test    al, al
0x180030dd4  jz      short loc_180030DF0
0x180030dd6  lea     rdx, byte_1800C5EDD
0x180030ddd  mov     dword ptr [rsp+2E0h+var_2A0], ebx
0x180030de1  lea     rax, [rsp+2E0h+var_2A0]
0x180030de6  mov     qword ptr [rsp+2E0h+dwCreationDisposition], rax
0x180030deb  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x180030df0  lea     rcx, [rsp+2E0h+lpString1]; void *
0x180030df5  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180030dfa  lea     rcx, [rsp+2E0h+lpFileName]; void *
0x180030dff  call    ?_Uninit@?$basic_string@DU?$char_traits@D@utl@@V?$allocator@D@2@@utl@@AEAAXXZ; utl::basic_string<char,utl::char_traits<char>,utl::allocator<char>>::_Uninit(void)
0x180030e04  lea     rcx, [rsp+2E0h+hFile]
0x180030e09  call    ??1?$unique_any@Ufile_handle_traits@tlx@@@tlx@@QEAA@XZ; tlx::unique_any<tlx::file_handle_traits>::~unique_any<tlx::file_handle_traits>(void)
0x180030e0e  mov     eax, ebx
0x180030e10  mov     rcx, [rbp+1E0h+var_30]
0x180030e17  xor     rcx, rsp; StackCookie
0x180030e1a  call    __security_check_cookie
0x180030e1f  mov     rbx, [rsp+2E0h+arg_10]
0x180030e27  add     rsp, 2C0h
0x180030e2e  pop     r15
0x180030e30  pop     r14
0x180030e32  pop     rdi
0x180030e33  pop     rsi
0x180030e34  pop     rbp
0x180030e35  retn
```
