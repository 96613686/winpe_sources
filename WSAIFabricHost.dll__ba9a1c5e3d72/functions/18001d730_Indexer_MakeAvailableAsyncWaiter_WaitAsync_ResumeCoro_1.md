# Indexer::MakeAvailableAsyncWaiter::WaitAsync$_ResumeCoro$1

- ea: `0x18001d730`
- end: `0x18001dc60`
- name: `Indexer::MakeAvailableAsyncWaiter::WaitAsync$_ResumeCoro$1`
- size: `1328`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001d710`
- `0x18001dc68`

## callees

- `0x180005140`
- `0x1800058d7`
- `0x180007f72`
- `0x1800082a9`
- `0x180009cf0`
- `0x18000c018`
- `0x18000c478`
- `0x180014688`
- `0x1800189b8`
- `0x180018fa0`
- `0x18001a10c`
- `0x18001a420`
- `0x18001d730`
- `0x18001de54`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d7cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d966`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d7cc`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001d966`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d879`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dafa`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001d879`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18001dafa`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d9b9`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18001d9b9`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d7f1`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18001d7f1`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001da46`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001daa9`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001da46`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x18001daa9`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001d97b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001d99c`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001d97b`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18001d99c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d7a6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockShared` at `0x18001d7a6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d7bb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockShared` at `0x18001d7bb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001d806`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001da21`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d841`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001da71`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001d841`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001da71`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d816`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18001d816`
- `msvcp_win!_Thrd_yield` at `0x18001d8c7`
- `msvcp_win!_Thrd_yield` at `0x18001d951`
- `msvcp_win!_Thrd_yield` at `0x18001d8c7`
- `msvcp_win!_Thrd_yield` at `0x18001d951`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001dc04`
- `msvcp_win!?__ExceptionPtrDestroy@@YAXPEAX@Z` at `0x18001dc04`

## string_xrefs

- `0x18001d828`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`
- `0x18001d9c3`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001d9ec`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001da50`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001dab3`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001dade`: `onecore\internal\sdk\inc\wil\opensource/wil/resource.h`
- `0x18001d861`: `onecoreuap\base\appmodel\search\common\aifabrichosthelper\lib\dependencymanager.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall Indexer::MakeAvailableAsyncWaiter::WaitAsync__ResumeCoro_1(char *a1)
{
  _WORD *v3; // r12
  bool v4; // bl
  HANDLE EventW; // rbx
  HANDLE v6; // r15
  const char *v7; // r9
  _BYTE *v8; // rbx
  _QWORD *v9; // r15
  struct _TP_WAIT *v10; // rcx
  volatile __int64 *v11; // rbx
  const struct winrt::impl::slim_source_location *v12; // rax
  struct _TP_WAIT *v13; // rcx
  volatile __int64 *v14; // rbx
  HANDLE v15; // rbx
  DWORD v16; // eax
  const char *v17; // r9
  const char *v18; // r9
  HANDLE v19; // r15
  HANDLE *v20; // rbx
  _QWORD *v21; // rcx
  const char *v22; // r9
  const char *v23; // r9
  const struct winrt::impl::slim_source_location *v24; // rax
  int v25; // [rsp+20h] [rbp-C8h]
  _BYTE pExceptionObject[24]; // [rsp+70h] [rbp-78h] BYREF
  _BYTE v27[96]; // [rsp+88h] [rbp-60h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]
  DWORD dwErrCode; // [rsp+F8h] [rbp+10h]
  DWORD dwErrCodea; // [rsp+F8h] [rbp+10h]
  HANDLE hEvent; // [rsp+100h] [rbp+18h]

  v3 = a1 + 136;
  LOWORD(v25) = *((_WORD *)a1 + 68);
  switch ( (__int16)v25 )
  {
    case -1:
    case 1:
    case 3:
      goto LABEL_53;
    case 2:
      AcquireSRWLockShared(&Indexer::MakeAvailableAsyncWaiter::m_lock);
      v4 = Indexer::MakeAvailableAsyncWaiter::m_waitEvent != 0;
      ReleaseSRWLockShared(&Indexer::MakeAvailableAsyncWaiter::m_lock);
      if ( !v4 )
      {
        AcquireSRWLockExclusive(&Indexer::MakeAvailableAsyncWaiter::m_lock);
        *((_QWORD *)a1 + 18) = &Indexer::MakeAvailableAsyncWaiter::m_lock;
        if ( !Indexer::MakeAvailableAsyncWaiter::m_waitEvent )
        {
          EventW = CreateEventW(0, 1, 1, 0);
          v6 = Indexer::MakeAvailableAsyncWaiter::m_waitEvent;
          if ( Indexer::MakeAvailableAsyncWaiter::m_waitEvent )
          {
            dwErrCode = GetLastError();
            if ( !CloseHandle(v6) )
              wil::details::in1diag3::_FailFast_GetLastError(
                retaddr,
                (void *)0xA0B,
                (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
                v7);
            SetLastError(dwErrCode);
          }
          Indexer::MakeAvailableAsyncWaiter::m_waitEvent = EventW;
          if ( !EventW )
            wil::details::in1diag3::Throw_Hr(
              retaddr,
              (void *)0x24,
              (unsigned int)"onecoreuap\\base\\appmodel\\search\\common\\aifabrichosthelper\\lib\\dependencymanager.cpp",
              (const char *)0x80004005LL,
              v25);
        }
        ReleaseSRWLockExclusive(&Indexer::MakeAvailableAsyncWaiter::m_lock);
      }
      v8 = a1 + 152;
      a1[152] = 1;
      v9 = a1 + 160;
      goto LABEL_47;
    case 4:
      goto LABEL_19;
    case 5:
      v10 = (struct _TP_WAIT *)*((_QWORD *)a1 + 21);
      if ( v10 )
      {
        CloseThreadpoolWait_0(v10);
        *((_QWORD *)a1 + 21) = 0;
      }
      v11 = (volatile __int64 *)*((_QWORD *)a1 + 20);
      if ( v11 )
      {
        while ( _InterlockedExchange64(v11, 0) == 1 )
          _Thrd_yield();
      }
      goto LABEL_53;
    default:
      __debugbreak();
      return;
  }
  while ( 1 )
  {
LABEL_19:
    if ( _InterlockedExchange((volatile __int32 *)a1 + 52, 0) == 2 )
    {
      v12 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 256);
      winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)pExceptionObject, v12);
      throw (winrt::hresult_canceled *)pExceptionObject;
    }
    v13 = (struct _TP_WAIT *)*((_QWORD *)a1 + 21);
    if ( v13 )
    {
      CloseThreadpoolWait_0(v13);
      *((_QWORD *)a1 + 21) = 0;
    }
    v9 = a1 + 160;
    v14 = (volatile __int64 *)*((_QWORD *)a1 + 20);
    if ( v14 )
    {
      while ( _InterlockedExchange64(v14, 0) == 1 )
        _Thrd_yield();
    }
    AcquireSRWLockExclusive(&Indexer::MakeAvailableAsyncWaiter::m_lock);
    v15 = Indexer::MakeAvailableAsyncWaiter::m_waitEvent;
    v16 = WaitForSingleObjectEx(Indexer::MakeAvailableAsyncWaiter::m_waitEvent, 0, 0);
    if ( v16 == 258 )
    {
      v8 = a1 + 152;
    }
    else
    {
      if ( v16 || WaitForSingleObjectEx(v15, 0, 0) )
        wil::details::in1diag3::FailFast_Unexpected(
          retaddr,
          (void *)0xB07,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v17);
      if ( !ResetEvent(Indexer::MakeAvailableAsyncWaiter::m_waitEvent) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA06,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v18);
      v19 = Indexer::MakeAvailableAsyncWaiter::m_waitEvent;
      if ( !Indexer::MakeAvailableAsyncWaiter::m_waitEvent )
        wil::details::in1diag3::FailFast_Unexpected(
          retaddr,
          (void *)0xAF3,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v18);
      v20 = (HANDLE *)*((_QWORD *)a1 + 16);
      v21 = a1 + 216;
      if ( v20 != (HANDLE *)(a1 + 216) )
      {
        hEvent = *v20;
        if ( *v20 )
        {
          dwErrCodea = GetLastError();
          if ( !SetEvent(hEvent) )
            wil::details::in1diag3::_FailFast_GetLastError(
              retaddr,
              (void *)0xA01,
              (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
              v22);
          SetLastError(dwErrCodea);
          v21 = a1 + 216;
        }
        *v20 = v19;
        v19 = 0;
      }
      *v21 = v19;
      v8 = a1 + 152;
      a1[152] = 0;
      if ( v19 && !SetEvent(v19) )
        wil::details::in1diag3::_FailFast_GetLastError(
          retaddr,
          (void *)0xA01,
          (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource/wil/resource.h",
          v23);
      v9 = a1 + 160;
    }
    ReleaseSRWLockExclusive(&Indexer::MakeAvailableAsyncWaiter::m_lock);
LABEL_47:
    if ( !*v8 )
      break;
    *v9 = 0;
    *((_QWORD *)a1 + 21) = 0;
    *((_QWORD *)a1 + 22) = 0;
    *((_QWORD *)a1 + 23) = Indexer::MakeAvailableAsyncWaiter::m_waitEvent;
    *((_DWORD *)a1 + 48) = 0;
    *((_QWORD *)a1 + 25) = 0;
    *((_DWORD *)a1 + 52) = 0;
    if ( *((_DWORD *)a1 + 28) == 2 )
    {
      v24 = (const struct winrt::impl::slim_source_location *)winrt::impl::slim_source_location::current(a1 + 232);
      winrt::hresult_canceled::hresult_canceled((winrt::hresult_canceled *)v27, v24);
      throw (winrt::hresult_canceled *)v27;
    }
    if ( WaitForSingleObject_0(*((HANDLE *)a1 + 23), 0) )
    {
      *v3 = 4;
      winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Indexer::MakeAvailableAsyncWaiter &>::promise_type>(
        v9,
        a1);
      return;
    }
  }
  *((_QWORD *)a1 + 28) = a1 + 16;
  *v3 = 0;
  *(_QWORD *)a1 = 0;
  if ( !(unsigned __int8)winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,enum winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
  {
LABEL_53:
    if ( *((_QWORD *)a1 + 13) )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 104);
    if ( *((_QWORD *)a1 + 12) )
      winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(a1 + 96);
    __ExceptionPtrDestroy(a1 + 72);
    winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(a1 + 16);
    if ( *((_WORD *)a1 + 69) )
      operator delete(a1, 0x120u);
  }
}

```

