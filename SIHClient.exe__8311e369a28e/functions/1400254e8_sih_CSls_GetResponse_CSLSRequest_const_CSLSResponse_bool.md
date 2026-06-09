# sih::CSls::GetResponse(CSLSRequest const &,CSLSResponse &,bool *)

- ea: `0x1400254e8`
- end: `0x140025a98`
- name: `?GetResponse@CSls@sih@@AEAAJAEBVCSLSRequest@@AEAVCSLSResponse@@PEA_N@Z`
- size: `1456`
- prototype: `__int64 __fastcall(sih::CSls *this, const struct CSLSRequest *, struct CSLSResponse *, bool *)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, registry_config, installer_update, broker_com_uri`

## callers

- `0x140024f14`

## callees

- `0x140003de4`
- `0x1400071c0`
- `0x1400073f0`
- `0x14000cb54`
- `0x14000ce30`
- `0x14000fc20`
- `0x1400154b4`
- `0x140017934`
- `0x140017bd0`
- `0x1400254e8`
- `0x140025c80`
- `0x1400332d4`
- `0x14003401c`
- `0x14003bcb0`
- `0x140045dc0`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400255de`
- `api-ms-win-core-com-l1-1-0!StringFromGUID2` at `0x1400255de`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400256aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400256bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140025763`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400256aa`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x1400256bf`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140025763`

## string_xrefs

- `0x1400257eb`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test`
- `0x1400257e4`: `SLSNoCache`
- `0x14002560e`: `ResponsePayloadFilePath`
- `0x14002559f`: `Software\Microsoft\Windows\CurrentVersion\WindowsUpdate\Test\SLS`
- `0x1400256df`: `Read local SLS override xml`
- `0x1400257fc`: `NoCache override set.`
- `0x1400259d6`: `Cached response absent/expired. Online refresh is needed but the caller has explicitly disallowed it.`
- `0x140025a70`: `Online refresh failed.  Using expired cache content.`

## pseudocode

