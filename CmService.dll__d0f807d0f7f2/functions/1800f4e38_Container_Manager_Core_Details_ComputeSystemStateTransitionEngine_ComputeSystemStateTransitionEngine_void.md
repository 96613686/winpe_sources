# Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::~ComputeSystemStateTransitionEngine(void)

- ea: `0x1800f4e38`
- end: `0x1800f510d`
- name: `??1ComputeSystemStateTransitionEngine@Details@Core@Manager@Container@@QEAA@XZ`
- size: `725`
- prototype: `void __fastcall(Container::Manager::Core::Details::ComputeSystemStateTransitionEngine *__hidden this)`
- caller_count: `4`
- callee_count: `7`
- tags: `file_ops, registry_config, broker_com_uri`

## callers

- `0x180099984`
- `0x1800a24bc`
- `0x1800ef76c`
- `0x1800f0078`

## callees

- `0x180004fc4`
- `0x180016658`
- `0x180066670`
- `0x180080880`
- `0x180080980`
- `0x18008d0d8`
- `0x1800f4e38`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f4f23`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x1800f4f23`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f4f64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f4fd6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f4f64`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x1800f4fd6`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f4f3b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolTimerCallbacks` at `0x1800f4f3b`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800f4eec`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800f4eec`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f4e84`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x1800f4e84`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f4e69`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x1800f4e69`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4f53`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4e9e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800f4f53`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f4ebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f4f72`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f4ebd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800f4f72`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4eaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f501d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f503e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f505b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5096`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4eaf`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f4f9a`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f501d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f503e`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f505b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5078`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800f5096`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ComputeSystemStateTransitionEngine::~ComputeSystemStateTransitionEngine(
        Container::Manager::Core::Details::ComputeSystemStateTransitionEngine *this)
{
  unsigned int v2; // r8d
  const char *v3; // r9
  char *v4; // rsi
  DWORD LastError; // ebx
  struct _TP_TIMER *v6; // rsi
  DWORD v7; // ebx
  char *v8; // rcx
  struct _TP_TIMER *v9; // rcx
  char *v10; // rcx
  void *v11; // rcx
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rcx
  unsigned int v15; // r8d
  const char *v16; // r9
  void *v17; // rcx
  unsigned int v18; // r8d
  const char *v19; // r9
  char *v20; // rcx
  void *v21; // rcx
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  if ( *((_QWORD *)this + 20) )
  {
    if ( (unsigned __int64)(*((_QWORD *)this + 12) - 1LL) <= 0xFFFFFFFFFFFFFFFDuLL )
    {
      if ( !SetEvent(*((HANDLE *)this + 13)) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v2, v3);
      WaitForSingleObject(*((HANDLE *)this + 12), 0xFFFFFFFF);
      v4 = (char *)*((_QWORD *)this + 12);
      if ( (unsigned __int64)(v4 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
      {
        LastError = GetLastError();
        CloseHandle(v4);
        SetLastError(LastError);
      }
      *((_QWORD *)this + 12) = 0;
    }
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(
      (char *)this + 1456,
      0);
    *((_DWORD *)this + 366) = 1;
    WakeByAddressAll((char *)this + 1464);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(
      (char *)this + 1472,
      0);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(
      (char *)this + 1448,
      0);
    SetThreadpoolTimer(*((PTP_TIMER *)this + 185), 0, 0, 0);
    WaitForThreadpoolTimerCallbacks(*((PTP_TIMER *)this + 185), 1);
    v6 = (struct _TP_TIMER *)*((_QWORD *)this + 185);
    if ( v6 )
    {
      v7 = GetLastError();
      CloseThreadpoolTimer(v6);
      SetLastError(v7);
    }
    *((_QWORD *)this + 185) = 0;
  }
  v8 = (char *)*((_QWORD *)this + 210);
  if ( (unsigned __int64)(v8 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v8);
  if ( *((_BYTE *)this + 1672) )
    Container::Manager::Core::Details::BindingSettings::~BindingSettings((Container::Manager::Core::Details::ComputeSystemStateTransitionEngine *)((char *)this + 1584));
  if ( *((_BYTE *)this + 1576) )
    utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>((char *)this + 1552);
  v9 = (struct _TP_TIMER *)*((_QWORD *)this + 185);
  if ( v9 )
    CloseThreadpoolTimer(v9);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(
    (char *)this + 1472,
    0);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(
    (char *)this + 1456,
    0);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(
    (char *)this + 1448,
    0);
  v10 = (char *)*((_QWORD *)this + 180);
  if ( (unsigned __int64)(v10 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v10);
  Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration((Container::Manager::Core::Details::ComputeSystemStateTransitionEngine *)((char *)this + 168));
  v11 = (void *)*((_QWORD *)this + 15);
  if ( v11 && !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
  v14 = (void *)*((_QWORD *)this + 14);
  if ( v14 && !CloseHandle(v14) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
  v17 = (void *)*((_QWORD *)this + 13);
  if ( v17 && !CloseHandle(v17) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v18, v19);
  v20 = (char *)*((_QWORD *)this + 12);
  if ( (unsigned __int64)(v20 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle(v20);
  v21 = (void *)*((_QWORD *)this + 9);
  if ( v21 != (void *)-1LL )
  {
    *((_QWORD *)this + 10) = v21;
    operator delete(v21, (const struct std::nothrow_t *)&std::nothrow);
  }
}

```

