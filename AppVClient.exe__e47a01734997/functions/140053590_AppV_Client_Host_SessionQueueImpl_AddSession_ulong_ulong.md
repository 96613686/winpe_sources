# AppV::Client::Host::SessionQueueImpl::AddSession(ulong,ulong &)

- ea: `0x140053590`
- end: `0x140053e05`
- name: `?AddSession@SessionQueueImpl@Host@Client@AppV@@UEAA_KKAEAK@Z`
- size: `2165`
- prototype: `unsigned __int64 __fastcall(AppV::Client::Host::SessionQueueImpl *__hidden this, unsigned int, unsigned int *)`
- caller_count: `0`
- callee_count: `18`
- tags: `broker_com_uri`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x1400060e8`
- `0x140006304`
- `0x140006438`
- `0x140006690`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x140018bec`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x1400508d4`
- `0x1400533f4`
- `0x140053590`
- `0x1400550cc`
- `0x14006a010`

## import_xrefs

- `KERNEL32!CreateEventW` at `0x140053633`
- `KERNEL32!CreateEventW` at `0x140053633`
- `KERNEL32!SetEvent` at `0x140053988`
- `KERNEL32!SetEvent` at `0x140053988`
- `KERNEL32!GetLastError` at `0x140053997`
- `KERNEL32!GetLastError` at `0x140053c6f`
- `KERNEL32!GetLastError` at `0x140053997`
- `KERNEL32!GetLastError` at `0x140053c6f`
- `KERNEL32!GetCurrentThreadId` at `0x1400537c7`
- `KERNEL32!GetCurrentThreadId` at `0x1400537c7`
- `KERNEL32!LeaveCriticalSection` at `0x140053bb1`
- `KERNEL32!LeaveCriticalSection` at `0x140053bb1`
- `KERNEL32!EnterCriticalSection` at `0x1400537b6`
- `KERNEL32!EnterCriticalSection` at `0x1400537b6`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140053d5e`
- `api-ms-win-crt-private-l1-1-0!strrchr` at `0x140053d5e`

## string_xrefs

