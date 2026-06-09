# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::RequestAccessMultipleInternal(Windows::Foundation::Collections::IIterable<HSTRING__ *> *,Windows::System::IUser *,ulong,ulong,Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> * *)

- ea: `0x18001a224`
- end: `0x18001a603`
- name: `?RequestAccessMultipleInternal@AppCapabilityAccessFactory@AppCapabilityAccess@Authorization@Security@Windows@@AEAAJPEAU?$IIterable@PEAUHSTRING__@@@Collections@Foundation@5@PEAUIUser@System@5@KKPEAPEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@785@@Z`
- size: `991`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800147d8`
- `0x180014880`

## callees

- `0x180003c80`
- `0x18000c6c8`
- `0x18000f9e4`
- `0x180011df8`
- `0x18001238c`
- `0x180013b8c`
- `0x1800142f8`
- `0x180014754`
- `0x180017700`
- `0x180017ff0`
- `0x1800181dc`
- `0x180018610`
- `0x18001a224`
- `0x18001b218`
- `0x18001b444`
- `0x18001b5ac`
- `0x18001de08`
- `0x180022cec`
- `0x180039010`

## string_xrefs

- `0x18001a26e`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a2b5`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a32c`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a37e`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a3b9`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a414`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a497`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a4d0`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a515`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a565`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`
- `0x18001a592`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccessfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=6 #try_helpers=1
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::RequestAccessMultipleInternal(
        __int64 a1,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned int a4,
        int a5,
        _QWORD *a6)
{
  __int64 *v9; // rax
  int v10; // eax
  __int64 UserSidStringFromIUser; // rax
  __int64 v12; // rdx
  __int64 v13; // rcx
  int v14; // eax
  __int64 (__fastcall *v15)(const unsigned __int16 *, __int64 **); // rbx
  int v16; // eax
  int v17; // eax
  __int64 v18; // rax
  int v19; // eax
  __int64 v20; // rsi
  __int64 (__fastcall *v21)(__int64, HSTRING, __int64, _QWORD); // rdi
  __int64 v22; // rbx
  __int64 v23; // rdx
  __int64 v24; // r8
  __int64 v25; // r9
  const unsigned __int16 *v26; // rax
  int v27; // eax
  int v28; // eax
  unsigned int v29; // eax
  int v30; // eax
  int v31; // eax
  int View; // eax
  int v34; // [rsp+20h] [rbp-C8h]
  char v35; // [rsp+40h] [rbp-A8h] BYREF
  _BYTE v36[3]; // [rsp+41h] [rbp-A7h] BYREF
  unsigned int v37; // [rsp+44h] [rbp-A4h] BYREF
  __int64 *v38; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v39; // [rsp+50h] [rbp-98h] BYREF
  __int64 v40; // [rsp+58h] [rbp-90h] BYREF
  __int64 v41; // [rsp+60h] [rbp-88h] BYREF
  __int64 v42; // [rsp+68h] [rbp-80h] BYREF
  HSTRING string[4]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v44[32]; // [rsp+90h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  if ( !a6 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x81,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)0x80004003LL,
      v34);
  *a6 = 0;
  v42 = 0;
  v9 = (__int64 *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[51])a2);
  v10 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
          *v9,
          (__int64)&v42);
  if ( v10 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v10,
      v34);
  std::wstring::wstring(v44);
  if ( a3 )
  {
    UserSidStringFromIUser = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromIUser(string, a3);
    std::wstring::operator=(v44, UserSidStringFromIUser);
    std::wstring::_Tidy_deallocate(string);
  }
  v40 = 0;
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,0>>::InternalRelease(&v40);
  v14 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(
          v13,
          v12,
          &v40);
  if ( v14 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x91,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v14,
      v34);
  v37 = 0;
  v38 = 0;
  v15 = *(__int64 (__fastcall **)(const unsigned __int16 *, __int64 **))(*(_QWORD *)a2 + 48LL);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  v16 = v15(a2, &v38);
  if ( v16 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v16,
      v34);
  v35 = 0;
  v17 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v38 + 56))(v38, &v35);
  if ( v17 < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)v17,
      v34);
  while ( v35 )
  {
    v39 = 0;
    v18 = *v38;
    v39 = 0;
    v19 = (*(__int64 (__fastcall **)(__int64 *, __int64 *))(v18 + 48))(v38, &v39);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9D,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)(unsigned int)v19,
        v34);
    v41 = 0;
    v20 = v42;
    v21 = *(__int64 (__fastcall **)(__int64, HSTRING, __int64, _QWORD))(*(_QWORD *)v42 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    v22 = v39;
    v26 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v44, v23, v24, v25);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v26);
    v34 = a5;
    v27 = v21(v20, string[0], v22, a4);
    if ( v27 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA7,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)(unsigned int)v27,
        a5);
    v28 = (*(__int64 (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v41 + 152LL))(v41, &v37);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xA9,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)(unsigned int)v28,
        a5);
    v36[0] = 0;
    v29 = Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::CapabilityAccessStatusToAppCapabilityAccessStatus(v37);
    v30 = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(
            v40,
            v39,
            v29,
            v36);
    if ( v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB3,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)(unsigned int)v30,
        a5);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v41);
    Windows::Internal::String::~String((Windows::Internal::String *)&v39);
    v31 = (*(__int64 (__fastcall **)(__int64 *, char *))(*v38 + 64))(v38, &v35);
    if ( v31 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x9A,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
        (const char *)(unsigned int)v31,
        a5);
  }
  View = Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(
           v40,
           a6);
  if ( View < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0xB6,
      (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccessfactory.cpp",
      (const char *)(unsigned int)View,
      v34);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
  Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<enum Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,0>>::InternalRelease(&v40);
  std::wstring::_Tidy_deallocate(v44);
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v42);
  return 0;
}

```

