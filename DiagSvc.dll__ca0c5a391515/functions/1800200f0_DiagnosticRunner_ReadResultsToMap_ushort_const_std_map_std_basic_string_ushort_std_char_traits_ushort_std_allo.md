# DiagnosticRunner::ReadResultsToMap(ushort const *,std::map<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::less<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>,std::allocator<std::pair<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>>> *)

- ea: `0x1800200f0`
- end: `0x180020931`
- name: `?ReadResultsToMap@DiagnosticRunner@@UEAAJPEBGPEAV?$map@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@U?$less@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@V?$allocator@U?$pair@$$CBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V12@@std@@@2@@std@@@Z`
- size: `2113`
- prototype: `int __fastcall(__int64, const unsigned __int16 *, __int64)`
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x180001720`
- `0x180001e7c`
- `0x180001fec`
- `0x18000216c`
- `0x1800031e4`
- `0x180003538`
- `0x180003fc0`
- `0x180004b78`
- `0x18000517c`
- `0x1800112d0`
- `0x18001cd68`
- `0x1800200f0`
- `0x180025350`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020779`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020779`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002076b`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18002076b`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180020237`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFileExistsW` at `0x180020237`

## string_xrefs

- `0x18002018a`: `DiagnosticRunner::ReadResultsToMap`
- `0x180020870`: `DiagnosticRunner::ReadResultsToMap`
- `0x180020163`: `result.xml`
- `0x1800201c9`: `About to read a file`
- `0x18002031b`: `Xml load fail`
- `0x1800205fa`: `Read key/value`
- `0x1800207bc`: `File delete fail`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
int __fastcall DiagnosticRunner::ReadResultsToMap(__int64 a1, const unsigned __int16 *a2, __int64 a3)
{
  int v3; // r12d
  unsigned __int64 v7; // rdx
  int result; // eax
  unsigned __int64 v9; // rdx
  __int64 v10; // rdx
  __int64 v11; // rcx
  __int64 v12; // r8
  int v13; // ebx
  int v14; // ecx
  int v15; // r8d
  int v16; // r9d
  __int64 v17; // rdx
  __int64 v18; // rcx
  __int64 v19; // r8
  int v20; // ecx
  int v21; // r8d
  int v22; // r9d
  __int64 v23; // rdx
  signed int v24; // ebx
  __int64 v25; // r8
  int v26; // r8d
  int v27; // r9d
  struct IXMLDOMDocument2 *v28; // rdi
  HRESULT (__stdcall *selectNodes)(IXMLDOMDocument2 *, BSTR, IXMLDOMNodeList **); // rbx
  __int64 v30; // rdx
  __int64 v31; // rcx
  __int64 v32; // r8
  int v33; // ecx
  int v34; // r8d
  int v35; // r9d
  __int64 v36; // rdi
  __int64 (__fastcall *v37)(__int64, _QWORD, const char **); // rbx
  const char *v38; // rdi
  __int64 (__fastcall *v39)(const char *, const char **); // rbx
  __int64 v40; // rdx
  __int64 v41; // rcx
  __int64 v42; // r8
  const char *v43; // rdi
  __int64 (__fastcall *v44)(const char *, const OLECHAR *, const char **); // rbx
  int v45; // r8d
  int v46; // r9d
  __int64 v47; // rdx
  __int64 v48; // rcx
  __int64 v49; // r8
  int v50; // ecx
  int v51; // r8d
  int v52; // r9d
  signed int LastError; // eax
  __int64 v54; // rdx
  __int64 v55; // rcx
  __int64 v56; // r8
  int v57; // ecx
  int v58; // r8d
  int v59; // r9d
  int v60; // ecx
  int v61; // r8d
  int v62; // r9d
  int v63; // [rsp+80h] [rbp-80h] BYREF
  int v64; // [rsp+84h] [rbp-7Ch] BYREF
  BOOL v65; // [rsp+88h] [rbp-78h] BYREF
  const char *v66; // [rsp+90h] [rbp-70h] BYREF
  const char *v67; // [rsp+98h] [rbp-68h] BYREF
  __int64 v68; // [rsp+A0h] [rbp-60h] BYREF
  const char *v69; // [rsp+A8h] [rbp-58h] BYREF
  const char *v70; // [rsp+B0h] [rbp-50h] BYREF
  WCHAR *v71; // [rsp+B8h] [rbp-48h] BYREF
  int v72; // [rsp+C0h] [rbp-40h] BYREF
  __int64 v73; // [rsp+C8h] [rbp-38h] BYREF
  const char *v74; // [rsp+D0h] [rbp-30h] BYREF
  const char *v75; // [rsp+D8h] [rbp-28h] BYREF
  const char *v76; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v77; // [rsp+E8h] [rbp-18h] BYREF
  __int64 v78; // [rsp+F0h] [rbp-10h] BYREF
  struct IXMLDOMDocument2 *v79; // [rsp+F8h] [rbp-8h] BYREF
  WCHAR *v80; // [rsp+100h] [rbp+0h] BYREF
  const char *v81; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v82[2]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v83[16]; // [rsp+120h] [rbp+20h] BYREF
  WCHAR pszPath[264]; // [rsp+130h] [rbp+30h] BYREF

  v3 = 0;
  if ( a2 && a3 )
  {
    memset_0(pszPath, 0, 0x208u);
    result = StringCchCatW(pszPath, v7, a2);
    if ( result >= 0 )
    {
      result = StringCchCatW(pszPath, v9, L"result.xml");
      v13 = result;
      if ( result >= 0 )
      {
        if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v11, v10, v12) )
        {
          v63 = 654;
          v71 = pszPath;
          v67 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
          v70 = (const char *)(a1 + 64);
          v69 = "About to read a file";
          v68 = a1 + 193;
          v66 = "DiagnosticRunner::ReadResultsToMap";
          v64 = v13;
          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
            v14,
            (unsigned int)&unk_180032068,
            v15,
            v16,
            (__int64)&v68,
            (__int64)&v64,
            (__int64)&v69,
            (__int64)&v66,
            (__int64)&v67,
            (__int64)&v63,
            (__int64)&v70,
            (__int64)&v71);
        }
        if ( PathFileExistsW(pszPath) )
        {
          v79 = 0;
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v79);
          v24 = SdpXmlLoad(pszPath, &v79);
          if ( v24 >= 0 )
          {
            v28 = v79;
            v78 = 0;
            v72 = 0;
            selectNodes = v79->lpVtbl->selectNodes;
            Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v78);
            v24 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, const wchar_t *, __int64 *))selectNodes)(
                    v28,
                    L"/Objects/Object/Property",
                    &v78);
            if ( !v24 )
            {
              v24 = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v78 + 64LL))(v78, &v72);
              if ( !v24 )
              {
                if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v31, v30, v32) )
                {
                  v64 = v72;
                  v71 = (WCHAR *)(a1 + 64);
                  v66 = "Property node count";
                  v68 = a1 + 193;
                  v63 = 697;
                  v70 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
                  v67 = "DiagnosticRunner::ReadResultsToMap";
                  v65 = 0;
                  _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
                    v33,
                    (unsigned int)&dword_180031EFC,
                    v34,
                    v35,
                    (__int64)&v68,
                    (__int64)&v65,
                    (__int64)&v66,
                    (__int64)&v67,
                    (__int64)&v70,
                    (__int64)&v63,
                    (__int64)&v71,
                    (__int64)&v64);
                }
                v69 = 0;
                if ( v72 > 0 )
                {
                  do
                  {
                    v36 = v78;
                    v37 = *(__int64 (__fastcall **)(__int64, _QWORD, const char **))(*(_QWORD *)v78 + 56LL);
                    Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v69);
                    v24 = v37(v36, (unsigned int)v3, &v69);
                    if ( !v24 )
                    {
                      v38 = v69;
                      v70 = 0;
                      v71 = 0;
                      v67 = 0;
                      v66 = 0;
                      v39 = *(__int64 (__fastcall **)(const char *, const char **))(*(_QWORD *)v69 + 136LL);
                      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v67);
                      v24 = v39(v38, &v67);
                      if ( !v24 )
                      {
                        v43 = v67;
                        v44 = *(__int64 (__fastcall **)(const char *, const OLECHAR *, const char **))(*(_QWORD *)v67 + 56LL);
                        Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v66);
                        v24 = v44(v43, L"Name", &v66);
                        if ( !v24 )
                        {
                          v24 = (*(__int64 (__fastcall **)(const char *, const char **))(*(_QWORD *)v66 + 208LL))(
                                  v66,
                                  &v70);
                          if ( !v24 )
                            v24 = (*(__int64 (__fastcall **)(const char *, WCHAR **))(*(_QWORD *)v69 + 208LL))(
                                    v69,
                                    &v71);
                        }
                      }
                      if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v41, v40, v42) )
                      {
                        v80 = v71;
                        v81 = v70;
                        v65 = v71 != 0;
                        v63 = 732;
                        v74 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
                        v75 = "DiagnosticRunner::ReadResultsToMap";
                        v64 = v70 != 0;
                        v73 = a1 + 64;
                        v76 = "Read key/value";
                        v77 = a1 + 193;
                        LODWORD(v68) = v24;
                        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
                          (_DWORD)v70,
                          (unsigned int)byte_180031E69,
                          v45,
                          v46,
                          (__int64)&v77,
                          (__int64)&v68,
                          (__int64)&v76,
                          (__int64)&v75,
                          (__int64)&v74,
                          (__int64)&v63,
                          (__int64)&v73,
                          (__int64)&v81,
                          (__int64)&v80,
                          (__int64)&v64,
                          (__int64)&v65);
                      }
                      if ( !v24 )
                      {
                        v82[0] = v70;
                        v82[1] = v71;
                        std::_Tree<std::_Tmap_traits<std::wstring,std::wstring,std::less<std::wstring>,std::allocator<std::pair<std::wstring const,std::wstring>>,0>>::_Emplace<std::pair<unsigned short *,unsigned short *>>(
                          a3,
                          v83,
                          v82);
                        if ( !v83[8]
                          && (unsigned int)dword_180039000 > 5
                          && (unsigned __int8)tlgKeywordOn(v48, v47, v49) )
                        {
                          LODWORD(v68) = 743;
                          v77 = a1 + 64;
                          v76 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
                          v74 = "Duplicate key";
                          v73 = a1 + 193;
                          v75 = "DiagnosticRunner::ReadResultsToMap";
                          v65 = 0;
                          _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                            v50,
                            (unsigned int)&word_180031DF6,
                            v51,
                            v52,
                            (__int64)&v73,
                            (__int64)&v65,
                            (__int64)&v74,
                            (__int64)&v75,
                            (__int64)&v76,
                            (__int64)&v68,
                            (__int64)&v77);
                        }
                      }
                      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v66);
                      Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v67);
                    }
                    ++v3;
                  }
                  while ( v3 < v72 );
                }
                Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v69);
              }
            }
            if ( !DeleteFileW(pszPath) )
            {
              LastError = GetLastError();
              v24 = LastError;
              if ( LastError > 0 )
                v24 = (unsigned __int16)LastError | 0x80070000;
              if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(v55, v54, v56) )
              {
                LODWORD(v68) = 757;
                v77 = a1 + 64;
                v76 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
                v74 = "File delete fail";
                v73 = a1 + 193;
                v75 = "DiagnosticRunner::ReadResultsToMap";
                v65 = v24;
                _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                  v57,
                  (unsigned int)byte_180031D83,
                  v58,
                  v59,
                  (__int64)&v73,
                  (__int64)&v65,
                  (__int64)&v74,
                  (__int64)&v75,
                  (__int64)&v76,
                  (__int64)&v68,
                  (__int64)&v77);
              }
            }
            Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v78);
          }
          else if ( (unsigned int)dword_180039000 > 5
                 && (unsigned __int8)tlgKeywordOn((unsigned int)dword_180039000, v23, v25) )
          {
            v64 = 676;
            v66 = "Xml load fail";
            v71 = (WCHAR *)(a1 + 64);
            v69 = (const char *)(a1 + 193);
            v70 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
            v67 = "DiagnosticRunner::ReadResultsToMap";
            v63 = v24;
            _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
              a1 + 64,
              (unsigned int)word_180031F82,
              v26,
              v27,
              (__int64)&v69,
              (__int64)&v63,
              (__int64)&v66,
              (__int64)&v67,
              (__int64)&v70,
              (__int64)&v64,
              (__int64)&v71);
          }
          Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(&v79);
          return v24;
        }
        else
        {
          if ( (unsigned int)dword_180039000 > 5 )
          {
            if ( (unsigned __int8)tlgKeywordOn(v18, v17, v19) )
            {
              v64 = 663;
              v71 = (WCHAR *)(a1 + 64);
              v70 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
              v66 = "File not found";
              v69 = (const char *)(a1 + 193);
              v67 = "DiagnosticRunner::ReadResultsToMap";
              v63 = v13;
              _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(
                v20,
                (unsigned int)byte_180031FF5,
                v21,
                v22,
                (__int64)&v69,
                (__int64)&v63,
                (__int64)&v66,
                (__int64)&v67,
                (__int64)&v70,
                (__int64)&v64,
                (__int64)&v71);
            }
          }
          return 0;
        }
      }
    }
  }
  else
  {
    if ( (unsigned int)dword_180039000 > 5 && (unsigned __int8)tlgKeywordOn(a1, a2, a3) )
    {
      v64 = 630;
      v63 = -2147024809;
      v76 = "onecoreuap\\base\\diagnosis\\pdi\\diagsvc\\engine\\diagnosticrunner\\lib\\diagnosticrunner.cpp";
      LODWORD(v68) = a3 == 0;
      v75 = "DiagnosticRunner::ReadResultsToMap";
      v65 = a2 == 0;
      v77 = a1 + 64;
      v74 = "Invalid arg";
      v73 = a1 + 193;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v60,
        (unsigned int)byte_1800320E5,
        v61,
        v62,
        (__int64)&v73,
        (__int64)&v63,
        (__int64)&v74,
        (__int64)&v75,
        (__int64)&v76,
        (__int64)&v64,
        (__int64)&v77,
        (__int64)&v65,
        (__int64)&v68);
    }
    return -2147024809;
  }
  return result;
}

```