- `0x140053d57`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140053d6e`: `admin\appman\appv\client\host\common\sessionqueueimpl.cpp`
- `0x140053caa`: `UserManager failed to create an event to synchronize operations for session %1% in the queue, error = %2%`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall AppV::Client::Host::SessionQueueImpl::AddSession(
        AppV::Client::Host::SessionQueueImpl *this,
        unsigned int a2,
        unsigned int *a3)
{
  _QWORD *v3; // rbx
  void *v4; // rdi
  HANDLE EventW; // rax
  int *v6; // r15
  void *v7; // r14
  volatile signed __int32 *v8; // rbx
  volatile signed __int32 *v9; // r12
  volatile signed __int32 *v10; // rbx
  AppV::Client::Host::SessionQueueImpl *v11; // rbx
  char *v12; // r13
  int v13; // ecx
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rax
  __int64 v18; // rbx
  __int64 v19; // rax
  _QWORD *v20; // rbx
  __int64 v21; // rdx
  _QWORD *v22; // rdx
  __int64 v23; // rcx
  __int64 v24; // rcx
  __int64 v25; // rax
  __int64 v26; // rax
  __int64 v27; // rax
  __int64 v28; // rbx
  __int64 v29; // rbx
  __int64 inserted; // rcx
  __int64 v31; // rax
  unsigned int v32; // r8d
  _DWORD *v33; // rax
  __int64 v36; // rcx
  __int64 v37; // rcx
  __int64 v38; // rax
  __int64 v39; // rax
  __int64 v40; // rbx
  char *v41; // rax
  const char *v42; // rax
  unsigned __int64 FileId; // rax
  __int64 v44; // rbx
  DWORD LastError; // [rsp+20h] [rbp-E0h] BYREF
  unsigned int v46; // [rsp+28h] [rbp-D8h] BYREF
  __int64 v47; // [rsp+30h] [rbp-D0h]
  AppV::Client::Host::SessionQueueImpl *v48; // [rsp+38h] [rbp-C8h]
  __int64 v49; // [rsp+40h] [rbp-C0h]
  __int128 v50; // [rsp+50h] [rbp-B0h] BYREF
  unsigned int *v51; // [rsp+60h] [rbp-A0h]
  _QWORD *v52; // [rsp+68h] [rbp-98h]
  void *v53; // [rsp+70h] [rbp-90h]
  void *v54; // [rsp+78h] [rbp-88h]
  void *v55; // [rsp+80h] [rbp-80h]
  __int128 v56; // [rsp+88h] [rbp-78h] BYREF
  __int64 v57; // [rsp+98h] [rbp-68h]
  __int64 v58; // [rsp+A0h] [rbp-60h]
  __int128 v59; // [rsp+A8h] [rbp-58h] BYREF
  __int64 v60; // [rsp+B8h] [rbp-48h]
  __int64 v61; // [rsp+C0h] [rbp-40h]
  char *v62[4]; // [rsp+C8h] [rbp-38h] BYREF
  int v63; // [rsp+E8h] [rbp-18h]
  __int128 v64; // [rsp+F0h] [rbp-10h] BYREF
  char *v65; // [rsp+100h] [rbp+0h]
  __int64 v66; // [rsp+108h] [rbp+8h]
  _QWORD v67[2]; // [rsp+110h] [rbp+10h] BYREF
  char *v68[4]; // [rsp+120h] [rbp+20h] BYREF

  v51 = a3;
  v48 = this;
  v46 = a2;
  v3 = operator new(8u);
  *v3 = 0;
  v4 = operator new(0x18u);
  *(_QWORD *)&v56 = v4;
  *(_OWORD *)v4 = 0;
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *(_QWORD *)v4 = &std::_Ref_count<softricity::shared::event>::`vftable';
  *((_QWORD *)v4 + 2) = v3;
  v52 = v3;
  v53 = v4;
  if ( *v3 || (EventW = CreateEventW(0, 1, 0, 0), (*v3 = EventW) != 0) )
  {
    v50 = 0;
    _InterlockedAdd((volatile signed __int32 *)v4 + 2, 1u);
    *(_QWORD *)&v56 = v3;
    *((_QWORD *)&v56 + 1) = v4;
    AppV::Client::Host::SessionQueueEntryFactory::CreateInstance(v46, &v56, &v50);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v4)(v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    v6 = (int *)operator new(0x28u);
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    *((_QWORD *)v6 + 3) = 0;
    *((_QWORD *)v6 + 4) = 0;
    *(_QWORD *)&v56 = v6;
    v7 = operator new(0x18u);
    *(_QWORD *)&v56 = v7;
    *(_OWORD *)v7 = 0;
    *((_DWORD *)v7 + 2) = 1;
    *((_DWORD *)v7 + 3) = 1;
    *(_QWORD *)v7 = &std::_Ref_count<AppV::Client::Host::SessionQueueImpl::SessionOperation>::`vftable';
    *((_QWORD *)v7 + 2) = v6;
    v54 = v6;
    v55 = v7;
    _InterlockedAdd((volatile signed __int32 *)v4 + 2, 1u);
    *((_QWORD *)v6 + 1) = v3;
    v8 = (volatile signed __int32 *)*((_QWORD *)v6 + 2);
    *((_QWORD *)v6 + 2) = v4;
    if ( v8 )
    {
      if ( _InterlockedExchangeAdd(v8 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v8)(v8);
        if ( _InterlockedExchangeAdd(v8 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v8 + 8LL))(v8);
      }
    }
    v9 = (volatile signed __int32 *)*((_QWORD *)&v50 + 1);
    if ( *((_QWORD *)&v50 + 1) )
      _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v50 + 1) + 8LL));
    *((_QWORD *)v6 + 3) = v50;
    v10 = (volatile signed __int32 *)*((_QWORD *)v6 + 4);
    *((_QWORD *)v6 + 4) = v9;
    if ( v10 )
    {
      if ( _InterlockedExchangeAdd(v10 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v10)(v10);
        if ( _InterlockedExchangeAdd(v10 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v10 + 8LL))(v10);
      }
    }
    *(_QWORD *)&v64 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
    v11 = v48;
    v12 = (char *)v48 + 8;
    v65 = (char *)v48 + 8;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)v48 + 8));
    ++*((_DWORD *)v48 + 12);
    if ( *((_DWORD *)v12 + 10) == 1 )
      *((_DWORD *)v12 + 11) = GetCurrentThreadId();
    BYTE8(v64) = 1;
    v13 = *((_DWORD *)v11 + 14);
    *((_DWORD *)v11 + 14) = v13 + 1;
    *v6 = v13;
    std::string::string(v62, "AppV::Client::Host::SessionQueueImpl::AddSession");
    v63 = 72;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v14);
    v56 = 0;
    v57 = 0;
    v58 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v56,
      L"UserManager is queuing an operation for session %1%, tracking cookie %2%",
      0x48u);
    v16 = AppV::Log::fmt(v15, v67, &v56);
    v17 = AppV::LogFormatter::operator%<unsigned long>(v16, (__int64)&v46);
    v18 = AppV::LogFormatter::operator%<unsigned long>(v17, (__int64)v6);
    v59 = 0;
    v60 = 0;
    v61 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v59, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v62, 4, (int)&v59, v18);
    std::wstring::~wstring((char **)&v59);
    v67[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v68);
    std::wstring::~wstring((char **)&v56);
    std::string::~string(v62);
    v19 = std::map<unsigned long,std::deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>>::operator[](
            (char *)v48 + 80,
            &v46);
    v20 = (_QWORD *)v19;
    if ( *(_QWORD *)(v19 + 16) <= (unsigned __int64)(*(_QWORD *)(v19 + 32) + 1LL) )
      std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Growmap(v19);
    v21 = v20[2] - 1LL;
    v20[3] &= v21;
    v47 = v20[3] + v20[4];
    v49 = v21 & v47;
    if ( !*(_QWORD *)(v20[1] + 8 * (v21 & v47)) )
      *(_QWORD *)(v20[1] + 8 * v49) = operator new(0x10u);
    v22 = *(_QWORD **)(v20[1] + 8 * (v47 & (v20[2] - 1LL)));
    *v22 = 0;
    v22[1] = 0;
    _InterlockedIncrement((volatile signed __int32 *)v7 + 2);
    *v22 = v6;
    v22[1] = v7;
    ++v20[4];
    if ( !SetEvent(**(HANDLE **)(**(_QWORD **)(v20[1] + 8 * (v20[3] & (v20[2] - 1LL))) + 8LL)) )
    {
      LastError = GetLastError();
      std::string::string(v62, "AppV::Client::Host::SessionQueueImpl::AddSession");
      v63 = 84;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v23);
      v56 = 0;
      v57 = 0;
      v58 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v56,
        L"UserManager failed to signal queued operation for session %1% with cookie %2%, error = %3%",
        0x5Au);
      v25 = AppV::Log::fmt(v24, v67, &v56);
      v26 = AppV::LogFormatter::operator%<unsigned long>(v25, (__int64)&v46);
      v27 = AppV::LogFormatter::operator%<unsigned long>(v26, **(_QWORD **)(v20[1] + 8 * (v20[3] & (v20[2] - 1LL))));
      v28 = AppV::LogFormatter::operator%<unsigned long>(v27, (__int64)&LastError);
      v59 = 0;
      v60 = 0;
      v61 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v59, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)v62, 2, (int)&v59, v28);
      std::wstring::~wstring((char **)&v59);
      v67[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v68);
      std::wstring::~wstring((char **)&v56);
      std::string::~string(v62);
    }
    LODWORD(v47) = v46;
    v29 = *((_QWORD *)v48 + 8);
    v49 = *(_QWORD *)(v29 + 8);
    LastError = 0;
    *(_QWORD *)&v56 = 0;
    inserted = v29;
    v31 = v49;
    if ( !*(_BYTE *)(v49 + 25) )
    {
      v32 = *v6;
      do
      {
        v49 = v31;
        if ( *(_DWORD *)(v31 + 28) >= v32 )
        {
          LastError = 1;
          inserted = v31;
          v31 = *(_QWORD *)v31;
        }
        else
        {
          LastError = 0;
          v31 = *(_QWORD *)(v31 + 16);
        }
      }
      while ( !*(_BYTE *)(v31 + 25) );
    }
    if ( *(_BYTE *)(inserted + 25) || (unsigned int)*v6 < *(_DWORD *)(inserted + 28) )
    {
      if ( *((_QWORD *)v48 + 9) == 0x666666666666666LL )
        std::_Throw_tree_length_error();
      v59 = (unsigned __int64)v48 + 64;
      v33 = operator new(0x28u);
      v33[7] = *v6;
      v33[8] = 0;
      *(_QWORD *)v33 = v29;
      *((_QWORD *)v33 + 1) = v29;
      *((_QWORD *)v33 + 2) = v29;
      *((_WORD *)v33 + 12) = 0;
      *(_QWORD *)&v50 = v49;
      *((_QWORD *)&v50 + 1) = __PAIR64__(v56, LastError);
      inserted = std::_Tree_val<std::_Tree_simple_types<std::pair<unsigned long const,std::deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>>>>::_Insert_node(
                   (char *)v48 + 64,
                   &v50,
                   v33);
    }
    *(_DWORD *)(inserted + 32) = v47;
    *v51 = *v6;
    if ( (*((_DWORD *)v12 + 10))-- == 1 )
      *((_DWORD *)v12 + 11) = 0;
    LeaveCriticalSection((LPCRITICAL_SECTION)v12);
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v7)(v7);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v7 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v7 + 8LL))(v7);
    }
    if ( v9 )
    {
      if ( _InterlockedExchangeAdd(v9 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(volatile signed __int32 *))v9)(v9);
        if ( _InterlockedExchangeAdd(v9 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v9 + 8LL))(v9);
      }
    }
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v4)(v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    return 0x8000000000LL;
  }
  else
  {
    LastError = GetLastError();
    std::string::string(v62, "AppV::Client::Host::SessionQueueImpl::AddSession");
    v63 = 55;
    AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v36);
    v59 = 0;
    v60 = 0;
    v61 = 0;
    std::wstring::_Construct<1,wchar_t const *>(
      (char **)&v59,
      L"UserManager failed to create an event to synchronize operations for session %1% in the queue, error = %2%",
      0x69u);
    v38 = AppV::Log::fmt(v37, v67, &v59);
    v39 = AppV::LogFormatter::operator%<unsigned long>(v38, (__int64)&v46);
    v40 = AppV::LogFormatter::operator%<unsigned long>(v39, (__int64)&LastError);
    v64 = 0;
    v65 = 0;
    v66 = 0;
    std::wstring::_Construct<1,wchar_t const *>((char **)&v64, L"Client", 6u);
    AppV::DecoratedLog::operator()((char *)v62, 1, (int)&v64, v40);
    std::wstring::~wstring((char **)&v64);
    v67[0] = &AppV::LogFormatter::`vftable';
    std::wstring::~wstring(v68);
    std::wstring::~wstring((char **)&v59);
    std::string::~string(v62);
    v41 = strrchr("admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp", 92);
    if ( v41 )
      v42 = v41 + 1;
    else
      v42 = "admin\\appman\\appv\\client\\host\\common\\sessionqueueimpl.cpp";
    FileId = AppV::FileLookUp::getFileId((AppV::FileLookUp *)&MeyersSingleton<AppV::FileLookUp>::instance_, v42);
    v44 = LastError | (FileId << 52) | 0x72E00000000LL;
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 2, 0xFFFFFFFF) == 1 )
    {
      (**(void (__fastcall ***)(void *))v4)(v4);
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v4 + 3, 0xFFFFFFFF) == 1 )
        (*(void (__fastcall **)(void *))(*(_QWORD *)v4 + 8LL))(v4);
    }
    return v44;
  }
}