## disassembly

```asm
0x1800f4e38  mov     [rsp+arg_0], rbx
0x1800f4e3d  mov     [rsp+arg_8], rsi
0x1800f4e42  push    rdi
0x1800f4e43  sub     rsp, 20h
0x1800f4e47  cmp     qword ptr [rcx+0A0h], 0
0x1800f4e4f  mov     rdi, rcx
0x1800f4e52  jz      loc_1800F4F89
0x1800f4e58  mov     rax, [rcx+60h]
0x1800f4e5c  dec     rax
0x1800f4e5f  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f4e63  ja      short loc_1800F4ED1
0x1800f4e65  mov     rcx, [rcx+68h]; hEvent
0x1800f4e69  call    cs:__imp_SetEvent
0x1800f4e70  nop     dword ptr [rax+rax+00h]
0x1800f4e75  test    eax, eax
0x1800f4e77  jz      loc_1800F50DD
0x1800f4e7d  mov     rcx, [rdi+60h]; hHandle
0x1800f4e81  or      edx, 0FFFFFFFFh; dwMilliseconds
0x1800f4e84  call    cs:__imp_WaitForSingleObject
0x1800f4e8b  nop     dword ptr [rax+rax+00h]
0x1800f4e90  mov     rsi, [rdi+60h]
0x1800f4e94  lea     rax, [rsi-1]
0x1800f4e98  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f4e9c  ja      short loc_1800F4EC9
0x1800f4e9e  call    cs:__imp_GetLastError
0x1800f4ea5  nop     dword ptr [rax+rax+00h]
0x1800f4eaa  mov     rcx, rsi; hObject
0x1800f4ead  mov     ebx, eax
0x1800f4eaf  call    cs:__imp_CloseHandle
0x1800f4eb6  nop     dword ptr [rax+rax+00h]
0x1800f4ebb  mov     ecx, ebx; dwErrCode
0x1800f4ebd  call    cs:__imp_SetLastError
0x1800f4ec4  nop     dword ptr [rax+rax+00h]
0x1800f4ec9  mov     qword ptr [rdi+60h], 0
0x1800f4ed1  lea     rcx, [rdi+5B0h]
0x1800f4ed8  xor     edx, edx
0x1800f4eda  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f4edf  lea     rcx, [rdi+5B8h]; Address
0x1800f4ee6  mov     dword ptr [rcx], 1
0x1800f4eec  call    cs:__imp_WakeByAddressAll
0x1800f4ef3  nop     dword ptr [rax+rax+00h]
0x1800f4ef8  lea     rcx, [rdi+5C0h]
0x1800f4eff  xor     edx, edx
0x1800f4f01  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f4f06  lea     rcx, [rdi+5A8h]
0x1800f4f0d  xor     edx, edx
0x1800f4f0f  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f4f14  mov     rcx, [rdi+5C8h]; pti
0x1800f4f1b  xor     r9d, r9d; msWindowLength
0x1800f4f1e  xor     r8d, r8d; msPeriod
0x1800f4f21  xor     edx, edx; pftDueTime
0x1800f4f23  call    cs:__imp_SetThreadpoolTimer
0x1800f4f2a  nop     dword ptr [rax+rax+00h]
0x1800f4f2f  mov     rcx, [rdi+5C8h]; pti
0x1800f4f36  mov     edx, 1; fCancelPendingCallbacks
0x1800f4f3b  call    cs:__imp_WaitForThreadpoolTimerCallbacks
0x1800f4f42  nop     dword ptr [rax+rax+00h]
0x1800f4f47  mov     rsi, [rdi+5C8h]
0x1800f4f4e  test    rsi, rsi
0x1800f4f51  jz      short loc_1800F4F7E
0x1800f4f53  call    cs:__imp_GetLastError
0x1800f4f5a  nop     dword ptr [rax+rax+00h]
0x1800f4f5f  mov     rcx, rsi; pti
0x1800f4f62  mov     ebx, eax
0x1800f4f64  call    cs:__imp_CloseThreadpoolTimer
0x1800f4f6b  nop     dword ptr [rax+rax+00h]
0x1800f4f70  mov     ecx, ebx; dwErrCode
0x1800f4f72  call    cs:__imp_SetLastError
0x1800f4f79  nop     dword ptr [rax+rax+00h]
0x1800f4f7e  mov     qword ptr [rdi+5C8h], 0
0x1800f4f89  mov     rcx, [rdi+690h]; hObject
0x1800f4f90  lea     rax, [rcx-1]
0x1800f4f94  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f4f98  ja      short loc_1800F4FA6
0x1800f4f9a  call    cs:__imp_CloseHandle
0x1800f4fa1  nop     dword ptr [rax+rax+00h]
0x1800f4fa6  lea     rcx, [rdi+630h]; this
0x1800f4fad  cmp     byte ptr [rcx+58h], 0
0x1800f4fb1  jz      short loc_1800F4FB8
0x1800f4fb3  call    ??1BindingSettings@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::BindingSettings::~BindingSettings(void)
0x1800f4fb8  lea     rcx, [rdi+610h]
0x1800f4fbf  cmp     byte ptr [rcx+18h], 0
0x1800f4fc3  jz      short loc_1800F4FCA
0x1800f4fc5  call    ??1?$vector@UWcifsInstanceSettings@Details@Core@Manager@Container@@V?$allocator@UWcifsInstanceSettings@Details@Core@Manager@Container@@@utl@@@utl@@QEAA@XZ; utl::vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>::~vector<Container::Manager::Core::Details::WcifsInstanceSettings,utl::allocator<Container::Manager::Core::Details::WcifsInstanceSettings>>(void)
0x1800f4fca  mov     rcx, [rdi+5C8h]; pti
0x1800f4fd1  test    rcx, rcx
0x1800f4fd4  jz      short loc_1800F4FE2
0x1800f4fd6  call    cs:__imp_CloseThreadpoolTimer
0x1800f4fdd  nop     dword ptr [rax+rax+00h]
0x1800f4fe2  lea     rcx, [rdi+5C0h]
0x1800f4fe9  xor     edx, edx
0x1800f4feb  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f4ff0  lea     rcx, [rdi+5B0h]
0x1800f4ff7  xor     edx, edx
0x1800f4ff9  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f4ffe  lea     rcx, [rdi+5A8h]
0x1800f5005  xor     edx, edx
0x1800f5007  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x1800f500c  mov     rcx, [rdi+5A0h]; hObject
0x1800f5013  lea     rax, [rcx-1]
0x1800f5017  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f501b  ja      short loc_1800F5029
0x1800f501d  call    cs:__imp_CloseHandle
0x1800f5024  nop     dword ptr [rax+rax+00h]
0x1800f5029  lea     rcx, [rdi+0A8h]; this
0x1800f5030  call    ??1ComputeSystemConfiguration@Hcs@Manager@Container@@QEAA@XZ; Container::Manager::Hcs::ComputeSystemConfiguration::~ComputeSystemConfiguration(void)
0x1800f5035  mov     rcx, [rdi+78h]; hObject
0x1800f5039  test    rcx, rcx
0x1800f503c  jz      short loc_1800F5052
0x1800f503e  call    cs:__imp_CloseHandle
0x1800f5045  nop     dword ptr [rax+rax+00h]
0x1800f504a  test    eax, eax
0x1800f504c  jz      loc_1800F50ED
0x1800f5052  mov     rcx, [rdi+70h]; hObject
0x1800f5056  test    rcx, rcx
0x1800f5059  jz      short loc_1800F506F
0x1800f505b  call    cs:__imp_CloseHandle
0x1800f5062  nop     dword ptr [rax+rax+00h]
0x1800f5067  test    eax, eax
0x1800f5069  jz      loc_1800F50FD
0x1800f506f  mov     rcx, [rdi+68h]; hObject
0x1800f5073  test    rcx, rcx
0x1800f5076  jz      short loc_1800F5088
0x1800f5078  call    cs:__imp_CloseHandle
0x1800f507f  nop     dword ptr [rax+rax+00h]
0x1800f5084  test    eax, eax
0x1800f5086  jz      short loc_1800F50CD
0x1800f5088  mov     rcx, [rdi+60h]; hObject
0x1800f508c  lea     rax, [rcx-1]
0x1800f5090  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1800f5094  ja      short loc_1800F50A2
0x1800f5096  call    cs:__imp_CloseHandle
0x1800f509d  nop     dword ptr [rax+rax+00h]
0x1800f50a2  mov     rcx, [rdi+48h]; void *
0x1800f50a6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x1800f50aa  jz      short loc_1800F50BC
0x1800f50ac  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800f50b3  mov     [rdi+50h], rcx
0x1800f50b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800f50bc  mov     rbx, [rsp+28h+arg_0]
0x1800f50c1  mov     rsi, [rsp+28h+arg_8]
0x1800f50c6  add     rsp, 20h
0x1800f50ca  pop     rdi
0x1800f50cb  retn
0x1800f50cd  mov     rcx, [rsp+28h]; this
0x1800f50d2  mov     edx, 0A0Bh; void *
0x1800f50d7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f50dd  mov     rcx, [rsp+28h]; this
0x1800f50e2  mov     edx, 0A01h; void *
0x1800f50e7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f50ed  mov     rcx, [rsp+28h]; this
0x1800f50f2  mov     edx, 0A0Bh; void *
0x1800f50f7  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x1800f50fd  mov     rcx, [rsp+28h]; this
0x1800f5102  mov     edx, 0A0Bh; void *
0x1800f5107  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
