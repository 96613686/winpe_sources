# Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::AddTokenBrokerAccount(ushort const *,uchar)

- ea: `0x18000db14`
- end: `0x18000de64`
- name: `?AddTokenBrokerAccount@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJPEBGE@Z`
- size: `848`
- prototype: `int(Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *__hidden this, const unsigned __int16 *, unsigned __int8)`
- caller_count: `1`
- callee_count: `15`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180013210`

## callees

- `0x180006eac`
- `0x180007ec0`
- `0x180007f0c`
- `0x180007f68`
- `0x180008128`
- `0x180008218`
- `0x180008df0`
- `0x180009d08`
- `0x18000aa04`
- `0x18000db14`
- `0x18000e87c`
- `0x180011c24`
- `0x180011ffc`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dd74`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18000dd74`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dd5b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18000dd5b`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000dbc3`
- `api-ms-win-core-winrt-l1-1-0!RoGetActivationFactory` at `0x18000dbc3`

## string_xrefs

- `0x18000db68`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000dbd6`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000dc27`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000dc66`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000dcad`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000dd19`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000dde3`: `onecoreuap\shell\accountscontrol\api\accountscontrollib\accountscontrolbroker.cpp`
- `0x18000db98`: `Windows.Internal.Security.Authentication.Web.TokenBrokerInternal`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::AddTokenBrokerAccount(
        Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *this,
        const unsigned __int16 *a2,
        unsigned __int8 a3)
{
  int v4; // r14d
  Windows::Internal::UI::ApplicationSettings::AccountsControlBroker *v5; // rcx
  int WebAccountProvider; // eax
  unsigned int v7; // ebx
  __int64 v8; // rbx
  int ActivationFactory; // eax
  _QWORD *v10; // rax
  int v11; // eax
  int v12; // eax
  const unsigned __int16 *v13; // rdx
  _QWORD *v14; // rax
  int v15; // eax
  __int64 v16; // rdi
  __int64 (__fastcall *v17)(__int64, _QWORD, __int64 *); // rbx
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rdx
  __int64 v21; // rbx
  __int64 (__fastcall *v22)(__int64, HSTRING, __int64, _BYTE *); // rsi
  __int64 v23; // rdi
  __int64 v24; // rax
  int v25; // eax
  int v27; // [rsp+20h] [rbp-59h]
  int v28; // [rsp+20h] [rbp-59h]
  _BYTE v29[8]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v30; // [rsp+38h] [rbp-41h] BYREF
  int v31[2]; // [rsp+40h] [rbp-39h] BYREF
  __int64 v32; // [rsp+48h] [rbp-31h] BYREF
  __int64 v33; // [rsp+50h] [rbp-29h] BYREF
  __int64 v34; // [rsp+58h] [rbp-21h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v35; // [rsp+60h] [rbp-19h] BYREF
  _QWORD v36[2]; // [rsp+68h] [rbp-11h] BYREF
  HSTRING string; // [rsp+78h] [rbp-1h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+80h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  v4 = (int)this;
  v36[1] = a2;
  v35 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  WebAccountProvider = Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(
                         v5,
                         a3,
                         &v35);
  v7 = WebAccountProvider;
  if ( WebAccountProvider >= 0 )
  {
    v30 = 0;
    *(_QWORD *)&hstringHeader.Reserved.Reserved2[16] = 0;
    Microsoft::WRL::Wrappers::HStringReference::CreateReference(
      (HSTRING_HEADER *)&string,
      L"Windows.Internal.Security.Authentication.Web.TokenBrokerInternal",
      0x41u,
      0x40u);
    v8 = *(_QWORD *)&hstringHeader.Reserved.Reserved2[16];
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    ActivationFactory = RoGetActivationFactory(v8, &GUID_b53a11bd_746a_45ee_80e6_aa5b7faa597c, &v30);
    v7 = ActivationFactory;
    if ( ActivationFactory < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41A,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)ActivationFactory,
        v27);
LABEL_5:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
      goto LABEL_26;
    }
    *(_QWORD *)v31 = 0;
    v10 = (_QWORD *)Windows::Internal::StringReference::StringReference(
                      &string,
                      L"Windows.Foundation.Collections.PropertySet");
    v11 = Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(
            *v10,
            v31);
    v7 = v11;
    if ( v11 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x41F,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v11,
        v27);
LABEL_8:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
      goto LABEL_5;
    }
    v32 = 0;
    v12 = Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(
            v31,
            &v32);
    v7 = v12;
    if ( v12 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x421,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v12,
        v27);
LABEL_11:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
      goto LABEL_8;
    }
    v34 = 0;
    v14 = (_QWORD *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[33])v13);
    v15 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(
            *v14,
            &v34);
    v7 = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x424,
        (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
        (const char *)(unsigned int)v15,
        v27);
LABEL_14:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
      goto LABEL_11;
    }
    v33 = 0;
    v29[0] = 0;
    v16 = v34;
    v17 = *(__int64 (__fastcall **)(__int64, _QWORD, __int64 *))(*(_QWORD *)v34 + 144LL);
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    v18 = Microsoft::WRL::Wrappers::HStringReference::HStringReference((HSTRING_HEADER *)&string);
    v19 = v17(v16, *(_QWORD *)(v18 + 24), &v33);
    v7 = v19;
    if ( v19 >= 0 )
    {
      v21 = v32;
      v22 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _BYTE *))(*(_QWORD *)v32 + 80LL);
      v23 = v33;
      if ( WindowsCreateStringReference(L"LoginHint", 9u, &hstringHeader, &string) < 0 )
        RaiseException(0xC000000D, 1u, 0, 0);
      v19 = v22(v21, string, v23, v29);
      v7 = v19;
      if ( v19 >= 0 )
      {
        v36[0] = 0;
        v24 = _lambda_ea3c615d7b6ac0412bf00512c875ea32_::_lambda_ea3c615d7b6ac0412bf00512c875ea32_(
                (unsigned int)&string,
                (unsigned int)&v30,
                v4,
                (unsigned int)&v35,
                (__int64)v31,
                (__int64)v36);
        v25 = RunInBrokerContext__lambda_21b8ee25ca54235441c20e3f1a7b2cce_(v24);
        v7 = v25;
        if ( v25 >= 0 )
        {
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v36);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v34);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v32);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v31);
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
          v7 = 0;
          goto LABEL_26;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x436,
          (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
          (const char *)(unsigned int)v25,
          v28);
        Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(v36);
        goto LABEL_18;
      }
      v20 = 1065;
    }
    else
    {
      v20 = 1064;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
      (const char *)(unsigned int)v19,
      v27);
LABEL_18:
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
    goto LABEL_14;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x415,
    (unsigned int)"onecoreuap\\shell\\accountscontrol\\api\\accountscontrollib\\accountscontrolbroker.cpp",
    (const char *)(unsigned int)WebAccountProvider,
    v27);
LABEL_26:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  return v7;
}

```