## disassembly

```asm
0x1800200f0  mov     [rsp-8+arg_0], rbx
0x1800200f5  push    rbp
0x1800200f6  push    rsi
0x1800200f7  push    rdi
0x1800200f8  push    r12
0x1800200fa  push    r13
0x1800200fc  push    r14
0x1800200fe  push    r15
0x180020100  lea     rbp, [rsp-250h]
0x180020108  sub     rsp, 350h
0x18002010f  mov     rax, cs:__security_cookie
0x180020116  xor     rax, rsp
0x180020119  mov     [rbp+280h+var_40], rax
0x180020120  xor     r12d, r12d
0x180020123  mov     r13, r8
0x180020126  mov     rbx, rdx
0x180020129  mov     rsi, rcx
0x18002012c  test    rdx, rdx
0x18002012f  jz      loc_18002082F
0x180020135  test    r8, r8
0x180020138  jz      loc_18002082F
0x18002013e  xor     edx, edx; Val
0x180020140  lea     rcx, [rbp+280h+pszPath]; void *
0x180020144  mov     r8d, 208h; Size
0x18002014a  call    memset_0
0x18002014f  mov     r8, rbx; unsigned __int16 *
0x180020152  lea     rcx, [rbp+280h+pszPath]; unsigned __int16 *
0x180020156  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x18002015b  test    eax, eax
0x18002015d  js      loc_180020907
0x180020163  lea     r8, aResultXml; "result.xml"
0x18002016a  lea     rcx, [rbp+280h+pszPath]; unsigned __int16 *
0x18002016e  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180020173  mov     ebx, eax
0x180020175  test    eax, eax
0x180020177  js      loc_180020907
0x18002017d  mov     eax, cs:dword_180039000
0x180020183  lea     r14, aOnecoreuapBase_0; "onecoreuap\\base\\diagnosis\\pdi\\diags"...
0x18002018a  lea     r15, aDiagnosticrunn_5; "DiagnosticRunner::ReadResultsToMap"
0x180020191  cmp     eax, 5
0x180020194  jbe     loc_180020233
0x18002019a  call    _tlgKeywordOn
0x18002019f  test    al, al
0x1800201a1  jz      loc_180020233
0x1800201a7  lea     rax, [rbp+280h+pszPath]
0x1800201ab  mov     [rbp+280h+var_300], 28Eh
0x1800201b2  mov     [rbp+280h+var_2C8], rax
0x1800201b6  lea     rdx, unk_180032068
0x1800201bd  lea     rax, [rsi+40h]
0x1800201c1  mov     [rbp+280h+var_2E8], r14
0x1800201c5  mov     [rbp+280h+var_2D0], rax
0x1800201c9  lea     rax, aAboutToReadAFi; "About to read a file"
0x1800201d0  mov     [rbp+280h+var_2D8], rax
0x1800201d4  lea     rax, [rsi+0C1h]
0x1800201db  mov     [rbp+280h+var_2E0], rax
0x1800201df  lea     rax, [rbp+280h+var_2C8]
0x1800201e3  mov     [rsp+380h+var_328], rax
0x1800201e8  lea     rax, [rbp+280h+var_2D0]
0x1800201ec  mov     [rsp+380h+var_330], rax
0x1800201f1  lea     rax, [rbp+280h+var_300]
0x1800201f5  mov     [rsp+380h+var_338], rax
0x1800201fa  lea     rax, [rbp+280h+var_2E8]
0x1800201fe  mov     [rsp+380h+var_340], rax
0x180020203  lea     rax, [rbp+280h+var_2F0]
0x180020207  mov     [rsp+380h+var_348], rax
0x18002020c  lea     rax, [rbp+280h+var_2D8]
0x180020210  mov     [rsp+380h+var_350], rax
0x180020215  lea     rax, [rbp+280h+var_2FC]
0x180020219  mov     [rsp+380h+var_358], rax
0x18002021e  lea     rax, [rbp+280h+var_2E0]
0x180020222  mov     [rsp+380h+var_360], rax
0x180020227  mov     [rbp+280h+var_2F0], r15
0x18002022b  mov     [rbp+280h+var_2FC], ebx
0x18002022e  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180020233  lea     rcx, [rbp+280h+pszPath]; pszPath
0x180020237  call    cs:__imp_PathFileExistsW
0x18002023d  test    eax, eax
0x18002023f  jnz     loc_1800202DF
0x180020245  mov     eax, cs:dword_180039000
0x18002024b  cmp     eax, 5
0x18002024e  jbe     loc_1800202D8
0x180020254  call    _tlgKeywordOn
0x180020259  test    al, al
0x18002025b  jz      short loc_1800202D8
0x18002025d  lea     rax, [rsi+40h]
0x180020261  mov     [rbp+280h+var_2FC], 297h
0x180020268  mov     [rbp+280h+var_2C8], rax
0x18002026c  lea     rdx, byte_180031FF5
0x180020273  lea     rax, aFileNotFound; "File not found"
0x18002027a  mov     [rbp+280h+var_2D0], r14
0x18002027e  mov     [rbp+280h+var_2F0], rax
0x180020282  lea     rax, [rsi+0C1h]
0x180020289  mov     [rbp+280h+var_2D8], rax
0x18002028d  lea     rax, [rbp+280h+var_2C8]
0x180020291  mov     [rsp+380h+var_330], rax
0x180020296  lea     rax, [rbp+280h+var_2FC]
0x18002029a  mov     [rsp+380h+var_338], rax
0x18002029f  lea     rax, [rbp+280h+var_2D0]
0x1800202a3  mov     [rsp+380h+var_340], rax
0x1800202a8  lea     rax, [rbp+280h+var_2E8]
0x1800202ac  mov     [rsp+380h+var_348], rax
0x1800202b1  lea     rax, [rbp+280h+var_2F0]
0x1800202b5  mov     [rsp+380h+var_350], rax
0x1800202ba  lea     rax, [rbp+280h+var_300]
0x1800202be  mov     [rsp+380h+var_358], rax
0x1800202c3  lea     rax, [rbp+280h+var_2D8]
0x1800202c7  mov     [rsp+380h+var_360], rax
0x1800202cc  mov     [rbp+280h+var_2E8], r15
0x1800202d0  mov     [rbp+280h+var_300], ebx
0x1800202d3  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x1800202d8  xor     eax, eax
0x1800202da  jmp     loc_180020907
0x1800202df  lea     rcx, [rbp+280h+var_288]
0x1800202e3  mov     [rbp+280h+var_288], r12
0x1800202e7  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800202ec  lea     rdx, [rbp+280h+var_288]; struct IXMLDOMDocument2 **
0x1800202f0  lea     rcx, [rbp+280h+pszPath]; psz
0x1800202f4  call    ?SdpXmlLoad@@YAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; SdpXmlLoad(ushort const *,IXMLDOMDocument2 * *)
0x1800202f9  mov     ebx, eax
0x1800202fb  test    eax, eax
0x1800202fd  jns     loc_1800203A6
0x180020303  mov     ecx, cs:dword_180039000
0x180020309  cmp     ecx, 5
0x18002030c  jbe     loc_180020396
0x180020312  call    _tlgKeywordOn
0x180020317  test    al, al
0x180020319  jz      short loc_180020396
0x18002031b  lea     rax, aXmlLoadFail; "Xml load fail"
0x180020322  mov     [rbp+280h+var_2FC], 2A4h
0x180020329  mov     [rbp+280h+var_2F0], rax
0x18002032d  lea     rcx, [rsi+40h]
0x180020331  lea     rax, [rsi+0C1h]
0x180020338  mov     [rbp+280h+var_2C8], rcx
0x18002033c  mov     [rbp+280h+var_2D8], rax
0x180020340  lea     rdx, word_180031F82
0x180020347  lea     rax, [rbp+280h+var_2C8]
0x18002034b  mov     [rbp+280h+var_2D0], r14
0x18002034f  mov     [rsp+380h+var_330], rax
0x180020354  lea     rax, [rbp+280h+var_2FC]
0x180020358  mov     [rsp+380h+var_338], rax
0x18002035d  lea     rax, [rbp+280h+var_2D0]
0x180020361  mov     [rsp+380h+var_340], rax
0x180020366  lea     rax, [rbp+280h+var_2E8]
0x18002036a  mov     [rsp+380h+var_348], rax
0x18002036f  lea     rax, [rbp+280h+var_2F0]
0x180020373  mov     [rsp+380h+var_350], rax
0x180020378  lea     rax, [rbp+280h+var_300]
0x18002037c  mov     [rsp+380h+var_358], rax
0x180020381  lea     rax, [rbp+280h+var_2D8]
0x180020385  mov     [rsp+380h+var_360], rax
0x18002038a  mov     [rbp+280h+var_2E8], r15
0x18002038e  mov     [rbp+280h+var_300], ebx
0x180020391  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@33343@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &)
0x180020396  lea     rcx, [rbp+280h+var_288]
0x18002039a  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18002039f  mov     eax, ebx
0x1800203a1  jmp     loc_180020907
0x1800203a6  mov     rdi, [rbp+280h+var_288]
0x1800203aa  lea     rcx, [rbp+280h+var_290]
0x1800203ae  mov     [rbp+280h+var_290], r12
0x1800203b2  mov     [rbp+280h+var_2C0], r12d
0x1800203b6  mov     rax, [rdi]
0x1800203b9  mov     rbx, [rax+120h]
0x1800203c0  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800203c5  lea     r8, [rbp+280h+var_290]
0x1800203c9  mov     rcx, rdi
0x1800203cc  lea     rdx, aObjectsObjectP; "/Objects/Object/Property"
0x1800203d3  mov     rax, rbx
0x1800203d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203db  mov     ebx, eax
0x1800203dd  test    eax, eax
0x1800203df  jnz     loc_180020767
0x1800203e5  mov     rcx, [rbp+280h+var_290]
0x1800203e9  lea     rdx, [rbp+280h+var_2C0]
0x1800203ed  mov     rax, [rcx]
0x1800203f0  mov     rax, [rax+40h]
0x1800203f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800203f9  mov     ebx, eax
0x1800203fb  test    eax, eax
0x1800203fd  jnz     loc_180020767
0x180020403  mov     eax, cs:dword_180039000
0x180020409  cmp     eax, 5
0x18002040c  jbe     loc_1800204AA
0x180020412  call    _tlgKeywordOn
0x180020417  test    al, al
0x180020419  jz      loc_1800204AA
0x18002041f  mov     eax, [rbp+280h+var_2C0]
0x180020422  lea     rdx, dword_180031EFC
0x180020429  mov     [rbp+280h+var_2FC], eax
0x18002042c  lea     rax, [rsi+40h]
0x180020430  mov     [rbp+280h+var_2C8], rax
0x180020434  lea     rax, aPropertyNodeCo; "Property node count"
0x18002043b  mov     [rbp+280h+var_2F0], rax
0x18002043f  lea     rax, [rsi+0C1h]
0x180020446  mov     [rbp+280h+var_2E0], rax
0x18002044a  lea     rax, [rbp+280h+var_2FC]
0x18002044e  mov     [rsp+380h+var_328], rax
0x180020453  lea     rax, [rbp+280h+var_2C8]
0x180020457  mov     [rsp+380h+var_330], rax
0x18002045c  lea     rax, [rbp+280h+var_300]
0x180020460  mov     [rsp+380h+var_338], rax
0x180020465  lea     rax, [rbp+280h+var_2D0]
0x180020469  mov     [rsp+380h+var_340], rax
0x18002046e  lea     rax, [rbp+280h+var_2E8]
0x180020472  mov     [rsp+380h+var_348], rax
0x180020477  lea     rax, [rbp+280h+var_2F0]
0x18002047b  mov     [rsp+380h+var_350], rax
0x180020480  lea     rax, [rbp+280h+var_2F8]
0x180020484  mov     [rsp+380h+var_358], rax
0x180020489  lea     rax, [rbp+280h+var_2E0]
0x18002048d  mov     [rsp+380h+var_360], rax
0x180020492  mov     [rbp+280h+var_300], 2B9h
0x180020499  mov     [rbp+280h+var_2D0], r14
0x18002049d  mov     [rbp+280h+var_2E8], r15
0x1800204a1  mov     [rbp+280h+var_2F8], r12d
0x1800204a5  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U1@U2@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@333434@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x1800204aa  mov     [rbp+280h+var_2D8], r12
0x1800204ae  cmp     [rbp+280h+var_2C0], r12d
0x1800204b2  jle     loc_18002075E
0x1800204b8  mov     rdi, [rbp+280h+var_290]
0x1800204bc  lea     rcx, [rbp+280h+var_2D8]
0x1800204c0  mov     rax, [rdi]
0x1800204c3  mov     rbx, [rax+38h]
0x1800204c7  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x1800204cc  lea     r8, [rbp+280h+var_2D8]
0x1800204d0  mov     edx, r12d
0x1800204d3  mov     rcx, rdi
0x1800204d6  mov     rax, rbx
0x1800204d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800204de  mov     ebx, eax
0x1800204e0  test    eax, eax
0x1800204e2  jnz     loc_180020751
0x1800204e8  mov     rdi, [rbp+280h+var_2D8]
0x1800204ec  lea     rcx, [rbp+280h+var_2E8]
0x1800204f0  mov     [rbp+280h+var_2D0], 0
0x1800204f8  mov     [rbp+280h+var_2C8], 0
0x180020500  mov     [rbp+280h+var_2E8], 0
0x180020508  mov     [rbp+280h+var_2F0], 0
0x180020510  mov     rax, [rdi]
0x180020513  mov     rbx, [rax+88h]
0x18002051a  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x18002051f  lea     rdx, [rbp+280h+var_2E8]
0x180020523  mov     rcx, rdi
0x180020526  mov     rax, rbx
0x180020529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002052e  mov     ebx, eax
0x180020530  test    eax, eax
0x180020532  jnz     short loc_18002059A
0x180020534  mov     rdi, [rbp+280h+var_2E8]
0x180020538  lea     rcx, [rbp+280h+var_2F0]
0x18002053c  mov     rax, [rdi]
0x18002053f  mov     rbx, [rax+38h]
0x180020543  call    ?InternalRelease@?$ComPtr@UIHttpMediaTypeHeaderValueFactory@Headers@Http@Web@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Web::Http::Headers::IHttpMediaTypeHeaderValueFactory>::InternalRelease(void)
0x180020548  lea     r8, [rbp+280h+var_2F0]
0x18002054c  mov     rcx, rdi
0x18002054f  lea     rdx, aName; "Name"
0x180020556  mov     rax, rbx
0x180020559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002055e  mov     ebx, eax
0x180020560  test    eax, eax
0x180020562  jnz     short loc_18002059A
0x180020564  mov     rcx, [rbp+280h+var_2F0]
0x180020568  lea     rdx, [rbp+280h+var_2D0]
0x18002056c  mov     rax, [rcx]
0x18002056f  mov     rax, [rax+0D0h]
0x180020576  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002057b  mov     ebx, eax
0x18002057d  test    eax, eax
0x18002057f  jnz     short loc_18002059A
0x180020581  mov     rcx, [rbp+280h+var_2D8]
0x180020585  lea     rdx, [rbp+280h+var_2C8]
0x180020589  mov     rax, [rcx]
0x18002058c  mov     rax, [rax+0D0h]
0x180020593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020598  mov     ebx, eax
0x18002059a  mov     eax, cs:dword_180039000
0x1800205a0  cmp     eax, 5
0x1800205a3  jbe     loc_18002067B
0x1800205a9  call    _tlgKeywordOn
0x1800205ae  test    al, al
0x1800205b0  jz      loc_18002067B
0x1800205b6  mov     rdx, [rbp+280h+var_2C8]
0x1800205ba  xor     eax, eax
0x1800205bc  mov     rcx, [rbp+280h+var_2D0]
0x1800205c0  test    rdx, rdx
0x1800205c3  mov     [rbp+280h+var_280], rdx
0x1800205c7  lea     rdx, byte_180031E69
0x1800205ce  setnz   al
0x1800205d1  mov     [rbp+280h+var_278], rcx
0x1800205d5  mov     [rbp+280h+var_2F8], eax
0x1800205d8  xor     eax, eax
0x1800205da  test    rcx, rcx
0x1800205dd  mov     [rbp+280h+var_300], 2DCh
0x1800205e4  mov     [rbp+280h+var_2B0], r14
0x1800205e8  setnz   al
0x1800205eb  mov     [rbp+280h+var_2A8], r15
0x1800205ef  mov     [rbp+280h+var_2FC], eax
0x1800205f2  lea     rax, [rsi+40h]
0x1800205f6  mov     [rbp+280h+var_2B8], rax
0x1800205fa  lea     rax, aReadKeyValue; "Read key/value"
  ... truncated ...
```
