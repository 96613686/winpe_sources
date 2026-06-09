# AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::SubscriberProc(void *)

- ea: `0x1400500a0`
- end: `0x140050822`
- name: `?SubscriberProc@?$SubscriberImpl@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@VEnterpriseWorkerStateManager@345@@Host@Client@AppV@@SAIPEAX@Z`
- size: `1922`
- prototype: ``
- caller_count: `0`
- callee_count: `17`
- tags: `file_ops`

## callees

- `0x140004280`
- `0x1400042a4`
- `0x140004558`
- `0x1400060e8`
- `0x140006304`
- `0x140006a08`
- `0x140008e64`
- `0x140010158`
- `0x14003c034`
- `0x14003c414`
- `0x14003c660`
- `0x140046c58`
- `0x14004dc8c`
- `0x14004ec48`
- `0x1400500a0`
- `0x140050aa8`
- `0x14006a010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x1400501f1`
- `KERNEL32!SetEvent` at `0x1400501f1`
- `KERNEL32!WaitForMultipleObjects` at `0x140050421`
- `KERNEL32!WaitForMultipleObjects` at `0x140050421`
- `KERNEL32!GetLastError` at `0x140050200`
- `KERNEL32!GetLastError` at `0x140050600`
- `KERNEL32!GetLastError` at `0x140050200`
- `KERNEL32!GetLastError` at `0x140050600`
- `KERNEL32!GetCurrentThreadId` at `0x14005045b`
- `KERNEL32!GetCurrentThreadId` at `0x14005045b`
- `KERNEL32!WaitForSingleObject` at `0x140050533`
- `KERNEL32!WaitForSingleObject` at `0x140050533`
- `KERNEL32!LeaveCriticalSection` at `0x140050513`
- `KERNEL32!LeaveCriticalSection` at `0x140050513`
- `KERNEL32!EnterCriticalSection` at `0x14005044a`
- `KERNEL32!EnterCriticalSection` at `0x14005044a`
- `ole32!CoUninitialize` at `0x140050161`
- `ole32!CoUninitialize` at `0x1400507fa`
- `ole32!CoUninitialize` at `0x140050161`
- `ole32!CoUninitialize` at `0x1400507fa`
- `ole32!CoInitializeEx` at `0x1400500ed`
- `ole32!CoInitializeEx` at `0x1400500ed`

## string_xrefs

- `0x14005023c`: `A Client event delivery thread failed to signal that it was ready, error = %1%`
- `0x14005063b`: `A Client event delivery thread failed to wait on the signals for next actions and exited prematurely, error = %1%`

## pseudocode

