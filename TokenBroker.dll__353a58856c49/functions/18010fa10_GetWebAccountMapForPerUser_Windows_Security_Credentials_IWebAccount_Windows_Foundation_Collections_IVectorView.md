# GetWebAccountMapForPerUser(Windows::Security::Credentials::IWebAccount *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *,HSTRING__ *)

- ea: `0x18010fa10`
- end: `0x18010fe83`
- name: `?GetWebAccountMapForPerUser@@YAJPEAUIWebAccount@Credentials@Security@Windows@@PEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@4@PEAUHSTRING__@@@Z`
- size: `1139`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800e3120`
- `0x1800e31a0`

## callees

- `0x180007350`
- `0x18000bd40`
- `0x180024544`
- `0x180040cc0`
- `0x18004fdbc`
- `0x18005f6c0`
- `0x180063ff0`
- `0x1800d3c94`
- `0x18010fa10`
- `0x18011b010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18010fd11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCompareStringOrdinal` at `0x18010fd11`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010faae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010faf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fbb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fc48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fcde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fd4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fdba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fdd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fe21`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010faae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010faf1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fbb5`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fc48`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fcde`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fd4e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fdba`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fdd3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18010fe21`

## string_xrefs

- `0x18010fa8d`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010fad0`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010fb45`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010fbe6`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010fd93`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010fe04`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010fe55`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`
- `0x18010fe6f`: `onecore\ds\security\tokenbroker\datastore\lib\account.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
__int64 __fastcall GetWebAccountMapForPerUser(
        __int64 (__fastcall ***a1)(_QWORD, GUID *, __int64 *),
        _QWORD *a2,
        HSTRING a3)
{
  __int64 (__fastcall *v6)(_QWORD, GUID *, __int64 *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  int PluginPFN; // eax
  __int64 v10; // rdx
  HSTRING v11; // rbx
  HRESULT AllProviderAccountsFromDataStore; // edi
  __int64 v13; // rdx
  __int64 v14; // rcx
  int v15; // eax
  __int64 (__fastcall *v16)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v17; // rdx
  __int64 v18; // rsi
  __int64 (__fastcall *v19)(__int64, HSTRING *); // rdi
  unsigned int v20; // r14d
  __int64 v21; // rsi
  __int64 (__fastcall *v22)(__int64, _QWORD, _QWORD); // rdi
  int v23; // eax
  int v24; // eax
  __int64 v25; // rsi
  __int64 (__fastcall *v26)(__int64, HSTRING *); // rdi
  __int64 v28; // rdx
  HSTRING string2; // [rsp+20h] [rbp-40h] BYREF
  __int64 v30; // [rsp+28h] [rbp-38h] BYREF
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64); // [rsp+30h] [rbp-30h] BYREF
  HSTRING string1; // [rsp+38h] [rbp-28h] BYREF
  __int64 v33; // [rsp+40h] [rbp-20h] BYREF
  HSTRING string; // [rsp+48h] [rbp-18h] BYREF
  struct Windows::Security::Credentials::IWebAccountProvider *v35; // [rsp+50h] [rbp-10h] BYREF
  __int64 v36; // [rsp+58h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+38h]
  unsigned int v38; // [rsp+A0h] [rbp+40h] BYREF
  INT32 result; // [rsp+A8h] [rbp+48h] BYREF
  HSTRING v40; // [rsp+B0h] [rbp+50h] BYREF
  __int64 v41; // [rsp+B8h] [rbp+58h] BYREF

  v40 = a3;
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      word_180157F1A,
      0,
      0);
  *a2 = 0;
  v36 = 0;
  v35 = 0;
  v6 = (*a1)[6];
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  v7 = ((__int64 (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *), struct Windows::Security::Credentials::IWebAccountProvider **))v6)(
         a1,
         &v35);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xE53,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)v7,
      (int)string2);
    goto LABEL_48;
  }
  string = 0;
  if ( a3 )
  {
    PluginPFN = Windows::Internal::String::Initialize((Windows::Internal::String *)&string, &v40);
    v8 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v10 = 3675;
LABEL_8:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)PluginPFN,
        (int)string2);
      if ( string )
        WindowsDeleteString(string);
      goto LABEL_48;
    }
  }
  else
  {
    WindowsDeleteString(0);
    string = 0;
    PluginPFN = Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(v35, &string);
    v8 = PluginPFN;
    if ( PluginPFN < 0 )
    {
      v10 = 3671;
      goto LABEL_8;
    }
  }
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  v11 = string;
  AllProviderAccountsFromDataStore = GetAllProviderAccountsFromDataStore(string, v35);
  if ( AllProviderAccountsFromDataStore < 0 )
  {
    v13 = 3678;
LABEL_14:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v13,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)AllProviderAccountsFromDataStore,
      (int)string2);
LABEL_45:
    if ( v11 )
      WindowsDeleteString(v11);
    v8 = AllProviderAccountsFromDataStore;
    goto LABEL_48;
  }
  v38 = 0;
  AllProviderAccountsFromDataStore = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v36 + 56LL))(
                                       v36,
                                       &v38);
  if ( AllProviderAccountsFromDataStore < 0 )
  {
    v13 = 3680;
    goto LABEL_14;
  }
  if ( v38 )
  {
    v41 = 0;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
    v15 = Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(
            v14,
            &v41);
    AllProviderAccountsFromDataStore = v15;
    if ( v15 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xE6E,
        (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
        (const char *)(unsigned int)v15,
        (int)string2);
LABEL_44:
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v41);
      goto LABEL_45;
    }
    string2 = 0;
    v30 = 0;
    v16 = **a1;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
    AllProviderAccountsFromDataStore = v16(a1, &GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824, &v30);
    if ( AllProviderAccountsFromDataStore >= 0 )
    {
      v18 = v30;
      v19 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v30 + 48LL);
      WindowsDeleteString(string2);
      string2 = 0;
      AllProviderAccountsFromDataStore = v19(v18, &string2);
      if ( AllProviderAccountsFromDataStore >= 0 )
      {
        v20 = 0;
        if ( v38 )
        {
          while ( 1 )
          {
            v31 = 0;
            v21 = v36;
            v22 = *(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)v36 + 48LL);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            v23 = v22(v21, v20, &v31);
            AllProviderAccountsFromDataStore = v23;
            if ( v23 < 0 )
              break;
            v33 = 0;
            v24 = Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Internal::Security::Credentials::IWebAccountSystemInformation>(
                    &v31,
                    (__int64)&v33);
            AllProviderAccountsFromDataStore = v24;
            if ( v24 < 0 )
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0xE7C,
                (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
                (const char *)(unsigned int)v24,
                (int)string2);
              goto LABEL_52;
            }
            string1 = 0;
            v25 = v33;
            v26 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)v33 + 64LL);
            WindowsDeleteString(0);
            string1 = 0;
            AllProviderAccountsFromDataStore = v26(v25, &string1);
            if ( AllProviderAccountsFromDataStore < 0 )
            {
              v28 = 3711;
              goto LABEL_50;
            }
            result = 0;
            AllProviderAccountsFromDataStore = WindowsCompareStringOrdinal(string1, string2, &result);
            if ( AllProviderAccountsFromDataStore < 0 )
            {
              v28 = 3714;
              goto LABEL_50;
            }
            if ( !result )
            {
              AllProviderAccountsFromDataStore = (*(__int64 (__fastcall **)(__int64, __int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*(_QWORD *)v41 + 104LL))(
                                                   v41,
                                                   v31);
              if ( AllProviderAccountsFromDataStore < 0 )
              {
                v28 = 3718;
LABEL_50:
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)v28,
                  (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
                  (const char *)(unsigned int)AllProviderAccountsFromDataStore,
                  (int)string2);
                if ( string1 )
                  WindowsDeleteString(string1);
LABEL_52:
                Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
                goto LABEL_53;
              }
            }
            if ( string1 )
              WindowsDeleteString(string1);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v33);
            Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
            if ( ++v20 >= v38 )
              goto LABEL_39;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xE79,
            (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
            (const char *)(unsigned int)v23,
            (int)string2);
LABEL_53:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v31);
          goto LABEL_42;
        }
LABEL_39:
        AllProviderAccountsFromDataStore = (*(__int64 (__fastcall **)(__int64, _QWORD *))(*(_QWORD *)v41 + 64LL))(
                                             v41,
                                             a2);
        if ( AllProviderAccountsFromDataStore >= 0 )
        {
LABEL_42:
          Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v30);
          if ( string2 )
            WindowsDeleteString(string2);
          goto LABEL_44;
        }
        v17 = 3722;
      }
      else
      {
        v17 = 3700;
      }
    }
    else
    {
      v17 = 3699;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v17,
      (unsigned int)"onecore\\ds\\security\\tokenbroker\\datastore\\lib\\account.cpp",
      (const char *)(unsigned int)AllProviderAccountsFromDataStore,
      (int)string2);
    goto LABEL_42;
  }
  if ( (unsigned int)dword_180175000 > 4 )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      &dword_180175000,
      word_180157E32,
      0,
      0);
  if ( v11 )
    WindowsDeleteString(v11);
  v8 = 0;
LABEL_48:
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v35);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&v36);
  return v8;
}

```

