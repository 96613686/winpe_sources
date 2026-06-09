# CUserIdentityProvider::MakeAccountJsonObject(Windows::Data::Json::IJsonValueStatics *,HSTRING__ *,HSTRING__ *,bool,HSTRING__ *,Windows::Data::Json::IJsonValue * *)

- ea: `0x1800b6360`
- end: `0x1800b6775`
- name: `?MakeAccountJsonObject@CUserIdentityProvider@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEAUHSTRING__@@1_N1PEAPEAUIJsonValue@345@@Z`
- size: `1045`
- prototype: `__int64 __fastcall(CUserIdentityProvider *__hidden this, struct Windows::Data::Json::IJsonValueStatics *, HSTRING, HSTRING, bool, HSTRING, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800b483c`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x1800168c8`
- `0x180032640`
- `0x1800327e4`
- `0x180036fc8`
- `0x1800b6360`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6536`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6607`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b66bd`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6467`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6536`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b6607`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800b66bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b647b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b654a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b661b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b66d1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b647b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b654a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b661b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800b66d1`

## string_xrefs

- `0x1800b63c1`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b6408`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b64db`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b65ac`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`
- `0x1800b6711`: `onecore\base\flighting\flightsettings\broker\lib\useridentityprovider.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall CUserIdentityProvider::MakeAccountJsonObject(
        CUserIdentityProvider *this,
        struct Windows::Data::Json::IJsonValueStatics *a2,
        HSTRING a3,
        HSTRING a4,
        bool a5,
        HSTRING a6,
        struct Windows::Data::Json::IJsonValue **a7)
{
  __int64 *v10; // rax
  int v11; // eax
  unsigned int v12; // ebx
  __int64 (__fastcall *v13)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *); // rbx
  int v14; // eax
  __int64 v15; // rdx
  __int64 v16; // r14
  __int64 (__fastcall *v17)(__int64, HSTRING, __int64); // r12
  __int64 v18; // r15
  unsigned __int64 v19; // rdi
  unsigned __int64 v20; // rcx
  const ULONG_PTR *v21; // r9
  __int64 (__fastcall *v22)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *); // rbx
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // r14
  __int64 (__fastcall *v26)(__int64, HSTRING, __int64); // r12
  __int64 v27; // r15
  unsigned __int64 v28; // rcx
  __int64 (__fastcall *v29)(struct Windows::Data::Json::IJsonValueStatics *, __int64, __int64 *); // rbx
  __int64 v30; // rdx
  int v31; // eax
  __int64 v32; // rdx
  __int64 v33; // r14
  __int64 (__fastcall *v34)(__int64, HSTRING, __int64); // r12
  __int64 v35; // r15
  unsigned __int64 v36; // rcx
  __int64 (__fastcall *v37)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *); // rbx
  int v38; // eax
  __int64 v39; // rdx
  __int64 v40; // rsi
  __int64 (__fastcall *v41)(__int64, HSTRING, __int64); // r15
  __int64 v42; // r14
  __int64 v43; // rdx
  UINT32 length; // [rsp+20h] [rbp-61h] BYREF
  __int64 v46; // [rsp+28h] [rbp-59h] BYREF
  __int64 v47; // [rsp+30h] [rbp-51h] BYREF
  __int64 v48; // [rsp+38h] [rbp-49h] BYREF
  __int64 v49; // [rsp+40h] [rbp-41h] BYREF
  __int64 v50; // [rsp+48h] [rbp-39h] BYREF
  struct Windows::Data::Json::IJsonValue **v51; // [rsp+50h] [rbp-31h]
  HSTRING string; // [rsp+58h] [rbp-29h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+60h] [rbp-21h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+47h]

  v51 = a7;
  v49 = 0;
  v10 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[29])a2);
  v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v10, &v49);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v46 = 0;
    v13 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *))(*(_QWORD *)a2 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    v14 = v13(a2, a3, &v46);
    v12 = v14;
    if ( v14 < 0 )
    {
      v15 = 1139;
LABEL_5:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v15,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v14,
        length);
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      goto LABEL_45;
    }
    v16 = v49;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v49 + 56LL);
    v18 = v46;
    length = 0;
    v19 = -1;
    v20 = -1;
    do
      ++v20;
    while ( CUserIdentityProvider::s_accountIdJsonTag[v20] );
    if ( (int)ULongLongToUInt(v20, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, v21);
    WindowsCreateStringReference(CUserIdentityProvider::s_accountIdJsonTag, length, &hstringHeader, &string);
    v14 = v17(v16, string, v18);
    v12 = v14;
    if ( v14 < 0 )
    {
      v15 = 1140;
      goto LABEL_5;
    }
    v47 = 0;
    v22 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *))(*(_QWORD *)a2 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    v23 = v22(a2, a4, &v47);
    v12 = v23;
    if ( v23 < 0 )
    {
      v24 = 1143;
LABEL_14:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v24,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v23,
        length);
LABEL_43:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
      goto LABEL_44;
    }
    v25 = v49;
    v26 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v49 + 56LL);
    v27 = v47;
    length = 0;
    v28 = -1;
    do
      ++v28;
    while ( CUserIdentityProvider::s_accountTypeJsonTag[v28] );
    if ( (int)ULongLongToUInt(v28, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(CUserIdentityProvider::s_accountTypeJsonTag, length, &hstringHeader, &string);
    v23 = v26(v25, string, v27);
    v12 = v23;
    if ( v23 < 0 )
    {
      v24 = 1144;
      goto LABEL_14;
    }
    v48 = 0;
    v29 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, __int64, __int64 *))(*(_QWORD *)a2 + 72LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    v31 = v29(a2, v30, &v48);
    v12 = v31;
    if ( v31 < 0 )
    {
      v32 = 1147;
LABEL_23:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v32,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
        (const char *)(unsigned int)v31,
        length);
LABEL_42:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
      goto LABEL_43;
    }
    v33 = v49;
    v34 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v49 + 56LL);
    v35 = v48;
    length = 0;
    v36 = -1;
    do
      ++v36;
    while ( CUserIdentityProvider::s_isPrimaryJsonTag[v36] );
    if ( (int)ULongLongToUInt(v36, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(CUserIdentityProvider::s_isPrimaryJsonTag, length, &hstringHeader, &string);
    v31 = v34(v33, string, v35);
    v12 = v31;
    if ( v31 < 0 )
    {
      v32 = 1148;
      goto LABEL_23;
    }
    v50 = 0;
    v37 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *))(*(_QWORD *)a2 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
    v38 = v37(a2, a6, &v50);
    v12 = v38;
    if ( v38 >= 0 )
    {
      v40 = v49;
      v41 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v49 + 56LL);
      v42 = v50;
      length = 0;
      do
        ++v19;
      while ( CUserIdentityProvider::s_authTicketJsonTag[v19] );
      if ( (int)ULongLongToUInt(v19, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(CUserIdentityProvider::s_authTicketJsonTag, length, &hstringHeader, &string);
      v38 = v41(v40, string, v42);
      v12 = v38;
      if ( v38 >= 0 )
      {
        v38 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::CopyTo(&v49, v43, v51);
        v12 = v38;
        if ( v38 >= 0 )
        {
LABEL_41:
          Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
          goto LABEL_42;
        }
        v39 = 1154;
      }
      else
      {
        v39 = 1152;
      }
    }
    else
    {
      v39 = 1151;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v39,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
      (const char *)(unsigned int)v38,
      length);
    goto LABEL_41;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x470,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\useridentityprovider.cpp",
    (const char *)(unsigned int)v11,
    length);
LABEL_45:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
  return v12;
}

```

