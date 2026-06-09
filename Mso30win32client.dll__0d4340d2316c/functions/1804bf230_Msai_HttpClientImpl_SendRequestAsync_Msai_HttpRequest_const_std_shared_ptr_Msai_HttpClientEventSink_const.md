# Msai::HttpClientImpl::SendRequestAsync(Msai::HttpRequest const &,std::shared_ptr<Msai::HttpClientEventSink> const &)

- ea: `0x1804bf230`
- end: `0x1804bf9f6`
- name: `?SendRequestAsync@HttpClientImpl@Msai@@UEAAXAEBUHttpRequest@2@AEBV?$shared_ptr@VHttpClientEventSink@Msai@@@std@@@Z`
- size: `1990`
- prototype: `__int64 __fastcall(Msai::HttpClientImpl *this)`
- caller_count: `0`
- callee_count: `19`
- tags: `broker_com_uri`

## callees

- `0x180015e3c`
- `0x18001bb20`
- `0x180029e40`
- `0x180036cd0`
- `0x180060614`
- `0x1800615e0`
- `0x1801924d8`
- `0x180192520`
- `0x1801a4dec`
- `0x1801be448`
- `0x1801c48cc`
- `0x180345cec`
- `0x1804bf230`
- `0x1804bf9f8`
- `0x1804bfbb0`
- `0x1804c06c0`
- `0x1804e312c`
- `0x180592df0`
- `0x1805caab0`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1804bf556`
- `KERNEL32!GetLastError` at `0x1804bf5d7`
- `KERNEL32!GetLastError` at `0x1804bf692`
- `KERNEL32!GetLastError` at `0x1804bf748`
- `KERNEL32!GetLastError` at `0x1804bf7a8`
- `KERNEL32!GetLastError` at `0x1804bf868`
- `KERNEL32!GetLastError` at `0x1804bf915`
- `KERNEL32!GetLastError` at `0x1804bf556`
- `KERNEL32!GetLastError` at `0x1804bf5d7`
- `KERNEL32!GetLastError` at `0x1804bf692`
- `KERNEL32!GetLastError` at `0x1804bf748`
- `KERNEL32!GetLastError` at `0x1804bf7a8`
- `KERNEL32!GetLastError` at `0x1804bf868`
- `KERNEL32!GetLastError` at `0x1804bf915`
- `MSVCP140!_Mtx_unlock` at `0x1804bf9c9`
- `MSVCP140!_Mtx_unlock` at `0x1804bf9c9`
- `WININET!HttpSendRequestA` at `0x1804bf8e7`
- `WININET!HttpSendRequestA` at `0x1804bf8e7`
- `WININET!InternetConnectA` at `0x1804bf670`
- `WININET!InternetConnectA` at `0x1804bf670`
- `WININET!InternetOpenA` at `0x1804bf547`
- `WININET!InternetOpenA` at `0x1804bf547`
- `WININET!InternetSetStatusCallbackW` at `0x1804bf5cb`
- `WININET!InternetSetStatusCallbackW` at `0x1804bf5cb`
- `WININET!InternetSetOptionW` at `0x1804bf73e`
- `WININET!InternetSetOptionW` at `0x1804bf79e`
- `WININET!InternetSetOptionW` at `0x1804bf73e`
- `WININET!InternetSetOptionW` at `0x1804bf79e`
- `WININET!HttpOpenRequestA` at `0x1804bf849`
- `WININET!HttpOpenRequestA` at `0x1804bf849`

## string_xrefs

- `0x1804bf978`: `Invalid request URI`
- `0x1804bf6d9`: `Setting read timeout to %lu seconds`
- `0x1804bf69a`: `Unable to open a connection handle via InternetConnect`
- `0x1804bf617`: `Opening connection handle`
- `0x1804bf870`: `Unable to open a request handle via HttpOpenRequest`
- `0x1804bf7e8`: `Opening request handle`
- `0x1804bf750`: `Unable to set internet read timeout via InternetSetOption`
- `0x1804bf55e`: `Couldn't open a session handle via InternetOpen`
- `0x1804bf519`: `Opening session handle`
- `0x1804bf540`: `Mozilla/5.0 (compatible; MSAL 1.0)`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
int __fastcall Msai::HttpClientImpl::SendRequestAsync(Msai::HttpClientImpl *this, _QWORD *a2, _QWORD *a3)
{
  struct _Mtx_internal_imp_t *v6; // rbx
  __int64 v7; // rax
  __int64 v8; // rdx
  std::_Ref_count_base *v9; // rcx
  unsigned __int16 **v10; // rsi
  __int64 v11; // r12
  unsigned __int16 **v12; // rdx
  unsigned __int64 v13; // r15
  int v14; // ecx
  _QWORD *v15; // rcx
  const char *v16; // rax
  const struct Msai::TempError *v17; // rax
  const char *v18; // rax
  DWORD v19; // r12d
  __int64 v20; // rax
  DWORD v21; // r13d
  __int64 v22; // rax
  __int64 v23; // r15
  std::_Ref_count_base *v24; // r14
  _QWORD *Scheme; // rax
  __int64 v26; // rdx
  INTERNET_PORT v27; // r14
  _QWORD *v28; // rax
  __int64 v29; // rdx
  HINTERNET v30; // rax
  DWORD v31; // eax
  const struct Msai::TempError *v32; // rax
  DWORD LastError; // eax
  const struct Msai::TempError *v34; // rax
  __int64 Environment; // rax
  DWORD v36; // eax
  const struct Msai::TempError *v37; // rax
  DWORD v38; // eax
  const struct Msai::TempError *v39; // rax
  DWORD v40; // eax
  const struct Msai::TempError *v41; // rax
  __int64 AbsolutePathReference; // rax
  const CHAR *v43; // rdx
  DWORD v44; // eax
  const struct Msai::TempError *v45; // rax
  const CHAR *v46; // rdx
  DWORD v47; // eax
  const struct Msai::TempError *v48; // rax
  const struct Msai::TempError *v49; // rax
  int Buffer; // [rsp+40h] [rbp-99h] BYREF
  int v52; // [rsp+44h] [rbp-95h] BYREF
  DWORD v53; // [rsp+48h] [rbp-91h]
  LPVOID lpOptional; // [rsp+50h] [rbp-89h]
  _BYTE v55[8]; // [rsp+58h] [rbp-81h] BYREF
  _BYTE v56[72]; // [rsp+60h] [rbp-79h] BYREF
  char *v57; // [rsp+A8h] [rbp-31h]
  _QWORD Src[4]; // [rsp+B0h] [rbp-29h] BYREF
  _BYTE v59[32]; // [rsp+D0h] [rbp-9h] BYREF

  v6 = (Msai::HttpClientImpl *)((char *)this + 144);
  v57 = (char *)this + 144;
  std::_Mutex_base::lock((Msai::HttpClientImpl *)((char *)this + 144));
  if ( !*a3 )
  {
    Msai::LoggingImpl::LogWithFormat(
      4,
      55,
      "SendRequestAsync",
      "SendRequestAsync failed: 'eventSink' cannot be nullptr");
    return _Mtx_unlock(v6);
  }
  v7 = a3[1];
  if ( v7 )
    _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
  v8 = a3[1];
  *((_QWORD *)this + 13) = *a3;
  v9 = (std::_Ref_count_base *)*((_QWORD *)this + 14);
  *((_QWORD *)this + 14) = v8;
  if ( v9 )
    std::_Ref_count_base::_Decref(v9);
  v10 = (unsigned __int16 **)((char *)this + 16);
  std::string::operator=((char *)this + 16);
  v11 = *((_QWORD *)this + 4);
  v12 = (unsigned __int16 **)((char *)this + 16);
  v13 = *((_QWORD *)this + 5);
  if ( v13 > 0xF )
    v12 = (unsigned __int16 **)*v10;
  if ( v11 != 3 )
    goto LABEL_67;
  v14 = *(unsigned __int16 *)v12 - 17735;
  if ( *(_WORD *)v12 == 17735 )
    v14 = *((unsigned __int8 *)v12 + 2) - 84;
  if ( v14 )
  {
LABEL_67:
    if ( v13 > 0xF )
      v10 = (unsigned __int16 **)*v10;
    if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v10, v11, "POST", 4) )
    {
      v15 = (_QWORD *)((char *)this + 16);
      if ( v13 > 0xF )
        v15 = (_QWORD *)*v15;
      if ( !(unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v15, v11, "PUT", 3) )
      {
        v16 = (char *)this + 16;
        if ( v13 > 0xF )
          v16 = *(const char **)v16;
        v17 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                                v55,
                                                593794771,
                                                0,
                                                0,
                                                0,
                                                "Not implemented Http Method '%s'",
                                                v16);
        Msai::HttpClientImpl::FireOnFailed(this, v17);
        std::_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>(v56);
        return _Mtx_unlock(v6);
      }
    }
  }
  v18 = (char *)this + 16;
  if ( *((_QWORD *)this + 5) > 0xFu )
    v18 = *(const char **)v18;
  Msai::LoggingImpl::LogWithFormat(1, 67, "SendRequestAsync", "Http Method '%s'", v18);
  std::vector<unsigned char>::operator=((char *)this + 48, a2 + 15);
  v19 = *((_DWORD *)this + 14) - *((_DWORD *)this + 12);
  lpOptional = 0;
  Msai::LoggingImpl::LogWithFormat(1, 72, "SendRequestAsync", "HTTP request called with %lu bytes of postdata", v19);
  if ( v19 )
    lpOptional = (LPVOID)*((_QWORD *)this + 6);
  if ( a2[9] )
  {
    v20 = Msai::StringUtils::ConvertHeadersToString(Src);
    std::string::operator=((char *)this + 72, v20);
    Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult((Microsoft::Authentication::BrowserNativeResult *)Src);
  }
  v21 = *((_DWORD *)this + 22);
  Msai::LoggingImpl::LogWithFormat(1, 83, "SendRequestAsync", "HTTP request called with %lu bytes of headers", v21);
  v22 = a2[5];
  if ( v22 )
    _InterlockedIncrement((volatile signed __int32 *)(v22 + 8));
  v23 = a2[4];
  Src[0] = v23;
  v24 = (std::_Ref_count_base *)a2[5];
  Src[1] = v24;
  if ( v23 )
  {
    Scheme = (_QWORD *)Msai::Uri::GetScheme(v23, v59);
    v26 = Scheme[2];
    if ( Scheme[3] > 0xFu )
      Scheme = (_QWORD *)*Scheme;
    v27 = (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(Scheme, v26, "https", 5) != 0 ? 443 : 80;
    Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult((Microsoft::Authentication::BrowserNativeResult *)v59);
    v28 = (_QWORD *)Msai::Uri::GetScheme(v23, v59);
    v29 = v28[2];
    if ( v28[3] > 0xFu )
      v28 = (_QWORD *)*v28;
    v53 = (unsigned __int8)std::_Traits_equal<std::char_traits<char>>(v28, v29, "https", 5) << 23;
    Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult((Microsoft::Authentication::BrowserNativeResult *)v59);
    Msai::LoggingImpl::LogWithFormat(1, 94, "SendRequestAsync", "Opening session handle");
    v30 = InternetOpenA("Mozilla/5.0 (compatible; MSAL 1.0)", 0, 0, 0, 0x10000000u);
    *((_QWORD *)this + 15) = v30;
    if ( v30 )
    {
      Msai::LoggingImpl::LogWithFormat(1, 109, "SendRequestAsync", "Registering callback");
      if ( InternetSetStatusCallbackW(*((HINTERNET *)this + 15), Msai::HttpClientImpl::StaticCallback) == (INTERNET_STATUS_CALLBACK)-1LL )
      {
        LastError = GetLastError();
        v34 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                                v55,
                                                593794774,
                                                0,
                                                0,
                                                LastError,
                                                "InternetSetStatusCallback failed with INTERNET_INVALID_STATUS_CALLBACK");
        Msai::HttpClientImpl::FireOnFailed(this, v34);
      }
      else
      {
        Msai::LoggingImpl::LogWithFormat(1, 120, "SendRequestAsync", "Opening connection handle");
        Environment = Msai::Uri::GetEnvironment(v23, v59);
        if ( *(_QWORD *)(Environment + 24) > 0xFu )
          Environment = *(_QWORD *)Environment;
        *((_QWORD *)this + 16) = InternetConnectA(
                                   *((HINTERNET *)this + 15),
                                   (LPCSTR)Environment,
                                   v27,
                                   0,
                                   0,
                                   3u,
                                   0,
                                   (DWORD_PTR)this);
        Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult((Microsoft::Authentication::BrowserNativeResult *)v59);
        if ( *((_QWORD *)this + 16) )
        {
          Msai::LoggingImpl::LogWithFormat(
            1,
            138,
            "SendRequestAsync",
            "Setting read timeout to %lu seconds",
            *((_DWORD *)this + 2));
          Msai::LoggingImpl::LogWithFormat(
            1,
            139,
            "SendRequestAsync",
            "Setting connect timeout to %lu seconds",
            *((_DWORD *)this + 3));
          Buffer = 1000 * *((_DWORD *)this + 2);
          v52 = 1000 * *((_DWORD *)this + 3);
          if ( InternetSetOptionW(*((HINTERNET *)this + 16), 6u, &Buffer, 4u) )
          {
            if ( InternetSetOptionW(*((HINTERNET *)this + 16), 2u, &v52, 4u) )
            {
              Msai::LoggingImpl::LogWithFormat(1, 164, "SendRequestAsync", "Opening request handle");
              AbsolutePathReference = Msai::Uri::GetAbsolutePathReference(v23, v59);
              if ( *(_QWORD *)(AbsolutePathReference + 24) > 0xFu )
                AbsolutePathReference = *(_QWORD *)AbsolutePathReference;
              v43 = (char *)this + 16;
              if ( *((_QWORD *)this + 5) > 0xFu )
                v43 = *(const CHAR **)v43;
              *((_QWORD *)this + 17) = HttpOpenRequestA(
                                         *((HINTERNET *)this + 16),
                                         v43,
                                         (LPCSTR)AbsolutePathReference,
                                         0,
                                         0,
                                         0,
                                         v53,
                                         (DWORD_PTR)this);
              Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult((Microsoft::Authentication::BrowserNativeResult *)v59);
              if ( *((_QWORD *)this + 17) )
              {
                Msai::LoggingImpl::LogWithFormat(1, 183, "SendRequestAsync", "Sending request");
                v46 = (char *)this + 72;
                if ( *((_QWORD *)this + 12) > 0xFu )
                  v46 = *(const CHAR **)v46;
                if ( HttpSendRequestA(*((HINTERNET *)this + 17), v46, v21, lpOptional, v19) )
                {
                  Msai::LoggingImpl::LogWithFormat(
                    1,
                    189,
                    "SendRequestAsync",
                    "HttpSendRequest executed synchronously, manually firing the callback");
                  Msai::HttpClientImpl::Callback(this);
                  goto LABEL_38;
                }
                v47 = GetLastError();
                if ( v47 == 997 )
                {
                  Msai::LoggingImpl::LogWithFormat(
                    1,
                    201,
                    "SendRequestAsync",
                    "HttpSendRequest executed asynchronously");
                  goto LABEL_38;
                }
                v48 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                                        v55,
                                                        593794778,
                                                        0,
                                                        0,
                                                        v47,
                                                        "Unexpected error in HttpSendRequest");
                Msai::HttpClientImpl::FireOnFailed(this, v48);
              }
              else
              {
                v44 = GetLastError();
                v45 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                                        v55,
                                                        593794777,
                                                        0,
                                                        0,
                                                        v44,
                                                        "Unable to open a request handle via HttpOpenRequest");
                Msai::HttpClientImpl::FireOnFailed(this, v45);
              }
            }
            else
            {
              v40 = GetLastError();
              v41 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                                      v55,
                                                      593794776,
                                                      0,
                                                      0,
                                                      v40,
                                                      "Unable to set internet connection timeout via InternetSetOption");
              Msai::HttpClientImpl::FireOnFailed(this, v41);
            }
          }
          else
          {
            v38 = GetLastError();
            v39 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                                    v55,
                                                    591995267,
                                                    0,
                                                    0,
                                                    v38,
                                                    "Unable to set internet read timeout via InternetSetOption");
            Msai::HttpClientImpl::FireOnFailed(this, v39);
          }
        }
        else
        {
          v36 = GetLastError();
          v37 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                                  v55,
                                                  595690117,
                                                  0,
                                                  0,
                                                  v36,
                                                  "Unable to open a connection handle via InternetConnect");
          Msai::HttpClientImpl::FireOnFailed(this, v37);
        }
      }
    }
    else
    {
      v31 = GetLastError();
      v32 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                              v55,
                                              593794773,
                                              0,
                                              0,
                                              v31,
                                              "Couldn't open a session handle via InternetOpen");
      Msai::HttpClientImpl::FireOnFailed(this, v32);
    }
    std::_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>(v56);