## disassembly

```asm
0x18001d730  mov     rax, rsp
0x18001d733  mov     [rax+8], rcx
0x18001d737  push    rbx
0x18001d738  push    rsi
0x18001d739  push    rdi
0x18001d73a  push    r12
0x18001d73c  push    r13
0x18001d73e  push    r14
0x18001d740  push    r15
0x18001d742  sub     rsp, 0B0h
0x18001d749  mov     rsi, rcx
0x18001d74c  mov     r13, rcx
0x18001d74f  mov     [rsp+0E8h+var_B8], rcx
0x18001d754  lea     r12, [rsi+88h]
0x18001d75b  movzx   eax, word ptr [r12]
0x18001d760  mov     word ptr [rsp+0E8h+var_C8], ax; int
0x18001d765  mov     r15d, 1
0x18001d76b  add     ax, r15w
0x18001d76f  cmp     ax, 6; switch 7 cases
0x18001d773  ja      def_18001D793; jumptable 000000018001D793 default case, case 1
0x18001d779  mov     [rsp+0E8h+var_C0], r12
0x18001d77e  movsx   rax, ax
0x18001d782  lea     rdx, __ImageBase
0x18001d789  mov     ecx, ds:(jpt_18001D793 - 180000000h)[rdx+rax*4]
0x18001d790  add     rcx, rdx
0x18001d793  jmp     rcx; switch jump
0x18001d795  xor     edi, edi; jumptable 000000018001D793 case 4
0x18001d797  jmp     loc_18001DBE4
0x18001d79c  lea     r14, ?m_lock@MakeAvailableAsyncWaiter@Indexer@@0Vsrwlock@wil@@A; jumptable 000000018001D793 case 3
0x18001d7a3  mov     rcx, r14; SRWLock
0x18001d7a6  call    cs:__imp_AcquireSRWLockShared
0x18001d7ac  xor     edi, edi
0x18001d7ae  cmp     cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rdi
0x18001d7b5  setnz   bl
0x18001d7b8  mov     rcx, r14; SRWLock
0x18001d7bb  call    cs:__imp_ReleaseSRWLockShared
0x18001d7c1  test    bl, bl
0x18001d7c3  jnz     loc_18001D87F
0x18001d7c9  mov     rcx, r14; SRWLock
0x18001d7cc  call    cs:__imp_AcquireSRWLockExclusive
0x18001d7d2  mov     [rsi+90h], r14
0x18001d7d9  cmp     cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rdi
0x18001d7e0  jnz     loc_18001D876
0x18001d7e6  xor     r9d, r9d; lpName
0x18001d7e9  mov     r8d, r15d; bInitialState
0x18001d7ec  mov     edx, r15d; bManualReset
0x18001d7ef  xor     ecx, ecx; lpEventAttributes
0x18001d7f1  call    cs:__imp_CreateEventW
0x18001d7f7  mov     rbx, rax
0x18001d7fa  mov     r15, cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18001d801  test    r15, r15
0x18001d804  jz      short loc_18001D847
0x18001d806  call    cs:__imp_GetLastError
0x18001d80c  mov     [rsp+0E8h+dwErrCode], eax
0x18001d813  mov     rcx, r15; hObject
0x18001d816  call    cs:__imp_CloseHandle
0x18001d81c  mov     rcx, [rsp+0E8h]; this
0x18001d824  test    eax, eax
0x18001d826  jnz     short loc_18001D83A
0x18001d828  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d82f  mov     edx, 0A0Bh; void *
0x18001d834  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d83a  mov     ecx, [rsp+0E8h+dwErrCode]; dwErrCode
0x18001d841  call    cs:__imp_SetLastError
0x18001d847  mov     cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A, rbx
0x18001d84e  mov     rcx, [rsp+0E8h]; this
0x18001d856  test    rbx, rbx
0x18001d859  jnz     short loc_18001D870
0x18001d85b  mov     r9d, 80004005h; char *
0x18001d861  lea     r8, aOnecoreuapBase_4; "onecoreuap\\base\\appmodel\\search\\com"...
0x18001d868  lea     edx, [rbx+24h]; void *
0x18001d86b  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001d870  mov     r15d, 1
0x18001d876  mov     rcx, r14; SRWLock
0x18001d879  call    cs:__imp_ReleaseSRWLockExclusive
0x18001d87f  lea     rbx, [rsi+98h]
0x18001d886  mov     [rbx], r15b
0x18001d889  lea     r15, [rsi+0A0h]
0x18001d890  jmp     loc_18001DB00
0x18001d895  mov     rcx, [rsi+0A8h]; jumptable 000000018001D793 case 6
0x18001d89c  mov     [rsp+0E8h+var_A8], rcx
0x18001d8a1  xor     edi, edi
0x18001d8a3  test    rcx, rcx
0x18001d8a6  jz      short loc_18001D8B4
0x18001d8a8  call    CloseThreadpoolWait_0
0x18001d8ad  mov     [rsi+0A8h], rdi
0x18001d8b4  mov     rbx, [rsi+0A0h]
0x18001d8bb  test    rbx, rbx
0x18001d8be  jz      short loc_18001D8D8
0x18001d8c0  mov     [rsp+0E8h+var_B0], rbx
0x18001d8c5  jmp     short loc_18001D8CD
0x18001d8c7  call    cs:__imp__Thrd_yield
0x18001d8cd  mov     rax, rdi
0x18001d8d0  xchg    rax, [rbx]
0x18001d8d3  cmp     rax, r15
0x18001d8d6  jz      short loc_18001D8C7
0x18001d8d8  jmp     loc_18001DBE4
0x18001d8dd  lea     r14, ?m_lock@MakeAvailableAsyncWaiter@Indexer@@0Vsrwlock@wil@@A; jumptable 000000018001D793 case 5
0x18001d8e4  xor     edi, edi
0x18001d8e6  mov     eax, edi
0x18001d8e8  xchg    eax, [rsi+0D0h]
0x18001d8ee  cmp     eax, 2
0x18001d8f1  jnz     short loc_18001D91E
0x18001d8f3  lea     rcx, [rsi+100h]
0x18001d8fa  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001d8ff  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001d902  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x18001d907  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001d90c  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001d913  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18001d918  call    _CxxThrowException_0
0x18001d91e  mov     rcx, [rsi+0A8h]; pwa
0x18001d925  mov     [rsp+0E8h+var_A8], rcx
0x18001d92a  test    rcx, rcx
0x18001d92d  jz      short loc_18001D93B
0x18001d92f  call    CloseThreadpoolWait_0
0x18001d934  mov     [rsi+0A8h], rdi
0x18001d93b  lea     r15, [rsi+0A0h]
0x18001d942  mov     rbx, [r15]
0x18001d945  mov     [rsp+0E8h+var_B0], rbx
0x18001d94a  test    rbx, rbx
0x18001d94d  jz      short loc_18001D963
0x18001d94f  jmp     short loc_18001D957
0x18001d951  call    cs:__imp__Thrd_yield
0x18001d957  mov     rax, rdi
0x18001d95a  xchg    rax, [rbx]
0x18001d95d  cmp     rax, 1
0x18001d961  jz      short loc_18001D951
0x18001d963  mov     rcx, r14; SRWLock
0x18001d966  call    cs:__imp_AcquireSRWLockExclusive
0x18001d96c  mov     rbx, cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18001d973  xor     r8d, r8d; bAlertable
0x18001d976  xor     edx, edx; dwMilliseconds
0x18001d978  mov     rcx, rbx; hHandle
0x18001d97b  call    cs:__imp_WaitForSingleObjectEx
0x18001d981  cmp     eax, 102h
0x18001d986  jz      loc_18001DAF0
0x18001d98c  test    eax, eax
0x18001d98e  jnz     loc_18001DAD6
0x18001d994  xor     r8d, r8d; bAlertable
0x18001d997  xor     edx, edx; dwMilliseconds
0x18001d999  mov     rcx, rbx; hHandle
0x18001d99c  call    cs:__imp_WaitForSingleObjectEx
0x18001d9a2  test    eax, eax
0x18001d9a4  jnz     loc_18001DAD6
0x18001d9aa  mov     rbx, [rsp+0E8h]
0x18001d9b2  mov     rcx, cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A; hEvent
0x18001d9b9  call    cs:__imp_ResetEvent
0x18001d9bf  test    eax, eax
0x18001d9c1  jnz     short loc_18001D9D8
0x18001d9c3  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d9ca  mov     edx, 0A06h; void *
0x18001d9cf  mov     rcx, rbx; this
0x18001d9d2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001d9d8  mov     r15, cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18001d9df  test    r15, r15
0x18001d9e2  jnz     short loc_18001D9FE
0x18001d9e4  mov     rcx, [rsp+0E8h]; this
0x18001d9ec  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001d9f3  mov     edx, 0AF3h; void *
0x18001d9f8  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001d9fe  mov     rbx, [rsi+80h]
0x18001da05  lea     rcx, [rsi+0D8h]
0x18001da0c  cmp     rbx, rcx
0x18001da0f  jz      short loc_18001DA84
0x18001da11  mov     rax, [rbx]
0x18001da14  mov     [rsp+0E8h+hEvent], rax
0x18001da1c  test    rax, rax
0x18001da1f  jz      short loc_18001DA7E
0x18001da21  call    cs:__imp_GetLastError
0x18001da27  mov     [rsp+0E8h+dwErrCode], eax
0x18001da2e  mov     rax, [rsp+0E8h]
0x18001da36  mov     [rsp+0E8h+arg_18], rax
0x18001da3e  mov     rcx, [rsp+0E8h+hEvent]; hEvent
0x18001da46  call    cs:__imp_SetEvent
0x18001da4c  test    eax, eax
0x18001da4e  jnz     short loc_18001DA6A
0x18001da50  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001da57  mov     edx, 0A01h; void *
0x18001da5c  mov     rcx, [rsp+0E8h+arg_18]; this
0x18001da64  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001da6a  mov     ecx, [rsp+0E8h+dwErrCode]; dwErrCode
0x18001da71  call    cs:__imp_SetLastError
0x18001da77  lea     rcx, [rsi+0D8h]
0x18001da7e  mov     [rbx], r15
0x18001da81  mov     r15, rdi
0x18001da84  mov     [rcx], r15
0x18001da87  lea     rbx, [rsi+98h]
0x18001da8e  mov     [rbx], dil
0x18001da91  test    r15, r15
0x18001da94  jz      short loc_18001DACD
0x18001da96  mov     rax, [rsp+0E8h]
0x18001da9e  mov     qword ptr [rsp+0E8h+dwErrCode], rax
0x18001daa6  mov     rcx, r15; hEvent
0x18001daa9  call    cs:__imp_SetEvent
0x18001daaf  test    eax, eax
0x18001dab1  jnz     short loc_18001DACD
0x18001dab3  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001daba  mov     edx, 0A01h; void *
0x18001dabf  mov     rcx, qword ptr [rsp+0E8h+dwErrCode]; this
0x18001dac7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18001dacd  lea     r15, [rsi+0A0h]
0x18001dad4  jmp     short loc_18001DAF7
0x18001dad6  mov     rcx, [rsp+0E8h]; this
0x18001dade  lea     r8, aOnecoreInterna_7; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18001dae5  mov     edx, 0B07h; void *
0x18001daea  call    ?FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::FailFast_Unexpected(void *,uint,char const *)
0x18001daf0  lea     rbx, [rsi+98h]
0x18001daf7  mov     rcx, r14; SRWLock
0x18001dafa  call    cs:__imp_ReleaseSRWLockExclusive
0x18001db00  cmp     [rbx], dil
0x18001db03  jz      loc_18001DBA9
0x18001db09  mov     [r15], rdi
0x18001db0c  mov     [rsi+0A8h], rdi
0x18001db13  mov     [rsi+0B0h], rdi
0x18001db1a  mov     rax, cs:?m_waitEvent@MakeAvailableAsyncWaiter@Indexer@@0V?$unique_any_t@V?$event_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@Uerr_exception_policy@3@@wil@@@wil@@A
0x18001db21  mov     [rsi+0B8h], rax
0x18001db28  mov     [rsi+0C0h], edi
0x18001db2e  mov     [rsi+0C8h], rdi
0x18001db35  mov     [rsi+0D0h], edi
0x18001db3b  mov     eax, [rsi+70h]
0x18001db3e  nop
0x18001db3f  cmp     eax, 2
0x18001db42  jnz     short loc_18001DB74
0x18001db44  lea     rcx, [rsi+0E8h]
0x18001db4b  call    ?current@slim_source_location@impl@winrt@@SA?AU123@IQEBD0@Z; winrt::impl::slim_source_location::current(uint,char const * const,char const * const)
0x18001db50  mov     rdx, rax; struct winrt::impl::slim_source_location *
0x18001db53  lea     rcx, [rsp+0E8h+var_60]; this
0x18001db5b  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18001db60  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18001db67  lea     rcx, [rsp+0E8h+var_60]; pExceptionObject
0x18001db6f  call    _CxxThrowException_0
0x18001db74  mov     rcx, [rsi+0B8h]; hHandle
0x18001db7b  mov     [rsp+0E8h+var_98], rcx
0x18001db80  xor     edx, edx; dwMilliseconds
0x18001db82  call    WaitForSingleObject_0
0x18001db87  test    eax, eax
0x18001db89  jz      loc_18001D8E6
0x18001db8f  mov     eax, 4
0x18001db94  mov     [r12], ax
0x18001db99  mov     rdx, rsi
0x18001db9c  mov     rcx, r15
0x18001db9f  call    ??$await_suspend@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUMakeAvailableAsyncWaiter@Indexer@@@std@@@signal_awaiter@impl@winrt@@QEAAXU?$coroutine_handle@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUMakeAvailableAsyncWaiter@Indexer@@@std@@@std@@@Z; winrt::impl::signal_awaiter::await_suspend<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Indexer::MakeAvailableAsyncWaiter &>::promise_type>(std::coroutine_handle<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,Indexer::MakeAvailableAsyncWaiter &>::promise_type>)
0x18001dba4  jmp     loc_18001DC2D
0x18001dba9  jmp     short loc_18001DBBF
0x18001dbab  xor     edi, edi
0x18001dbad  mov     rsi, [rsp+0E8h+arg_0]
0x18001dbb5  mov     r12, [rsp+0E8h+var_C0]
0x18001dbba  mov     r13, [rsp+0E8h+var_B8]
0x18001dbbf  lea     rcx, [rsi+0E0h]
0x18001dbc6  lea     rax, [rsi+10h]
0x18001dbca  mov     [rcx], rax
0x18001dbcd  xor     eax, eax
0x18001dbcf  mov     [r12], ax
0x18001dbd4  mov     [rsi], rdi
0x18001dbd7  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@AEAUIndexerSemanticStore@@W4ModelKind@SemanticSearch@Indexer@34@@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@std@@@Z; winrt::impl::promise_base<std::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,IndexerSemanticStore &,winrt::Windows::Indexer::SemanticSearch::ModelKind>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::coroutine_handle<void>)
0x18001dbdc  test    al, al
0x18001dbde  jz      short loc_18001DBE4
0x18001dbe0  jmp     short loc_18001DC2D
0x18001dbe2  xor     edi, edi; jumptable 000000018001D793 cases 0,2
0x18001dbe4  lea     rcx, [rsi+68h]
0x18001dbe8  cmp     [rcx], rdi
0x18001dbeb  jz      short loc_18001DBF2
0x18001dbed  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001dbf2  lea     rcx, [rsi+60h]
0x18001dbf6  cmp     [rcx], rdi
0x18001dbf9  jz      short loc_18001DC00
0x18001dbfb  call    ?unconditional_release_ref@?$com_ptr@UISessionManagerStatics@SessionManager@Workloads@Private@Windows@Microsoft@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::Microsoft::Windows::Private::Workloads::SessionManager::ISessionManagerStatics>::unconditional_release_ref(void)
0x18001dc00  lea     rcx, [rsi+48h]
0x18001dc04  call    cs:__imp_?__ExceptionPtrDestroy@@YAXPEAX@Z; __ExceptionPtrDestroy(void *)
0x18001dc0a  lea     rcx, [rsi+10h]
0x18001dc0e  call    ??1?$root_implements@UIndexerSemanticSearchServicesImpl@@UIIndexerSemanticSearchServices@@UISemanticSearchServices@SemanticSearch@Indexer@Windows@winrt@@Unon_agile@7@@impl@winrt@@MEAA@XZ; winrt::impl::root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>::~root_implements<IndexerSemanticSearchServicesImpl,IIndexerSemanticSearchServices,winrt::Windows::Indexer::SemanticSearch::ISemanticSearchServices,winrt::non_agile>(void)
0x18001dc13  cmp     [r13+8Ah], di
0x18001dc1b  jz      short loc_18001DC2D
0x18001dc1d  mov     edx, 120h; unsigned __int64
0x18001dc22  mov     rcx, rsi; void *
0x18001dc25  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001dc2a  jmp     short loc_18001DC2D
0x18001dc2c  int     3; Trap to Debugger
0x18001dc2d  add     rsp, 0B0h
0x18001dc34  pop     r15
0x18001dc36  pop     r14
0x18001dc38  pop     r13
0x18001dc3a  pop     r12
0x18001dc3c  pop     rdi
0x18001dc3d  pop     rsi
0x18001dc3e  pop     rbx
0x18001dc3f  retn
```
