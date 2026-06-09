# PackageCollector::Search(void)

- ea: `0x14000b454`
- end: `0x14000bc9c`
- name: `?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ`
- size: `2120`
- prototype: `_QWORD *__fastcall(__int64, _QWORD *)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x140006b70`

## callees

- `0x140001008`
- `0x1400010f4`
- `0x140001104`
- `0x140001130`
- `0x14000124c`
- `0x14000132c`
- `0x140001424`
- `0x140001674`
- `0x140001ebf`
- `0x1400032e8`
- `0x140008850`
- `0x140008b88`
- `0x140008ca8`
- `0x140008cd8`
- `0x140008e50`
- `0x140008f60`
- `0x140009040`
- `0x14000a3b8`
- `0x14000a99c`
- `0x14000b454`
- `0x14000c0e0`
- `0x14000ded0`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x14000b55f`
- `msvcrt!_wcsicmp` at `0x14000b55f`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b72d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b743`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b92a`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b969`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b97b`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b72d`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b743`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b92a`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b969`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b97b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6ec`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000b6ec`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x14000b6b1`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x14000b841`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x14000b6b1`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x14000b841`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x14000b53f`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x14000b53f`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000b937`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x14000b937`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000b6d9`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x14000b6d9`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000b4cd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000b4eb`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000b4cd`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x14000b4eb`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b95a`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x14000b95a`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000b508`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x14000b508`

## pseudocode