## disassembly

```asm
0x18001a224  mov     [rsp+arg_0], rbx
0x18001a229  push    rsi
0x18001a22a  push    rdi
0x18001a22b  push    r12
0x18001a22d  push    r14
0x18001a22f  push    r15
0x18001a231  sub     rsp, 0C0h
0x18001a238  mov     rax, cs:__security_cookie
0x18001a23f  xor     rax, rsp
0x18001a242  mov     [rsp+0E8h+var_38], rax
0x18001a24a  mov     r12d, r9d
0x18001a24d  mov     rbx, r8
0x18001a250  mov     rdi, rdx
0x18001a253  mov     r14, [rsp+0E8h+arg_28]
0x18001a25b  mov     rcx, [rsp+0E8h]; this
0x18001a263  test    r14, r14
0x18001a266  jnz     short loc_18001A27F
0x18001a268  mov     r9d, 80004003h; char *
0x18001a26e  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a275  mov     edx, 81h; void *
0x18001a27a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a27f  mov     qword ptr [r14], 0
0x18001a286  mov     [rsp+0E8h+var_80], 0
0x18001a28f  lea     rcx, [rsp+0E8h+string]; string
0x18001a294  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18001a299  lea     rdx, [rsp+0E8h+var_80]
0x18001a29e  mov     rcx, [rax]
0x18001a2a1  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x18001a2a6  mov     rcx, [rsp+0E8h]; this
0x18001a2ae  test    eax, eax
0x18001a2b0  jns     short loc_18001A2C6
0x18001a2b2  mov     r9d, eax; char *
0x18001a2b5  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a2bc  mov     edx, 87h; void *
0x18001a2c1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a2c6  lea     rcx, [rsp+0E8h+var_58]
0x18001a2ce  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::wstring(void)
0x18001a2d3  nop
0x18001a2d4  test    rbx, rbx
0x18001a2d7  jz      short loc_18001A300
0x18001a2d9  mov     rdx, rbx
0x18001a2dc  lea     rcx, [rsp+0E8h+string]
0x18001a2e1  call    ?GetUserSidStringFromIUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUser@System@4@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromIUser(Windows::System::IUser *)
0x18001a2e6  mov     rdx, rax
0x18001a2e9  lea     rcx, [rsp+0E8h+var_58]
0x18001a2f1  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001a2f6  lea     rcx, [rsp+0E8h+string]
0x18001a2fb  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a300  mov     [rsp+0E8h+var_90], 0
0x18001a309  lea     rcx, [rsp+0E8h+var_90]
0x18001a30e  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,0>>::InternalRelease(void)
0x18001a313  lea     r8, [rsp+0E8h+var_90]
0x18001a318  call    ?Make@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@SAJAEBU?$DefaultHash@PEAUHSTRING__@@@2345@AEBU?$DefaultEqualityPredicate@PEAUHSTRING__@@@2345@PEAPEAV12345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Make(Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *> const &,Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>> * *)
0x18001a31d  mov     rcx, [rsp+0E8h]; this
0x18001a325  test    eax, eax
0x18001a327  jns     short loc_18001A33D
0x18001a329  mov     r9d, eax; char *
0x18001a32c  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a333  mov     edx, 91h; void *
0x18001a338  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a33d  mov     [rsp+0E8h+var_A4], 0
0x18001a345  mov     [rsp+0E8h+var_A0], 0
0x18001a34e  mov     rax, [rdi]
0x18001a351  mov     rbx, [rax+30h]
0x18001a355  lea     rcx, [rsp+0E8h+var_A0]
0x18001a35a  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a35f  lea     rdx, [rsp+0E8h+var_A0]
0x18001a364  mov     rcx, rdi
0x18001a367  mov     rax, rbx
0x18001a36a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a36f  mov     rcx, [rsp+0E8h]; this
0x18001a377  test    eax, eax
0x18001a379  jns     short loc_18001A38F
0x18001a37b  mov     r9d, eax; char *
0x18001a37e  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a385  mov     edx, 97h; void *
0x18001a38a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a38f  mov     [rsp+0E8h+var_A8], 0
0x18001a394  mov     rcx, [rsp+0E8h+var_A0]
0x18001a399  mov     rax, [rcx]
0x18001a39c  lea     rdx, [rsp+0E8h+var_A8]
0x18001a3a1  mov     rax, [rax+38h]
0x18001a3a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a3aa  mov     rcx, [rsp+0E8h]; this
0x18001a3b2  test    eax, eax
0x18001a3b4  jns     short loc_18001A3CA
0x18001a3b6  mov     r9d, eax; char *
0x18001a3b9  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a3c0  mov     edx, 9Ah; void *
0x18001a3c5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a3ca  mov     r15d, [rsp+0E8h+arg_20]
0x18001a3d2  cmp     [rsp+0E8h+var_A8], 0
0x18001a3d7  jz      loc_18001A576
0x18001a3dd  mov     [rsp+0E8h+var_98], 0
0x18001a3e6  mov     rcx, [rsp+0E8h+var_A0]
0x18001a3eb  mov     rax, [rcx]
0x18001a3ee  mov     [rsp+0E8h+var_98], 0
0x18001a3f7  lea     rdx, [rsp+0E8h+var_98]
0x18001a3fc  mov     rax, [rax+30h]
0x18001a400  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a405  mov     rcx, [rsp+0E8h]; this
0x18001a40d  test    eax, eax
0x18001a40f  jns     short loc_18001A425
0x18001a411  mov     r9d, eax; char *
0x18001a414  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a41b  mov     edx, 9Dh; void *
0x18001a420  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a425  mov     [rsp+0E8h+var_88], 0
0x18001a42e  mov     rsi, [rsp+0E8h+var_80]
0x18001a433  mov     rax, [rsi]
0x18001a436  mov     rdi, [rax+38h]
0x18001a43a  lea     rcx, [rsp+0E8h+var_88]
0x18001a43f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a444  mov     rbx, [rsp+0E8h+var_98]
0x18001a449  lea     rcx, [rsp+0E8h+var_58]
0x18001a451  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001a456  mov     rdx, rax; unsigned __int16 *
0x18001a459  lea     rcx, [rsp+0E8h+string]; this
0x18001a45e  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001a463  lea     rax, [rsp+0E8h+var_88]
0x18001a468  mov     [rsp+0E8h+var_C0], rax
0x18001a46d  mov     [rsp+0E8h+var_C8], r15d; int
0x18001a472  mov     r9d, r12d
0x18001a475  mov     r8, rbx
0x18001a478  mov     rdx, [rsp+0E8h+string]
0x18001a47d  mov     rcx, rsi
0x18001a480  mov     rax, rdi
0x18001a483  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a488  mov     rcx, [rsp+0E8h]; this
0x18001a490  test    eax, eax
0x18001a492  jns     short loc_18001A4A8
0x18001a494  mov     r9d, eax; char *
0x18001a497  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a49e  mov     edx, 0A7h; void *
0x18001a4a3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a4a8  mov     rcx, [rsp+0E8h+var_88]
0x18001a4ad  mov     rax, [rcx]
0x18001a4b0  lea     rdx, [rsp+0E8h+var_A4]
0x18001a4b5  mov     rax, [rax+98h]
0x18001a4bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a4c1  mov     rcx, [rsp+0E8h]; this
0x18001a4c9  test    eax, eax
0x18001a4cb  jns     short loc_18001A4E1
0x18001a4cd  mov     r9d, eax; char *
0x18001a4d0  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a4d7  mov     edx, 0A9h; void *
0x18001a4dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a4e1  mov     [rsp+0E8h+var_A7], 0
0x18001a4e6  mov     ecx, [rsp+0E8h+var_A4]
0x18001a4ea  call    ?CapabilityAccessStatusToAppCapabilityAccessStatus@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@SA?AW4AppCapabilityAccessStatus@2345@W4CapabilityAccessStatus@CapabilityAccess@Internal@5@@Z; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::CapabilityAccessStatusToAppCapabilityAccessStatus(Windows::Internal::CapabilityAccess::CapabilityAccessStatus)
0x18001a4ef  mov     r8d, eax
0x18001a4f2  lea     r9, [rsp+0E8h+var_A7]
0x18001a4f7  mov     rdx, [rsp+0E8h+var_98]
0x18001a4fc  mov     rcx, [rsp+0E8h+var_90]
0x18001a501  call    ?Insert@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@5@PEAE@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::Insert(HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,uchar *)
0x18001a506  mov     rcx, [rsp+0E8h]; this
0x18001a50e  test    eax, eax
0x18001a510  jns     short loc_18001A527
0x18001a512  mov     r9d, eax; char *
0x18001a515  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a51c  mov     edx, 0B3h; void *
0x18001a521  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a527  lea     rcx, [rsp+0E8h+var_88]
0x18001a52c  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a531  nop
0x18001a532  lea     rcx, [rsp+0E8h+var_98]; this
0x18001a537  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001a53c  mov     rcx, [rsp+0E8h+var_A0]
0x18001a541  mov     rax, [rcx]
0x18001a544  lea     rdx, [rsp+0E8h+var_A8]
0x18001a549  mov     rax, [rax+40h]
0x18001a54d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a552  mov     rcx, [rsp+0E8h]; this
0x18001a55a  test    eax, eax
0x18001a55c  jns     loc_18001A3D2
0x18001a562  mov     r9d, eax; char *
0x18001a565  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a56c  mov     edx, 9Ah; void *
0x18001a571  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a576  mov     rdx, r14
0x18001a579  mov     rcx, [rsp+0E8h+var_90]
0x18001a57e  call    ?GetView@?$HashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@U?$HashMapOptions@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@Internal@Collections@Foundation@6@$0A@$00$0A@@89Foundation@6@@Internal@Collections@Foundation@Windows@@UEAAJPEAPEAU?$IMapView@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@345@@Z; Windows::Foundation::Collections::Internal::HashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,Windows::Foundation::Collections::Internal::HashMapOptions<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,0,1,0>>::GetView(Windows::Foundation::Collections::IMapView<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus> * *)
0x18001a583  mov     rcx, [rsp+0E8h]; this
0x18001a58b  test    eax, eax
0x18001a58d  jns     short loc_18001A5A4
0x18001a58f  mov     r9d, eax; char *
0x18001a592  lea     r8, aOnecoreBaseDev; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001a599  mov     edx, 0B6h; void *
0x18001a59e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001a5a4  lea     rcx, [rsp+0E8h+var_A0]
0x18001a5a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a5ae  nop
0x18001a5af  lea     rcx, [rsp+0E8h+var_90]
0x18001a5b4  call    ?InternalRelease@?$ComPtr@V?$AgileHashMap@PEAUHSTRING__@@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@U?$DefaultHash@PEAUHSTRING__@@@Internal@Collections@Foundation@6@U?$DefaultEqualityPredicate@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@PEAUHSTRING__@@@89Foundation@6@U?$DefaultLifetimeTraits@W4AppCapabilityAccessStatus@AppCapabilityAccess@Authorization@Security@Windows@@@89Foundation@6@$0A@@Internal@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::Internal::AgileHashMap<HSTRING__ *,Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus,Windows::Foundation::Collections::Internal::DefaultHash<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultEqualityPredicate<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<HSTRING__ *>,Windows::Foundation::Collections::Internal::DefaultLifetimeTraits<Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessStatus>,0>>::InternalRelease(void)
0x18001a5b9  nop
0x18001a5ba  lea     rcx, [rsp+0E8h+var_58]
0x18001a5c2  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a5c7  nop
0x18001a5c8  lea     rcx, [rsp+0E8h+var_80]
0x18001a5cd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001a5d2  xor     eax, eax
0x18001a5d4  jmp     short loc_18001A5DA
0x18001a5d6  mov     eax, [rsp+0E8h+var_A4]
0x18001a5da  mov     rcx, [rsp+0E8h+var_38]
0x18001a5e2  xor     rcx, rsp; StackCookie
0x18001a5e5  call    __security_check_cookie
0x18001a5ea  mov     rbx, [rsp+0E8h+arg_0]
0x18001a5f2  add     rsp, 0C0h
0x18001a5f9  pop     r15
0x18001a5fb  pop     r14
0x18001a5fd  pop     r12
0x18001a5ff  pop     rdi
0x18001a600  pop     rsi
0x18001a601  retn
```