```

## disassembly

```asm
0x140053590  mov     [rsp-8+arg_18], rbx
0x140053595  push    rbp
0x140053596  push    rsi
0x140053597  push    rdi
0x140053598  push    r12
0x14005359a  push    r13
0x14005359c  push    r14
0x14005359e  push    r15
0x1400535a0  lea     rbp, [rsp-50h]
0x1400535a5  sub     rsp, 150h
0x1400535ac  mov     rax, cs:__security_cookie
0x1400535b3  xor     rax, rsp
0x1400535b6  mov     [rbp+80h+var_40], rax
0x1400535ba  mov     [rsp+180h+var_120], r8
0x1400535bf  mov     [rsp+180h+var_148], rcx
0x1400535c4  mov     [rsp+180h+var_158], edx
0x1400535c8  mov     ecx, 8; Size
0x1400535cd  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400535d2  mov     rbx, rax
0x1400535d5  mov     qword ptr [rbp+80h+var_F8], rax
0x1400535d9  xor     r13d, r13d
0x1400535dc  mov     [rax], r13
0x1400535df  mov     qword ptr [rbp+80h+var_F8], rax
0x1400535e3  lea     r14d, [r13+18h]
0x1400535e7  mov     ecx, r14d; Size
0x1400535ea  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400535ef  mov     rdi, rax
0x1400535f2  mov     qword ptr [rbp+80h+var_F8], rax
0x1400535f6  xorps   xmm0, xmm0
0x1400535f9  movups  xmmword ptr [rax], xmm0
0x1400535fc  lea     r12d, [r13+1]
0x140053600  mov     [rax+8], r12d
0x140053604  mov     [rax+0Ch], r12d
0x140053608  lea     rax, ??_7?$_Ref_count@Vevent@shared@softricity@@@std@@6B@; const std::_Ref_count<softricity::shared::event>::`vftable'
0x14005360f  mov     [rdi], rax
0x140053612  mov     [rdi+10h], rbx
0x140053616  mov     [rsp+180h+var_118], rbx
0x14005361b  mov     [rsp+180h+var_110], rdi
0x140053620  mov     rax, [rbx]
0x140053623  test    rax, rax
0x140053626  jnz     short loc_140053645
0x140053628  xor     r9d, r9d; lpName
0x14005362b  xor     r8d, r8d; bInitialState
0x14005362e  mov     edx, r12d; bManualReset
0x140053631  xor     ecx, ecx; lpEventAttributes
0x140053633  call    cs:__imp_CreateEventW
0x140053639  mov     [rbx], rax
0x14005363c  test    rax, rax
0x14005363f  jz      loc_140053C6F
0x140053645  xorps   xmm0, xmm0
0x140053648  movdqu  [rsp+180h+var_130], xmm0
0x14005364e  lock add [rdi+8], r12d
0x140053653  mov     qword ptr [rbp+80h+var_F8], rbx
0x140053657  mov     qword ptr [rbp+80h+var_F8+8], rdi
0x14005365b  lea     r8, [rsp+180h+var_130]
0x140053660  lea     rdx, [rbp+80h+var_F8]
0x140053664  mov     ecx, [rsp+180h+var_158]
0x140053668  call    ?CreateInstance@SessionQueueEntryFactory@Host@Client@AppV@@SAXKAEBV?$shared_ptr@$$CBVevent@shared@softricity@@@std@@AEAV?$shared_ptr@VSessionQueueEntry@Host@Client@AppV@@@6@@Z; AppV::Client::Host::SessionQueueEntryFactory::CreateInstance(ulong,std::shared_ptr<softricity::shared::event const> const &,std::shared_ptr<AppV::Client::Host::SessionQueueEntry> &)
0x14005366d  nop
0x14005366e  or      esi, 0FFFFFFFFh
0x140053671  mov     eax, esi
0x140053673  lock xadd [rdi+8], eax
0x140053678  add     eax, esi
0x14005367a  jnz     short loc_1400536A4
0x14005367c  mov     rax, [rdi]
0x14005367f  mov     rcx, rdi
0x140053682  mov     rax, [rax]
0x140053685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005368a  mov     eax, esi
0x14005368c  lock xadd [rdi+0Ch], eax
0x140053691  add     eax, esi
0x140053693  jnz     short loc_1400536A4
0x140053695  mov     rax, [rdi]
0x140053698  mov     rcx, rdi
0x14005369b  mov     rax, [rax+8]
0x14005369f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400536a4  mov     ecx, 28h ; '('; Size
0x1400536a9  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400536ae  mov     r15, rax
0x1400536b1  mov     [rax+8], r13
0x1400536b5  mov     [rax+10h], r13
0x1400536b9  mov     [rax+18h], r13
0x1400536bd  mov     [rax+20h], r13
0x1400536c1  mov     qword ptr [rbp+80h+var_F8], rax
0x1400536c5  mov     rcx, r14; Size
0x1400536c8  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400536cd  mov     r14, rax
0x1400536d0  mov     qword ptr [rbp+80h+var_F8], rax
0x1400536d4  xorps   xmm0, xmm0
0x1400536d7  movups  xmmword ptr [rax], xmm0
0x1400536da  mov     [rax+8], r12d
0x1400536de  mov     [rax+0Ch], r12d
0x1400536e2  lea     rax, ??_7?$_Ref_count@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@6B@; const std::_Ref_count<AppV::Client::Host::SessionQueueImpl::SessionOperation>::`vftable'
0x1400536e9  mov     [r14], rax
0x1400536ec  mov     [r14+10h], r15
0x1400536f0  mov     [rsp+180h+var_108], r15
0x1400536f5  mov     [rbp+80h+var_100], r14
0x1400536f9  lock add [rdi+8], r12d
0x1400536fe  mov     [r15+8], rbx
0x140053702  mov     rbx, [r15+10h]
0x140053706  mov     [r15+10h], rdi
0x14005370a  test    rbx, rbx
0x14005370d  jz      short loc_140053742
0x14005370f  mov     eax, esi
0x140053711  lock xadd [rbx+8], eax
0x140053716  add     eax, esi
0x140053718  jnz     short loc_140053742
0x14005371a  mov     rax, [rbx]
0x14005371d  mov     rcx, rbx
0x140053720  mov     rax, [rax]
0x140053723  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053728  mov     eax, esi
0x14005372a  lock xadd [rbx+0Ch], eax
0x14005372f  add     eax, esi
0x140053731  jnz     short loc_140053742
0x140053733  mov     rax, [rbx]
0x140053736  mov     rcx, rbx
0x140053739  mov     rax, [rax+8]
0x14005373d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053742  mov     r12, qword ptr [rsp+180h+var_130+8]
0x140053747  test    r12, r12
0x14005374a  jz      short loc_140053752
0x14005374c  lock inc dword ptr [r12+8]
0x140053752  mov     rax, qword ptr [rsp+180h+var_130]
0x140053757  mov     [r15+18h], rax
0x14005375b  mov     rbx, [r15+20h]
0x14005375f  mov     [r15+20h], r12
0x140053763  test    rbx, rbx
0x140053766  jz      short loc_14005379B
0x140053768  mov     eax, esi
0x14005376a  lock xadd [rbx+8], eax
0x14005376f  add     eax, esi
0x140053771  jnz     short loc_14005379B
0x140053773  mov     rax, [rbx]
0x140053776  mov     rcx, rbx
0x140053779  mov     rax, [rax]
0x14005377c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140053781  mov     eax, esi
0x140053783  lock xadd [rbx+0Ch], eax
0x140053788  add     eax, esi
0x14005378a  jnz     short loc_14005379B
0x14005378c  mov     rax, [rbx]
0x14005378f  mov     rcx, rbx
0x140053792  mov     rax, [rax+8]
0x140053796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005379b  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x1400537a2  mov     qword ptr [rbp+80h+var_90], rax
0x1400537a6  mov     rbx, [rsp+180h+var_148]
0x1400537ab  lea     r13, [rbx+8]
0x1400537af  mov     [rbp+80h+var_80], r13
0x1400537b3  mov     rcx, r13; lpCriticalSection
0x1400537b6  call    cs:__imp_EnterCriticalSection
0x1400537bc  inc     dword ptr [r13+28h]
0x1400537c0  cmp     dword ptr [r13+28h], 1
0x1400537c5  jnz     short loc_1400537D1
0x1400537c7  call    cs:__imp_GetCurrentThreadId
0x1400537cd  mov     [r13+2Ch], eax
0x1400537d1  mov     byte ptr [rbp+80h+var_90+8], 1
0x1400537d5  mov     ecx, [rbx+38h]
0x1400537d8  lea     eax, [rcx+1]
0x1400537db  mov     [rbx+38h], eax
0x1400537de  mov     [r15], ecx
0x1400537e1  lea     rdx, aAppvClientHost_13; "AppV::Client::Host::SessionQueueImpl::A"...
0x1400537e8  lea     rcx, [rbp+80h+var_B8]
0x1400537ec  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400537f1  mov     ebx, 48h ; 'H'
0x1400537f6  mov     [rbp+80h+var_98], ebx
0x1400537f9  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400537fe  xorps   xmm0, xmm0
0x140053801  movups  [rbp+80h+var_F8], xmm0
0x140053805  mov     [rbp+80h+var_E8], 0
0x14005380d  mov     [rbp+80h+var_E0], 0
0x140053815  mov     r8d, ebx
0x140053818  lea     rdx, aUsermanagerIsQ; "UserManager is queuing an operation for"...
0x14005381f  lea     rcx, [rbp+80h+var_F8]
0x140053823  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x140053828  nop
0x140053829  lea     r8, [rbp+80h+var_F8]
0x14005382d  lea     rdx, [rbp+80h+var_70]
0x140053831  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x140053836  nop
0x140053837  lea     rdx, [rsp+180h+var_158]
0x14005383c  mov     rcx, rax
0x14005383f  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140053844  mov     rdx, r15
0x140053847  mov     rcx, rax
0x14005384a  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x14005384f  mov     rbx, rax
0x140053852  xorps   xmm0, xmm0
0x140053855  movups  [rbp+80h+var_D8], xmm0
0x140053859  mov     [rbp+80h+var_C8], 0
0x140053861  mov     [rbp+80h+var_C0], 0
0x140053869  mov     r8d, 6
0x14005386f  lea     rdx, aClient; "Client"
0x140053876  lea     rcx, [rbp+80h+var_D8]
0x14005387a  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005387f  nop
0x140053880  mov     r9, rbx
0x140053883  lea     r8, [rbp+80h+var_D8]
0x140053887  mov     edx, 4
0x14005388c  lea     rcx, [rbp+80h+var_B8]
0x140053890  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x140053895  nop
0x140053896  lea     rcx, [rbp+80h+var_D8]
0x14005389a  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x14005389f  nop
0x1400538a0  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400538a7  mov     [rbp+80h+var_70], rax
0x1400538ab  lea     rcx, [rbp+80h+var_60]
0x1400538af  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400538b4  nop
0x1400538b5  lea     rcx, [rbp+80h+var_F8]
0x1400538b9  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400538be  nop
0x1400538bf  lea     rcx, [rbp+80h+var_B8]
0x1400538c3  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400538c8  mov     rcx, [rsp+180h+var_148]
0x1400538cd  add     rcx, 50h ; 'P'
0x1400538d1  lea     rdx, [rsp+180h+var_158]
0x1400538d6  call    ??A?$map@KV?$deque@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@@2@@std@@U?$less@K@2@V?$allocator@U?$pair@$$CBKV?$deque@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@@2@@std@@@std@@@2@@std@@QEAAAEAV?$deque@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@USessionOperation@SessionQueueImpl@Host@Client@AppV@@@std@@@2@@1@AEBK@Z; std::map<ulong,std::deque<std::shared_ptr<AppV::Client::Host::SessionQueueImpl::SessionOperation>>>::operator[](ulong const &)
0x1400538db  mov     rbx, rax
0x1400538de  mov     rcx, [rax+20h]
0x1400538e2  inc     rcx
0x1400538e5  cmp     [rax+10h], rcx
0x1400538e9  ja      short loc_1400538F3
0x1400538eb  mov     rcx, rax
0x1400538ee  call    ?_Growmap@?$deque@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@2@@std@@AEAAX_K@Z; std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Growmap(unsigned __int64)
0x1400538f3  mov     rdx, [rbx+10h]
0x1400538f7  dec     rdx
0x1400538fa  and     [rbx+18h], rdx
0x1400538fe  mov     rax, [rbx+20h]
0x140053902  add     rax, [rbx+18h]
0x140053906  mov     [rsp+180h+var_150], rax
0x14005390b  mov     rcx, rax
0x14005390e  and     rcx, rdx
0x140053911  mov     [rsp+180h+var_140], rcx
0x140053916  mov     rax, [rbx+8]
0x14005391a  cmp     qword ptr [rax+rcx*8], 0
0x14005391f  jnz     short loc_140053938
0x140053921  mov     ecx, 10h; Size
0x140053926  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14005392b  mov     rcx, [rbx+8]
0x14005392f  mov     rdx, [rsp+180h+var_140]
0x140053934  mov     [rcx+rdx*8], rax
0x140053938  mov     rcx, [rbx+10h]
0x14005393c  dec     rcx
0x14005393f  and     rcx, [rsp+180h+var_150]
0x140053944  mov     rax, [rbx+8]
0x140053948  mov     rdx, [rax+rcx*8]
0x14005394c  mov     qword ptr [rdx], 0
0x140053953  mov     qword ptr [rdx+8], 0
0x14005395b  lock inc dword ptr [r14+8]
0x140053960  mov     [rdx], r15
0x140053963  mov     [rdx+8], r14
0x140053967  inc     qword ptr [rbx+20h]
0x14005396b  mov     rcx, [rbx+10h]
0x14005396f  dec     rcx
0x140053972  and     rcx, [rbx+18h]
0x140053976  mov     rax, [rbx+8]
0x14005397a  mov     rcx, [rax+rcx*8]
0x14005397e  mov     rax, [rcx]
0x140053981  mov     rcx, [rax+8]
0x140053985  mov     rcx, [rcx]; hEvent
0x140053988  call    cs:__imp_SetEvent
0x14005398e  cmp     eax, 1
0x140053991  jz      loc_140053AAA
0x140053997  call    cs:__imp_GetLastError
0x14005399d  mov     [rsp+180h+var_160], eax
0x1400539a1  lea     rdx, aAppvClientHost_13; "AppV::Client::Host::SessionQueueImpl::A"...
0x1400539a8  lea     rcx, [rbp+80h+var_B8]
0x1400539ac  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x1400539b1  mov     [rbp+80h+var_98], 54h ; 'T'
0x1400539b8  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x1400539bd  xorps   xmm0, xmm0
0x1400539c0  movups  [rbp+80h+var_F8], xmm0
0x1400539c4  mov     [rbp+80h+var_E8], 0
0x1400539cc  mov     [rbp+80h+var_E0], 0
0x1400539d4  mov     r8d, 5Ah ; 'Z'
0x1400539da  lea     rdx, aUsermanagerFai_6; "UserManager failed to signal queued ope"...
0x1400539e1  lea     rcx, [rbp+80h+var_F8]
0x1400539e5  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x1400539ea  nop
0x1400539eb  lea     r8, [rbp+80h+var_F8]
0x1400539ef  lea     rdx, [rbp+80h+var_70]
0x1400539f3  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x1400539f8  nop
0x1400539f9  lea     rdx, [rsp+180h+var_158]
0x1400539fe  mov     rcx, rax
0x140053a01  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140053a06  mov     rdx, [rbx+10h]
0x140053a0a  dec     rdx
0x140053a0d  and     rdx, [rbx+18h]
0x140053a11  mov     rcx, [rbx+8]
0x140053a15  mov     rdx, [rcx+rdx*8]
0x140053a19  mov     rdx, [rdx]
0x140053a1c  mov     rcx, rax
0x140053a1f  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140053a24  lea     rdx, [rsp+180h+var_160]
0x140053a29  mov     rcx, rax
0x140053a2c  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
  ... truncated ...
```
