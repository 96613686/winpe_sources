# FSPropertyBag::GetCtacCollection(Windows::Data::Json::IJsonValueStatics *,Windows::Internal::Flighting::ICommonTargetingAttributesFactory *,ushort const *,Windows::Data::Json::IJsonValue * *)

- ea: `0x1800bbcac`
- end: `0x1800bc072`
- name: `?GetCtacCollection@FSPropertyBag@@AEAAJPEAUIJsonValueStatics@Json@Data@Windows@@PEAUICommonTargetingAttributesFactory@Flighting@Internal@5@PEBGPEAPEAUIJsonValue@345@@Z`
- size: `966`
- prototype: `int(FSPropertyBag *__hidden this, struct Windows::Data::Json::IJsonValueStatics *, struct Windows::Internal::Flighting::ICommonTargetingAttributesFactory *, const unsigned __int16 *, struct Windows::Data::Json::IJsonValue **)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800bb934`

## callees

- `0x180004b80`
- `0x18000b19c`
- `0x18000cc8c`
- `0x180010fe0`
- `0x1800168c8`
- `0x180032640`
- `0x1800327e4`
- `0x180036fc8`
- `0x1800bbcac`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbd23`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbd5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbe79`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbf35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbfb4`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbd23`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbd5d`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbe79`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbf35`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x1800bbfb4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbd0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbd71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbe8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbf49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbfc8`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbd0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbd71`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbe8d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbf49`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x1800bbfc8`

## string_xrefs

- `0x1800bbd9d`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bbdd8`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bbe22`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bbeb3`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`
- `0x1800bc007`: `onecore\base\flighting\flightsettings\broker\lib\fspropertybag.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall FSPropertyBag::GetCtacCollection(
        FSPropertyBag *this,
        struct Windows::Data::Json::IJsonValueStatics *a2,
        struct Windows::Internal::Flighting::ICommonTargetingAttributesFactory *a3,
        const unsigned __int16 *a4,
        struct Windows::Data::Json::IJsonValue **a5)
{
  __int64 (__fastcall *v8)(struct Windows::Internal::Flighting::ICommonTargetingAttributesFactory *, HSTRING, HSTRING, __int64 *); // r12
  HSTRING v9; // rbx
  unsigned __int64 v10; // rdi
  unsigned __int64 v11; // rcx
  const ULONG_PTR *v12; // r9
  int v13; // eax
  unsigned int v14; // ebx
  int v15; // eax
  __int64 (__fastcall *v16)(struct Windows::Data::Json::IJsonValueStatics *, __int64, __int64 *); // rbx
  int v17; // eax
  __int64 (__fastcall *v18)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *); // rbx
  unsigned __int64 v19; // rcx
  int v20; // eax
  const unsigned __int16 *v21; // rdx
  __int64 *v22; // rax
  int v23; // eax
  __int64 v24; // rdx
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, HSTRING, __int64); // r15
  __int64 v27; // r14
  unsigned __int64 v28; // rcx
  __int64 v29; // rsi
  __int64 (__fastcall *v30)(__int64, HSTRING, __int64); // r15
  __int64 v31; // r14
  __int64 v32; // rdx
  int v34; // [rsp+20h] [rbp-71h]
  UINT32 length; // [rsp+30h] [rbp-61h] BYREF
  __int64 v36; // [rsp+38h] [rbp-59h] BYREF
  __int64 v37; // [rsp+40h] [rbp-51h] BYREF
  __int64 v38; // [rsp+48h] [rbp-49h] BYREF
  __int64 v39; // [rsp+50h] [rbp-41h] BYREF
  __int64 v40; // [rsp+58h] [rbp-39h] BYREF
  HSTRING v41; // [rsp+60h] [rbp-31h] BYREF
  HSTRING_HEADER v42; // [rsp+68h] [rbp-29h] BYREF
  HSTRING string; // [rsp+80h] [rbp-11h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+88h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+57h]

  v40 = 0;
  v8 = *(__int64 (__fastcall **)(struct Windows::Internal::Flighting::ICommonTargetingAttributesFactory *, HSTRING, HSTRING, __int64 *))(*(_QWORD *)a3 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  if ( WindowsCreateStringReference(L"10.0", 4u, &hstringHeader, &string) < 0 )
    RaiseException(0xC000000D, 1u, 0, 0);
  v9 = string;
  length = 0;
  v10 = -1;
  v11 = -1;
  do
    ++v11;
  while ( a4[v11] );
  if ( (int)ULongLongToUInt(v11, &length) < 0 )
    RaiseException(0xC000000D, 1u, 0, v12);
  WindowsCreateStringReference(a4, length, &v42, &v41);
  v13 = v8(a3, v41, v9, &v40);
  v14 = v13;
  if ( v13 >= 0 )
  {
    v37 = 0;
    v15 = (*(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v40 + 48LL))(v40, &v37);
    v14 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x740,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v15,
        v34);
LABEL_39:
      Windows::Internal::String::~String((Windows::Internal::String *)&v37);
      goto LABEL_40;
    }
    v36 = 0;
    v16 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, __int64, __int64 *))(*(_QWORD *)a2 + 48LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
    v17 = v16(a2, v37, &v36);
    v14 = v17;
    if ( v17 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x744,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v17,
        v34);
LABEL_38:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v36);
      goto LABEL_39;
    }
    v39 = 0;
    v18 = *(__int64 (__fastcall **)(struct Windows::Data::Json::IJsonValueStatics *, HSTRING, __int64 *))(*(_QWORD *)a2 + 80LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
    length = 0;
    v19 = -1;
    do
      ++v19;
    while ( a4[v19] );
    if ( (int)ULongLongToUInt(v19, &length) < 0 )
      RaiseException(0xC000000D, 1u, 0, 0);
    WindowsCreateStringReference(a4, length, &v42, &v41);
    v20 = v18(a2, v41, &v39);
    v14 = v20;
    if ( v20 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x748,
        (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
        (const char *)(unsigned int)v20,
        v34);
LABEL_37:
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
      goto LABEL_38;
    }
    v38 = 0;
    v22 = (__int64 *)Windows::Internal::StringReference::StringReference(&v41, (const unsigned __int16 (*)[29])v21);
    v23 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(*v22, &v38);
    v14 = v23;
    if ( v23 >= 0 )
    {
      v25 = v38;
      v26 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v38 + 56LL);
      v27 = v36;
      length = 0;
      v28 = -1;
      do
        ++v28;
      while ( FSPropertyBag::s_ctacProperties[v28] );
      if ( (int)ULongLongToUInt(v28, &length) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      WindowsCreateStringReference(FSPropertyBag::s_ctacProperties, length, &v42, &v41);
      v23 = v26(v25, v41, v27);
      v14 = v23;
      if ( v23 >= 0 )
      {
        v29 = v38;
        v30 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64))(*(_QWORD *)v38 + 56LL);
        v31 = v39;
        length = 0;
        do
          ++v10;
        while ( FSPropertyBag::s_ctacAppId[v10] );
        if ( (int)ULongLongToUInt(v10, &length) < 0 )
          RaiseException(0xC000000D, 1u, 0, 0);
        WindowsCreateStringReference(FSPropertyBag::s_ctacAppId, length, &v42, &v41);
        v23 = v30(v29, v41, v31);
        v14 = v23;
        if ( v23 >= 0 )
        {
          v23 = Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::CopyTo(&v38, v32, a5);
          v14 = v23;
          if ( v23 >= 0 )
          {
LABEL_36:
            Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
            goto LABEL_37;
          }
          v24 = 1873;
        }
        else
        {
          v24 = 1871;
        }
      }
      else
      {
        v24 = 1870;
      }
    }
    else
    {
      v24 = 1868;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v24,
      (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
      (const char *)(unsigned int)v23,
      v34);
    goto LABEL_36;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x73D,
    (unsigned int)"onecore\\base\\flighting\\flightsettings\\broker\\lib\\fspropertybag.cpp",
    (const char *)(unsigned int)v13,
    v34);
