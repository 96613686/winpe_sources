# COpenSearchRowset::_OpenUrlRequest(ushort const *,ulong,OPENSEARCH_REQUEST_TYPE,void * *)

- ea: `0x1800451b0`
- end: `0x1800453e7`
- name: `?_OpenUrlRequest@COpenSearchRowset@@AEAAJPEBGKW4OPENSEARCH_REQUEST_TYPE@@PEAPEAX@Z`
- size: `567`
- prototype: `__int64 __fastcall(__int64, __int64, DWORD, int, _QWORD *)`
- caller_count: `2`
- callee_count: `9`
- tags: `reparse_path, registry_config, broker_com_uri`

## callers

- `0x180044d50`
- `0x180046b78`

## callees

- `0x1800054b0`
- `0x180005c88`
- `0x180006900`
- `0x18000eec0`
- `0x1800129f8`
- `0x18002fa14`
- `0x18004362c`
- `0x1800451b0`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_GetAcceptLanguagesW` at `0x180045328`
- `SHLWAPI!__imp_GetAcceptLanguagesW` at `0x180045328`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453b4`
- `OLEAUT32!__imp_SysFreeString` at `0x1800453b4`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180045216`
- `ext-ms-win-core-iuri-l1-1-0!CreateUri` at `0x180045216`
- `WININET!HttpOpenRequestW` at `0x1800452ef`
- `WININET!HttpOpenRequestW` at `0x1800452ef`
- `WININET!InternetSetOptionW` at `0x18004538c`
- `WININET!InternetSetOptionW` at `0x18004538c`
- `WININET!InternetCloseHandle` at `0x1800453a9`
- `WININET!InternetCloseHandle` at `0x1800453a9`
- `WININET!HttpAddRequestHeadersW` at `0x18004536c`
- `WININET!HttpAddRequestHeadersW` at `0x18004536c`

## string_xrefs

- `0x1800452ad`: `text/xml`

## pseudocode

```c
__int64 __fastcall COpenSearchRowset::_OpenUrlRequest(__int64 a1, __int64 a2, DWORD a3, int a4, _QWORD *a5)
{
  IUri **v8; // rax
  LPCWSTR v9; // r10
  int Uri; // ebx
  HINTERNET v11; // rax
  void *v12; // rdi
  __int64 v13; // r8
  int v15; // [rsp+40h] [rbp-C0h] BYREF
  __int64 *v16; // [rsp+48h] [rbp-B8h] BYREF
  DWORD pcchLanguages; // [rsp+50h] [rbp-B0h] BYREF
  int Buffer; // [rsp+54h] [rbp-ACh] BYREF
  LPCWSTR lpszObjectName; // [rsp+58h] [rbp-A8h] BYREF
  LPCWSTR lpszAcceptTypes[2]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR szHeaders[104]; // [rsp+70h] [rbp-90h] BYREF
  WCHAR pszLanguages[80]; // [rsp+140h] [rbp+40h] BYREF

  *a5 = 0;
  ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(&v16);
  v8 = (IUri **)ATL::CComPtrBase<IXMLDOMDocument>::operator&(&v16);
  Uri = CreateUri(v9, 4u, 0, v8);
  if ( Uri >= 0 )
  {
    v15 = 0;
    Uri = (*(__int64 (__fastcall **)(__int64 *, int *))(*v16 + 192))(v16, &v15);
    if ( Uri >= 0 )
    {
      if ( v15 != 2 && v15 != 11 )
      {
        Uri = -2147024846;
        goto LABEL_25;
      }
      Uri = COpenSearchRowset::_EnsureInternetConnection(a1, v16, a4);
      if ( Uri < 0 )
        goto LABEL_25;
      lpszObjectName = 0;
      Uri = (*(__int64 (__fastcall **)(__int64 *, LPCWSTR *))(*v16 + 128))(v16, &lpszObjectName);
      if ( Uri >= 0 )
      {
        lpszAcceptTypes[0] = L"text/xml";
        lpszAcceptTypes[1] = 0;
        if ( v15 == 11 )
          a3 |= 0x800000u;
        v11 = HttpOpenRequestW(*(HINTERNET *)(a1 + 96), L"GET", lpszObjectName, 0, 0, lpszAcceptTypes, a3, 0);
        v12 = v11;
        if ( a4 == 1 || v11 )
        {
          Uri = 0;
          goto LABEL_14;
        }
        Uri = ResultFromKnownLastError();
        if ( Uri >= 0 )
        {
LABEL_14:
          pcchLanguages = 80;
          if ( !GetAcceptLanguagesW(pszLanguages, &pcchLanguages)
            && StringCchPrintfW(szHeaders, 0x66u, L"Accept-Language: %s\r\n", pszLanguages) >= 0 )
          {
            v13 = -1;
            do
              ++v13;
            while ( szHeaders[v13] );
            HttpAddRequestHeadersW(v12, szHeaders, v13, 0);
          }
          Buffer = 4;
          if ( !InternetSetOptionW(v12, 0x55u, &Buffer, 4u) )
            Uri = ResultFromKnownLastError();
          if ( Uri < 0 )
            InternetCloseHandle(v12);
          else
            *a5 = v12;
        }
      }
      SysFreeString((BSTR)lpszObjectName);
    }
  }
LABEL_25:
  ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&v16);
  return (unsigned int)Uri;
}

