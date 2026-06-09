# Csi::CSoapWebService::Init(wchar_t const *,wchar_t const *,IAsyncSoapCallback *,bool,bool)

- ea: `0x18048dad0`
- end: `0x18048f3f2`
- name: `?Init@CSoapWebService@Csi@@UEAAJPEB_W0PEAUIAsyncSoapCallback@@_N2@Z`
- size: `6434`
- prototype: `__int64 __fastcall(Csi::CSoapWebService *__hidden this, const wchar_t *, const wchar_t *, struct IAsyncSoapCallback *, bool, bool)`
- caller_count: `0`
- callee_count: `22`
- tags: `loader_planting, service_task, broker_com_uri`

## callees

- `0x18001cff0`
- `0x18003afb0`
- `0x18003b080`
- `0x18003b330`
- `0x180044ad0`
- `0x18006e208`
- `0x1801907f4`
- `0x180192520`
- `0x180192560`
- `0x1801e20d4`
- `0x1801e2734`
- `0x1801e2948`
- `0x1801e29b0`
- `0x1801e2bc8`
- `0x1801e36fc`
- `0x18048dad0`
- `0x18048f3f4`
- `0x18048f4dc`
- `0x18048f5a0`
- `0x18048f5d8`
- `0x18048f5fc`
- `0x1806802fc`

## import_xrefs

- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18048dc6c`
- `Mso20Win32Client!__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z` at `0x18048dc6c`
- `Mso20Win32Client!__imp_?GetAPI@Http@Mso@@YAAEAUIThreadNetworkContextFactory@12@XZ` at `0x18048dc02`
- `Mso20Win32Client!__imp_?GetAPI@Http@Mso@@YAAEAUIThreadNetworkContextFactory@12@XZ` at `0x18048dc02`
- `Mso20Win32Client!__imp_?MsoPwchStrStrRightFast@@YAPEB_WPEB_WH0H@Z` at `0x18048e194`
- `Mso20Win32Client!__imp_?MsoPwchStrStrRightFast@@YAPEB_WPEB_WH0H@Z` at `0x18048e1d4`
- `Mso20Win32Client!__imp_?MsoPwchStrStrRightFast@@YAPEB_WPEB_WH0H@Z` at `0x18048e194`
- `Mso20Win32Client!__imp_?MsoPwchStrStrRightFast@@YAPEB_WPEB_WH0H@Z` at `0x18048e1d4`
- `Mso20Win32Client!__imp_?WzGetCurrentUserAgentAppName@Http@Mso@@YAPEB_WXZ` at `0x18048e39d`
- `Mso20Win32Client!__imp_?WzGetCurrentUserAgentAppName@Http@Mso@@YAPEB_WXZ` at `0x18048e39d`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x18048db7b`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x18048dd3a`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x18048e20d`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x18048db7b`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x18048dd3a`
- `Mso20Win32Client!__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z` at `0x18048e20d`
- `webservices!WsOpenServiceProxy` at `0x18048f275`
- `webservices!WsOpenServiceProxy` at `0x18048f275`
- `webservices!WsCreateServiceProxy` at `0x18048e6fc`
- `webservices!WsCreateServiceProxy` at `0x18048e8b9`
- `webservices!WsCreateServiceProxy` at `0x18048f160`
- `webservices!WsCreateServiceProxy` at `0x18048e6fc`
- `webservices!WsCreateServiceProxy` at `0x18048e8b9`
- `webservices!WsCreateServiceProxy` at `0x18048f160`
- `webservices!WsCreateHeap` at `0x18048deb9`
- `webservices!WsCreateHeap` at `0x18048deb9`
- `webservices!WsCreateError` at `0x18048de60`
- `webservices!WsCreateError` at `0x18048de60`

## string_xrefs

