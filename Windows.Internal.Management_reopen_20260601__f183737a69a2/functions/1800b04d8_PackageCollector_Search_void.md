# PackageCollector::Search(void)

- ea: `0x1800b04d8`
- end: `0x1800b0be2`
- name: `?Search@PackageCollector@@QEAA?AV?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@XZ`
- size: `1802`
- prototype: ``
- caller_count: `2`
- callee_count: `25`
- tags: `file_ops, reparse_path, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180073220`
- `0x180073540`

## callees

- `0x1800011d4`
- `0x180001350`
- `0x180001424`
- `0x180001a7c`
- `0x180002cdc`
- `0x180003884`
- `0x180004570`
- `0x180004eb0`
- `0x18000539c`
- `0x180005a74`
- `0x18000868c`
- `0x18000d50c`
- `0x1800131a8`
- `0x180017094`
- `0x180036d2c`
- `0x18003973c`
- `0x180039a14`
- `0x18003a394`
- `0x18003e5d4`
- `0x1800449f0`
- `0x180090758`
- `0x18009f988`
- `0x1800afcf0`
- `0x1800b04d8`
- `0x1800b1c5c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b05fd`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b05fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0724`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800b0724`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b070b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x1800b070b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b0552`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b0574`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b0552`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1800b0574`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b08a9`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x1800b08a9`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b05d6`
- `api-ms-win-core-path-l1-1-0!PathCchFindExtension` at `0x1800b05d6`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800b06db`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800b0828`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800b06db`
- `api-ms-win-core-path-l1-1-0!PathCchCombineEx` at `0x1800b0828`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b0595`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindFileNameW` at `0x1800b0595`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
      if ( (unsigned int)dword_1800FE488 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FE488, 0) )
      {
        v38 = std::wstring::c_str(v3);
        v39 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v61, v38);
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
          v40,
          (unsigned int)&dword_1800EE1AC,
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
        if ( (unsigned int)dword_1800FE488 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FE488, 0) )
        {
          LODWORD(cFileName) = v17;
          v33 = std::vector<unsigned short>::data(pszPathOut);
          v34 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v61, v33);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&dword_1800FE488,
            (unsigned int)&byte_1800EE0C7,
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
          if ( (unsigned int)dword_1800FE488 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FE488, 0) )
          {
            LODWORD(cFileName) = v48;
            v49 = std::vector<unsigned short>::data(pszPathOut);
            v50 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(
                    &v61,
                    v49);
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
              (unsigned int)&dword_1800FE488,
              (unsigned int)&word_1800EE136,
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
        if ( (unsigned int)dword_1800FE488 > 4 )
        {
          cFileName = (unsigned __int64)pszPathOut[0];
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
            v24,
            (unsigned int)&dword_1800EE104,
            LastError,
            (_DWORD)v25,
            (__int64)&cFileName);
        }
      }
      else
      {
        do
        {
          if ( (unsigned int)dword_1800FE488 > 5 )
          {
            cFileName = (unsigned __int64)FindFileData.cFileName;
            *(PWSTR *)v60 = pszPathOut[0];
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
              v18,
              (unsigned int)&unk_1800EE170,
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
            if ( (unsigned int)dword_1800FE488 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FE488, 0) )
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
                (unsigned int)&word_1800EE04E,
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
        if ( (unsigned int)dword_1800FE488 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800FE488, 0x400000000000LL) )
        {
          LODWORD(cFileName) = -2147024809;
          wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v61, FileNameW);
          v43 = std::wstring::c_str(v3);
          v44 = wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(&v67, v43);
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
            (unsigned int)&cFileName,
            (unsigned int)byte_1800EE1CD,
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
  if ( (unsigned int)dword_1800FE488 > 5 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_1800FE488,
      byte_1800EE09D,
      0);
  return a2;
}