LABEL_38:
    std::shared_ptr<Msai::BrowserNativeResultInternal>::~shared_ptr<Msai::BrowserNativeResultInternal>(Src);
    return _Mtx_unlock(v6);
  }
  v49 = (const struct Msai::TempError *)Msai::TempErrorFactoryImpl::Create(
                                          v55,
                                          593794772,
                                          0,
                                          0,
                                          0,
                                          "Invalid request URI");
  Msai::HttpClientImpl::FireOnFailed(this, v49);
  std::_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>(v56);
  if ( v24 )
    std::_Ref_count_base::_Decref(v24);
  return _Mtx_unlock(v6);
}

```

## disassembly

```asm
0x1804bf230  mov     [rsp-8+arg_18], rbx
0x1804bf235  push    rbp
0x1804bf236  push    rsi
0x1804bf237  push    rdi
0x1804bf238  push    r12
0x1804bf23a  push    r13
0x1804bf23c  push    r14
0x1804bf23e  push    r15
0x1804bf240  lea     rbp, [rsp-27h]
0x1804bf245  sub     rsp, 100h
0x1804bf24c  mov     rax, cs:__security_cookie
0x1804bf253  xor     rax, rsp
0x1804bf256  mov     [rbp+57h+var_40], rax
0x1804bf25a  mov     rsi, r8
0x1804bf25d  mov     r14, rdx
0x1804bf260  mov     rdi, rcx
0x1804bf263  lea     rbx, [rcx+90h]
0x1804bf26a  mov     [rbp+57h+var_88], rbx
0x1804bf26e  mov     rcx, rbx; this
0x1804bf271  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1804bf276  xor     r13d, r13d
0x1804bf279  cmp     [rsi], r13
0x1804bf27c  jnz     short loc_1804BF29D
0x1804bf27e  lea     r9, aSendrequestasy; "SendRequestAsync failed: 'eventSink' ca"...
0x1804bf285  lea     r8, aSendrequestasy_0; "SendRequestAsync"
0x1804bf28c  lea     edx, [r13+37h]
0x1804bf290  lea     ecx, [rdx-33h]
0x1804bf293  call    ?LogWithFormat@LoggingImpl@Msai@@SAXW4LogLevelInternal@2@HPEBD1ZZ; Msai::LoggingImpl::LogWithFormat(Msai::LogLevelInternal,int,char const *,char const *,...)
0x1804bf298  jmp     loc_1804BF9C6
0x1804bf29d  mov     rax, [rsi+8]
0x1804bf2a1  test    rax, rax
0x1804bf2a4  jz      short loc_1804BF2AA
0x1804bf2a6  lock inc dword ptr [rax+8]
0x1804bf2aa  mov     rdx, [rsi+8]
0x1804bf2ae  mov     rax, [rsi]
0x1804bf2b1  mov     [rdi+68h], rax
0x1804bf2b5  mov     rcx, [rdi+70h]; this
0x1804bf2b9  mov     [rdi+70h], rdx
0x1804bf2bd  test    rcx, rcx
0x1804bf2c0  jz      short loc_1804BF2C7
0x1804bf2c2  call    ?_Decref@_Ref_count_base@std@@QEAAXXZ; std::_Ref_count_base::_Decref(void)
0x1804bf2c7  lea     rsi, [rdi+10h]
0x1804bf2cb  mov     rdx, r14
0x1804bf2ce  mov     rcx, rsi
0x1804bf2d1  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@AEBV01@@Z; std::string::operator=(std::string const &)
0x1804bf2d6  mov     r12, [rsi+10h]
0x1804bf2da  mov     rdx, rsi
0x1804bf2dd  mov     r15, [rsi+18h]
0x1804bf2e1  cmp     r15, 0Fh
0x1804bf2e5  jbe     short loc_1804BF2EA
0x1804bf2e7  mov     rdx, [rsi]
0x1804bf2ea  cmp     r12, 3
0x1804bf2ee  jnz     short loc_1804BF30B
0x1804bf2f0  movzx   ecx, word ptr [rdx]
0x1804bf2f3  mov     eax, 4547h
0x1804bf2f8  sub     ecx, eax
0x1804bf2fa  jnz     short loc_1804BF303
0x1804bf2fc  movzx   ecx, byte ptr [rdx+2]
0x1804bf300  sub     ecx, 54h ; 'T'
0x1804bf303  test    ecx, ecx
0x1804bf305  jz      loc_1804BF3AA
0x1804bf30b  cmp     r15, 0Fh
0x1804bf30f  jbe     short loc_1804BF314
0x1804bf311  mov     rsi, [rsi]
0x1804bf314  mov     r9d, 4
0x1804bf31a  lea     r8, aPost_0; "POST"
0x1804bf321  mov     rdx, r12
0x1804bf324  mov     rcx, rsi
0x1804bf327  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1804bf32c  test    al, al
0x1804bf32e  jnz     short loc_1804BF3AA
0x1804bf330  lea     rcx, [rdi+10h]
0x1804bf334  cmp     r15, 0Fh
0x1804bf338  jbe     short loc_1804BF33D
0x1804bf33a  mov     rcx, [rcx]
0x1804bf33d  mov     r9d, 3
0x1804bf343  lea     r8, aPut; "PUT"
0x1804bf34a  mov     rdx, r12
0x1804bf34d  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1804bf352  test    al, al
0x1804bf354  jnz     short loc_1804BF3AA
0x1804bf356  lea     rax, [rdi+10h]
0x1804bf35a  cmp     r15, 0Fh
0x1804bf35e  jbe     short loc_1804BF363
0x1804bf360  mov     rax, [rax]
0x1804bf363  mov     qword ptr [rsp+130h+var_100], rax
0x1804bf368  lea     rax, aNotImplemented; "Not implemented Http Method '%s'"
0x1804bf36f  mov     qword ptr [rsp+130h+dwService], rax
0x1804bf374  mov     qword ptr [rsp+130h+dwFlags], r13
0x1804bf379  xor     r9d, r9d
0x1804bf37c  xor     r8d, r8d
0x1804bf37f  mov     edx, 236496D3h
0x1804bf384  lea     rcx, [rsp+130h+var_D8]
0x1804bf389  call    ?Create@TempErrorFactoryImpl@Msai@@SA?AUTempError@2@HW4StatusInternal@2@W4SubStatusInternal@2@_JPEBDZZ; Msai::TempErrorFactoryImpl::Create(int,Msai::StatusInternal,Msai::SubStatusInternal,__int64,char const *,...)
0x1804bf38e  nop
0x1804bf38f  nop
0x1804bf390  mov     rdx, rax; struct Msai::TempError *
0x1804bf393  mov     rcx, rdi; this
0x1804bf396  call    ?FireOnFailed@HttpClientImpl@Msai@@AEAAXAEBUTempError@2@@Z; Msai::HttpClientImpl::FireOnFailed(Msai::TempError const &)
0x1804bf39b  nop
0x1804bf39c  lea     rcx, [rbp+57h+var_D0]
0x1804bf3a0  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x1804bf3a5  jmp     loc_1804BF9C6
0x1804bf3aa  lea     rax, [rdi+10h]
0x1804bf3ae  cmp     qword ptr [rax+18h], 0Fh
0x1804bf3b3  jbe     short loc_1804BF3B8
0x1804bf3b5  mov     rax, [rax]
0x1804bf3b8  mov     qword ptr [rsp+130h+dwFlags], rax
0x1804bf3bd  lea     r9, aHttpMethodS; "Http Method '%s'"
0x1804bf3c4  lea     rsi, aSendrequestasy_0; "SendRequestAsync"
0x1804bf3cb  mov     r8, rsi
0x1804bf3ce  mov     edx, 43h ; 'C'
0x1804bf3d3  lea     ecx, [rdx-42h]
0x1804bf3d6  call    ?LogWithFormat@LoggingImpl@Msai@@SAXW4LogLevelInternal@2@HPEBD1ZZ; Msai::LoggingImpl::LogWithFormat(Msai::LogLevelInternal,int,char const *,char const *,...)
0x1804bf3db  lea     r15, [rdi+30h]
0x1804bf3df  lea     rdx, [r14+78h]
0x1804bf3e3  mov     rcx, r15
0x1804bf3e6  call    ??4?$vector@EV?$allocator@E@std@@@std@@QEAAAEAV01@AEBV01@@Z; std::vector<uchar>::operator=(std::vector<uchar> const &)
0x1804bf3eb  mov     r12d, [r15+8]
0x1804bf3ef  sub     r12d, [r15]
0x1804bf3f2  mov     [rsp+130h+lpOptional], r13
0x1804bf3f7  mov     [rsp+130h+dwFlags], r12d
0x1804bf3fc  lea     r9, aHttpRequestCal; "HTTP request called with %lu bytes of p"...
0x1804bf403  mov     r8, rsi
0x1804bf406  mov     edx, 48h ; 'H'
0x1804bf40b  lea     ecx, [rdx-47h]
0x1804bf40e  call    ?LogWithFormat@LoggingImpl@Msai@@SAXW4LogLevelInternal@2@HPEBD1ZZ; Msai::LoggingImpl::LogWithFormat(Msai::LogLevelInternal,int,char const *,char const *,...)
0x1804bf413  test    r12d, r12d
0x1804bf416  jz      short loc_1804BF420
0x1804bf418  mov     rax, [r15]
0x1804bf41b  mov     [rsp+130h+lpOptional], rax
0x1804bf420  lea     rdx, [r14+30h]
0x1804bf424  cmp     [rdx+18h], r13
0x1804bf428  jz      short loc_1804BF448
0x1804bf42a  lea     rcx, [rbp+57h+Src]; Src
0x1804bf42e  call    ?ConvertHeadersToString@StringUtils@Msai@@SA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@AEBV?$unordered_map@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@UCaseInsensitiveStringHashAscii@Detail@Msai@@UCaseInsensitiveStringEqualToAscii@45@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@@4@@Z; Msai::StringUtils::ConvertHeadersToString(std::unordered_map<std::string,std::string,Msai::Detail::CaseInsensitiveStringHashAscii,Msai::Detail::CaseInsensitiveStringEqualToAscii,std::allocator<std::pair<std::string const,std::string>>> const &)
0x1804bf433  lea     rcx, [rdi+48h]
0x1804bf437  mov     rdx, rax
0x1804bf43a  call    ??4?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::string::operator=(std::string &&)
0x1804bf43f  lea     rcx, [rbp+57h+Src]; this
0x1804bf443  call    ??1BrowserNativeResult@Authentication@Microsoft@@QEAA@XZ; Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult(void)
0x1804bf448  mov     r13d, [rdi+58h]
0x1804bf44c  mov     [rsp+130h+dwFlags], r13d
0x1804bf451  lea     r9, aHttpRequestCal_0; "HTTP request called with %lu bytes of h"...
0x1804bf458  mov     r8, rsi
0x1804bf45b  mov     edx, 53h ; 'S'
0x1804bf460  lea     ecx, [rdx-52h]
0x1804bf463  call    ?LogWithFormat@LoggingImpl@Msai@@SAXW4LogLevelInternal@2@HPEBD1ZZ; Msai::LoggingImpl::LogWithFormat(Msai::LogLevelInternal,int,char const *,char const *,...)
0x1804bf468  mov     rax, [r14+28h]
0x1804bf46c  test    rax, rax
0x1804bf46f  jz      short loc_1804BF475
0x1804bf471  lock inc dword ptr [rax+8]
0x1804bf475  mov     r15, [r14+20h]
0x1804bf479  mov     [rbp+57h+Src], r15
0x1804bf47d  mov     r14, [r14+28h]
0x1804bf481  mov     [rbp+57h+var_78], r14
0x1804bf485  test    r15, r15
0x1804bf488  jz      loc_1804BF978
0x1804bf48e  lea     rdx, [rbp+57h+var_60]
0x1804bf492  mov     rcx, r15
0x1804bf495  call    ?GetScheme@Uri@Msai@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Msai::Uri::GetScheme(void)
0x1804bf49a  mov     rdx, [rax+10h]
0x1804bf49e  cmp     qword ptr [rax+18h], 0Fh
0x1804bf4a3  jbe     short loc_1804BF4A8
0x1804bf4a5  mov     rax, [rax]
0x1804bf4a8  mov     r9d, 5
0x1804bf4ae  lea     r8, aHttps_0; "https"
0x1804bf4b5  mov     rcx, rax
0x1804bf4b8  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1804bf4bd  neg     al
0x1804bf4bf  sbb     r14w, r14w
0x1804bf4c3  and     r14w, 16Bh
0x1804bf4c9  add     r14w, 50h ; 'P'
0x1804bf4ce  lea     rcx, [rbp+57h+var_60]; this
0x1804bf4d2  call    ??1BrowserNativeResult@Authentication@Microsoft@@QEAA@XZ; Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult(void)
0x1804bf4d7  lea     rdx, [rbp+57h+var_60]
0x1804bf4db  mov     rcx, r15
0x1804bf4de  call    ?GetScheme@Uri@Msai@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Msai::Uri::GetScheme(void)
0x1804bf4e3  mov     rdx, [rax+10h]
0x1804bf4e7  cmp     qword ptr [rax+18h], 0Fh
0x1804bf4ec  jbe     short loc_1804BF4F1
0x1804bf4ee  mov     rax, [rax]
0x1804bf4f1  mov     r9d, 5
0x1804bf4f7  lea     r8, aHttps_0; "https"
0x1804bf4fe  mov     rcx, rax
0x1804bf501  call    ??$_Traits_equal@U?$char_traits@D@std@@@std@@YA_NQEBD_K01@Z; std::_Traits_equal<std::char_traits<char>>(char const * const,unsigned __int64,char const * const,unsigned __int64)
0x1804bf506  movzx   eax, al
0x1804bf509  shl     eax, 17h
0x1804bf50c  mov     [rsp+130h+var_E8], eax
0x1804bf510  lea     rcx, [rbp+57h+var_60]; this
0x1804bf514  call    ??1BrowserNativeResult@Authentication@Microsoft@@QEAA@XZ; Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult(void)
0x1804bf519  lea     r9, aOpeningSession; "Opening session handle"
0x1804bf520  mov     r8, rsi
0x1804bf523  mov     edx, 5Eh ; '^'
0x1804bf528  lea     ecx, [rdx-5Dh]
0x1804bf52b  call    ?LogWithFormat@LoggingImpl@Msai@@SAXW4LogLevelInternal@2@HPEBD1ZZ; Msai::LoggingImpl::LogWithFormat(Msai::LogLevelInternal,int,char const *,char const *,...)
0x1804bf530  mov     [rsp+130h+dwFlags], 10000000h; dwFlags
0x1804bf538  xor     r9d, r9d; lpszProxyBypass
0x1804bf53b  xor     r8d, r8d; lpszProxy
0x1804bf53e  xor     edx, edx; dwAccessType
0x1804bf540  lea     rcx, szAgent; "Mozilla/5.0 (compatible; MSAL 1.0)"
0x1804bf547  call    cs:__imp_InternetOpenA
0x1804bf54d  mov     [rdi+78h], rax
0x1804bf551  test    rax, rax
0x1804bf554  jnz     short loc_1804BF5A9
0x1804bf556  call    cs:__imp_GetLastError
0x1804bf55c  mov     eax, eax
0x1804bf55e  lea     rcx, aCouldnTOpenASe; "Couldn't open a session handle via Inte"...
0x1804bf565  mov     qword ptr [rsp+130h+dwService], rcx
0x1804bf56a  mov     qword ptr [rsp+130h+dwFlags], rax
0x1804bf56f  xor     r9d, r9d
0x1804bf572  xor     r8d, r8d
0x1804bf575  mov     edx, 236496D5h
0x1804bf57a  lea     rcx, [rsp+130h+var_D8]
0x1804bf57f  call    ?Create@TempErrorFactoryImpl@Msai@@SA?AUTempError@2@HW4StatusInternal@2@W4SubStatusInternal@2@_JPEBDZZ; Msai::TempErrorFactoryImpl::Create(int,Msai::StatusInternal,Msai::SubStatusInternal,__int64,char const *,...)
0x1804bf584  nop
0x1804bf585  mov     rdx, rax; struct Msai::TempError *
0x1804bf588  mov     rcx, rdi; this
0x1804bf58b  call    ?FireOnFailed@HttpClientImpl@Msai@@AEAAXAEBUTempError@2@@Z; Msai::HttpClientImpl::FireOnFailed(Msai::TempError const &)
0x1804bf590  nop
0x1804bf591  lea     rcx, [rbp+57h+var_D0]
0x1804bf595  call    ??1?$_Hash@V?$_Umap_traits@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@V?$_Uhash_compare@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@U?$hash@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@U?$equal_to@V?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@@2@@2@V?$allocator@U?$pair@$$CBV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@V12@@std@@@2@$0A@@std@@@std@@QEAA@XZ; std::_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>::~_Hash<std::_Umap_traits<std::string,std::string,std::_Uhash_compare<std::string,std::hash<std::string>,std::equal_to<std::string>>,std::allocator<std::pair<std::string const,std::string>>,0>>(void)
0x1804bf59a  nop
0x1804bf59b  lea     rcx, [rbp+57h+Src]
0x1804bf59f  call    ??1?$shared_ptr@VBrowserNativeResultInternal@Msai@@@std@@QEAA@XZ; std::shared_ptr<Msai::BrowserNativeResultInternal>::~shared_ptr<Msai::BrowserNativeResultInternal>(void)
0x1804bf5a4  jmp     loc_1804BF9C6
0x1804bf5a9  lea     r9, aRegisteringCal; "Registering callback"
0x1804bf5b0  mov     r8, rsi
0x1804bf5b3  mov     edx, 6Dh ; 'm'
0x1804bf5b8  lea     ecx, [rdx-6Ch]
0x1804bf5bb  call    ?LogWithFormat@LoggingImpl@Msai@@SAXW4LogLevelInternal@2@HPEBD1ZZ; Msai::LoggingImpl::LogWithFormat(Msai::LogLevelInternal,int,char const *,char const *,...)
0x1804bf5c0  lea     rdx, ?StaticCallback@HttpClientImpl@Msai@@CAXPEAX_KK0K@Z; lpfnInternetCallback
0x1804bf5c7  mov     rcx, [rdi+78h]; hInternet
0x1804bf5cb  call    cs:__imp_InternetSetStatusCallbackW
0x1804bf5d1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1804bf5d5  jnz     short loc_1804BF617
0x1804bf5d7  call    cs:__imp_GetLastError
0x1804bf5dd  mov     eax, eax
0x1804bf5df  lea     rcx, aInternetsetsta_0; "InternetSetStatusCallback failed with I"...
0x1804bf5e6  mov     qword ptr [rsp+130h+dwService], rcx
0x1804bf5eb  mov     qword ptr [rsp+130h+dwFlags], rax
0x1804bf5f0  xor     r9d, r9d
0x1804bf5f3  xor     r8d, r8d
0x1804bf5f6  mov     edx, 236496D6h
0x1804bf5fb  lea     rcx, [rsp+130h+var_D8]
0x1804bf600  call    ?Create@TempErrorFactoryImpl@Msai@@SA?AUTempError@2@HW4StatusInternal@2@W4SubStatusInternal@2@_JPEBDZZ; Msai::TempErrorFactoryImpl::Create(int,Msai::StatusInternal,Msai::SubStatusInternal,__int64,char const *,...)
0x1804bf605  nop
0x1804bf606  mov     rdx, rax; struct Msai::TempError *
0x1804bf609  mov     rcx, rdi; this
0x1804bf60c  call    ?FireOnFailed@HttpClientImpl@Msai@@AEAAXAEBUTempError@2@@Z; Msai::HttpClientImpl::FireOnFailed(Msai::TempError const &)
0x1804bf611  nop
0x1804bf612  jmp     loc_1804BF591
0x1804bf617  lea     r9, aOpeningConnect; "Opening connection handle"
0x1804bf61e  mov     r8, rsi
0x1804bf621  mov     edx, 78h ; 'x'
0x1804bf626  lea     ecx, [rdx-77h]
0x1804bf629  call    ?LogWithFormat@LoggingImpl@Msai@@SAXW4LogLevelInternal@2@HPEBD1ZZ; Msai::LoggingImpl::LogWithFormat(Msai::LogLevelInternal,int,char const *,char const *,...)
0x1804bf62e  lea     rdx, [rbp+57h+var_60]
0x1804bf632  mov     rcx, r15
0x1804bf635  call    ?GetEnvironment@Uri@Msai@@QEBA?AV?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@XZ; Msai::Uri::GetEnvironment(void)
0x1804bf63a  cmp     qword ptr [rax+18h], 0Fh
0x1804bf63f  jbe     short loc_1804BF644
0x1804bf641  mov     rax, [rax]
0x1804bf644  mov     [rsp+130h+dwContext], rdi; dwContext
0x1804bf649  mov     [rsp+130h+var_100], 0; dwFlags
0x1804bf651  mov     [rsp+130h+dwService], 3; dwService
0x1804bf659  mov     qword ptr [rsp+130h+dwFlags], 0; lpszPassword
0x1804bf662  xor     r9d, r9d; lpszUserName
0x1804bf665  movzx   r8d, r14w; nServerPort
0x1804bf669  mov     rdx, rax; lpszServerName
0x1804bf66c  mov     rcx, [rdi+78h]; hInternet
0x1804bf670  call    cs:__imp_InternetConnectA
0x1804bf676  mov     [rdi+80h], rax
0x1804bf67d  lea     rcx, [rbp+57h+var_60]; this
0x1804bf681  call    ??1BrowserNativeResult@Authentication@Microsoft@@QEAA@XZ; Microsoft::Authentication::BrowserNativeResult::~BrowserNativeResult(void)
0x1804bf686  xor     r14d, r14d
0x1804bf689  cmp     [rdi+80h], r14
0x1804bf690  jnz     short loc_1804BF6D2
0x1804bf692  call    cs:__imp_GetLastError
0x1804bf698  mov     eax, eax
0x1804bf69a  lea     rcx, aUnableToOpenAC; "Unable to open a connection handle via "...
0x1804bf6a1  mov     qword ptr [rsp+130h+dwService], rcx
0x1804bf6a6  mov     qword ptr [rsp+130h+dwFlags], rax
0x1804bf6ab  xor     r9d, r9d
0x1804bf6ae  xor     r8d, r8d
0x1804bf6b1  mov     edx, 23818285h
0x1804bf6b6  lea     rcx, [rsp+130h+var_D8]
0x1804bf6bb  call    ?Create@TempErrorFactoryImpl@Msai@@SA?AUTempError@2@HW4StatusInternal@2@W4SubStatusInternal@2@_JPEBDZZ; Msai::TempErrorFactoryImpl::Create(int,Msai::StatusInternal,Msai::SubStatusInternal,__int64,char const *,...)
0x1804bf6c0  nop
0x1804bf6c1  mov     rdx, rax; struct Msai::TempError *
0x1804bf6c4  mov     rcx, rdi; this
0x1804bf6c7  call    ?FireOnFailed@HttpClientImpl@Msai@@AEAAXAEBUTempError@2@@Z; Msai::HttpClientImpl::FireOnFailed(Msai::TempError const &)
0x1804bf6cc  nop
0x1804bf6cd  jmp     loc_1804BF591
0x1804bf6d2  mov     eax, [rdi+8]
0x1804bf6d5  mov     [rsp+130h+dwFlags], eax
0x1804bf6d9  lea     r9, aSettingReadTim; "Setting read timeout to %lu seconds"
0x1804bf6e0  mov     r8, rsi
0x1804bf6e3  mov     edx, 8Ah
0x1804bf6e8  mov     ecx, 1
  ... truncated ...
```
