# AppV::Client::Host::UserManagerImpl::InternalLogon(ulong)

- ea: `0x140049e30`
- end: `0x14004a576`
- name: `?InternalLogon@UserManagerImpl@Host@Client@AppV@@AEAA_KK@Z`
- size: `1862`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::UserManagerImpl *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `17`
- tags: `broker_com_uri`

## callers

- `0x14004a950`

## callees

- `0x140004280`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x1400484c4`
- `0x1400493b0`
- `0x140049e30`
- `0x14004b4dc`
- `0x140050d9c`
- `0x140052d90`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140049ecd`
- `KERNEL32!GetCurrentThreadId` at `0x14004a494`
- `KERNEL32!GetCurrentThreadId` at `0x140049ecd`
- `KERNEL32!GetCurrentThreadId` at `0x14004a494`
- `KERNEL32!LeaveCriticalSection` at `0x140049f6b`
- `KERNEL32!LeaveCriticalSection` at `0x14004a3d2`
- `KERNEL32!LeaveCriticalSection` at `0x14004a4b6`
- `KERNEL32!LeaveCriticalSection` at `0x140049f6b`
- `KERNEL32!LeaveCriticalSection` at `0x14004a3d2`
- `KERNEL32!LeaveCriticalSection` at `0x14004a4b6`
- `KERNEL32!EnterCriticalSection` at `0x140049ebe`
- `KERNEL32!EnterCriticalSection` at `0x14004a485`
- `KERNEL32!EnterCriticalSection` at `0x140049ebe`
- `KERNEL32!EnterCriticalSection` at `0x14004a485`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049ffb`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x140049ffb`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004a252`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14004a252`

## string_xrefs

