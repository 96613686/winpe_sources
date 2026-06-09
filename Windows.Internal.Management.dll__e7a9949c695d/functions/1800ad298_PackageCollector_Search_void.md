# PackageCollector::Search(void)

- ea: `0x1800ad298`
- end: `0x1800ad965`
- name: `?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ`
- size: `1741`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180071b50`
- `0x180071ea0`

## callees

- `0x1800011d4`
- `0x18000133c`
- `0x180001408`
- `0x180001a60`
- `0x180002bdc`
- `0x18000377c`
- `0x180004460`
- `0x180004d50`
- `0x18000523c`
- `0x180005904`
- `0x1800084e0`
- `0x18000cfdc`
- `0x180012ae8`
- `0x180016934`
- `0x180037a84`
- `0x18003a430`
- `0x18003a6e4`
- `0x18003b004`
- `0x18003ec00`
- `0x180044d84`
- `0x18008e258`
- `0x18009caa0`
- `0x1800acb38`
- `0x1800ad298`
- `0x1800ae954`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ad3a5`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800ad3a5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4ba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800ad4ba`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ad312`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ad32e`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ad312`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800ad32e`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800ad633`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800ad633`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800ad4a7`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800ad4a7`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800ad384`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800ad384`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800ad47d`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800ad5b8`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800ad47d`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800ad5b8`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800ad349`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800ad349`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall PackageCollector::Search(__int64 a1, _QWORD *a2)
{
  __int64 v3; // r14
  __int64 v4; // r12
  const WCHAR *v5; // rcx
  const char *v6; // r9
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  LPWSTR FileNameW; // rsi
  const WCHAR *v10; // rcx
  HRESULT Extension; // eax
  void *v12; // rdi
  __int64 v13; // rbx
  __int64 v14; // rax
  const WCHAR *v15; // r9
  const WCHAR *v16; // r8
  HRESULT v17; // ebx
  int v18; // ecx
  PWSTR *FirstFileW; // rbx
  __int64 v20; // r8
  int v21; // r9d
  DWORD LastError; // eax
  __int64 v23; // rdx
  int v24; // ecx
  const char *v25; // r9
  int v26; // eax
  const WCHAR *v27; // r8
  HRESULT v28; // edi
  void *v29; // rsi
  __int64 v30; // rdi
  __int64 v31; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  int v35; // r8d
  int v36; // r9d
  unsigned int v37; // eax
  __int64 v38; // rax
  __int64 v39; // rax
  int v40; // ecx
  int v41; // r8d
  int v42; // r9d
  __int64 v43; // rax
  __int64 v44; // rax
  __int64 v45; // r8
  int v46; // r9d
  unsigned int v47; // eax
  int v48; // r8d
  __int64 v49; // rax
  __int64 v50; // rax
  int v51; // r8d
  int v52; // r9d
  __int64 v53; // rax
  __int64 v54; // rax
  __int64 v55; // r8
  int v56; // r9d
  unsigned int v57; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  unsigned __int64 cFileName; // [rsp+40h] [rbp-C0h] BYREF
  int v60[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v61; // [rsp+50h] [rbp-B0h] BYREF
  int v62; // [rsp+58h] [rbp-A8h]
  PWSTR pszPathOut[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v64; // [rsp+70h] [rbp-90h]
  PCWSTR ppszExt; // [rsp+78h] [rbp-88h] BYREF
  PWSTR *v66; // [rsp+80h] [rbp-80h] BYREF
  void *v67; // [rsp+88h] [rbp-78h] BYREF
  PWSTR v68[2]; // [rsp+90h] [rbp-70h] BYREF
  __int64 v69; // [rsp+A0h] [rbp-60h]
  _QWORD *v70; // [rsp+B0h] [rbp-50h]
  _BYTE v71[32]; // [rsp+B8h] [rbp-48h] BYREF
  _BYTE v72[32]; // [rsp+D8h] [rbp-28h] BYREF
  PCWSTR pszMore[5]; // [rsp+F8h] [rbp-8h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+3A8h] [rbp+2A8h]

  v70 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v62 = 1;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD *)(a1 + 16);
  while ( v3 != v4 )
  {
    v5 = (const WCHAR *)v3;
    if ( *(_QWORD *)(v3 + 24) > 7u )
      v5 = *(const WCHAR **)v3;
    if ( GetFileAttributesW(v5) == -1 )
    {
      if ( (unsigned int)dword_1800FA480 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FA480, 0) )
      {
        v38 = std::wstring::c_str(v3);
        v39 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v61, v38);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v40,
          (unsigned int)&word_1800EA3FE,
          v41,
          v42,
          v39);
      }
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        v6);
    }
    v7 = (const WCHAR *)v3;
    if ( *(_QWORD *)(v3 + 24) > 7u )
      v7 = *(const WCHAR **)v3;
    if ( (GetFileAttributesW(v7) & 0x10) != 0 )
    {
      std::wstring::wstring(pszMore, L"*.ppkg");
      *(_OWORD *)pszPathOut = 0;
      v64 = 0;
      std::vector<unsigned short>::reserve(pszPathOut, (char *)pszMore[2] + *(_QWORD *)(v3 + 16) + 6);
      v15 = (const WCHAR *)pszMore;
      if ( pszMore[3] > (PCWSTR)7 )
        v15 = pszMore[0];
      v16 = (const WCHAR *)v3;
      if ( *(_QWORD *)(v3 + 24) > 7u )
        v16 = *(const WCHAR **)v3;
      v17 = PathCchCombineEx(pszPathOut[0], (signed __int64)(v64 - (unsigned __int64)pszPathOut[0]) >> 1, v16, v15, 1u);
      if ( v17 < 0 )
      {
        if ( (unsigned int)dword_1800FA480 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FA480, 0) )
        {
          LODWORD(cFileName) = v17;
          v33 = std::vector<unsigned short>::data(pszPathOut);
          v34 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v61, v33);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800FA480,
            (unsigned int)byte_1800EA323,
            v35,
            v36,
            v34,
            (__int64)&cFileName);
        }
        v37 = wil::verify_hresult<long>((unsigned int)v17);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v37,
          dwFlags);
      }
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = (PWSTR *)FindFirstFileW(pszPathOut[0], &FindFileData);
      v66 = FirstFileW;
      if ( FirstFileW == (PWSTR *)-1LL )
      {
        LastError = GetLastError();
        v20 = LastError;
        if ( LastError != 2 )
        {
          if ( (unsigned int)dword_1800FA480 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FA480, 0) )
          {
            LODWORD(cFileName) = v48;
            v49 = std::vector<unsigned short>::data(pszPathOut);
            v50 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                    &v61,
                    v49);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800FA480,
              (unsigned int)word_1800EA392,
              v51,
              v52,
              v50,
              (__int64)&cFileName);
          }
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xF9,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
            v25);
        }
        if ( (unsigned int)dword_1800FA480 > 4 )
        {
          cFileName = (unsigned __int64)pszPathOut[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v24,
            (unsigned int)&unk_1800EA360,
            LastError,
            (_DWORD)v25,
            (__int64)&cFileName);
        }
      }
      else
      {
        do
        {
          if ( (unsigned int)dword_1800FA480 > 5 )
          {
            cFileName = (unsigned __int64)FindFileData.cFileName;
            *(PWSTR *)v60 = pszPathOut[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v18,
              (unsigned int)&unk_1800EA298,
              v20,
              v21,
              (__int64)v60,
              (__int64)&cFileName);
          }
          cFileName = 0;
          v26 = StringCchLengthW(FindFileData.cFileName, 0x104u, &cFileName);
          if ( v26 < 0 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)(unsigned int)v26,
              dwFlags);
          *(_OWORD *)v68 = 0;
          v69 = 0;
          std::vector<unsigned short>::reserve(v68, *(_QWORD *)(v3 + 16) + cFileName + 6);
          if ( *(_QWORD *)(v3 + 24) <= 7u )
            v27 = (const WCHAR *)v3;
          else
            v27 = *(const WCHAR **)v3;
          v28 = PathCchCombineEx(
                  v68[0],
                  (signed __int64)(v69 - (unsigned __int64)v68[0]) >> 1,
                  v27,
                  FindFileData.cFileName,
                  1u);
          if ( v28 < 0 )
          {
            if ( (unsigned int)dword_1800FA480 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FA480, 0) )
            {
              LODWORD(cFileName) = v28;
              wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                &v61,
                FindFileData.cFileName);
              v53 = std::vector<unsigned short>::data(v68);
              v54 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                      &v67,
                      v53);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (unsigned int)&cFileName,
                (unsigned int)&dword_1800EA2D4,
                v55,
                v56,
                v54,
                v55,
                (__int64)&cFileName);
            }
            v57 = wil::verify_hresult<long>((unsigned int)v28);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x113,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)v57,
              dwFlags);
          }
          v29 = operator new(0xA8u);
          v61 = v29;
          *(_QWORD *)v60 = v71;
          v30 = std::wstring::wstring(v71, v68[0]);
          v31 = std::wstring::wstring(v72, FindFileData.cFileName);
          *(_QWORD *)v60 = ProvPackage::ProvPackage(v29, v31, v30);
          std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(a2, v60);
          std::vector<unsigned short>::_Tidy(v68);
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
      }
      wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int FindClose(void *)>>(
        &v66,
        v23,
        v20);
      std::vector<unsigned short>::_Tidy(pszPathOut);
      std::wstring::_Tidy_deallocate(pszMore);
    }
    else
    {
      v8 = (const WCHAR *)v3;
      if ( *(_QWORD *)(v3 + 24) > 7u )
        v8 = *(const WCHAR **)v3;
      FileNameW = PathFindFileNameW(v8);
      if ( !FileNameW )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xC9,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)0x80070057LL,
          dwFlags);
      ppszExt = 0;
      v10 = (const WCHAR *)v3;
      if ( *(_QWORD *)(v3 + 24) > 7u )
        v10 = *(const WCHAR **)v3;
      Extension = PathCchFindExtension(v10, *(_QWORD *)(v3 + 16) + 1LL, &ppszExt);
      if ( Extension < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)(unsigned int)Extension,
          dwFlags);
      if ( (unsigned int)_o__wcsicmp(ppszExt, L".ppkg") )
      {
        if ( (unsigned int)dword_1800FA480 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FA480, 0x400000000000LL) )
        {
          LODWORD(cFileName) = -2147024809;
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v61, FileNameW);
          v43 = std::wstring::c_str(v3);
          v44 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v67, v43);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&cFileName,
            (unsigned int)&byte_1800EA41F,
            v45,
            v46,
            v44,
            v45,
            (__int64)&cFileName);
        }
        v47 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v47,
          dwFlags);
      }
      v12 = operator new(0xA8u);
      v67 = v12;
      v66 = v68;
      v13 = std::wstring::wstring(v68, v3);
      v14 = std::wstring::wstring(v71, FileNameW);
      cFileName = ProvPackage::ProvPackage(v12, v14, v13);
      std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(a2, &cFileName);
    }
    v3 += 32;
  }
  if ( (unsigned int)dword_1800FA480 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1800FA480,
      &word_1800EA26E,
      0);
  return a2;
}

```

