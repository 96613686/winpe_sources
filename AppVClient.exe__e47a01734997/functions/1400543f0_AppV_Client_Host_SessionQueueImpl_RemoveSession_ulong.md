# AppV::Client::Host::SessionQueueImpl::RemoveSession(ulong)

- ea: `0x1400543f0`
- end: `0x140054c42`
- name: `?RemoveSession@SessionQueueImpl@Host@Client@AppV@@UEAA_KK@Z`
- size: `2130`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::SessionQueueImpl *__hidden this, unsigned int)`
- caller_count: `0`
- callee_count: `15`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140004280`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018788`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x1400530f8`
- `0x1400543f0`
- `0x140054c80`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400546a0`
- `KERNEL32!SetEvent` at `0x140054762`
- `KERNEL32!SetEvent` at `0x1400546a0`
- `KERNEL32!SetEvent` at `0x140054762`
- `KERNEL32!GetLastError` at `0x140054771`
- `KERNEL32!GetLastError` at `0x140054771`
- `KERNEL32!GetCurrentThreadId` at `0x140054449`
- `KERNEL32!GetCurrentThreadId` at `0x140054449`
- `KERNEL32!LeaveCriticalSection` at `0x140054881`
- `KERNEL32!LeaveCriticalSection` at `0x140054c11`
- `KERNEL32!LeaveCriticalSection` at `0x140054881`
- `KERNEL32!LeaveCriticalSection` at `0x140054c11`
- `KERNEL32!EnterCriticalSection` at `0x14005443a`
- `KERNEL32!EnterCriticalSection` at `0x14005443a`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140054977`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140054aa3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140054bca`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140054977`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140054aa3`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140054bca`

## string_xrefs