## disassembly

```asm
0x18000db14  push    rbp
0x18000db16  push    rbx
0x18000db17  push    rsi
0x18000db18  push    rdi
0x18000db19  push    r14
0x18000db1b  lea     rbp, [rsp-37h]
0x18000db20  sub     rsp, 0B0h
0x18000db27  mov     rax, cs:__security_cookie
0x18000db2e  xor     rax, rsp
0x18000db31  mov     [rbp+57h+var_30], rax
0x18000db35  mov     bl, r8b
0x18000db38  mov     r14, rcx
0x18000db3b  mov     [rbp+57h+var_60], rdx
0x18000db3f  mov     [rbp+57h+var_70], 0
0x18000db47  lea     rcx, [rbp+57h+var_70]
0x18000db4b  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000db50  lea     r8, [rbp+57h+var_70]; struct Windows::Security::Credentials::IWebAccountProvider **
0x18000db54  mov     dl, bl; unsigned __int8
0x18000db56  call    ?GetWebAccountProvider@AccountsControlBroker@ApplicationSettings@UI@Internal@Windows@@AEAAJEPEAPEAUIWebAccountProvider@Credentials@Security@5@@Z; Windows::Internal::UI::ApplicationSettings::AccountsControlBroker::GetWebAccountProvider(uchar,Windows::Security::Credentials::IWebAccountProvider * *)
0x18000db5b  mov     ebx, eax
0x18000db5d  test    eax, eax
0x18000db5f  jns     short loc_18000DB7E
0x18000db61  mov     rcx, [rbp+5Fh]; this
0x18000db65  mov     r9d, eax; char *
0x18000db68  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000db6f  mov     edx, 415h; void *
0x18000db74  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000db79  jmp     loc_18000DE3F
0x18000db7e  mov     [rbp+57h+var_98], 0
0x18000db86  mov     qword ptr [rbp+57h+hstringHeader.Reserved+10h], 0
0x18000db8e  mov     r9d, 40h ; '@'; unsigned int
0x18000db94  lea     r8d, [r9+1]; unsigned int
0x18000db98  lea     rdx, ?RuntimeClass_Windows_Internal_Security_Authentication_Web_TokenBrokerInternal@@3QBGB; "Windows.Internal.Security.Authenticatio"...
0x18000db9f  lea     rcx, [rbp+57h+string]; hstringHeader
0x18000dba3  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x18000dba8  mov     rbx, qword ptr [rbp+57h+hstringHeader.Reserved+10h]
0x18000dbac  lea     rcx, [rbp+57h+var_98]
0x18000dbb0  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dbb5  lea     r8, [rbp+57h+var_98]
0x18000dbb9  lea     rdx, _GUID_b53a11bd_746a_45ee_80e6_aa5b7faa597c
0x18000dbc0  mov     rcx, rbx
0x18000dbc3  call    cs:__imp_RoGetActivationFactory
0x18000dbc9  mov     ebx, eax
0x18000dbcb  test    eax, eax
0x18000dbcd  jns     short loc_18000DBF6
0x18000dbcf  mov     rcx, [rbp+5Fh]; this
0x18000dbd3  mov     r9d, eax; char *
0x18000dbd6  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000dbdd  mov     edx, 41Ah; void *
0x18000dbe2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dbe7  nop
0x18000dbe8  lea     rcx, [rbp+57h+var_98]
0x18000dbec  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dbf1  jmp     loc_18000DE3F
0x18000dbf6  mov     qword ptr [rbp+57h+var_90], 0
0x18000dbfe  lea     rdx, ?RuntimeClass_Windows_Foundation_Collections_PropertySet@@3QBGB; "Windows.Foundation.Collections.Property"...
0x18000dc05  lea     rcx, [rbp+57h+string]; string
0x18000dc09  call    ??$?0$0CL@@StringReference@Internal@Windows@@QEAA@AEAY0CL@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[43])
0x18000dc0e  lea     rdx, [rbp+57h+var_90]
0x18000dc12  mov     rcx, [rax]
0x18000dc15  call    ??$ActivateInstance@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::ActivateInstance<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>>)
0x18000dc1a  mov     ebx, eax
0x18000dc1c  test    eax, eax
0x18000dc1e  jns     short loc_18000DC44
0x18000dc20  mov     rcx, [rbp+5Fh]; this
0x18000dc24  mov     r9d, eax; char *
0x18000dc27  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000dc2e  mov     edx, 41Fh; void *
0x18000dc33  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc38  nop
0x18000dc39  lea     rcx, [rbp+57h+var_90]
0x18000dc3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dc42  jmp     short loc_18000DBE8
0x18000dc44  mov     [rbp+57h+var_88], 0
0x18000dc4c  lea     rdx, [rbp+57h+var_88]
0x18000dc50  lea     rcx, [rbp+57h+var_90]
0x18000dc54  call    ??$As@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@?$ComPtr@UIPropertySet@Collections@Foundation@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@U?$IMap@PEAUHSTRING__@@PEAUIInspectable@@@Collections@Foundation@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IPropertySet>::As<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IMap<HSTRING__ *,IInspectable *>>>)
0x18000dc59  mov     ebx, eax
0x18000dc5b  test    eax, eax
0x18000dc5d  jns     short loc_18000DC83
0x18000dc5f  mov     rcx, [rbp+5Fh]; this
0x18000dc63  mov     r9d, eax; char *
0x18000dc66  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000dc6d  mov     edx, 421h; void *
0x18000dc72  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dc77  nop
0x18000dc78  lea     rcx, [rbp+57h+var_88]
0x18000dc7c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dc81  jmp     short loc_18000DC39
0x18000dc83  mov     [rbp+57h+var_78], 0
0x18000dc8b  lea     rcx, [rbp+57h+string]; string
0x18000dc8f  call    ??$?0$0CB@@StringReference@Internal@Windows@@QEAA@AEAY0CB@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[33])
0x18000dc94  lea     rdx, [rbp+57h+var_78]
0x18000dc98  mov     rcx, [rax]
0x18000dc9b  call    ??$GetActivationFactory@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UIPropertyValueStatics@Foundation@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Foundation::IPropertyValueStatics>>)
0x18000dca0  mov     ebx, eax
0x18000dca2  test    eax, eax
0x18000dca4  jns     short loc_18000DCCA
0x18000dca6  mov     rcx, [rbp+5Fh]; this
0x18000dcaa  mov     r9d, eax; char *
0x18000dcad  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000dcb4  mov     edx, 424h; void *
0x18000dcb9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dcbe  nop
0x18000dcbf  lea     rcx, [rbp+57h+var_78]
0x18000dcc3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dcc8  jmp     short loc_18000DC78
0x18000dcca  mov     [rbp+57h+var_80], 0
0x18000dcd2  mov     [rbp+57h+var_A0], 0
0x18000dcd6  mov     rdi, [rbp+57h+var_78]
0x18000dcda  mov     rax, [rdi]
0x18000dcdd  mov     rbx, [rax+90h]
0x18000dce4  lea     rcx, [rbp+57h+var_80]
0x18000dce8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dced  lea     rdx, [rbp+57h+var_60]
0x18000dcf1  lea     rcx, [rbp+57h+string]; hstringHeader
0x18000dcf5  call    ??$?0V?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBV?$NativeString@V?$LocalMemPolicy@G@Internal@Windows@@@Internal@Windows@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(Windows::Internal::NativeString<Windows::Internal::LocalMemPolicy<ushort>> const &,Microsoft::WRL::Details::Dummy)
0x18000dcfa  nop
0x18000dcfb  lea     r8, [rbp+57h+var_80]
0x18000dcff  mov     rdx, [rax+18h]
0x18000dd03  mov     rcx, rdi
0x18000dd06  mov     rax, rbx
0x18000dd09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd0e  mov     ebx, eax
0x18000dd10  test    eax, eax
0x18000dd12  jns     short loc_18000DD38
0x18000dd14  mov     edx, 428h; void *
0x18000dd19  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000dd20  mov     r9d, eax; char *
0x18000dd23  mov     rcx, [rbp+5Fh]; this
0x18000dd27  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000dd2c  nop
0x18000dd2d  lea     rcx, [rbp+57h+var_80]
0x18000dd31  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000dd36  jmp     short loc_18000DCBF
0x18000dd38  mov     rbx, [rbp+57h+var_88]
0x18000dd3c  mov     rax, [rbx]
0x18000dd3f  mov     rsi, [rax+50h]
0x18000dd43  mov     rdi, [rbp+57h+var_80]
0x18000dd47  lea     r9, [rbp+57h+string]; string
0x18000dd4b  lea     r8, [rbp+57h+hstringHeader]; hstringHeader
0x18000dd4f  mov     edx, 9; length
0x18000dd54  lea     rcx, sourceString; "LoginHint"
0x18000dd5b  call    cs:__imp_WindowsCreateStringReference
0x18000dd61  test    eax, eax
0x18000dd63  jns     short loc_18000DD7A
0x18000dd65  xor     r9d, r9d; lpArguments
0x18000dd68  xor     r8d, r8d; nNumberOfArguments
0x18000dd6b  lea     edx, [r9+1]; dwExceptionFlags
0x18000dd6f  mov     ecx, 0C000000Dh; dwExceptionCode
0x18000dd74  call    cs:__imp_RaiseException
0x18000dd7a  lea     r9, [rbp+57h+var_A0]
0x18000dd7e  mov     r8, rdi
0x18000dd81  mov     rdx, [rbp+57h+string]
0x18000dd85  mov     rcx, rbx
0x18000dd88  mov     rax, rsi
0x18000dd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dd90  mov     ebx, eax
0x18000dd92  test    eax, eax
0x18000dd94  jns     short loc_18000DDA0
0x18000dd96  mov     edx, 429h
0x18000dd9b  jmp     loc_18000DD19
0x18000dda0  mov     [rbp+57h+var_68], 0
0x18000dda8  lea     rax, [rbp+57h+var_68]
0x18000ddac  mov     [rsp+0D0h+var_A8], rax
0x18000ddb1  lea     rax, [rbp+57h+var_90]
0x18000ddb5  mov     qword ptr [rsp+0D0h+var_B0], rax; int
0x18000ddba  lea     r9, [rbp+57h+var_70]
0x18000ddbe  mov     r8, r14
0x18000ddc1  lea     rdx, [rbp+57h+var_98]
0x18000ddc5  lea     rcx, [rbp+57h+string]
0x18000ddc9  call    ??0_lambda_ea3c615d7b6ac0412bf00512c875ea32_@@QEAA@PEAV?$SimpleVectorIterator@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@V?$Vector@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@U?$DefaultEqualityPredicate@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@6789@U?$VectorOptions@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@$0A@$00$0A@@6789@@Internal@Collections@Foundation@Windows@@U?$DefaultLifetimeTraits@W4AccountSyncContentType@Sync@Experiences@PhoneInternal@@@6789@UIntVersionTag@XWinRT@@$00@Internal@Collections@Foundation@Windows@@AEAIAEAPEAW4AccountSyncContentType@Sync@Experiences@PhoneInternal@@AEAPEAIAEAV_lambda_393af4cc79259440c365c842be03dec3_@@@Z; _lambda_ea3c615d7b6ac0412bf00512c875ea32_::_lambda_ea3c615d7b6ac0412bf00512c875ea32_(Windows::Foundation::Collections::Internal::SimpleVectorIterator<PhoneInternal::Experiences::Sync::AccountSyncContentType,Windows::Foundation::Collections::Internal::Vector<PhoneInternal::Experiences::Sync::AccountSyncContentType,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::AccountSyncContentType>,Windows::Foundation::Collections::Internal::VectorOptions<PhoneInternal::Experiences::Sync::AccountSyncContentType,0,1,0>>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<PhoneInternal::Experiences::Sync::AccountSyncContentType>,XWinRT::IntVersionTag,1> *,uint &,PhoneInternal::Experiences::Sync::AccountSyncContentType * &,uint * &,_lambda_393af4cc79259440c365c842be03dec3_ &)
0x18000ddce  mov     rcx, rax
0x18000ddd1  call    RunInBrokerContext__lambda_21b8ee25ca54235441c20e3f1a7b2cce___; RunInBrokerContext__lambda_21b8ee25ca54235441c20e3f1a7b2cce_
0x18000ddd6  mov     ebx, eax
0x18000ddd8  test    eax, eax
0x18000ddda  jns     short loc_18000DE02
0x18000dddc  mov     rcx, [rbp+5Fh]; this
0x18000dde0  mov     r9d, eax; char *
0x18000dde3  lea     r8, aOnecoreuapShel_27; "onecoreuap\\shell\\accountscontrol\\api"...
0x18000ddea  mov     edx, 436h; void *
0x18000ddef  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ddf4  lea     rcx, [rbp+57h+var_68]
0x18000ddf8  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000ddfd  jmp     loc_18000DD2D
0x18000de02  lea     rcx, [rbp+57h+var_68]
0x18000de06  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000de0b  nop
0x18000de0c  lea     rcx, [rbp+57h+var_80]
0x18000de10  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000de15  nop
0x18000de16  lea     rcx, [rbp+57h+var_78]
0x18000de1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000de1f  nop
0x18000de20  lea     rcx, [rbp+57h+var_88]
0x18000de24  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000de29  nop
0x18000de2a  lea     rcx, [rbp+57h+var_90]
0x18000de2e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000de33  nop
0x18000de34  lea     rcx, [rbp+57h+var_98]
0x18000de38  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000de3d  xor     ebx, ebx
0x18000de3f  lea     rcx, [rbp+57h+var_70]
0x18000de43  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18000de48  mov     eax, ebx
0x18000de4a  mov     rcx, [rbp+57h+var_30]
0x18000de4e  xor     rcx, rsp; StackCookie
0x18000de51  call    __security_check_cookie
0x18000de56  add     rsp, 0B0h
0x18000de5d  pop     r14
0x18000de5f  pop     rdi
0x18000de60  pop     rsi
0x18000de61  pop     rbx
0x18000de62  pop     rbp
0x18000de63  retn
```
