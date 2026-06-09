# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RuntimeClassInitialize(HSTRING__ *,Windows::System::IUser *,ulong)

- ea: `0x18001f424`
- end: `0x18001f921`
- name: `?RuntimeClassInitialize@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@QEAAJPEAUHSTRING__@@PEAUIUser@System@5@K@Z`
- size: `1277`
- prototype: `__int64 __fastcall(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this, HSTRING, struct Windows::System::IUser *, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x180012ac4`

## callees

- `0x180003c80`
- `0x18000c6c8`
- `0x18000f9e4`
- `0x180011df8`
- `0x18001238c`
- `0x1800142f8`
- `0x180014754`
- `0x180014790`
- `0x180016a38`
- `0x18001b218`
- `0x18001b444`
- `0x18001b5ac`
- `0x18001def8`
- `0x18001eb24`
- `0x18001f424`
- `0x18001f9fc`
- `0x180022cec`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f5a9`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f689`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f5a9`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f689`

## string_xrefs

- `0x18001f82f`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f844`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f859`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f86d`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f881`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f895`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f8a9`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f8bd`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f8d1`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f8e5`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f8fa`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f90e`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RuntimeClassInitialize(
        Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *this,
        HSTRING a2,
        struct Windows::System::IUser *a3,
        unsigned int a4)
{
  int v8; // eax
  const unsigned __int16 *v9; // rdx
  __int64 *v10; // rax
  int v11; // eax
  __int64 UserSidStringFromIUser; // rax
  __int64 v13; // rdi
  __int64 (__fastcall *v14)(__int64, HSTRING, HSTRING, _QWORD); // rbx
  __int64 v15; // rdx
  __int64 v16; // r8
  __int64 v17; // r9
  const unsigned __int16 *v18; // rax
  int v19; // eax
  HSTRING *v20; // rax
  HSTRING *v21; // rbx
  __int64 *v22; // rdi
  __int64 v23; // rdi
  __int64 (__fastcall *v24)(__int64, HSTRING, HSTRING, _QWORD); // rbx
  __int64 v25; // rdx
  __int64 v26; // r8
  __int64 v27; // r9
  const unsigned __int16 *v28; // rax
  int v29; // eax
  _QWORD *v30; // rax
  _QWORD *v31; // rbx
  __int64 v32; // rdi
  int v33; // eax
  __int64 v34; // rdx
  int v35; // eax
  __int64 v36; // rdx
  int v37; // eax
  __int64 v38; // rdx
  int v39; // eax
  __int64 v40; // rax
  int v41; // eax
  int IUserFromSidString; // eax
  const char *v43; // r9
  __int64 result; // rax
  int v45; // [rsp+20h] [rbp-C8h]
  HSTRING v46; // [rsp+40h] [rbp-A8h] BYREF
  __int64 *v47; // [rsp+48h] [rbp-A0h] BYREF
  __int64 v48; // [rsp+50h] [rbp-98h] BYREF
  char *v49; // [rsp+58h] [rbp-90h] BYREF
  __int64 v50; // [rsp+60h] [rbp-88h] BYREF
  _OWORD v51[2]; // [rsp+68h] [rbp-80h] BYREF
  HSTRING string[4]; // [rsp+88h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v46 = a2;
  v8 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 16, &v46);
  try
  {
    if ( v8 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE3,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v8,
        v45);
    v50 = 0;
    v10 = (__int64 *)Windows::Internal::StringReference::StringReference(string, (const unsigned __int16 (*)[51])v9);
    v11 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
            *v10,
            (__int64)&v50);
    if ( v11 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xE6,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v11,
        v45);
    v51[0] = 0;
    v51[1] = _mm_load_si128((const __m128i *)&_xmm);
    LOWORD(v51[0]) = 0;
    if ( a3 )
    {
      UserSidStringFromIUser = Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromIUser(string, a3);
      std::wstring::operator=(v51, UserSidStringFromIUser);
      std::wstring::_Tidy_deallocate(string);
    }
    v47 = 0;
    v48 = 0;
    v13 = v50;
    v14 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _QWORD))(*(_QWORD *)v50 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    v18 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51, v15, v16, v17);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v18);
    v19 = v14(v13, string[0], a2, a4);
    if ( v19 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF3,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v19,
        0);
    v46 = (HSTRING)((char *)this + 80);
    v20 = (HSTRING *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v46);
    v21 = v20;
    v22 = v47;
    if ( v47 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v20);
      LODWORD(v22) = RoGetAgileReference(0, &GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e, v22, v21);
    }
    else
    {
      v49 = 0;
      v46 = *v20;
      *v20 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
    }
    if ( (int)v22 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF4,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v22,
        0);
    v23 = v50;
    v24 = *(__int64 (__fastcall **)(__int64, HSTRING, HSTRING, _QWORD))(*(_QWORD *)v50 + 56LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    v28 = (const unsigned __int16 *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v51, v25, v26, v27);
    Windows::Internal::StringReference::_ConstructorHelper((Windows::Internal::StringReference *)string, v28);
    v29 = v24(v23, string[0], a2, a4);
    if ( v29 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF6,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v29,
        0);
    v49 = (char *)this + 88;
    v30 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v49);
    v31 = v30;
    v32 = v48;
    if ( v48 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v30);
      LODWORD(v32) = RoGetAgileReference(0, &GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e, v32, v31);
    }
    else
    {
      v46 = 0;
      v49 = (char *)*v30;
      *v30 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v49);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v46);
    }
    if ( (int)v32 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF7,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v32,
        0);
    v33 = (*(__int64 (__fastcall **)(__int64 *, _QWORD))(*v47 + 88))(v47, 0);
    if ( v33 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v33,
        0);
    LOBYTE(v34) = 1;
    v35 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 88LL))(v48, v34);
    if ( v35 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFA,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v35,
        0);
    LOBYTE(v36) = 1;
    v37 = (*(__int64 (__fastcall **)(__int64 *, __int64))(*v47 + 192))(v47, v36);
    if ( v37 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFE,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v37,
        0);
    LOBYTE(v38) = 1;
    v39 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v48 + 192LL))(v48, v38);
    if ( v39 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xFF,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v39,
        0);
    Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::EnsureAuditBehaviorIsDisabled(this);
    if ( a3 )
    {
      v46 = 0;
      v40 = *v47;
      v46 = 0;
      v41 = (*(__int64 (__fastcall **)(__int64 *, HSTRING *))(v40 + 112))(v47, &v46);
      if ( v41 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10B,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
          (const char *)(unsigned int)v41,
          0);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 72);
      IUserFromSidString = Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::GetIUserFromSidString(
                             v46,
                             (struct Windows::System::IUser **)this + 9);
      if ( IUserFromSidString < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x10C,
          (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
          (const char *)(unsigned int)IUserFromSidString,
          0);
      Windows::Internal::String::~String((Windows::Internal::String *)&v46);
    }
    Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RegisterWnf(this);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v48);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v47);
    std::wstring::_Tidy_deallocate(v51);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v50);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x115,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
                           v43);
  }
  return result;
}

```