LABEL_40:
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
  return v14;
}

```

## disassembly

```asm
0x1800bbcac  mov     [rsp-8+arg_0], rbx
0x1800bbcb1  push    rbp
0x1800bbcb2  push    rsi
0x1800bbcb3  push    rdi
0x1800bbcb4  push    r12
0x1800bbcb6  push    r13
0x1800bbcb8  push    r14
0x1800bbcba  push    r15
0x1800bbcbc  lea     rbp, [rsp-1Fh]
0x1800bbcc1  sub     rsp, 0B0h
0x1800bbcc8  mov     rax, cs:__security_cookie
0x1800bbccf  xor     rax, rsp
0x1800bbcd2  mov     [rbp+4Fh+var_40], rax
0x1800bbcd6  mov     rsi, r9
0x1800bbcd9  mov     r15, r8
0x1800bbcdc  mov     r14, rdx
0x1800bbcdf  mov     r13, [rbp+4Fh+arg_20]
0x1800bbce3  xor     edi, edi
0x1800bbce5  mov     [rbp+4Fh+var_88], rdi
0x1800bbce9  mov     rax, [r8]
0x1800bbcec  mov     r12, [rax+30h]
0x1800bbcf0  lea     rcx, [rbp+4Fh+var_88]
0x1800bbcf4  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbcf9  lea     r9, [rbp+4Fh+string]; string
0x1800bbcfd  lea     r8, [rbp+4Fh+hstringHeader]; hstringHeader
0x1800bbd01  lea     edx, [rdi+4]; length
0x1800bbd04  lea     rcx, a100; "10.0"
0x1800bbd0b  call    cs:__imp_WindowsCreateStringReference
0x1800bbd11  test    eax, eax
0x1800bbd13  jns     short loc_1800BBD29
0x1800bbd15  xor     r9d, r9d; lpArguments
0x1800bbd18  xor     r8d, r8d; nNumberOfArguments
0x1800bbd1b  lea     edx, [rdi+1]; dwExceptionFlags
0x1800bbd1e  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bbd23  call    cs:__imp_RaiseException
0x1800bbd29  mov     rbx, [rbp+4Fh+string]
0x1800bbd2d  mov     [rbp+4Fh+length], edi
0x1800bbd30  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800bbd34  mov     rcx, rdi
0x1800bbd37  xor     r9d, r9d
0x1800bbd3a  inc     rcx; unsigned __int64
0x1800bbd3d  cmp     [rsi+rcx*2], r9w
0x1800bbd42  jnz     short loc_1800BBD3A
0x1800bbd44  lea     rdx, [rbp+4Fh+length]; unsigned int *
0x1800bbd48  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bbd4d  test    eax, eax
0x1800bbd4f  jns     short loc_1800BBD63
0x1800bbd51  xor     r8d, r8d; nNumberOfArguments
0x1800bbd54  lea     edx, [r8+1]; dwExceptionFlags
0x1800bbd58  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bbd5d  call    cs:__imp_RaiseException
0x1800bbd63  lea     r9, [rbp+4Fh+var_80]; string
0x1800bbd67  lea     r8, [rbp+4Fh+var_78]; hstringHeader
0x1800bbd6b  mov     edx, [rbp+4Fh+length]; length
0x1800bbd6e  mov     rcx, rsi; sourceString
0x1800bbd71  call    cs:__imp_WindowsCreateStringReference
0x1800bbd77  lea     r9, [rbp+4Fh+var_88]
0x1800bbd7b  mov     r8, rbx
0x1800bbd7e  mov     rdx, [rbp+4Fh+var_80]
0x1800bbd82  mov     rcx, r15
0x1800bbd85  mov     rax, r12
0x1800bbd88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbd8d  mov     ebx, eax
0x1800bbd8f  xor     r12d, r12d
0x1800bbd92  test    eax, eax
0x1800bbd94  jns     short loc_1800BBDB3
0x1800bbd96  mov     rcx, [rbp+57h]; this
0x1800bbd9a  mov     r9d, eax; char *
0x1800bbd9d  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bbda4  mov     edx, 73Dh; void *
0x1800bbda9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbdae  jmp     loc_1800BC040
0x1800bbdb3  mov     [rbp+4Fh+var_A0], r12
0x1800bbdb7  mov     rcx, [rbp+4Fh+var_88]
0x1800bbdbb  mov     rax, [rcx]
0x1800bbdbe  lea     rdx, [rbp+4Fh+var_A0]
0x1800bbdc2  mov     rax, [rax+30h]
0x1800bbdc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbdcb  mov     ebx, eax
0x1800bbdcd  test    eax, eax
0x1800bbdcf  jns     short loc_1800BBDEE
0x1800bbdd1  mov     rcx, [rbp+57h]; this
0x1800bbdd5  mov     r9d, eax; char *
0x1800bbdd8  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bbddf  mov     edx, 740h; void *
0x1800bbde4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbde9  jmp     loc_1800BC036
0x1800bbdee  mov     [rbp+4Fh+var_A8], r12
0x1800bbdf2  mov     rax, [r14]
0x1800bbdf5  mov     rbx, [rax+30h]
0x1800bbdf9  lea     rcx, [rbp+4Fh+var_A8]
0x1800bbdfd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbe02  lea     r8, [rbp+4Fh+var_A8]
0x1800bbe06  mov     rdx, [rbp+4Fh+var_A0]
0x1800bbe0a  mov     rcx, r14
0x1800bbe0d  mov     rax, rbx
0x1800bbe10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbe15  mov     ebx, eax
0x1800bbe17  test    eax, eax
0x1800bbe19  jns     short loc_1800BBE38
0x1800bbe1b  mov     rcx, [rbp+57h]; this
0x1800bbe1f  mov     r9d, eax; char *
0x1800bbe22  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bbe29  mov     edx, 744h; void *
0x1800bbe2e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbe33  jmp     loc_1800BC02C
0x1800bbe38  mov     [rbp+4Fh+var_90], r12
0x1800bbe3c  mov     rax, [r14]
0x1800bbe3f  mov     rbx, [rax+50h]
0x1800bbe43  lea     rcx, [rbp+4Fh+var_90]
0x1800bbe47  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bbe4c  mov     [rbp+4Fh+length], r12d
0x1800bbe50  mov     rcx, rdi
0x1800bbe53  inc     rcx; unsigned __int64
0x1800bbe56  cmp     [rsi+rcx*2], r12w
0x1800bbe5b  jnz     short loc_1800BBE53
0x1800bbe5d  lea     rdx, [rbp+4Fh+length]; unsigned int *
0x1800bbe61  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bbe66  test    eax, eax
0x1800bbe68  jns     short loc_1800BBE7F
0x1800bbe6a  xor     r9d, r9d; lpArguments
0x1800bbe6d  xor     r8d, r8d; nNumberOfArguments
0x1800bbe70  lea     edx, [r9+1]; dwExceptionFlags
0x1800bbe74  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bbe79  call    cs:__imp_RaiseException
0x1800bbe7f  lea     r9, [rbp+4Fh+var_80]; string
0x1800bbe83  lea     r8, [rbp+4Fh+var_78]; hstringHeader
0x1800bbe87  mov     edx, [rbp+4Fh+length]; length
0x1800bbe8a  mov     rcx, rsi; sourceString
0x1800bbe8d  call    cs:__imp_WindowsCreateStringReference
0x1800bbe93  lea     r8, [rbp+4Fh+var_90]
0x1800bbe97  mov     rdx, [rbp+4Fh+var_80]
0x1800bbe9b  mov     rcx, r14
0x1800bbe9e  mov     rax, rbx
0x1800bbea1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbea6  mov     ebx, eax
0x1800bbea8  test    eax, eax
0x1800bbeaa  jns     short loc_1800BBEC9
0x1800bbeac  mov     rcx, [rbp+57h]; this
0x1800bbeb0  mov     r9d, eax; char *
0x1800bbeb3  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bbeba  mov     edx, 748h; void *
0x1800bbebf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bbec4  jmp     loc_1800BC022
0x1800bbec9  mov     [rbp+4Fh+var_98], r12
0x1800bbecd  lea     rcx, [rbp+4Fh+var_80]; string
0x1800bbed1  call    ??$?0$0BN@@StringReference@Internal@Windows@@QEAA@AEAY0BN@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[29])
0x1800bbed6  lea     rdx, [rbp+4Fh+var_98]
0x1800bbeda  mov     rcx, [rax]
0x1800bbedd  call    ??$ActivateInstance@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>>)
0x1800bbee2  mov     ebx, eax
0x1800bbee4  test    eax, eax
0x1800bbee6  jns     short loc_1800BBEF2
0x1800bbee8  mov     edx, 74Ch
0x1800bbeed  jmp     loc_1800BC004
0x1800bbef2  mov     rsi, [rbp+4Fh+var_98]
0x1800bbef6  mov     rax, [rsi]
0x1800bbef9  mov     r15, [rax+38h]
0x1800bbefd  mov     r14, [rbp+4Fh+var_A8]
0x1800bbf01  mov     rbx, cs:?s_ctacProperties@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_ctacProperties
0x1800bbf08  mov     [rbp+4Fh+length], r12d
0x1800bbf0c  mov     rcx, rdi
0x1800bbf0f  inc     rcx; unsigned __int64
0x1800bbf12  cmp     [rbx+rcx*2], r12w
0x1800bbf17  jnz     short loc_1800BBF0F
0x1800bbf19  lea     rdx, [rbp+4Fh+length]; unsigned int *
0x1800bbf1d  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bbf22  test    eax, eax
0x1800bbf24  jns     short loc_1800BBF3B
0x1800bbf26  xor     r9d, r9d; lpArguments
0x1800bbf29  xor     r8d, r8d; nNumberOfArguments
0x1800bbf2c  lea     edx, [r9+1]; dwExceptionFlags
0x1800bbf30  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bbf35  call    cs:__imp_RaiseException
0x1800bbf3b  lea     r9, [rbp+4Fh+var_80]; string
0x1800bbf3f  lea     r8, [rbp+4Fh+var_78]; hstringHeader
0x1800bbf43  mov     edx, [rbp+4Fh+length]; length
0x1800bbf46  mov     rcx, rbx; sourceString
0x1800bbf49  call    cs:__imp_WindowsCreateStringReference
0x1800bbf4f  mov     r8, r14
0x1800bbf52  mov     rdx, [rbp+4Fh+var_80]
0x1800bbf56  mov     rcx, rsi
0x1800bbf59  mov     rax, r15
0x1800bbf5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbf61  mov     ebx, eax
0x1800bbf63  test    eax, eax
0x1800bbf65  jns     short loc_1800BBF71
0x1800bbf67  mov     edx, 74Eh
0x1800bbf6c  jmp     loc_1800BC004
0x1800bbf71  mov     rsi, [rbp+4Fh+var_98]
0x1800bbf75  mov     rax, [rsi]
0x1800bbf78  mov     r15, [rax+38h]
0x1800bbf7c  mov     r14, [rbp+4Fh+var_90]
0x1800bbf80  mov     rbx, cs:?s_ctacAppId@FSPropertyBag@@0QEBGEB; ushort const * const FSPropertyBag::s_ctacAppId
0x1800bbf87  mov     [rbp+4Fh+length], r12d
0x1800bbf8b  inc     rdi
0x1800bbf8e  cmp     [rbx+rdi*2], r12w
0x1800bbf93  jnz     short loc_1800BBF8B
0x1800bbf95  lea     rdx, [rbp+4Fh+length]; unsigned int *
0x1800bbf99  mov     rcx, rdi; unsigned __int64
0x1800bbf9c  call    ?ULongLongToUInt@@YAJ_KPEAI@Z; ULongLongToUInt(unsigned __int64,uint *)
0x1800bbfa1  test    eax, eax
0x1800bbfa3  jns     short loc_1800BBFBA
0x1800bbfa5  xor     r9d, r9d; lpArguments
0x1800bbfa8  xor     r8d, r8d; nNumberOfArguments
0x1800bbfab  lea     edx, [r9+1]; dwExceptionFlags
0x1800bbfaf  mov     ecx, 0C000000Dh; dwExceptionCode
0x1800bbfb4  call    cs:__imp_RaiseException
0x1800bbfba  lea     r9, [rbp+4Fh+var_80]; string
0x1800bbfbe  lea     r8, [rbp+4Fh+var_78]; hstringHeader
0x1800bbfc2  mov     edx, [rbp+4Fh+length]; length
0x1800bbfc5  mov     rcx, rbx; sourceString
0x1800bbfc8  call    cs:__imp_WindowsCreateStringReference
0x1800bbfce  mov     r8, r14
0x1800bbfd1  mov     rdx, [rbp+4Fh+var_80]
0x1800bbfd5  mov     rcx, rsi
0x1800bbfd8  mov     rax, r15
0x1800bbfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800bbfe0  mov     ebx, eax
0x1800bbfe2  test    eax, eax
0x1800bbfe4  jns     short loc_1800BBFED
0x1800bbfe6  mov     edx, 74Fh
0x1800bbfeb  jmp     short loc_1800BC004
0x1800bbfed  mov     r8, r13
0x1800bbff0  lea     rcx, [rbp+4Fh+var_98]
0x1800bbff4  call    ?CopyTo@?$ComPtr@UIJsonObject@Json@Data@Windows@@@WRL@Microsoft@@QEBAJAEBU_GUID@@PEAPEAX@Z; Microsoft::WRL::ComPtr<Windows::Data::Json::IJsonObject>::CopyTo(_GUID const &,void * *)
0x1800bbff9  mov     ebx, eax
0x1800bbffb  test    eax, eax
0x1800bbffd  jns     short loc_1800BC018
0x1800bbfff  mov     edx, 751h; void *
0x1800bc004  mov     r9d, eax; char *
0x1800bc007  lea     r8, aOnecoreBaseFli_84; "onecore\\base\\flighting\\flightsetting"...
0x1800bc00e  mov     rcx, [rbp+57h]; this
0x1800bc012  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800bc017  nop
0x1800bc018  lea     rcx, [rbp+4Fh+var_98]
0x1800bc01c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc021  nop
0x1800bc022  lea     rcx, [rbp+4Fh+var_90]
0x1800bc026  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc02b  nop
0x1800bc02c  lea     rcx, [rbp+4Fh+var_A8]
0x1800bc030  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc035  nop
0x1800bc036  lea     rcx, [rbp+4Fh+var_A0]; this
0x1800bc03a  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x1800bc03f  nop
0x1800bc040  lea     rcx, [rbp+4Fh+var_88]
0x1800bc044  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x1800bc049  mov     eax, ebx
0x1800bc04b  mov     rcx, [rbp+4Fh+var_40]
0x1800bc04f  xor     rcx, rsp; StackCookie
0x1800bc052  call    __security_check_cookie
0x1800bc057  mov     rbx, [rsp+0E0h+arg_0]
0x1800bc05f  add     rsp, 0B0h
0x1800bc066  pop     r15
0x1800bc068  pop     r14
0x1800bc06a  pop     r13
0x1800bc06c  pop     r12
0x1800bc06e  pop     rdi
0x1800bc06f  pop     rsi
0x1800bc070  pop     rbp
0x1800bc071  retn
```
