# CGeneralHttpRequest::OpenPostRequest(ushort const *,ushort const *,ushort const *,bool)

- ea: `0x1800aecd4`
- end: `0x1800af13b`
- name: `?OpenPostRequest@CGeneralHttpRequest@@IEAAJPEBG00_N@Z`
- size: `1127`
- prototype: `__int64 __fastcall(CGeneralHttpRequest *this, const unsigned __int16 *, const unsigned __int16 *, unsigned __int16 *, bool)`
- caller_count: `3`
- callee_count: `23`
- tags: `file_ops, registry_config, service_task, broker_com_uri`

## callers

- `0x180098278`
- `0x1800987a4`
- `0x180098dd0`

## callees

- `0x180004b80`
- `0x180005020`
- `0x180005744`
- `0x18000cc6c`
- `0x18000cc8c`
- `0x18001c6f4`
- `0x18001ec48`
- `0x1800254ac`
- `0x18002f364`
- `0x180086644`
- `0x1800880cc`
- `0x1800adcd0`
- `0x1800add10`
- `0x1800add94`
- `0x1800addc0`
- `0x1800ae094`
- `0x1800ae98c`
- `0x1800aea4c`
- `0x1800aebd8`
- `0x1800aec80`
- `0x1800aecd4`
- `0x1800af2d4`
- `0x1800af90c`

## import_xrefs

- `WINHTTP!WinHttpQueryOption` at `0x1800aefb6`
- `WINHTTP!WinHttpQueryOption` at `0x1800aefb6`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800aef97`
- `WINHTTP!WinHttpSetTimeouts` at `0x1800aef97`
- `WINHTTP!WinHttpOpen` at `0x1800aeeed`
- `WINHTTP!WinHttpOpen` at `0x1800aeeed`
- `WINHTTP!WinHttpCrackUrl` at `0x1800aee6b`
- `WINHTTP!WinHttpCrackUrl` at `0x1800aee6b`

## string_xrefs

- `0x1800aed76`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800aedd0`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800aee7c`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800aeebe`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800aef0a`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800af070`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800af09c`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`
- `0x1800af0d1`: `onecore\base\flighting\flightsettings\broker\libs\common\generalhttprequest.cpp`

## pseudocode