```c
__int64 __fastcall sih::CSls::GetResponse(
        sih::CSls *this,
        const struct CSLSRequest *a2,
        struct CSLSResponse *a3,
        bool *a4)
{
  __int64 v6; // rcx
  GUID *p_Src; // rdx
  int UrlContent; // edi
  void *v9; // r14
  sih::CSls *v10; // rcx
  int v11; // eax
  char v12; // cl
  int v13; // ebx
  bool v14; // r15
  __int64 v15; // rcx
  char *v16; // rcx
  char *v17; // rbx
  __int64 v18; // rax
  sih::CSls *v20; // rbx
  struct CSLSResponse *v21; // [rsp+20h] [rbp-E0h]
  char *v22[2]; // [rsp+40h] [rbp-C0h] BYREF
  void *lpMem; // [rsp+50h] [rbp-B0h]
  __int64 v24; // [rsp+58h] [rbp-A8h]
  bool *v25; // [rsp+60h] [rbp-A0h]
  sih::CSls *v26; // [rsp+68h] [rbp-98h]
  _OWORD v27[4]; // [rsp+70h] [rbp-90h] BYREF
  bool v28[8]; // [rsp+B0h] [rbp-50h] BYREF
  struct _FILETIME v29; // [rsp+B8h] [rbp-48h] BYREF
  GUID v30; // [rsp+C0h] [rbp-40h] BYREF
  void *v31[2]; // [rsp+D0h] [rbp-30h]
  __int64 v32; // [rsp+E0h] [rbp-20h]
  char v33; // [rsp+E8h] [rbp-18h]
  int v34; // [rsp+E9h] [rbp-17h]
  __int16 v35; // [rsp+EDh] [rbp-13h]
  char v36; // [rsp+EFh] [rbp-11h]
  LPCWCH lpWideCharStr[2]; // [rsp+F0h] [rbp-10h]
  GUID Src; // [rsp+100h] [rbp+0h] BYREF
  __int128 v39; // [rsp+110h] [rbp+10h]
  __int64 v40; // [rsp+120h] [rbp+20h]
  BOOL v41; // [rsp+128h] [rbp+28h]
  int v42; // [rsp+12Ch] [rbp+2Ch]
  char *v43; // [rsp+130h] [rbp+30h]
  LPCWCH v44; // [rsp+138h] [rbp+38h]
  OLECHAR sz[40]; // [rsp+140h] [rbp+40h] BYREF
  wchar_t v46[264]; // [rsp+190h] [rbp+90h] BYREF

  v25 = a4;
  v26 = this;
  *a4 = 0;
  v29 = 0;
  v28[0] = 0;
  v30 = GUID_NULL;
  *(_OWORD *)v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  v35 = 0;
  v36 = 0;
  *(_OWORD *)lpWideCharStr = 0;
  if ( !(unsigned int)AreTestKeysAllowed((bool)this) )
  {
LABEL_13:
    GetSystemTimeAsFileTime(&v29);
    v11 = sih::CSls::DatastoreLookup(v10, a2, &v29, (struct sih::SlsCacheEntry *)&v30, v28);
    v13 = v11;
    if ( v11 >= 0 || (v12 = v11 - 32, (unsigned int)(v11 + 2145091552) <= 9) || v11 == -2145091577 )
    {
      v14 = v28[0];
    }
    else
    {
      LODWORD(v21) = v11;
      WUTrace(0, 0, 0x400000, 3, v21, L"DatastoreLookup got error. Continuing...");
      v14 = 1;
    }
    if ( (unsigned int)AreTestKeysAllowed(v12)
      && (unsigned int)RegQueryDwordValueWithDefaultAndRangeCheck(
                         v15,
                         L"Software\\Microsoft\\Windows\\CurrentVersion\\WindowsUpdate\\Test",
                         L"SLSNoCache",
                         0) == 1 )
    {
      WUTrace(0, 0, 0x400000, 4, 0, L"NoCache override set.");
      v14 = 1;
    }
    if ( v13 >= 0 && lpWideCharStr[0] )
    {
      Src = v30;
      v39 = *(_OWORD *)v31;
      v40 = v32;
      v41 = v33 != 0;
      v22[0] = 0;
      UrlContent = ConvertWideToAnsi_Alloc(lpWideCharStr[0], v22);
      if ( UrlContent < 0 )
      {
        v16 = v22[0];
        if ( !v22[0] )
          goto LABEL_11;
LABEL_25:
        SusFree(v16);
        goto LABEL_11;
      }
      v17 = v22[0];
      v43 = v22[0];
      v18 = -1;
      do
        ++v18;
      while ( v22[0][v18] );
      v42 = v18 + 1;
      v44 = lpWideCharStr[1];
      UrlContent = CSLSResponse::PopulateFromDataStore(a3, (const struct tagDSSLSData *)&Src);
      if ( UrlContent < 0 )
      {
        LODWORD(v21) = UrlContent;
        WUTrace(0, 0, 0x400000, 1, v21, L"PopulateFromDataStore");
        if ( !v17 )
          goto LABEL_11;
        v16 = v17;
        goto LABEL_25;
      }
      if ( !v14 )
      {
        *v25 = 1;
        if ( v17 )
          SusFree(v17);
        goto LABEL_34;
      }
      if ( v17 )
        SusFree(v17);
    }
    v20 = v26;
    if ( !*(_BYTE *)v26 )
    {
      WUTrace(
        0,
        0,
        0x400000,
        3,
        0,
        L"Cached response absent/expired. Online refresh is needed but the caller has explicitly disallowed it.");
      UrlContent = -2145103859;
      goto LABEL_11;
    }
    if ( lpWideCharStr[1] )
      WUTrace(0, 0, 0x400000, 4, 0, L"Retrieving SLS response from server using ETAG %ws...");
    else
      WUTrace(0, 0, 0x400000, 4, 0, L"Retrieving SLS response from server...");
    v28[0] = 0;
    UrlContent = CSLSDownloader::GetUrlContent(
                   (CSLSDownloader *)v28,
                   0,
                   a2,
                   *((const struct CCallerIdentity **)v20 + 1),
                   a3,
                   0);
    if ( UrlContent < 0 )
    {
      if ( !lpWideCharStr[0] )
        goto LABEL_11;
      UrlContent = 0;
      WUTrace(0, 0, 0x400000, 3, 0, L"Online refresh failed.  Using expired cache content.");
    }
    goto LABEL_34;
  }
  memset(v46, 0, 520);
  Src = 0;
  v39 = 0;
  std::wstring::_Construct<1,wchar_t const *>(&Src);
  std::wstring::append(&Src, (void *)L"\\");
  memset(sz, 0, 78);
  StringFromGUID2((const GUID *const)a2, sz, 39);
  std::wstring::append(&Src, sz);
  p_Src = &Src;
  if ( *((_QWORD *)&v39 + 1) > 7u )
    p_Src = *(GUID **)&Src.Data1;
  if ( (int)RegQueryStringValue(v6, p_Src, L"ResponsePayloadFilePath", v46, 260) < 0 )
  {
    std::wstring::~wstring(&Src);
    goto LABEL_13;
  }
  WUTrace(0, 0, 0x400000, 4, 0, L"local from %ws");
  v22[1] = (char *)&CSafeBuffer<unsigned char>::`vftable';
  lpMem = 0;
  v24 = 0;
  memset(v27, 0, sizeof(v27));
  UrlContent = ReadFileToSafeByteBuffer(v46);
  if ( UrlContent < 0 )
  {
    v9 = lpMem;
  }
  else
  {
    v9 = 0;
    v27[0] = *(_OWORD *)a2;
    GetSystemTimeAsFileTime((LPFILETIME)&v27[1] + 1);
    *(_QWORD *)&v27[3] = lpMem;
    HIDWORD(v27[2]) = HIDWORD(v24);
    GetSystemTimeAsFileTime((LPFILETIME)&v27[2]);
    UrlContent = CSLSResponse::PopulateFromDataStore(a3, (const struct tagDSSLSData *)v27);
    if ( UrlContent >= 0 )
      goto LABEL_10;
  }
  LODWORD(v21) = UrlContent;
  WUTrace(0, 0, 0x400000, 1, v21, L"Read local SLS override xml");