```c
_QWORD *__fastcall PackageCollector::Search(__int64 a1, _QWORD *a2)
{
  __int64 v3; // rbx
  __int64 v4; // rsi
  const WCHAR *v5; // rcx
  const char *v6; // r9
  const WCHAR *v7; // rcx
  const WCHAR *v8; // rcx
  LPWSTR FileNameW; // rdi
  const WCHAR *v10; // rcx
  HRESULT Extension; // eax
  void *v12; // r14
  __int64 v13; // r8
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rdx
  unsigned __int64 v17; // r8
  const WCHAR *v18; // r9
  const WCHAR *v19; // r8
  WCHAR *v20; // r12
  HRESULT v21; // edi
  int v22; // ecx
  HANDLE FirstFileW; // rdi
  int v24; // r8d
  int v25; // r9d
  int v26; // ecx
  DWORD LastError; // r8d
  const char *v28; // r9
  __int64 v29; // r9
  WCHAR *v30; // rax
  __int64 v31; // rcx
  unsigned __int64 v32; // rdx
  const WCHAR *v33; // r8
  PWSTR v34; // r15
  HRESULT v35; // r14d
  void *v36; // r14
  __int64 v37; // r8
  __int64 v38; // r8
  __int64 v39; // rax
  __int64 v41; // rax
  __int64 v42; // rax
  int v43; // ecx
  int v44; // r8d
  int v45; // r9d
  __int64 v46; // rax
  __int64 v47; // rax
  int v48; // ecx
  __int64 v49; // r8
  int v50; // r9d
  unsigned int v51; // eax
  int v52; // r8d
  __int64 v53; // rax
  __int64 v54; // rax
  int v55; // r8d
  int v56; // r9d
  __int64 v57; // rax
  __int64 v58; // rax
  __int64 v59; // r8
  int v60; // r9d
  unsigned int v61; // eax
  __int64 v62; // rax
  __int64 v63; // rax
  int v64; // r8d
  int v65; // r9d
  unsigned int v66; // eax
  int dwFlags; // [rsp+20h] [rbp-E0h]
  WCHAR *cFileName; // [rsp+40h] [rbp-C0h] BYREF
  int v69[2]; // [rsp+48h] [rbp-B8h] BYREF
  void *v70; // [rsp+50h] [rbp-B0h] BYREF
  int v71; // [rsp+58h] [rbp-A8h]
  PWSTR pszPathOut[2]; // [rsp+60h] [rbp-A0h] BYREF
  __int64 v73; // [rsp+70h] [rbp-90h]
  __int64 v74; // [rsp+78h] [rbp-88h]
  PCWSTR ppszExt; // [rsp+80h] [rbp-80h] BYREF
  PWSTR v76[2]; // [rsp+88h] [rbp-78h] BYREF
  __int64 v77; // [rsp+98h] [rbp-68h]
  __int64 v78; // [rsp+A0h] [rbp-60h]
  void *v79; // [rsp+A8h] [rbp-58h] BYREF
  HANDLE v80; // [rsp+B0h] [rbp-50h] BYREF
  _WORD v81[8]; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v82; // [rsp+C8h] [rbp-38h]
  __int64 v83; // [rsp+D0h] [rbp-30h]
  _QWORD *v84; // [rsp+D8h] [rbp-28h]
  PCWSTR pszMore[2]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v86; // [rsp+F0h] [rbp-10h]
  unsigned __int64 v87; // [rsp+F8h] [rbp-8h]
  _WIN32_FIND_DATAW FindFileData; // [rsp+100h] [rbp+0h] BYREF
  _WORD v89[8]; // [rsp+350h] [rbp+250h] BYREF
  __int64 v90; // [rsp+360h] [rbp+260h]
  __int64 v91; // [rsp+368h] [rbp+268h]
  wil::details::in1diag3 *retaddr; // [rsp+3C8h] [rbp+2C8h]

  v84 = a2;
  *a2 = 0;
  a2[1] = 0;
  a2[2] = 0;
  v71 = 1;
  v3 = *(_QWORD *)(a1 + 8);
  v4 = *(_QWORD *)(a1 + 16);
  while ( v3 != v4 )
  {
    if ( *(_QWORD *)(v3 + 24) < 8u )
      v5 = (const WCHAR *)v3;
    else
      v5 = *(const WCHAR **)v3;
    if ( GetFileAttributesW(v5) == -1 )
    {
      if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0) )
      {
        v41 = std::wstring::c_str(v3);
        v42 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, v41);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v43,
          (unsigned int)byte_1400135F3,
          v44,
          v45,
          v42);
      }
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0xC3,
        (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
        v6);
    }
    if ( *(_QWORD *)(v3 + 24) < 8u )
      v7 = (const WCHAR *)v3;
    else
      v7 = *(const WCHAR **)v3;
    if ( (GetFileAttributesW(v7) & 0x10) != 0 )
    {
      v87 = 7;
      v86 = 0;
      LOWORD(pszMore[0]) = 0;
      std::wstring::assign(pszMore, L"*.ppkg");
      *(_OWORD *)pszPathOut = 0;
      v16 = 0;
      v73 = 0;
      v17 = v86 + 6 + *(_QWORD *)(v3 + 16);
      if ( v17 )
      {
        if ( v17 > 0x7FFFFFFFFFFFFFFFLL )
          std::vector<std::unique_ptr<ProvPackage>>::_Xlen(v15, 0, v17);
        std::vector<unsigned short>::_Reallocate(pszPathOut, v17);
        v16 = v73;
      }
      v18 = (const WCHAR *)pszMore;
      if ( v87 >= 8 )
        v18 = pszMore[0];
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v19 = (const WCHAR *)v3;
      else
        v19 = *(const WCHAR **)v3;
      v20 = pszPathOut[0];
      v21 = PathCchCombineEx(pszPathOut[0], (signed __int64)(v16 - (unsigned __int64)pszPathOut[0]) >> 1, v19, v18, 1u);
      if ( v21 < 0 )
      {
        if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0) )
        {
          LODWORD(cFileName) = v21;
          v62 = std::vector<unsigned short>::data(pszPathOut);
          v63 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, v62);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&cFileName,
            (unsigned int)word_14001357A,
            v64,
            v65,
            v63,
            (__int64)&cFileName);
        }
        v66 = wil::verify_hresult<long>((unsigned int)v21);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xE6,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v66,
          dwFlags);
      }
      memset_0(&FindFileData, 0, sizeof(FindFileData));
      FirstFileW = FindFirstFileW(v20, &FindFileData);
      v80 = FirstFileW;
      if ( FirstFileW == (HANDLE)-1LL )
      {
        LastError = GetLastError();
        if ( LastError != 2 )
        {
          if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0) )
          {
            LODWORD(cFileName) = v52;
            v53 = std::vector<unsigned short>::data(pszPathOut);
            v54 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, v53);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&cFileName,
              (unsigned int)&word_14001350E,
              v55,
              v56,
              v54,
              (__int64)&cFileName);
          }
          wil::details::in1diag3::Throw_GetLastError(
            retaddr,
            (void *)0xF9,
            (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
            v28);
        }
        if ( (unsigned int)dword_140017048 > 4 )
        {
          cFileName = v20;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v26,
            (unsigned int)&unk_140013548,
            LastError,
            (_DWORD)v28,
            (__int64)&cFileName);
        }
        if ( v20 )
          operator delete(v20);
        if ( v87 >= 8 )
          goto LABEL_74;
      }
      else
      {
        do
        {
          if ( (unsigned int)dword_140017048 > 5 )
          {
            cFileName = FindFileData.cFileName;
            *(_QWORD *)v69 = v20;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v22,
              (unsigned int)word_1400134D2,
              v24,
              v25,
              (__int64)v69,
              (__int64)&cFileName);
          }
          v29 = 260;
          v30 = FindFileData.cFileName;
          do
          {
            if ( !*v30 )
              break;
            ++v30;
            --v29;
          }
          while ( v29 );
          if ( !v29 )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x104,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)0x80070057LL,
              dwFlags);
          *(_OWORD *)v76 = 0;
          v31 = 0;
          v77 = 0;
          v32 = ((260 - v29) & ((unsigned __int128)-(__int128)(unsigned __int64)v29 >> 64) & -(__int64)(v29 != 0))
              + *(_QWORD *)(v3 + 16)
              + 6LL;
          if ( v32 )
          {
            if ( v32 > 0x7FFFFFFFFFFFFFFFLL )
              std::vector<std::unique_ptr<ProvPackage>>::_Xlen(0, v32, -v29);
            std::vector<unsigned short>::_Reallocate(v76, v32);
            v31 = v77;
          }
          if ( *(_QWORD *)(v3 + 24) < 8u )
            v33 = (const WCHAR *)v3;
          else
            v33 = *(const WCHAR **)v3;
          v34 = v76[0];
          v35 = PathCchCombineEx(
                  v76[0],
                  (signed __int64)(v31 - (unsigned __int64)v76[0]) >> 1,
                  v33,
                  FindFileData.cFileName,
                  1u);
          if ( v35 < 0 )
          {
            if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0) )
            {
              LODWORD(cFileName) = v35;
              _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, FindFileData.cFileName);
              v57 = std::vector<unsigned short>::data(v76);
              v58 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v79, v57);
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
                (unsigned int)&cFileName,
                (unsigned int)byte_140013483,
                v59,
                v60,
                v58,
                v59,
                (__int64)&cFileName);
            }
            v61 = wil::verify_hresult<long>((unsigned int)v35);
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x113,
              (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
              (const char *)v61,
              dwFlags);
          }
          v36 = operator new(0xA8u);
          v70 = v36;
          if ( v36 )
          {
            *(_QWORD *)v69 = v81;
            v83 = 7;
            v82 = 0;
            v81[0] = 0;
            if ( *v34 )
            {
              v37 = -1;
              do
                ++v37;
              while ( v34[v37] );
            }
            std::wstring::assign(v81, v34);
            v91 = 7;
            v90 = 0;
            v89[0] = 0;
            if ( FindFileData.cFileName[0] )
            {
              v38 = -1;
              do
                ++v38;
              while ( FindFileData.cFileName[v38] );
            }
            std::wstring::assign(v89, FindFileData.cFileName);
            v39 = ProvPackage::ProvPackage(v36, v89, v81);
          }
          else
          {
            v39 = 0;
          }
          *(_QWORD *)v69 = v39;
          std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(a2, v69);
          if ( v34 )
            operator delete(v34);
        }
        while ( FindNextFileW(FirstFileW, &FindFileData) );
        if ( FirstFileW )
          FindClose(FirstFileW);
        if ( v20 )
          operator delete(v20);
        if ( v87 >= 8 )
LABEL_74:
          operator delete((void *)pszMore[0]);
      }
    }
    else
    {
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v8 = (const WCHAR *)v3;
      else
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
      if ( *(_QWORD *)(v3 + 24) < 8u )
        v10 = (const WCHAR *)v3;
      else
        v10 = *(const WCHAR **)v3;
      Extension = PathCchFindExtension(v10, *(_QWORD *)(v3 + 16) + 1LL, &ppszExt);
      if ( Extension < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)(unsigned int)Extension,
          dwFlags);
      if ( _wcsicmp(ppszExt, L".ppkg") )
      {
        if ( (unsigned int)dword_140017048 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140017048, 0x400000000000LL) )
        {
          LODWORD(cFileName) = -2147024809;
          _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v70, FileNameW);
          v46 = std::wstring::c_str(v3);
          v47 = _tlgWrapSz<unsigned short>::_tlgWrapSz<unsigned short>(&v80, v46);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            v48,
            (unsigned int)&byte_1400135B7,
            v49,
            v50,
            v47,
            v49,
            (__int64)&cFileName);
        }
        v51 = wil::verify_hresult<long>(2147942487LL);
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xD3,
          (unsigned int)"onecoreuap\\admin\\prov\\lib\\packagecollector.cpp",
          (const char *)v51,
          dwFlags);
      }
      v12 = operator new(0xA8u);
      v79 = v12;
      if ( v12 )
      {
        *(_QWORD *)v69 = v76;
        v78 = 7;
        v77 = 0;
        LOWORD(v76[0]) = 0;
        std::wstring::assign(v76);
        v74 = 7;
        v73 = 0;
        LOWORD(pszPathOut[0]) = 0;
        if ( *FileNameW )
        {
          v13 = -1;
          do
            ++v13;
          while ( FileNameW[v13] );
        }
        std::wstring::assign(pszPathOut, FileNameW);
        v14 = ProvPackage::ProvPackage(v12, pszPathOut, v76);
      }
      else
      {
        v14 = 0;
      }
      cFileName = (WCHAR *)v14;
      std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(a2, &cFileName);
    }
    v3 += 32;
  }
  if ( (unsigned int)dword_140017048 > 5 )
    tlgWriteTransfer_EventWriteTransfer(&dword_140017048, byte_140013459, 0, 0);
  return a2;
}

```