```

## disassembly

```asm
0x1800b04d8  mov     [rsp-8+arg_10], rbx
0x1800b04dd  mov     [rsp-8+arg_18], rsi
0x1800b04e2  push    rbp
0x1800b04e3  push    rdi
0x1800b04e4  push    r12
0x1800b04e6  push    r14
0x1800b04e8  push    r15
0x1800b04ea  lea     rbp, [rsp-280h]
0x1800b04f2  sub     rsp, 380h
0x1800b04f9  mov     rax, cs:__security_cookie
0x1800b0500  xor     rax, rsp
0x1800b0503  mov     [rbp+2A0h+var_30], rax
0x1800b050a  mov     r15, rdx
0x1800b050d  mov     [rbp+2A0h+var_2F0], rdx
0x1800b0511  mov     [rsp+3A0h+var_348], 0
0x1800b0519  mov     qword ptr [rdx], 0
0x1800b0520  mov     qword ptr [rdx+8], 0
0x1800b0528  mov     qword ptr [rdx+10h], 0
0x1800b0530  mov     [rsp+3A0h+var_348], 1
0x1800b0538  mov     r14, [rcx+8]
0x1800b053c  mov     r12, [rcx+10h]
0x1800b0540  jmp     loc_1800B08DF
0x1800b0545  mov     rcx, r14
0x1800b0548  cmp     qword ptr [r14+18h], 7
0x1800b054d  jbe     short loc_1800B0552
0x1800b054f  mov     rcx, [r14]; lpFileName
0x1800b0552  call    cs:__imp_GetFileAttributesW
0x1800b0559  nop     dword ptr [rax+rax+00h]
0x1800b055e  cmp     eax, 0FFFFFFFFh
0x1800b0561  jz      loc_1800B09B5
0x1800b0567  mov     rcx, r14
0x1800b056a  cmp     qword ptr [r14+18h], 7
0x1800b056f  jbe     short loc_1800B0574
0x1800b0571  mov     rcx, [r14]; lpFileName
0x1800b0574  call    cs:__imp_GetFileAttributesW
0x1800b057b  nop     dword ptr [rax+rax+00h]
0x1800b0580  test    al, 10h
0x1800b0582  jnz     loc_1800B066C
0x1800b0588  mov     rcx, r14
0x1800b058b  cmp     qword ptr [r14+18h], 7
0x1800b0590  jbe     short loc_1800B0595
0x1800b0592  mov     rcx, [r14]; pszPath
0x1800b0595  call    cs:__imp_PathFindFileNameW
0x1800b059c  nop     dword ptr [rax+rax+00h]
0x1800b05a1  mov     rsi, rax
0x1800b05a4  mov     rcx, [rbp+2A8h]; this
0x1800b05ab  test    rax, rax
0x1800b05ae  jz      loc_1800B0ABD
0x1800b05b4  mov     [rsp+3A0h+ppszExt], 0
0x1800b05bd  mov     rdx, [r14+10h]
0x1800b05c1  inc     rdx; cchPath
0x1800b05c4  mov     rcx, r14
0x1800b05c7  cmp     qword ptr [r14+18h], 7
0x1800b05cc  jbe     short loc_1800B05D1
0x1800b05ce  mov     rcx, [r14]; pszPath
0x1800b05d1  lea     r8, [rsp+3A0h+ppszExt]; ppszExt
0x1800b05d6  call    cs:__imp_PathCchFindExtension
0x1800b05dd  nop     dword ptr [rax+rax+00h]
0x1800b05e2  mov     rcx, [rbp+2A8h]; this
0x1800b05e9  test    eax, eax
0x1800b05eb  js      loc_1800B0AA8
0x1800b05f1  lea     rdx, aPpkg_0; ".ppkg"
0x1800b05f8  mov     rcx, [rsp+3A0h+ppszExt]
0x1800b05fd  call    cs:__imp__o__wcsicmp
0x1800b0604  nop     dword ptr [rax+rax+00h]
0x1800b0609  test    eax, eax
0x1800b060b  jnz     loc_1800B0A11
0x1800b0611  mov     ecx, 0A8h; Size
0x1800b0616  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b061b  mov     rdi, rax
0x1800b061e  mov     [rbp+2A0h+var_318], rax
0x1800b0622  lea     rax, [rbp+2A0h+var_310]
0x1800b0626  mov     [rbp+2A0h+var_320], rax
0x1800b062a  mov     rdx, r14
0x1800b062d  lea     rcx, [rbp+2A0h+var_310]
0x1800b0631  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z; std::wstring::wstring(std::wstring const &)
0x1800b0636  mov     rbx, rax
0x1800b0639  mov     rdx, rsi
0x1800b063c  lea     rcx, [rbp+2A0h+var_2E8]
0x1800b0640  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b0645  nop
0x1800b0646  mov     r8, rbx
0x1800b0649  mov     rdx, rax
0x1800b064c  mov     rcx, rdi
0x1800b064f  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x1800b0654  nop
0x1800b0655  mov     [rsp+3A0h+var_360], rax
0x1800b065a  lea     rdx, [rsp+3A0h+var_360]
0x1800b065f  mov     rcx, r15
0x1800b0662  call    ??$emplace_back@PEAVProvPackage@@@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@1@$$QEAPEAVProvPackage@@@Z; std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(ProvPackage * &&)
0x1800b0667  jmp     loc_1800B08DB
0x1800b066c  lea     rdx, aPpkg; "*.ppkg"
0x1800b0673  lea     rcx, [rbp+2A0h+pszMore]
0x1800b0677  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b067c  nop
0x1800b067d  xorps   xmm0, xmm0
0x1800b0680  movdqu  xmmword ptr [rsp+3A0h+pszPathOut], xmm0
0x1800b0686  mov     [rsp+3A0h+var_330], 0
0x1800b068f  mov     rdx, [r14+10h]
0x1800b0693  mov     rax, [rbp+2A0h+var_298]
0x1800b0697  add     rax, 6
0x1800b069b  add     rdx, rax
0x1800b069e  lea     rcx, [rsp+3A0h+pszPathOut]
0x1800b06a3  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x1800b06a8  lea     r9, [rbp+2A0h+pszMore]
0x1800b06ac  cmp     [rbp+2A0h+var_290], 7
0x1800b06b1  cmova   r9, [rbp+2A0h+pszMore]; pszMore
0x1800b06b6  mov     r8, r14
0x1800b06b9  cmp     qword ptr [r14+18h], 7
0x1800b06be  jbe     short loc_1800B06C3
0x1800b06c0  mov     r8, [r14]; pszPathIn
0x1800b06c3  mov     rcx, [rsp+3A0h+pszPathOut]; pszPathOut
0x1800b06c8  mov     rdx, [rsp+3A0h+var_330]
0x1800b06cd  sub     rdx, rcx
0x1800b06d0  sar     rdx, 1; cchPathOut
0x1800b06d3  mov     [rsp+3A0h+dwFlags], 1; dwFlags
0x1800b06db  call    cs:__imp_PathCchCombineEx
0x1800b06e2  nop     dword ptr [rax+rax+00h]
0x1800b06e7  mov     ebx, eax
0x1800b06e9  test    eax, eax
0x1800b06eb  js      loc_1800B0938
0x1800b06f1  xor     edx, edx; Val
0x1800b06f3  mov     r8d, 250h; Size
0x1800b06f9  lea     rcx, [rbp+2A0h+FindFileData]; void *
0x1800b06fd  call    memset_0
0x1800b0702  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x1800b0706  mov     rcx, [rsp+3A0h+pszPathOut]; lpFileName
0x1800b070b  call    cs:__imp_FindFirstFileW
0x1800b0712  nop     dword ptr [rax+rax+00h]
0x1800b0717  mov     rbx, rax
0x1800b071a  mov     [rbp+2A0h+var_320], rax
0x1800b071e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800b0722  jnz     short loc_1800B0770
0x1800b0724  call    cs:__imp_GetLastError
0x1800b072b  nop     dword ptr [rax+rax+00h]
0x1800b0730  mov     r8d, eax
0x1800b0733  cmp     eax, 2
0x1800b0736  mov     eax, cs:dword_1800FE488
0x1800b073c  jnz     loc_1800B0AD5
0x1800b0742  cmp     eax, 4
0x1800b0745  jbe     loc_1800B08BD
0x1800b074b  mov     rax, [rsp+3A0h+pszPathOut]
0x1800b0750  mov     [rsp+3A0h+var_360], rax
0x1800b0755  lea     rax, [rsp+3A0h+var_360]
0x1800b075a  mov     qword ptr [rsp+3A0h+dwFlags], rax
0x1800b075f  lea     rdx, dword_1800EE104
0x1800b0766  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x1800b076b  jmp     loc_1800B08BD
0x1800b0770  mov     eax, cs:dword_1800FE488
0x1800b0776  cmp     eax, 5
0x1800b0779  jbe     short loc_1800B07AE
0x1800b077b  lea     rax, [rbp+2A0h+FindFileData.cFileName]
0x1800b077f  mov     [rsp+3A0h+var_360], rax
0x1800b0784  mov     rax, [rsp+3A0h+pszPathOut]
0x1800b0789  mov     qword ptr [rsp+3A0h+var_358], rax
0x1800b078e  lea     rax, [rsp+3A0h+var_360]
0x1800b0793  mov     [rsp+3A0h+var_378], rax
0x1800b0798  lea     rax, [rsp+3A0h+var_358]
0x1800b079d  mov     qword ptr [rsp+3A0h+dwFlags], rax; int
0x1800b07a2  lea     rdx, unk_1800EE170
0x1800b07a9  call    ??$Write@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x1800b07ae  mov     [rsp+3A0h+var_360], 0
0x1800b07b7  lea     r8, [rsp+3A0h+var_360]; unsigned __int64 *
0x1800b07bc  mov     edx, 104h; unsigned __int64
0x1800b07c1  lea     rcx, [rbp+2A0h+FindFileData.cFileName]; unsigned __int16 *
0x1800b07c5  call    ?StringCchLengthW@@YAJPEBG_KPEA_K@Z; StringCchLengthW(ushort const *,unsigned __int64,unsigned __int64 *)
0x1800b07ca  mov     rcx, [rbp+2A8h]; this
0x1800b07d1  test    eax, eax
0x1800b07d3  js      loc_1800B0BCD
0x1800b07d9  xorps   xmm0, xmm0
0x1800b07dc  movdqu  xmmword ptr [rbp+2A0h+var_310], xmm0
0x1800b07e1  mov     [rbp+2A0h+var_300], 0
0x1800b07e9  mov     rdx, [rsp+3A0h+var_360]
0x1800b07ee  add     rdx, 6
0x1800b07f2  add     rdx, [r14+10h]
0x1800b07f6  lea     rcx, [rbp+2A0h+var_310]
0x1800b07fa  call    ?reserve@?$vector@GV?$allocator@G@std@@@std@@QEAAX_K@Z; std::vector<ushort>::reserve(unsigned __int64)
0x1800b07ff  cmp     qword ptr [r14+18h], 7
0x1800b0804  jbe     short loc_1800B080B
0x1800b0806  mov     r8, [r14]
0x1800b0809  jmp     short loc_1800B080E
0x1800b080b  mov     r8, r14; pszPathIn
0x1800b080e  mov     rcx, [rbp+2A0h+var_310]; pszPathOut
0x1800b0812  mov     rdx, [rbp+2A0h+var_300]
0x1800b0816  sub     rdx, rcx
0x1800b0819  sar     rdx, 1; cchPathOut
0x1800b081c  mov     [rsp+3A0h+dwFlags], 1; int
0x1800b0824  lea     r9, [rbp+2A0h+FindFileData.cFileName]; pszMore
0x1800b0828  call    cs:__imp_PathCchCombineEx
0x1800b082f  nop     dword ptr [rax+rax+00h]
0x1800b0834  mov     edi, eax
0x1800b0836  test    eax, eax
0x1800b0838  js      loc_1800B0B43
0x1800b083e  mov     ecx, 0A8h; Size
0x1800b0843  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800b0848  mov     rsi, rax
0x1800b084b  mov     [rsp+3A0h+var_350], rax
0x1800b0850  lea     rax, [rbp+2A0h+var_2E8]
0x1800b0854  mov     qword ptr [rsp+3A0h+var_358], rax
0x1800b0859  mov     rdx, [rbp+2A0h+var_310]
0x1800b085d  lea     rcx, [rbp+2A0h+var_2E8]
0x1800b0861  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b0866  mov     rdi, rax
0x1800b0869  lea     rdx, [rbp+2A0h+FindFileData.cFileName]
0x1800b086d  lea     rcx, [rbp+2A0h+var_2C8]
0x1800b0871  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@QEBG@Z; std::wstring::wstring(ushort const * const)
0x1800b0876  nop
0x1800b0877  mov     r8, rdi
0x1800b087a  mov     rdx, rax
0x1800b087d  mov     rcx, rsi
0x1800b0880  call    ??0ProvPackage@@QEAA@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@0@Z; ProvPackage::ProvPackage(std::wstring,std::wstring)
0x1800b0885  nop
0x1800b0886  mov     qword ptr [rsp+3A0h+var_358], rax
0x1800b088b  lea     rdx, [rsp+3A0h+var_358]
0x1800b0890  mov     rcx, r15
0x1800b0893  call    ??$emplace_back@PEAVProvPackage@@@?$vector@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@V?$allocator@V?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@std@@@2@@std@@QEAAAEAV?$unique_ptr@VProvPackage@@U?$default_delete@VProvPackage@@@std@@@1@$$QEAPEAVProvPackage@@@Z; std::vector<std::unique_ptr<ProvPackage>>::emplace_back<ProvPackage *>(ProvPackage * &&)
0x1800b0898  nop
0x1800b0899  lea     rcx, [rbp+2A0h+var_310]
0x1800b089d  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b08a2  lea     rdx, [rbp+2A0h+FindFileData]; lpFindFileData
0x1800b08a6  mov     rcx, rbx; hFindFile
0x1800b08a9  call    cs:__imp_FindNextFileW
0x1800b08b0  nop     dword ptr [rax+rax+00h]
0x1800b08b5  test    eax, eax
0x1800b08b7  jnz     loc_1800B0770
0x1800b08bd  lea     rcx, [rbp+2A0h+var_320]
0x1800b08c1  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?FindClose@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&FindClose(void *)>>(void)
0x1800b08c6  nop
0x1800b08c7  lea     rcx, [rsp+3A0h+pszPathOut]
0x1800b08cc  call    ?_Tidy@?$vector@GV?$allocator@G@std@@@std@@AEAAXXZ; std::vector<ushort>::_Tidy(void)
0x1800b08d1  nop
0x1800b08d2  lea     rcx, [rbp+2A0h+pszMore]
0x1800b08d6  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x1800b08db  add     r14, 20h ; ' '
0x1800b08df  cmp     r14, r12
0x1800b08e2  jnz     loc_1800B0545
0x1800b08e8  mov     ecx, cs:dword_1800FE488
0x1800b08ee  cmp     ecx, 5
0x1800b08f1  jbe     short loc_1800B0909
0x1800b08f3  xor     r8d, r8d
0x1800b08f6  lea     rdx, byte_1800EE09D
0x1800b08fd  lea     rcx, dword_1800FE488
0x1800b0904  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800b0909  mov     rax, r15
0x1800b090c  mov     rcx, [rbp+2A0h+var_30]
0x1800b0913  xor     rcx, rsp; StackCookie
0x1800b0916  call    __security_check_cookie
0x1800b091b  lea     r11, [rsp+3A0h+var_20]
0x1800b0923  mov     rbx, [r11+40h]
0x1800b0927  mov     rsi, [r11+48h]
0x1800b092b  mov     rsp, r11
0x1800b092e  pop     r15
0x1800b0930  pop     r14
0x1800b0932  pop     r12
0x1800b0934  pop     rdi
0x1800b0935  pop     rbp
0x1800b0936  retn
0x1800b0938  mov     eax, cs:dword_1800FE488
0x1800b093e  cmp     eax, 2
0x1800b0941  jbe     short loc_1800B0992
0x1800b0943  xor     edx, edx
0x1800b0945  lea     rcx, dword_1800FE488
0x1800b094c  call    _tlgKeywordOn
0x1800b0951  test    al, al
0x1800b0953  jz      short loc_1800B0992
0x1800b0955  mov     dword ptr [rsp+3A0h+var_360], ebx
0x1800b0959  lea     rcx, [rsp+3A0h+pszPathOut]
0x1800b095e  call    ?data@?$vector@GV?$allocator@G@std@@@std@@QEAAPEAGXZ; std::vector<ushort>::data(void)
0x1800b0963  mov     rdx, rax
0x1800b0966  lea     rcx, [rsp+3A0h+var_350]
0x1800b096b  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b0970  lea     rcx, [rsp+3A0h+var_360]
0x1800b0975  mov     [rsp+3A0h+var_378], rcx
0x1800b097a  mov     qword ptr [rsp+3A0h+dwFlags], rax; int
0x1800b097f  lea     rdx, byte_1800EE0C7
0x1800b0986  lea     rcx, dword_1800FE488
0x1800b098d  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800b0992  mov     ecx, ebx
0x1800b0994  call    ??$verify_hresult@J@wil@@YAJJ@Z; wil::verify_hresult<long>(long)
0x1800b0999  mov     r9d, eax; char *
0x1800b099c  mov     rcx, [rbp+2A8h]; this
0x1800b09a3  lea     r8, aOnecoreuapAdmi_33; "onecoreuap\\admin\\prov\\lib\\packageco"...
0x1800b09aa  mov     edx, 0E6h; void *
0x1800b09af  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800b09b5  mov     eax, cs:dword_1800FE488
0x1800b09bb  cmp     eax, 2
0x1800b09be  jbe     short loc_1800B09F8
0x1800b09c0  xor     edx, edx
0x1800b09c2  lea     rcx, dword_1800FE488
0x1800b09c9  call    _tlgKeywordOn
0x1800b09ce  test    al, al
0x1800b09d0  jz      short loc_1800B09F8
0x1800b09d2  mov     rcx, r14
0x1800b09d5  call    ?c_str@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAPEBGXZ; std::wstring::c_str(void)
0x1800b09da  mov     rdx, rax
0x1800b09dd  lea     rcx, [rsp+3A0h+var_350]
0x1800b09e2  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x1800b09e7  mov     qword ptr [rsp+3A0h+dwFlags], rax
0x1800b09ec  lea     rdx, dword_1800EE1AC
0x1800b09f3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
  ... truncated ...
```
