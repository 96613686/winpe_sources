# CGeneralHttpRequest::OpenGetRequest(ushort const *,ushort const *,std::basic_string_view<ushort,std::char_traits<ushort>>,int &,bool,bool)

- ea: `0x1800285b0`
- end: `0x18002894e`
- name: `?OpenGetRequest@CGeneralHttpRequest@@IEAAJPEBG0V?$basic_string_view@GU?$char_traits@G@std@@@std@@AEAH_N3@Z`
- size: `926`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, __int64, int, char, char)`
- caller_count: `2`
- callee_count: `20`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180027660`
- `0x180028480`

## callees

- `0x18000a6e0`
- `0x18000abc4`
- `0x18000b2b4`
- `0x18001206c`
- `0x18001208c`
- `0x180019764`
- `0x180023bac`
- `0x18002407c`
- `0x1800240b8`
- `0x180026ebc`
- `0x180027104`
- `0x180027170`
- `0x180027244`
- `0x180027e10`
- `0x1800285b0`
- `0x180028a48`
- `0x180028d60`
- `0x180029758`
- `0x180029cc8`
- `0x18002a488`

## import_xrefs

- `WINHTTP!WinHttpOpen` at `0x1800287e4`
- `WINHTTP!WinHttpOpen` at `0x1800287e4`
- `WINHTTP!WinHttpCrackUrl` at `0x18002878f`
- `WINHTTP!WinHttpCrackUrl` at `0x18002878f`
- `WINHTTP!WinHttpSetTimeouts` at `0x180028820`
- `WINHTTP!WinHttpSetTimeouts` at `0x180028820`
- `WINHTTP!WinHttpQueryOption` at `0x180028841`
- `WINHTTP!WinHttpQueryOption` at `0x180028841`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CGeneralHttpRequest::OpenGetRequest(
        __int64 a1,
        const WCHAR *a2,
        __int64 a3,
        __int64 a4,
        int a5,
        char a6,
        char a7)
{
  unsigned int v10; // edx
  __int64 v11; // rdi
  int v12; // eax
  int LastError; // ebx
  __int64 v14; // rdx
  unsigned __int64 v15; // rdx
  CHAR *v16; // rbx
  __int64 v17; // rdx
  const char *v18; // r9
  __int64 v19; // rdx
  HINTERNET *v20; // rbx
  HINTERNET v21; // rax
  __int64 v22; // rax
  __int64 v23; // rdx
  __int64 v24; // rcx
  unsigned int v25; // edx
  void *v26; // rcx
  bool v27; // zf
  void *v28; // rcx
  int dwFlags; // [rsp+20h] [rbp-E0h]
  char v31; // [rsp+50h] [rbp-B0h] BYREF
  int v32; // [rsp+51h] [rbp-AFh] BYREF
  void *v33; // [rsp+58h] [rbp-A8h] BYREF
  int nSendTimeout; // [rsp+60h] [rbp-A0h] BYREF
  void *v35; // [rsp+68h] [rbp-98h] BYREF
  unsigned int Buffer; // [rsp+70h] [rbp-90h] BYREF
  DWORD dwBufferLength; // [rsp+74h] [rbp-8Ch] BYREF
  __int64 v38; // [rsp+78h] [rbp-88h] BYREF
  __int64 v39; // [rsp+80h] [rbp-80h] BYREF
  _QWORD v40[3]; // [rsp+88h] [rbp-78h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+A0h] [rbp-60h] BYREF
  char v42; // [rsp+110h] [rbp+10h] BYREF
  _QWORD v43[42]; // [rsp+160h] [rbp+60h] BYREF
  char v44; // [rsp+2B0h] [rbp+1B0h]
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v39 = a3;
  wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(
    v43,
    "MitigationHttpRequestActivity");
  v43[0] = &MitigationTelemetryClass::MitigationHttpRequestActivity::`vftable';
  v44 = 0;
  MitigationTelemetryClass::MitigationHttpRequestActivity::StartActivity(
    (MitigationTelemetryClass::MitigationHttpRequestActivity *)v43,
    v10);
  LOBYTE(v32) = 1;
  v31 = a6;
  nSendTimeout = 0;
  v38 = -2147483646;
  dwFlags = 0;
  if ( (int)MitigationRegUtils::GetMitigationRegDWORD(&v38, 0, L"TestFlags", &nSendTimeout) >= 0
    && (nSendTimeout & 0x800) != 0 )
  {
    v31 = 0;
  }
  memset(v40, 0, sizeof(v40));
  v11 = -1;
  v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Initialize(v40, v39, -1);
  LastError = v12;
  if ( v12 < 0 )
  {
    v14 = 72;
LABEL_9:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\generalhttprequest.cpp",
      (const char *)(unsigned int)v12,
      0);
    goto LABEL_30;
  }
  if ( v31 )
  {
    v12 = Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Concat(
            v40,
            L"Accept-Encoding: gzip,deflate\r\n",
            31);
    LastError = v12;
    if ( v12 < 0 )
    {
      v14 = 76;
      goto LABEL_9;
    }
  }
  wil::make_unique_nothrow<unsigned short [0]>(&v33, 260);
  if ( v33 )
  {
    wil::make_unique_nothrow<unsigned short [0]>(&v35, 4096);
    v16 = (CHAR *)v35;
    if ( !v35 )
    {
      LastError = -2147024882;
      v17 = 83;
      goto LABEL_25;
    }
    memset_0(&UrlComponents, 0, sizeof(UrlComponents));
    UrlComponents.dwStructSize = 104;
    UrlComponents.lpszHostName = (LPSTR)v33;
    UrlComponents.lpszUrlPath = v16;
    UrlComponents.dwHostNameLength = 260;
    UrlComponents.dwUrlPathLength = 4096;
    do
      ++v11;
    while ( a2[v11] );
    if ( WinHttpCrackUrl(a2, v11, 0x10000000u, &UrlComponents) )
    {
      if ( a7 )
        LOBYTE(v32) = UrlComponents.nScheme == INTERNET_SCHEME_GOPHER;
      v20 = (HINTERNET *)(a1 + 48);
      v21 = WinHttpOpen(&CGeneralHttpRequest::s_UserAgentHeaderString, 4u, 0, 0, 0);
      wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
        a1 + 48,
        v21);
      if ( *(_QWORD *)(a1 + 48) )
      {
        nSendTimeout = 0;
        CGeneralHttpRequest::GetRequestTimeout((unsigned int *)&nSendTimeout);
        WinHttpSetTimeouts(*v20, 0, nSendTimeout, nSendTimeout, nSendTimeout);
        Buffer = 0;
        dwBufferLength = 4;
        WinHttpQueryOption(*v20, 5u, &Buffer, &dwBufferLength);
        v38 = -2147483646;
        MitigationRegUtils::SetMitigationRegDWORD(&v38, 1, L"CurrentTimeout", Buffer);
        v22 = lambda_d98214fa0de6a2f421d89065e4517fba_::_lambda_d98214fa0de6a2f421d89065e4517fba_(
                (unsigned int)&v42,
                a5,
                a1,
                (unsigned int)&v33,
                (__int64)&v32,
                (__int64)&v35,
                a4,
                (__int64)&v31,
                (__int64)v40,
                (__int64)&v39);
        LastError = CGeneralHttpRequest::DoRetriableOperation__lambda_d98214fa0de6a2f421d89065e4517fba___(v24, v23, v22);
        MitigationTelemetryClass::MitigationHttpRequestActivity::Stop(
          (MitigationTelemetryClass::MitigationHttpRequestActivity *)v43,
          v25);
        if ( LastError >= 0 )
          goto LABEL_26;
        v17 = 194;
LABEL_25:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v17,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\generalhttprequest.cpp",
          (const char *)(unsigned int)LastError,
          dwFlags);
LABEL_26:
        v26 = v35;
        v27 = v35 == 0;
        v35 = 0;
        if ( !v27 )
          operator delete(v26, v15);
        goto LABEL_28;
      }
      v19 = 103;
    }
    else
    {
      v19 = 94;
    }
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)v19,
                  (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\generalhttprequest.cpp",
                  v18);
    goto LABEL_26;
  }
  LastError = -2147024882;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x51,
    (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationrestclient\\generalhttprequest.cpp",
    (const char *)0x8007000ELL,
    0);
LABEL_28:
  v28 = v33;
  v27 = v33 == 0;
  v33 = 0;
  if ( !v27 )
    operator delete(v28, v15);
LABEL_30:
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(v40);
  MitigationTelemetryClass::MitigationHttpRequestActivity::~MitigationHttpRequestActivity((MitigationTelemetryClass::MitigationHttpRequestActivity *)v43);
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1800285b0  push    rbp
0x1800285b2  push    rbx
0x1800285b3  push    rsi
0x1800285b4  push    rdi
0x1800285b5  push    r12
0x1800285b7  push    r13
0x1800285b9  push    r14
0x1800285bb  push    r15
0x1800285bd  lea     rbp, [rsp-1D8h]
0x1800285c5  sub     rsp, 2D8h
0x1800285cc  mov     rax, cs:__security_cookie
0x1800285d3  xor     rax, rsp
0x1800285d6  mov     [rbp+210h+var_50], rax
0x1800285dd  mov     r15, r9
0x1800285e0  mov     rsi, rdx
0x1800285e3  mov     r14, rcx
0x1800285e6  mov     [rbp+210h+var_290], r8
0x1800285ea  mov     r12, [rbp+210h+arg_20]
0x1800285f1  lea     rdx, aMitigationhttp; "MitigationHttpRequestActivity"
0x1800285f8  lea     rcx, [rbp+210h+var_1B0]
0x1800285fc  call    ??0?$ActivityBase@VMitigationTelemetryClass@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<MitigationTelemetryClass,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180028601  lea     rax, ??_7MitigationHttpRequestActivity@MitigationTelemetryClass@@6B@; const MitigationTelemetryClass::MitigationHttpRequestActivity::`vftable'
0x180028608  mov     [rbp+210h+var_1B0], rax
0x18002860c  xor     r13d, r13d
0x18002860f  mov     [rbp+210h+var_60], r13b
0x180028616  lea     rcx, [rbp+210h+var_1B0]; this
0x18002861a  call    ?StartActivity@MitigationHttpRequestActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::MitigationHttpRequestActivity::StartActivity(ulong)
0x18002861f  nop
0x180028620  mov     byte ptr [rsp+310h+var_2BF], 1
0x180028625  mov     al, [rbp+210h+arg_28]
0x18002862b  mov     [rsp+310h+var_2C0], al
0x18002862f  mov     [rsp+310h+nSendTimeout], r13d
0x180028634  mov     [rsp+310h+var_298], 0FFFFFFFF80000002h
0x18002863d  mov     qword ptr [rsp+310h+dwFlags], r13; int
0x180028642  lea     r9, [rsp+310h+nSendTimeout]
0x180028647  lea     r8, aTestflags; "TestFlags"
0x18002864e  xor     edx, edx
0x180028650  lea     rcx, [rsp+310h+var_298]
0x180028655  call    ?GetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGPEAK2@Z; MitigationRegUtils::GetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong *,ushort const *)
0x18002865a  test    eax, eax
0x18002865c  js      short loc_18002866D
0x18002865e  test    [rsp+310h+nSendTimeout], 800h
0x180028666  jz      short loc_18002866D
0x180028668  mov     [rsp+310h+var_2C0], r13b
0x18002866d  mov     [rbp+210h+var_288], r13
0x180028671  mov     [rbp+210h+var_280], r13
0x180028675  mov     [rbp+210h+var_278], r13
0x180028679  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18002867d  mov     r8, rdi
0x180028680  mov     rdx, [rbp+210h+var_290]
0x180028684  lea     rcx, [rbp+210h+var_288]
0x180028688  call    ?_Initialize@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Initialize(ushort const *,unsigned __int64)
0x18002868d  mov     ebx, eax
0x18002868f  test    eax, eax
0x180028691  jns     short loc_180028698
0x180028693  lea     edx, [rdi+49h]
0x180028696  jmp     short loc_1800286C0
0x180028698  cmp     [rsp+310h+var_2C0], r13b
0x18002869d  jz      short loc_1800286DB
0x18002869f  mov     r8d, 1Fh
0x1800286a5  lea     rdx, aAcceptEncoding; "Accept-Encoding: gzip,deflate\r\n"
0x1800286ac  lea     rcx, [rbp+210h+var_288]
0x1800286b0  call    ?_Concat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAJPEBG_K@Z; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Concat(ushort const *,unsigned __int64)
0x1800286b5  mov     ebx, eax
0x1800286b7  test    eax, eax
0x1800286b9  jns     short loc_1800286DB
0x1800286bb  mov     edx, 4Ch ; 'L'; void *
0x1800286c0  lea     r8, aOnecoreBaseDia_9; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800286c7  mov     r9d, eax; char *
0x1800286ca  mov     rcx, [rbp+218h]; this
0x1800286d1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800286d6  jmp     loc_180028916
0x1800286db  mov     edx, 104h
0x1800286e0  lea     rcx, [rsp+310h+var_2B8]
0x1800286e5  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800286ea  nop
0x1800286eb  cmp     [rsp+310h+var_2B8], r13
0x1800286f0  jnz     short loc_180028717
0x1800286f2  mov     rcx, [rbp+218h]; this
0x1800286f9  mov     ebx, 8007000Eh
0x1800286fe  mov     r9d, ebx; char *
0x180028701  lea     r8, aOnecoreBaseDia_9; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180028708  mov     edx, 51h ; 'Q'; void *
0x18002870d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180028712  jmp     loc_180028901
0x180028717  mov     edx, 1000h
0x18002871c  lea     rcx, [rsp+310h+var_2A8]
0x180028721  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x180028726  nop
0x180028727  mov     rbx, [rsp+310h+var_2A8]
0x18002872c  test    rbx, rbx
0x18002872f  jnz     short loc_180028740
0x180028731  mov     ebx, 8007000Eh
0x180028736  mov     edx, 53h ; 'S'
0x18002873b  jmp     loc_1800288D5
0x180028740  mov     r13d, 68h ; 'h'
0x180028746  mov     r8d, r13d; Size
0x180028749  xor     edx, edx; Val
0x18002874b  lea     rcx, [rbp+210h+UrlComponents]; void *
0x18002874f  call    memset_0
0x180028754  mov     [rbp+210h+UrlComponents.dwStructSize], r13d
0x180028758  mov     rax, [rsp+310h+var_2B8]
0x18002875d  mov     [rbp+210h+UrlComponents.lpszHostName], rax
0x180028761  mov     [rbp+210h+UrlComponents.lpszUrlPath], rbx
0x180028765  mov     [rbp+210h+UrlComponents.dwHostNameLength], 104h
0x18002876c  mov     [rbp+210h+UrlComponents.dwUrlPathLength], 1000h
0x180028773  xor     r13d, r13d
0x180028776  inc     rdi
0x180028779  cmp     [rsi+rdi*2], r13w
0x18002877e  jnz     short loc_180028776
0x180028780  lea     r9, [rbp+210h+UrlComponents]; lpUrlComponents
0x180028784  mov     r8d, 10000000h; dwFlags
0x18002878a  mov     edx, edi; dwUrlLength
0x18002878c  mov     rcx, rsi; pwszUrl
0x18002878f  call    cs:__imp_WinHttpCrackUrl
0x180028795  test    eax, eax
0x180028797  jnz     short loc_1800287B6
0x180028799  lea     edx, [rax+5Eh]; void *
0x18002879c  lea     r8, aOnecoreBaseDia_9; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800287a3  mov     rcx, [rbp+218h]; this
0x1800287aa  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800287af  mov     ebx, eax
0x1800287b1  jmp     loc_1800288EC
0x1800287b6  cmp     [rbp+210h+arg_30], r13b
0x1800287bd  jz      short loc_1800287C8
0x1800287bf  cmp     [rbp+210h+UrlComponents.nScheme], 2
0x1800287c3  setz    byte ptr [rsp+310h+var_2BF]
0x1800287c8  lea     rbx, [r14+30h]
0x1800287cc  mov     [rsp+310h+dwFlags], r13d; dwFlags
0x1800287d1  xor     r9d, r9d; pszProxyBypassW
0x1800287d4  xor     r8d, r8d; pszProxyW
0x1800287d7  lea     edi, [r9+4]
0x1800287db  mov     edx, edi; dwAccessType
0x1800287dd  lea     rcx, ?s_UserAgentHeaderString@CGeneralHttpRequest@@0PAGA; pszAgentW
0x1800287e4  call    cs:__imp_WinHttpOpen
0x1800287ea  mov     rdx, rax
0x1800287ed  mov     rcx, rbx
0x1800287f0  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800287f5  cmp     [rbx], r13
0x1800287f8  jnz     short loc_1800287FF
0x1800287fa  lea     edx, [rdi+63h]
0x1800287fd  jmp     short loc_18002879C
0x1800287ff  mov     [rsp+310h+nSendTimeout], r13d
0x180028804  lea     rcx, [rsp+310h+nSendTimeout]; unsigned int *
0x180028809  call    ?GetRequestTimeout@CGeneralHttpRequest@@CAXPEAK@Z; CGeneralHttpRequest::GetRequestTimeout(ulong *)
0x18002880e  mov     r8d, [rsp+310h+nSendTimeout]; nConnectTimeout
0x180028813  mov     [rsp+310h+dwFlags], r8d; nReceiveTimeout
0x180028818  mov     r9d, r8d; nSendTimeout
0x18002881b  xor     edx, edx; nResolveTimeout
0x18002881d  mov     rcx, [rbx]; hInternet
0x180028820  call    cs:__imp_WinHttpSetTimeouts
0x180028826  mov     [rsp+310h+Buffer], r13d
0x18002882b  mov     [rsp+310h+dwBufferLength], edi
0x18002882f  lea     r9, [rsp+310h+dwBufferLength]; lpdwBufferLength
0x180028834  lea     r8, [rsp+310h+Buffer]; lpBuffer
0x180028839  mov     edx, 5; dwOption
0x18002883e  mov     rcx, [rbx]; hInternet
0x180028841  call    cs:__imp_WinHttpQueryOption
0x180028847  mov     [rsp+310h+var_298], 0FFFFFFFF80000002h
0x180028850  mov     qword ptr [rsp+310h+dwFlags], r13
0x180028855  mov     r9d, [rsp+310h+Buffer]
0x18002885a  lea     r8, aCurrenttimeout; "CurrentTimeout"
0x180028861  mov     edx, 1
0x180028866  lea     rcx, [rsp+310h+var_298]
0x18002886b  call    ?SetMitigationRegDWORD@MitigationRegUtils@@SAJAEBQEAUHKEY__@@W4MitigationRegistryKey@@PEBGK2@Z; MitigationRegUtils::SetMitigationRegDWORD(HKEY__ * const &,MitigationRegistryKey,ushort const *,ulong,ushort const *)
0x180028870  lea     rax, [rbp+210h+var_290]
0x180028874  mov     [rsp+310h+var_2C8], rax
0x180028879  lea     rax, [rbp+210h+var_288]
0x18002887d  mov     [rsp+310h+var_2D0], rax
0x180028882  lea     rax, [rsp+310h+var_2C0]
0x180028887  mov     [rsp+310h+var_2D8], rax
0x18002888c  mov     [rsp+310h+var_2E0], r15
0x180028891  lea     rax, [rsp+310h+var_2A8]
0x180028896  mov     [rsp+310h+var_2E8], rax
0x18002889b  lea     rax, [rsp+310h+var_2BF]
0x1800288a0  mov     qword ptr [rsp+310h+dwFlags], rax; int
0x1800288a5  lea     r9, [rsp+310h+var_2B8]
0x1800288aa  mov     r8, r14
0x1800288ad  mov     rdx, r12
0x1800288b0  lea     rcx, [rbp+210h+var_200]
0x1800288b4  call    _lambda_d98214fa0de6a2f421d89065e4517fba____lambda_d98214fa0de6a2f421d89065e4517fba_
0x1800288b9  mov     r8, rax
0x1800288bc  call    CGeneralHttpRequest__DoRetriableOperation__lambda_d98214fa0de6a2f421d89065e4517fba___
0x1800288c1  mov     ebx, eax
0x1800288c3  lea     rcx, [rbp+210h+var_1B0]; this
0x1800288c7  call    ?Stop@MitigationHttpRequestActivity@MitigationTelemetryClass@@QEAAXK@Z; MitigationTelemetryClass::MitigationHttpRequestActivity::Stop(ulong)
0x1800288cc  test    ebx, ebx
0x1800288ce  jns     short loc_1800288EC
0x1800288d0  mov     edx, 0C2h; void *
0x1800288d5  mov     r9d, ebx; char *
0x1800288d8  lea     r8, aOnecoreBaseDia_9; "onecore\\base\\diagnosis\\mitigation\\c"...
0x1800288df  mov     rcx, [rbp+218h]; this
0x1800288e6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800288eb  nop
0x1800288ec  mov     rcx, [rsp+310h+var_2A8]; void *
0x1800288f1  test    rcx, rcx
0x1800288f4  mov     [rsp+310h+var_2A8], r13
0x1800288f9  jz      short loc_180028901
0x1800288fb  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028900  nop
0x180028901  mov     rcx, [rsp+310h+var_2B8]; void *
0x180028906  test    rcx, rcx
0x180028909  mov     [rsp+310h+var_2B8], r13
0x18002890e  jz      short loc_180028916
0x180028910  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180028915  nop
0x180028916  lea     rcx, [rbp+210h+var_288]
0x18002891a  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18002891f  nop
0x180028920  lea     rcx, [rbp+210h+var_1B0]; this
0x180028924  call    ??1MitigationHttpRequestActivity@MitigationTelemetryClass@@QEAA@XZ; MitigationTelemetryClass::MitigationHttpRequestActivity::~MitigationHttpRequestActivity(void)
0x180028929  mov     eax, ebx
0x18002892b  mov     rcx, [rbp+210h+var_50]
0x180028932  xor     rcx, rsp; StackCookie
0x180028935  call    __security_check_cookie
0x18002893a  add     rsp, 2D8h
0x180028941  pop     r15
0x180028943  pop     r14
0x180028945  pop     r13
0x180028947  pop     r12
0x180028949  pop     rdi
0x18002894a  pop     rsi
0x18002894b  pop     rbx
0x18002894c  pop     rbp
0x18002894d  retn
```
