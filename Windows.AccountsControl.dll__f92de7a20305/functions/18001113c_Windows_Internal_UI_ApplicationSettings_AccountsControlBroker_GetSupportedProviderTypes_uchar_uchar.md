# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetSupportedProviderTypes(uchar *,uchar *)

- ea: `0x18001113c`
- end: `0x18001143f`
- name: `?GetSupportedProviderTypes@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEAE0@Z`
- size: `771`
- prototype: `__int64 __fastcall(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, unsigned __int8 *, unsigned __int8 *)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x1800137b0`

## callees

- `0x180006eac`
- `0x180008e2c`
- `0x18000e87c`
- `0x18001113c`
- `0x180011c24`
- `0x180011ffc`
- `0x180069730`
- `0x18006c010`

## string_xrefs

- `0x180011198`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800111d3`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18001122a`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180011281`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800113ad`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x1800113cc`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x180011259`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetSupportedProviderTypes(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        unsigned __int8 *a2,
        unsigned __int8 *a3)
{
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v6; // rcx
  int WebAccountProvider; // eax
  unsigned int v8; // ebx
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v9; // rcx
  int v10; // eax
  __int64 v11; // rdi
  __int64 (__fastcall *v12)(__int64, __int64 *); // rbx
  int v13; // eax
  int v14; // eax
  __int64 v15; // rdx
  unsigned int i; // esi
  __int64 v17; // rdi
  __int64 (__fastcall *v18)(__int64, _QWORD, __int64 *); // rbx
  int v19; // eax
  __int64 v20; // rdi
  __int64 (__fastcall *v21)(__int64, __int64 *); // rbx
  int v22; // eax
  __int64 v23; // rdx
  int v25; // [rsp+20h] [rbp-49h]
  __int64 v26; // [rsp+30h] [rbp-39h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v27; // [rsp+38h] [rbp-31h] BYREF
  __int64 v28; // [rsp+40h] [rbp-29h] BYREF
  __int64 v29; // [rsp+48h] [rbp-21h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h] BYREF
  unsigned int v31; // [rsp+58h] [rbp-11h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v32; // [rsp+60h] [rbp-9h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+68h] [rbp-1h] BYREF
  __int64 v34; // [rsp+80h] [rbp+17h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  *a2 = 0;
  *a3 = 0;
  v32 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  WebAccountProvider = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(
                         v6,
                         0,
                         &v32);
  v8 = WebAccountProvider;
  if ( WebAccountProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x35F,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)WebAccountProvider,
      v25);
    goto LABEL_31;
  }
  v27 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v10 = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(v9, 1u, &v27);
  v8 = v10;
  if ( v10 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x361,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v10,
      v25);
LABEL_5:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
    goto LABEL_31;
  }
  v26 = 0;
  v11 = *((_QWORD *)this + 78);
  v12 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v11 + 48LL);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  v13 = v12(v11, &v26);
  v8 = v13;
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x365,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v13,
      v25);
LABEL_8:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
    goto LABEL_5;
  }
  v28 = 0;
  v34 = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(
    &hstringHeader,
    L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
    0x41u,
    0x40u);
  v14 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(
          v34,
          &v28);
  v8 = v14;
  if ( v14 < 0 )
  {
    v15 = 872;
    goto LABEL_11;
  }
  v31 = 0;
  v14 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v26 + 56LL))(v26, &v31);
  v8 = v14;
  if ( v14 < 0 )
  {
    v15 = 875;
LABEL_11:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v15,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v14,
      v25);
LABEL_12:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
    goto LABEL_8;
  }
  v30 = 0;
  for ( i = 0; i < v31; ++i )
  {
    v17 = v26;
    v18 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v26 + 48LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    v19 = v18(v17, i, &v30);
    v8 = v19;
    if ( v19 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x370,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v19,
        v25);
      goto LABEL_29;
    }
    v29 = 0;
    v20 = v30;
    v21 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)v30 + 80LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
    v22 = v21(v20, &v29);
    v8 = v22;
    if ( v22 < 0 )
    {
      v23 = 883;
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v23,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v22,
        v25);
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
LABEL_29:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      goto LABEL_12;
    }
    if ( !*a3 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Security::Credentials::IWebAccountProvider *, unsigned __int8 *))(*(_QWORD *)v28 + 344LL))(
              v28,
              v29,
              v32,
              a3);
      v8 = v22;
      if ( v22 < 0 )
      {
        v23 = 887;
        goto LABEL_27;
      }
    }
    if ( !*a2 )
    {
      v22 = (*(__int64 (__fastcall **)(__int64, __int64, struct Windows::Security::Credentials::IWebAccountProvider *, unsigned __int8 *))(*(_QWORD *)v28 + 344LL))(
              v28,
              v29,
              v27,
              a2);
      v8 = v22;
      if ( v22 < 0 )
      {
        v23 = 891;
        goto LABEL_27;
      }
    }
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v29);
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v28);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v26);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v27);
  v8 = 0;
