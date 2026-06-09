# AppV::Client::Host::SessionQueueImpl::GetQueueEntry(ulong,std::shared_ptr<AppV::Client::Host::SessionQueueEntry> &)

- ea: `0x140053e10`
- end: `0x1400543e8`
- name: `?GetQueueEntry@SessionQueueImpl@Host@Client@AppV@@UEBA_KKAEAV?$shared_ptr@VSessionQueueEntry@Host@Client@AppV@@@std@@@Z`
- size: `1496`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `broker_com_uri`

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
- `0x140053e10`
- `0x14006a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140053eba`
- `KERNEL32!GetCurrentThreadId` at `0x140053eba`
- `KERNEL32!LeaveCriticalSection` at `0x14005403b`
- `KERNEL32!LeaveCriticalSection` at `0x1400543b0`
- `KERNEL32!LeaveCriticalSection` at `0x14005403b`
- `KERNEL32!LeaveCriticalSection` at `0x1400543b0`
- `KERNEL32!EnterCriticalSection` at `0x140053eab`
- `KERNEL32!EnterCriticalSection` at `0x140053eab`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140053ff4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005417c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400542ec`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140053ff4`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x14005417c`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x1400542ec`

## string_xrefs

- `0x140053fed`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140054004`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140054175`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x14005418c`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x1400542e5`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x1400542fc`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall AppV::Client::Host::SessionQueueImpl::GetQueueEntry(__int64 a1, int a2, _QWORD *a3)
{
  volatile signed __int32 *v5; // rbx
  __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // r8
  char v9; // r10
  __int64 *v10; // rcx
  __int64 v11; // rcx
  __int64 v12; // rcx
  __int64 v13; // rax
  __int64 v14; // rbx
  char *v15; // rax
  const char *v16; // rax
  unsigned __int64 FileId; // rbx
  __int64 v18; // rax
  unsigned __int64 v19; // rbx
  bool v20; // zf
  _DWORD *v22; // rbx
  __int64 *v23; // r8
  __int64 *v24; // rcx
  __int64 *i; // rdx
  __int64 v26; // rcx
  __int64 v27; // rcx
  __int64 v28; // rax
  __int64 v29; // rax
  __int64 v30; // rbx
  char *v31; // rax
  const char *v32; // rax
  __int64 v33; // r8
  __int64 v34; // r11
  __int64 *v35; // r9
  __int64 v36; // r10
  __int64 v37; // rcx
  __int64 v38; // rcx
  __int64 v39; // rax
  __int64 v40; // rax
  __int64 v41; // rbx
  char *v42; // rax
  const char *v43; // rax
  __int64 v44; // rax
  __int64 *v45; // rcx
  __int64 v46; // rdx
  __int64 v47; // rax
  __int64 v48; // rcx
  volatile signed __int32 *v49; // rbx
  _DWORD v50[4]; // [rsp+20h] [rbp-99h] BYREF
  void **v51; // [rsp+30h] [rbp-89h]
  char v52; // [rsp+38h] [rbp-81h]
  __int64 v53; // [rsp+40h] [rbp-79h]
  __int128 v54; // [rsp+48h] [rbp-71h] BYREF
  __int128 v55; // [rsp+58h] [rbp-61h]
  __int128 v56; // [rsp+68h] [rbp-51h] BYREF
  __int128 v57; // [rsp+78h] [rbp-41h]
  char *v58[4]; // [rsp+88h] [rbp-31h] BYREF
  int v59; // [rsp+A8h] [rbp-11h]
  _QWORD v60[2]; // [rsp+B0h] [rbp-9h] BYREF
  char *v61[4]; // [rsp+C0h] [rbp+7h] BYREF

  v50[0] = a2;
  *a3 = 0;
  v5 = (volatile signed __int32 *)a3[1];
  a3[1] = 0;
  if ( v5 )
  {
    if ( _InterlockedExchangeAdd(v5 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v5)(v5);
      if ( _InterlockedExchangeAdd(v5 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v5 + 8LL))(v5);
    }
  }
  v51 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
  v53 = a1 + 8;
  EnterCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  if ( ++*(_DWORD *)(a1 + 48) == 1 )
    *(_DWORD *)(a1 + 52) = GetCurrentThreadId();
  v52 = 1;
  v6 = *(_QWORD *)(a1 + 64);
  v7 = *(_QWORD *)(v6 + 8);
  HIDWORD(v54) = 0;
  v8 = v6;
  while ( !*(_BYTE *)(v7 + 25) )
  {
    if ( *(_DWORD *)(v7 + 28) >= v50[0] )
    {
      v9 = 0;
      v8 = v7;
    }
    else
    {
      v9 = 1;
    }
    v10 = (__int64 *)(v7 + 16);
    if ( !v9 )
      v10 = (__int64 *)v7;
    v7 = *v10;
  }
  if ( *(_BYTE *)(v8 + 25) || v50[0] < *(_DWORD *)(v8 + 28) )
    v8 = v6;
  if ( v6 == v8 )
  {
    std::string::string(v58, "AppV::Client::Host::SessionQueueImpl::GetQueueEntry");
    v59 = 173;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v11);
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v56,
      L"UserManager failed to lookup a session operation for unknown cookie %1%",
      0x47u);
    v13 = AppV::Log::fmt(v12, v60, &v56);
    v14 = AppV::LogFormatter::operator%<unsigned long>(v13, (__int64)v50);
    v54 = 0;
    v55 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v54, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v58, 1, (int)&v54, v14);
    std::wstring::~wstring((char **)&v54);
    v60[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v61);
    std::wstring::~wstring((char **)&v56);
    std::string::~string(v58);
    v15 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp", 92);
    if ( v15 )
      v16 = v15 + 1;
    else
      v16 = "admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v16);
    v18 = 0x150E00000305LL;
LABEL_23:
    v19 = v18 | (FileId << 52);
    v20 = (*(_DWORD *)(a1 + 48))-- == 1;
    if ( v20 )
      *(_DWORD *)(a1 + 52) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
    return v19;
  }
  v22 = (_DWORD *)(v8 + 32);
  v23 = *(__int64 **)(a1 + 80);
  v24 = (__int64 *)v23[1];
  HIDWORD(v54) = 0;
  for ( i = v23; !*((_BYTE *)v24 + 25); v24 = (__int64 *)*v24 )
  {
    if ( *((_DWORD *)v24 + 8) >= *v22 )
      i = v24;
    else
      v24 += 2;
  }
  if ( *((_BYTE *)i + 25) || *v22 < *((_DWORD *)i + 8) )
    i = v23;
  if ( v23 == i )
  {
    std::string::string(v58, "AppV::Client::Host::SessionQueueImpl::GetQueueEntry");
    v59 = 184;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v26);
    v54 = 0;
    v55 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v54,
      L"UserManager failed to lookup a session operation for cookie %2% matched to unknown session %1%",
      0x5Eu);
    v28 = AppV::Log::fmt(v27, v60, &v54);
    v29 = AppV::LogFormatter::operator%<unsigned long>(v28, (__int64)v22);
    v30 = AppV::LogFormatter::operator%<unsigned long>(v29, (__int64)v50);
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v56, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v58, 1, (int)&v56, v30);
    std::wstring::~wstring((char **)&v56);
    v60[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v61);
    std::wstring::~wstring((char **)&v54);
    std::string::~string(v58);
    v31 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp", 92);
    if ( v31 )
      v32 = v31 + 1;
    else
      v32 = "admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v32);
    v18 = 0x170E00000305LL;
    goto LABEL_23;
  }
  v33 = i[8];
  v34 = v33 + i[9];
  if ( i == (__int64 *)-40LL )
  {
    v35 = 0;
  }
  else
  {
    v35 = (__int64 *)i[5];
    if ( v35 )
    {
      v36 = *v35;
      goto LABEL_44;
    }
  }
  v36 = 0;
  while ( 1 )
  {
LABEL_44:
    if ( v34 == v33 )
      goto LABEL_48;
    if ( ***(_DWORD ***)(*(_QWORD *)(v36 + 8) + 8 * (v33 & (*(_QWORD *)(v36 + 16) - 1LL))) == v50[0] )
      break;
    ++v33;
  }
  if ( v34 == v33 )
  {
LABEL_48:
    std::string::string(v58, "AppV::Client::Host::SessionQueueImpl::GetQueueEntry");
    v59 = 196;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v37);
    v54 = 0;
    v55 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v54,
      L"UserManager failed to lookup a session operation for cookie %2% no longer queued for session %1%",
      0x60u);
    v39 = AppV::Log::fmt(v38, v60, &v54);
    v40 = AppV::LogFormatter::operator%<unsigned long>(v39, (__int64)v22);
    v41 = AppV::LogFormatter::operator%<unsigned long>(v40, (__int64)v50);
    v56 = 0;
    v57 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v56, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v58, 1, (int)&v56, v41);
    std::wstring::~wstring((char **)&v56);
    v60[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v61);
    std::wstring::~wstring((char **)&v54);
    std::string::~string(v58);
    v42 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp", 92);
    if ( v42 )
      v43 = v42 + 1;
    else
      v43 = "admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v43);
    v18 = 0x180E00000305LL;
    goto LABEL_23;
  }
  if ( v35 )
    v44 = *v35;
  else
    v44 = 0;
  v45 = *(__int64 **)(*(_QWORD *)(v44 + 8) + 8 * (v33 & (*(_QWORD *)(v44 + 16) - 1LL)));
  v46 = *v45;
  v47 = *(_QWORD *)(*v45 + 32);
  if ( v47 )
    _InterlockedIncrement((volatile signed __int32 *)(v47 + 8));
  v48 = *(_QWORD *)(v46 + 32);
  *a3 = *(_QWORD *)(v46 + 24);
  v49 = (volatile signed __int32 *)a3[1];
  a3[1] = v48;
  if ( v49 )
  {
    if ( _InterlockedExchangeAdd(v49 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(volatile signed __int32 *))v49)(v49);
      if ( _InterlockedExchangeAdd(v49 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v49 + 8LL))(v49);
    }
  }
  v20 = (*(_DWORD *)(a1 + 48))-- == 1;
  if ( v20 )
    *(_DWORD *)(a1 + 52) = 0;
  LeaveCriticalSection((LPCRITICAL_SECTION)(a1 + 8));
  return 0x8000000000LL;
}

```