- `0x14004a24b`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004a262`: `admin\appman\appv\client\host\common\usermanagerimpl.cpp`
- `0x14004a19d`: `User Manager rejecting a logon for session %1% because it is already tracking that as a logon session for a different user`
- `0x14004a03a`: `User Manager ignoring duplicate logon event for session %1% that it is already tracking for the same user`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
unsigned __int64 __fastcall AppV::Client::Host::UserManagerImpl::InternalLogon(
        struct _RTL_CRITICAL_SECTION *this,
        unsigned int a2)
{
  unsigned __int64 UserToken; // rax
  unsigned __int64 v4; // r14
  struct _RTL_CRITICAL_SECTION *v5; // rbx
  __int64 v6; // r8
  __int64 v7; // rdx
  __int64 v8; // rcx
  __int64 v9; // r14
  __int64 *v10; // rax
  __int64 v11; // rax
  __int64 v12; // r15
  volatile signed __int32 *v13; // r14
  bool v14; // zf
  unsigned __int64 v15; // r12
  __int128 *v16; // rdx
  __int128 *v17; // rcx
  __int64 v18; // rcx
  __int64 v19; // rcx
  __int64 v20; // rax
  __int64 v21; // rbx
  __int64 v22; // rbx
  void (__fastcall **v23)(__int64); // rax
  __int64 v24; // rcx
  __int64 v25; // rcx
  __int64 v26; // rcx
  __int64 v27; // rax
  __int64 v28; // rbx
  char *v29; // rax
  const char *v30; // rax
  unsigned __int64 v31; // r15
  __int64 v32; // rbx
  void (__fastcall **v33)(__int64); // rax
  __int64 v34; // rcx
  volatile signed __int32 *v35; // rbx
  _QWORD *v37; // rax
  __int64 v38; // r14
  __int64 v39; // r12
  volatile signed __int32 *v40; // r15
  volatile signed __int32 *v41; // rbx
  volatile signed __int32 *v42; // rbx
  unsigned int v43[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v44; // [rsp+30h] [rbp-D0h] BYREF
  __int128 v45; // [rsp+40h] [rbp-C0h] BYREF
  void **v46; // [rsp+50h] [rbp-B0h]
  char v47; // [rsp+58h] [rbp-A8h]
  struct _RTL_CRITICAL_SECTION *v48; // [rsp+60h] [rbp-A0h]
  __int64 v49; // [rsp+68h] [rbp-98h]
  volatile signed __int32 *v50; // [rsp+70h] [rbp-90h]
  __int128 v51; // [rsp+80h] [rbp-80h] BYREF
  __int128 v52; // [rsp+90h] [rbp-70h]
  __int128 v53; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v54; // [rsp+B0h] [rbp-50h]
  __int128 v55; // [rsp+C0h] [rbp-40h] BYREF
  __m128i v56; // [rsp+D0h] [rbp-30h]
  __int128 v57; // [rsp+E0h] [rbp-20h] BYREF
  __m128i si128; // [rsp+F0h] [rbp-10h]
  char *v59[4]; // [rsp+100h] [rbp+0h] BYREF
  int v60; // [rsp+120h] [rbp+20h]
  _QWORD v61[2]; // [rsp+128h] [rbp+28h] BYREF
  char *v62[4]; // [rsp+138h] [rbp+38h] BYREF

  v43[0] = a2;
  v44 = 0;
  UserToken = AppV::Client::Host::UserManagerImpl::GetUserToken(a2, &v44);
  v4 = UserToken;
  if ( (UserToken & 0x8000000000LL) != 0 )
  {
    v45 = 0;
    AppV::Client::Host::SessionFactory::CreateInstance(this[2].OwningThread, v43[0], &v44, &v45);
    v46 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
    v5 = this + 3;
    v48 = this + 3;
    EnterCriticalSection(this + 3);
    if ( ++LODWORD(this[4].DebugInfo) == 1 )
      HIDWORD(this[4].DebugInfo) = GetCurrentThreadId();
    v47 = 1;
    v7 = *(_QWORD *)&this[4].LockCount;
    v8 = *(_QWORD *)(v7 + 8);
    HIDWORD(v50) = 0;
    v9 = v7;
    while ( !*(_BYTE *)(v8 + 25) )
    {
      if ( *(_DWORD *)(v8 + 32) >= v43[0] )
      {
        LOBYTE(v6) = 0;
        v9 = v8;
      }
      else
      {
        LOBYTE(v6) = 1;
      }
      v10 = (__int64 *)(v8 + 16);
      if ( !(_BYTE)v6 )
        v10 = (__int64 *)v8;
      v8 = *v10;
    }
    if ( *(_BYTE *)(v9 + 25) || v43[0] < *(_DWORD *)(v9 + 32) || v7 == v9 )
    {
      v37 = (_QWORD *)std::map<unsigned long,std::shared_ptr<AppV::Client::Host::Session>>::operator[](
                        &this[4].LockCount,
                        v43,
                        v6,
                        v43[0]);
      v38 = *((_QWORD *)&v45 + 1);
      if ( *((_QWORD *)&v45 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v45 + 1) + 8LL));
      v39 = v45;
      *v37 = v45;
      v40 = (volatile signed __int32 *)v37[1];
      v37[1] = v38;
      if ( v40 )
      {
        if ( _InterlockedExchangeAdd(v40 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v40)(v40);
          if ( _InterlockedExchangeAdd(v40 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v40 + 8LL))(v40);
        }
      }
      v14 = LODWORD(this[4].DebugInfo)-- == 1;
      if ( v14 )
        HIDWORD(this[4].DebugInfo) = 0;
      LeaveCriticalSection(v5);
      v47 = 0;
      v31 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v39 + 8LL))(v39);
      if ( (v31 & 0x8000000000LL) != 0 )
      {
        if ( !v38 )
          goto LABEL_65;
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 8), 0xFFFFFFFF) != 1 )
          goto LABEL_65;
        (**(void (__fastcall ***)(__int64))v38)(v38);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 12), 0xFFFFFFFF) != 1 )
          goto LABEL_65;
        v23 = *(void (__fastcall ***)(__int64))v38;
        v24 = v38;
LABEL_64:
        v23[1](v24);
LABEL_65:
        v41 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
        if ( *((_QWORD *)&v44 + 1)
          && _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v41)(v41);
          if ( _InterlockedExchangeAdd(v41 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v41 + 8LL))(v41);
        }
        return 0x8000000000LL;
      }
      EnterCriticalSection(v5);
      if ( ++LODWORD(this[4].DebugInfo) == 1 )
        HIDWORD(this[4].DebugInfo) = GetCurrentThreadId();
      std::_Tree<std::_Tmap_traits<unsigned long,std::shared_ptr<AppV::Client::Host::Session>,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,std::shared_ptr<AppV::Client::Host::Session>>>,0>>::erase(
        &this[4].LockCount,
        v43);
      v14 = LODWORD(this[4].DebugInfo)-- == 1;
      if ( v14 )
        HIDWORD(this[4].DebugInfo) = 0;
      LeaveCriticalSection(v5);
      if ( !v38 )
        goto LABEL_46;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 8), 0xFFFFFFFF) != 1 )
        goto LABEL_46;
      (**(void (__fastcall ***)(__int64))v38)(v38);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v38 + 12), 0xFFFFFFFF) != 1 )
        goto LABEL_46;
      v33 = *(void (__fastcall ***)(__int64))v38;
      v34 = v38;
    }
    else
    {
      v11 = *(_QWORD *)(v9 + 48);
      if ( v11 )
        _InterlockedIncrement((volatile signed __int32 *)(v11 + 8));
      v12 = *(_QWORD *)(v9 + 40);
      v49 = v12;
      v13 = *(volatile signed __int32 **)(v9 + 48);
      v50 = v13;
      v14 = LODWORD(this[4].DebugInfo)-- == 1;
      if ( v14 )
        HIDWORD(this[4].DebugInfo) = 0;
      LeaveCriticalSection(v5);
      v47 = 0;
      v57 = 0;
      si128 = _mm_load_si128((const __m128i *)&_xmm);
      LOWORD(v57) = 0;
      v55 = 0;
      v56 = si128;
      LOWORD(v55) = 0;
      v15 = (*(__int64 (__fastcall **)(_QWORD, __int128 *))(*(_QWORD *)v45 + 24LL))(v45, &v57);
      if ( (v15 & 0x8000000000LL) != 0 )
      {
        v15 = (*(__int64 (__fastcall **)(__int64, __int128 *))(*(_QWORD *)v12 + 24LL))(v12, &v55);
        if ( (v15 & 0x8000000000LL) != 0 )
        {
          v16 = &v55;
          if ( v56.m128i_i64[1] > 7uLL )
            v16 = (__int128 *)v55;
          v17 = &v57;
          if ( si128.m128i_i64[1] > 7uLL )
            v17 = (__int128 *)v57;
          if ( !(unsigned int)_o__wcsicmp(v17, v16) )
          {
            std::string::string(v59, "AppV::Client::Host::UserManagerImpl::InternalLogon");
            v60 = 236;
            AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v18);
            v53 = 0;
            v54 = 0;
            std::wstring::_Construct<1,wchar_t const *>(
              (char **)&v53,
              L"User Manager ignoring duplicate logon event for session %1% that it is already tracking for the same user",
              0x69u);
            v20 = AppV::Log::fmt(v19, v61, &v53);
            v21 = AppV::LogFormatter::operator%<unsigned long>(v20, (__int64)v43);
            v51 = 0;
            v52 = 0;
            std::wstring::_Construct<1,wchar_t const *>((char **)&v51, L"Client", 6u);
            AppV::DecoratedLog::operator()((char *)v59, 4, (int)&v51, v21);
            std::wstring::~wstring((char **)&v51);
            v61[0] = &AppV::LogFormatter::`vftable';
            std::wstring::~wstring(v62);
            std::wstring::~wstring((char **)&v53);
            std::string::~string(v59);
            std::wstring::~wstring((char **)&v55);
            std::wstring::~wstring((char **)&v57);
            if ( v13 )
            {
              if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
              {
                (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
                if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
                  (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
              }
            }
            v22 = *((_QWORD *)&v45 + 1);
            if ( !*((_QWORD *)&v45 + 1) )
              goto LABEL_65;
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v45 + 1) + 8LL), 0xFFFFFFFF) != 1 )
              goto LABEL_65;
            (**(void (__fastcall ***)(__int64))v22)(v22);
            if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v22 + 12), 0xFFFFFFFF) != 1 )
              goto LABEL_65;
            v23 = *(void (__fastcall ***)(__int64))v22;
            v24 = v22;
            goto LABEL_64;
          }
        }
      }
      std::string::string(v59, "AppV::Client::Host::UserManagerImpl::InternalLogon");
      v60 = 229;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v25);
      v51 = 0;
      v52 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v51,
        L"User Manager rejecting a logon for session %1% because it is already tracking that as a logon session for a different user",
        0x7Au);
      v27 = AppV::Log::fmt(v26, v61, &v51);
      v28 = AppV::LogFormatter::operator%<unsigned long>(v27, (__int64)v43);
      v53 = 0;
      v54 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v53, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v59, 1, (int)&v53, v28);
      std::wstring::~wstring((char **)&v53);
      v61[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v62);
      std::wstring::~wstring((char **)&v51);
      std::string::~string(v59);
      AppV::Client::Host::Session::ReportPublicLogonError(v43[0], v15);
      v29 = strrchr("admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp", 92);
      if ( v29 )
        v30 = v29 + 1;
      else
        v30 = "admin\\appman\\appv\\client\\host\\common\\usermanagerimpl.cpp";
      v31 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v30) << 52)
          | 0x1D0E00000304LL;
      std::wstring::~wstring((char **)&v55);
      std::wstring::~wstring((char **)&v57);
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      v32 = *((_QWORD *)&v45 + 1);
      if ( !*((_QWORD *)&v45 + 1) )
        goto LABEL_46;
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v45 + 1) + 8LL), 0xFFFFFFFF) != 1 )
        goto LABEL_46;
      (**(void (__fastcall ***)(__int64))v32)(v32);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(v32 + 12), 0xFFFFFFFF) != 1 )
        goto LABEL_46;
      v33 = *(void (__fastcall ***)(__int64))v32;
      v34 = v32;
    }
    v33[1](v34);