- `0x18048e4ca`: `CSoapWebService::Init() Detecting the proxy auth scheme.`
- `0x18048e41f`: `CSoapWebService::Init() Detecting the auth scheme.`
- `0x18048dfe4`: `CSoapWebService::Init() Setting the auth scheme to anonymous`
- `0x18048dd66`: `CSoapWebService::Init() Failed to create Url`
- `0x18048de32`: `CSoapWebService::Init() Failed to get server`
- `0x18048e756`: `Failed to create a service proxy for the request`
- `0x18048e913`: `Failed to create a service proxy for the request`
- `0x18048f1ba`: `Failed to create a service proxy for the request`
- `0x18048de88`: `Unable to create an error for the SOAP Call`
- `0x18048eb49`: `CSoapWebService::Init() FAuthSchemeNeedsCreds. Using Secure Credential.`
- `0x18048eb69`: `CSoapWebService::Init() FAuthSchemeNeedsCreds. Using Windows Default Credential.`
- `0x18048ea5d`: `CSoapWebService::Init() Mapping AUTHSCHEME to WS Auth Scheme.`
- `0x18048edbe`: `CSoapWebService::Init() NeedsProxyAuth Using Windows Default Credential.`
- `0x18048eef0`: `CSoapWebService::Init() Ignore SSL Binding.`
- `0x18048ecaf`: `CSoapWebService::Init() Mapping Proxy AUTHSCHEME to WS Auth Scheme.`
- `0x18048ed9e`: `CSoapWebService::Init() NeedsProxyAuth Using Secure Credential.`
- `0x18048ef53`: `CSoapWebService::Init() Use Certificate.`
- `0x18048f063`: `CSoapWebService::Init() Not using https.`
- `0x18048f32c`: `Call completed Synchronously even though even though we expected async`
- `0x18048f2cf`: `CSoapWebService::Init() WsOpenServiceProxy`
- `0x18048df60`: `Unable to create a heap for the SOAP Call`
- `0x18048e2b7`: `Failed to create url.`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Csi::CSoapWebService::Init(
        Csi::CSoapWebService *this,
        const wchar_t *a2,
        const wchar_t *a3,
        struct IAsyncSoapCallback *a4,
        bool a5,
        bool a6)
{
  __int64 result; // rax
  __int64 v10; // rcx
  __int64 v11; // r15
  __int64 v12; // rax
  __int64 v13; // rcx
  __int64 v14; // rax
  Mso::Http *v15; // rcx
  __int64 v16; // rax
  struct Mso::Http::IThreadNetworkContextFactory *API; // rax
  __int64 Instance; // rax
  __int64 v19; // r12
  __int64 v20; // rax
  __m128i si128; // xmm6
  HRESULT Error; // ebx
  int v23; // r9d
  const char *v24; // rax
  int v25; // ecx
  const wchar_t *v26; // rcx
  HRESULT Heap; // eax
  int v28; // r9d
  int v29; // eax
  _BYTE *v30; // rcx
  Mso::Http *v31; // rcx
  unsigned int v32; // ebx
  __int64 v33; // r8
  int v34; // eax
  int v35; // r9d
  __int64 v36; // rdx
  const wchar_t *v37; // rax
  __int64 v38; // rdx
  const wchar_t *v39; // rax
  int v40; // eax
  int v41; // r9d
  struct IMsoUrl *v42; // rbx
  struct IMsoUrl *v43; // rdx
  struct COfficeCredStore *v44; // rdi
  void (__fastcall *v45)(struct COfficeCredStore *, struct IMsoUrl *, const wchar_t *, __int64); // rbx
  const wchar_t *CurrentUserAgentAppName; // rax
  __int64 v47; // r9
  unsigned int v48; // r13d
  char v49; // al
  char v50; // r13
  struct IMsoUrl *v51; // rdx
  __int128 *v52; // r15
  WS_SERVICE_PROXY **v53; // r12
  HRESULT v54; // eax
  int v55; // r9d
  WS_SECURITY_DESCRIPTION *v56; // rdi
  __int64 v57; // rax
  WS_SECURITY_DESCRIPTION *v58; // rbx
  __int64 v59; // rax
  HRESULT v60; // eax
  int v61; // r9d
  __int128 v62; // xmm0
  unsigned int v63; // eax
  int v64; // r9d
  __int64 v65; // rdx
  int v66; // r12d
  const wchar_t *UserName; // rbx
  const wchar_t *Password; // rax
  const wchar_t *v69; // rdx
  __int64 v70; // rcx
  __int64 v71; // rax
  int *v72; // rbx
  const char *v73; // rax
  int v74; // ecx
  __int128 v75; // xmm0
  unsigned int v76; // eax
  int v77; // r8d
  int v78; // r9d
  char v79; // bl
  __int128 *v80; // r8
  const wchar_t *v81; // rbx
  const wchar_t *v82; // rax
  __int64 v83; // rcx
  int *v84; // rbx
  const char *v85; // rax
  int v86; // ecx
  int v87; // r15d
  char v88; // al
  char v89; // al
  __int128 *v90; // rax
  __int128 *v91; // rax
  WS_SECURITY_DESCRIPTION *v92; // rax
  __int128 *v93; // rax
  const WS_SECURITY_DESCRIPTION *p_p_p_securityDescription; // r8
  HRESULT v95; // eax
  int v96; // r9d
  HRESULT v97; // eax
  int v98; // r9d
  __int64 v99; // rcx
  const char *v100; // [rsp+50h] [rbp-B0h] BYREF
  const char *v101; // [rsp+58h] [rbp-A8h] BYREF
  struct IMsoUrl *v102; // [rsp+60h] [rbp-A0h] BYREF
  char v103; // [rsp+68h] [rbp-98h]
  WS_CHANNEL_PROPERTY *channelProperties[2]; // [rsp+70h] [rbp-90h] BYREF
  int v105; // [rsp+80h] [rbp-80h] BYREF
  __int64 v106; // [rsp+88h] [rbp-78h]
  WS_PROXY_PROPERTY properties; // [rsp+90h] [rbp-70h] BYREF
  int v108; // [rsp+A8h] [rbp-58h] BYREF
  int v109; // [rsp+ACh] [rbp-54h] BYREF
  unsigned int v110; // [rsp+B0h] [rbp-50h]
  int v111; // [rsp+B4h] [rbp-4Ch]
  __int128 v112; // [rsp+B8h] [rbp-48h] BYREF
  __int64 v113; // [rsp+C8h] [rbp-38h]
  unsigned int v114; // [rsp+D0h] [rbp-30h] BYREF
  unsigned int v115; // [rsp+D4h] [rbp-2Ch] BYREF
  __int128 *v116; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v117[16]; // [rsp+E0h] [rbp-20h] BYREF
  __int64 v118; // [rsp+F0h] [rbp-10h]
  __int128 v119; // [rsp+F8h] [rbp-8h] BYREF
  __int128 v120; // [rsp+108h] [rbp+8h]
  WS_SECURITY_DESCRIPTION **p_p_securityDescription; // [rsp+118h] [rbp+18h] BYREF
  int v122; // [rsp+120h] [rbp+20h]
  __int128 v123; // [rsp+124h] [rbp+24h]
  int v124; // [rsp+134h] [rbp+34h]
  __int64 v125; // [rsp+138h] [rbp+38h] BYREF
  __int128 v126; // [rsp+140h] [rbp+40h] BYREF
  __int128 v127; // [rsp+150h] [rbp+50h]
  __int64 v128; // [rsp+160h] [rbp+60h]
  WS_SECURITY_DESCRIPTION securityDescription; // [rsp+168h] [rbp+68h] BYREF
  __int64 v130; // [rsp+188h] [rbp+88h]
  __int128 v131; // [rsp+190h] [rbp+90h] BYREF
  __int64 v132; // [rsp+1A0h] [rbp+A0h]
  __int128 v133; // [rsp+1A8h] [rbp+A8h] BYREF
  __int64 v134; // [rsp+1B8h] [rbp+B8h]
  WS_PROXY_PROPERTY v135; // [rsp+1C0h] [rbp+C0h] BYREF
  __int128 v136; // [rsp+1D8h] [rbp+D8h] BYREF
  __int128 v137; // [rsp+1E8h] [rbp+E8h]
  __int128 v138; // [rsp+1F8h] [rbp+F8h]
  __int128 v139; // [rsp+208h] [rbp+108h] BYREF
  __int128 v140; // [rsp+218h] [rbp+118h]
  __int128 v141; // [rsp+228h] [rbp+128h]
  __int64 v142; // [rsp+238h] [rbp+138h]
  __int64 v143; // [rsp+250h] [rbp+150h]
  _OWORD v144[2]; // [rsp+258h] [rbp+158h] BYREF
  __int64 v145; // [rsp+278h] [rbp+178h]
  void **v146; // [rsp+280h] [rbp+180h] BYREF
  const char *v147; // [rsp+288h] [rbp+188h]
  __int64 v148; // [rsp+290h] [rbp+190h]
  _BYTE v149[40]; // [rsp+298h] [rbp+198h] BYREF
  __int128 v150; // [rsp+2C0h] [rbp+1C0h] BYREF
  _BYTE v151[48]; // [rsp+2D0h] [rbp+1D0h] BYREF
  void **v152; // [rsp+300h] [rbp+200h] BYREF
  const char *v153; // [rsp+308h] [rbp+208h]
  __int64 v154; // [rsp+310h] [rbp+210h]
  __int16 v155; // [rsp+318h] [rbp+218h]
  __int128 v156; // [rsp+320h] [rbp+220h] BYREF
  __m128i v157; // [rsp+330h] [rbp+230h]
  void ***v158; // [rsp+340h] [rbp+240h]
  const wchar_t *v159; // [rsp+348h] [rbp+248h]
  int v160; // [rsp+350h] [rbp+250h]
  _WORD v161[2092]; // [rsp+358h] [rbp+258h] BYREF
  WS_SECURITY_DESCRIPTION *p_securityDescription; // [rsp+13B0h] [rbp+12B0h] BYREF
  __int128 *v163; // [rsp+13B8h] [rbp+12B8h]
  __int128 *v164; // [rsp+13C0h] [rbp+12C0h]

  *((_BYTE *)this + 269) = a4 != 0;
  *((_QWORD *)this + 34) = a4;
  *((_BYTE *)this + 268) = 1;
  MsoCF::Strings::FCopyWzToWz(a2, (char *)this + 280);
  MsoCF::Strings::FCopyWzToWz(a2, (char *)this + 312);
  if ( !a3 )
    a3 = a2;
  result = MsoHrCreateUrlSimpleFromUser((char *)this + 304, a3, 1200, 0, 0, 0);
  if ( (int)result >= 0 )
  {
    v10 = *((_QWORD *)this + 36);
    v11 = -1;
    if ( v10 )
    {
      v12 = -1;
      do
        ++v12;
      while ( *(_WORD *)(v10 + 2 * v12) );
    }
    else
    {
      LODWORD(v12) = 0;
    }
    *(_WORD *)(v10 + 2LL * (int)v12) = 0;
    v13 = *((_QWORD *)this + 40);
    if ( v13 )
    {
      v14 = -1;
      do
        ++v14;
      while ( *(_WORD *)(v13 + 2 * v14) );
    }
    else
    {
      LODWORD(v14) = 0;
    }
    *(_WORD *)(v13 + 2LL * (int)v14) = 0;
    v15 = (Mso::Http *)*((_QWORD *)this + 36);
    *((_QWORD *)this + 107) = v15;
    if ( v15 )
    {
      v16 = -1;
      do
        ++v16;
      while ( *((_WORD *)v15 + v16) );
    }
    else
    {
      LODWORD(v16) = 0;
    }
    *((_DWORD *)this + 212) = v16;
    API = Mso::Http::GetAPI(v15);
    (**(void (__fastcall ***)(struct Mso::Http::IThreadNetworkContextFactory *, __int64 *, _QWORD))API)(
      API,
      &v125,
      *((_QWORD *)this + 38));
    *((_OWORD *)this + 14) = *((_OWORD *)this + 53);
    v130 = 0;
    Instance = MsoCF::CJotComObject<CPlatformSpecficHelpersForSapphire_Win,MsoCF::CAllocatorOnNew>::CreateInstance();
    v19 = Instance;
    v106 = Instance;
    if ( Instance )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)Instance + 8LL))(Instance);
    v130 = v19;
    if ( !v19 )
    {
      CrashWithRecovery(0x1807220u, 0);
      __debugbreak();
    }
    v102 = 0;
    v108 = 255;
    v20 = *((_QWORD *)this + 36);
    v146 = &Mso::Authentication::Logging::Structured::Email::`vftable';
    v147 = "url";
    v148 = v20;
    *(_WORD *)v149 = 16;
    *(_OWORD *)&v149[8] = 0;
    si128 = _mm_load_si128((const __m128i *)&_xmm);
    *(__m128i *)&v149[24] = si128;
    *(_WORD *)&v149[8] = 0;
    channelProperties[0] = (WS_CHANNEL_PROPERTY *)"Creating the SOAP call";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
      6566303,
      434,
      50,
      2,
      (__int64)channelProperties,
      (__int64)&v146);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v149[8]);
    Error = MsoHrCreateUrlSimpleFromUser(&v102, *((_QWORD *)this + 36), 1200, 0, 0, 0);
    if ( Error < 0 )
    {
      v147 = "HRESULT";
      v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
      v24 = "CSoapWebService::Init() Failed to create Url";
      v25 = 559464860;
LABEL_25:
      channelProperties[0] = (WS_CHANNEL_PROPERTY *)v24;
      memset(v149, 0, 24);
      LODWORD(v148) = Error;
      *(_QWORD *)&v149[24] = 7;
      *(_WORD *)v149 = 0;
      *(_WORD *)&v149[32] = 4;
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
        v25,
        434,
        10,
        v23,
        (__int64)channelProperties,
        (__int64)&v146);
LABEL_26:
      Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
LABEL_175:
      CsiSoapLogIfError(v26, *((struct _WS_ERROR **)this + 5));
      if ( v102 )
        (*(void (__fastcall **)(struct IMsoUrl *))(*(_QWORD *)v102 + 16LL))(v102);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
      v99 = v125;
      if ( v125 )
      {
        v125 = 0;
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v99 + 8LL))(v99);
      }
      return (unsigned int)Error;
    }
    Error = (*(__int64 (__fastcall **)(struct IMsoUrl *, char *, int *))(*(_QWORD *)v102 + 192LL))(
              v102,
              (char *)this + 336,
              &v108);
    *((_WORD *)this + v108 + 168) = 0;
    if ( Error < 0 )
    {
      v147 = "HRESULT";
      v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
      v24 = "CSoapWebService::Init() Failed to get server";
      v25 = 559464858;
      goto LABEL_25;
    }
    channelProperties[0] = (WS_CHANNEL_PROPERTY *)(*(__int64 (__fastcall **)(Csi::CSoapWebService *))(*(_QWORD *)this + 80LL))(this);
    Error = WsCreateError(0, 0, (WS_ERROR **)this + 5);
    if ( Error < 0 )
    {
      v147 = "HRESULT";
      v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
      v24 = "Unable to create an error for the SOAP Call";
      v25 = 6566304;
      goto LABEL_25;
    }
    Heap = WsCreateHeap(*((unsigned int *)this + 8), 0x200u, 0, 0, (WS_HEAP **)this + 3, *((WS_ERROR **)this + 5));
    Error = Heap;
    if ( Heap < 0 )
    {
      v147 = "HRESULT";
      LODWORD(v148) = Heap;
      memset(v149, 0, 24);
      *(_QWORD *)&v149[24] = 7;
      *(_WORD *)v149 = 0;
      *(_WORD *)&v149[32] = 4;
      v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
      v29 = *((_DWORD *)this + 8);
      *(_QWORD *)&v150 = &Mso::Authentication::Logging::Structured::LibraryType::`vftable';
      *((_QWORD *)&v150 + 1) = "HeapSizeInBytes";
      *(_DWORD *)v151 = v29;
      *(_WORD *)&v151[4] = 4;
      *(_OWORD *)&v151[8] = 0;
      *(__m128i *)&v151[24] = si128;
      *(_WORD *)&v151[8] = 0;
      channelProperties[0] = (WS_CHANNEL_PROPERTY *)"Unable to create a heap for the SOAP Call";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
        6566305,
        434,
        100,
        v28,
        (__int64)channelProperties,
        (__int64)&v150,
        (__int64)&v146);
      v30 = &v151[8];