```c
// Hidden C++ exception states: #wind=14
__int64 __fastcall AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::SubscriberProc(
        __int64 a1)
{
  DWORD v3; // edi
  __int64 v4; // rax
  __int64 v5; // r13
  volatile signed __int32 *v6; // rsi
  __int64 v7; // rax
  HANDLE *v8; // rdi
  volatile signed __int32 *v9; // r14
  __int64 v10; // rax
  volatile signed __int32 *v11; // r15
  __int64 v12; // rax
  volatile signed __int32 *v13; // r12
  __int64 v14; // rcx
  __int64 v15; // rcx
  __int64 v16; // rax
  __int64 v17; // rbx
  DWORD v18; // ebx
  bool v19; // zf
  DWORD v20; // eax
  __int64 v21; // rbx
  void ***v22; // rax
  __int64 v23; // rsi
  __int64 v24; // r14
  __int64 v25; // rax
  HANDLE *v26; // rsi
  __int64 v27; // rcx
  volatile signed __int32 *v28; // rbx
  void *v29; // rcx
  __int64 v30; // rcx
  __int64 v31; // rcx
  __int64 v32; // rax
  __int64 v33; // rbx
  DWORD LastError; // [rsp+20h] [rbp-E0h] BYREF
  char v35; // [rsp+24h] [rbp-DCh] BYREF
  __int64 v36; // [rsp+28h] [rbp-D8h] BYREF
  int v37; // [rsp+30h] [rbp-D0h] BYREF
  bool v38; // [rsp+34h] [rbp-CCh]
  HRESULT v39; // [rsp+38h] [rbp-C8h]
  void **v40; // [rsp+40h] [rbp-C0h] BYREF
  int v41; // [rsp+48h] [rbp-B8h]
  char v42; // [rsp+4Ch] [rbp-B4h]
  __int128 v43; // [rsp+50h] [rbp-B0h]
  __int64 v44; // [rsp+60h] [rbp-A0h]
  HANDLE *v45; // [rsp+68h] [rbp-98h]
  void **v46; // [rsp+70h] [rbp-90h]
  __int64 v47; // [rsp+78h] [rbp-88h]
  volatile signed __int32 *v48; // [rsp+80h] [rbp-80h]
  HANDLE Handles[3]; // [rsp+88h] [rbp-78h] BYREF
  volatile signed __int32 *v50; // [rsp+A0h] [rbp-60h]
  __int64 v51; // [rsp+A8h] [rbp-58h]
  volatile signed __int32 *v52; // [rsp+B0h] [rbp-50h]
  HANDLE *v53; // [rsp+B8h] [rbp-48h]
  volatile signed __int32 *v54; // [rsp+C0h] [rbp-40h]
  void *Block[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v56; // [rsp+D8h] [rbp-28h]
  __int64 v57; // [rsp+E0h] [rbp-20h]
  __int64 v58; // [rsp+E8h] [rbp-18h]
  __int128 v59; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v60; // [rsp+100h] [rbp+0h]
  __int64 v61; // [rsp+108h] [rbp+8h]
  __int128 v62; // [rsp+110h] [rbp+10h] BYREF
  __int64 v63; // [rsp+120h] [rbp+20h]
  __int64 v64; // [rsp+128h] [rbp+28h]
  _QWORD v65[2]; // [rsp+130h] [rbp+30h] BYREF
  char *v66[4]; // [rsp+140h] [rbp+40h] BYREF

  if ( !a1 )
    return 87;
  v37 = 0;
  v39 = CoInitializeEx(0, 0);
  v38 = v39 >= 0;
  v40 = &AppV::Client::Impersonator::`vftable';
  v41 = 0;
  v42 = 0;
  v43 = 0;
  v3 = AppV::Client::Host::EnterpriseWorkerStateManager::Initialize(&v37, a1);
  LastError = v3;
  if ( v3 )
  {
    if ( *((_QWORD *)&v43 + 1) )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v43 + 1) + 16LL))(*((_QWORD *)&v43 + 1));
    AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v40);
    if ( v38 )
      CoUninitialize();
    return v3;
  }
  else
  {
    v4 = *(_QWORD *)(a1 + 24);
    if ( v4 )
      _InterlockedIncrement((volatile signed __int32 *)(v4 + 8));
    v5 = *(_QWORD *)(a1 + 16);
    v47 = v5;
    v6 = *(volatile signed __int32 **)(a1 + 24);
    v48 = v6;
    v7 = *(_QWORD *)(a1 + 40);
    if ( v7 )
      _InterlockedIncrement((volatile signed __int32 *)(v7 + 8));
    v8 = *(HANDLE **)(a1 + 32);
    Handles[2] = v8;
    v9 = *(volatile signed __int32 **)(a1 + 40);
    v50 = v9;
    v10 = *(_QWORD *)(a1 + 56);
    if ( v10 )
      _InterlockedIncrement((volatile signed __int32 *)(v10 + 8));
    v44 = *(_QWORD *)(a1 + 48);
    v51 = v44;
    v11 = *(volatile signed __int32 **)(a1 + 56);
    v52 = v11;
    v12 = *(_QWORD *)(a1 + 72);
    if ( v12 )
      _InterlockedIncrement((volatile signed __int32 *)(v12 + 8));
    v45 = *(HANDLE **)(a1 + 64);
    v53 = v45;
    v13 = *(volatile signed __int32 **)(a1 + 72);
    v54 = v13;
    if ( SetEvent(*(HANDLE *)(a1 + 8)) )
    {
      LastError = 0;
      Handles[0] = *v45;
      Handles[1] = *v8;
      while ( 1 )
      {
        v20 = WaitForMultipleObjects(2u, Handles, 0, 0xFFFFFFFF);
        if ( !v20 )
          break;
        if ( v20 != 1 )
        {
          LastError = GetLastError();
          std::string::string(
            Block,
            "AppV::Client::Host::SubscriberImpl<struct IAppVClientEventSink,long,struct AppV::Client::Host::EnterpriseDel"
            "iveryParameters,class AppV::Client::Host::EnterpriseWorkerStateManager>::SubscriberProc");
          LODWORD(v58) = 567;
          AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v30);
          v62 = 0;
          v63 = 0;
          v64 = 0;
          std::wstring::_Construct<1,wchar_t const *>(
            (char **)&v62,
            L"A Client event delivery thread failed to wait on the signals for next actions and exited prematurely, error = %1%",
            0x71u);
          v32 = AppV::Log::fmt(v31, v65, &v62);
          v33 = AppV::LogFormatter::operator%<unsigned long>(v32, (__int64)&LastError);
          v59 = 0;
          v60 = 0;
          v61 = 0;
          std::wstring::_Construct<1,wchar_t const *>((char **)&v59, L"Client", 6u);
          AppV::DecoratedLog::operator()((char *)Block, 1, (int)&v59, v33);
          std::wstring::~wstring((char **)&v59);
          v65[0] = &AppV::LogFormatter::`vftable';
          std::wstring::~wstring(v66);
          std::wstring::~wstring((char **)&v62);
          std::string::~string((char **)Block);
          break;
        }
        *(_QWORD *)&v59 = &softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable';
        v60 = v5;
        EnterCriticalSection((LPCRITICAL_SECTION)v5);
        if ( ++*(_DWORD *)(v5 + 40) == 1 )
          *(_DWORD *)(v5 + 44) = GetCurrentThreadId();
        BYTE8(v59) = 1;
        *(_OWORD *)Block = 0;
        v56 = 0;
        v57 = 0;
        v58 = 0;
        v21 = *(_QWORD *)(v44 + 24);
        v36 = v21 + *(_QWORD *)(v44 + 32);
        *((_QWORD *)&v62 + 1) = &v35;
        v22 = (void ***)operator new(0x10u);
        *(_QWORD *)&v62 = v22;
        *v22 = Block;
        v22[1] = 0;
        Block[0] = v22;
        v46 = Block;
        v23 = v44;
        v24 = v36;
        while ( v21 != v24 )
          std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Emplace_back_internal<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &>(
            Block,
            *(_QWORD *)(*(_QWORD *)(v23 + 8) + 8 * (v21++ & (*(_QWORD *)(v23 + 16) - 1LL))));
        *(_QWORD *)&v62 = 0;
        std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Tidy(v23);
        v19 = (*(_DWORD *)(v5 + 40))-- == 1;
        v9 = v50;
        if ( v19 )
          *(_DWORD *)(v5 + 44) = 0;
        LeaveCriticalSection((LPCRITICAL_SECTION)v5);
        BYTE8(v59) = 0;
        v25 = v58;
        v26 = v45;
        while ( v25 && WaitForSingleObject(*v26, 0) )
        {
          v27 = **((_QWORD **)Block[1] + (v57 & (v56 - 1)));
          (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v27 + 8LL))(v27, *((_QWORD *)&v43 + 1));
          v28 = *(volatile signed __int32 **)(*((_QWORD *)Block[1] + (v57 & (v56 - 1))) + 8LL);
          if ( v28 )
          {
            if ( _InterlockedExchangeAdd(v28 + 2, 0xFFFFFFFF) == 1 )
            {
              (**(void (__fastcall ***)(volatile signed __int32 *))v28)(v28);
              if ( _InterlockedExchangeAdd(v28 + 3, 0xFFFFFFFF) == 1 )
                (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v28 + 8LL))(v28);
            }
          }
          v25 = --v58;
          if ( v58 )
            ++v57;
          else
            v57 = 0;
        }
        std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Tidy(Block);
        v29 = Block[0];
        Block[0] = 0;
        operator delete(v29);
        v6 = v48;
      }
      v18 = LastError;
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
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
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      if ( *((_QWORD *)&v43 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v43 + 1) + 16LL))(*((_QWORD *)&v43 + 1));
      AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v40);
      v19 = !v38;
    }
    else
    {
      LODWORD(v36) = GetLastError();
      std::string::string(
        Block,
        "AppV::Client::Host::SubscriberImpl<struct IAppVClientEventSink,long,struct AppV::Client::Host::EnterpriseDeliver"
        "yParameters,class AppV::Client::Host::EnterpriseWorkerStateManager>::SubscriberProc");
      LODWORD(v58) = 525;
      AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(v14);
      v62 = 0;
      v63 = 0;
      v64 = 0;
      std::wstring::_Construct<1,wchar_t const *>(
        (char **)&v62,
        L"A Client event delivery thread failed to signal that it was ready, error = %1%",
        0x4Eu);
      v16 = AppV::Log::fmt(v15, v65, &v62);
      v17 = AppV::LogFormatter::operator%<unsigned long>(v16, (__int64)&v36);
      v59 = 0;
      v60 = 0;
      v61 = 0;
      std::wstring::_Construct<1,wchar_t const *>((char **)&v59, L"Client", 6u);
      AppV::DecoratedLog::operator()((char *)Block, 1, (int)&v59, v17);
      std::wstring::~wstring((char **)&v59);
      v65[0] = &AppV::LogFormatter::`vftable';
      std::wstring::~wstring(v66);
      std::wstring::~wstring((char **)&v62);
      std::string::~string((char **)Block);
      v18 = v36;
      if ( v13 )
      {
        if ( _InterlockedExchangeAdd(v13 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v13)(v13);
          if ( _InterlockedExchangeAdd(v13 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v13 + 8LL))(v13);
        }
      }
      if ( v11 )
      {
        if ( _InterlockedExchangeAdd(v11 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v11)(v11);
          if ( _InterlockedExchangeAdd(v11 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v11 + 8LL))(v11);
        }
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
      if ( v6 )
      {
        if ( _InterlockedExchangeAdd(v6 + 2, 0xFFFFFFFF) == 1 )
        {
          (**(void (__fastcall ***)(volatile signed __int32 *))v6)(v6);
          if ( _InterlockedExchangeAdd(v6 + 3, 0xFFFFFFFF) == 1 )
            (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)v6 + 8LL))(v6);
        }
      }
      if ( *((_QWORD *)&v43 + 1) )
        (*(void (__fastcall **)(_QWORD))(**((_QWORD **)&v43 + 1) + 16LL))(*((_QWORD *)&v43 + 1));
      AppV::Client::Impersonator::~Impersonator((AppV::Client::Impersonator *)&v40);
      v19 = !v38;
    }
    if ( !v19 )
      CoUninitialize();
    return v18;
  }
}