## disassembly

```asm
0x1800b6360  push    rbp
0x1800b6362  push    rbx
0x1800b6363  push    rsi
0x1800b6364  push    rdi
0x1800b6365  push    r12
0x1800b6367  push    r13
0x1800b6369  push    r14
0x1800b636b  push    r15
0x1800b636d  lea     rbp, [rsp-7]
0x1800b6372  sub     rsp, 88h
0x1800b6379  mov     rax, cs:__security_cookie
0x1800b6380  xor     rax, rsp
0x1800b6383  mov     [rbp+3Fh+var_48], rax
0x1800b6387  mov     r13, r9
0x1800b638a  mov     rdi, r8
0x1800b638d  mov     rsi, rdx
0x1800b6390  mov     rax, [rbp+3Fh+arg_30]
0x1800b6394  mov     [rbp+3Fh+var_70], rax
0x1800b6398  xor     r14d, r14d
0x1800b639b  mov     [rbp+3Fh+var_80], r14
0x1800b639f  lea     rcx, [rbp+3Fh+string]; string
0x1800b63a3  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800b63a8  lea     rdx, [rbp+3Fh+var_80]
0x1800b63ac  mov     rcx, [rax]
0x1800b63af  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800b63b4  mov     ebx, eax
0x1800b63b6  test    eax, eax
0x1800b63b8  jns     short loc_1800B63D7
0x1800b63ba  mov     rcx, [rbp+47h]; this
0x1800b63be  mov     r9d, eax; char *
0x1800b63c1  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b63c8  mov     edx, 470h; void *
0x1800b63cd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b63d2  jmp     loc_1800B674A
0x1800b63d7  mov     [rbp+3Fh+var_98], r14
0x1800b63db  mov     rax, [rsi]
0x1800b63de  mov     rbx, [rax+50h]
0x1800b63e2  lea     rcx, [rbp+3Fh+var_98]
0x1800b63e6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b63eb  lea     r8, [rbp+3Fh+var_98]
0x1800b63ef  mov     rdx, rdi
0x1800b63f2  mov     rcx, rsi
0x1800b63f5  mov     rax, rbx
0x1800b63f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b63fd  mov     ebx, eax
0x1800b63ff  test    eax, eax
0x1800b6401  jns     short loc_1800B6420
0x1800b6403  mov     edx, 473h; void *
0x1800b6408  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b640f  mov     r9d, eax; char *
0x1800b6412  mov     rcx, [rbp+47h]; this
0x1800b6416  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b641b  jmp     loc_1800B6740
0x1800b6420  mov     r14, [rbp+3Fh+var_80]
0x1800b6424  mov     rax, [r14]
0x1800b6427  mov     r12, [rax+38h]
0x1800b642b  mov     r15, [rbp+3Fh+var_98]
0x1800b642f  mov     rbx, cs:?s_accountIdJsonTag@CUserIdentityProvider@@0QEBGEB; ushort const * const CUserIdentityProvider::s_accountIdJsonTag
0x1800b6436  xor     r9d, r9d
0x1800b6439  mov     [rbp+3Fh+length], r9d
0x1800b643d  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800b6441  mov     rcx, rdi
0x1800b6444  inc     rcx; unsigned __int64
0x1800b6447  cmp     [rbx+rcx*2], r9w
0x1800b644c  jnz     short loc_1800B6444
0x1800b644e  lea     rdx, [rbp+3Fh+length]; unsigned int *
0x1800b6452  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800b6457  test    eax, eax
0x1800b6459  jns     short loc_1800B646D
0x1800b645b  xor     r8d, r8d; nNumberOfArguments
0x1800b645e  lea     edx, [r8+1]; dwExceptionFlags
0x1800b6462  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b6467  call    cs:__imp_RaiseException
0x1800b646d  lea     r9, [rbp+3Fh+string]; string
0x1800b6471  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800b6475  mov     edx, [rbp+3Fh+length]; length
0x1800b6478  mov     rcx, rbx; sourceString
0x1800b647b  call    cs:__imp_WindowsCreateStringReference
0x1800b6481  mov     r8, r15
0x1800b6484  mov     rdx, [rbp+3Fh+string]
0x1800b6488  mov     rcx, r14
0x1800b648b  mov     rax, r12
0x1800b648e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6493  mov     ebx, eax
0x1800b6495  test    eax, eax
0x1800b6497  jns     short loc_1800B64A3
0x1800b6499  mov     edx, 474h
0x1800b649e  jmp     loc_1800B6408
0x1800b64a3  mov     [rbp+3Fh+var_90], 0
0x1800b64ab  mov     rax, [rsi]
0x1800b64ae  mov     rbx, [rax+50h]
0x1800b64b2  lea     rcx, [rbp+3Fh+var_90]
0x1800b64b6  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b64bb  lea     r8, [rbp+3Fh+var_90]
0x1800b64bf  mov     rdx, r13
0x1800b64c2  mov     rcx, rsi
0x1800b64c5  mov     rax, rbx
0x1800b64c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b64cd  mov     ebx, eax
0x1800b64cf  xor     r13d, r13d
0x1800b64d2  test    eax, eax
0x1800b64d4  jns     short loc_1800B64F3
0x1800b64d6  mov     edx, 477h; void *
0x1800b64db  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b64e2  mov     r9d, eax; char *
0x1800b64e5  mov     rcx, [rbp+47h]; this
0x1800b64e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b64ee  jmp     loc_1800B6736
0x1800b64f3  mov     r14, [rbp+3Fh+var_80]
0x1800b64f7  mov     rax, [r14]
0x1800b64fa  mov     r12, [rax+38h]
0x1800b64fe  mov     r15, [rbp+3Fh+var_90]
0x1800b6502  mov     rbx, cs:?s_accountTypeJsonTag@CUserIdentityProvider@@0QEBGEB; ushort const * const CUserIdentityProvider::s_accountTypeJsonTag
0x1800b6509  mov     [rbp+3Fh+length], r13d
0x1800b650d  mov     rcx, rdi
0x1800b6510  inc     rcx; unsigned __int64
0x1800b6513  cmp     [rbx+rcx*2], r13w
0x1800b6518  jnz     short loc_1800B6510
0x1800b651a  lea     rdx, [rbp+3Fh+length]; unsigned int *
0x1800b651e  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800b6523  test    eax, eax
0x1800b6525  jns     short loc_1800B653C
0x1800b6527  xor     r9d, r9d; lpArguments
0x1800b652a  xor     r8d, r8d; nNumberOfArguments
0x1800b652d  lea     edx, [r9+1]; dwExceptionFlags
0x1800b6531  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b6536  call    cs:__imp_RaiseException
0x1800b653c  lea     r9, [rbp+3Fh+string]; string
0x1800b6540  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800b6544  mov     edx, [rbp+3Fh+length]; length
0x1800b6547  mov     rcx, rbx; sourceString
0x1800b654a  call    cs:__imp_WindowsCreateStringReference
0x1800b6550  mov     r8, r15
0x1800b6553  mov     rdx, [rbp+3Fh+string]
0x1800b6557  mov     rcx, r14
0x1800b655a  mov     rax, r12
0x1800b655d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6562  mov     ebx, eax
0x1800b6564  test    eax, eax
0x1800b6566  jns     short loc_1800B6572
0x1800b6568  mov     edx, 478h
0x1800b656d  jmp     loc_1800B64DB
0x1800b6572  mov     [rbp+3Fh+var_88], r13
0x1800b6576  mov     rax, [rsi]
0x1800b6579  mov     rbx, [rax+48h]
0x1800b657d  lea     rcx, [rbp+3Fh+var_88]
0x1800b6581  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b6586  movzx   ecx, [rbp+3Fh+arg_20]
0x1800b658a  movd    xmm1, ecx
0x1800b658e  cvtdq2pd xmm1, xmm1
0x1800b6592  lea     r8, [rbp+3Fh+var_88]
0x1800b6596  mov     rcx, rsi
0x1800b6599  mov     rax, rbx
0x1800b659c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b65a1  mov     ebx, eax
0x1800b65a3  test    eax, eax
0x1800b65a5  jns     short loc_1800B65C4
0x1800b65a7  mov     edx, 47Bh; void *
0x1800b65ac  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b65b3  mov     r9d, eax; char *
0x1800b65b6  mov     rcx, [rbp+47h]; this
0x1800b65ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b65bf  jmp     loc_1800B672C
0x1800b65c4  mov     r14, [rbp+3Fh+var_80]
0x1800b65c8  mov     rax, [r14]
0x1800b65cb  mov     r12, [rax+38h]
0x1800b65cf  mov     r15, [rbp+3Fh+var_88]
0x1800b65d3  mov     rbx, cs:?s_isPrimaryJsonTag@CUserIdentityProvider@@0QEBGEB; ushort const * const CUserIdentityProvider::s_isPrimaryJsonTag
0x1800b65da  mov     [rbp+3Fh+length], r13d
0x1800b65de  mov     rcx, rdi
0x1800b65e1  inc     rcx; unsigned __int64
0x1800b65e4  cmp     [rbx+rcx*2], r13w
0x1800b65e9  jnz     short loc_1800B65E1
0x1800b65eb  lea     rdx, [rbp+3Fh+length]; unsigned int *
0x1800b65ef  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800b65f4  test    eax, eax
0x1800b65f6  jns     short loc_1800B660D
0x1800b65f8  xor     r9d, r9d; lpArguments
0x1800b65fb  xor     r8d, r8d; nNumberOfArguments
0x1800b65fe  lea     edx, [r9+1]; dwExceptionFlags
0x1800b6602  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b6607  call    cs:__imp_RaiseException
0x1800b660d  lea     r9, [rbp+3Fh+string]; string
0x1800b6611  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800b6615  mov     edx, [rbp+3Fh+length]; length
0x1800b6618  mov     rcx, rbx; sourceString
0x1800b661b  call    cs:__imp_WindowsCreateStringReference
0x1800b6621  mov     r8, r15
0x1800b6624  mov     rdx, [rbp+3Fh+string]
0x1800b6628  mov     rcx, r14
0x1800b662b  mov     rax, r12
0x1800b662e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b6633  mov     ebx, eax
0x1800b6635  test    eax, eax
0x1800b6637  jns     short loc_1800B6643
0x1800b6639  mov     edx, 47Ch
0x1800b663e  jmp     loc_1800B65AC
0x1800b6643  mov     [rbp+3Fh+var_78], r13
0x1800b6647  mov     rax, [rsi]
0x1800b664a  mov     rbx, [rax+50h]
0x1800b664e  lea     rcx, [rbp+3Fh+var_78]
0x1800b6652  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b6657  lea     r8, [rbp+3Fh+var_78]
0x1800b665b  mov     rdx, [rbp+3Fh+arg_28]
0x1800b665f  mov     rcx, rsi
0x1800b6662  mov     rax, rbx
0x1800b6665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b666a  mov     ebx, eax
0x1800b666c  test    eax, eax
0x1800b666e  jns     short loc_1800B667A
0x1800b6670  mov     edx, 47Fh
0x1800b6675  jmp     loc_1800B670E
0x1800b667a  mov     rsi, [rbp+3Fh+var_80]
0x1800b667e  mov     rax, [rsi]
0x1800b6681  mov     r15, [rax+38h]
0x1800b6685  mov     r14, [rbp+3Fh+var_78]
0x1800b6689  mov     rbx, cs:?s_authTicketJsonTag@CUserIdentityProvider@@0QEBGEB; ushort const * const CUserIdentityProvider::s_authTicketJsonTag
0x1800b6690  mov     [rbp+3Fh+length], r13d
0x1800b6694  inc     rdi
0x1800b6697  cmp     [rbx+rdi*2], r13w
0x1800b669c  jnz     short loc_1800B6694
0x1800b669e  lea     rdx, [rbp+3Fh+length]; unsigned int *
0x1800b66a2  mov     rcx, rdi; unsigned __int64
0x1800b66a5  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800b66aa  test    eax, eax
0x1800b66ac  jns     short loc_1800B66C3
0x1800b66ae  xor     r9d, r9d; lpArguments
0x1800b66b1  xor     r8d, r8d; nNumberOfArguments
0x1800b66b4  lea     edx, [r9+1]; dwExceptionFlags
0x1800b66b8  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800b66bd  call    cs:__imp_RaiseException
0x1800b66c3  lea     r9, [rbp+3Fh+string]; string
0x1800b66c7  lea     r8, [rbp+3Fh+hstringHeader]; hstringHeader
0x1800b66cb  mov     edx, [rbp+3Fh+length]; length
0x1800b66ce  mov     rcx, rbx; sourceString
0x1800b66d1  call    cs:__imp_WindowsCreateStringReference
0x1800b66d7  mov     r8, r14
0x1800b66da  mov     rdx, [rbp+3Fh+string]
0x1800b66de  mov     rcx, rsi
0x1800b66e1  mov     rax, r15
0x1800b66e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b66e9  mov     ebx, eax
0x1800b66eb  test    eax, eax
0x1800b66ed  jns     short loc_1800B66F6
0x1800b66ef  mov     edx, 480h
0x1800b66f4  jmp     short loc_1800B670E
0x1800b66f6  mov     r8, [rbp+3Fh+var_70]
0x1800b66fa  lea     rcx, [rbp+3Fh+var_80]
0x1800b66fe  call    ?CopyTo@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::CopyTo(_GUID const &,void * *)
0x1800b6703  mov     ebx, eax
0x1800b6705  test    eax, eax
0x1800b6707  jns     short loc_1800B6722
0x1800b6709  mov     edx, 482h; void *
0x1800b670e  mov     r9d, eax; char *
0x1800b6711  lea     r8, aOnecoreBaseFli_12; "onecore\\base\\flighting\\flightsetting"...
0x1800b6718  mov     rcx, [rbp+47h]; this
0x1800b671c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b6721  nop
0x1800b6722  lea     rcx, [rbp+3Fh+var_78]
0x1800b6726  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b672b  nop
0x1800b672c  lea     rcx, [rbp+3Fh+var_88]
0x1800b6730  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b6735  nop
0x1800b6736  lea     rcx, [rbp+3Fh+var_90]
0x1800b673a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b673f  nop
0x1800b6740  lea     rcx, [rbp+3Fh+var_98]
0x1800b6744  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b6749  nop
0x1800b674a  lea     rcx, [rbp+3Fh+var_80]
0x1800b674e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800b6753  mov     eax, ebx
0x1800b6755  mov     rcx, [rbp+3Fh+var_48]
0x1800b6759  xor     rcx, rsp; StackCookie
0x1800b675c  call    __security_check_cookie
0x1800b6761  add     rsp, 88h
0x1800b6768  pop     r15
0x1800b676a  pop     r14
0x1800b676c  pop     r13
0x1800b676e  pop     r12
0x1800b6770  pop     rdi
0x1800b6771  pop     rsi
0x1800b6772  pop     rbx
0x1800b6773  pop     rbp
0x1800b6774  retn
```