## disassembly

```asm
0x14000b454  push    rbp
0x14000b456  push    rbx
0x14000b457  push    rsi
0x14000b458  push    rdi
0x14000b459  push    r12
0x14000b45b  push    r13
0x14000b45d  push    r14
0x14000b45f  push    r15
0x14000b461  lea     rbp, [rsp-288h]
0x14000b469  sub     rsp, 388h
0x14000b470  mov     rax, cs:__security_cookie
0x14000b477  xor     rax, rsp
0x14000b47a  mov     [rbp+2C0h+var_50], rax
0x14000b481  mov     r13, rdx
0x14000b484  mov     [rbp+2C0h+var_2E8], rdx
0x14000b488  xor     r15d, r15d
0x14000b48b  mov     [rsp+3C0h+var_368], r15d
0x14000b490  mov     [rdx], r15
0x14000b493  mov     [rdx+8], r15
0x14000b497  mov     [rdx+10h], r15
0x14000b49b  mov     [rsp+3C0h+var_368], 1
0x14000b4a3  mov     rbx, [rcx+8]
0x14000b4a7  mov     rsi, [rcx+10h]
0x14000b4ab  mov     r14, 7FFFFFFFFFFFFFFFh
0x14000b4b5  cmp     rbx, rsi
0x14000b4b8  jz      loc_14000B994
0x14000b4be  cmp     qword ptr [rbx+18h], 8
0x14000b4c3  jb      short loc_14000B4CA
0x14000b4c5  mov     rcx, [rbx]
0x14000b4c8  jmp     short loc_14000B4CD
0x14000b4ca  mov     rcx, rbx; lpFileName
0x14000b4cd  call    cs:__imp_GetFileAttributesW
0x14000b4d3  cmp     eax, 0FFFFFFFFh
0x14000b4d6  jz      loc_14000B9F2
0x14000b4dc  cmp     qword ptr [rbx+18h], 8
0x14000b4e1  jb      short loc_14000B4E8
0x14000b4e3  mov     rcx, [rbx]
0x14000b4e6  jmp     short loc_14000B4EB
0x14000b4e8  mov     rcx, rbx; lpFileName
0x14000b4eb  call    cs:__imp_GetFileAttributesW
0x14000b4f1  test    al, 10h
0x14000b4f3  jnz     loc_14000B619
0x14000b4f9  cmp     qword ptr [rbx+18h], 8
0x14000b4fe  jb      short loc_14000B505
0x14000b500  mov     rcx, [rbx]
0x14000b503  jmp     short loc_14000B508
0x14000b505  mov     rcx, rbx; pszPath
0x14000b508  call    cs:__imp_PathFindFileNameW
0x14000b50e  mov     rdi, rax
0x14000b511  mov     rcx, [rbp+2C8h]; this
0x14000b518  test    rax, rax
0x14000b51b  jz      loc_14000BAFA
0x14000b521  mov     [rbp+2C0h+ppszExt], r15
0x14000b525  mov     rdx, [rbx+10h]
0x14000b529  inc     rdx; cchPath
0x14000b52c  cmp     qword ptr [rbx+18h], 8
0x14000b531  jb      short loc_14000B538
0x14000b533  mov     rcx, [rbx]
0x14000b536  jmp     short loc_14000B53B
0x14000b538  mov     rcx, rbx; pszPath
0x14000b53b  lea     r8, [rbp+2C0h+ppszExt]; ppszExt
0x14000b53f  call    cs:__imp_PathCchFindExtension
0x14000b545  mov     rcx, [rbp+2C8h]; this
0x14000b54c  test    eax, eax
0x14000b54e  js      loc_14000BAE5
0x14000b554  lea     rdx, aPpkg_0; ".ppkg"
0x14000b55b  mov     rcx, [rbp+2C0h+ppszExt]; String1
0x14000b55f  call    cs:__imp__wcsicmp
0x14000b565  test    eax, eax
0x14000b567  jnz     loc_14000BA4E
0x14000b56d  mov     ecx, 0A8h; Size
0x14000b572  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b577  mov     r14, rax
0x14000b57a  mov     [rbp+2C0h+var_318], rax
0x14000b57e  test    rax, rax
0x14000b581  jz      short loc_14000B5FF
0x14000b583  lea     rax, [rbp+2C0h+var_338]
0x14000b587  mov     qword ptr [rsp+3C0h+var_378], rax
0x14000b58c  mov     [rbp+2C0h+var_320], 7
0x14000b594  mov     [rbp+2C0h+var_328], r15
0x14000b598  mov     word ptr [rbp+2C0h+var_338], r15w
0x14000b59d  or      r9, 0FFFFFFFFFFFFFFFFh
0x14000b5a1  xor     r8d, r8d
0x14000b5a4  mov     rdx, rbx
0x14000b5a7  lea     rcx, [rbp+2C0h+var_338]; void *
0x14000b5ab  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x14000b5b0  nop
0x14000b5b1  mov     [rsp+3C0h+var_348], 7
0x14000b5ba  mov     [rsp+3C0h+var_350], r15
0x14000b5bf  mov     word ptr [rsp+3C0h+pszPathOut], r15w
0x14000b5c5  cmp     [rdi], r15w
0x14000b5c9  jnz     short loc_14000B5D0
0x14000b5cb  mov     r8, r15
0x14000b5ce  jmp     short loc_14000B5DE
0x14000b5d0  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000b5d4  inc     r8
0x14000b5d7  cmp     [rdi+r8*2], r15w
0x14000b5dc  jnz     short loc_14000B5D4
0x14000b5de  mov     rdx, rdi; Src
0x14000b5e1  lea     rcx, [rsp+3C0h+pszPathOut]; void *
0x14000b5e6  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000b5eb  nop
0x14000b5ec  lea     r8, [rbp+2C0h+var_338]
0x14000b5f0  lea     rdx, [rsp+3C0h+pszPathOut]
0x14000b5f5  mov     rcx, r14
0x14000b5f8  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x14000b5fd  jmp     short loc_14000B602
0x14000b5ff  mov     rax, r15
0x14000b602  mov     [rsp+3C0h+var_380], rax
0x14000b607  lea     rdx, [rsp+3C0h+var_380]
0x14000b60c  mov     rcx, r13
0x14000b60f  call    ??$emplace_back@PEAVProvPackage@@@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAX$$QEAPEAVProvPackage@@@Z; std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(ProvPackage * &&)
0x14000b614  jmp     loc_14000B981
0x14000b619  mov     [rbp+2C0h+var_2C8], 7
0x14000b621  mov     [rbp+2C0h+var_2D0], r15
0x14000b625  mov     word ptr [rbp+2C0h+pszMore], r15w
0x14000b62a  mov     r8d, 6
0x14000b630  lea     rdx, aPpkg; "*.ppkg"
0x14000b637  lea     rcx, [rbp+2C0h+pszMore]; void *
0x14000b63b  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000b640  nop
0x14000b641  xorps   xmm0, xmm0
0x14000b644  movdqu  xmmword ptr [rsp+3C0h+pszPathOut], xmm0
0x14000b64a  mov     rdx, r15
0x14000b64d  mov     [rsp+3C0h+var_350], rdx
0x14000b652  mov     r8, [rbx+10h]
0x14000b656  mov     rax, [rbp+2C0h+var_2D0]
0x14000b65a  add     rax, 6
0x14000b65e  add     r8, rax
0x14000b661  jz      short loc_14000B67E
0x14000b663  cmp     r8, r14
0x14000b666  ja      loc_14000BB12
0x14000b66c  mov     rdx, r8
0x14000b66f  lea     rcx, [rsp+3C0h+pszPathOut]
0x14000b674  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x14000b679  mov     rdx, [rsp+3C0h+var_350]
0x14000b67e  lea     r9, [rbp+2C0h+pszMore]
0x14000b682  cmp     [rbp+2C0h+var_2C8], 8
0x14000b687  cmovnb  r9, [rbp+2C0h+pszMore]; pszMore
0x14000b68c  cmp     qword ptr [rbx+18h], 8
0x14000b691  jb      short loc_14000B698
0x14000b693  mov     r8, [rbx]
0x14000b696  jmp     short loc_14000B69B
0x14000b698  mov     r8, rbx; pszPathIn
0x14000b69b  mov     r12, [rsp+3C0h+pszPathOut]
0x14000b6a0  sub     rdx, r12
0x14000b6a3  sar     rdx, 1; cchPathOut
0x14000b6a6  mov     [rsp+3C0h+dwFlags], 1; dwFlags
0x14000b6ae  mov     rcx, r12; pszPathOut
0x14000b6b1  call    cs:__imp_PathCchCombineEx
0x14000b6b7  mov     edi, eax
0x14000b6b9  test    eax, eax
0x14000b6bb  js      loc_14000BC26
0x14000b6c1  xor     edx, edx; Val
0x14000b6c3  mov     r8d, 250h; Size
0x14000b6c9  lea     rcx, [rbp+2C0h+FindFileData]; void *
0x14000b6cd  call    memset_0
0x14000b6d2  lea     rdx, [rbp+2C0h+FindFileData]; lpFindFileData
0x14000b6d6  mov     rcx, r12; lpFileName
0x14000b6d9  call    cs:__imp_FindFirstFileW
0x14000b6df  mov     rdi, rax
0x14000b6e2  mov     [rbp+2C0h+var_310], rax
0x14000b6e6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x14000b6ea  jnz     short loc_14000B74E
0x14000b6ec  call    cs:__imp_GetLastError
0x14000b6f2  mov     r8d, eax
0x14000b6f5  cmp     eax, 2
0x14000b6f8  mov     eax, cs:dword_140017048
0x14000b6fe  jnz     loc_14000BB18
0x14000b704  cmp     eax, 4
0x14000b707  jbe     short loc_14000B725
0x14000b709  mov     [rsp+3C0h+var_380], r12
0x14000b70e  lea     rax, [rsp+3C0h+var_380]
0x14000b713  mov     qword ptr [rsp+3C0h+dwFlags], rax
0x14000b718  lea     rdx, unk_140013548
0x14000b71f  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000b724  nop
0x14000b725  test    r12, r12
0x14000b728  jz      short loc_14000B734
0x14000b72a  mov     rcx, r12
0x14000b72d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000b733  nop
0x14000b734  cmp     [rbp+2C0h+var_2C8], 8
0x14000b739  jb      loc_14000B98B
0x14000b73f  mov     rcx, [rbp+2C0h+pszMore]
0x14000b743  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000b749  jmp     loc_14000B98B
0x14000b74e  mov     eax, cs:dword_140017048
0x14000b754  cmp     eax, 5
0x14000b757  jbe     short loc_14000B787
0x14000b759  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x14000b75d  mov     [rsp+3C0h+var_380], rax
0x14000b762  mov     qword ptr [rsp+3C0h+var_378], r12
0x14000b767  lea     rax, [rsp+3C0h+var_380]
0x14000b76c  mov     [rsp+3C0h+var_398], rax
0x14000b771  lea     rax, [rsp+3C0h+var_378]
0x14000b776  mov     qword ptr [rsp+3C0h+dwFlags], rax; int
0x14000b77b  lea     rdx, word_1400134D2
0x14000b782  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x14000b787  mov     r9d, 104h
0x14000b78d  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x14000b791  cmp     [rax], r15w
0x14000b795  jz      short loc_14000B7A1
0x14000b797  add     rax, 2
0x14000b79b  sub     r9, 1
0x14000b79f  jnz     short loc_14000B791
0x14000b7a1  mov     rax, r9
0x14000b7a4  neg     rax
0x14000b7a7  sbb     r10d, r10d
0x14000b7aa  not     r10d
0x14000b7ad  and     r10d, 80070057h
0x14000b7b4  mov     r8, r9
0x14000b7b7  mov     rax, r9
0x14000b7ba  mov     ecx, 104h
0x14000b7bf  sub     rcx, r9
0x14000b7c2  neg     rax
0x14000b7c5  sbb     rdx, rdx
0x14000b7c8  and     rdx, rcx
0x14000b7cb  neg     r8
0x14000b7ce  sbb     r11, r11
0x14000b7d1  and     r11, rdx
0x14000b7d4  mov     rcx, [rbp+2C8h]; this
0x14000b7db  test    r9, r9
0x14000b7de  jz      loc_14000BC11
0x14000b7e4  xorps   xmm0, xmm0
0x14000b7e7  movdqu  xmmword ptr [rbp+2C0h+var_338], xmm0
0x14000b7ec  mov     rcx, r15
0x14000b7ef  mov     [rbp+2C0h+var_328], rcx
0x14000b7f3  mov     rdx, [rbx+10h]
0x14000b7f7  add     rdx, 6
0x14000b7fb  add     rdx, r11
0x14000b7fe  jz      short loc_14000B816
0x14000b800  cmp     rdx, r14
0x14000b803  ja      loc_14000BB7F
0x14000b809  lea     rcx, [rbp+2C0h+var_338]
0x14000b80d  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x14000b812  mov     rcx, [rbp+2C0h+var_328]
0x14000b816  cmp     qword ptr [rbx+18h], 8
0x14000b81b  jb      short loc_14000B822
0x14000b81d  mov     r8, [rbx]
0x14000b820  jmp     short loc_14000B825
0x14000b822  mov     r8, rbx; pszPathIn
0x14000b825  mov     r15, [rbp+2C0h+var_338]
0x14000b829  sub     rcx, r15
0x14000b82c  sar     rcx, 1
0x14000b82f  mov     [rsp+3C0h+dwFlags], 1; dwFlags
0x14000b837  lea     r9, [rbp+2C0h+FindFileData.cFileName]; pszMore
0x14000b83b  mov     rdx, rcx; cchPathOut
0x14000b83e  mov     rcx, r15; pszPathOut
0x14000b841  call    cs:__imp_PathCchCombineEx
0x14000b847  mov     r14d, eax
0x14000b84a  test    eax, eax
0x14000b84c  js      loc_14000BB85
0x14000b852  mov     ecx, 0A8h; Size
0x14000b857  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000b85c  mov     r14, rax
0x14000b85f  mov     [rsp+3C0h+var_370], rax
0x14000b864  xor     edx, edx
0x14000b866  test    rax, rax
0x14000b869  jz      loc_14000B90C
0x14000b86f  lea     rax, [rbp+2C0h+var_308]
0x14000b873  mov     qword ptr [rsp+3C0h+var_378], rax
0x14000b878  mov     [rbp+2C0h+var_2F0], 7
0x14000b880  mov     [rbp+2C0h+var_2F8], rdx
0x14000b884  mov     [rbp+2C0h+var_308], dx
0x14000b888  cmp     [r15], dx
0x14000b88c  jnz     short loc_14000B893
0x14000b88e  mov     r8d, edx
0x14000b891  jmp     short loc_14000B8A1
0x14000b893  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000b897  inc     r8
0x14000b89a  cmp     [r15+r8*2], dx
0x14000b89f  jnz     short loc_14000B897
0x14000b8a1  mov     rdx, r15; Src
0x14000b8a4  lea     rcx, [rbp+2C0h+var_308]; void *
0x14000b8a8  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000b8ad  nop
0x14000b8ae  mov     [rbp+2C0h+var_58], 7
0x14000b8b9  xor     ecx, ecx
0x14000b8bb  mov     [rbp+2C0h+var_60], rcx
0x14000b8c2  mov     [rbp+2C0h+var_70], cx
0x14000b8c9  cmp     [rbp+2C0h+FindFileData.cFileName], cx
0x14000b8cd  jnz     short loc_14000B8D4
0x14000b8cf  mov     r8d, ecx
0x14000b8d2  jmp     short loc_14000B8E6
0x14000b8d4  lea     rax, [rbp+2C0h+FindFileData.cFileName]
0x14000b8d8  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000b8dc  inc     r8
0x14000b8df  cmp     [rax+r8*2], cx
0x14000b8e4  jnz     short loc_14000B8DC
0x14000b8e6  lea     rdx, [rbp+2C0h+FindFileData.cFileName]; Src
0x14000b8ea  lea     rcx, [rbp+2C0h+var_70]; void *
0x14000b8f1  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000b8f6  nop
0x14000b8f7  lea     r8, [rbp+2C0h+var_308]
0x14000b8fb  lea     rdx, [rbp+2C0h+var_70]
0x14000b902  mov     rcx, r14
0x14000b905  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x14000b90a  jmp     short loc_14000B90F
0x14000b90c  mov     rax, rdx
  ... truncated ...
```