## disassembly

```asm
0x18010fa10  mov     [rsp-38h+arg_10], r8
0x18010fa15  push    rbp
0x18010fa16  push    rbx
0x18010fa17  push    rsi
0x18010fa18  push    rdi
0x18010fa19  push    r12
0x18010fa1b  push    r14
0x18010fa1d  push    r15
0x18010fa1f  mov     rbp, rsp
0x18010fa22  sub     rsp, 60h
0x18010fa26  mov     rdi, r8
0x18010fa29  mov     r15, rdx
0x18010fa2c  mov     rsi, rcx
0x18010fa2f  mov     eax, cs:dword_180175000
0x18010fa35  cmp     eax, 4
0x18010fa38  jbe     short loc_18010FA53
0x18010fa3a  xor     r9d, r9d
0x18010fa3d  xor     r8d, r8d
0x18010fa40  lea     rdx, word_180157F1A
0x18010fa47  lea     rcx, dword_180175000
0x18010fa4e  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010fa53  xor     r12d, r12d
0x18010fa56  mov     [r15], r12
0x18010fa59  mov     [rbp+var_8], r12
0x18010fa5d  mov     [rbp+var_10], r12
0x18010fa61  mov     rax, [rsi]
0x18010fa64  mov     rbx, [rax+30h]
0x18010fa68  lea     rcx, [rbp+var_10]
0x18010fa6c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fa71  lea     rdx, [rbp+var_10]
0x18010fa75  mov     rcx, rsi
0x18010fa78  mov     rax, rbx
0x18010fa7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fa80  mov     ebx, eax
0x18010fa82  test    eax, eax
0x18010fa84  jns     short loc_18010FAA3
0x18010fa86  mov     rcx, [rbp+38h]; this
0x18010fa8a  mov     r9d, eax; char *
0x18010fa8d  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010fa94  mov     edx, 0E53h; void *
0x18010fa99  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fa9e  jmp     loc_18010FDDB
0x18010faa3  mov     [rbp+string], r12
0x18010faa7  test    rdi, rdi
0x18010faaa  jnz     short loc_18010FAFC
0x18010faac  xor     ecx, ecx; string
0x18010faae  call    cs:__imp_WindowsDeleteString
0x18010fab4  mov     [rbp+string], r12
0x18010fab8  lea     rdx, [rbp+string]; HSTRING *
0x18010fabc  mov     rcx, [rbp+var_10]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18010fac0  call    ?GetPluginPFN@PluginRegistration@TokenBroker@Authentication@Security@Internal@Windows@@SAJPEAUIWebAccountProvider@Credentials@46@PEAPEAUHSTRING__@@@Z; Windows::Internal::Security::Authentication::TokenBroker::PluginRegistration::GetPluginPFN(Windows::Security::Credentials::IWebAccountProvider *,HSTRING__ * *)
0x18010fac5  mov     ebx, eax
0x18010fac7  test    eax, eax
0x18010fac9  jns     short loc_18010FB16
0x18010facb  mov     edx, 0E57h; void *
0x18010fad0  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010fad7  mov     r9d, eax; char *
0x18010fada  mov     rcx, [rbp+38h]; this
0x18010fade  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fae3  nop
0x18010fae4  mov     rcx, [rbp+string]; string
0x18010fae8  test    rcx, rcx
0x18010faeb  jz      loc_18010FDDB
0x18010faf1  call    cs:__imp_WindowsDeleteString
0x18010faf7  jmp     loc_18010FDDB
0x18010fafc  lea     rdx, [rbp+arg_10]; HSTRING *
0x18010fb00  lea     rcx, [rbp+string]; this
0x18010fb04  call    ?Initialize@String@Internal@Windows@@QEAAJAEBQEAUHSTRING__@@@Z; Windows::Internal::String::Initialize(HSTRING__ * const &)
0x18010fb09  mov     ebx, eax
0x18010fb0b  test    eax, eax
0x18010fb0d  jns     short loc_18010FB16
0x18010fb0f  mov     edx, 0E5Bh
0x18010fb14  jmp     short loc_18010FAD0
0x18010fb16  lea     rcx, [rbp+var_8]
0x18010fb1a  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fb1f  lea     r9, ?AlwaysTrueFilter@@YAJPEAUIWebAccount@Credentials@Security@Windows@@AEA_N@Z; AlwaysTrueFilter(Windows::Security::Credentials::IWebAccount *,bool &)
0x18010fb26  lea     r8, [rbp+var_8]
0x18010fb2a  mov     rdx, [rbp+var_10]; struct Windows::Security::Credentials::IWebAccountProvider *
0x18010fb2e  mov     rbx, [rbp+string]
0x18010fb32  mov     rcx, rbx; HSTRING
0x18010fb35  call    ?GetAllProviderAccountsFromDataStore@@YAJPEAUHSTRING__@@PEAUIWebAccountProvider@Credentials@Security@Windows@@PEAPEAU?$IVectorView@PEAVWebAccount@Credentials@Security@Windows@@@Collections@Foundation@5@P6AJPEAUIWebAccount@345@AEA_N@Z@Z; GetAllProviderAccountsFromDataStore(HSTRING__ *,Windows::Security::Credentials::IWebAccountProvider *,Windows::Foundation::Collections::IVectorView<Windows::Security::Credentials::WebAccount *> * *,long (*)(Windows::Security::Credentials::IWebAccount *,bool &))
0x18010fb3a  mov     edi, eax
0x18010fb3c  test    eax, eax
0x18010fb3e  jns     short loc_18010FB5D
0x18010fb40  mov     edx, 0E5Eh; void *
0x18010fb45  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010fb4c  mov     r9d, edi; char *
0x18010fb4f  mov     rcx, [rbp+38h]; this
0x18010fb53  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fb58  jmp     loc_18010FDCB
0x18010fb5d  mov     [rbp+arg_0], r12d
0x18010fb61  mov     rcx, [rbp+var_8]
0x18010fb65  mov     rax, [rcx]
0x18010fb68  lea     rdx, [rbp+arg_0]
0x18010fb6c  mov     rax, [rax+38h]
0x18010fb70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fb75  mov     edi, eax
0x18010fb77  test    eax, eax
0x18010fb79  jns     short loc_18010FB82
0x18010fb7b  mov     edx, 0E60h
0x18010fb80  jmp     short loc_18010FB45
0x18010fb82  cmp     [rbp+arg_0], r12d
0x18010fb86  jnz     short loc_18010FBC3
0x18010fb88  mov     eax, cs:dword_180175000
0x18010fb8e  cmp     eax, 4
0x18010fb91  jbe     short loc_18010FBAD
0x18010fb93  xor     r9d, r9d
0x18010fb96  xor     r8d, r8d
0x18010fb99  lea     rdx, word_180157E32
0x18010fba0  lea     rcx, dword_180175000
0x18010fba7  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x18010fbac  nop
0x18010fbad  test    rbx, rbx
0x18010fbb0  jz      short loc_18010FBBB
0x18010fbb2  mov     rcx, rbx; string
0x18010fbb5  call    cs:__imp_WindowsDeleteString
0x18010fbbb  mov     ebx, r12d
0x18010fbbe  jmp     loc_18010FDDB
0x18010fbc3  mov     [rbp+arg_18], r12
0x18010fbc7  lea     rcx, [rbp+arg_18]
0x18010fbcb  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fbd0  lea     rdx, [rbp+arg_18]
0x18010fbd4  call    ??$CreateExternalObjectVector@VWebAccount@Credentials@Security@Windows@@V?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@Internal@Collections@Foundation@4@@detail@Internal@Collections@Foundation@Windows@@YAJP8IVectorStatics@Detail@234@EAAJPEBUObjectVectorInfo@6234@PEAPEAUIInspectable@@@ZPEAPEAV?$AgileVector@PEAVWebAccount@Credentials@Security@Windows@@U?$DefaultEqualityPredicate@PEAVWebAccount@Credentials@Security@Windows@@@Internal@Collections@Foundation@4@U?$DefaultLifetimeTraits@PEAVWebAccount@Credentials@Security@Windows@@@6784@$0A@@1234@@Z; Windows::Foundation::Collections::Internal::detail::CreateExternalObjectVector<Windows::Security::Credentials::WebAccount,Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0>>(long (Windows::Foundation::Collections::Detail::IVectorStatics::*)(Windows::Foundation::Collections::Detail::ObjectVectorInfo const *,IInspectable * *),Windows::Foundation::Collections::Internal::AgileVector<Windows::Security::Credentials::WebAccount *,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<Windows::Security::Credentials::WebAccount *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Credentials::WebAccount *>,0> * *)
0x18010fbd9  mov     edi, eax
0x18010fbdb  test    eax, eax
0x18010fbdd  jns     short loc_18010FBFC
0x18010fbdf  mov     rcx, [rbp+38h]; this
0x18010fbe3  mov     r9d, eax; char *
0x18010fbe6  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010fbed  mov     edx, 0E6Eh; void *
0x18010fbf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fbf7  jmp     loc_18010FDC1
0x18010fbfc  mov     [rbp+string2], r12
0x18010fc00  mov     [rbp+var_38], r12
0x18010fc04  mov     rax, [rsi]
0x18010fc07  mov     rdi, [rax]
0x18010fc0a  lea     rcx, [rbp+var_38]
0x18010fc0e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fc13  lea     r8, [rbp+var_38]
0x18010fc17  lea     rdx, _GUID_7b56d6f8_990b_4eb5_94a7_5621f3a8b824
0x18010fc1e  mov     rcx, rsi
0x18010fc21  mov     rax, rdi
0x18010fc24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fc29  mov     edi, eax
0x18010fc2b  test    eax, eax
0x18010fc2d  jns     short loc_18010FC39
0x18010fc2f  mov     edx, 0E73h
0x18010fc34  jmp     loc_18010FD93
0x18010fc39  mov     rsi, [rbp+var_38]
0x18010fc3d  mov     rax, [rsi]
0x18010fc40  mov     rdi, [rax+30h]
0x18010fc44  mov     rcx, [rbp+string2]; string
0x18010fc48  call    cs:__imp_WindowsDeleteString
0x18010fc4e  mov     [rbp+string2], r12
0x18010fc52  lea     rdx, [rbp+string2]
0x18010fc56  mov     rcx, rsi
0x18010fc59  mov     rax, rdi
0x18010fc5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fc61  mov     edi, eax
0x18010fc63  test    eax, eax
0x18010fc65  jns     short loc_18010FC71
0x18010fc67  mov     edx, 0E74h
0x18010fc6c  jmp     loc_18010FD93
0x18010fc71  mov     r14d, r12d
0x18010fc74  cmp     [rbp+arg_0], r12d
0x18010fc78  jbe     loc_18010FD75
0x18010fc7e  mov     [rbp+var_30], r12
0x18010fc82  mov     rsi, [rbp+var_8]
0x18010fc86  mov     rax, [rsi]
0x18010fc89  mov     rdi, [rax+30h]
0x18010fc8d  lea     rcx, [rbp+var_30]
0x18010fc91  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fc96  lea     r8, [rbp+var_30]
0x18010fc9a  mov     edx, r14d
0x18010fc9d  mov     rcx, rsi
0x18010fca0  mov     rax, rdi
0x18010fca3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fca8  mov     edi, eax
0x18010fcaa  test    eax, eax
0x18010fcac  js      loc_18010FE68
0x18010fcb2  mov     [rbp+var_20], r12
0x18010fcb6  lea     rdx, [rbp+var_20]
0x18010fcba  lea     rcx, [rbp+var_30]
0x18010fcbe  call    ??$As@UIWebAccountSystemInformation@Credentials@Security@Internal@Windows@@@?$ComPtr@UIWebAccount@Credentials@Security@Windows@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIWebAccountSystemInformation@Credentials@Security@Internal@Windows@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<Windows::Security::Credentials::IWebAccount>::As<Windows::Internal::Security::Credentials::IWebAccountSystemInformation>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::Security::Credentials::IWebAccountSystemInformation>>)
0x18010fcc3  mov     edi, eax
0x18010fcc5  test    eax, eax
0x18010fcc7  js      loc_18010FE4E
0x18010fccd  mov     [rbp+string1], r12
0x18010fcd1  mov     rsi, [rbp+var_20]
0x18010fcd5  mov     rax, [rsi]
0x18010fcd8  mov     rdi, [rax+40h]
0x18010fcdc  xor     ecx, ecx; string
0x18010fcde  call    cs:__imp_WindowsDeleteString
0x18010fce4  mov     [rbp+string1], r12
0x18010fce8  lea     rdx, [rbp+string1]
0x18010fcec  mov     rcx, rsi
0x18010fcef  mov     rax, rdi
0x18010fcf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fcf7  mov     edi, eax
0x18010fcf9  test    eax, eax
0x18010fcfb  js      loc_18010FE47
0x18010fd01  mov     [rbp+result], r12d
0x18010fd05  lea     r8, [rbp+result]; result
0x18010fd09  mov     rdx, [rbp+string2]; string2
0x18010fd0d  mov     rcx, [rbp+string1]; string1
0x18010fd11  call    cs:__imp_WindowsCompareStringOrdinal
0x18010fd17  mov     edi, eax
0x18010fd19  test    eax, eax
0x18010fd1b  js      loc_18010FE40
0x18010fd21  cmp     [rbp+result], r12d
0x18010fd25  jnz     short loc_18010FD45
0x18010fd27  mov     rcx, [rbp+arg_18]
0x18010fd2b  mov     rax, [rcx]
0x18010fd2e  mov     rdx, [rbp+var_30]
0x18010fd32  mov     rax, [rax+68h]
0x18010fd36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fd3b  mov     edi, eax
0x18010fd3d  test    eax, eax
0x18010fd3f  js      loc_18010FDFF
0x18010fd45  mov     rcx, [rbp+string1]; string
0x18010fd49  test    rcx, rcx
0x18010fd4c  jz      short loc_18010FD55
0x18010fd4e  call    cs:__imp_WindowsDeleteString
0x18010fd54  nop
0x18010fd55  lea     rcx, [rbp+var_20]
0x18010fd59  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fd5e  nop
0x18010fd5f  lea     rcx, [rbp+var_30]
0x18010fd63  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fd68  inc     r14d
0x18010fd6b  cmp     r14d, [rbp+arg_0]
0x18010fd6f  jb      loc_18010FC7E
0x18010fd75  mov     rcx, [rbp+arg_18]
0x18010fd79  mov     rax, [rcx]
0x18010fd7c  mov     rdx, r15
0x18010fd7f  mov     rax, [rax+40h]
0x18010fd83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18010fd88  mov     edi, eax
0x18010fd8a  test    eax, eax
0x18010fd8c  jns     short loc_18010FDA7
0x18010fd8e  mov     edx, 0E8Ah; void *
0x18010fd93  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010fd9a  mov     r9d, edi; char *
0x18010fd9d  mov     rcx, [rbp+38h]; this
0x18010fda1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fda6  nop
0x18010fda7  lea     rcx, [rbp+var_38]
0x18010fdab  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fdb0  nop
0x18010fdb1  mov     rcx, [rbp+string2]; string
0x18010fdb5  test    rcx, rcx
0x18010fdb8  jz      short loc_18010FDC1
0x18010fdba  call    cs:__imp_WindowsDeleteString
0x18010fdc0  nop
0x18010fdc1  lea     rcx, [rbp+arg_18]
0x18010fdc5  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fdca  nop
0x18010fdcb  test    rbx, rbx
0x18010fdce  jz      short loc_18010FDD9
0x18010fdd0  mov     rcx, rbx; string
0x18010fdd3  call    cs:__imp_WindowsDeleteString
0x18010fdd9  mov     ebx, edi
0x18010fddb  lea     rcx, [rbp+var_10]
0x18010fddf  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fde4  nop
0x18010fde5  lea     rcx, [rbp+var_8]
0x18010fde9  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fdee  mov     eax, ebx
0x18010fdf0  add     rsp, 60h
0x18010fdf4  pop     r15
0x18010fdf6  pop     r14
0x18010fdf8  pop     r12
0x18010fdfa  pop     rdi
0x18010fdfb  pop     rsi
0x18010fdfc  pop     rbx
0x18010fdfd  pop     rbp
0x18010fdfe  retn
0x18010fdff  mov     edx, 0E86h; void *
0x18010fe04  lea     r8, aOnecoreDsSecur_28; "onecore\\ds\\security\\tokenbroker\\dat"...
0x18010fe0b  mov     r9d, edi; char *
0x18010fe0e  mov     rcx, [rbp+38h]; this
0x18010fe12  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18010fe17  nop
0x18010fe18  mov     rcx, [rbp+string1]; string
0x18010fe1c  test    rcx, rcx
0x18010fe1f  jz      short loc_18010FE28
0x18010fe21  call    cs:__imp_WindowsDeleteString
0x18010fe27  nop
0x18010fe28  lea     rcx, [rbp+var_20]
0x18010fe2c  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fe31  nop
0x18010fe32  lea     rcx, [rbp+var_30]
0x18010fe36  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x18010fe3b  jmp     loc_18010FDA7
0x18010fe40  mov     edx, 0E82h
0x18010fe45  jmp     short loc_18010FE04
0x18010fe47  mov     edx, 0E7Fh
0x18010fe4c  jmp     short loc_18010FE04
0x18010fe4e  mov     rcx, [rbp+38h]; this
0x18010fe52  mov     r9d, edi; char *
  ... truncated ...
```