```

## disassembly

```asm
0x1800451b0  push    rbp
0x1800451b2  push    rbx
0x1800451b3  push    rsi
0x1800451b4  push    rdi
0x1800451b5  push    r12
0x1800451b7  push    r14
0x1800451b9  push    r15
0x1800451bb  lea     rbp, [rsp-0F0h]
0x1800451c3  sub     rsp, 1F0h
0x1800451ca  mov     rax, cs:__security_cookie
0x1800451d1  xor     rax, rsp
0x1800451d4  mov     [rbp+120h+var_40], rax
0x1800451db  mov     r15, [rbp+120h+arg_20]
0x1800451e2  mov     rsi, rcx
0x1800451e5  xor     r12d, r12d
0x1800451e8  lea     rcx, [rsp+220h+var_1D8]; void *
0x1800451ed  mov     r14d, r9d
0x1800451f0  mov     edi, r8d
0x1800451f3  mov     r10, rdx
0x1800451f6  mov     [r15], r12
0x1800451f9  call    ??0?$CComPtr@UIWDSConfigFactory@@@ATL@@QEAA@XZ; ATL::CComPtr<IWDSConfigFactory>::CComPtr<IWDSConfigFactory>(void)
0x1800451fe  lea     rcx, [rsp+220h+var_1D8]
0x180045203  call    ??I?$CComPtrBase@UIXMLDOMDocument@@@ATL@@QEAAPEAPEAUIXMLDOMDocument@@XZ; ATL::CComPtrBase<IXMLDOMDocument>::operator&(void)
0x180045208  mov     r9, rax; ppURI
0x18004520b  lea     edx, [r12+4]; dwFlags
0x180045210  xor     r8d, r8d; dwReserved
0x180045213  mov     rcx, r10; pwzURI
0x180045216  call    cs:__imp_CreateUri
0x18004521c  mov     ebx, eax
0x18004521e  test    eax, eax
0x180045220  js      loc_1800453BA
0x180045226  mov     rcx, [rsp+220h+var_1D8]
0x18004522b  lea     rdx, [rsp+220h+var_1E0]
0x180045230  mov     [rsp+220h+var_1E0], r12d
0x180045235  mov     rax, [rcx]
0x180045238  mov     rax, [rax+0C0h]
0x18004523f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045244  mov     ebx, eax
0x180045246  test    eax, eax
0x180045248  js      loc_1800453BA
0x18004524e  cmp     [rsp+220h+var_1E0], 2
0x180045253  jz      short loc_180045266
0x180045255  cmp     [rsp+220h+var_1E0], 0Bh
0x18004525a  jz      short loc_180045266
0x18004525c  mov     ebx, 80070032h
0x180045261  jmp     loc_1800453BA
0x180045266  mov     rdx, [rsp+220h+var_1D8]
0x18004526b  mov     r8d, r14d
0x18004526e  mov     rcx, rsi
0x180045271  call    ?_EnsureInternetConnection@COpenSearchRowset@@AEAAJPEAUIUri@@W4OPENSEARCH_REQUEST_TYPE@@@Z; COpenSearchRowset::_EnsureInternetConnection(IUri *,OPENSEARCH_REQUEST_TYPE)
0x180045276  mov     ebx, eax
0x180045278  test    eax, eax
0x18004527a  js      loc_1800453BA
0x180045280  mov     rcx, [rsp+220h+var_1D8]
0x180045285  lea     rdx, [rsp+220h+lpszObjectName]
0x18004528a  mov     [rsp+220h+lpszObjectName], r12
0x18004528f  mov     rax, [rcx]
0x180045292  mov     rax, [rax+80h]
0x180045299  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004529e  mov     ebx, eax
0x1800452a0  test    eax, eax
0x1800452a2  js      loc_1800453AF
0x1800452a8  cmp     [rsp+220h+var_1E0], 0Bh
0x1800452ad  lea     rax, aTextXml; "text/xml"
0x1800452b4  mov     [rsp+220h+lpszAcceptTypes], rax
0x1800452b9  mov     [rsp+220h+var_1B8], r12
0x1800452be  jnz     short loc_1800452C4
0x1800452c0  bts     edi, 17h
0x1800452c4  mov     r8, [rsp+220h+lpszObjectName]; lpszObjectName
0x1800452c9  lea     rax, [rsp+220h+lpszAcceptTypes]
0x1800452ce  mov     rcx, [rsi+60h]; hConnect
0x1800452d2  lea     rdx, szVerb; "GET"
0x1800452d9  mov     [rsp+220h+dwContext], r12; dwContext
0x1800452de  xor     r9d, r9d; lpszVersion
0x1800452e1  mov     [rsp+220h+dwFlags], edi; dwFlags
0x1800452e5  mov     [rsp+220h+lplpszAcceptTypes], rax; lplpszAcceptTypes
0x1800452ea  mov     [rsp+220h+lpszReferrer], r12; lpszReferrer
0x1800452ef  call    cs:__imp_HttpOpenRequestW
0x1800452f5  mov     rdi, rax
0x1800452f8  cmp     r14d, 1
0x1800452fc  jnz     short loc_180045303
0x1800452fe  mov     ebx, r12d
0x180045301  jmp     short loc_180045317
0x180045303  test    rdi, rdi
0x180045306  jnz     short loc_1800452FE
0x180045308  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004530d  mov     ebx, eax
0x18004530f  test    eax, eax
0x180045311  js      loc_1800453AF
0x180045317  lea     rdx, [rsp+220h+pcchLanguages]; pcchLanguages
0x18004531c  mov     [rsp+220h+pcchLanguages], 50h ; 'P'
0x180045324  lea     rcx, [rbp+120h+pszLanguages]; pszLanguages
0x180045328  call    cs:__imp_GetAcceptLanguagesW
0x18004532e  test    eax, eax
0x180045330  jnz     short loc_180045372
0x180045332  lea     r9, [rbp+120h+pszLanguages]
0x180045336  lea     r8, aAcceptLanguage; "Accept-Language: %s\r\n"
0x18004533d  lea     edx, [rax+66h]; unsigned __int64
0x180045340  lea     rcx, [rsp+220h+szHeaders]; unsigned __int16 *
0x180045345  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004534a  test    eax, eax
0x18004534c  js      short loc_180045372
0x18004534e  lea     rax, [rsp+220h+szHeaders]
0x180045353  or      r8, 0FFFFFFFFFFFFFFFFh
0x180045357  inc     r8; dwHeadersLength
0x18004535a  cmp     [rax+r8*2], r12w
0x18004535f  jnz     short loc_180045357
0x180045361  xor     r9d, r9d; dwModifiers
0x180045364  lea     rdx, [rsp+220h+szHeaders]; lpszHeaders
0x180045369  mov     rcx, rdi; hRequest
0x18004536c  call    cs:__imp_HttpAddRequestHeadersW
0x180045372  mov     r9d, 4; dwBufferLength
0x180045378  mov     [rsp+220h+Buffer], 4
0x180045380  lea     r8, [rsp+220h+Buffer]; lpBuffer
0x180045385  mov     rcx, rdi; hInternet
0x180045388  lea     edx, [r9+51h]; dwOption
0x18004538c  call    cs:__imp_InternetSetOptionW
0x180045392  test    eax, eax
0x180045394  jnz     short loc_18004539D
0x180045396  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18004539b  mov     ebx, eax
0x18004539d  test    ebx, ebx
0x18004539f  js      short loc_1800453A6
0x1800453a1  mov     [r15], rdi
0x1800453a4  jmp     short loc_1800453AF
0x1800453a6  mov     rcx, rdi; hInternet
0x1800453a9  call    cs:__imp_InternetCloseHandle
0x1800453af  mov     rcx, [rsp+220h+lpszObjectName]; bstrString
0x1800453b4  call    cs:__imp_SysFreeString
0x1800453ba  lea     rcx, [rsp+220h+var_1D8]
0x1800453bf  call    ??1?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(void)
0x1800453c4  mov     eax, ebx
0x1800453c6  mov     rcx, [rbp+120h+var_40]
0x1800453cd  xor     rcx, rsp; StackCookie
0x1800453d0  call    __security_check_cookie
0x1800453d5  add     rsp, 1F0h
0x1800453dc  pop     r15
0x1800453de  pop     r14
0x1800453e0  pop     r12
0x1800453e2  pop     rdi
0x1800453e3  pop     rsi
0x1800453e4  pop     rbx
0x1800453e5  pop     rbp
0x1800453e6  retn
```