## disassembly

```asm
0x18001f424  push    rbx
0x18001f426  push    rsi
0x18001f427  push    rdi
0x18001f428  push    r12
0x18001f42a  push    r14
0x18001f42c  push    r15
0x18001f42e  sub     rsp, 0B8h
0x18001f435  mov     rax, cs:__security_cookie
0x18001f43c  xor     rax, rsp
0x18001f43f  mov     [rsp+0E8h+var_40], rax
0x18001f447  mov     r12d, r9d
0x18001f44a  mov     r14, r8
0x18001f44d  mov     r15, rdx
0x18001f450  mov     rsi, rcx
0x18001f453  mov     [rsp+0E8h+var_A8], rdx
0x18001f458  sub     rcx, 0FFFFFFFFFFFFFF80h; newString
0x18001f45c  lea     rdx, [rsp+0E8h+var_A8]; HSTRING *
0x18001f461  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18001f466  mov     rcx, [rsp+0E8h]; this
0x18001f46e  test    eax, eax
0x18001f470  js      loc_18001F82C
0x18001f476  mov     [rsp+0E8h+var_88], 0
0x18001f47f  lea     rcx, [rsp+0E8h+string]; string
0x18001f487  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18001f48c  lea     rdx, [rsp+0E8h+var_88]
0x18001f491  mov     rcx, [rax]
0x18001f494  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x18001f499  mov     rcx, [rsp+0E8h]; this
0x18001f4a1  test    eax, eax
0x18001f4a3  js      loc_18001F841
0x18001f4a9  xorps   xmm0, xmm0
0x18001f4ac  movups  [rsp+0E8h+var_80], xmm0
0x18001f4b1  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x18001f4b9  movdqu  [rsp+0E8h+var_70], xmm1
0x18001f4bf  xor     eax, eax
0x18001f4c1  mov     word ptr [rsp+0E8h+var_80], ax
0x18001f4c6  test    r14, r14
0x18001f4c9  jz      short loc_18001F4F5
0x18001f4cb  mov     rdx, r14
0x18001f4ce  lea     rcx, [rsp+0E8h+string]
0x18001f4d6  call    ?GetUserSidStringFromIUser@Private@CapabilityAccess@Internal@Windows@@YA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAUIUser@System@4@@Z; Windows::Internal::CapabilityAccess::Private::GetUserSidStringFromIUser(Windows::System::IUser *)
0x18001f4db  mov     rdx, rax
0x18001f4de  lea     rcx, [rsp+0E8h+var_80]
0x18001f4e3  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@$$QEAV01@@Z; std::wstring::operator=(std::wstring &&)
0x18001f4e8  lea     rcx, [rsp+0E8h+string]
0x18001f4f0  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f4f5  mov     [rsp+0E8h+var_A0], 0
0x18001f4fe  mov     [rsp+0E8h+var_98], 0
0x18001f507  mov     rdi, [rsp+0E8h+var_88]
0x18001f50c  mov     rax, [rdi]
0x18001f50f  mov     rbx, [rax+38h]
0x18001f513  lea     rcx, [rsp+0E8h+var_A0]
0x18001f518  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f51d  lea     rcx, [rsp+0E8h+var_80]
0x18001f522  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f527  mov     rdx, rax; unsigned __int16 *
0x18001f52a  lea     rcx, [rsp+0E8h+string]; this
0x18001f532  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f537  lea     rax, [rsp+0E8h+var_A0]
0x18001f53c  mov     [rsp+0E8h+var_C0], rax
0x18001f541  mov     [rsp+0E8h+var_C8], 0; int
0x18001f549  mov     r9d, r12d
0x18001f54c  mov     r8, r15
0x18001f54f  mov     rdx, [rsp+0E8h+string]
0x18001f557  mov     rcx, rdi
0x18001f55a  mov     rax, rbx
0x18001f55d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f562  mov     rcx, [rsp+0E8h]; this
0x18001f56a  test    eax, eax
0x18001f56c  js      loc_18001F856
0x18001f572  lea     rax, [rsi+50h]
0x18001f576  mov     [rsp+0E8h+var_A8], rax
0x18001f57b  lea     rcx, [rsp+0E8h+var_A8]
0x18001f580  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001f585  mov     rbx, rax
0x18001f588  mov     rdi, [rsp+0E8h+var_A0]
0x18001f58d  test    rdi, rdi
0x18001f590  jz      short loc_18001F5B3
0x18001f592  mov     rcx, rax
0x18001f595  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f59a  mov     r9, rbx
0x18001f59d  mov     r8, rdi
0x18001f5a0  lea     rdx, _GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e
0x18001f5a7  xor     ecx, ecx
0x18001f5a9  call    cs:__imp_RoGetAgileReference
0x18001f5af  mov     edi, eax
0x18001f5b1  jmp     short loc_18001F5D7
0x18001f5b3  mov     [rsp+0E8h+var_90], rdi
0x18001f5b8  mov     rax, [rax]
0x18001f5bb  mov     [rsp+0E8h+var_A8], rax
0x18001f5c0  mov     [rbx], rdi
0x18001f5c3  lea     rcx, [rsp+0E8h+var_A8]
0x18001f5c8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f5cd  lea     rcx, [rsp+0E8h+var_90]
0x18001f5d2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f5d7  mov     rcx, [rsp+0E8h]; this
0x18001f5df  test    edi, edi
0x18001f5e1  js      loc_18001F86A
0x18001f5e7  mov     rdi, [rsp+0E8h+var_88]
0x18001f5ec  mov     rax, [rdi]
0x18001f5ef  mov     rbx, [rax+38h]
0x18001f5f3  lea     rcx, [rsp+0E8h+var_98]
0x18001f5f8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f5fd  lea     rcx, [rsp+0E8h+var_80]
0x18001f602  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18001f607  mov     rdx, rax; unsigned __int16 *
0x18001f60a  lea     rcx, [rsp+0E8h+string]; this
0x18001f612  call    ?_ConstructorHelper@StringReference@Internal@Windows@@AEAAXPEBG@Z; Windows::Internal::StringReference::_ConstructorHelper(ushort const *)
0x18001f617  lea     rax, [rsp+0E8h+var_98]
0x18001f61c  mov     [rsp+0E8h+var_C0], rax
0x18001f621  mov     [rsp+0E8h+var_C8], 0; int
0x18001f629  mov     r9d, r12d
0x18001f62c  mov     r8, r15
0x18001f62f  mov     rdx, [rsp+0E8h+string]
0x18001f637  mov     rcx, rdi
0x18001f63a  mov     rax, rbx
0x18001f63d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f642  mov     rcx, [rsp+0E8h]; this
0x18001f64a  test    eax, eax
0x18001f64c  js      loc_18001F87E
0x18001f652  lea     rax, [rsi+58h]
0x18001f656  mov     [rsp+0E8h+var_90], rax
0x18001f65b  lea     rcx, [rsp+0E8h+var_90]
0x18001f660  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001f665  mov     rbx, rax
0x18001f668  mov     rdi, [rsp+0E8h+var_98]
0x18001f66d  test    rdi, rdi
0x18001f670  jz      short loc_18001F693
0x18001f672  mov     rcx, rax
0x18001f675  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f67a  mov     r9, rbx
0x18001f67d  mov     r8, rdi
0x18001f680  lea     rdx, _GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e
0x18001f687  xor     ecx, ecx
0x18001f689  call    cs:__imp_RoGetAgileReference
0x18001f68f  mov     edi, eax
0x18001f691  jmp     short loc_18001F6B7
0x18001f693  mov     [rsp+0E8h+var_A8], rdi
0x18001f698  mov     rax, [rax]
0x18001f69b  mov     [rsp+0E8h+var_90], rax
0x18001f6a0  mov     [rbx], rdi
0x18001f6a3  lea     rcx, [rsp+0E8h+var_90]
0x18001f6a8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f6ad  lea     rcx, [rsp+0E8h+var_A8]
0x18001f6b2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f6b7  mov     rcx, [rsp+0E8h]; this
0x18001f6bf  test    edi, edi
0x18001f6c1  js      loc_18001F892
0x18001f6c7  mov     rcx, [rsp+0E8h+var_A0]
0x18001f6cc  mov     rax, [rcx]
0x18001f6cf  xor     edx, edx
0x18001f6d1  mov     rax, [rax+58h]
0x18001f6d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6da  mov     rcx, [rsp+0E8h]; this
0x18001f6e2  test    eax, eax
0x18001f6e4  js      loc_18001F8A6
0x18001f6ea  mov     rcx, [rsp+0E8h+var_98]
0x18001f6ef  mov     rax, [rcx]
0x18001f6f2  mov     dl, 1
0x18001f6f4  mov     rax, [rax+58h]
0x18001f6f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f6fd  mov     rcx, [rsp+0E8h]; this
0x18001f705  test    eax, eax
0x18001f707  js      loc_18001F8BA
0x18001f70d  mov     rcx, [rsp+0E8h+var_A0]
0x18001f712  mov     rax, [rcx]
0x18001f715  mov     dl, 1
0x18001f717  mov     rax, [rax+0C0h]
0x18001f71e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f723  mov     rcx, [rsp+0E8h]; this
0x18001f72b  test    eax, eax
0x18001f72d  js      loc_18001F8CE
0x18001f733  mov     rcx, [rsp+0E8h+var_98]
0x18001f738  mov     rax, [rcx]
0x18001f73b  mov     dl, 1
0x18001f73d  mov     rax, [rax+0C0h]
0x18001f744  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f749  mov     rcx, [rsp+0E8h]; this
0x18001f751  test    eax, eax
0x18001f753  js      loc_18001F8E2
0x18001f759  mov     rcx, rsi; this
0x18001f75c  call    ?EnsureAuditBehaviorIsDisabled@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAXXZ; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::EnsureAuditBehaviorIsDisabled(void)
0x18001f761  test    r14, r14
0x18001f764  jz      short loc_18001F7CF
0x18001f766  mov     [rsp+0E8h+var_A8], 0
0x18001f76f  mov     rcx, [rsp+0E8h+var_A0]
0x18001f774  mov     rax, [rcx]
0x18001f777  mov     [rsp+0E8h+var_A8], 0
0x18001f780  lea     rdx, [rsp+0E8h+var_A8]
0x18001f785  mov     rax, [rax+70h]
0x18001f789  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f78e  mov     rcx, [rsp+0E8h]; this
0x18001f796  test    eax, eax
0x18001f798  js      loc_18001F8F7
0x18001f79e  lea     rcx, [rsi+48h]
0x18001f7a2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f7a7  lea     rdx, [rsi+48h]; struct Windows::System::IUser **
0x18001f7ab  mov     rcx, [rsp+0E8h+var_A8]; string
0x18001f7b0  call    ?GetIUserFromSidString@AppCapabilityAccessFactory@AppCapabilityAccess@Authorization@Security@Windows@@SAJPEAUHSTRING__@@PEAPEAUIUser@System@5@@Z; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::GetIUserFromSidString(HSTRING__ *,Windows::System::IUser * *)
0x18001f7b5  mov     rcx, [rsp+0E8h]; this
0x18001f7bd  test    eax, eax
0x18001f7bf  js      loc_18001F90B
0x18001f7c5  lea     rcx, [rsp+0E8h+var_A8]; this
0x18001f7ca  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001f7cf  mov     rcx, rsi; this
0x18001f7d2  call    ?RegisterWnf@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAJXZ; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RegisterWnf(void)
0x18001f7d7  nop
0x18001f7d8  lea     rcx, [rsp+0E8h+var_98]
0x18001f7dd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f7e2  nop
0x18001f7e3  lea     rcx, [rsp+0E8h+var_A0]
0x18001f7e8  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f7ed  nop
0x18001f7ee  lea     rcx, [rsp+0E8h+var_80]
0x18001f7f3  call    ?_Tidy_deallocate@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001f7f8  nop
0x18001f7f9  lea     rcx, [rsp+0E8h+var_88]
0x18001f7fe  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f803  xor     eax, eax
0x18001f805  jmp     short loc_18001F80B
0x18001f807  mov     eax, dword ptr [rsp+0E8h+var_A0]
0x18001f80b  mov     rcx, [rsp+0E8h+var_40]
0x18001f813  xor     rcx, rsp; StackCookie
0x18001f816  call    __security_check_cookie
0x18001f81b  add     rsp, 0B8h
0x18001f822  pop     r15
0x18001f824  pop     r14
0x18001f826  pop     r12
0x18001f828  pop     rdi
0x18001f829  pop     rsi
0x18001f82a  pop     rbx
0x18001f82b  retn
0x18001f82c  mov     r9d, eax; char *
0x18001f82f  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f836  mov     edx, 0E3h; void *
0x18001f83b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f841  mov     r9d, eax; char *
0x18001f844  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f84b  mov     edx, 0E6h; void *
0x18001f850  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f856  mov     r9d, eax; char *
0x18001f859  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f860  mov     edx, 0F3h; void *
0x18001f865  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f86a  mov     r9d, edi; char *
0x18001f86d  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f874  mov     edx, 0F4h; void *
0x18001f879  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f87e  mov     r9d, eax; char *
0x18001f881  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f888  mov     edx, 0F6h; void *
0x18001f88d  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f892  mov     r9d, edi; char *
0x18001f895  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f89c  mov     edx, 0F7h; void *
0x18001f8a1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f8a6  mov     r9d, eax; char *
0x18001f8a9  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f8b0  mov     edx, 0F9h; void *
0x18001f8b5  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f8ba  mov     r9d, eax; char *
0x18001f8bd  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f8c4  mov     edx, 0FAh; void *
0x18001f8c9  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f8ce  mov     r9d, eax; char *
0x18001f8d1  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f8d8  mov     edx, 0FEh; void *
0x18001f8dd  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f8e2  mov     r9d, eax; char *
0x18001f8e5  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f8ec  mov     edx, 0FFh; void *
0x18001f8f1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f8f7  mov     r9d, eax; char *
0x18001f8fa  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f901  mov     edx, 10Bh; void *
0x18001f906  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f90b  mov     r9d, eax; char *
0x18001f90e  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f915  mov     edx, 10Ch; void *
0x18001f91a  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