```c
__int64 __fastcall CGeneralHttpRequest::OpenPostRequest(
        CGeneralHttpRequest *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        unsigned __int16 *a4,
        bool a5)
{
  const unsigned __int16 *v8; // r8
  int v9; // eax
  int LastError; // ebx
  unsigned __int16 *v11; // rdi
  CGeneralHttpRequest *v12; // rcx
  int v13; // eax
  CHAR *v14; // rbx
  CGeneralHttpRequest *v15; // rcx
  const char *v16; // r9
  const struct std::nothrow_t *v17; // rdx
  int v18; // eax
  HINTERNET *v19; // rbx
  HINTERNET v20; // rax
  const char *v21; // r9
  void *v22; // rcx
  bool v23; // zf
  void *v24; // rcx
  CGeneralHttpRequest *v26; // rcx
  __int64 v27; // rsi
  unsigned int v28; // edi
  unsigned int v29; // edx
  const struct std::nothrow_t *v30; // rdx
  void *v31; // rcx
  void *v32; // rcx
  int dwFlags; // [rsp+20h] [rbp-E0h]
  int dwFlagsa; // [rsp+20h] [rbp-E0h]
  bool v35[8]; // [rsp+50h] [rbp-B0h] BYREF
  void *v36; // [rsp+58h] [rbp-A8h] BYREF
  void *v37; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int Buffer; // [rsp+68h] [rbp-98h] BYREF
  unsigned int v39; // [rsp+6Ch] [rbp-94h] BYREF
  unsigned __int8 *v40; // [rsp+70h] [rbp-90h] BYREF
  int nSendTimeout[2]; // [rsp+78h] [rbp-88h] BYREF
  unsigned __int16 *v42; // [rsp+80h] [rbp-80h] BYREF
  __int64 v43; // [rsp+88h] [rbp-78h]
  __int64 v44; // [rsp+90h] [rbp-70h]
  LPCWSTR pwszUrl; // [rsp+98h] [rbp-68h] BYREF
  DWORD dwUrlLength[2]; // [rsp+A0h] [rbp-60h]
  __int64 v47; // [rsp+A8h] [rbp-58h]
  DWORD dwBufferLength; // [rsp+B0h] [rbp-50h] BYREF
  unsigned __int16 *v49; // [rsp+B8h] [rbp-48h] BYREF
  $BC2FB811D417144E831EE3AEA4A279C8 UrlComponents; // [rsp+C0h] [rbp-40h] BYREF
  char v51; // [rsp+130h] [rbp+30h] BYREF
  _BYTE v52[352]; // [rsp+170h] [rbp+70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+318h] [rbp+218h]

  v49 = a4;
  FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::Start<unsigned long>((FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity *)v52);
  v35[0] = a5;
  if ( FSCommonUtils::IsTestFlagSet(0x800u) )
    v35[0] = 0;
  pwszUrl = 0;
  *(_QWORD *)dwUrlLength = 0;
  v47 = 0;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pwszUrl);
  *(_QWORD *)dwUrlLength = -1;
  v47 = -1;
  v9 = CGeneralHttpRequest::InitializeQuery(this, a2, v8, (unsigned __int16 **)&pwszUrl);
  LastError = v9;
  if ( v9 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x96,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
      (const char *)(unsigned int)v9,
      dwFlags);
LABEL_21:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pwszUrl);
    FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::~FlightingHttpRequestActivity((FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity *)v52);
    return (unsigned int)LastError;
  }
  v42 = 0;
  v43 = 0;
  v44 = 0;
  v11 = v49;
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
  v43 = -1;
  v44 = -1;
  v13 = CGeneralHttpRequest::InitializePostHeaders(v12, &v42, v11, v35[0]);
  LastError = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
      (const char *)(unsigned int)v13,
      dwFlags);
LABEL_20:
    Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
    goto LABEL_21;
  }
  wil::make_unique_nothrow<unsigned short [0]>(&v36, 260);
  if ( v36 )
  {
    wil::make_unique_nothrow<unsigned short [0]>(&v37, 4096);
    v14 = (CHAR *)v37;
    if ( v37 )
    {
      memset_0(&UrlComponents, 0, sizeof(UrlComponents));
      UrlComponents.dwStructSize = 104;
      UrlComponents.lpszHostName = (LPSTR)v36;
      UrlComponents.lpszUrlPath = v14;
      UrlComponents.dwHostNameLength = 260;
      UrlComponents.dwUrlPathLength = 4096;
      Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(&pwszUrl);
      if ( WinHttpCrackUrl(pwszUrl, dwUrlLength[0], 0x10000000u, &UrlComponents) )
      {
        v40 = 0;
        v39 = 0;
        v18 = CGeneralHttpRequest::ConvertPostDataToByteArray(v15, a3, &v40, &v39);
        LastError = v18;
        if ( v18 >= 0 )
        {
          v19 = (HINTERNET *)((char *)this + 40);
          v20 = WinHttpOpen(&CGeneralHttpRequest::s_UserAgentHeaderString, 4u, 0, 0, 0);
          wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&int WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(
            (char *)this + 40,
            v20);
          if ( *((_QWORD *)this + 5) )
          {
            nSendTimeout[0] = 0;
            CGeneralHttpRequest::GetRequestTimeout((unsigned int *)nSendTimeout);
            WinHttpSetTimeouts(*v19, 0, nSendTimeout[0], nSendTimeout[0], nSendTimeout[0]);
            Buffer = 0;
            dwBufferLength = 4;
            WinHttpQueryOption(*v19, 5u, &Buffer, &dwBufferLength);
            *(_QWORD *)nSendTimeout = -2147483646;
            FSRegUtils::SetFlightingRegDWORD(nSendTimeout, 1, L"CurrentTimeout", Buffer);
            v27 = lambda_27838f32262d2b016b2f4de37b361281_::_lambda_27838f32262d2b016b2f4de37b361281_(
                    (unsigned int)&v51,
                    (_DWORD)this,
                    (unsigned int)&v36,
                    (unsigned int)&v37,
                    (__int64)v35,
                    (__int64)&v42,
                    (__int64)&v49,
                    (__int64)&v40,
                    (__int64)&v39);
            v35[1] = 1;
            LastError = -2147467259;
            v28 = 0;
            do
            {
              if ( LastError >= 0 )
                break;
              if ( v28 >= 2 )
                break;
              LastError = lambda_27838f32262d2b016b2f4de37b361281_::operator()(v27, &v35[1]);
              ++v28;
            }
            while ( v35[1] );
            if ( !CGeneralHttpRequest::IsExpectedHresult(v26, LastError) && LastError < 0 )
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x21A,
                (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
                (const char *)(unsigned int)LastError,
                dwFlagsa);
            FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::Stop(
              (FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity *)v52,
              v29);
          }
          else
          {
            LastError = wil::details::in1diag3::Return_GetLastError(
                          retaddr,
                          (void *)0xB5,
                          (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
                          v21);
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xB0,
            (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
            (const char *)(unsigned int)v18,
            dwFlags);
        }
        CCoTaskMemPtr<unsigned char>::~CCoTaskMemPtr<unsigned char>(&v40);
      }
      else
      {
        LastError = wil::details::in1diag3::Return_GetLastError(
                      retaddr,
                      (void *)0xAB,
                      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
                      v16);
      }
      v22 = v37;
      v23 = v37 == 0;
      v37 = 0;
      if ( !v23 )
        operator delete(v22, v17);
      v24 = v36;
      v23 = v36 == 0;
      v36 = 0;
      if ( !v23 )
        operator delete(v24, v17);
      goto LABEL_20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA0,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
    v31 = v37;
    v37 = 0;
    if ( v31 )
      operator delete(v31, v30);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9E,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\libs\\common\\generalhttprequest.cpp",
      (const char *)0x8007000ELL,
      dwFlags);
  }
  v32 = v36;
  v23 = v36 == 0;
  v36 = 0;
  if ( !v23 )
    operator delete(v32, v30);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&v42);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(&pwszUrl);
  FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::~FlightingHttpRequestActivity((FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity *)v52);
  return 2147942414LL;
}

```