## disassembly

```asm
0x140053e10  mov     [rsp-8+arg_0], rbx
0x140053e15  mov     [rsp-8+arg_18], rsi
0x140053e1a  push    rbp
0x140053e1b  push    rdi
0x140053e1c  push    r12
0x140053e1e  push    r14
0x140053e20  push    r15
0x140053e22  lea     rbp, [rsp-37h]
0x140053e27  sub     rsp, 0F0h
0x140053e2e  mov     rax, cs:__security_cookie
0x140053e35  xor     rax, rsp
0x140053e38  mov     [rbp+57h+var_30], rax
0x140053e3c  mov     rsi, r8
0x140053e3f  mov     r14, rcx
0x140053e42  mov     [rsp+110h+var_F0], edx
0x140053e46  xor     r15d, r15d
0x140053e49  mov     [r8], r15
0x140053e4c  mov     rbx, [r8+8]
0x140053e50  mov     [r8+8], r15
0x140053e54  or      r12d, 0FFFFFFFFh
0x140053e58  test    rbx, rbx
0x140053e5b  jz      short loc_140053E94
0x140053e5d  mov     eax, r12d
0x140053e60  lock xadd [rbx+8], eax
0x140053e65  add     eax, r12d
0x140053e68  jnz     short loc_140053E94
0x140053e6a  mov     rax, [rbx]
0x140053e6d  mov     rcx, rbx
0x140053e70  mov     rax, [rax]
0x140053e73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053e78  mov     eax, r12d
0x140053e7b  lock xadd [rbx+0Ch], eax
0x140053e80  add     eax, r12d
0x140053e83  jnz     short loc_140053E94
0x140053e85  mov     rax, [rbx]
0x140053e88  mov     rcx, rbx
0x140053e8b  mov     rax, [rax+8]
0x140053e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053e94  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x140053e9b  mov     [rsp+110h+var_E0], rax
0x140053ea0  lea     rdi, [r14+8]
0x140053ea4  mov     [rbp+57h+var_D0], rdi
0x140053ea8  mov     rcx, rdi; lpCriticalSection
0x140053eab  call    cs:__imp_EnterCriticalSection
0x140053eb1  inc     dword ptr [rdi+28h]
0x140053eb4  cmp     dword ptr [rdi+28h], 1
0x140053eb8  jnz     short loc_140053EC3
0x140053eba  call    cs:__imp_GetCurrentThreadId
0x140053ec0  mov     [rdi+2Ch], eax
0x140053ec3  mov     [rsp+110h+var_D8], 1
0x140053ec8  mov     r9, [r14+40h]
0x140053ecc  mov     rdx, [r9+8]
0x140053ed0  xor     eax, eax
0x140053ed2  mov     dword ptr [rbp+57h+var_C8+0Ch], eax
0x140053ed5  mov     r8, r9
0x140053ed8  mov     eax, [rsp+110h+var_F0]
0x140053edc  jmp     short loc_140053EFC
0x140053ede  cmp     [rdx+1Ch], eax
0x140053ee1  jnb     short loc_140053EE8
0x140053ee3  mov     r10b, 1
0x140053ee6  jmp     short loc_140053EEE
0x140053ee8  mov     r10b, r15b
0x140053eeb  mov     r8, rdx
0x140053eee  lea     rcx, [rdx+10h]
0x140053ef2  test    r10b, r10b
0x140053ef5  cmovz   rcx, rdx
0x140053ef9  mov     rdx, [rcx]
0x140053efc  cmp     [rdx+19h], r15b
0x140053f00  jz      short loc_140053EDE
0x140053f02  cmp     [r8+19h], r15b
0x140053f06  jnz     short loc_140053F0E
0x140053f08  cmp     eax, [r8+1Ch]
0x140053f0c  jnb     short loc_140053F11
0x140053f0e  mov     r8, r9
0x140053f11  cmp     r9, r8
0x140053f14  jnz     loc_140054049
0x140053f1a  lea     rdx, aAppvClientHost_5; "AppV::Client::Host::SessionQueueImpl::G"...
0x140053f21  lea     rcx, [rbp+57h+var_88]
0x140053f25  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140053f2a  mov     [rbp+57h+var_68], 0ADh
0x140053f31  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140053f36  xorps   xmm0, xmm0
0x140053f39  movups  [rbp+57h+var_A8], xmm0
0x140053f3d  xorps   xmm1, xmm1
0x140053f40  movdqu  [rbp+57h+var_98], xmm1
0x140053f45  mov     r8d, 47h ; 'G'
0x140053f4b  lea     rdx, aUsermanagerFai; "UserManager failed to lookup a session "...
0x140053f52  lea     rcx, [rbp+57h+var_A8]
0x140053f56  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140053f5b  nop
0x140053f5c  lea     r8, [rbp+57h+var_A8]
0x140053f60  lea     rdx, [rbp+57h+var_60]
0x140053f64  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140053f69  nop
0x140053f6a  lea     rdx, [rsp+110h+var_F0]
0x140053f6f  mov     rcx, rax
0x140053f72  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140053f77  mov     rbx, rax
0x140053f7a  xorps   xmm0, xmm0
0x140053f7d  movups  [rbp+57h+var_C8], xmm0
0x140053f81  xorps   xmm1, xmm1
0x140053f84  movdqu  [rbp+57h+var_B8], xmm1
0x140053f89  mov     r8d, 6
0x140053f8f  lea     rdx, aClient; "Client"
0x140053f96  lea     rcx, [rbp+57h+var_C8]
0x140053f9a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140053f9f  nop
0x140053fa0  mov     r9, rbx
0x140053fa3  lea     r8, [rbp+57h+var_C8]
0x140053fa7  mov     edx, 1
0x140053fac  lea     rcx, [rbp+57h+var_88]
0x140053fb0  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140053fb5  nop
0x140053fb6  lea     rcx, [rbp+57h+var_C8]
0x140053fba  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140053fbf  nop
0x140053fc0  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x140053fc7  mov     [rbp+57h+var_60], rax
0x140053fcb  lea     rcx, [rbp+57h+var_50]
0x140053fcf  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140053fd4  nop
0x140053fd5  lea     rcx, [rbp+57h+var_A8]
0x140053fd9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140053fde  nop
0x140053fdf  lea     rcx, [rbp+57h+var_88]
0x140053fe3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140053fe8  mov     edx, 5Ch ; '\'; Ch
0x140053fed  lea     rcx, aAdminAppmanApp_15; "admin\\appman\\appv\\client\\host\\comm"...
0x140053ff4  call    cs:__imp_strrchr
0x140053ffa  test    rax, rax
0x140053ffd  jz      short loc_140054004
0x140053fff  inc     rax
0x140054002  jmp     short loc_14005400B
0x140054004  lea     rax, aAdminAppmanApp_15; "admin\\appman\\appv\\client\\host\\comm"...
0x14005400b  mov     rdx, rax; char *
0x14005400e  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x140054015  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x14005401a  mov     rbx, rax
0x14005401d  mov     rax, 150E00000305h
0x140054027  shl     rbx, 34h
0x14005402b  or      rbx, rax
0x14005402e  add     [rdi+28h], r12d
0x140054032  jnz     short loc_140054038
0x140054034  mov     [rdi+2Ch], r15d
0x140054038  mov     rcx, rdi; lpCriticalSection
0x14005403b  call    cs:__imp_LeaveCriticalSection
0x140054041  mov     rax, rbx
0x140054044  jmp     loc_1400543C0
0x140054049  lea     rbx, [r8+20h]
0x14005404d  mov     r8, [r14+50h]
0x140054051  mov     rcx, [r8+8]
0x140054055  xor     edx, edx
0x140054057  mov     dword ptr [rbp+57h+var_C8+0Ch], edx
0x14005405a  mov     rdx, r8
0x14005405d  cmp     [rcx+19h], r15b
0x140054061  jnz     short loc_14005407E
0x140054063  mov     r9d, [rbx]
0x140054066  cmp     [rcx+20h], r9d
0x14005406a  jnb     short loc_140054072
0x14005406c  add     rcx, 10h
0x140054070  jmp     short loc_140054075
0x140054072  mov     rdx, rcx
0x140054075  mov     rcx, [rcx]
0x140054078  cmp     [rcx+19h], r15b
0x14005407c  jz      short loc_140054066
0x14005407e  cmp     [rdx+19h], r15b
0x140054082  jnz     short loc_14005408B
0x140054084  mov     ecx, [rdx+20h]
0x140054087  cmp     [rbx], ecx
0x140054089  jnb     short loc_14005408E
0x14005408b  mov     rdx, r8
0x14005408e  cmp     r8, rdx
0x140054091  jnz     loc_1400541B4
0x140054097  lea     rdx, aAppvClientHost_5; "AppV::Client::Host::SessionQueueImpl::G"...
0x14005409e  lea     rcx, [rbp+57h+var_88]
0x1400540a2  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400540a7  mov     [rbp+57h+var_68], 0B8h
0x1400540ae  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400540b3  xorps   xmm0, xmm0
0x1400540b6  movups  [rbp+57h+var_C8], xmm0
0x1400540ba  xorps   xmm1, xmm1
0x1400540bd  movdqu  [rbp+57h+var_B8], xmm1
0x1400540c2  mov     r8d, 5Eh ; '^'
0x1400540c8  lea     rdx, aUsermanagerFai_0; "UserManager failed to lookup a session "...
0x1400540cf  lea     rcx, [rbp+57h+var_C8]
0x1400540d3  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400540d8  nop
0x1400540d9  lea     r8, [rbp+57h+var_C8]
0x1400540dd  lea     rdx, [rbp+57h+var_60]
0x1400540e1  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400540e6  nop
0x1400540e7  mov     rdx, rbx
0x1400540ea  mov     rcx, rax
0x1400540ed  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400540f2  lea     rdx, [rsp+110h+var_F0]
0x1400540f7  mov     rcx, rax
0x1400540fa  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x1400540ff  mov     rbx, rax
0x140054102  xorps   xmm0, xmm0
0x140054105  movups  [rbp+57h+var_A8], xmm0
0x140054109  xorps   xmm1, xmm1
0x14005410c  movdqu  [rbp+57h+var_98], xmm1
0x140054111  mov     r8d, 6
0x140054117  lea     rdx, aClient; "Client"
0x14005411e  lea     rcx, [rbp+57h+var_A8]
0x140054122  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140054127  nop
0x140054128  mov     r9, rbx
0x14005412b  lea     r8, [rbp+57h+var_A8]
0x14005412f  mov     edx, 1
0x140054134  lea     rcx, [rbp+57h+var_88]
0x140054138  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x14005413d  nop
0x14005413e  lea     rcx, [rbp+57h+var_A8]
0x140054142  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140054147  nop
0x140054148  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x14005414f  mov     [rbp+57h+var_60], rax
0x140054153  lea     rcx, [rbp+57h+var_50]
0x140054157  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005415c  nop
0x14005415d  lea     rcx, [rbp+57h+var_C8]
0x140054161  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x140054166  nop
0x140054167  lea     rcx, [rbp+57h+var_88]
0x14005416b  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x140054170  mov     edx, 5Ch ; '\'; Ch
0x140054175  lea     rcx, aAdminAppmanApp_15; "admin\\appman\\appv\\client\\host\\comm"...
0x14005417c  call    cs:__imp_strrchr
0x140054182  test    rax, rax
0x140054185  jz      short loc_14005418C
0x140054187  inc     rax
0x14005418a  jmp     short loc_140054193
0x14005418c  lea     rax, aAdminAppmanApp_15; "admin\\appman\\appv\\client\\host\\comm"...
0x140054193  mov     rdx, rax; char *
0x140054196  lea     rcx, ?instance_@?$MeyersSingleton@VFileLookUp@AppV@@@@1VFileLookUp@AppV@@A; this
0x14005419d  call    ?getFileId@FileLookUp@AppV@@QEBA_KPEBD@Z; AppV::FileLookUp::getFileId(char const *)
0x1400541a2  mov     rbx, rax
0x1400541a5  mov     rax, 170E00000305h
0x1400541af  jmp     loc_140054027
0x1400541b4  lea     r9, [rdx+28h]
0x1400541b8  mov     r8, [r9+18h]
0x1400541bc  mov     r11, [r9+20h]
0x1400541c0  add     r11, r8
0x1400541c3  test    r9, r9
0x1400541c6  jz      short loc_1400541D5
0x1400541c8  mov     r9, [r9]
0x1400541cb  test    r9, r9
0x1400541ce  jz      short loc_1400541D8
0x1400541d0  mov     r10, [r9]
0x1400541d3  jmp     short loc_1400541DB
0x1400541d5  mov     r9, r15
0x1400541d8  mov     r10, r15
0x1400541db  cmp     r11, r8
0x1400541de  jz      short loc_140054207
0x1400541e0  mov     rdx, [r10+10h]
0x1400541e4  dec     rdx
0x1400541e7  and     rdx, r8
0x1400541ea  mov     rcx, [r10+8]
0x1400541ee  mov     rdx, [rcx+rdx*8]
0x1400541f2  mov     rcx, [rdx]
0x1400541f5  cmp     [rcx], eax
0x1400541f7  jz      short loc_1400541FE
0x1400541f9  inc     r8
0x1400541fc  jmp     short loc_1400541DB
0x1400541fe  cmp     r11, r8
0x140054201  jnz     loc_140054324
0x140054207  lea     rdx, aAppvClientHost_5; "AppV::Client::Host::SessionQueueImpl::G"...
0x14005420e  lea     rcx, [rbp+57h+var_88]
0x140054212  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x140054217  mov     [rbp+57h+var_68], 0C4h
0x14005421e  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140054223  xorps   xmm0, xmm0
0x140054226  movups  [rbp+57h+var_C8], xmm0
0x14005422a  xorps   xmm1, xmm1
0x14005422d  movdqu  [rbp+57h+var_B8], xmm1
0x140054232  mov     r8d, 60h ; '`'
0x140054238  lea     rdx, aUsermanagerFai_7; "UserManager failed to lookup a session "...
0x14005423f  lea     rcx, [rbp+57h+var_C8]
0x140054243  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140054248  nop
0x140054249  lea     r8, [rbp+57h+var_C8]
0x14005424d  lea     rdx, [rbp+57h+var_60]
0x140054251  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140054256  nop
0x140054257  mov     rdx, rbx
0x14005425a  mov     rcx, rax
0x14005425d  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140054262  lea     rdx, [rsp+110h+var_F0]
0x140054267  mov     rcx, rax
0x14005426a  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14005426f  mov     rbx, rax
0x140054272  xorps   xmm0, xmm0
0x140054275  movups  [rbp+57h+var_A8], xmm0
0x140054279  xorps   xmm1, xmm1
0x14005427c  movdqu  [rbp+57h+var_98], xmm1
0x140054281  mov     r8d, 6
0x140054287  lea     rdx, aClient; "Client"
0x14005428e  lea     rcx, [rbp+57h+var_A8]
0x140054292  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
  ... truncated ...
```