LABEL_33:
      Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v30);
      goto LABEL_26;
    }
    v111 = (*(__int64 (__fastcall **)(struct IMsoUrl *))(*(_QWORD *)v102 + 152LL))(v102);
    if ( a5 )
    {
      v32 = 128;
      v101 = "CSoapWebService::Init() Setting the auth scheme to anonymous";
      Mso::Diagnostics::SendDiagnosticTrace<>(559464854, 434, 50, 2, (__int64)&v101);
    }
    else
    {
      if ( a6 )
      {
        v158 = &off_180F81D90;
        v159 = v161;
        v160 = 4170;
        v161[0] = 0;
        v105 = 2085;
        v34 = (*(__int64 (__fastcall **)(struct IMsoUrl *, __int64, _WORD *, int *, _DWORD))(*(_QWORD *)v102 + 112LL))(
                v102,
                255,
                v161,
                &v105,
                0);
        Error = v34;
        if ( v34 < 0 )
        {
          v147 = "HRESULT";
          LODWORD(v148) = v34;
          memset(v149, 0, 24);
          *(_QWORD *)&v149[24] = 7;
          *(_WORD *)v149 = 0;
          *(_WORD *)&v149[32] = 4;
          v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
          *(_QWORD *)&v150 = &Mso::Authentication::Logging::Structured::Email::`vftable';
          *((_QWORD *)&v150 + 1) = "url";
          *(_QWORD *)v151 = v159;
          *(_WORD *)&v151[8] = 16;
          *(_OWORD *)&v151[16] = 0;
          *(__m128i *)&v151[32] = si128;
          *(_WORD *)&v151[16] = 0;
          channelProperties[0] = (WS_CHANNEL_PROPERTY *)"Failed to get url.";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
            6566306,
            434,
            10,
            v35,
            (__int64)channelProperties,
            (__int64)&v150,
            (__int64)&v146);
          v30 = &v151[16];
          goto LABEL_33;
        }
        if ( v159 )
        {
          v36 = -1;
          do
            ++v36;
          while ( v159[v36] );
        }
        else
        {
          LODWORD(v36) = 0;
        }
        v37 = MsoPwchStrStrRightFast(v159, v36, L"_vti_bin/lists.asmx", 19);
        if ( v37 && *v37 )
          *v37 = 0;
        if ( v159 )
        {
          v38 = -1;
          do
            ++v38;
          while ( v159[v38] );
        }
        else
        {
          LODWORD(v38) = 0;
        }
        v39 = MsoPwchStrStrRightFast(v159, v38, L"_vti_bin/webs.asmx", 18);
        if ( v39 && *v39 )
          *v39 = 0;
        v101 = 0;
        v40 = MsoHrCreateUrlSimpleFromUser(&v101, v159, 1200, 0, 0, 0);
        Error = v40;
        if ( v40 < 0 )
        {
          v147 = "HRESULT";
          LODWORD(v148) = v40;
          memset(v149, 0, 24);
          *(_QWORD *)&v149[24] = 7;
          *(_WORD *)v149 = 0;
          *(_WORD *)&v149[32] = 4;
          v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
          *(_QWORD *)&v150 = &Mso::Authentication::Logging::Structured::Email::`vftable';
          *((_QWORD *)&v150 + 1) = "url";
          *(_QWORD *)v151 = v159;
          *(_WORD *)&v151[8] = 16;
          *(_OWORD *)&v151[16] = 0;
          *(__m128i *)&v151[32] = si128;
          *(_WORD *)&v151[16] = 0;
          channelProperties[0] = (WS_CHANNEL_PROPERTY *)"Failed to create url.";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
            6566307,
            434,
            10,
            v41,
            (__int64)channelProperties,
            (__int64)&v150,
            (__int64)&v146);
          Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v151[16]);
          Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
          v26 = (const wchar_t *)v101;
          if ( v101 )
            (*(void (__fastcall **)(const char *))(*(_QWORD *)v101 + 16LL))(v101);
          goto LABEL_175;
        }
        v31 = (Mso::Http *)v101;
        v42 = (struct IMsoUrl *)v101;
        if ( v101 )
        {
          (*(void (__fastcall **)(const char *))(*(_QWORD *)v101 + 8LL))(v101);
          v31 = (Mso::Http *)v101;
        }
        v43 = v102;
        v102 = v42;
        if ( v43 )
        {
          (*(void (__fastcall **)(struct IMsoUrl *))(*(_QWORD *)v43 + 16LL))(v43);
          v31 = (Mso::Http *)v101;
        }
        if ( v31 )
          (*(void (__fastcall **)(Mso::Http *))(*(_QWORD *)v31 + 16LL))(v31);
      }
      if ( v102 )
      {
        v44 = COfficeCredStore::s_pocs;
        v45 = *(void (__fastcall **)(struct COfficeCredStore *, struct IMsoUrl *, const wchar_t *, __int64))(*(_QWORD *)COfficeCredStore::s_pocs + 176LL);
        CurrentUserAgentAppName = Mso::Http::WzGetCurrentUserAgentAppName(v31);
        LOBYTE(v47) = 1;
        v45(v44, v102, CurrentUserAgentAppName, v47);
      }
      v32 = (*(__int64 (__fastcall **)(struct COfficeCredStore *, struct IMsoUrl *, _QWORD))(*(_QWORD *)COfficeCredStore::s_pocs
                                                                                           + 160LL))(
              COfficeCredStore::s_pocs,
              v102,
              0);
      *(_QWORD *)&v150 = &Mso::Authentication::Logging::Structured::LibraryType::`vftable';
      *((_QWORD *)&v150 + 1) = "AuthScheme";
      *(_DWORD *)v151 = v32;
      *(_WORD *)&v151[4] = 4;
      *(_OWORD *)&v151[8] = 0;
      *(__m128i *)&v151[24] = si128;
      *(_WORD *)&v151[8] = 0;
      v101 = "CSoapWebService::Init() Detecting the auth scheme.";
      Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
        559464850,
        434,
        50,
        2,
        (__int64)&v101,
        (__int64)&v150);
      Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v151[8]);
    }
    LOBYTE(v33) = 1;
    v48 = (*(__int64 (__fastcall **)(struct COfficeCredStore *, struct IMsoUrl *, __int64))(*(_QWORD *)COfficeCredStore::s_pocs
                                                                                          + 160LL))(
            COfficeCredStore::s_pocs,
            v102,
            v33);
    v110 = v48;
    *(_QWORD *)&v150 = &Mso::Authentication::Logging::Structured::LibraryType::`vftable';
    *((_QWORD *)&v150 + 1) = "ProxyAuthScheme";
    *(_DWORD *)v151 = v48;
    *(_WORD *)&v151[4] = 4;
    *(_OWORD *)&v151[8] = 0;
    *(__m128i *)&v151[24] = si128;
    *(_WORD *)&v151[8] = 0;
    v101 = "CSoapWebService::Init() Detecting the proxy auth scheme.";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(
      559464848,
      434,
      50,
      2,
      (__int64)&v101,
      (__int64)&v150);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v151[8]);
    v103 = Mso::WebServices::AuthHelper::FAuthSchemeNeedsCreds(v32);
    if ( v103 )
    {
      v50 = 0;
    }
    else
    {
      v49 = Mso::WebServices::AuthHelper::NeedsProxyAuth(v48);
      v50 = 0;
      if ( !v49 )
      {
        if ( v111 == 1 )
        {
          memset(&securityDescription.securityBindingCount + 1, 0, 20);
          v112 = 0;
          v113 = 0;
          v119 = 0;
          v120 = 0;
          v126 = 0;
          v127 = 0;
          v128 = 0;
          LODWORD(v119) = 1;
          v51 = v102;
          if ( v102 )
          {
            if ( (*(unsigned __int8 (__fastcall **)(struct COfficeCredStore *))(*(_QWORD *)COfficeCredStore::s_pocs
                                                                              + 200LL))(COfficeCredStore::s_pocs) )
            {
              v118 = 0;
              *(_QWORD *)&v112 = 20;
              *((_QWORD *)&v112 + 1) = &unk_180F90B20;
              v113 = 4;
              *((_QWORD *)&v119 + 1) = &v112;
              LODWORD(v120) = 1;
              v101 = "InitChannel setting ignore invalid cert flag(2)";
              Mso::Diagnostics::SendDiagnosticTrace<>(6566337, 434, 50, 2, (__int64)&v101);
            }
            v51 = v102;
          }
          p_securityDescription = 0;
          v163 = 0;
          LOBYTE(v164) = 0;
          CSecureCredHandler::Init((CSecureCredHandler *)&p_securityDescription, v51, 0);
          v52 = v163;
          if ( v163 && (*(unsigned __int8 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v19 + 24LL))(v19, &v126) )
          {
            *((_QWORD *)&v120 + 1) = &v126;
            v101 = "InitChannel Using Custom Credential.";
            Mso::Diagnostics::SendDiagnosticTrace<>(559464798, 434, 50, 2, (__int64)&v101);
          }
          v116 = &v119;
          securityDescription.securityBindings = (WS_SECURITY_BINDING **)&v116;
          securityDescription.securityBindingCount = 1;
          v118 = 0;
          *((_DWORD *)&properties.id + 1) = 0;
          *(&properties.valueSize + 1) = 0;
          properties.id = WS_PROXY_PROPERTY_CALL_TIMEOUT;
          properties.value = (char *)this + 76;
          properties.valueSize = 4;
          v53 = (WS_SERVICE_PROXY **)((char *)this + 16);
          v54 = WsCreateServiceProxy(
                  WS_CHANNEL_TYPE_REQUEST,
                  WS_HTTP_CHANNEL_BINDING,
                  &securityDescription,
                  &properties,
                  1u,
                  channelProperties[0],
                  *((_DWORD *)this + 14),
                  (WS_SERVICE_PROXY **)this + 2,
                  *((WS_ERROR **)this + 5));
          Error = v54;
          if ( v54 < 0 )
          {
            v147 = "HRESULT";
            LODWORD(v148) = v54;
            memset(v149, 0, 24);
            *(_QWORD *)&v149[24] = 7;
            *(_WORD *)v149 = 0;
            *(_WORD *)&v149[32] = 4;
            v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
            channelProperties[0] = (WS_CHANNEL_PROPERTY *)"Failed to create a service proxy for the request";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
              6566338,
              434,
              10,
              v55,
              (__int64)channelProperties,
              (__int64)&v146);
            Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
            v56 = p_securityDescription;
            if ( p_securityDescription && (_BYTE)v164 )
            {
              v57 = Mso::TCntPtr<Csi::IWopiContainerMetadata>::operator->(&p_securityDescription);
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v57 + 48LL))(v57);
            }
            if ( v52 )
              (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v52 + 8LL))(v52);
            if ( v56 )
              (*((void (__fastcall **)(WS_SECURITY_DESCRIPTION *))v56->securityBindings + 1))(v56);
            goto LABEL_174;
          }
          v58 = p_securityDescription;
          if ( p_securityDescription && (_BYTE)v164 )
          {
            v59 = Mso::TCntPtr<Csi::IWopiContainerMetadata>::operator->(&p_securityDescription);
            (*(void (__fastcall **)(__int64))(*(_QWORD *)v59 + 48LL))(v59);
          }
          if ( v52 )
            (*(void (__fastcall **)(__int128 *))(*(_QWORD *)v52 + 8LL))(v52);
          if ( v58 )
            (*((void (__fastcall **)(WS_SECURITY_DESCRIPTION *))v58->securityBindings + 1))(v58);
