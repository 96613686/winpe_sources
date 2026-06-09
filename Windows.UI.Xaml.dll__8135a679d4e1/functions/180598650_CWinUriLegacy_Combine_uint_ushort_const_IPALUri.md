# CWinUriLegacy::Combine(uint,ushort const *,IPALUri * *)

- ea: `0x180598650`
- end: `0x180598bb9`
- name: `?Combine@CWinUriLegacy@@UEAAJIPEBGPEAPEAUIPALUri@@@Z`
- size: `1385`
- prototype: `HRESULT __fastcall(CWinUriLegacy *this, unsigned int cUri, const wchar_t *pUri, IPALUri **ppUriCombine)`
- caller_count: `1`
- callee_count: `26`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180728880`

## callees

- `0x180004bc0`
- `0x18001c368`
- `0x180090304`
- `0x1800913b4`
- `0x1800d2490`
- `0x18017d850`
- `0x1801800b8`
- `0x180194584`
- `0x1801e2980`
- `0x1801eb6f4`
- `0x18020a400`
- `0x1803096c4`
- `0x180315988`
- `0x1804e7328`
- `0x180598650`
- `0x180598cdc`
- `0x18063a8dc`
- `0x180687a78`
- `0x180688828`
- `0x1806c06e8`
- `0x18076e110`
- `0x18076e990`
- `0x18076f08c`
- `0x18098ffb8`
- `0x180990bc4`
- `0x180c010f0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1805986fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059879e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1805987f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059887f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1805986fd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059879e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1805987f6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18059887f`
- `WININET!InternetCombineUrlW` at `0x180598794`
- `WININET!InternetCombineUrlW` at `0x1805987ec`
- `WININET!InternetCombineUrlW` at `0x180598875`
- `WININET!InternetCombineUrlW` at `0x180598794`
- `WININET!InternetCombineUrlW` at `0x1805987ec`
- `WININET!InternetCombineUrlW` at `0x180598875`
- `WININET!InternetCreateUrlW` at `0x1805986f3`
- `WININET!InternetCreateUrlW` at `0x1805986f3`

## pseudocode

```c
__int64 __fastcall CWinUriLegacy::Combine(
        CWinUriLegacy *this,
        unsigned int cUri,
        const wchar_t *pUri,
        CWinUriLegacy **ppUriCombine)
{
  int v4; // r14d
  __int64 v5; // rsi
  CWinUriLegacy *v9; // rdi
  HRESULT v10; // ecx
  HRESULT v11; // ebx
  HRESULT v12; // ecx
  signed int LastError; // eax
  signed int v14; // eax
  unsigned int v15; // edx
  signed int v16; // eax
  HRESULT HealthyUrl; // eax
  unsigned int v18; // edx
  signed int v19; // eax
  const xstring_ptr_view *v20; // rax
  const xstring_ptr_view *v21; // rax
  HRESULT v22; // eax
  const xstring_ptr_view *v23; // rax
  const xstring_ptr_view *v24; // rax
  unsigned int v25; // eax
  int v26; // r9d
  HRESULT appended; // eax
  const xstring_ptr_view *v28; // rax
  xstring_ptr_view *v29; // rax
  bool bIsFileUri; // [rsp+30h] [rbp-D0h] BYREF
  bool isMsResourceUri; // [rsp+31h] [rbp-CFh] BYREF
  unsigned int cCombine; // [rsp+34h] [rbp-CCh] BYREF
  unsigned int cHealthyUrl; // [rsp+38h] [rbp-C8h] BYREF
  unsigned int cBase; // [rsp+3Ch] [rbp-C4h] BYREF
  CWinUriLegacy *pTempUri; // [rsp+40h] [rbp-C0h] BYREF
  xephemeral_string_ptr strFilePath; // [rsp+48h] [rbp-B8h] BYREF
  xephemeral_string_ptr v38; // [rsp+60h] [rbp-A0h] BYREF
  xephemeral_string_ptr v39; // [rsp+74h] [rbp-8Ch] BYREF
  TStringBuilder<96> adjustedFilePathBuilder; // [rsp+90h] [rbp-70h] BYREF
  wchar_t strCombine[2088]; // [rsp+170h] [rbp+70h] BYREF
  WCHAR strRelative[2088]; // [rsp+11C0h] [rbp+10C0h] BYREF
  wchar_t strBase[2088]; // [rsp+2210h] [rbp+2110h] BYREF
  wchar_t strHealthyUrl[2088]; // [rsp+3260h] [rbp+3160h] BYREF

  v4 = 0;
  v5 = cUri;
  cBase = 0;
  cCombine = 0;
  isMsResourceUri = 0;
  bIsFileUri = 0;
  v9 = 0;
  pTempUri = 0;
  if ( ppUriCombine )
  {
    if ( xfindchar(pUri, cUri, 0x5Cu) != -1 )
    {
      v11 = -2147483630;
      OnFailure_957_(v10);
      return (unsigned int)v11;
    }
    cBase = 2085;
    if ( !InternetCreateUrlW(&this->m_uc, 0, strBase, &cBase) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      OnNewFailure_3049_(v11);
      return (unsigned int)v11;
    }
    if ( (unsigned int)(v5 + 1) > 0x825 )
    {
      v11 = -2147467259;
      OnFailure_977_(v12);
      return (unsigned int)v11;
    }
    if ( (_DWORD)v5 )
      memcpy_0(strRelative, pUri, 2 * v5);
    if ( (unsigned __int64)(2 * v5) >= 0x104A )
      _report_rangecheckfailure();
    strRelative[v5] = 0;
    cCombine = 2085;
    if ( !InternetCombineUrlW(strBase, strRelative, strCombine, &cCombine, 0x28000000u) )
    {
      v14 = GetLastError();
      v11 = v14;
      if ( v14 > 0 )
        v11 = (unsigned __int16)v14 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
LABEL_20:
      OnNewFailure_3049_(v11);
      return (unsigned int)v11;
    }
    cCombine = 2085;
    if ( !InternetCombineUrlW(strBase, strRelative, strCombine, &cCombine, 0x20000000u) )
    {
      v16 = GetLastError();
      v11 = v16;
      if ( v16 > 0 )
        v11 = (unsigned __int16)v16 | 0x80070000;
      if ( v11 >= 0 )
        v11 = -2147467259;
      goto LABEL_20;
    }
    HealthyUrl = UriSchemeEquals(strCombine, v15, L"file", 4u, &bIsFileUri);
    v11 = HealthyUrl;
    if ( HealthyUrl < 0 )
      goto LABEL_57;
    if ( bIsFileUri )
    {
      cCombine = 2085;
      if ( !InternetCombineUrlW(strBase, strRelative, strCombine, &cCombine, 0x30000000u) )
      {
        v19 = GetLastError();
        v11 = v19;
        if ( v19 > 0 )
          v11 = (unsigned __int16)v19 | 0x80070000;
        if ( v11 >= 0 )
          v11 = -2147467259;
        OnNewFailure_3049_(v11);
        return (unsigned int)v11;
      }
    }
    HealthyUrl = UriSchemeEquals(strCombine, v18, L"ms-resource", 0xBu, &isMsResourceUri);
    v11 = HealthyUrl;
    if ( HealthyUrl < 0 )
      goto LABEL_57;
    if ( isMsResourceUri )
    {
      xephemeral_string_ptr::xephemeral_string_ptr(&strFilePath, this->m_uc.lpszUrlPath, this->m_uc.dwUrlPathLength);
      xephemeral_string_ptr::xephemeral_string_ptr(&v39, L"/Files/", 7u);
      if ( xstring_ptr_view::StartsWith(&strFilePath.xstring_ptr_view, v20, xstrCompareCaseInsensitive)
        || (xephemeral_string_ptr::xephemeral_string_ptr(&v38, L"Files/", 6u),
            xstring_ptr_view::StartsWith(&strFilePath.xstring_ptr_view, v21, xstrCompareCaseInsensitive)) )
      {
        if ( (_DWORD)v5 && *pUri != 47 )
          v4 = 1;
      }
    }
    cHealthyUrl = 2085;
    HealthyUrl = CWinUriLegacy::GetHealthyUrl(cCombine, strCombine, &cHealthyUrl, strHealthyUrl);
    v11 = HealthyUrl;
    if ( HealthyUrl < 0 )
    {
LABEL_57:
      OnFailure_2990_(HealthyUrl);
      return (unsigned int)v11;
    }
    v22 = CWinUriLegacy::Create(0, cHealthyUrl, strHealthyUrl, &pTempUri);
    v11 = v22;
    if ( v22 < 0 )
    {
      OnFailure_2990_(v22);
      v9 = pTempUri;
    }
    else
    {
      v9 = pTempUri;
      if ( !v4 )
        goto LABEL_54;
      xephemeral_string_ptr::xephemeral_string_ptr(
        &strFilePath,
        pTempUri->m_uc.lpszUrlPath,
        pTempUri->m_uc.dwUrlPathLength);
      xephemeral_string_ptr::xephemeral_string_ptr(&v38, L"/Files/", 7u);
      if ( xstring_ptr_view::StartsWith(&strFilePath.xstring_ptr_view, v23, xstrCompareCaseInsensitive) )
        goto LABEL_54;
      xephemeral_string_ptr::xephemeral_string_ptr(&v39, L"Files/", 6u);
      if ( xstring_ptr_view::StartsWith(&strFilePath.xstring_ptr_view, v24, xstrCompareCaseInsensitive) )
        goto LABEL_54;
      adjustedFilePathBuilder.m_hPreallocatedBuffer = 0;
      adjustedFilePathBuilder.m_pBuffer = adjustedFilePathBuilder.m_inlineBuffer;
      *(_QWORD *)&adjustedFilePathBuilder.m_cBuffer = 96;
      xstring_ptr_view::GetCount(&strFilePath.xstring_ptr_view);
      v25 = xstrlen(L"/Files/");
      appended = TStringBuilder<96>::Initialize(&adjustedFilePathBuilder, v25 + v26);
      v11 = appended;
      if ( appended >= 0 )
      {
        xephemeral_string_ptr::xephemeral_string_ptr(&v38, L"/Files", 6u);
        appended = TStringBuilder<96>::Append(&adjustedFilePathBuilder, v28);
        v11 = appended;
        if ( appended >= 0 )
        {
          if ( !xstring_ptr_view::GetCount(&strFilePath.xstring_ptr_view)
            || *xstring_ptr_view::GetBuffer(&strFilePath.xstring_ptr_view) == 47
            || (appended = TStringBuilder<96>::AppendChar(&adjustedFilePathBuilder, 0x2Fu), v11 = appended,
                                                                                            appended >= 0) )
          {
            appended = TStringBuilder<96>::Append(&adjustedFilePathBuilder, &strFilePath);
            v11 = appended;
            if ( appended >= 0 )
            {
              v9->m_uc.dwUrlPathLength = adjustedFilePathBuilder.m_cActual;
              operator delete(v9->m_uc.lpszUrlPath);
              xephemeral_string_ptr::xephemeral_string_ptr(
                &v38,
                adjustedFilePathBuilder.m_pBuffer,
                adjustedFilePathBuilder.m_cActual);
              v9->m_uc.lpszUrlPath = xstring_ptr_view::MakeBufferCopy(v29);
              TStringBuilder<16>::~TStringBuilder<16>(&adjustedFilePathBuilder);
LABEL_54:
              *(_DWORD *)v9->m_componentResourceLocation = *(_DWORD *)this->m_componentResourceLocation;
              *ppUriCombine = v9;
              return (unsigned int)v11;
            }
          }
        }
      }
      OnFailure_2990_(appended);
      TStringBuilder<16>::~TStringBuilder<16>(&adjustedFilePathBuilder);
    }
  }
  else
  {
    v11 = -2147467261;
    OnNewFailure_1172_((HRESULT)this);
  }
  if ( v9 )
    CInterlockedReferenceCount::Release((ImageSharingEngineHost *)&v9->CInterlockedReferenceCount);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180598650  push    rbp
0x180598652  push    rbx
0x180598653  push    rsi
0x180598654  push    rdi
0x180598655  push    r12
0x180598657  push    r13
0x180598659  push    r14
0x18059865b  push    r15
0x18059865d  lea     rbp, [rsp-41C8h]
0x180598665  mov     eax, 42C8h
0x18059866a  call    _alloca_probe
0x18059866f  sub     rsp, rax
0x180598672  mov     rax, cs:__security_cookie
0x180598679  xor     rax, rsp
0x18059867c  mov     [rbp+4200h+var_50], rax
0x180598683  xor     r14d, r14d
0x180598686  mov     esi, cUri
0x180598688  mov     [rsp+4300h+cBase], r14d
0x18059868d  mov     r12, ppUriCombine
0x180598690  mov     [rsp+4300h+cCombine], r14d
0x180598695  mov     r15, pUri
0x180598698  mov     [rsp+4300h+isMsResourceUri], r14b
0x18059869d  mov     r13, this
0x1805986a0  mov     [rsp+4300h+bIsFileUri], r14b
0x1805986a5  mov     edi, r14d
0x1805986a8  mov     [rsp+4300h+pTempUri], r14
0x1805986ad  test    ppUriCombine, ppUriCombine
0x1805986b0  jz      loc_180598B7C
0x1805986b6  lea     r8d, [r14+5Ch]; theChar
0x1805986ba  mov     cUri, esi; theStringLen
0x1805986bc  mov     this, r15; theString
0x1805986bf  call    ?xfindchar@@YAIPEBGIG@Z; xfindchar(ushort const *,uint,ushort)
0x1805986c4  cmp     eax, 0FFFFFFFFh
0x1805986c7  jz      short loc_1805986D8
0x1805986c9  mov     ebx, 80000012h
0x1805986ce  call    OnFailure_957_
0x1805986d3  jmp     loc_180598B94
0x1805986d8  mov     edi, 825h
0x1805986dd  lea     this, [r13+18h]; lpUrlComponents
0x1805986e1  lea     ppUriCombine, [rsp+4300h+cBase]; lpdwUrlLength
0x1805986e6  mov     [rsp+4300h+cBase], edi
0x1805986ea  lea     pUri, [rbp+4200h+strBase]; lpszUrl
0x1805986f1  xor     cUri, cUri; dwFlags
0x1805986f3  call    cs:__imp_InternetCreateUrlW
0x1805986f9  test    eax, eax
0x1805986fb  jnz     short loc_180598728
0x1805986fd  call    cs:__imp_GetLastError
0x180598703  mov     ebx, eax
0x180598705  test    eax, eax
0x180598707  jle     short loc_180598712
0x180598709  movzx   ebx, ax
0x18059870c  or      ebx, 80070000h
0x180598712  test    ebx, ebx
0x180598714  mov     eax, 80004005h
0x180598719  cmovns  ebx, eax
0x18059871c  mov     ecx, ebx; failedFrameHR
0x18059871e  call    OnNewFailure_3049_
0x180598723  jmp     loc_180598B94
0x180598728  lea     eax, [rsi+1]
0x18059872b  cmp     eax, edi
0x18059872d  jbe     short loc_18059873E
0x18059872f  mov     ebx, 80004005h
0x180598734  call    OnFailure_977_
0x180598739  jmp     loc_180598B94
0x18059873e  lea     this, [rbp+4200h+strRelative]; void *
0x180598745  test    esi, esi
0x180598747  jz      short loc_180598757
0x180598749  mov     pUri, rsi
0x18059874c  mov     rdx, r15; Src
0x18059874f  add     pUri, pUri; Size
0x180598752  call    memcpy_0
0x180598757  lea     this, [rsi+rsi]
0x18059875b  cmp     this, 104Ah
0x180598762  jnb     loc_180598B76
0x180598768  mov     [rbp+this+4200h+strRelative], r14w
0x180598771  lea     ppUriCombine, [rsp+4300h+cCombine]; lpdwBufferLength
0x180598776  lea     this, [rbp+4200h+strBase]; lpszBaseUrl
0x18059877d  mov     [rsp+4300h+cCombine], edi
0x180598781  lea     pUri, [rbp+4200h+strCombine]; lpszBuffer
0x180598785  mov     [rsp+4300h+dwFlags], 28000000h; dwFlags
0x18059878d  lea     rdx, [rbp+4200h+strRelative]; lpszRelativeUrl
0x180598794  call    cs:__imp_InternetCombineUrlW
0x18059879a  test    eax, eax
0x18059879c  jnz     short loc_1805987C9
0x18059879e  call    cs:__imp_GetLastError
0x1805987a4  mov     ebx, eax
0x1805987a6  test    eax, eax
0x1805987a8  jle     short loc_1805987B3
0x1805987aa  movzx   ebx, ax
0x1805987ad  or      ebx, 80070000h
0x1805987b3  test    ebx, ebx
0x1805987b5  mov     eax, 80004005h
0x1805987ba  cmovns  ebx, eax
0x1805987bd  mov     ecx, ebx; failedFrameHR
0x1805987bf  call    OnNewFailure_3049_
0x1805987c4  jmp     loc_180598B94
0x1805987c9  lea     ppUriCombine, [rsp+4300h+cCombine]; lpdwBufferLength
0x1805987ce  mov     [rsp+4300h+cCombine], edi
0x1805987d2  lea     pUri, [rbp+4200h+strCombine]; lpszBuffer
0x1805987d6  mov     [rsp+4300h+dwFlags], 20000000h; dwFlags
0x1805987de  lea     rdx, [rbp+4200h+strRelative]; lpszRelativeUrl
0x1805987e5  lea     this, [rbp+4200h+strBase]; lpszBaseUrl
0x1805987ec  call    cs:__imp_InternetCombineUrlW
0x1805987f2  test    eax, eax
0x1805987f4  jnz     short loc_180598821
0x1805987f6  call    cs:__imp_GetLastError
0x1805987fc  mov     ebx, eax
0x1805987fe  test    eax, eax
0x180598800  jle     short loc_18059880B
0x180598802  movzx   ebx, ax
0x180598805  or      ebx, 80070000h
0x18059880b  test    ebx, ebx
0x18059880d  mov     eax, 80004005h
0x180598812  cmovns  ebx, eax
0x180598815  mov     ecx, ebx; failedFrameHR
0x180598817  call    OnNewFailure_3049_
0x18059881c  jmp     loc_180598B94
0x180598821  lea     rax, [rsp+4300h+bIsFileUri]
0x180598826  mov     r9d, 4; pResult
0x18059882c  lea     pUri, aFile_0; "file"
0x180598833  mov     qword ptr [rsp+4300h+dwFlags], rax; pstrUri
0x180598838  lea     this, [rbp+4200h+strCombine]; pstrUri
0x18059883c  call    UriSchemeEquals
0x180598841  mov     ebx, eax
0x180598843  test    eax, eax
0x180598845  js      loc_180598B6D
0x18059884b  cmp     [rsp+4300h+bIsFileUri], r14b
0x180598850  jz      short loc_1805988AA
0x180598852  lea     ppUriCombine, [rsp+4300h+cCombine]; lpdwBufferLength
0x180598857  mov     [rsp+4300h+cCombine], edi
0x18059885b  lea     pUri, [rbp+4200h+strCombine]; lpszBuffer
0x18059885f  mov     [rsp+4300h+dwFlags], 30000000h; dwFlags
0x180598867  lea     rdx, [rbp+4200h+strRelative]; lpszRelativeUrl
0x18059886e  lea     this, [rbp+4200h+strBase]; lpszBaseUrl
0x180598875  call    cs:__imp_InternetCombineUrlW
0x18059887b  test    eax, eax
0x18059887d  jnz     short loc_1805988AA
0x18059887f  call    cs:__imp_GetLastError
0x180598885  mov     ebx, eax
0x180598887  test    eax, eax
0x180598889  jle     short loc_180598894
0x18059888b  movzx   ebx, ax
0x18059888e  or      ebx, 80070000h
0x180598894  test    ebx, ebx
0x180598896  mov     eax, 80004005h
0x18059889b  cmovns  ebx, eax
0x18059889e  mov     ecx, ebx; failedFrameHR
0x1805988a0  call    OnNewFailure_3049_
0x1805988a5  jmp     loc_180598B94
0x1805988aa  lea     rax, [rsp+4300h+isMsResourceUri]
0x1805988af  mov     r9d, 0Bh; pResult
0x1805988b5  lea     pUri, aMsResource_0; "ms-resource"
0x1805988bc  mov     qword ptr [rsp+4300h+dwFlags], rax; pstrUri
0x1805988c1  lea     this, [rbp+4200h+strCombine]; pstrUri
0x1805988c5  call    UriSchemeEquals
0x1805988ca  mov     ebx, eax
0x1805988cc  test    eax, eax
0x1805988ce  js      loc_180598B64
0x1805988d4  mov     ebx, 1
0x1805988d9  cmp     [rsp+4300h+isMsResourceUri], r14b
0x1805988de  jz      short loc_180598955
0x1805988e0  mov     r8d, [r13+68h]; count
0x1805988e4  lea     this, [rsp+4300h+strFilePath]; this
0x1805988e9  mov     rdx, [r13+60h]; buffer
0x1805988ed  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x1805988f2  lea     r8d, [rbx+6]; count
0x1805988f6  lea     rdx, aFiles_2; "/Files/"
0x1805988fd  lea     this, [rsp+4300h+var_428C]; this
0x180598902  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x180598907  mov     rdx, rax; strStringToFind
0x18059890a  lea     this, [rsp+4300h+strFilePath]; this
0x18059890f  mov     r8d, ebx; eCompareBehavior
0x180598912  call    ?StartsWith@xstring_ptr_view@@QEBAIAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::StartsWith(xstring_ptr_view const &,xstrCompareBehavior)
0x180598917  test    eax, eax
0x180598919  jnz     short loc_180598944
0x18059891b  lea     r8d, [rbx+5]; count
0x18059891f  lea     rdx, aFiles_1; "Files/"
0x180598926  lea     this, [rsp+4300h+var_42A0]; this
0x18059892b  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x180598930  mov     rdx, rax; strStringToFind
0x180598933  lea     this, [rsp+4300h+strFilePath]; this
0x180598938  mov     r8d, ebx; eCompareBehavior
0x18059893b  call    ?StartsWith@xstring_ptr_view@@QEBAIAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::StartsWith(xstring_ptr_view const &,xstrCompareBehavior)
0x180598940  test    eax, eax
0x180598942  jz      short loc_180598955
0x180598944  test    esi, esi
0x180598946  jz      short loc_180598955
0x180598948  mov     eax, 2Fh ; '/'
0x18059894d  cmp     [r15], ax
0x180598951  cmovnz  r14d, ebx
0x180598955  mov     ecx, [rsp+4300h+cCombine]; cString
0x180598959  lea     ppUriCombine, [rbp+4200h+strHealthyUrl]; pOutString
0x180598960  lea     pUri, [rsp+4300h+cHealthyUrl]; pcOutString
0x180598965  mov     [rsp+4300h+cHealthyUrl], edi
0x180598969  lea     rdx, [rbp+4200h+strCombine]; pString
0x18059896d  call    ?GetHealthyUrl@CWinUriLegacy@@CAJIPEBGPEAIPEAG@Z; CWinUriLegacy::GetHealthyUrl(uint,ushort const *,uint *,ushort *)
0x180598972  mov     ebx, eax
0x180598974  test    eax, eax
0x180598976  js      loc_180598B5B
0x18059897c  mov     cUri, [rsp+4300h+cHealthyUrl]; cString
0x180598980  lea     ppUriCombine, [rsp+4300h+pTempUri]; ppUri
0x180598985  lea     pUri, [rbp+4200h+strHealthyUrl]; pString
0x18059898c  xor     ecx, ecx; bCanonicalize
0x18059898e  call    ?Create@CWinUriLegacy@@CAJHIPEBGPEAPEAUIPALUri@@@Z; CWinUriLegacy::Create(int,uint,ushort const *,IPALUri * *)
0x180598993  mov     ebx, eax
0x180598995  test    eax, eax
0x180598997  js      loc_180598B4D
0x18059899d  mov     rdi, [rsp+4300h+pTempUri]
0x1805989a2  test    r14d, r14d
0x1805989a5  jz      loc_180598B16
0x1805989ab  mov     r8d, [rdi+68h]; count
0x1805989af  lea     this, [rsp+4300h+strFilePath]; this
0x1805989b4  mov     rdx, [rdi+60h]; buffer
0x1805989b8  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x1805989bd  mov     r8d, 7; count
0x1805989c3  lea     rdx, aFiles_2; "/Files/"
0x1805989ca  lea     this, [rsp+4300h+var_42A0]; this
0x1805989cf  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x1805989d4  mov     esi, 1
0x1805989d9  lea     this, [rsp+4300h+strFilePath]; this
0x1805989de  mov     r8d, esi; eCompareBehavior
0x1805989e1  mov     rdx, rax; strStringToFind
0x1805989e4  call    ?StartsWith@xstring_ptr_view@@QEBAIAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::StartsWith(xstring_ptr_view const &,xstrCompareBehavior)
0x1805989e9  xor     r14d, r14d
0x1805989ec  test    eax, eax
0x1805989ee  jnz     loc_180598B16
0x1805989f4  lea     r15d, [rsi+5]
0x1805989f8  mov     r8d, r15d; count
0x1805989fb  lea     rdx, aFiles_1; "Files/"
0x180598a02  lea     this, [rsp+4300h+var_428C]; this
0x180598a07  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x180598a0c  mov     rdx, rax; strStringToFind
0x180598a0f  lea     this, [rsp+4300h+strFilePath]; this
0x180598a14  mov     r8d, esi; eCompareBehavior
0x180598a17  call    ?StartsWith@xstring_ptr_view@@QEBAIAEBV1@W4xstrCompareBehavior@@@Z; xstring_ptr_view::StartsWith(xstring_ptr_view const &,xstrCompareBehavior)
0x180598a1c  test    eax, eax
0x180598a1e  jnz     loc_180598B16
0x180598a24  lea     rax, [rbp+4200h+adjustedFilePathBuilder.m_inlineBuffer]
0x180598a28  mov     [rbp+4200h+adjustedFilePathBuilder.m_hPreallocatedBuffer], r14
0x180598a2c  lea     this, [rsp+4300h+strFilePath]; this
0x180598a31  mov     [rbp+4200h+adjustedFilePathBuilder.m_pBuffer], rax
0x180598a35  mov     qword ptr [rbp+4200h+adjustedFilePathBuilder.m_cBuffer], 60h ; '`'
0x180598a3d  call    ?GetCount@xstring_ptr_view@@QEBAIXZ; xstring_ptr_view::GetCount(void)
0x180598a42  lea     this, aFiles_2; "/Files/"
0x180598a49  mov     r9d, eax
0x180598a4c  call    ?xstrlen@@YAIPEBG@Z; xstrlen(ushort const *)
0x180598a51  lea     this, [rbp+4200h+adjustedFilePathBuilder]; this
0x180598a55  lea     cUri, [rax+ppUriCombine]; initialBufferSize
0x180598a59  call    ?Initialize@?$TStringBuilder@$0GA@@@QEAAJI@Z; TStringBuilder<96>::Initialize(uint)
0x180598a5e  mov     ebx, eax
0x180598a60  test    eax, eax
0x180598a62  js      loc_180598B3B
0x180598a68  mov     r8d, r15d; count
0x180598a6b  lea     rdx, aFiles; "/Files"
0x180598a72  lea     this, [rsp+4300h+var_42A0]; this
0x180598a77  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x180598a7c  mov     rdx, rax; strToAppend
0x180598a7f  lea     this, [rbp+4200h+adjustedFilePathBuilder]; this
0x180598a83  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180598a88  mov     ebx, eax
0x180598a8a  test    eax, eax
0x180598a8c  js      loc_180598B32
0x180598a92  lea     this, [rsp+4300h+strFilePath]; this
0x180598a97  call    ?GetCount@xstring_ptr_view@@QEBAIXZ; xstring_ptr_view::GetCount(void)
0x180598a9c  test    eax, eax
0x180598a9e  jz      short loc_180598ACC
0x180598aa0  lea     this, [rsp+4300h+strFilePath]; this
0x180598aa5  call    ?GetBuffer@xstring_ptr_view@@QEBAPEBGXZ; xstring_ptr_view::GetBuffer(void)
0x180598aaa  lea     ecx, [rsi+2Eh]
0x180598aad  cmp     [rax], cx
0x180598ab0  jz      short loc_180598ACC
0x180598ab2  mov     cUri, ecx; ch
0x180598ab4  lea     this, [rbp+4200h+adjustedFilePathBuilder]; this
0x180598ab8  call    ?AppendChar@?$TStringBuilder@$0GA@@@QEAAJG@Z; TStringBuilder<96>::AppendChar(ushort)
0x180598abd  mov     ebx, eax
0x180598abf  test    eax, eax
0x180598ac1  jns     short loc_180598ACC
0x180598ac3  mov     ecx, eax; failedFrameHR
0x180598ac5  call    OnFailure_2990_
0x180598aca  jmp     short loc_180598B42
0x180598acc  lea     rdx, [rsp+4300h+strFilePath]; strToAppend
0x180598ad1  lea     this, [rbp+4200h+adjustedFilePathBuilder]; this
0x180598ad5  call    ?Append@?$TStringBuilder@$0GA@@@QEAAJAEBVxstring_ptr_view@@@Z; TStringBuilder<96>::Append(xstring_ptr_view const &)
0x180598ada  mov     ebx, eax
0x180598adc  test    eax, eax
0x180598ade  js      short loc_180598B29
0x180598ae0  mov     eax, [rbp+4200h+adjustedFilePathBuilder.m_cActual]
0x180598ae3  mov     [rdi+68h], eax
0x180598ae6  mov     this, [rdi+60h]; pAddress
0x180598aea  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180598aef  mov     r8d, [rbp+4200h+adjustedFilePathBuilder.m_cActual]; count
0x180598af3  lea     this, [rsp+4300h+var_42A0]; this
0x180598af8  mov     rdx, [rbp+4200h+adjustedFilePathBuilder.m_pBuffer]; buffer
0x180598afc  call    ??0xephemeral_string_ptr@@QEAA@PEBGI@Z; xephemeral_string_ptr::xephemeral_string_ptr(ushort const *,uint)
0x180598b01  mov     this, rax; this
0x180598b04  call    ?MakeBufferCopy@xstring_ptr_view@@QEBAPEAGXZ; xstring_ptr_view::MakeBufferCopy(void)
0x180598b09  lea     this, [rbp+4200h+adjustedFilePathBuilder]; this
0x180598b0d  mov     [rdi+60h], rax
0x180598b11  call    ??1?$TStringBuilder@$0BA@@@QEAA@XZ; TStringBuilder<16>::~TStringBuilder<16>(void)
0x180598b16  mov     eax, [r13+80h]
  ... truncated ...
```