LABEL_46:
    v35 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
    if ( *((_QWORD *)&v44 + 1) )
    {
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v35)(v35);
        if ( _InterlockedExchangeAdd(v35 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v35 + 8LL))(v35);
      }
    }
    return v31;
  }
  AppV::Client::Host::Session::ReportPublicLogonError(v43[0], UserToken);
  v42 = (volatile signed __int32 *)*((_QWORD *)&v44 + 1);
  if ( *((_QWORD *)&v44 + 1) )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)(*((_QWORD *)&v44 + 1) + 8LL), 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v42)(v42);
      if ( _InterlockedExchangeAdd(v42 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v42 + 8LL))(v42);
    }
  }
  return v4;
}

```

## disassembly

```asm
0x140049e30  mov     [rsp-8+arg_10], rbx
0x140049e35  push    rbp
0x140049e36  push    rsi
0x140049e37  push    rdi
0x140049e38  push    r12
0x140049e3a  push    r13
0x140049e3c  push    r14
0x140049e3e  push    r15
0x140049e40  lea     rbp, [rsp-60h]
0x140049e45  sub     rsp, 160h
0x140049e4c  mov     rax, cs:__security_cookie
0x140049e53  xor     rax, rsp
0x140049e56  mov     [rbp+90h+var_38], rax
0x140049e5a  mov     eax, edx
0x140049e5c  mov     rdi, rcx
0x140049e5f  mov     [rsp+190h+var_170], edx
0x140049e63  xorps   xmm0, xmm0
0x140049e66  movdqu  [rsp+190h+var_160], xmm0
0x140049e6c  lea     rdx, [rsp+190h+var_160]
0x140049e71  mov     ecx, eax
0x140049e73  call    ?GetUserToken@UserManagerImpl@Host@Client@AppV@@CA_KKAEAV?$shared_ptr@VCHandle@ATL@@@std@@@Z; AppV::Client::Host::UserManagerImpl::GetUserToken(ulong,std::shared_ptr<ATL::CHandle> &)
0x140049e78  mov     r14, rax
0x140049e7b  bt      rax, 27h ; '''
0x140049e80  jnb     loc_14004A4FF
0x140049e86  xorps   xmm0, xmm0
0x140049e89  movdqu  [rsp+190h+var_150], xmm0
0x140049e8f  lea     r9, [rsp+190h+var_150]
0x140049e94  lea     r8, [rsp+190h+var_160]
0x140049e99  mov     edx, [rsp+190h+var_170]
0x140049e9d  mov     rcx, [rdi+60h]
0x140049ea1  call    ?CreateInstance@SessionFactory@Host@Client@AppV@@SAXAEAVClientComponent@34@KAEBV?$shared_ptr@VCHandle@ATL@@@std@@AEAV?$shared_ptr@VSession@Host@Client@AppV@@@7@@Z; AppV::Client::Host::SessionFactory::CreateInstance(AppV::Client::ClientComponent &,ulong,std::shared_ptr<ATL::CHandle> const &,std::shared_ptr<AppV::Client::Host::Session> &)
0x140049ea6  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140049ead  mov     [rsp+190h+var_140], rax
0x140049eb2  lea     rbx, [rdi+78h]
0x140049eb6  mov     [rsp+190h+var_130], rbx
0x140049ebb  mov     rcx, rbx; lpCriticalSection
0x140049ebe  call    cs:__imp_EnterCriticalSection
0x140049ec4  inc     dword ptr [rbx+28h]
0x140049ec7  cmp     dword ptr [rbx+28h], 1
0x140049ecb  jnz     short loc_140049ED6
0x140049ecd  call    cs:__imp_GetCurrentThreadId
0x140049ed3  mov     [rbx+2Ch], eax
0x140049ed6  mov     [rsp+190h+var_138], 1
0x140049edb  lea     r13, [rdi+0A8h]
0x140049ee2  mov     rdx, [r13+0]
0x140049ee6  mov     rcx, [rdx+8]
0x140049eea  xor     eax, eax
0x140049eec  mov     [rsp+190h+var_11C], eax
0x140049ef0  mov     r14, rdx
0x140049ef3  mov     r9d, [rsp+190h+var_170]
0x140049ef8  xor     esi, esi
0x140049efa  jmp     short loc_140049F1B
0x140049efc  cmp     [rcx+20h], r9d
0x140049f00  jnb     short loc_140049F07
0x140049f02  mov     r8b, 1
0x140049f05  jmp     short loc_140049F0D
0x140049f07  mov     r8b, sil
0x140049f0a  mov     r14, rcx
0x140049f0d  lea     rax, [rcx+10h]
0x140049f11  test    r8b, r8b
0x140049f14  cmovz   rax, rcx
0x140049f18  mov     rcx, [rax]
0x140049f1b  cmp     [rcx+19h], sil
0x140049f1f  jz      short loc_140049EFC
0x140049f21  cmp     [r14+19h], sil
0x140049f25  jnz     loc_14004A35E
0x140049f2b  cmp     r9d, [r14+20h]
0x140049f2f  jb      loc_14004A35E
0x140049f35  cmp     rdx, r14
0x140049f38  jz      loc_14004A35E
0x140049f3e  mov     rax, [r14+30h]
0x140049f42  test    rax, rax
0x140049f45  jz      short loc_140049F4B
0x140049f47  lock inc dword ptr [rax+8]
0x140049f4b  mov     r15, [r14+28h]
0x140049f4f  mov     [rsp+190h+var_128], r15
0x140049f54  mov     r14, [r14+30h]
0x140049f58  mov     [rsp+70h], r14
0x140049f5d  or      edi, 0FFFFFFFFh
0x140049f60  add     [rbx+28h], edi
0x140049f63  jnz     short loc_140049F68
0x140049f65  mov     [rbx+2Ch], esi
0x140049f68  mov     rcx, rbx; lpCriticalSection
0x140049f6b  call    cs:__imp_LeaveCriticalSection
0x140049f71  mov     [rsp+190h+var_138], sil
0x140049f76  xorps   xmm0, xmm0
0x140049f79  movups  [rbp+90h+var_B0], xmm0
0x140049f7d  movdqa  xmm1, cs:__xmm@00000000000000070000000000000000
0x140049f85  movdqu  [rbp+90h+var_A0], xmm1
0x140049f8a  mov     word ptr [rbp+90h+var_B0], si
0x140049f8e  movups  [rbp+90h+var_D0], xmm0
0x140049f92  movdqu  [rbp+90h+var_C0], xmm1
0x140049f97  mov     word ptr [rbp+90h+var_D0], si
0x140049f9b  mov     rcx, qword ptr [rsp+190h+var_150]
0x140049fa0  mov     rax, [rcx]
0x140049fa3  lea     rdx, [rbp+90h+var_B0]
0x140049fa7  mov     rax, [rax+18h]
0x140049fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049fb0  mov     r12, rax
0x140049fb3  bt      rax, 27h ; '''
0x140049fb8  jnb     loc_14004A16C
0x140049fbe  mov     rax, [r15]
0x140049fc1  lea     rdx, [rbp+90h+var_D0]
0x140049fc5  mov     rcx, r15
0x140049fc8  mov     rax, [rax+18h]
0x140049fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140049fd1  mov     r12, rax
0x140049fd4  bt      rax, 27h ; '''
0x140049fd9  jnb     loc_14004A16C
0x140049fdf  lea     rdx, [rbp+90h+var_D0]
0x140049fe3  cmp     qword ptr [rbp+90h+var_C0+8], 7
0x140049fe8  cmova   rdx, qword ptr [rbp+90h+var_D0]
0x140049fed  lea     rcx, [rbp+90h+var_B0]
0x140049ff1  cmp     qword ptr [rbp+90h+var_A0+8], 7
0x140049ff6  cmova   rcx, qword ptr [rbp+90h+var_B0]
0x140049ffb  call    cs:__imp__o__wcsicmp
0x14004a001  test    eax, eax
0x14004a003  jnz     loc_14004A16C
0x14004a009  lea     rdx, aAppvClientHost_19; "AppV::Client::Host::UserManagerImpl::In"...
0x14004a010  lea     rcx, [rbp+90h+var_90]
0x14004a014  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004a019  mov     [rbp+90h+var_70], 0ECh
0x14004a020  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004a025  xorps   xmm0, xmm0
0x14004a028  movups  [rbp+90h+var_F0], xmm0
0x14004a02c  xorps   xmm1, xmm1
0x14004a02f  movdqu  [rbp+90h+var_E0], xmm1
0x14004a034  mov     r8d, 69h ; 'i'
0x14004a03a  lea     rdx, aUserManagerIgn; "User Manager ignoring duplicate logon e"...
0x14004a041  lea     rcx, [rbp+90h+var_F0]
0x14004a045  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a04a  nop
0x14004a04b  lea     r8, [rbp+90h+var_F0]
0x14004a04f  lea     rdx, [rbp+90h+var_68]
0x14004a053  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004a058  nop
0x14004a059  lea     rdx, [rsp+190h+var_170]
0x14004a05e  mov     rcx, rax
0x14004a061  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004a066  mov     rbx, rax
0x14004a069  xorps   xmm0, xmm0
0x14004a06c  movups  [rbp+90h+var_110], xmm0
0x14004a070  xorps   xmm1, xmm1
0x14004a073  movdqu  [rbp+90h+var_100], xmm1
0x14004a078  mov     r8d, 6
0x14004a07e  lea     rdx, aClient; "Client"
0x14004a085  lea     rcx, [rbp+90h+var_110]
0x14004a089  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a08e  nop
0x14004a08f  mov     r9, rbx
0x14004a092  lea     r8, [rbp+90h+var_110]
0x14004a096  mov     edx, 4
0x14004a09b  lea     rcx, [rbp+90h+var_90]
0x14004a09f  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004a0a4  nop
0x14004a0a5  lea     rcx, [rbp+90h+var_110]
0x14004a0a9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a0ae  nop
0x14004a0af  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004a0b6  mov     [rbp+90h+var_68], rax
0x14004a0ba  lea     rcx, [rbp+90h+var_58]
0x14004a0be  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a0c3  nop
0x14004a0c4  lea     rcx, [rbp+90h+var_F0]
0x14004a0c8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a0cd  nop
0x14004a0ce  lea     rcx, [rbp+90h+var_90]
0x14004a0d2  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004a0d7  nop
0x14004a0d8  lea     rcx, [rbp+90h+var_D0]
0x14004a0dc  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a0e1  nop
0x14004a0e2  lea     rcx, [rbp+90h+var_B0]
0x14004a0e6  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a0eb  nop
0x14004a0ec  test    r14, r14
0x14004a0ef  jz      short loc_14004A127
0x14004a0f1  mov     eax, edi
0x14004a0f3  lock xadd [r14+8], eax
0x14004a0f9  add     eax, edi
0x14004a0fb  jnz     short loc_14004A127
0x14004a0fd  mov     rax, [r14]
0x14004a100  mov     rcx, r14
0x14004a103  mov     rax, [rax]
0x14004a106  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a10b  mov     eax, edi
0x14004a10d  lock xadd [r14+0Ch], eax
0x14004a113  add     eax, edi
0x14004a115  jnz     short loc_14004A127
0x14004a117  mov     rax, [r14]
0x14004a11a  mov     rcx, r14
0x14004a11d  mov     rax, [rax+8]
0x14004a121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a126  nop
0x14004a127  mov     rbx, qword ptr [rsp+190h+var_150+8]
0x14004a12c  test    rbx, rbx
0x14004a12f  jz      loc_14004A436
0x14004a135  mov     eax, edi
0x14004a137  lock xadd [rbx+8], eax
0x14004a13c  add     eax, edi
0x14004a13e  jnz     loc_14004A436
0x14004a144  mov     rax, [rbx]
0x14004a147  mov     rcx, rbx
0x14004a14a  mov     rax, [rax]
0x14004a14d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a152  mov     eax, edi
0x14004a154  lock xadd [rbx+0Ch], eax
0x14004a159  add     eax, edi
0x14004a15b  jnz     loc_14004A436
0x14004a161  mov     rax, [rbx]
0x14004a164  mov     rcx, rbx
0x14004a167  jmp     loc_14004A42C
0x14004a16c  lea     rdx, aAppvClientHost_19; "AppV::Client::Host::UserManagerImpl::In"...
0x14004a173  lea     rcx, [rbp+90h+var_90]
0x14004a177  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14004a17c  mov     [rbp+90h+var_70], 0E5h
0x14004a183  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x14004a188  xorps   xmm0, xmm0
0x14004a18b  movups  [rbp+90h+var_110], xmm0
0x14004a18f  xorps   xmm1, xmm1
0x14004a192  movdqu  [rbp+90h+var_100], xmm1
0x14004a197  mov     r8d, 7Ah ; 'z'
0x14004a19d  lea     rdx, aUserManagerRej; "User Manager rejecting a logon for sess"...
0x14004a1a4  lea     rcx, [rbp+90h+var_110]
0x14004a1a8  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a1ad  nop
0x14004a1ae  lea     r8, [rbp+90h+var_110]
0x14004a1b2  lea     rdx, [rbp+90h+var_68]
0x14004a1b6  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14004a1bb  nop
0x14004a1bc  lea     rdx, [rsp+190h+var_170]
0x14004a1c1  mov     rcx, rax
0x14004a1c4  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14004a1c9  mov     rbx, rax
0x14004a1cc  xorps   xmm0, xmm0
0x14004a1cf  movups  [rbp+90h+var_F0], xmm0
0x14004a1d3  xorps   xmm1, xmm1
0x14004a1d6  movdqu  [rbp+90h+var_E0], xmm1
0x14004a1db  mov     r8d, 6
0x14004a1e1  lea     rdx, aClient; "Client"
0x14004a1e8  lea     rcx, [rbp+90h+var_F0]
0x14004a1ec  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14004a1f1  nop
0x14004a1f2  mov     r9, rbx
0x14004a1f5  lea     r8, [rbp+90h+var_F0]
0x14004a1f9  mov     edx, 1
0x14004a1fe  lea     rcx, [rbp+90h+var_90]
0x14004a202  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14004a207  nop
0x14004a208  lea     rcx, [rbp+90h+var_F0]
0x14004a20c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a211  nop
0x14004a212  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14004a219  mov     [rbp+90h+var_68], rax
0x14004a21d  lea     rcx, [rbp+90h+var_58]
0x14004a221  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a226  nop
0x14004a227  lea     rcx, [rbp+90h+var_110]
0x14004a22b  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a230  nop
0x14004a231  lea     rcx, [rbp+90h+var_90]
0x14004a235  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x14004a23a  mov     rdx, r12; unsigned __int64
0x14004a23d  mov     ecx, [rsp+190h+var_170]; unsigned int
0x14004a241  call    ?ReportPublicLogonError@Session@Host@Client@AppV@@SAXK_K@Z; AppV::Client::Host::Session::ReportPublicLogonError(ulong,unsigned __int64)
0x14004a246  mov     edx, 5Ch ; '\'; Ch
0x14004a24b  lea     rcx, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004a252  call    cs:__imp_strrchr
0x14004a258  test    rax, rax
0x14004a25b  jz      short loc_14004A262
0x14004a25d  inc     rax
0x14004a260  jmp     short loc_14004A269
0x14004a262  lea     rax, aAdminAppmanApp_17; "admin\\appman\\appv\\client\\host\\comm"...
0x14004a269  mov     rdx, rax; char *
0x14004a26c  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14004a273  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14004a278  mov     r15, rax
0x14004a27b  shl     r15, 34h
0x14004a27f  mov     rax, 1D0E00000304h
0x14004a289  or      r15, rax
0x14004a28c  lea     rcx, [rbp+90h+var_D0]
0x14004a290  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a295  nop
0x14004a296  lea     rcx, [rbp+90h+var_B0]
0x14004a29a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14004a29f  nop
0x14004a2a0  test    r14, r14
0x14004a2a3  jz      short loc_14004A2DB
0x14004a2a5  mov     eax, edi
0x14004a2a7  lock xadd [r14+8], eax
0x14004a2ad  add     eax, edi
0x14004a2af  jnz     short loc_14004A2DB
0x14004a2b1  mov     rax, [r14]
0x14004a2b4  mov     rcx, r14
0x14004a2b7  mov     rax, [rax]
0x14004a2ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004a2bf  mov     eax, edi
0x14004a2c1  lock xadd [r14+0Ch], eax
0x14004a2c7  add     eax, edi
0x14004a2c9  jnz     short loc_14004A2DB
  ... truncated ...
```