LABEL_166:
          *(_OWORD *)channelProperties = 0;
          if ( *((_BYTE *)this + 269) )
            (*(void (__fastcall **)(Csi::CSoapWebService *, _QWORD, WS_CHANNEL_PROPERTY **, _QWORD))(*(_QWORD *)this + 48LL))(
              this,
              0,
              channelProperties,
              *((_QWORD *)this + 34));
          v97 = WsOpenServiceProxy(
                  *v53,
                  (const WS_ENDPOINT_ADDRESS *)((char *)this + 224),
                  (const WS_ASYNC_CONTEXT *)((unsigned __int64)channelProperties
                                           & -(__int64)(*((_BYTE *)this + 269) != 0)),
                  *((WS_ERROR **)this + 5));
          Error = v97;
          if ( v97 < 0 )
          {
            v147 = "HRESULT";
            LODWORD(v148) = v97;
            memset(v149, 0, 24);
            *(_QWORD *)&v149[24] = 7;
            *(_WORD *)v149 = 0;
            *(_WORD *)&v149[32] = 4;
            v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
            v100 = "CSoapWebService::Init() WsOpenServiceProxy";
            Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
              559464794,
              434,
              10,
              v98,
              (__int64)&v100,
              (__int64)&v146);
            Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
          }
          if ( *((_BYTE *)this + 269) && *((_QWORD *)this + 34) && Error != 3997696 )
          {
            v100 = "Call completed Synchronously even though even though we expected async";
            Mso::Diagnostics::SendDiagnosticTrace<>(6566340, 434, 15, 2, (__int64)&v100);
            (***((void (__fastcall ****)(_QWORD, _QWORD))this + 34))(*((_QWORD *)this + 34), (unsigned int)Error);
          }
          goto LABEL_174;
        }
        v118 = 0;
        *((_DWORD *)&properties.id + 1) = 0;
        *(&properties.valueSize + 1) = 0;
        properties.id = WS_PROXY_PROPERTY_CALL_TIMEOUT;
        properties.value = (char *)this + 76;
        properties.valueSize = 4;
        v53 = (WS_SERVICE_PROXY **)((char *)this + 16);
        v60 = WsCreateServiceProxy(
                WS_CHANNEL_TYPE_REQUEST,
                WS_HTTP_CHANNEL_BINDING,
                0,
                &properties,
                1u,
                channelProperties[0],
                *((_DWORD *)this + 14),
                (WS_SERVICE_PROXY **)this + 2,
                *((WS_ERROR **)this + 5));
        Error = v60;
        if ( v60 >= 0 )
          goto LABEL_166;
        v147 = "HRESULT";
        LODWORD(v148) = v60;
        memset(v149, 0, 24);
        *(_QWORD *)&v149[24] = 7;
        *(_WORD *)v149 = 0;
        *(_WORD *)&v149[32] = 4;
        v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
        channelProperties[0] = (WS_CHANNEL_PROPERTY *)"Failed to create a service proxy for the request";
        Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
          6566339,
          434,
          10,
          v61,
          (__int64)channelProperties,
          (__int64)&v146);
        Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
