# Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RuntimeClassInitialize(HSTRING__ *)

- ea: `0x18001f014`
- end: `0x18001f41d`
- name: `?RuntimeClassInitialize@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@QEAAJPEAUHSTRING__@@@Z`
- size: `1033`
- prototype: `__int64 __fastcall(Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *__hidden this, HSTRING)`
- caller_count: `1`
- callee_count: `13`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800129dc`

## callees

- `0x180003c80`
- `0x18000c6c8`
- `0x180011df8`
- `0x18001238c`
- `0x1800142f8`
- `0x180014790`
- `0x180016a38`
- `0x18001b5ac`
- `0x18001def8`
- `0x18001eb24`
- `0x18001f014`
- `0x18001f9fc`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f0c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f18b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f0c4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x18001f18b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f0bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f183`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f0bc`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001f183`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f12f`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f1f6`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f12f`
- `api-ms-win-core-com-l1-1-1!RoGetAgileReference` at `0x18001f1f6`

## string_xrefs

- `0x18001f356`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f36b`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f380`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f394`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f3a8`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f3bc`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f3d0`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f3e4`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f3f9`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`
- `0x18001f40a`: `onecore\base\devices\cam\winrt\lib\appcapabilityaccess.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RuntimeClassInitialize(
        Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer *this,
        HSTRING a2)
{
  int v4; // eax
  const unsigned __int16 *v5; // rdx
  __int64 *v6; // rax
  int v7; // eax
  __int64 v8; // rsi
  __int64 (__fastcall *v9)(__int64, HSTRING, _QWORD, _QWORD); // rdi
  DWORD CurrentThreadId; // ebx
  DWORD CurrentProcessId; // eax
  int v12; // eax
  HSTRING *v13; // rax
  HSTRING *v14; // rbx
  __int64 *v15; // rdi
  __int64 v16; // rsi
  __int64 (__fastcall *v17)(__int64, HSTRING, _QWORD, _QWORD); // rdi
  DWORD v18; // ebx
  DWORD v19; // eax
  int v20; // eax
  _QWORD *v21; // rax
  _QWORD *v22; // rbx
  __int64 v23; // rdi
  int v24; // eax
  __int64 v25; // rdx
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  unsigned int IUserFromSidString; // eax
  const char *v30; // r9
  const char *v31; // r9
  __int64 result; // rax
  int v33; // [rsp+20h] [rbp-88h]
  int v34[2]; // [rsp+30h] [rbp-78h] BYREF
  HSTRING v35; // [rsp+38h] [rbp-70h] BYREF
  int v36[2]; // [rsp+40h] [rbp-68h] BYREF
  char *v37; // [rsp+48h] [rbp-60h] BYREF
  HSTRING v38; // [rsp+50h] [rbp-58h] BYREF
  __int64 v39; // [rsp+58h] [rbp-50h] BYREF
  HSTRING string; // [rsp+60h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+0h]

  v35 = a2;
  v4 = Microsoft::WRL::Wrappers::HString::Set((HSTRING *)this + 16, &v35);
  try
  {
    if ( v4 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xB9,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v4,
        v33);
    v39 = 0;
    v6 = (__int64 *)Windows::Internal::StringReference::StringReference(&string, (const unsigned __int16 (*)[51])v5);
    v7 = Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(
           *v6,
           (__int64)&v39);
    if ( v7 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v7,
        v33);
    *(_QWORD *)v34 = 0;
    *(_QWORD *)v36 = 0;
    v8 = v39;
    v9 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, _QWORD))(*(_QWORD *)v39 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
    CurrentThreadId = GetCurrentThreadId();
    CurrentProcessId = GetCurrentProcessId();
    v12 = v9(v8, a2, CurrentProcessId, CurrentThreadId);
    if ( v12 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC1,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v12,
        (int)v34);
    v35 = (HSTRING)((char *)this + 80);
    v13 = (HSTRING *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v35);
    v14 = v13;
    v15 = *(__int64 **)v34;
    if ( *(_QWORD *)v34 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v13);
      LODWORD(v15) = RoGetAgileReference(0, &GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e, v15, v14);
    }
    else
    {
      v37 = 0;
      v35 = *v13;
      *v13 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
    }
    if ( (int)v15 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC2,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v15,
        (int)v34);
    v16 = v39;
    v17 = *(__int64 (__fastcall **)(__int64, HSTRING, _QWORD, _QWORD))(*(_QWORD *)v39 + 64LL);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v36);
    v18 = GetCurrentThreadId();
    v19 = GetCurrentProcessId();
    v20 = v17(v16, a2, v19, v18);
    if ( v20 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC4,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v20,
        (int)v36);
    v37 = (char *)this + 88;
    v21 = (_QWORD *)Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(&v37);
    v22 = v21;
    v23 = *(_QWORD *)v36;
    if ( *(_QWORD *)v36 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v21);
      LODWORD(v23) = RoGetAgileReference(0, &GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e, v23, v22);
    }
    else
    {
      v35 = 0;
      v37 = (char *)*v21;
      *v21 = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v37);
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v35);
    }
    if ( (int)v23 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC5,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v23,
        (int)v36);
    v24 = (*(__int64 (__fastcall **)(_QWORD, _QWORD))(**(_QWORD **)v34 + 88LL))(*(_QWORD *)v34, 0);
    if ( v24 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC7,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v24,
        (int)v36);
    LOBYTE(v25) = 1;
    v26 = (*(__int64 (__fastcall **)(_QWORD, __int64))(**(_QWORD **)v36 + 88LL))(*(_QWORD *)v36, v25);
    if ( v26 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xC8,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v26,
        (int)v36);
    Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::EnsureAuditBehaviorIsDisabled(this);
    v38 = 0;
    v27 = **(_QWORD **)v34;
    v38 = 0;
    v28 = (*(__int64 (__fastcall **)(_QWORD, HSTRING *))(v27 + 112))(*(_QWORD *)v34, &v38);
    if ( v28 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xCE,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        (const char *)(unsigned int)v28,
        (int)v36);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease((char *)this + 72);
    IUserFromSidString = Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::GetIUserFromSidString(
                           v38,
                           (struct Windows::System::IUser **)this + 9);
    v30 = 0;
    if ( IUserFromSidString != -2147023584 )
      v30 = (const char *)IUserFromSidString;
    if ( (int)v30 < 0 )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0xD7,
        (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
        v30,
        (int)v36);
    Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RegisterWnf(this);
    Windows::Internal::String::~String((Windows::Internal::String *)&v38);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v36);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v34);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xDF,
                           (unsigned int)"onecore\\base\\devices\\cam\\winrt\\lib\\appcapabilityaccess.cpp",
                           v31);
  }
  return result;
}

```