LABEL_31:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
  return v8;
}

```

## disassembly

```asm
0x18001113c  push    rbp
0x18001113e  push    rbx
0x18001113f  push    rsi
0x180011140  push    rdi
0x180011141  push    r12
0x180011143  push    r14
0x180011145  push    r15
0x180011147  lea     rbp, [rsp-27h]
0x18001114c  sub     rsp, 90h
0x180011153  mov     rax, cs:__security_cookie
0x18001115a  xor     rax, rsp
0x18001115d  mov     [rbp+57h+var_38], rax
0x180011161  mov     r15, r8
0x180011164  mov     r14, rdx
0x180011167  mov     rdi, rcx
0x18001116a  xor     r12d, r12d
0x18001116d  mov     [rdx], r12b
0x180011170  mov     [r8], r12b
0x180011173  mov     [rbp+57h+var_60], r12
0x180011177  lea     rcx, [rbp+57h+var_60]
0x18001117b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011180  lea     r8, [rbp+57h+var_60]; struct Windows::Security::Credentials::IWebAccountProvider **
0x180011184  xor     edx, edx; unsigned __int8
0x180011186  call    ?GetWebAccountProvider@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJEPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(uchar,Windows::Security::Credentials::IWebAccountProvider * *)
0x18001118b  mov     ebx, eax
0x18001118d  test    eax, eax
0x18001118f  jns     short loc_1800111AE
0x180011191  mov     rcx, [rbp+5Fh]; this
0x180011195  mov     r9d, eax; char *
0x180011198  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18001119f  mov     edx, 35Fh; void *
0x1800111a4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111a9  jmp     loc_180011416
0x1800111ae  mov     [rbp+57h+var_88], r12
0x1800111b2  lea     rcx, [rbp+57h+var_88]
0x1800111b6  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800111bb  lea     r8, [rbp+57h+var_88]; struct Windows::Security::Credentials::IWebAccountProvider **
0x1800111bf  mov     dl, 1; unsigned __int8
0x1800111c1  call    ?GetWebAccountProvider@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJEPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(uchar,Windows::Security::Credentials::IWebAccountProvider * *)
0x1800111c6  mov     ebx, eax
0x1800111c8  test    eax, eax
0x1800111ca  jns     short loc_1800111F3
0x1800111cc  mov     rcx, [rbp+5Fh]; this
0x1800111d0  mov     r9d, eax; char *
0x1800111d3  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800111da  mov     edx, 361h; void *
0x1800111df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800111e4  nop
0x1800111e5  lea     rcx, [rbp+57h+var_88]
0x1800111e9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800111ee  jmp     loc_180011416
0x1800111f3  mov     [rbp+57h+var_90], r12
0x1800111f7  mov     rdi, [rdi+270h]
0x1800111fe  mov     rax, [rdi]
0x180011201  mov     rbx, [rax+30h]
0x180011205  lea     rcx, [rbp+57h+var_90]
0x180011209  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001120e  lea     rdx, [rbp+57h+var_90]
0x180011212  mov     rcx, rdi
0x180011215  mov     rax, rbx
0x180011218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001121d  mov     ebx, eax
0x18001121f  test    eax, eax
0x180011221  jns     short loc_180011247
0x180011223  mov     rcx, [rbp+5Fh]; this
0x180011227  mov     r9d, eax; char *
0x18001122a  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180011231  mov     edx, 365h; void *
0x180011236  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001123b  nop
0x18001123c  lea     rcx, [rbp+57h+var_90]
0x180011240  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011245  jmp     short loc_1800111E5
0x180011247  mov     [rbp+57h+var_80], r12
0x18001124b  mov     [rbp+57h+var_40], r12
0x18001124f  mov     r9d, 40h ; '@'; unsigned int
0x180011255  lea     r8d, [r9+1]; unsigned int
0x180011259  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x180011260  lea     rcx, [rbp+57h+hstringHeader]; hstringHeader
0x180011264  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180011269  lea     rdx, [rbp+57h+var_80]
0x18001126d  mov     rcx, [rbp+57h+var_40]
0x180011271  call    ??$GetActivationFactory@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UITokenBrokerInternalStatics@Web@Authentication@Security@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Authentication::Web::ITokenBrokerInternalStatics>>)
0x180011276  mov     ebx, eax
0x180011278  test    eax, eax
0x18001127a  jns     short loc_1800112A0
0x18001127c  mov     edx, 368h; void *
0x180011281  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x180011288  mov     r9d, eax; char *
0x18001128b  mov     rcx, [rbp+5Fh]; this
0x18001128f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180011294  nop
0x180011295  lea     rcx, [rbp+57h+var_80]
0x180011299  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001129e  jmp     short loc_18001123C
0x1800112a0  mov     [rbp+57h+var_68], r12d
0x1800112a4  mov     rcx, [rbp+57h+var_90]
0x1800112a8  mov     rax, [rcx]
0x1800112ab  lea     rdx, [rbp+57h+var_68]
0x1800112af  mov     rax, [rax+38h]
0x1800112b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112b8  mov     ebx, eax
0x1800112ba  test    eax, eax
0x1800112bc  jns     short loc_1800112C5
0x1800112be  mov     edx, 36Bh
0x1800112c3  jmp     short loc_180011281
0x1800112c5  mov     [rbp+57h+var_70], r12
0x1800112c9  mov     esi, r12d
0x1800112cc  cmp     esi, [rbp+57h+var_68]
0x1800112cf  jnb     loc_1800113EC
0x1800112d5  mov     rdi, [rbp+57h+var_90]
0x1800112d9  mov     rax, [rdi]
0x1800112dc  mov     rbx, [rax+30h]
0x1800112e0  lea     rcx, [rbp+57h+var_70]
0x1800112e4  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800112e9  lea     r8, [rbp+57h+var_70]
0x1800112ed  mov     edx, esi
0x1800112ef  mov     rcx, rdi
0x1800112f2  mov     rax, rbx
0x1800112f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800112fa  mov     ebx, eax
0x1800112fc  test    eax, eax
0x1800112fe  js      loc_1800113C5
0x180011304  mov     [rbp+57h+var_78], r12
0x180011308  mov     rdi, [rbp+57h+var_70]
0x18001130c  mov     rax, [rdi]
0x18001130f  mov     rbx, [rax+50h]
0x180011313  lea     rcx, [rbp+57h+var_78]
0x180011317  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001131c  lea     rdx, [rbp+57h+var_78]
0x180011320  mov     rcx, rdi
0x180011323  mov     rax, rbx
0x180011326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001132b  mov     ebx, eax
0x18001132d  test    eax, eax
0x18001132f  js      short loc_1800113A1
0x180011331  cmp     [r15], r12b
0x180011334  jnz     short loc_18001135A
0x180011336  mov     rcx, [rbp+57h+var_80]
0x18001133a  mov     rax, [rcx]
0x18001133d  mov     r9, r15
0x180011340  mov     r8, [rbp+57h+var_60]
0x180011344  mov     rdx, [rbp+57h+var_78]
0x180011348  mov     rax, [rax+158h]
0x18001134f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011354  mov     ebx, eax
0x180011356  test    eax, eax
0x180011358  js      short loc_180011393
0x18001135a  cmp     [r14], r12b
0x18001135d  jnz     short loc_180011383
0x18001135f  mov     rcx, [rbp+57h+var_80]
0x180011363  mov     rax, [rcx]
0x180011366  mov     r9, r14
0x180011369  mov     r8, [rbp+57h+var_88]
0x18001136d  mov     rdx, [rbp+57h+var_78]
0x180011371  mov     rax, [rax+158h]
0x180011378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001137d  mov     ebx, eax
0x18001137f  test    eax, eax
0x180011381  js      short loc_18001139A
0x180011383  lea     rcx, [rbp+57h+var_78]
0x180011387  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001138c  inc     esi
0x18001138e  jmp     loc_1800112CC
0x180011393  mov     edx, 377h
0x180011398  jmp     short loc_1800113A6
0x18001139a  mov     edx, 37Bh
0x18001139f  jmp     short loc_1800113A6
0x1800113a1  mov     edx, 373h; void *
0x1800113a6  mov     rcx, [rbp+5Fh]; this
0x1800113aa  mov     r9d, eax; char *
0x1800113ad  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800113b4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113b9  nop
0x1800113ba  lea     rcx, [rbp+57h+var_78]
0x1800113be  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800113c3  jmp     short loc_1800113DE
0x1800113c5  mov     rcx, [rbp+5Fh]; this
0x1800113c9  mov     r9d, eax; char *
0x1800113cc  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x1800113d3  mov     edx, 370h; void *
0x1800113d8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800113dd  nop
0x1800113de  lea     rcx, [rbp+57h+var_70]
0x1800113e2  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800113e7  jmp     loc_180011295
0x1800113ec  lea     rcx, [rbp+57h+var_70]
0x1800113f0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800113f5  nop
0x1800113f6  lea     rcx, [rbp+57h+var_80]
0x1800113fa  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x1800113ff  nop
0x180011400  lea     rcx, [rbp+57h+var_90]
0x180011404  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011409  nop
0x18001140a  lea     rcx, [rbp+57h+var_88]
0x18001140e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180011413  mov     ebx, r12d
0x180011416  lea     rcx, [rbp+57h+var_60]
0x18001141a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18001141f  mov     eax, ebx
0x180011421  mov     rcx, [rbp+57h+var_38]
0x180011425  xor     rcx, rsp; StackCookie
0x180011428  call    __security_check_cookie
0x18001142d  add     rsp, 90h
0x180011434  pop     r15
0x180011436  pop     r14
0x180011438  pop     r12
0x18001143a  pop     rdi
0x18001143b  pop     rsi
0x18001143c  pop     rbx
0x18001143d  pop     rbp
0x18001143e  retn
```