LABEL_174:
        v19 = v106;
        goto LABEL_175;
      }
    }
    v123 = 0;
    v124 = 0;
    CSecureCredHandler::CSecureCredHandler((CSecureCredHandler *)&properties, v102, 0);
    CSecureCredHandler::CSecureCredHandler((CSecureCredHandler *)v117, v102, 1);
    v62 = 0;
    v119 = 0;
    v120 = 0;
    v139 = 0;
    v140 = 0;
    v141 = 0;
    v142 = 0;
    v109 = 0;
    v131 = 0;
    v132 = 0;
    *(double *)&v62 = Mso::WebServices::AuthHelper::WsSchemeFromAuthScheme(v32, 0);
    v114 = v63;
    v152 = &Mso::Http::Logging::Structured::StatusCode::`vftable';
    v153 = "WSAuthScheme";
    v154 = v63;
    v155 = 4;
    v156 = v62;
    v157 = si128;
    LOWORD(v156) = 0;
    v146 = &Mso::Authentication::Logging::Structured::LibraryType::`vftable';
    v147 = "AuthScheme";
    LODWORD(v148) = v32;
    WORD2(v148) = 4;
    *(_OWORD *)v149 = v62;
    *(__m128i *)&v149[16] = si128;
    *(_WORD *)v149 = 0;
    v100 = "CSoapWebService::Init() Mapping AUTHSCHEME to WS Auth Scheme.";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
      559464846,
      434,
      50,
      v64,
      (__int64)&v100,
      (__int64)&v146,
      (__int64)&v152);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v156);
    v66 = 3;
    if ( v103 )
    {
      if ( CSecureCredHandler::BeginAccessCreds((CSecureCredHandler *)&properties) )
      {
        UserName = CSecureCredHandler::WzGetUserName((CSecureCredHandler *)&properties);
        Password = CSecureCredHandler::WzGetPassword((CSecureCredHandler *)&properties);
        v69 = Password;
        LODWORD(v139) = 1;
        *(_QWORD *)&v140 = UserName;
        if ( UserName )
        {
          v70 = -1;
          do
            ++v70;
          while ( UserName[v70] );
        }
        else
        {
          LODWORD(v70) = 0;
        }
        DWORD2(v139) = v70;
        *(_QWORD *)&v141 = Password;
        if ( Password )
        {
          v71 = -1;
          do
            ++v71;
          while ( v69[v71] );
        }
        else
        {
          LODWORD(v71) = 0;
        }
        DWORD2(v140) = v71;
        v72 = (int *)&v139;
        v73 = "CSoapWebService::Init() FAuthSchemeNeedsCreds. Using Secure Credential.";
        v74 = 559464844;
      }
      else
      {
        v109 = 2;
        v72 = &v109;
        v73 = "CSoapWebService::Init() FAuthSchemeNeedsCreds. Using Windows Default Credential.";
        v74 = 559464842;
      }
      v100 = v73;
      Mso::Diagnostics::SendDiagnosticTrace<>(v74, 434, 50, 2, (__int64)&v100);
      LODWORD(v131) = 6;
      *((_QWORD *)&v131 + 1) = &v114;
      LODWORD(v132) = 4;
      LODWORD(v119) = 3;
      *((_QWORD *)&v119 + 1) = &v131;
      LODWORD(v120) = 1;
      *((_QWORD *)&v120 + 1) = v72;
      v50 = 1;
    }
    v75 = 0;
    v126 = 0;
    v127 = 0;
    LOBYTE(v65) = 1;
    *(double *)&v75 = Mso::WebServices::AuthHelper::WsSchemeFromAuthScheme(v110, v65);
    v115 = v76;
    v150 = v75;
    *(_OWORD *)v151 = v75;
    *(_OWORD *)&v151[16] = v75;
    *(_QWORD *)&v151[32] = 0;
    v136 = v75;
    v137 = v75;
    v138 = v75;
    v105 = 0;
    LODWORD(v116) = 2;
    v152 = &Mso::Http::Logging::Structured::StatusCode::`vftable';
    v153 = "WSAuthScheme";
    v154 = v76;
    v155 = 4;
    v156 = v75;
    v157 = si128;
    LOWORD(v156) = 0;
    v146 = &Mso::Authentication::Logging::Structured::LibraryType::`vftable';
    v147 = "ProxyAuthScheme";
    LODWORD(v148) = v77;
    WORD2(v148) = 4;
    *(_OWORD *)v149 = v75;
    *(__m128i *)&v149[16] = si128;
    *(_WORD *)v149 = 0;
    v100 = "CSoapWebService::Init() Mapping Proxy AUTHSCHEME to WS Auth Scheme.";
    Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>,Mso::Diagnostics::ClassifiedStructuredObject<unsigned int>>(
      559464840,
      434,
      50,
      v78,
      (__int64)&v100,
      (__int64)&v146,
      (__int64)&v152);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
    Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(&v156);
    v79 = 0;
    if ( (unsigned __int8)Mso::WebServices::AuthHelper::NeedsProxyAuth(v110) )
    {
      if ( CSecureCredHandler::BeginAccessCreds((CSecureCredHandler *)v117) )
      {
        v81 = CSecureCredHandler::WzGetUserName((CSecureCredHandler *)v117);
        v82 = CSecureCredHandler::WzGetPassword((CSecureCredHandler *)v117);
        LODWORD(v150) = 1;
        *(_QWORD *)v151 = v81;
        if ( v81 )
        {
          v83 = -1;
          do
            ++v83;
          while ( v81[v83] );
        }
        else
        {
          LODWORD(v83) = 0;
        }
        DWORD2(v150) = v83;
        *(_QWORD *)&v151[16] = v82;
        if ( v82 )
        {
          do
            ++v11;
          while ( v82[v11] );
        }
        else
        {
          LODWORD(v11) = 0;
        }
        *(_DWORD *)&v151[8] = v11;
        v84 = (int *)&v150;
        v85 = "CSoapWebService::Init() NeedsProxyAuth Using Secure Credential.";
        v86 = 559464838;
      }
      else
      {
        v105 = 2;
        v84 = &v105;
        v85 = "CSoapWebService::Init() NeedsProxyAuth Using Windows Default Credential.";
        v86 = 559464836;
      }
      v100 = v85;
      Mso::Diagnostics::SendDiagnosticTrace<>(v86, 434, 50, 2, (__int64)&v100);
      LODWORD(v136) = 6;
      *((_QWORD *)&v136 + 1) = &v115;
      LODWORD(v137) = 4;
      DWORD2(v137) = 7;
      *(_QWORD *)&v138 = &v116;
      DWORD2(v138) = 4;
      LODWORD(v126) = 3;
      *((_QWORD *)&v126 + 1) = &v136;
      LODWORD(v127) = 2;
      *((_QWORD *)&v127 + 1) = v84;
      v79 = 1;
      v80 = 0;
    }
    v164 = v80;
    v112 = 0;
    v113 = 0;
    memset(&securityDescription, 0, sizeof(securityDescription));
    memset(v144, 0, sizeof(v144));
    v145 = 0;
    v87 = v111;
    if ( v111 == 1 )
    {
      LODWORD(securityDescription.securityBindings) = 1;
      if ( v102 )
      {
        v88 = (*(__int64 (__fastcall **)(struct COfficeCredStore *))(*(_QWORD *)COfficeCredStore::s_pocs + 200LL))(COfficeCredStore::s_pocs);
        v80 = 0;
        if ( v88 )
        {
          v143 = 0;
          *(_QWORD *)&v112 = 20;
          *((_QWORD *)&v112 + 1) = &unk_180F90B20;
          v113 = 4;
          *(_QWORD *)&securityDescription.securityBindingCount = &v112;
          LODWORD(securityDescription.properties) = v87;
          v100 = "CSoapWebService::Init() Ignore SSL Binding.";
          Mso::Diagnostics::SendDiagnosticTrace<>(559464834, 434, v87 + 49, v87 + 1, (__int64)&v100);
          v80 = 0;
        }
      }
      if ( properties.value != v80 )
      {
        v89 = (*(__int64 (__fastcall **)(__int64, _OWORD *))(*(_QWORD *)v106 + 24LL))(v106, v144);
        v80 = 0;
        if ( v89 )
        {
          *(_QWORD *)&securityDescription.propertyCount = v144;
          v100 = "CSoapWebService::Init() Use Certificate.";
          Mso::Diagnostics::SendDiagnosticTrace<>(559464832, 434, 50, 2, (__int64)&v100);
          v80 = 0;
        }
      }
      p_securityDescription = &securityDescription;
      if ( v50 )
      {
        v90 = &v119;
      }
      else
      {
        if ( v79 )
        {
          v163 = &v126;
          goto LABEL_138;
        }
        v90 = v80;
      }
      v163 = v90;
      if ( v50 )
      {
        v91 = &v126;
        if ( v79 )
        {
LABEL_139:
          v164 = v91;
          p_p_securityDescription = &p_securityDescription;
          if ( v50 )
          {
            if ( !v79 )
              goto LABEL_143;
          }
          else
          {
            v66 = 1;
            if ( v79 )
LABEL_143:
              v66 = 2;
          }
          v122 = v66;
LABEL_159:
          v133 = 0;
          v134 = 0;
          LODWORD(v101) = 1;
          if ( v87 != 1 )
          {
            LODWORD(v133) = 1;
            *((_QWORD *)&v133 + 1) = &v101;
            LODWORD(v134) = 4;
            HIDWORD(v123) = 1;
            *(_QWORD *)((char *)&v123 + 4) = &v133;
          }
          v143 = 0;
          *((_DWORD *)&v135.id + 1) = 0;
          *(&v135.valueSize + 1) = 0;
          v135.id = WS_PROXY_PROPERTY_CALL_TIMEOUT;
          v135.value = (char *)this + 76;
          v135.valueSize = 4;
          p_p_p_securityDescription = (const WS_SECURITY_DESCRIPTION *)&p_p_securityDescription;
          if ( !v66 )
            p_p_p_securityDescription = 0;
          v53 = (WS_SERVICE_PROXY **)((char *)this + 16);
          v95 = WsCreateServiceProxy(
                  WS_CHANNEL_TYPE_REQUEST,
                  WS_HTTP_CHANNEL_BINDING,
                  p_p_p_securityDescription,
                  &v135,
                  1u,
                  channelProperties[0],
                  *((_DWORD *)this + 14),
                  (WS_SERVICE_PROXY **)this + 2,
                  *((WS_ERROR **)this + 5));
          Error = v95;
          if ( v95 >= 0 )
          {
            CSecureCredHandler::~CSecureCredHandler((CSecureCredHandler *)v117);
            CSecureCredHandler::~CSecureCredHandler((CSecureCredHandler *)&properties);
            goto LABEL_166;
          }
          v147 = "HRESULT";
          LODWORD(v148) = v95;
          memset(v149, 0, 24);
          *(_QWORD *)&v149[24] = 7;
          *(_WORD *)v149 = 0;
          *(_WORD *)&v149[32] = 4;
          v146 = &Mso::Diagnostics::ClassifiedStructuredHr::`vftable';
          v100 = "Failed to create a service proxy for the request";
          Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(
            6566336,
            434,
            10,
            v96,
            (__int64)&v100,
            (__int64)&v146);
          Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(v149);
          CSecureCredHandler::~CSecureCredHandler((CSecureCredHandler *)v117);
          CSecureCredHandler::~CSecureCredHandler((CSecureCredHandler *)&properties);
          goto LABEL_174;
        }
      }
LABEL_138:
      v91 = v80;
      goto LABEL_139;
    }
    if ( v50 )
    {
      v92 = (WS_SECURITY_DESCRIPTION *)&v119;
    }
    else
    {
      if ( v79 )
      {
        p_securityDescription = (WS_SECURITY_DESCRIPTION *)&v126;
        goto LABEL_152;
      }
      v92 = (WS_SECURITY_DESCRIPTION *)v80;
    }
    p_securityDescription = v92;
    if ( v50 )
    {
      v93 = &v126;
      if ( v79 )
      {
LABEL_153:
        v163 = v93;
        p_p_securityDescription = &p_securityDescription;
        if ( v50 )
        {
          if ( v79 )
          {
            v122 = 2;
LABEL_158:
            v100 = "CSoapWebService::Init() Not using https.";
            Mso::Diagnostics::SendDiagnosticTrace<>(559464802, 434, 50, 2, (__int64)&v100);
            v66 = v122;
            goto LABEL_159;
          }
        }
        else
        {
          v122 = (int)v80;
          if ( !v79 )
            goto LABEL_158;
        }
        v122 = 1;
        goto LABEL_158;
      }
    }
LABEL_152:
    v93 = v80;
    goto LABEL_153;
  }
  return result;
}

```

## disassembly

```asm
0x18048dad0  mov     [rsp-8+arg_18], rbx
0x18048dad5  push    rbp
0x18048dad6  push    rsi
0x18048dad7  push    rdi
0x18048dad8  push    r12
0x18048dada  push    r13
0x18048dadc  push    r14
0x18048dade  push    r15
0x18048dae0  lea     rbp, [rsp-12E0h]
0x18048dae8  mov     eax, 13E0h
0x18048daed  call    _alloca_probe
0x18048daf2  sub     rsp, rax
0x18048daf5  movaps  [rsp+1410h+var_40], xmm6
0x18048dafd  mov     rax, cs:__security_cookie
0x18048db04  xor     rax, rsp
0x18048db07  mov     [rbp+1310h+var_48], rax
0x18048db0e  mov     rdi, r8
0x18048db11  mov     rbx, rdx
0x18048db14  mov     rsi, rcx
0x18048db17  xor     r13d, r13d
0x18048db1a  test    r9, r9
0x18048db1d  setnz   al
0x18048db20  mov     [rcx+10Dh], al
0x18048db26  mov     [rcx+110h], r9
0x18048db2d  mov     byte ptr [rcx+10Ch], 1
0x18048db34  lea     rdx, [rcx+118h]
0x18048db3b  mov     rcx, rbx
0x18048db3e  call    ?FCopyWzToWz@Strings@MsoCF@@YA_NPEB_WAEAV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CBuffer@_W@2@@2@PEAH@Z; MsoCF::Strings::FCopyWzToWz(wchar_t const *,MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CBuffer<wchar_t>> &,int *)
0x18048db43  lea     rdx, [rsi+138h]
0x18048db4a  mov     rcx, rbx
0x18048db4d  call    ?FCopyWzToWz@Strings@MsoCF@@YA_NPEB_WAEAV?$CWzInBuffer_T@V?$String@UWzTraits@MsoCF@@@MsoCF@@V?$CBuffer@_W@2@@2@PEAH@Z; MsoCF::Strings::FCopyWzToWz(wchar_t const *,MsoCF::CWzInBuffer_T<MsoCF::String<MsoCF::WzTraits>,MsoCF::CBuffer<wchar_t>> &,int *)
0x18048db52  lea     r14, [rsi+130h]
0x18048db59  test    rdi, rdi
0x18048db5c  cmovz   rdi, rbx
0x18048db60  mov     [rsp+1410h+error], r13
0x18048db65  mov     [rsp+1410h+heap], r13
0x18048db6a  xor     r9d, r9d
0x18048db6d  mov     ebx, 4B0h
0x18048db72  mov     r8d, ebx
0x18048db75  mov     rdx, rdi
0x18048db78  mov     rcx, r14
0x18048db7b  call    cs:__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z; MsoHrCreateUrlSimpleFromUser(IMsoUrl * *,wchar_t const *,ulong,IMsoUrl const *,MsoUrlCreateFlags,IMsoMemHeap *)
0x18048db81  test    eax, eax
0x18048db83  js      loc_18048F3C3
0x18048db89  mov     rcx, [rsi+120h]
0x18048db90  or      r15, 0FFFFFFFFFFFFFFFFh
0x18048db94  test    rcx, rcx
0x18048db97  jz      short loc_18048DBA8
0x18048db99  mov     rax, r15
0x18048db9c  inc     rax
0x18048db9f  cmp     [rcx+rax*2], r13w
0x18048dba4  jnz     short loc_18048DB9C
0x18048dba6  jmp     short loc_18048DBAB
0x18048dba8  mov     rax, r13
0x18048dbab  cdqe
0x18048dbad  mov     [rcx+rax*2], r13w
0x18048dbb2  mov     rcx, [rsi+140h]
0x18048dbb9  test    rcx, rcx
0x18048dbbc  jz      short loc_18048DBCD
0x18048dbbe  mov     rax, r15
0x18048dbc1  inc     rax
0x18048dbc4  cmp     [rcx+rax*2], r13w
0x18048dbc9  jnz     short loc_18048DBC1
0x18048dbcb  jmp     short loc_18048DBD0
0x18048dbcd  mov     rax, r13
0x18048dbd0  cdqe
0x18048dbd2  mov     [rcx+rax*2], r13w
0x18048dbd7  mov     rcx, [rsi+120h]
0x18048dbde  mov     [rsi+358h], rcx
0x18048dbe5  test    rcx, rcx
0x18048dbe8  jz      short loc_18048DBF9
0x18048dbea  mov     rax, r15
0x18048dbed  inc     rax
0x18048dbf0  cmp     [rcx+rax*2], r13w
0x18048dbf5  jnz     short loc_18048DBED
0x18048dbf7  jmp     short loc_18048DBFC
0x18048dbf9  mov     rax, r13
0x18048dbfc  mov     [rsi+350h], eax
0x18048dc02  call    cs:__imp_?GetAPI@Http@Mso@@YAAEAUIThreadNetworkContextFactory@12@XZ; Mso::Http::GetAPI(void)
0x18048dc08  mov     r9, rax
0x18048dc0b  mov     rcx, [rax]
0x18048dc0e  mov     rax, [rcx]
0x18048dc11  mov     r8, [r14]
0x18048dc14  lea     rdx, [rbp+1310h+var_12D8]
0x18048dc18  mov     rcx, r9
0x18048dc1b  call    cs:__guard_dispatch_icall_fptr
0x18048dc21  nop
0x18048dc22  movups  xmm0, xmmword ptr [rsi+350h]
0x18048dc29  movdqu  xmmword ptr [rsi+0E0h], xmm0
0x18048dc31  mov     [rbp+1310h+var_1288], r13
0x18048dc38  call    ?CreateInstance@?$CJotComObject@VCPlatformSpecficHelpersForSapphire_Win@@VCAllocatorOnNew@MsoCF@@@MsoCF@@SAPEAVCPlatformSpecficHelpersForSapphire_Win@@AEAVCAllocatorOnNew@2@_N@Z; MsoCF::CJotComObject<CPlatformSpecficHelpersForSapphire_Win,MsoCF::CAllocatorOnNew>::CreateInstance(MsoCF::CAllocatorOnNew &,bool)
0x18048dc3d  mov     r12, rax
0x18048dc40  mov     [rbp+1310h+var_1388], rax
0x18048dc44  test    rax, rax
0x18048dc47  jz      short loc_18048DC59
0x18048dc49  mov     rcx, [rax]
0x18048dc4c  mov     rax, [rcx+8]
0x18048dc50  mov     rcx, r12
0x18048dc53  call    cs:__guard_dispatch_icall_fptr
0x18048dc59  mov     [rbp+1310h+var_1288], r12
0x18048dc60  test    r12, r12
0x18048dc63  jnz     short loc_18048DC73
0x18048dc65  xor     edx, edx
0x18048dc67  mov     ecx, 1807220h
0x18048dc6c  call    cs:__imp_?CrashWithRecovery@@YAXIPEAUCrashContext@@@Z; CrashWithRecovery(uint,CrashContext *)
0x18048dc72  int     3; Trap to Debugger
0x18048dc73  mov     [rsp+1410h+var_13B0], r13
0x18048dc78  mov     [rbp+1310h+var_1368], 0FFh
0x18048dc7f  mov     rax, [rsi+120h]
0x18048dc86  lea     rcx, ??_7Email@Structured@Logging@Authentication@Mso@@6B@; const Mso::Authentication::Logging::Structured::Email::`vftable'
0x18048dc8d  mov     [rbp+1310h+var_1190], rcx
0x18048dc94  lea     rcx, aUrl_3; "url"
0x18048dc9b  mov     [rbp+1310h+var_1188], rcx
0x18048dca2  mov     [rbp+1310h+var_1180], rax
0x18048dca9  mov     eax, 10h
0x18048dcae  mov     word ptr [rbp+1310h+var_1178], ax
0x18048dcb5  xorps   xmm0, xmm0
0x18048dcb8  movups  [rbp+1310h+var_1178+8], xmm0
0x18048dcbf  movdqa  xmm6, cs:__xmm@00000000000000070000000000000000
0x18048dcc7  movdqa  [rbp+1310h+var_1168+8], xmm6
0x18048dccf  mov     word ptr [rbp+1310h+var_1178+8], r13w
0x18048dcd7  lea     rax, aCreatingTheSoa; "Creating the SOAP call"
0x18048dcde  mov     [rsp+1410h+channelProperties], rax
0x18048dce3  mov     r9d, 2
0x18048dce9  lea     rax, [rbp+1310h+var_1190]
0x18048dcf0  mov     [rsp+1410h+error], rax
0x18048dcf5  lea     rax, [rsp+1410h+channelProperties]
0x18048dcfa  mov     [rsp+1410h+heap], rax
0x18048dcff  mov     edx, 1B2h
0x18048dd04  mov     ecx, 64319Fh
0x18048dd09  lea     r8d, [r9+30h]
0x18048dd0d  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@PEB_W@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@PEB_W@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<wchar_t const *> &&)
0x18048dd12  lea     rcx, [rbp+1310h+var_1178+8]; void *
0x18048dd19  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x18048dd1e  mov     [rsp+1410h+error], r13
0x18048dd23  mov     [rsp+1410h+heap], r13
0x18048dd28  xor     r9d, r9d
0x18048dd2b  mov     r8d, ebx
0x18048dd2e  mov     rdx, [rsi+120h]
0x18048dd35  lea     rcx, [rsp+1410h+var_13B0]
0x18048dd3a  call    cs:__imp_?MsoHrCreateUrlSimpleFromUser@@YAJPEAPEAUIMsoUrl@@PEB_WKPEBU1@W4MsoUrlCreateFlags@@PEAUIMsoMemHeap@@@Z; MsoHrCreateUrlSimpleFromUser(IMsoUrl * *,wchar_t const *,ulong,IMsoUrl const *,MsoUrlCreateFlags,IMsoMemHeap *)
0x18048dd40  mov     ebx, eax
0x18048dd42  test    eax, eax
0x18048dd44  jns     loc_18048DDE3
0x18048dd4a  lea     rax, aHresult_0; "HRESULT"
0x18048dd51  mov     [rbp+1310h+var_1188], rax
0x18048dd58  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18048dd5f  mov     [rbp+1310h+var_1190], rax
0x18048dd66  lea     rax, aCsoapwebservic_20; "CSoapWebService::Init() Failed to creat"...
0x18048dd6d  mov     ecx, 2158C19Ch
0x18048dd72  mov     [rsp+1410h+channelProperties], rax
0x18048dd77  lea     rax, [rbp+1310h+var_1190]
0x18048dd7e  xorps   xmm0, xmm0
0x18048dd81  mov     [rsp+1410h+error], rax
0x18048dd86  mov     edi, 7
0x18048dd8b  movups  [rbp+1310h+var_1178], xmm0
0x18048dd92  lea     r14d, [rdi-3]
0x18048dd96  lea     rax, [rsp+1410h+channelProperties]
0x18048dd9b  mov     dword ptr [rbp+1310h+var_1180], ebx
0x18048dda1  mov     qword ptr [rbp+1310h+var_1168], r13
0x18048dda8  mov     qword ptr [rbp+1310h+var_1168+8], rdi
0x18048ddaf  mov     word ptr [rbp+1310h+var_1178], r13w
0x18048ddb7  mov     [rbp+1310h+var_1158], r14w
0x18048ddbf  mov     [rsp+1410h+heap], rax
0x18048ddc4  mov     edx, 1B2h
0x18048ddc9  lea     r8d, [rdi+3]
0x18048ddcd  call    ??$SendDiagnosticTrace@V?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@Diagnostics@Mso@@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAV?$ToClassifiedStructured@VServiceParams@Authentication@Mso@@@01@@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ToClassifiedStructured<Mso::Authentication::ServiceParams> &&)
0x18048ddd2  lea     rcx, [rbp+1310h+var_1178]; void *
0x18048ddd9  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x18048ddde  jmp     loc_18048F374
0x18048dde3  mov     rcx, [rsp+1410h+var_13B0]
0x18048dde8  mov     rax, [rcx]
0x18048ddeb  lea     rdx, [rsi+150h]
0x18048ddf2  lea     r8, [rbp+1310h+var_1368]
0x18048ddf6  mov     rax, [rax+0C0h]
0x18048ddfd  call    cs:__guard_dispatch_icall_fptr
0x18048de03  mov     ebx, eax
0x18048de05  movsxd  rax, [rbp+1310h+var_1368]
0x18048de09  mov     [rsi+rax*2+150h], r13w
0x18048de12  test    ebx, ebx
0x18048de14  jns     short loc_18048DE43
0x18048de16  lea     rax, aHresult_0; "HRESULT"
0x18048de1d  mov     [rbp+1310h+var_1188], rax
0x18048de24  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18048de2b  mov     [rbp+1310h+var_1190], rax
0x18048de32  lea     rax, aCsoapwebservic_7; "CSoapWebService::Init() Failed to get s"...
0x18048de39  mov     ecx, 2158C19Ah
0x18048de3e  jmp     loc_18048DD72
0x18048de43  mov     rax, [rsi]
0x18048de46  mov     rcx, rsi
0x18048de49  mov     rax, [rax+50h]
0x18048de4d  call    cs:__guard_dispatch_icall_fptr
0x18048de53  mov     [rsp+1410h+channelProperties], rax
0x18048de58  lea     r8, [rsi+28h]; error
0x18048de5c  xor     edx, edx; propertyCount
0x18048de5e  xor     ecx, ecx; properties
0x18048de60  call    cs:__imp_WsCreateError
0x18048de66  mov     ebx, eax
0x18048de68  test    eax, eax
0x18048de6a  jns     short loc_18048DE99
0x18048de6c  lea     rax, aHresult_0; "HRESULT"
0x18048de73  mov     [rbp+1310h+var_1188], rax
0x18048de7a  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18048de81  mov     [rbp+1310h+var_1190], rax
0x18048de88  lea     rax, aUnableToCreate_0; "Unable to create an error for the SOAP "...
0x18048de8f  mov     ecx, 6431A0h
0x18048de94  jmp     loc_18048DD72
0x18048de99  lea     rdx, [rsi+18h]
0x18048de9d  mov     ecx, [rsi+20h]; maxSize
0x18048dea0  mov     rax, [rsi+28h]
0x18048dea4  mov     [rsp+1410h+error], rax; error
0x18048dea9  mov     [rsp+1410h+heap], rdx; heap
0x18048deae  xor     r9d, r9d; propertyCount
0x18048deb1  xor     r8d, r8d; properties
0x18048deb4  mov     edx, 200h; trimSize
0x18048deb9  call    cs:__imp_WsCreateHeap
0x18048debf  mov     ebx, eax
0x18048dec1  test    eax, eax
0x18048dec3  jns     loc_18048DFB2
0x18048dec9  lea     rax, aHresult_0; "HRESULT"
0x18048ded0  mov     [rbp+1310h+var_1188], rax
0x18048ded7  mov     dword ptr [rbp+1310h+var_1180], ebx
0x18048dedd  xorps   xmm0, xmm0
0x18048dee0  movups  [rbp+1310h+var_1178], xmm0
0x18048dee7  mov     qword ptr [rbp+1310h+var_1168], r13
0x18048deee  mov     edi, 7
0x18048def3  mov     qword ptr [rbp+1310h+var_1168+8], rdi
0x18048defa  mov     word ptr [rbp+1310h+var_1178], r13w
0x18048df02  lea     r14d, [rdi-3]
0x18048df06  mov     [rbp+1310h+var_1158], r14w
0x18048df0e  lea     rax, ??_7ClassifiedStructuredHr@Diagnostics@Mso@@6B@; const Mso::Diagnostics::ClassifiedStructuredHr::`vftable'
0x18048df15  mov     [rbp+1310h+var_1190], rax
0x18048df1c  mov     eax, [rsi+20h]
0x18048df1f  lea     rcx, ??_7LibraryType@Structured@Logging@Authentication@Mso@@6B@; const Mso::Authentication::Logging::Structured::LibraryType::`vftable'
0x18048df26  mov     qword ptr [rbp+1310h+var_1150], rcx
0x18048df2d  lea     rcx, aHeapsizeinbyte; "HeapSizeInBytes"
0x18048df34  mov     qword ptr [rbp+1310h+var_1150+8], rcx
0x18048df3b  mov     dword ptr [rbp+1310h+var_1140], eax
0x18048df41  mov     word ptr [rbp+1310h+var_1140+4], r14w
0x18048df49  movups  [rbp+1310h+var_1140+8], xmm0
0x18048df50  movdqu  [rbp+1310h+var_1130+8], xmm6
0x18048df58  mov     word ptr [rbp+1310h+var_1140+8], r13w
0x18048df60  lea     rax, aUnableToCreate_3; "Unable to create a heap for the SOAP Ca"...
0x18048df67  mov     [rsp+1410h+channelProperties], rax
0x18048df6c  lea     rax, [rbp+1310h+var_1190]
0x18048df73  mov     qword ptr [rsp+1410h+channelPropertyCount], rax
0x18048df78  lea     rax, [rbp+1310h+var_1150]
0x18048df7f  mov     [rsp+1410h+error], rax
0x18048df84  lea     rax, [rsp+1410h+channelProperties]
0x18048df89  mov     [rsp+1410h+heap], rax
0x18048df8e  mov     edx, 1B2h
0x18048df93  mov     ecx, 6431A1h
0x18048df98  lea     r8d, [rdi+5Dh]
0x18048df9c  call    ??$SendDiagnosticTrace@U?$ClassifiedStructuredObject@I@Diagnostics@Mso@@U123@@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@$$QEAU?$ClassifiedStructuredObject@I@01@4@Z; Mso::Diagnostics::SendDiagnosticTrace<Mso::Diagnostics::ClassifiedStructuredObject<uint>,Mso::Diagnostics::ClassifiedStructuredObject<uint>>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&,Mso::Diagnostics::ClassifiedStructuredObject<uint> &&)
0x18048dfa1  lea     rcx, [rbp+1310h+var_1140+8]; void *
0x18048dfa8  call    ??1?$KeyValue@$$CBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@$$CBU_msoreg@@@Collections@Mso@@QEAA@XZ; Mso::Collections::KeyValue<std::wstring const,_msoreg const>::~KeyValue<std::wstring const,_msoreg const>(void)
0x18048dfad  jmp     loc_18048DDD2
0x18048dfb2  mov     rcx, [rsp+1410h+var_13B0]
0x18048dfb7  mov     rax, [rcx]
0x18048dfba  mov     rax, [rax+98h]
0x18048dfc1  call    cs:__guard_dispatch_icall_fptr
0x18048dfc7  mov     [rbp+1310h+var_135C], eax
0x18048dfca  mov     r14d, 4
0x18048dfd0  lea     rdi, ??_7LibraryType@Structured@Logging@Authentication@Mso@@6B@; const Mso::Authentication::Logging::Structured::LibraryType::`vftable'
0x18048dfd7  cmp     [rbp+1310h+arg_20], r13b
0x18048dfde  jz      short loc_18048E016
0x18048dfe0  lea     ebx, [r14+7Ch]
0x18048dfe4  lea     rax, aCsoapwebservic_15; "CSoapWebService::Init() Setting the aut"...
0x18048dfeb  mov     [rsp+1410h+var_13B8], rax
0x18048dff0  lea     r9d, [r14-2]
0x18048dff4  lea     rax, [rsp+1410h+var_13B8]
0x18048dff9  mov     [rsp+1410h+heap], rax
0x18048dffe  mov     edx, 1B2h
0x18048e003  mov     ecx, 2158C196h
0x18048e008  lea     r8d, [r14+2Eh]
0x18048e00c  call    ??$SendDiagnosticTrace@$$V@Diagnostics@Mso@@YAXKW4Category@Logging@1@W4Severity@31@W4ValidDataCategories@01@AEBV?$StringLiteral@D@StringLiterals@1@@Z; Mso::Diagnostics::SendDiagnosticTrace<>(ulong,Mso::Logging::Category,Mso::Logging::Severity,Mso::Diagnostics::ValidDataCategories,Mso::StringLiterals::StringLiteral<char> const &)
0x18048e011  jmp     loc_18048E466
0x18048e016  cmp     [rbp+1310h+arg_28], r13b
0x18048e01d  jz      loc_18048E385
0x18048e023  lea     rax, off_180F81D90
0x18048e02a  mov     [rbp+1310h+var_10D0], rax
0x18048e031  lea     r8, [rbp+1310h+var_10B8]
0x18048e038  mov     [rbp+1310h+var_10C8], r8
0x18048e03f  mov     eax, 104Ah
0x18048e044  mov     [rbp+1310h+var_10C0], eax
0x18048e04a  xor     ecx, ecx
0x18048e04c  mov     [rbp+1310h+var_10B8], cx
0x18048e053  shr     eax, 1
0x18048e055  mov     [rbp+1310h+var_1390], eax
0x18048e058  mov     rcx, [rsp+1410h+var_13B0]
0x18048e05d  mov     rax, [rcx]
0x18048e060  mov     dword ptr [rsp+1410h+heap], r13d
0x18048e065  lea     r9, [rbp+1310h+var_1390]
0x18048e069  mov     edx, 0FFh
0x18048e06e  mov     rax, [rax+70h]
0x18048e072  call    cs:__guard_dispatch_icall_fptr
0x18048e078  mov     ebx, eax
0x18048e07a  test    eax, eax
0x18048e07c  jns     loc_18048E169
0x18048e082  lea     rax, aHresult_0; "HRESULT"
  ... truncated ...
```