## disassembly

```asm
0x1800aecd4  push    rbp
0x1800aecd6  push    rbx
0x1800aecd7  push    rsi
0x1800aecd8  push    rdi
0x1800aecd9  push    r12
0x1800aecdb  push    r14
0x1800aecdd  push    r15
0x1800aecdf  lea     rbp, [rsp-1E0h]
0x1800aece7  sub     rsp, 2E0h
0x1800aecee  mov     rax, cs:__security_cookie
0x1800aecf5  xor     rax, rsp
0x1800aecf8  mov     [rbp+210h+var_40], rax
0x1800aecff  mov     r14, r8
0x1800aed02  mov     rbx, rdx
0x1800aed05  mov     rsi, rcx
0x1800aed08  mov     [rbp+210h+var_258], r9
0x1800aed0c  lea     rcx, [rbp+210h+var_1A0]; this
0x1800aed10  call    ??$Start@K@FlightingHttpRequestActivity@FlightSettingsAPITelemetryClass@@SA?AV01@$$QEAK@Z; FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::Start<ulong>(ulong &&)
0x1800aed15  nop
0x1800aed16  mov     al, [rbp+210h+arg_20]
0x1800aed1c  mov     [rsp+310h+var_2C0], al
0x1800aed20  mov     ecx, 800h; unsigned int
0x1800aed25  call    ?IsTestFlagSet@FSCommonUtils@@SA_NK@Z; FSCommonUtils::IsTestFlagSet(ulong)
0x1800aed2a  xor     r15d, r15d
0x1800aed2d  test    al, al
0x1800aed2f  jz      short loc_1800AED36
0x1800aed31  mov     [rsp+310h+var_2C0], r15b
0x1800aed36  mov     [rbp+210h+pwszUrl], r15
0x1800aed3a  mov     qword ptr [rbp+210h+dwUrlLength], r15
0x1800aed3e  mov     [rbp+210h+var_268], r15
0x1800aed42  lea     rcx, [rbp+210h+pwszUrl]
0x1800aed46  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800aed4b  or      r12, 0FFFFFFFFFFFFFFFFh
0x1800aed4f  mov     qword ptr [rbp+210h+dwUrlLength], r12
0x1800aed53  mov     [rbp+210h+var_268], r12
0x1800aed57  lea     r9, [rbp+210h+pwszUrl]; unsigned __int16 **
0x1800aed5b  mov     rdx, rbx; unsigned __int16 *
0x1800aed5e  mov     rcx, rsi; this
0x1800aed61  call    ?InitializeQuery@CGeneralHttpRequest@@AEAAJPEBG0PEAPEAG@Z; CGeneralHttpRequest::InitializeQuery(ushort const *,ushort const *,ushort * *)
0x1800aed66  mov     ebx, eax
0x1800aed68  test    eax, eax
0x1800aed6a  jns     short loc_1800AED8C
0x1800aed6c  mov     rcx, [rbp+218h]; this
0x1800aed73  mov     r9d, eax; char *
0x1800aed76  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800aed7d  mov     edx, 96h; void *
0x1800aed82  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aed87  jmp     loc_1800AEF5C
0x1800aed8c  mov     [rbp+210h+var_290], r15
0x1800aed90  mov     [rbp+210h+var_288], r15
0x1800aed94  mov     [rbp+210h+var_280], r15
0x1800aed98  mov     bl, [rsp+310h+var_2C0]
0x1800aed9c  mov     rdi, [rbp+210h+var_258]
0x1800aeda0  lea     rcx, [rbp+210h+var_290]
0x1800aeda4  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800aeda9  mov     [rbp+210h+var_288], r12
0x1800aedad  mov     [rbp+210h+var_280], r12
0x1800aedb1  mov     r9b, bl; bool
0x1800aedb4  mov     r8, rdi; unsigned __int16 *
0x1800aedb7  lea     rdx, [rbp+210h+var_290]; unsigned __int16 **
0x1800aedbb  call    ?InitializePostHeaders@CGeneralHttpRequest@@AEAAJPEAPEAGPEBG_N@Z; CGeneralHttpRequest::InitializePostHeaders(ushort * *,ushort const *,bool)
0x1800aedc0  mov     ebx, eax
0x1800aedc2  test    eax, eax
0x1800aedc4  jns     short loc_1800AEDE6
0x1800aedc6  mov     rcx, [rbp+218h]; this
0x1800aedcd  mov     r9d, eax; char *
0x1800aedd0  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800aedd7  mov     edx, 9Ah; void *
0x1800aeddc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aede1  jmp     loc_1800AEF52
0x1800aede6  mov     r12d, 104h
0x1800aedec  mov     edx, r12d
0x1800aedef  lea     rcx, [rsp+310h+var_2B8]
0x1800aedf4  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800aedf9  nop
0x1800aedfa  cmp     [rsp+310h+var_2B8], r15
0x1800aedff  jz      loc_1800AF0C4
0x1800aee05  mov     edx, 1000h
0x1800aee0a  lea     rcx, [rsp+310h+var_2B0]
0x1800aee0f  call    ??$make_unique_nothrow@$$BY0A@G@wil@@YA?AV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@_K@Z; wil::make_unique_nothrow<ushort [0]>(unsigned __int64)
0x1800aee14  nop
0x1800aee15  mov     rbx, [rsp+310h+var_2B0]
0x1800aee1a  test    rbx, rbx
0x1800aee1d  jz      loc_1800AF08F
0x1800aee23  mov     edi, 68h ; 'h'
0x1800aee28  mov     r8d, edi; Size
0x1800aee2b  xor     edx, edx; Val
0x1800aee2d  lea     rcx, [rbp+210h+UrlComponents]; void *
0x1800aee31  call    memset_0
0x1800aee36  mov     [rbp+210h+UrlComponents.dwStructSize], edi
0x1800aee39  mov     rax, [rsp+310h+var_2B8]
0x1800aee3e  mov     [rbp+210h+UrlComponents.lpszHostName], rax
0x1800aee42  mov     [rbp+210h+UrlComponents.lpszUrlPath], rbx
0x1800aee46  mov     [rbp+210h+UrlComponents.dwHostNameLength], r12d
0x1800aee4a  mov     [rbp+210h+UrlComponents.dwUrlPathLength], 1000h
0x1800aee51  lea     rcx, [rbp+210h+pwszUrl]
0x1800aee55  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x1800aee5a  lea     r9, [rbp+210h+UrlComponents]; lpUrlComponents
0x1800aee5e  mov     r8d, 10000000h; dwFlags
0x1800aee64  mov     edx, [rbp+210h+dwUrlLength]; dwUrlLength
0x1800aee67  mov     rcx, [rbp+210h+pwszUrl]; pwszUrl
0x1800aee6b  call    cs:__imp_WinHttpCrackUrl
0x1800aee71  test    eax, eax
0x1800aee73  jnz     short loc_1800AEE92
0x1800aee75  mov     rcx, [rbp+218h]; this
0x1800aee7c  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800aee83  lea     edx, [rdi+43h]; void *
0x1800aee86  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aee8b  mov     ebx, eax
0x1800aee8d  jmp     loc_1800AEF28
0x1800aee92  mov     [rsp+310h+var_2A0], r15
0x1800aee97  mov     [rsp+310h+var_2A4], r15d
0x1800aee9c  lea     r9, [rsp+310h+var_2A4]; unsigned int *
0x1800aeea1  lea     r8, [rsp+310h+var_2A0]; unsigned __int8 **
0x1800aeea6  mov     rdx, r14; unsigned __int16 *
0x1800aeea9  call    ?ConvertPostDataToByteArray@CGeneralHttpRequest@@IEAAJPEBGPEAPEAEPEAK@Z; CGeneralHttpRequest::ConvertPostDataToByteArray(ushort const *,uchar * *,ulong *)
0x1800aeeae  mov     ebx, eax
0x1800aeeb0  test    eax, eax
0x1800aeeb2  jns     short loc_1800AEED1
0x1800aeeb4  mov     rcx, [rbp+218h]; this
0x1800aeebb  mov     r9d, eax; char *
0x1800aeebe  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800aeec5  mov     edx, 0B0h; void *
0x1800aeeca  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800aeecf  jmp     short loc_1800AEF1D
0x1800aeed1  lea     rbx, [rsi+28h]
0x1800aeed5  mov     [rsp+310h+dwFlags], r15d; dwFlags
0x1800aeeda  xor     r9d, r9d; pszProxyBypassW
0x1800aeedd  xor     r8d, r8d; pszProxyW
0x1800aeee0  lea     edi, [r9+4]
0x1800aeee4  mov     edx, edi; dwAccessType
0x1800aeee6  lea     rcx, ?s_UserAgentHeaderString@CGeneralHttpRequest@@0PAGA; pszAgentW
0x1800aeeed  call    cs:__imp_WinHttpOpen
0x1800aeef3  mov     rdx, rax
0x1800aeef6  mov     rcx, rbx
0x1800aeef9  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AHPEAX@Z$1?WinHttpCloseHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::resource_policy<void *,int (*)(void *),&WinHttpCloseHandle(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::reset(void *)
0x1800aeefe  cmp     [rbx], r15
0x1800aef01  jnz     short loc_1800AEF76
0x1800aef03  mov     rcx, [rbp+218h]; this
0x1800aef0a  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800aef11  mov     edx, 0B5h; void *
0x1800aef16  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800aef1b  mov     ebx, eax
0x1800aef1d  lea     rcx, [rsp+310h+var_2A0]
0x1800aef22  call    ??1?$CCoTaskMemPtr@E@@QEAA@XZ; CCoTaskMemPtr<uchar>::~CCoTaskMemPtr<uchar>(void)
0x1800aef27  nop
0x1800aef28  mov     rcx, [rsp+310h+var_2B0]; void *
0x1800aef2d  test    rcx, rcx
0x1800aef30  mov     [rsp+310h+var_2B0], r15
0x1800aef35  jz      short loc_1800AEF3D
0x1800aef37  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aef3c  nop
0x1800aef3d  mov     rcx, [rsp+310h+var_2B8]; void *
0x1800aef42  test    rcx, rcx
0x1800aef45  mov     [rsp+310h+var_2B8], r15
0x1800aef4a  jz      short loc_1800AEF52
0x1800aef4c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800aef51  nop
0x1800aef52  lea     rcx, [rbp+210h+var_290]
0x1800aef56  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800aef5b  nop
0x1800aef5c  lea     rcx, [rbp+210h+pwszUrl]
0x1800aef60  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800aef65  nop
0x1800aef66  lea     rcx, [rbp+210h+var_1A0]; this
0x1800aef6a  call    ??1FlightingHttpRequestActivity@FlightSettingsAPITelemetryClass@@QEAA@XZ; FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::~FlightingHttpRequestActivity(void)
0x1800aef6f  mov     eax, ebx
0x1800aef71  jmp     loc_1800AF11A
0x1800aef76  mov     [rsp+310h+nSendTimeout], r15d
0x1800aef7b  lea     rcx, [rsp+310h+nSendTimeout]; unsigned int *
0x1800aef80  call    ?GetRequestTimeout@CGeneralHttpRequest@@CAXPEAK@Z; CGeneralHttpRequest::GetRequestTimeout(ulong *)
0x1800aef85  mov     r8d, [rsp+310h+nSendTimeout]; nConnectTimeout
0x1800aef8a  mov     [rsp+310h+dwFlags], r8d; nReceiveTimeout
0x1800aef8f  mov     r9d, r8d; nSendTimeout
0x1800aef92  xor     edx, edx; nResolveTimeout
0x1800aef94  mov     rcx, [rbx]; hInternet
0x1800aef97  call    cs:__imp_WinHttpSetTimeouts
0x1800aef9d  mov     [rsp+310h+Buffer], r15d
0x1800aefa2  mov     [rbp+210h+dwBufferLength], edi
0x1800aefa5  lea     r9, [rbp+210h+dwBufferLength]; lpdwBufferLength
0x1800aefa9  lea     r8, [rsp+310h+Buffer]; lpBuffer
0x1800aefae  mov     edx, 5; dwOption
0x1800aefb3  mov     rcx, [rbx]; hInternet
0x1800aefb6  call    cs:__imp_WinHttpQueryOption
0x1800aefbc  mov     qword ptr [rsp+310h+nSendTimeout], 0FFFFFFFF80000002h
0x1800aefc5  mov     r9d, [rsp+310h+Buffer]
0x1800aefca  lea     r8, aCurrenttimeout; "CurrentTimeout"
0x1800aefd1  mov     edx, 1
0x1800aefd6  lea     rcx, [rsp+310h+nSendTimeout]
0x1800aefdb  call    ?SetFlightingRegDWORD@FSRegUtils@@SAJAEBQEAUHKEY__@@W4FlightingRegistryKey@@PEBGK@Z; FSRegUtils::SetFlightingRegDWORD(HKEY__ * const &,FlightingRegistryKey,ushort const *,ulong)
0x1800aefe0  lea     rax, [rsp+310h+var_2A4]
0x1800aefe5  mov     [rsp+310h+var_2D0], rax
0x1800aefea  lea     rax, [rsp+310h+var_2A0]
0x1800aefef  mov     [rsp+310h+var_2D8], rax
0x1800aeff4  lea     rax, [rbp+210h+var_258]
0x1800aeff8  mov     [rsp+310h+var_2E0], rax
0x1800aeffd  lea     rax, [rbp+210h+var_290]
0x1800af001  mov     [rsp+310h+var_2E8], rax
0x1800af006  lea     rax, [rsp+310h+var_2C0]
0x1800af00b  mov     qword ptr [rsp+310h+dwFlags], rax; int
0x1800af010  lea     r9, [rsp+310h+var_2B0]
0x1800af015  lea     r8, [rsp+310h+var_2B8]
0x1800af01a  mov     rdx, rsi
0x1800af01d  lea     rcx, [rbp+210h+var_1E0]
0x1800af021  call    _lambda_27838f32262d2b016b2f4de37b361281____lambda_27838f32262d2b016b2f4de37b361281_
0x1800af026  mov     rsi, rax
0x1800af029  mov     [rsp+310h+var_2C0+1], 1
0x1800af02e  mov     ebx, 80004005h
0x1800af033  mov     edi, r15d
0x1800af036  test    ebx, ebx
0x1800af038  jns     short loc_1800AF057
0x1800af03a  cmp     edi, 2
0x1800af03d  jnb     short loc_1800AF057
0x1800af03f  lea     rdx, [rsp+310h+var_2C0+1]
0x1800af044  mov     rcx, rsi
0x1800af047  call    _lambda_27838f32262d2b016b2f4de37b361281___operator__
0x1800af04c  mov     ebx, eax
0x1800af04e  inc     edi
0x1800af050  cmp     [rsp+310h+var_2C0+1], r15b
0x1800af055  jnz     short loc_1800AF036
0x1800af057  mov     edx, ebx; int
0x1800af059  call    ?IsExpectedHresult@CGeneralHttpRequest@@AEAA_NJ@Z; CGeneralHttpRequest::IsExpectedHresult(long)
0x1800af05e  test    al, al
0x1800af060  jnz     short loc_1800AF081
0x1800af062  test    ebx, ebx
0x1800af064  jns     short loc_1800AF081
0x1800af066  mov     rcx, [rbp+218h]; this
0x1800af06d  mov     r9d, ebx; char *
0x1800af070  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800af077  mov     edx, 21Ah; void *
0x1800af07c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af081  lea     rcx, [rbp+210h+var_1A0]; this
0x1800af085  call    ?Stop@FlightingHttpRequestActivity@FlightSettingsAPITelemetryClass@@QEAAXK@Z; FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::Stop(ulong)
0x1800af08a  jmp     loc_1800AEF1D
0x1800af08f  mov     rcx, [rbp+218h]; this
0x1800af096  mov     r9d, 8007000Eh; char *
0x1800af09c  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800af0a3  mov     edx, 0A0h; void *
0x1800af0a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af0ad  nop
0x1800af0ae  mov     rcx, [rsp+310h+var_2B0]; void *
0x1800af0b3  mov     [rsp+310h+var_2B0], r15
0x1800af0b8  test    rcx, rcx
0x1800af0bb  jz      short loc_1800AF0E3
0x1800af0bd  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800af0c2  jmp     short loc_1800AF0E3
0x1800af0c4  mov     rcx, [rbp+218h]; this
0x1800af0cb  mov     r9d, 8007000Eh; char *
0x1800af0d1  lea     r8, aOnecoreBaseFli_56; "onecore\\base\\flighting\\flightsetting"...
0x1800af0d8  mov     edx, 9Eh; void *
0x1800af0dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800af0e2  nop
0x1800af0e3  mov     rcx, [rsp+310h+var_2B8]; void *
0x1800af0e8  test    rcx, rcx
0x1800af0eb  mov     [rsp+310h+var_2B8], r15
0x1800af0f0  jz      short loc_1800AF0F8
0x1800af0f2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800af0f7  nop
0x1800af0f8  lea     rcx, [rbp+210h+var_290]
0x1800af0fc  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800af101  nop
0x1800af102  lea     rcx, [rbp+210h+pwszUrl]
0x1800af106  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x1800af10b  nop
0x1800af10c  lea     rcx, [rbp+210h+var_1A0]; this
0x1800af110  call    ??1FlightingHttpRequestActivity@FlightSettingsAPITelemetryClass@@QEAA@XZ; FlightSettingsAPITelemetryClass::FlightingHttpRequestActivity::~FlightingHttpRequestActivity(void)
0x1800af115  mov     eax, 8007000Eh
0x1800af11a  mov     rcx, [rbp+210h+var_40]
0x1800af121  xor     rcx, rsp; StackCookie
0x1800af124  call    __security_check_cookie
0x1800af129  add     rsp, 2E0h
0x1800af130  pop     r15
0x1800af132  pop     r14
0x1800af134  pop     r12
0x1800af136  pop     rdi
0x1800af137  pop     rsi
0x1800af138  pop     rbx
0x1800af139  pop     rbp
0x1800af13a  retn
```