LABEL_10:
  SusFree(v9);
  std::wstring::~wstring(&Src);
  if ( UrlContent < 0 )
  {
LABEL_11:
    LODWORD(v21) = UrlContent;
    WUTrace("sih::CSls::GetResponse", 307, 0x400000, 1, v21, L"Method failed");
    goto LABEL_35;
  }
LABEL_34:
  WUTrace(0, 0, 0x400000, 5, 0, L"GetResponse succeeded. The file %ws downloaded.");
LABEL_35:
  if ( lpWideCharStr[1] )
  {
    SusFree((void *)lpWideCharStr[1]);
    lpWideCharStr[1] = 0;
  }
  if ( lpWideCharStr[0] )
  {
    SusFree((void *)lpWideCharStr[0]);
    lpWideCharStr[0] = 0;
  }
  if ( v31[0] )
    SusFree(v31[0]);
  return (unsigned int)UrlContent;
}

```

## disassembly

```asm
0x1400254e8  push    rbp
0x1400254ea  push    rbx
0x1400254eb  push    rsi
0x1400254ec  push    rdi
0x1400254ed  push    r12
0x1400254ef  push    r13
0x1400254f1  push    r14
0x1400254f3  push    r15
0x1400254f5  lea     rbp, [rsp-2B8h]
0x1400254fd  sub     rsp, 3B8h
0x140025504  mov     rax, cs:__security_cookie
0x14002550b  xor     rax, rsp
0x14002550e  mov     [rbp+2F0h+var_50], rax
0x140025515  mov     [rsp+3F0h+var_390], r9
0x14002551a  mov     r12, r8
0x14002551d  mov     r13, rdx
0x140025520  mov     [rsp+3F0h+var_388], rcx
0x140025525  xor     r15d, r15d
0x140025528  mov     [r9], r15b
0x14002552b  mov     qword ptr [rbp+2F0h+var_338.dwLowDateTime], r15
0x14002552f  mov     [rbp+2F0h+var_340], r15b
0x140025533  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x14002553a  movdqu  [rbp+2F0h+var_330], xmm0
0x14002553f  xorps   xmm0, xmm0
0x140025542  movdqa  xmmword ptr [rbp+2F0h+var_320], xmm0
0x140025547  xor     eax, eax
0x140025549  mov     [rbp+2F0h+var_310], rax
0x14002554d  mov     [rbp+2F0h+var_308], r15b
0x140025551  mov     [rbp+2F0h+var_307], eax
0x140025554  mov     [rbp+2F0h+var_303], ax
0x140025558  mov     [rbp+2F0h+var_301], al
0x14002555b  movdqa  xmmword ptr [rbp+2F0h+lpWideCharStr], xmm0
0x140025560  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x140025565  test    eax, eax
0x140025567  jz      loc_14002575F
0x14002556d  mov     [rbp+2F0h+var_260], r15w
0x140025575  xor     edx, edx; Val
0x140025577  mov     r8d, 206h; Size
0x14002557d  lea     rcx, [rbp+2F0h+var_25E]; void *
0x140025584  call    memset
0x140025589  xorps   xmm0, xmm0
0x14002558c  movups  [rbp+2F0h+Src], xmm0
0x140025590  xorps   xmm1, xmm1
0x140025593  movdqu  [rbp+2F0h+var_2E0], xmm1
0x140025598  lea     edi, [r15+40h]
0x14002559c  mov     r8d, edi
0x14002559f  lea     rdx, ?c_szWUTestSLSKey@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400255a6  lea     rcx, [rbp+2F0h+Src]
0x1400255aa  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400255af  lea     rdx, SubBlock; "\\"
0x1400255b6  lea     rcx, [rbp+2F0h+Src]; Src
0x1400255ba  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1400255bf  mov     [rbp+2F0h+sz], r15w
0x1400255c4  xor     edx, edx; Val
0x1400255c6  lea     r8d, [r15+4Ch]; Size
0x1400255ca  lea     rcx, [rbp+2F0h+var_2AE]; void *
0x1400255ce  call    memset
0x1400255d3  lea     r8d, [r15+27h]; cchMax
0x1400255d7  lea     rdx, [rbp+2F0h+sz]; lpsz
0x1400255db  mov     rcx, r13; rguid
0x1400255de  call    cs:__imp_StringFromGUID2
0x1400255e4  lea     rdx, [rbp+2F0h+sz]; void *
0x1400255e8  lea     rcx, [rbp+2F0h+Src]; Src
0x1400255ec  call    ?append@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@QEB_W@Z; std::wstring::append(wchar_t const * const)
0x1400255f1  lea     rdx, [rbp+2F0h+Src]
0x1400255f5  cmp     qword ptr [rbp+2F0h+var_2E0+8], 7
0x1400255fa  cmova   rdx, qword ptr [rbp+2F0h+Src]
0x1400255ff  mov     dword ptr [rsp+3F0h+var_3D0], 104h
0x140025607  lea     r9, [rbp+2F0h+var_260]
0x14002560e  lea     r8, ?c_szRegSLSResponsePayloadFilePath@@3QB_WB; "ResponsePayloadFilePath"
0x140025615  call    ?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z; RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)
0x14002561a  test    eax, eax
0x14002561c  js      loc_140025756
0x140025622  lea     rax, [rbp+2F0h+var_260]
0x140025629  mov     [rsp+3F0h+var_3C0], rax
0x14002562e  lea     rax, aLocalFromWs; "local from %ws"
0x140025635  mov     [rsp+3F0h+var_3C8], rax
0x14002563a  mov     [rsp+3F0h+var_3D0], r15
0x14002563f  mov     esi, 400000h
0x140025644  lea     r9d, [r15+4]
0x140025648  mov     r8d, esi
0x14002564b  xor     edx, edx
0x14002564d  xor     ecx, ecx
0x14002564f  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140025654  lea     rax, ??_7?$CSafeBuffer@E@@6B@; const CSafeBuffer<uchar>::`vftable'
0x14002565b  mov     [rsp+3F0h+var_3A8], rax
0x140025660  mov     [rsp+3F0h+lpMem], r15
0x140025665  mov     [rsp+3F0h+var_398], r15
0x14002566a  mov     ebx, r15d
0x14002566d  mov     r8d, edi; Size
0x140025670  xor     edx, edx; Val
0x140025672  lea     rcx, [rsp+3F0h+var_380]; void *
0x140025677  call    memset
0x14002567c  lea     rdx, [rsp+3F0h+var_3A8]
0x140025681  lea     rcx, [rbp+2F0h+var_260]
0x140025688  call    ?ReadFileToSafeByteBuffer@@YAJPEB_WPEAV?$CSafeBuffer@E@@@Z; ReadFileToSafeByteBuffer(wchar_t const *,CSafeBuffer<uchar> *)
0x14002568d  mov     edi, eax
0x14002568f  test    eax, eax
0x140025691  js      short loc_1400256DA
0x140025693  mov     rbx, [rsp+3F0h+lpMem]
0x140025698  mov     r14d, r15d
0x14002569b  movups  xmm0, xmmword ptr [r13+0]
0x1400256a0  movdqu  [rsp+3F0h+var_380], xmm0
0x1400256a6  lea     rcx, [rbp+2F0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x1400256aa  call    cs:__imp_GetSystemTimeAsFileTime
0x1400256b0  mov     [rbp+2F0h+var_350], rbx
0x1400256b4  mov     eax, dword ptr [rsp+3F0h+var_398+4]
0x1400256b8  mov     [rbp+2F0h+var_354], eax
0x1400256bb  lea     rcx, [rbp+2F0h+var_360]; lpSystemTimeAsFileTime
0x1400256bf  call    cs:__imp_GetSystemTimeAsFileTime
0x1400256c5  lea     rdx, [rsp+3F0h+var_380]; struct tagDSSLSData *
0x1400256ca  mov     rcx, r12; this
0x1400256cd  call    ?PopulateFromDataStore@CSLSResponse@@QEAAJAEBUtagDSSLSData@@@Z; CSLSResponse::PopulateFromDataStore(tagDSSLSData const &)
0x1400256d2  mov     edi, eax
0x1400256d4  test    eax, eax
0x1400256d6  jns     short loc_140025701
0x1400256d8  jmp     short loc_1400256DF
0x1400256da  mov     r14, [rsp+3F0h+lpMem]
0x1400256df  lea     rax, aReadLocalSlsOv; "Read local SLS override xml"
0x1400256e6  mov     [rsp+3F0h+var_3C8], rax
0x1400256eb  mov     dword ptr [rsp+3F0h+var_3D0], edi
0x1400256ef  mov     r9d, 1
0x1400256f5  mov     r8d, esi
0x1400256f8  xor     edx, edx
0x1400256fa  xor     ecx, ecx
0x1400256fc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140025701  test    rbx, rbx
0x140025704  jz      short loc_14002570E
0x140025706  mov     rcx, rbx; lpMem
0x140025709  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002570e  mov     rcx, r14; lpMem
0x140025711  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025716  lea     rcx, [rbp+2F0h+Src]; void *
0x14002571a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002571f  test    edi, edi
0x140025721  jns     loc_14002591A
0x140025727  lea     rax, aMethodFailed; "Method failed"
0x14002572e  mov     [rsp+3F0h+var_3C8], rax
0x140025733  mov     dword ptr [rsp+3F0h+var_3D0], edi
0x140025737  mov     r9d, 1
0x14002573d  mov     r8d, esi
0x140025740  mov     edx, 133h
0x140025745  lea     rcx, aSihCslsGetresp; "sih::CSls::GetResponse"
0x14002574c  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140025751  jmp     loc_140025959
0x140025756  lea     rcx, [rbp+2F0h+Src]; void *
0x14002575a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14002575f  lea     rcx, [rbp+2F0h+var_338]; lpSystemTimeAsFileTime
0x140025763  call    cs:__imp_GetSystemTimeAsFileTime
0x140025769  lea     rax, [rbp+2F0h+var_340]
0x14002576d  mov     [rsp+3F0h+var_3D0], rax; bool *
0x140025772  lea     r9, [rbp+2F0h+var_330]; struct sih::SlsCacheEntry *
0x140025776  lea     r8, [rbp+2F0h+var_338]; struct _FILETIME *
0x14002577a  mov     rdx, r13; struct CSLSRequest *
0x14002577d  call    ?DatastoreLookup@CSls@sih@@AEBAJAEBVCSLSRequest@@AEBU_FILETIME@@AEAUSlsCacheEntry@2@PEA_N@Z; sih::CSls::DatastoreLookup(CSLSRequest const &,_FILETIME const &,sih::SlsCacheEntry &,bool *)
0x140025782  mov     ebx, eax
0x140025784  mov     esi, 400000h
0x140025789  test    eax, eax
0x14002578b  jns     short loc_1400257C6
0x14002578d  lea     ecx, [rax+7FDB7FE0h]
0x140025793  cmp     ecx, 9
0x140025796  jbe     short loc_1400257C6
0x140025798  cmp     eax, 80248007h
0x14002579d  jz      short loc_1400257C6
0x14002579f  lea     rax, aDatastorelooku; "DatastoreLookup got error. Continuing.."...
0x1400257a6  mov     [rsp+3F0h+var_3C8], rax
0x1400257ab  mov     dword ptr [rsp+3F0h+var_3D0], ebx
0x1400257af  mov     r9d, 3
0x1400257b5  mov     r8d, esi
0x1400257b8  xor     edx, edx
0x1400257ba  xor     ecx, ecx
0x1400257bc  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400257c1  mov     r15b, 1
0x1400257c4  jmp     short loc_1400257CA
0x1400257c6  mov     r15b, [rbp+2F0h+var_340]
0x1400257ca  call    ?AreTestKeysAllowed@@YAH_N@Z; AreTestKeysAllowed(bool)
0x1400257cf  xor     edi, edi
0x1400257d1  lea     r14d, [rdi+4]
0x1400257d5  test    eax, eax
0x1400257d7  jz      short loc_14002581F
0x1400257d9  mov     dword ptr [rsp+3F0h+var_3C8], 0FFFFFFFFh
0x1400257e1  xor     r9d, r9d
0x1400257e4  lea     r8, ?c_szRegSLSNoCache@@3QB_WB; "SLSNoCache"
0x1400257eb  lea     rdx, ?c_szRegWUTest@@3QB_WB; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1400257f2  call    ?RegQueryDwordValueWithDefaultAndRangeCheck@@YAKPEAUHKEY__@@PEB_W1KKKW4RegistryHiveType@@@Z; RegQueryDwordValueWithDefaultAndRangeCheck(HKEY__ *,wchar_t const *,wchar_t const *,ulong,ulong,ulong,RegistryHiveType)
0x1400257f7  cmp     eax, 1
0x1400257fa  jnz     short loc_14002581F
0x1400257fc  lea     rax, aNocacheOverrid; "NoCache override set."
0x140025803  mov     [rsp+3F0h+var_3C8], rax
0x140025808  mov     [rsp+3F0h+var_3D0], rdi
0x14002580d  mov     r9d, r14d
0x140025810  mov     r8d, esi
0x140025813  xor     edx, edx
0x140025815  xor     ecx, ecx
0x140025817  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x14002581c  mov     r15b, 1
0x14002581f  test    ebx, ebx
0x140025821  js      loc_1400259C2
0x140025827  mov     rcx, [rbp+2F0h+lpWideCharStr]; lpWideCharStr
0x14002582b  test    rcx, rcx
0x14002582e  jz      loc_1400259C2
0x140025834  movaps  xmm0, [rbp+2F0h+var_330]
0x140025838  movdqu  [rbp+2F0h+Src], xmm0
0x14002583d  mov     rax, [rbp+2F0h+var_320]
0x140025841  mov     qword ptr [rbp+2F0h+var_2E0], rax
0x140025845  mov     rax, [rbp+2F0h+var_320+8]
0x140025849  mov     qword ptr [rbp+2F0h+var_2E0+8], rax
0x14002584d  mov     rax, [rbp+2F0h+var_310]
0x140025851  mov     [rbp+2F0h+var_2D0], rax
0x140025855  mov     eax, edi
0x140025857  cmp     [rbp+2F0h+var_308], dil
0x14002585b  setnz   al
0x14002585e  mov     [rbp+2F0h+var_2C8], eax
0x140025861  mov     [rsp+3F0h+var_3B0], rdi
0x140025866  lea     rdx, [rsp+3F0h+var_3B0]; char **
0x14002586b  call    ?ConvertWideToAnsi_Alloc@@YAJPEB_WPEAPEAD@Z; ConvertWideToAnsi_Alloc(wchar_t const *,char * *)
0x140025870  mov     edi, eax
0x140025872  test    eax, eax
0x140025874  jns     short loc_140025891
0x140025876  mov     rcx, [rsp+3F0h+var_3B0]; lpMem
0x14002587b  xor     r15d, r15d
0x14002587e  test    rcx, rcx
0x140025881  jz      loc_140025727
0x140025887  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002588c  jmp     loc_140025727
0x140025891  mov     rbx, [rsp+3F0h+var_3B0]
0x140025896  mov     [rbp+2F0h+var_2C0], rbx
0x14002589a  or      rax, 0FFFFFFFFFFFFFFFFh
0x14002589e  inc     rax
0x1400258a1  cmp     byte ptr [rbx+rax], 0
0x1400258a5  jnz     short loc_14002589E
0x1400258a7  inc     eax
0x1400258a9  mov     [rbp+2F0h+var_2C4], eax
0x1400258ac  mov     rax, [rbp+2F0h+lpWideCharStr+8]
0x1400258b0  mov     [rbp+2F0h+var_2B8], rax
0x1400258b4  lea     rdx, [rbp+2F0h+Src]; struct tagDSSLSData *
0x1400258b8  mov     rcx, r12; this
0x1400258bb  call    ?PopulateFromDataStore@CSLSResponse@@QEAAJAEBUtagDSSLSData@@@Z; CSLSResponse::PopulateFromDataStore(tagDSSLSData const &)
0x1400258c0  mov     edi, eax
0x1400258c2  test    eax, eax
0x1400258c4  jns     short loc_1400258F9
0x1400258c6  lea     rax, aPopulatefromda; "PopulateFromDataStore"
0x1400258cd  mov     [rsp+3F0h+var_3C8], rax
0x1400258d2  mov     dword ptr [rsp+3F0h+var_3D0], edi
0x1400258d6  mov     r9d, 1
0x1400258dc  mov     r8d, esi
0x1400258df  xor     edx, edx
0x1400258e1  xor     ecx, ecx
0x1400258e3  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x1400258e8  xor     r15d, r15d
0x1400258eb  test    rbx, rbx
0x1400258ee  jz      loc_140025727
0x1400258f4  mov     rcx, rbx
0x1400258f7  jmp     short loc_140025887
0x1400258f9  test    r15b, r15b
0x1400258fc  jnz     loc_1400259B0
0x140025902  mov     rax, [rsp+3F0h+var_390]
0x140025907  mov     byte ptr [rax], 1
0x14002590a  xor     r15d, r15d
0x14002590d  test    rbx, rbx
0x140025910  jz      short loc_14002591A
0x140025912  mov     rcx, rbx; lpMem
0x140025915  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002591a  lea     rcx, aWas; "was"
0x140025921  lea     rax, aWasNot; "was not"
0x140025928  cmp     [r12+1Ch], r15b
0x14002592d  cmovnz  rax, rcx
0x140025931  mov     [rsp+3F0h+var_3C0], rax
0x140025936  lea     rax, aGetresponseSuc; "GetResponse succeeded. The file %ws dow"...
0x14002593d  mov     [rsp+3F0h+var_3C8], rax
0x140025942  mov     [rsp+3F0h+var_3D0], r15
0x140025947  mov     r9d, 5
0x14002594d  mov     r8d, esi
0x140025950  xor     edx, edx
0x140025952  xor     ecx, ecx
0x140025954  call    ?WUTrace@@YAXPEBDKW4WUTraceLoggingCategory@@IJPEB_WZZ; WUTrace(char const *,ulong,WUTraceLoggingCategory,uint,long,wchar_t const *,...)
0x140025959  mov     rcx, [rbp+2F0h+lpWideCharStr+8]; lpMem
0x14002595d  test    rcx, rcx
0x140025960  jz      short loc_14002596B
0x140025962  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025967  mov     [rbp+2F0h+lpWideCharStr+8], r15
0x14002596b  mov     rcx, [rbp+2F0h+lpWideCharStr]; lpMem
0x14002596f  test    rcx, rcx
0x140025972  jz      short loc_14002597D
0x140025974  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x140025979  mov     [rbp+2F0h+lpWideCharStr], r15
0x14002597d  mov     rcx, [rbp+2F0h+var_320]; lpMem
0x140025981  test    rcx, rcx
0x140025984  jz      short loc_14002598B
0x140025986  call    ?SusFree@@YAXPEAX@Z; SusFree(void *)
0x14002598b  mov     eax, edi
0x14002598d  mov     rcx, [rbp+2F0h+var_50]
0x140025994  xor     rcx, rsp; StackCookie
0x140025997  call    __security_check_cookie
0x14002599c  add     rsp, 3B8h
0x1400259a3  pop     r15
0x1400259a5  pop     r14
0x1400259a7  pop     r13
0x1400259a9  pop     r12
0x1400259ab  pop     rdi
  ... truncated ...
```