## disassembly

```asm
0x1800ad298  mov     [rsp-8+arg_10], rbx
0x1800ad29d  mov     [rsp-8+arg_18], rsi
0x1800ad2a2  push    rbp
0x1800ad2a3  push    rdi
0x1800ad2a4  push    r12
0x1800ad2a6  push    r14
0x1800ad2a8  push    r15
0x1800ad2aa  lea     rbp, [rsp-280h]
0x1800ad2b2  sub     rsp, 380h
0x1800ad2b9  mov     rax, cs:__security_cookie
0x1800ad2c0  xor     rax, rsp
0x1800ad2c3  mov     [rbp+2A0h+var_30], rax
0x1800ad2ca  mov     r15, rdx
0x1800ad2cd  mov     [rbp+2A0h+var_2F0], rdx
0x1800ad2d1  mov     [rsp+3A0h+var_348], 0
0x1800ad2d9  mov     qword ptr [rdx], 0
0x1800ad2e0  mov     qword ptr [rdx+8], 0
0x1800ad2e8  mov     qword ptr [rdx+10h], 0
0x1800ad2f0  mov     [rsp+3A0h+var_348], 1
0x1800ad2f8  mov     r14, [rcx+8]
0x1800ad2fc  mov     r12, [rcx+10h]
0x1800ad300  jmp     loc_1800AD663
0x1800ad305  mov     rcx, r14
0x1800ad308  cmp     qword ptr [r14+18h], 7
0x1800ad30d  jbe     short loc_1800AD312
0x1800ad30f  mov     rcx, [r14]; lpFileName
0x1800ad312  call    cs:__imp_GetFileAttributesW
0x1800ad318  cmp     eax, 0FFFFFFFFh
0x1800ad31b  jz      loc_1800AD738
0x1800ad321  mov     rcx, r14
0x1800ad324  cmp     qword ptr [r14+18h], 7
0x1800ad329  jbe     short loc_1800AD32E
0x1800ad32b  mov     rcx, [r14]; lpFileName
0x1800ad32e  call    cs:__imp_GetFileAttributesW
0x1800ad334  test    al, 10h
0x1800ad336  jnz     loc_1800AD40E
0x1800ad33c  mov     rcx, r14
0x1800ad33f  cmp     qword ptr [r14+18h], 7
0x1800ad344  jbe     short loc_1800AD349
0x1800ad346  mov     rcx, [r14]; pszPath
0x1800ad349  call    cs:__imp_PathFindFileNameW
0x1800ad34f  mov     rsi, rax
0x1800ad352  mov     rcx, [rbp+2A8h]; this
0x1800ad359  test    rax, rax
0x1800ad35c  jz      loc_1800AD840
0x1800ad362  mov     [rsp+3A0h+ppszExt], 0
0x1800ad36b  mov     rdx, [r14+10h]
0x1800ad36f  inc     rdx; cchPath
0x1800ad372  mov     rcx, r14
0x1800ad375  cmp     qword ptr [r14+18h], 7
0x1800ad37a  jbe     short loc_1800AD37F
0x1800ad37c  mov     rcx, [r14]; pszPath
0x1800ad37f  lea     r8, [rsp+3A0h+ppszExt]; ppszExt
0x1800ad384  call    cs:__imp_PathCchFindExtension
0x1800ad38a  mov     rcx, [rbp+2A8h]; this
0x1800ad391  test    eax, eax
0x1800ad393  js      loc_1800AD82B
0x1800ad399  lea     rdx, aPpkg_0; ".ppkg"
0x1800ad3a0  mov     rcx, [rsp+3A0h+ppszExt]
0x1800ad3a5  call    cs:__imp__o__wcsicmp
0x1800ad3ab  test    eax, eax
0x1800ad3ad  jnz     loc_1800AD794
0x1800ad3b3  mov     ecx, 0A8h; Size
0x1800ad3b8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ad3bd  mov     rdi, rax
0x1800ad3c0  mov     [rbp+2A0h+var_318], rax
0x1800ad3c4  lea     rax, [rbp+2A0h+var_310]
0x1800ad3c8  mov     [rbp+2A0h+var_320], rax
0x1800ad3cc  mov     rdx, r14
0x1800ad3cf  lea     rcx, [rbp+2A0h+var_310]
0x1800ad3d3  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800ad3d8  mov     rbx, rax
0x1800ad3db  mov     rdx, rsi
0x1800ad3de  lea     rcx, [rbp+2A0h+var_2E8]
0x1800ad3e2  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ad3e7  nop
0x1800ad3e8  mov     r8, rbx
0x1800ad3eb  mov     rdx, rax
0x1800ad3ee  mov     rcx, rdi
0x1800ad3f1  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x1800ad3f6  nop
0x1800ad3f7  mov     [rsp+3A0h+var_360], rax
0x1800ad3fc  lea     rdx, [rsp+3A0h+var_360]
0x1800ad401  mov     rcx, r15
0x1800ad404  call    ??$emplace_back@PEAVProvPackage@@@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@1@$$QEAPEAVProvPackage@@@Z; std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(ProvPackage * &&)
0x1800ad409  jmp     loc_1800AD65F
0x1800ad40e  lea     rdx, aPpkg; "*.ppkg"
0x1800ad415  lea     rcx, [rbp+2A0h+pszMore]
0x1800ad419  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ad41e  nop
0x1800ad41f  xorps   xmm0, xmm0
0x1800ad422  movdqu  xmmword ptr [rsp+3A0h+pszPathOut], xmm0
0x1800ad428  mov     [rsp+3A0h+var_330], 0
0x1800ad431  mov     rdx, [r14+10h]
0x1800ad435  mov     rax, [rbp+2A0h+var_298]
0x1800ad439  add     rax, 6
0x1800ad43d  add     rdx, rax
0x1800ad440  lea     rcx, [rsp+3A0h+pszPathOut]
0x1800ad445  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x1800ad44a  lea     r9, [rbp+2A0h+pszMore]
0x1800ad44e  cmp     [rbp+2A0h+var_290], 7
0x1800ad453  cmova   r9, [rbp+2A0h+pszMore]; pszMore
0x1800ad458  mov     r8, r14
0x1800ad45b  cmp     qword ptr [r14+18h], 7
0x1800ad460  jbe     short loc_1800AD465
0x1800ad462  mov     r8, [r14]; pszPathIn
0x1800ad465  mov     rcx, [rsp+3A0h+pszPathOut]; pszPathOut
0x1800ad46a  mov     rdx, [rsp+3A0h+var_330]
0x1800ad46f  sub     rdx, rcx
0x1800ad472  sar     rdx, 1; cchPathOut
0x1800ad475  mov     [rsp+3A0h+dwFlags], 1; dwFlags
0x1800ad47d  call    cs:__imp_PathCchCombineEx
0x1800ad483  mov     ebx, eax
0x1800ad485  test    eax, eax
0x1800ad487  js      loc_1800AD6BB
0x1800ad48d  xor     edx, edx; Val
0x1800ad48f  mov     r8d, 250h; Size
0x1800ad495  lea     rcx, [rbp+2A0h+FindFileData]; void *
0x1800ad499  call    memset_0
0x1800ad49e  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x1800ad4a2  mov     rcx, [rsp+3A0h+pszPathOut]; lpFileName
0x1800ad4a7  call    cs:__imp_FindFirstFileW
0x1800ad4ad  mov     rbx, rax
0x1800ad4b0  mov     [rbp+2A0h+var_320], rax
0x1800ad4b4  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800ad4b8  jnz     short loc_1800AD500
0x1800ad4ba  call    cs:__imp_GetLastError
0x1800ad4c0  mov     r8d, eax
0x1800ad4c3  cmp     eax, 2
0x1800ad4c6  mov     eax, cs:dword_1800FA480
0x1800ad4cc  jnz     loc_1800AD858
0x1800ad4d2  cmp     eax, 4
0x1800ad4d5  jbe     loc_1800AD641
0x1800ad4db  mov     rax, [rsp+3A0h+pszPathOut]
0x1800ad4e0  mov     [rsp+3A0h+var_360], rax
0x1800ad4e5  lea     rax, [rsp+3A0h+var_360]
0x1800ad4ea  mov     qword ptr [rsp+3A0h+dwFlags], rax
0x1800ad4ef  lea     rdx, unk_1800EA360
0x1800ad4f6  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800ad4fb  jmp     loc_1800AD641
0x1800ad500  mov     eax, cs:dword_1800FA480
0x1800ad506  cmp     eax, 5
0x1800ad509  jbe     short loc_1800AD53E
0x1800ad50b  lea     rax, [rbp+2A0h+FindFileData.cFileName]
0x1800ad50f  mov     [rsp+3A0h+var_360], rax
0x1800ad514  mov     rax, [rsp+3A0h+pszPathOut]
0x1800ad519  mov     qword ptr [rsp+3A0h+var_358], rax
0x1800ad51e  lea     rax, [rsp+3A0h+var_360]
0x1800ad523  mov     [rsp+3A0h+var_378], rax
0x1800ad528  lea     rax, [rsp+3A0h+var_358]
0x1800ad52d  mov     qword ptr [rsp+3A0h+dwFlags], rax; int
0x1800ad532  lea     rdx, unk_1800EA298
0x1800ad539  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800ad53e  mov     [rsp+3A0h+var_360], 0
0x1800ad547  lea     r8, [rsp+3A0h+var_360]; unsigned __int64 *
0x1800ad54c  mov     edx, 104h; unsigned __int64
0x1800ad551  lea     rcx, [rbp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x1800ad555  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800ad55a  mov     rcx, [rbp+2A8h]; this
0x1800ad561  test    eax, eax
0x1800ad563  js      loc_1800AD950
0x1800ad569  xorps   xmm0, xmm0
0x1800ad56c  movdqu  xmmword ptr [rbp+2A0h+var_310], xmm0
0x1800ad571  mov     [rbp+2A0h+var_300], 0
0x1800ad579  mov     rdx, [rsp+3A0h+var_360]
0x1800ad57e  add     rdx, 6
0x1800ad582  add     rdx, [r14+10h]
0x1800ad586  lea     rcx, [rbp+2A0h+var_310]
0x1800ad58a  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x1800ad58f  cmp     qword ptr [r14+18h], 7
0x1800ad594  jbe     short loc_1800AD59B
0x1800ad596  mov     r8, [r14]
0x1800ad599  jmp     short loc_1800AD59E
0x1800ad59b  mov     r8, r14; pszPathIn
0x1800ad59e  mov     rcx, [rbp+2A0h+var_310]; pszPathOut
0x1800ad5a2  mov     rdx, [rbp+2A0h+var_300]
0x1800ad5a6  sub     rdx, rcx
0x1800ad5a9  sar     rdx, 1; cchPathOut
0x1800ad5ac  mov     [rsp+3A0h+dwFlags], 1; int
0x1800ad5b4  lea     r9, [rbp+2A0h+FindFileData.cFileName]; pszMore
0x1800ad5b8  call    cs:__imp_PathCchCombineEx
0x1800ad5be  mov     edi, eax
0x1800ad5c0  test    eax, eax
0x1800ad5c2  js      loc_1800AD8C6
0x1800ad5c8  mov     ecx, 0A8h; Size
0x1800ad5cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800ad5d2  mov     rsi, rax
0x1800ad5d5  mov     [rsp+3A0h+var_350], rax
0x1800ad5da  lea     rax, [rbp+2A0h+var_2E8]
0x1800ad5de  mov     qword ptr [rsp+3A0h+var_358], rax
0x1800ad5e3  mov     rdx, [rbp+2A0h+var_310]
0x1800ad5e7  lea     rcx, [rbp+2A0h+var_2E8]
0x1800ad5eb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ad5f0  mov     rdi, rax
0x1800ad5f3  lea     rdx, [rbp+2A0h+FindFileData.cFileName]
0x1800ad5f7  lea     rcx, [rbp+2A0h+var_2C8]
0x1800ad5fb  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800ad600  nop
0x1800ad601  mov     r8, rdi
0x1800ad604  mov     rdx, rax
0x1800ad607  mov     rcx, rsi
0x1800ad60a  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x1800ad60f  nop
0x1800ad610  mov     qword ptr [rsp+3A0h+var_358], rax
0x1800ad615  lea     rdx, [rsp+3A0h+var_358]
0x1800ad61a  mov     rcx, r15
0x1800ad61d  call    ??$emplace_back@PEAVProvPackage@@@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@1@$$QEAPEAVProvPackage@@@Z; std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(ProvPackage * &&)
0x1800ad622  nop
0x1800ad623  lea     rcx, [rbp+2A0h+var_310]
0x1800ad627  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800ad62c  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x1800ad630  mov     rcx, rbx; hFindFile
0x1800ad633  call    cs:__imp_FindNextFileW
0x1800ad639  test    eax, eax
0x1800ad63b  jnz     loc_1800AD500
0x1800ad641  lea     rcx, [rbp+2A0h+var_320]
0x1800ad645  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800ad64a  nop
0x1800ad64b  lea     rcx, [rsp+3A0h+pszPathOut]
0x1800ad650  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800ad655  nop
0x1800ad656  lea     rcx, [rbp+2A0h+pszMore]
0x1800ad65a  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800ad65f  add     r14, 20h ; ' '
0x1800ad663  cmp     r14, r12
0x1800ad666  jnz     loc_1800AD305
0x1800ad66c  mov     ecx, cs:dword_1800FA480
0x1800ad672  cmp     ecx, 5
0x1800ad675  jbe     short loc_1800AD68D
0x1800ad677  xor     r8d, r8d
0x1800ad67a  lea     rdx, word_1800EA26E
0x1800ad681  lea     rcx, dword_1800FA480
0x1800ad688  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800ad68d  mov     rax, r15
0x1800ad690  mov     rcx, [rbp+2A0h+var_30]
0x1800ad697  xor     rcx, rsp; StackCookie
0x1800ad69a  call    __security_check_cookie
0x1800ad69f  lea     r11, [rsp+3A0h+var_20]
0x1800ad6a7  mov     rbx, [r11+40h]
0x1800ad6ab  mov     rsi, [r11+48h]
0x1800ad6af  mov     rsp, r11
0x1800ad6b2  pop     r15
0x1800ad6b4  pop     r14
0x1800ad6b6  pop     r12
0x1800ad6b8  pop     rdi
0x1800ad6b9  pop     rbp
0x1800ad6ba  retn
0x1800ad6bb  mov     eax, cs:dword_1800FA480
0x1800ad6c1  cmp     eax, 2
0x1800ad6c4  jbe     short loc_1800AD715
0x1800ad6c6  xor     edx, edx
0x1800ad6c8  lea     rcx, dword_1800FA480
0x1800ad6cf  call    _tlgKeywordOn
0x1800ad6d4  test    al, al
0x1800ad6d6  jz      short loc_1800AD715
0x1800ad6d8  mov     dword ptr [rsp+3A0h+var_360], ebx
0x1800ad6dc  lea     rcx, [rsp+3A0h+pszPathOut]
0x1800ad6e1  call    ?data@?$vector@GV?$allocator@G@std@@@std@@QEAAPEAGXZ; std::vector<ushort>::data(void)
0x1800ad6e6  mov     rdx, rax
0x1800ad6e9  lea     rcx, [rsp+3A0h+var_350]
0x1800ad6ee  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800ad6f3  lea     rcx, [rsp+3A0h+var_360]
0x1800ad6f8  mov     [rsp+3A0h+var_378], rcx
0x1800ad6fd  mov     qword ptr [rsp+3A0h+dwFlags], rax; int
0x1800ad702  lea     rdx, byte_1800EA323
0x1800ad709  lea     rcx, dword_1800FA480
0x1800ad710  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800ad715  mov     ecx, ebx
0x1800ad717  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800ad71c  mov     r9d, eax; char *
0x1800ad71f  mov     rcx, [rbp+2A8h]; this
0x1800ad726  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800ad72d  mov     edx, 0E6h; void *
0x1800ad732  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800ad738  mov     eax, cs:dword_1800FA480
0x1800ad73e  cmp     eax, 2
0x1800ad741  jbe     short loc_1800AD77B
0x1800ad743  xor     edx, edx
0x1800ad745  lea     rcx, dword_1800FA480
0x1800ad74c  call    _tlgKeywordOn
0x1800ad751  test    al, al
0x1800ad753  jz      short loc_1800AD77B
0x1800ad755  mov     rcx, r14
0x1800ad758  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800ad75d  mov     rdx, rax
0x1800ad760  lea     rcx, [rsp+3A0h+var_350]
0x1800ad765  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800ad76a  mov     qword ptr [rsp+3A0h+dwFlags], rax
0x1800ad76f  lea     rdx, word_1800EA3FE
0x1800ad776  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800ad77b  mov     rcx, [rbp+2A8h]; this
0x1800ad782  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800ad789  mov     edx, 0C3h; void *
0x1800ad78e  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1800ad794  mov     eax, cs:dword_1800FA480
0x1800ad79a  cmp     eax, 2
0x1800ad79d  jbe     short loc_1800AD805
0x1800ad79f  mov     rdx, 400000000000h
0x1800ad7a9  lea     rcx, dword_1800FA480
0x1800ad7b0  call    _tlgKeywordOn
  ... truncated ...
```