- `0x140054970`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140054987`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140054a9c`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140054ab3`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140054bc3`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140054bda`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x1400544aa`: `AppV::Client::Host::SessionQueueImpl::RemoveSession`
- `0x14005477b`: `AppV::Client::Host::SessionQueueImpl::RemoveSession`
- `0x140054896`: `AppV::Client::Host::SessionQueueImpl::RemoveSession`
- `0x1400549c3`: `AppV::Client::Host::SessionQueueImpl::RemoveSession`
- `0x140054af0`: `AppV::Client::Host::SessionQueueImpl::RemoveSession`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
unsigned __int64 __fastcall AppV::Client::Host::SessionQueueImpl::RemoveSession(
        AppV::Client::Host::SessionQueueImpl *this,
        unsigned int a2)
{
  char *v3; // rsi
  __int64 *v4; // rcx
  __int64 *v5; // rax
  __int64 *v6; // rbx
  __int64 v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rax
  __int64 v11; // rdi
  __int64 **v12; // rcx
  __int64 *v13; // rdx
  __int64 *i; // rax
  __int64 *j; // rcx
  void *v16; // rax
  __int64 *v17; // rcx
  __int64 *v18; // rax
  __int64 *v19; // rbx
  __int64 v20; // rdi
  __int64 v21; // r9
  char *v22; // r15
  __int64 v23; // r8
  __int64 v24; // rax
  __int64 **v25; // rdx
  __int64 *v26; // rax
  __int64 *k; // rcx
  __int64 *m; // rdx
  char *v29; // rbx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rax
  __int64 v34; // rax
  __int64 v35; // rbx
  bool v36; // zf
  __int64 v38; // rcx
  __int64 v39; // rcx
  __int64 v40; // rax
  __int64 v41; // rax
  __int64 v42; // rbx
  char *v43; // rax
  const char *v44; // rax
  unsigned __int64 v45; // rbx
  __int64 v46; // rcx
  __int64 v47; // rcx
  __int64 v48; // rax
  __int64 v49; // rax
  __int64 v50; // rbx
  char *v51; // rax
  const char *v52; // rax
  __int64 v53; // rcx
  __int64 v54; // rcx
  __int64 v55; // rax
  __int64 v56; // rbx
  char *v57; // rax
  const char *v58; // rax
  unsigned int v59; // [rsp+20h] [rbp-99h] BYREF
  unsigned int v60; // [rsp+28h] [rbp-91h] BYREF
  DWORD LastError; // [rsp+2Ch] [rbp-8Dh] BYREF
  void **v62; // [rsp+30h] [rbp-89h]
  char v63; // [rsp+38h] [rbp-81h]
  char *v64; // [rsp+40h] [rbp-79h]
  __int128 v65; // [rsp+48h] [rbp-71h] BYREF
  __int64 v66; // [rsp+58h] [rbp-61h]
  __int64 v67; // [rsp+60h] [rbp-59h]
  __int128 v68; // [rsp+68h] [rbp-51h] BYREF
  __int64 v69; // [rsp+78h] [rbp-41h]
  __int64 v70; // [rsp+80h] [rbp-39h]
  char *v71[4]; // [rsp+88h] [rbp-31h] BYREF
  int v72; // [rsp+A8h] [rbp-11h]
  _QWORD v73[2]; // [rsp+B0h] [rbp-9h] BYREF
  char *v74[4]; // [rsp+C0h] [rbp+7h] BYREF

  v59 = a2;
  v62 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v3 = (char *)this + 8;
  v64 = (char *)this + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
  if ( ++*((_DWORD *)v3 + 10) == 1 )
    *((_DWORD *)v3 + 11) = GetCurrentThreadId();
  v63 = 1;
  v4 = (__int64 *)*((_QWORD *)this + 8);
  v5 = (__int64 *)v4[1];
  HIDWORD(v65) = 0;
  v6 = v4;
  while ( !*((_BYTE *)v5 + 25) )
  {
    if ( *((_DWORD *)v5 + 7) >= v59 )
    {
      v6 = v5;
      v5 = (__int64 *)*v5;
    }
    else
    {
      v5 = (__int64 *)v5[2];
    }
  }
  if ( *((_BYTE *)v6 + 25) || v59 < *((_DWORD *)v6 + 7) || v4 == v6 )
  {
    std::string::string(v71, "AppV::Client::Host::SessionQueueImpl::RemoveSession");
    v72 = 101;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v53);
    v65 = 0;
    v66 = 0;
    v67 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v65,
      L"UserManager dropping request to dequeue session operations for unknown cookie %1%",
      0x51u);
    v55 = AppV::Log::fmt(v54, v73, &v65);
    v56 = AppV::LogFormatter::operator%<unsigned long>(v55, (__int64)&v59);
    v68 = 0;
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v71, 1, (int)&v68, v56);
    std::wstring::~wstring((char **)&v68);
    v73[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v74);
    std::wstring::~wstring((char **)&v65);
    std::string::~string(v71);
    v57 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp", 92);
    if ( v57 )
      v58 = v57 + 1;
    else
      v58 = "admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp";
    v45 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v58) << 52)
        | 0xC0E00000305LL;
    v36 = (*((_DWORD *)v3 + 10))-- == 1;
    if ( v36 )
      *((_DWORD *)v3 + 11) = 0;
  }
  else
  {
    v60 = *((_DWORD *)v6 + 8);
    std::string::string(v71, "AppV::Client::Host::SessionQueueImpl::RemoveSession");
    v72 = 109;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v7);
    v65 = 0;
    v66 = 0;
    v67 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v65,
      L"UserManager is dequeuing the operation for session %1% with tracking cookie %2%",
      0x4Fu);
    v9 = AppV::Log::fmt(v8, v73, &v65);
    v10 = AppV::LogFormatter::operator%<unsigned long>(v9, (__int64)&v60);
    v11 = AppV::LogFormatter::operator%<unsigned long>(v10, (__int64)&v59);
    v68 = 0;
    v69 = 0;
    v70 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v71, 4, (int)&v68, v11);
    std::wstring::~wstring((char **)&v68);
    v73[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v74);
    std::wstring::~wstring((char **)&v65);
    std::string::~string(v71);
    v12 = (__int64 **)v6[2];
    v13 = v6;
    if ( *((_BYTE *)v12 + 25) )
    {
      for ( i = (__int64 *)v6[1]; !*((_BYTE *)i + 25) && v6 == (__int64 *)i[2]; i = (__int64 *)i[1] )
        v6 = i;
    }
    else
    {
      for ( j = *v12; !*((_BYTE *)j + 25); j = (__int64 *)*j )
        ;
    }
    v16 = (void *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned long>>>::_Extract(
                    (char *)this + 64,
                    v13);
    operator delete(v16);
    v17 = (__int64 *)*((_QWORD *)this + 10);
    v18 = (__int64 *)v17[1];
    HIDWORD(v65) = 0;
    v19 = v17;
    while ( !*((_BYTE *)v18 + 25) )
    {
      if ( *((_DWORD *)v18 + 8) >= v60 )
      {
        v19 = v18;
        v18 = (__int64 *)*v18;
      }
      else
      {
        v18 = (__int64 *)v18[2];
      }
    }
    if ( *((_BYTE *)v19 + 25) || v60 < *((_DWORD *)v19 + 8) || v17 == v19 )
    {
      std::string::string(v71, "AppV::Client::Host::SessionQueueImpl::RemoveSession");
      v72 = 119;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v46);
      v65 = 0;
      v66 = 0;
      v67 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v65,
        L"UserManager dropping request to dequeue session operations for cookie %2% matched to unknown session %1%",
        0x68u);
      v48 = AppV::Log::fmt(v47, v73, &v65);
      v49 = AppV::LogFormatter::operator%<unsigned long>(v48, (__int64)&v60);
      v50 = AppV::LogFormatter::operator%<unsigned long>(v49, (__int64)&v59);
      v68 = 0;
      v69 = 0;
      v70 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v71, 1, (int)&v68, v50);
      std::wstring::~wstring((char **)&v68);
      v73[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v74);
      std::wstring::~wstring((char **)&v65);
      std::string::~string(v71);
      v51 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp", 92);
      if ( v51 )
        v52 = v51 + 1;
      else
        v52 = "admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp";
      v45 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v52) << 52)
          | 0xF0E00000305LL;
      v36 = (*((_DWORD *)v3 + 10))-- == 1;
      if ( v36 )
        *((_DWORD *)v3 + 11) = 0;
    }
    else
    {
      v20 = v19[8];
      v21 = v20 + v19[9];
      v22 = (char *)v19[5];
      if ( v22 )
        v23 = *(_QWORD *)v22;
      else
        v23 = 0;
      while ( v21 != v20 )
      {
        if ( ***(_DWORD ***)(*(_QWORD *)(v23 + 8) + 8 * (v20 & (*(_QWORD *)(v23 + 16) - 1LL))) == v59 )
        {
          if ( v21 != v20 )
          {
            if ( v22 )
              v24 = *(_QWORD *)v22;
            else
              v24 = 0;
            SetEvent(**(HANDLE **)(**(_QWORD **)(*(_QWORD *)(v24 + 8) + 8 * (v20 & (*(_QWORD *)(v24 + 16) - 1LL))) + 8LL));
            v71[1] = 0;
            v71[0] = v22;
            v71[2] = (char *)(v20 + 1);
            v65 = (unsigned __int64)v22;
            v66 = v20;
            std::deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>::erase(
              v19 + 5,
              &v68,
              &v65,
              v71);
            if ( v19[9] )
            {
              if ( !SetEvent(**(HANDLE **)(**(_QWORD **)(v19[6] + 8 * (v19[8] & (v19[7] - 1))) + 8LL)) )
              {
                LastError = GetLastError();
                std::string::string(v71, "AppV::Client::Host::SessionQueueImpl::RemoveSession");
                v72 = 157;
                AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v30);
                v65 = 0;
                v66 = 0;
                v67 = 0;
                std::wstring::_Construct<1,wchar_t const *>(
                  (char **)&v65,
                  L"UserManager failed to signal queued operation for session %1% with cookie %2%, error = %3%",
                  0x5Au);
                v32 = AppV::Log::fmt(v31, v73, &v65);
                v33 = AppV::LogFormatter::operator%<unsigned long>(v32, (__int64)&v60);
                v34 = AppV::LogFormatter::operator%<unsigned long>(
                        v33,
                        **(_QWORD **)(v19[6] + 8 * (v19[8] & (v19[7] - 1))));
                v35 = AppV::LogFormatter::operator%<unsigned long>(v34, (__int64)&LastError);
                v68 = 0;
                v69 = 0;
                v70 = 0;
                std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Client", 6u);
                AppV::DecoratedLog::operator()((char *)v71, 2, (int)&v68, v35);
                std::wstring::~wstring((char **)&v68);
                v73[0] = &AppV::LogFormatter::`vftable';
                std::wstring::~wstring(v74);
                std::wstring::~wstring((char **)&v65);
                std::string::~string(v71);
              }
            }
            else
            {
              v25 = (__int64 **)v19[2];
              if ( *((_BYTE *)v25 + 25) )
              {
                v26 = v19;
                for ( k = (__int64 *)v19[1]; !*((_BYTE *)k + 25) && v26 == (__int64 *)k[2]; k = (__int64 *)k[1] )
                  v26 = k;
              }
              else
              {
                for ( m = *v25; !*((_BYTE *)m + 25); m = (__int64 *)*m )
                  ;
              }
              v29 = (char *)std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,unsigned long>>>::_Extract(
                              (char *)this + 80,
                              v19);
              std::deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>::~deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>(v29 + 40);
              operator delete(v29);
            }
            v36 = (*((_DWORD *)v3 + 10))-- == 1;
            if ( v36 )
              *((_DWORD *)v3 + 11) = 0;
            LeaveCriticalSection((LPCRITICAL_SECTION)v3);
            return 0x8000000000LL;
          }
          break;
        }
        ++v20;
      }
      std::string::string(v71, "AppV::Client::Host::SessionQueueImpl::RemoveSession");
      v72 = 131;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v38);
      v65 = 0;
      v66 = 0;
      v67 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v65,
        L"UserManager dropping request to dequeue session operations for cookie %2% no longer queued for session %1%",
        0x6Au);
      v40 = AppV::Log::fmt(v39, v73, &v65);
      v41 = AppV::LogFormatter::operator%<unsigned long>(v40, (__int64)&v60);
      v42 = AppV::LogFormatter::operator%<unsigned long>(v41, (__int64)&v59);
      v68 = 0;
      v69 = 0;
      v70 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v68, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v71, 1, (int)&v68, v42);
      std::wstring::~wstring((char **)&v68);
      v73[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v74);
      std::wstring::~wstring((char **)&v65);
      std::string::~string(v71);
      v43 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp", 92);
      if ( v43 )
        v44 = v43 + 1;
      else
        v44 = "admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp";
      v45 = (AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v44) << 52)
          | 0x100E00000305LL;
      v36 = (*((_DWORD *)v3 + 10))-- == 1;
      if ( v36 )
        *((_DWORD *)v3 + 11) = 0;
    }
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)v3);
  return v45;
}

```

## disassembly

```asm
0x1400543f0  mov     [rsp-8+arg_10], rbx
0x1400543f5  mov     [rsp-8+arg_18], rsi
0x1400543fa  push    rbp
0x1400543fb  push    rdi
0x1400543fc  push    r12
0x1400543fe  push    r14
0x140054400  push    r15
0x140054402  lea     rbp, [rsp-37h]
0x140054407  sub     rsp, 0F0h
0x14005440e  mov     rax, cs:__security_cookie
0x140054415  xor     rax, rsp
0x140054418  mov     [rbp+57h+var_30], rax
0x14005441c  mov     r14, rcx
0x14005441f  mov     [rsp+110h+var_F0], edx
0x140054423  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14005442a  mov     [rsp+110h+var_E0], rax
0x14005442f  lea     rsi, [rcx+8]
0x140054433  mov     [rbp+57h+var_D0], rsi
0x140054437  mov     rcx, rsi; lpCriticalSection
0x14005443a  call    cs:__imp_EnterCriticalSection
0x140054440  inc     dword ptr [rsi+28h]
0x140054443  cmp     dword ptr [rsi+28h], 1
0x140054447  jnz     short loc_140054452
0x140054449  call    cs:__imp_GetCurrentThreadId
0x14005444f  mov     [rsi+2Ch], eax
0x140054452  mov     [rsp+110h+var_D8], 1
0x140054457  mov     rcx, [r14+40h]
0x14005445b  mov     rax, [rcx+8]
0x14005445f  xor     edx, edx
0x140054461  mov     dword ptr [rbp+57h+var_C8+0Ch], edx
0x140054464  mov     rbx, rcx
0x140054467  mov     edx, [rsp+110h+var_F0]
0x14005446b  xor     r12d, r12d
0x14005446e  jmp     short loc_140054481
0x140054470  cmp     [rax+1Ch], edx
0x140054473  jnb     short loc_14005447B
0x140054475  mov     rax, [rax+10h]
0x140054479  jmp     short loc_140054481
0x14005447b  mov     rbx, rax
0x14005447e  mov     rax, [rax]
0x140054481  cmp     [rax+19h], r12b
0x140054485  jz      short loc_140054470
0x140054487  cmp     [rbx+19h], r12b
0x14005448b  jnz     loc_140054AF0
0x140054491  cmp     edx, [rbx+1Ch]
0x140054494  jb      loc_140054AF0
0x14005449a  cmp     rcx, rbx
0x14005449d  jz      loc_140054AF0
0x1400544a3  mov     eax, [rbx+20h]
0x1400544a6  mov     [rsp+110h+var_E8], eax
0x1400544aa  lea     rdx, aAppvClientHost_2; "AppV::Client::Host::SessionQueueImpl::R"...
0x1400544b1  lea     rcx, [rbp+57h+var_88]
0x1400544b5  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400544ba  mov     [rbp+57h+var_68], 6Dh ; 'm'
0x1400544c1  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400544c6  xorps   xmm0, xmm0
0x1400544c9  movups  [rbp+57h+var_C8], xmm0
0x1400544cd  mov     [rbp+57h+var_B8], r12
0x1400544d1  mov     [rbp+57h+var_B0], r12
0x1400544d5  mov     r8d, 4Fh ; 'O'
0x1400544db  lea     rdx, aUsermanagerIsD; "UserManager is dequeuing the operation "...
0x1400544e2  lea     rcx, [rbp+57h+var_C8]
0x1400544e6  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400544eb  nop
0x1400544ec  lea     r8, [rbp+57h+var_C8]
0x1400544f0  lea     rdx, [rbp+57h+var_60]
0x1400544f4  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400544f9  nop
0x1400544fa  lea     rdx, [rsp+110h+var_E8]
0x1400544ff  mov     rcx, rax
0x140054502  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140054507  lea     rdx, [rsp+110h+var_F0]
0x14005450c  mov     rcx, rax
0x14005450f  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140054514  mov     rdi, rax
0x140054517  xorps   xmm0, xmm0
0x14005451a  movups  [rbp+57h+var_A8], xmm0
0x14005451e  mov     [rbp+57h+var_98], r12
0x140054522  mov     [rbp+57h+var_90], r12
0x140054526  mov     r8d, 6
0x14005452c  lea     rdx, aClient; "Client"
0x140054533  lea     rcx, [rbp+57h+var_A8]
0x140054537  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005453c  nop
0x14005453d  mov     r9, rdi
0x140054540  lea     r8, [rbp+57h+var_A8]
0x140054544  mov     edx, 4
0x140054549  lea     rcx, [rbp+57h+var_88]
0x14005454d  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140054552  nop
0x140054553  lea     rcx, [rbp+57h+var_A8]
0x140054557  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005455c  nop
0x14005455d  lea     rdi, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140054564  mov     [rbp+57h+var_60], rdi
0x140054568  lea     rcx, [rbp+57h+var_50]
0x14005456c  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140054571  nop
0x140054572  lea     rcx, [rbp+57h+var_C8]
0x140054576  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005457b  nop
0x14005457c  lea     rcx, [rbp+57h+var_88]
0x140054580  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140054585  mov     rcx, [rbx+10h]
0x140054589  mov     rdx, rbx
0x14005458c  cmp     [rcx+19h], r12b
0x140054590  jz      short loc_1400545AD
0x140054592  mov     rax, [rbx+8]
0x140054596  jmp     short loc_1400545A5
0x140054598  cmp     rbx, [rax+10h]
0x14005459c  jnz     short loc_1400545C2
0x14005459e  mov     rbx, rax
0x1400545a1  mov     rax, [rax+8]
0x1400545a5  cmp     [rax+19h], r12b
0x1400545a9  jz      short loc_140054598
0x1400545ab  jmp     short loc_1400545C2
0x1400545ad  mov     rcx, [rcx]
0x1400545b0  cmp     [rcx+19h], r12b
0x1400545b4  jnz     short loc_1400545C2
0x1400545b6  mov     rax, [rcx]
0x1400545b9  mov     rcx, rax
0x1400545bc  cmp     [rax+19h], r12b
0x1400545c0  jz      short loc_1400545B6
0x1400545c2  lea     rcx, [r14+40h]
0x1400545c6  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKK@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>,std::_Iterator_base0>)
0x1400545cb  mov     edx, 28h ; '('
0x1400545d0  mov     rcx, rax; Block
0x1400545d3  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x1400545d8  lea     r12, [r14+50h]
0x1400545dc  mov     rcx, [r12]
0x1400545e0  mov     rax, [rcx+8]
0x1400545e4  xor     edx, edx
0x1400545e6  mov     dword ptr [rbp+57h+var_C8+0Ch], edx
0x1400545e9  mov     rbx, rcx
0x1400545ec  mov     edx, [rsp+110h+var_E8]
0x1400545f0  xor     r14d, r14d
0x1400545f3  jmp     short loc_140054606
0x1400545f5  cmp     [rax+20h], edx
0x1400545f8  jnb     short loc_140054600
0x1400545fa  mov     rax, [rax+10h]
0x1400545fe  jmp     short loc_140054606
0x140054600  mov     rbx, rax
0x140054603  mov     rax, [rax]
0x140054606  cmp     [rax+19h], r14b
0x14005460a  jz      short loc_1400545F5
0x14005460c  cmp     [rbx+19h], r14b
0x140054610  jnz     loc_1400549C3
0x140054616  cmp     edx, [rbx+20h]
0x140054619  jb      loc_1400549C3
0x14005461f  cmp     rcx, rbx
0x140054622  jz      loc_1400549C3
0x140054628  mov     eax, [rsp+110h+var_F0]
0x14005462c  mov     rdi, [rbx+40h]
0x140054630  mov     r9, [rbx+48h]
0x140054634  add     r9, rdi
0x140054637  mov     r15, [rbx+28h]
0x14005463b  test    r15, r15
0x14005463e  jz      short loc_140054645
0x140054640  mov     r8, [r15]
0x140054643  jmp     short loc_140054648
0x140054645  xor     r8d, r8d
0x140054648  cmp     r9, rdi
0x14005464b  jz      loc_140054896
0x140054651  mov     rdx, [r8+10h]
0x140054655  dec     rdx
0x140054658  and     rdx, rdi
0x14005465b  mov     rcx, [r8+8]
0x14005465f  mov     rdx, [rcx+rdx*8]
0x140054663  mov     rcx, [rdx]
0x140054666  cmp     [rcx], eax
0x140054668  jz      short loc_14005466F
0x14005466a  inc     rdi
0x14005466d  jmp     short loc_140054648
0x14005466f  cmp     r9, rdi
0x140054672  jz      loc_140054896
0x140054678  test    r15, r15
0x14005467b  jz      short loc_140054682
0x14005467d  mov     rax, [r15]
0x140054680  jmp     short loc_140054684
0x140054682  xor     eax, eax
0x140054684  mov     rcx, [rax+10h]
0x140054688  dec     rcx
0x14005468b  and     rcx, rdi
0x14005468e  mov     rax, [rax+8]
0x140054692  mov     rcx, [rax+rcx*8]
0x140054696  mov     rax, [rcx]
0x140054699  mov     rcx, [rax+8]
0x14005469d  mov     rcx, [rcx]; hEvent
0x1400546a0  call    cs:__imp_SetEvent
0x1400546a6  mov     [rbp+57h+var_80], r14
0x1400546aa  mov     [rbp+57h+var_88], r15
0x1400546ae  lea     rax, [rdi+1]
0x1400546b2  mov     [rbp+57h+var_78], rax
0x1400546b6  mov     qword ptr [rbp+57h+var_C8+8], r14
0x1400546ba  mov     qword ptr [rbp+57h+var_C8], r15
0x1400546be  mov     [rbp+57h+var_B8], rdi
0x1400546c2  lea     r9, [rbp+57h+var_88]
0x1400546c6  lea     r8, [rbp+57h+var_C8]
0x1400546ca  lea     rdx, [rbp+57h+var_A8]
0x1400546ce  lea     rcx, [rbx+28h]
0x1400546d2  call    ?erase@?$deque@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@@2@@std@@QEAA?AV?$_Deque_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@@std@@@std@@@2@V?$_Deque_const_iterator@V?$_Deque_val@U?$_Deque_simple_types@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@@std@@@std@@@2@0@Z; std::deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>::erase(std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>>>,std::_Deque_const_iterator<std::_Deque_val<std::_Deque_simple_types<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>>>)
0x1400546d7  xor     edi, edi
0x1400546d9  cmp     [rbx+48h], rdi
0x1400546dd  jnz     short loc_140054745
0x1400546df  mov     rdx, [rbx+10h]
0x1400546e3  cmp     [rdx+19h], dil
0x1400546e7  jz      short loc_140054707
0x1400546e9  mov     rax, rbx
0x1400546ec  mov     rcx, [rbx+8]
0x1400546f0  jmp     short loc_1400546FF
0x1400546f2  cmp     rax, [rcx+10h]
0x1400546f6  jnz     short loc_14005471C
0x1400546f8  mov     rax, rcx
0x1400546fb  mov     rcx, [rcx+8]
0x1400546ff  cmp     [rcx+19h], dil
0x140054703  jz      short loc_1400546F2
0x140054705  jmp     short loc_14005471C
0x140054707  mov     rdx, [rdx]
0x14005470a  cmp     [rdx+19h], dil
0x14005470e  jnz     short loc_14005471C
0x140054710  mov     rax, [rdx]
0x140054713  mov     rdx, rax
0x140054716  cmp     [rax+19h], dil
0x14005471a  jz      short loc_140054710
0x14005471c  mov     rdx, rbx
0x14005471f  mov     rcx, r12
0x140054722  call    ?_Extract@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBKK@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBKK@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>::_Extract(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,ulong>>>,std::_Iterator_base0>)
0x140054727  mov     rbx, rax
0x14005472a  lea     rcx, [rax+28h]
0x14005472e  call    ??1?$deque@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@@2@@std@@QEAA@XZ; std::deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>::~deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>(void)
0x140054733  mov     edx, 50h ; 'P'
0x140054738  mov     rcx, rbx; Block
0x14005473b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x140054740  jmp     loc_140054875
0x140054745  mov     rcx, [rbx+38h]
0x140054749  dec     rcx
0x14005474c  and     rcx, [rbx+40h]
0x140054750  mov     rax, [rbx+30h]
0x140054754  mov     rcx, [rax+rcx*8]
0x140054758  mov     rax, [rcx]
0x14005475b  mov     rcx, [rax+8]
0x14005475f  mov     rcx, [rcx]; hEvent
0x140054762  call    cs:__imp_SetEvent
0x140054768  cmp     eax, 1
0x14005476b  jz      loc_140054875
0x140054771  call    cs:__imp_GetLastError
0x140054777  mov     [rsp+110h+var_E4], eax
0x14005477b  lea     rdx, aAppvClientHost_2; "AppV::Client::Host::SessionQueueImpl::R"...
0x140054782  lea     rcx, [rbp+57h+var_88]
0x140054786  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005478b  mov     [rbp+57h+var_68], 9Dh
0x140054792  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140054797  xorps   xmm0, xmm0
0x14005479a  movups  [rbp+57h+var_C8], xmm0
0x14005479e  mov     [rbp+57h+var_B8], rdi
0x1400547a2  mov     [rbp+57h+var_B0], rdi
0x1400547a6  mov     r8d, 5Ah ; 'Z'
0x1400547ac  lea     rdx, aUsermanagerFai_6; "UserManager failed to signal queued ope"...
0x1400547b3  lea     rcx, [rbp+57h+var_C8]
0x1400547b7  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400547bc  nop
0x1400547bd  lea     r8, [rbp+57h+var_C8]
0x1400547c1  lea     rdx, [rbp+57h+var_60]
0x1400547c5  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400547ca  nop
0x1400547cb  lea     rdx, [rsp+110h+var_E8]
0x1400547d0  mov     rcx, rax
0x1400547d3  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400547d8  mov     rdx, [rbx+38h]
0x1400547dc  dec     rdx
0x1400547df  and     rdx, [rbx+40h]
0x1400547e3  mov     rcx, [rbx+30h]
0x1400547e7  mov     rdx, [rcx+rdx*8]
0x1400547eb  mov     rdx, [rdx]
0x1400547ee  mov     rcx, rax
0x1400547f1  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400547f6  lea     rdx, [rsp+110h+var_E4]
0x1400547fb  mov     rcx, rax
0x1400547fe  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140054803  mov     rbx, rax
0x140054806  xorps   xmm0, xmm0
0x140054809  movups  [rbp+57h+var_A8], xmm0
0x14005480d  mov     [rbp+57h+var_98], rdi
0x140054811  mov     [rbp+57h+var_90], rdi
0x140054815  mov     r8d, 6
0x14005481b  lea     rdx, aClient; "Client"
0x140054822  lea     rcx, [rbp+57h+var_A8]
0x140054826  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005482b  nop
0x14005482c  mov     r9, rbx
0x14005482f  lea     r8, [rbp+57h+var_A8]
0x140054833  mov     edx, 2
0x140054838  lea     rcx, [rbp+57h+var_88]
0x14005483c  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140054841  nop
0x140054842  lea     rcx, [rbp+57h+var_A8]
0x140054846  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005484b  nop
0x14005484c  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140054853  mov     [rbp+57h+var_60], rax
  ... truncated ...
```