```

## disassembly

```asm
0x1400500a0  push    rbp
0x1400500a2  push    rbx
0x1400500a3  push    rsi
0x1400500a4  push    rdi
0x1400500a5  push    r12
0x1400500a7  push    r13
0x1400500a9  push    r14
0x1400500ab  push    r15
0x1400500ad  lea     rbp, [rsp-78h]
0x1400500b2  sub     rsp, 178h
0x1400500b9  mov     rax, cs:__security_cookie
0x1400500c0  xor     rax, rsp
0x1400500c3  mov     [rbp+0B0h+var_50], rax
0x1400500c7  mov     rbx, rcx
0x1400500ca  xor     r12d, r12d
0x1400500cd  test    rcx, rcx
0x1400500d0  jnz     short loc_1400500DA
0x1400500d2  lea     eax, [rcx+57h]
0x1400500d5  jmp     loc_140050802
0x1400500da  mov     [rsp+1B0h+var_180], r12d
0x1400500df  mov     [rsp+1B0h+var_17C], r12b
0x1400500e4  mov     [rsp+1B0h+var_178], r12d
0x1400500e9  xor     edx, edx; dwCoInit
0x1400500eb  xor     ecx, ecx; pvReserved
0x1400500ed  call    cs:__imp_CoInitializeEx
0x1400500f3  mov     [rsp+1B0h+var_178], eax
0x1400500f7  test    eax, eax
0x1400500f9  js      short loc_140050100
0x1400500fb  mov     [rsp+1B0h+var_17C], 1
0x140050100  lea     rax, ??_7Impersonator@Client@AppV@@6B@; const AppV::Client::Impersonator::`vftable'
0x140050107  mov     [rsp+1B0h+var_170], rax
0x14005010c  mov     [rsp+1B0h+var_168], r12d
0x140050111  mov     [rsp+1B0h+var_164], r12b
0x140050116  xorps   xmm0, xmm0
0x140050119  movdqu  [rsp+1B0h+var_160], xmm0
0x14005011f  mov     rdx, rbx
0x140050122  lea     rcx, [rsp+1B0h+var_180]
0x140050127  call    ?Initialize@EnterpriseWorkerStateManager@Host@Client@AppV@@QEAAKPEAVWorkerStartupData@?$SubscriberImpl@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@VEnterpriseWorkerStateManager@345@@234@@Z; AppV::Client::Host::EnterpriseWorkerStateManager::Initialize(AppV::Client::Host::SubscriberImpl<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters,AppV::Client::Host::EnterpriseWorkerStateManager>::WorkerStartupData *)
0x14005012c  mov     edi, eax
0x14005012e  mov     [rsp+1B0h+var_190], eax
0x140050132  test    eax, eax
0x140050134  jz      short loc_14005016E
0x140050136  mov     rdx, qword ptr [rsp+1B0h+var_160+8]
0x14005013b  test    rdx, rdx
0x14005013e  jz      short loc_140050150
0x140050140  mov     rcx, [rdx]
0x140050143  mov     rax, [rcx+10h]
0x140050147  mov     rcx, rdx
0x14005014a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005014f  nop
0x140050150  lea     rcx, [rsp+1B0h+var_170]; this
0x140050155  call    ??1Impersonator@Client@AppV@@UEAA@XZ; AppV::Client::Impersonator::~Impersonator(void)
0x14005015a  cmp     [rsp+1B0h+var_17C], r12b
0x14005015f  jz      short loc_140050167
0x140050161  call    cs:__imp_CoUninitialize
0x140050167  mov     eax, edi
0x140050169  jmp     loc_140050802
0x14005016e  mov     rax, [rbx+18h]
0x140050172  test    rax, rax
0x140050175  jz      short loc_14005017B
0x140050177  lock inc dword ptr [rax+8]
0x14005017b  mov     r13, [rbx+10h]
0x14005017f  mov     [rsp+1B0h+var_138], r13
0x140050184  mov     rsi, [rbx+18h]
0x140050188  mov     [rbp+0B0h+var_130], rsi
0x14005018c  mov     rax, [rbx+28h]
0x140050190  test    rax, rax
0x140050193  jz      short loc_140050199
0x140050195  lock inc dword ptr [rax+8]
0x140050199  mov     rdi, [rbx+20h]
0x14005019d  mov     [rbp+0B0h+var_118], rdi
0x1400501a1  mov     r14, [rbx+28h]
0x1400501a5  mov     [rbp+0B0h+var_110], r14
0x1400501a9  mov     rax, [rbx+38h]
0x1400501ad  test    rax, rax
0x1400501b0  jz      short loc_1400501B6
0x1400501b2  lock inc dword ptr [rax+8]
0x1400501b6  mov     rax, [rbx+30h]
0x1400501ba  mov     [rsp+1B0h+var_150], rax
0x1400501bf  mov     [rbp+0B0h+var_108], rax
0x1400501c3  mov     r15, [rbx+38h]
0x1400501c7  mov     [rbp+0B0h+var_100], r15
0x1400501cb  mov     rax, [rbx+48h]
0x1400501cf  test    rax, rax
0x1400501d2  jz      short loc_1400501D8
0x1400501d4  lock inc dword ptr [rax+8]
0x1400501d8  mov     rax, [rbx+40h]
0x1400501dc  mov     [rsp+1B0h+var_148], rax
0x1400501e1  mov     [rbp+0B0h+var_F8], rax
0x1400501e5  mov     r12, [rbx+48h]
0x1400501e9  mov     [rbp+0B0h+var_F0], r12
0x1400501ed  mov     rcx, [rbx+8]; hEvent
0x1400501f1  call    cs:__imp_SetEvent
0x1400501f7  cmp     eax, 1
0x1400501fa  jz      loc_1400503F6
0x140050200  call    cs:__imp_GetLastError
0x140050206  mov     dword ptr [rsp+1B0h+var_188], eax
0x14005020a  lea     rdx, aAppvClientHost_30; "AppV::Client::Host::SubscriberImpl<stru"...
0x140050211  lea     rcx, [rbp+0B0h+Block]
0x140050215  call    ??0?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@QEBD@Z; std::string::string(char const * const)
0x14005021a  mov     dword ptr [rbp+0B0h+var_C8], 20Dh
0x140050221  call    ?Instance@?$LoggerSingleton@VLog@AppV@@V12@@AppV@@SAPEAVLog@2@XZ; AppV::LoggerSingleton<AppV::Log,AppV::Log>::Instance(void)
0x140050226  xorps   xmm0, xmm0
0x140050229  movups  [rbp+0B0h+var_A0], xmm0
0x14005022d  xor     r13d, r13d
0x140050230  mov     [rbp+0B0h+var_90], r13
0x140050234  mov     [rbp+0B0h+var_88], r13
0x140050238  lea     r8d, [r13+4Eh]
0x14005023c  lea     rdx, aAClientEventDe_0; "A Client event delivery thread failed t"...
0x140050243  lea     rcx, [rbp+0B0h+var_A0]
0x140050247  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005024c  nop
0x14005024d  lea     r8, [rbp+0B0h+var_A0]
0x140050251  lea     rdx, [rbp+0B0h+var_80]
0x140050255  call    ?fmt@Log@AppV@@QEAA?AVLogFormatter@2@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@@Z; AppV::Log::fmt(std::wstring const &)
0x14005025a  nop
0x14005025b  lea     rdx, [rsp+1B0h+var_188]
0x140050260  mov     rcx, rax
0x140050263  call    ??$?LK@LogFormatter@AppV@@QEAAAEAV01@AEAK@Z; AppV::LogFormatter::operator%<ulong>(ulong &)
0x140050268  mov     rbx, rax
0x14005026b  xorps   xmm0, xmm0
0x14005026e  movups  [rbp+0B0h+var_C0], xmm0
0x140050272  mov     [rbp+0B0h+var_B0], r13
0x140050276  mov     [rbp+0B0h+var_A8], r13
0x14005027a  lea     r8d, [r13+6]
0x14005027e  lea     rdx, aClient; "Client"
0x140050285  lea     rcx, [rbp+0B0h+var_C0]
0x140050289  call    ??$_Construct@$00PEB_W@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXQEB_W_K@Z; std::wstring::_Construct<1,wchar_t const *>(wchar_t const * const,unsigned __int64)
0x14005028e  nop
0x14005028f  mov     r9, rbx
0x140050292  lea     r8, [rbp+0B0h+var_C0]
0x140050296  lea     edx, [r13+1]
0x14005029a  lea     rcx, [rbp+0B0h+Block]
0x14005029e  call    ??RDecoratedLog@AppV@@QEBAXW4APPV_LOG_LEVEL@1@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAVLogFormatter@1@@Z; AppV::DecoratedLog::operator()(AppV::APPV_LOG_LEVEL,std::wstring const &,AppV::LogFormatter &)
0x1400502a3  nop
0x1400502a4  lea     rcx, [rbp+0B0h+var_C0]
0x1400502a8  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400502ad  nop
0x1400502ae  lea     rax, ??_7LogFormatter@AppV@@6B@; const AppV::LogFormatter::`vftable'
0x1400502b5  mov     [rbp+0B0h+var_80], rax
0x1400502b9  lea     rcx, [rbp+0B0h+var_70]
0x1400502bd  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400502c2  nop
0x1400502c3  lea     rcx, [rbp+0B0h+var_A0]
0x1400502c7  call    ??1?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x1400502cc  nop
0x1400502cd  lea     rcx, [rbp+0B0h+Block]
0x1400502d1  call    ??1?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAA@XZ; std::string::~string(void)
0x1400502d6  mov     ebx, dword ptr [rsp+1B0h+var_188]
0x1400502da  or      edi, 0FFFFFFFFh
0x1400502dd  test    r12, r12
0x1400502e0  jz      short loc_14005031C
0x1400502e2  mov     eax, edi
0x1400502e4  lock xadd [r12+8], eax
0x1400502eb  add     eax, edi
0x1400502ed  jnz     short loc_14005031C
0x1400502ef  mov     rax, [r12]
0x1400502f3  mov     rcx, r12
0x1400502f6  mov     rax, [rax]
0x1400502f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400502fe  mov     eax, edi
0x140050300  lock xadd [r12+0Ch], eax
0x140050307  add     eax, edi
0x140050309  jnz     short loc_14005031C
0x14005030b  mov     rax, [r12]
0x14005030f  mov     rcx, r12
0x140050312  mov     rax, [rax+8]
0x140050316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005031b  nop
0x14005031c  test    r15, r15
0x14005031f  jz      short loc_140050357
0x140050321  mov     eax, edi
0x140050323  lock xadd [r15+8], eax
0x140050329  add     eax, edi
0x14005032b  jnz     short loc_140050357
0x14005032d  mov     rax, [r15]
0x140050330  mov     rcx, r15
0x140050333  mov     rax, [rax]
0x140050336  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14005033b  mov     eax, edi
0x14005033d  lock xadd [r15+0Ch], eax
0x140050343  add     eax, edi
0x140050345  jnz     short loc_140050357
0x140050347  mov     rax, [r15]
0x14005034a  mov     rcx, r15
0x14005034d  mov     rax, [rax+8]
0x140050351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050356  nop
0x140050357  test    r14, r14
0x14005035a  jz      short loc_140050392
0x14005035c  mov     eax, edi
0x14005035e  lock xadd [r14+8], eax
0x140050364  add     eax, edi
0x140050366  jnz     short loc_140050392
0x140050368  mov     rax, [r14]
0x14005036b  mov     rcx, r14
0x14005036e  mov     rax, [rax]
0x140050371  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050376  mov     eax, edi
0x140050378  lock xadd [r14+0Ch], eax
0x14005037e  add     eax, edi
0x140050380  jnz     short loc_140050392
0x140050382  mov     rax, [r14]
0x140050385  mov     rcx, r14
0x140050388  mov     rax, [rax+8]
0x14005038c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140050391  nop
0x140050392  test    rsi, rsi
0x140050395  jz      short loc_1400503CB
0x140050397  mov     eax, edi
0x140050399  lock xadd [rsi+8], eax
0x14005039e  add     eax, edi
0x1400503a0  jnz     short loc_1400503CB
0x1400503a2  mov     rax, [rsi]
0x1400503a5  mov     rcx, rsi
0x1400503a8  mov     rax, [rax]
0x1400503ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400503b0  mov     eax, edi
0x1400503b2  lock xadd [rsi+0Ch], eax
0x1400503b7  add     eax, edi
0x1400503b9  jnz     short loc_1400503CB
0x1400503bb  mov     rax, [rsi]
0x1400503be  mov     rcx, rsi
0x1400503c1  mov     rax, [rax+8]
0x1400503c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400503ca  nop
0x1400503cb  mov     rcx, qword ptr [rsp+1B0h+var_160+8]
0x1400503d0  test    rcx, rcx
0x1400503d3  jz      short loc_1400503E2
0x1400503d5  mov     rax, [rcx]
0x1400503d8  mov     rax, [rax+10h]
0x1400503dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400503e1  nop
0x1400503e2  lea     rcx, [rsp+1B0h+var_170]; this
0x1400503e7  call    ??1Impersonator@Client@AppV@@UEAA@XZ; AppV::Client::Impersonator::~Impersonator(void)
0x1400503ec  cmp     [rsp+1B0h+var_17C], r13b
0x1400503f1  jmp     loc_1400507F8
0x1400503f6  xor     ebx, ebx
0x1400503f8  mov     [rsp+1B0h+var_190], ebx
0x1400503fc  mov     rax, [rsp+1B0h+var_148]
0x140050401  mov     rax, [rax]
0x140050404  mov     [rbp+0B0h+Handles], rax
0x140050408  mov     rax, [rdi]
0x14005040b  mov     [rbp+0B0h+var_120], rax
0x14005040f  or      edi, 0FFFFFFFFh
0x140050412  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x140050416  xor     r8d, r8d; bWaitAll
0x140050419  lea     rdx, [rbp+0B0h+Handles]; lpHandles
0x14005041d  lea     ecx, [r8+2]; nCount
0x140050421  call    cs:__imp_WaitForMultipleObjects
0x140050427  test    eax, eax
0x140050429  jz      loc_1400506E0
0x14005042f  cmp     eax, 1
0x140050432  jnz     loc_140050600
0x140050438  lea     rax, ??_7?$lock_holder@Vcritical_section@shared@softricity@@@shared@softricity@@6B@; const softricity::shared::lock_holder<softricity::shared::critical_section>::`vftable'
0x14005043f  mov     qword ptr [rbp+0B0h+var_C0], rax
0x140050443  mov     [rbp+0B0h+var_B0], r13
0x140050447  mov     rcx, r13; lpCriticalSection
0x14005044a  call    cs:__imp_EnterCriticalSection
0x140050450  inc     dword ptr [r13+28h]
0x140050454  cmp     dword ptr [r13+28h], 1
0x140050459  jnz     short loc_140050465
0x14005045b  call    cs:__imp_GetCurrentThreadId
0x140050461  mov     [r13+2Ch], eax
0x140050465  mov     byte ptr [rbp+0B0h+var_C0+8], 1
0x140050469  xorps   xmm0, xmm0
0x14005046c  movdqu  xmmword ptr [rbp+0B0h+Block], xmm0
0x140050471  mov     [rbp+0B0h+var_D8], rbx
0x140050475  mov     [rbp+0B0h+var_D0], rbx
0x140050479  mov     [rbp+0B0h+var_C8], rbx
0x14005047d  mov     rax, [rsp+1B0h+var_150]
0x140050482  mov     rbx, [rax+18h]
0x140050486  mov     rax, [rax+20h]
0x14005048a  add     rax, rbx
0x14005048d  mov     [rsp+1B0h+var_188], rax
0x140050492  lea     rax, [rsp+1B0h+var_18C]
0x140050497  mov     qword ptr [rbp+0B0h+var_A0+8], rax
0x14005049b  mov     ecx, 10h; Size
0x1400504a0  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1400504a5  mov     qword ptr [rbp+0B0h+var_A0], rax
0x1400504a9  lea     rcx, [rbp+0B0h+Block]
0x1400504ad  mov     [rax], rcx
0x1400504b0  mov     qword ptr [rax+8], 0
0x1400504b8  mov     [rbp+0B0h+Block], rax
0x1400504bc  lea     rax, [rbp+0B0h+Block]
0x1400504c0  mov     [rsp+1B0h+var_140], rax
0x1400504c5  mov     rsi, [rsp+1B0h+var_150]
0x1400504ca  mov     r14, [rsp+1B0h+var_188]
0x1400504cf  cmp     rbx, r14
0x1400504d2  jz      short loc_1400504F4
0x1400504d4  mov     rax, [rsi+10h]
0x1400504d8  dec     rax
0x1400504db  and     rax, rbx
0x1400504de  mov     rdx, [rsi+8]
0x1400504e2  mov     rdx, [rdx+rax*8]
0x1400504e6  lea     rcx, [rbp+0B0h+Block]
0x1400504ea  call    ??$_Emplace_back_internal@AEBV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@?$deque@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@V?$allocator@V?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@std@@@2@@std@@AEAAXAEBV?$shared_ptr@VEventCall@?$Subscriber@UIAppVClientEventSink@@JUEnterpriseDeliveryParameters@Host@Client@AppV@@@Host@Client@AppV@@@1@@Z; std::deque<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall>>::_Emplace_back_internal<std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &>(std::shared_ptr<AppV::Client::Host::Subscriber<IAppVClientEventSink,long,AppV::Client::Host::EnterpriseDeliveryParameters>::EventCall> const &)
0x1400504ef  inc     rbx
0x1400504f2  jmp     short loc_1400504CF
0x1400504f4  xor     ebx, ebx
  ... truncated ...
```