## disassembly

```asm
0x18001f014  mov     r11, rsp
0x18001f017  mov     [r11+18h], rbx
0x18001f01b  mov     [r11+20h], rsi
0x18001f01f  push    rdi
0x18001f020  push    r14
0x18001f022  push    r15
0x18001f024  sub     rsp, 90h
0x18001f02b  mov     rax, cs:__security_cookie
0x18001f032  xor     rax, rsp
0x18001f035  mov     [rsp+0A8h+var_28], rax
0x18001f03d  mov     r15, rdx
0x18001f040  mov     r14, rcx
0x18001f043  mov     [r11-70h], rdx
0x18001f047  sub     rcx, 0FFFFFFFFFFFFFF80h; newString
0x18001f04b  lea     rdx, [r11-70h]; HSTRING *
0x18001f04f  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18001f054  mov     rcx, [rsp+0A8h]; this
0x18001f05c  test    eax, eax
0x18001f05e  js      loc_18001F353
0x18001f064  mov     [rsp+0A8h+var_50], 0
0x18001f06d  lea     rcx, [rsp+0A8h+string]; string
0x18001f072  call    ??$?0$0DD@@StringReference@Internal@Windows@@QEAA@AEAY0DD@$$CBG@Z; Windows::Internal::StringReference::StringReference(ushort const (&)[51])
0x18001f077  lea     rdx, [rsp+0A8h+var_50]
0x18001f07c  mov     rcx, [rax]
0x18001f07f  call    ??$GetActivationFactory@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Foundation@Windows@@YAJPEAUHSTRING__@@V?$ComPtrRef@V?$ComPtr@UICapabilityAccessStatics@CapabilityAccess@Internal@Windows@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; Windows::Foundation::GetActivationFactory<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>(HSTRING__ *,Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<Windows::Internal::CapabilityAccess::ICapabilityAccessStatics>>)
0x18001f084  mov     rcx, [rsp+0A8h]; this
0x18001f08c  test    eax, eax
0x18001f08e  js      loc_18001F368
0x18001f094  mov     qword ptr [rsp+0A8h+var_78], 0
0x18001f09d  mov     qword ptr [rsp+0A8h+var_68], 0
0x18001f0a6  mov     rsi, [rsp+0A8h+var_50]
0x18001f0ab  mov     rax, [rsi]
0x18001f0ae  mov     rdi, [rax+40h]
0x18001f0b2  lea     rcx, [rsp+0A8h+var_78]
0x18001f0b7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f0bc  call    cs:__imp_GetCurrentThreadId
0x18001f0c2  mov     ebx, eax
0x18001f0c4  call    cs:__imp_GetCurrentProcessId
0x18001f0ca  lea     rcx, [rsp+0A8h+var_78]
0x18001f0cf  mov     qword ptr [rsp+0A8h+var_88], rcx; int
0x18001f0d4  mov     r9d, ebx
0x18001f0d7  mov     r8d, eax
0x18001f0da  mov     rdx, r15
0x18001f0dd  mov     rcx, rsi
0x18001f0e0  mov     rax, rdi
0x18001f0e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f0e8  mov     rcx, [rsp+0A8h]; this
0x18001f0f0  test    eax, eax
0x18001f0f2  js      loc_18001F37D
0x18001f0f8  lea     rax, [r14+50h]
0x18001f0fc  mov     [rsp+0A8h+var_70], rax
0x18001f101  lea     rcx, [rsp+0A8h+var_70]
0x18001f106  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001f10b  mov     rbx, rax
0x18001f10e  mov     rdi, qword ptr [rsp+0A8h+var_78]
0x18001f113  test    rdi, rdi
0x18001f116  jz      short loc_18001F139
0x18001f118  mov     rcx, rax
0x18001f11b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f120  mov     r9, rbx
0x18001f123  mov     r8, rdi
0x18001f126  lea     rdx, _GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e
0x18001f12d  xor     ecx, ecx
0x18001f12f  call    cs:__imp_RoGetAgileReference
0x18001f135  mov     edi, eax
0x18001f137  jmp     short loc_18001F15D
0x18001f139  mov     [rsp+0A8h+var_60], rdi
0x18001f13e  mov     rax, [rax]
0x18001f141  mov     [rsp+0A8h+var_70], rax
0x18001f146  mov     [rbx], rdi
0x18001f149  lea     rcx, [rsp+0A8h+var_70]
0x18001f14e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f153  lea     rcx, [rsp+0A8h+var_60]
0x18001f158  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f15d  mov     rcx, [rsp+0A8h]; this
0x18001f165  test    edi, edi
0x18001f167  js      loc_18001F391
0x18001f16d  mov     rsi, [rsp+0A8h+var_50]
0x18001f172  mov     rax, [rsi]
0x18001f175  mov     rdi, [rax+40h]
0x18001f179  lea     rcx, [rsp+0A8h+var_68]
0x18001f17e  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f183  call    cs:__imp_GetCurrentThreadId
0x18001f189  mov     ebx, eax
0x18001f18b  call    cs:__imp_GetCurrentProcessId
0x18001f191  lea     rcx, [rsp+0A8h+var_68]
0x18001f196  mov     qword ptr [rsp+0A8h+var_88], rcx; int
0x18001f19b  mov     r9d, ebx
0x18001f19e  mov     r8d, eax
0x18001f1a1  mov     rdx, r15
0x18001f1a4  mov     rcx, rsi
0x18001f1a7  mov     rax, rdi
0x18001f1aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f1af  mov     rcx, [rsp+0A8h]; this
0x18001f1b7  test    eax, eax
0x18001f1b9  js      loc_18001F3A5
0x18001f1bf  lea     rax, [r14+58h]
0x18001f1c3  mov     [rsp+0A8h+var_60], rax
0x18001f1c8  lea     rcx, [rsp+0A8h+var_60]
0x18001f1cd  call    ??B?$ComPtrRef@VAgileRef@WRL@Microsoft@@@Details@WRL@Microsoft@@QEAAPEAVAgileRef@23@XZ; Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::AgileRef>::operator Microsoft::WRL::AgileRef *(void)
0x18001f1d2  mov     rbx, rax
0x18001f1d5  mov     rdi, qword ptr [rsp+0A8h+var_68]
0x18001f1da  test    rdi, rdi
0x18001f1dd  jz      short loc_18001F200
0x18001f1df  mov     rcx, rax
0x18001f1e2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f1e7  mov     r9, rbx
0x18001f1ea  mov     r8, rdi
0x18001f1ed  lea     rdx, _GUID_0f8e44dd_ee48_4b95_a524_f4ceb214ab7e
0x18001f1f4  xor     ecx, ecx
0x18001f1f6  call    cs:__imp_RoGetAgileReference
0x18001f1fc  mov     edi, eax
0x18001f1fe  jmp     short loc_18001F224
0x18001f200  mov     [rsp+0A8h+var_70], rdi
0x18001f205  mov     rax, [rax]
0x18001f208  mov     [rsp+0A8h+var_60], rax
0x18001f20d  mov     [rbx], rdi
0x18001f210  lea     rcx, [rsp+0A8h+var_60]
0x18001f215  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f21a  lea     rcx, [rsp+0A8h+var_70]
0x18001f21f  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f224  mov     rcx, [rsp+0A8h]; this
0x18001f22c  test    edi, edi
0x18001f22e  js      loc_18001F3B9
0x18001f234  mov     rcx, qword ptr [rsp+0A8h+var_78]
0x18001f239  mov     rax, [rcx]
0x18001f23c  xor     edx, edx
0x18001f23e  mov     rax, [rax+58h]
0x18001f242  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f247  mov     rcx, [rsp+0A8h]; this
0x18001f24f  test    eax, eax
0x18001f251  js      loc_18001F3CD
0x18001f257  mov     rcx, qword ptr [rsp+0A8h+var_68]
0x18001f25c  mov     rax, [rcx]
0x18001f25f  mov     dl, 1
0x18001f261  mov     rax, [rax+58h]
0x18001f265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f26a  mov     rcx, [rsp+0A8h]; this
0x18001f272  test    eax, eax
0x18001f274  js      loc_18001F3E1
0x18001f27a  mov     rcx, r14; this
0x18001f27d  call    ?EnsureAuditBehaviorIsDisabled@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAXXZ; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::EnsureAuditBehaviorIsDisabled(void)
0x18001f282  mov     [rsp+0A8h+var_58], 0
0x18001f28b  mov     rcx, qword ptr [rsp+0A8h+var_78]
0x18001f290  mov     rax, [rcx]
0x18001f293  mov     [rsp+0A8h+var_58], 0
0x18001f29c  lea     rdx, [rsp+0A8h+var_58]
0x18001f2a1  mov     rax, [rax+70h]
0x18001f2a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2aa  mov     rcx, [rsp+0A8h]; this
0x18001f2b2  test    eax, eax
0x18001f2b4  js      loc_18001F3F6
0x18001f2ba  lea     rcx, [r14+48h]
0x18001f2be  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f2c3  lea     rdx, [r14+48h]; struct Windows::System::IUser **
0x18001f2c7  mov     rcx, [rsp+0A8h+var_58]; string
0x18001f2cc  call    ?GetIUserFromSidString@AppCapabilityAccessFactory@AppCapabilityAccess@Authorization@Security@Windows@@SAJPEAUHSTRING__@@PEAPEAUIUser@System@5@@Z; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessFactory::GetIUserFromSidString(HSTRING__ *,Windows::System::IUser * *)
0x18001f2d1  xor     r9d, r9d
0x18001f2d4  cmp     eax, 80070520h
0x18001f2d9  cmovnz  r9d, eax; char *
0x18001f2dd  mov     rcx, [rsp+0A8h]; this
0x18001f2e5  test    r9d, r9d
0x18001f2e8  js      loc_18001F40A
0x18001f2ee  mov     rcx, r14; this
0x18001f2f1  call    ?RegisterWnf@AppCapabilityAccessServer@AppCapabilityAccess@Authorization@Security@Windows@@AEAAJXZ; Windows::Security::Authorization::AppCapabilityAccess::AppCapabilityAccessServer::RegisterWnf(void)
0x18001f2f6  nop
0x18001f2f7  lea     rcx, [rsp+0A8h+var_58]; this
0x18001f2fc  call    ??1String@Internal@Windows@@QEAA@XZ; Windows::Internal::String::~String(void)
0x18001f301  nop
0x18001f302  lea     rcx, [rsp+0A8h+var_68]
0x18001f307  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f30c  nop
0x18001f30d  lea     rcx, [rsp+0A8h+var_78]
0x18001f312  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f317  nop
0x18001f318  lea     rcx, [rsp+0A8h+var_50]
0x18001f31d  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f322  xor     eax, eax
0x18001f324  jmp     short loc_18001F32A
0x18001f326  mov     eax, [rsp+0A8h+var_78]
0x18001f32a  mov     rcx, [rsp+0A8h+var_28]
0x18001f332  xor     rcx, rsp; StackCookie
0x18001f335  call    __security_check_cookie
0x18001f33a  lea     r11, [rsp+0A8h+var_18]
0x18001f342  mov     rbx, [r11+30h]
0x18001f346  mov     rsi, [r11+38h]
0x18001f34a  mov     rsp, r11
0x18001f34d  pop     r15
0x18001f34f  pop     r14
0x18001f351  pop     rdi
0x18001f352  retn
0x18001f353  mov     r9d, eax; char *
0x18001f356  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f35d  mov     edx, 0B9h; void *
0x18001f362  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f368  mov     r9d, eax; char *
0x18001f36b  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f372  mov     edx, 0BCh; void *
0x18001f377  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f37d  mov     r9d, eax; char *
0x18001f380  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f387  mov     edx, 0C1h; void *
0x18001f38c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f391  mov     r9d, edi; char *
0x18001f394  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f39b  mov     edx, 0C2h; void *
0x18001f3a0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f3a5  mov     r9d, eax; char *
0x18001f3a8  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f3af  mov     edx, 0C4h; void *
0x18001f3b4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f3b9  mov     r9d, edi; char *
0x18001f3bc  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f3c3  mov     edx, 0C5h; void *
0x18001f3c8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f3cd  mov     r9d, eax; char *
0x18001f3d0  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f3d7  mov     edx, 0C7h; void *
0x18001f3dc  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f3e1  mov     r9d, eax; char *
0x18001f3e4  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f3eb  mov     edx, 0C8h; void *
0x18001f3f0  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f3f6  mov     r9d, eax; char *
0x18001f3f9  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f400  mov     edx, 0CEh; void *
0x18001f405  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001f40a  lea     r8, aOnecoreBaseDev_10; "onecore\\base\\devices\\cam\\winrt\\lib"...
0x18001f411  mov     edx, 0D7h; void *
0x18001f416  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
