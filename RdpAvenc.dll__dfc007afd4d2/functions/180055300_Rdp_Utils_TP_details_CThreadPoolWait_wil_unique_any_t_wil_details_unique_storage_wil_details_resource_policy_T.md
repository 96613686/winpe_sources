# Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::~CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>(void)

- ea: `0x180055300`
- end: `0x18005548f`
- name: `??1?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@UEAA@XZ`
- size: `399`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180055e20`

## callees

- `0x18000b07c`
- `0x18000ba24`
- `0x180055300`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800553c6`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800553c6`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005539b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180055369`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18005539b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005533a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055380`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005533a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180055380`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005538b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800553d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800553ef`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18005538b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800553d8`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800553ef`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055361`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055448`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055361`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x180055448`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005534a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180055431`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005534a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180055431`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180055358`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005543f`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180055358`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18005543f`

## pseudocode

```c
void __fastcall Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::~CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>(
        __int64 a1)
{
  __int64 v2; // rdx
  struct _TP_WAIT *v3; // rsi
  DWORD LastError; // ebx
  void *v5; // rbx
  DWORD v6; // esi
  unsigned int v7; // r8d
  const char *v8; // r9
  __int64 v9; // rcx
  void *v11; // rcx
  unsigned int v12; // r8d
  const char *v13; // r9
  void *v14; // rcx
  unsigned int v15; // r8d
  const char *v16; // r9
  __int64 v17; // rcx
  struct _TP_WAIT *v18; // rbx
  __int64 v19; // [rsp+20h] [rbp-18h] BYREF
  char v20; // [rsp+28h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)a1 = &Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::`vftable';
  std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(
    &v19,
    a1 + 88);
  if ( *(_QWORD *)(a1 + 80) )
  {
    v3 = *(struct _TP_WAIT **)(a1 + 8);
    if ( v3 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v3, 0, 0);
      WaitForThreadpoolWaitCallbacks(v3, 1);
      CloseThreadpoolWait(v3);
      SetLastError(LastError);
    }
    *(_QWORD *)(a1 + 8) = 0;
    v5 = *(void **)(a1 + 80);
    if ( v5 )
    {
      v6 = GetLastError();
      if ( !CloseHandle(v5) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v7, v8);
      SetLastError(v6);
    }
    *(_QWORD *)(a1 + 80) = 0;
  }
  if ( v20 )
  {
    v9 = v19;
    if ( (*(_DWORD *)(v19 + 76))-- == 1 )
    {
      *(_DWORD *)(v9 + 72) = -1;
      ReleaseSRWLockExclusive((PSRWLOCK)(v9 + 16));
    }
  }
  v11 = *(void **)(a1 + 168);
  if ( v11 && !CloseHandle(v11) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v12, v13);
  v14 = *(void **)(a1 + 80);
  if ( v14 && !CloseHandle(v14) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v15, v16);
  v17 = *(_QWORD *)(a1 + 72);
  if ( v17 )
  {
    LOBYTE(v2) = v17 != a1 + 16;
    (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v17 + 32LL))(v17, v2);
    *(_QWORD *)(a1 + 72) = 0;
  }
  v18 = *(struct _TP_WAIT **)(a1 + 8);
  if ( v18 )
  {
    SetThreadpoolWait(*(PTP_WAIT *)(a1 + 8), 0, 0);
    WaitForThreadpoolWaitCallbacks(v18, 1);
    CloseThreadpoolWait(v18);
  }
}

```

## disassembly

```asm
0x180055300  mov     [rsp+arg_8], rbx
0x180055305  mov     [rsp+arg_10], rsi
0x18005530a  push    rdi
0x18005530b  sub     rsp, 30h
0x18005530f  mov     rdi, rcx
0x180055312  lea     rax, ??_7?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@6B@; const Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::`vftable'
0x180055319  mov     [rcx], rax
0x18005531c  lea     rdx, [rcx+58h]
0x180055320  lea     rcx, [rsp+38h+var_18]
0x180055325  call    ??0?$unique_lock@Vrundown_mutex@Synchronization@Utils@Rdp@@@std@@QEAA@AEAVrundown_mutex@Synchronization@Utils@Rdp@@@Z; std::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>::unique_lock<Rdp::Utils::Synchronization::rundown_mutex>(Rdp::Utils::Synchronization::rundown_mutex &)
0x18005532a  cmp     qword ptr [rdi+50h], 0
0x18005532f  jz      short loc_1800553A9
0x180055331  mov     rsi, [rdi+8]
0x180055335  test    rsi, rsi
0x180055338  jz      short loc_18005536F
0x18005533a  call    cs:__imp_GetLastError
0x180055340  mov     ebx, eax
0x180055342  xor     r8d, r8d; pftTimeout
0x180055345  xor     edx, edx; h
0x180055347  mov     rcx, rsi; pwa
0x18005534a  call    cs:__imp_SetThreadpoolWait
0x180055350  mov     edx, 1; fCancelPendingCallbacks
0x180055355  mov     rcx, rsi; pwa
0x180055358  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005535e  mov     rcx, rsi; pwa
0x180055361  call    cs:__imp_CloseThreadpoolWait
0x180055367  mov     ecx, ebx; dwErrCode
0x180055369  call    cs:__imp_SetLastError
0x18005536f  mov     qword ptr [rdi+8], 0
0x180055377  mov     rbx, [rdi+50h]
0x18005537b  test    rbx, rbx
0x18005537e  jz      short loc_1800553A1
0x180055380  call    cs:__imp_GetLastError
0x180055386  mov     esi, eax
0x180055388  mov     rcx, rbx; hObject
0x18005538b  call    cs:__imp_CloseHandle
0x180055391  test    eax, eax
0x180055393  jz      loc_18005546F
0x180055399  mov     ecx, esi; dwErrCode
0x18005539b  call    cs:__imp_SetLastError
0x1800553a1  mov     qword ptr [rdi+50h], 0
0x1800553a9  cmp     [rsp+38h+var_10], 0
0x1800553ae  jz      short loc_1800553CC
0x1800553b0  mov     rcx, [rsp+38h+var_18]
0x1800553b5  sub     dword ptr [rcx+4Ch], 1
0x1800553b9  jnz     short loc_1800553CC
0x1800553bb  mov     dword ptr [rcx+48h], 0FFFFFFFFh
0x1800553c2  add     rcx, 10h; SRWLock
0x1800553c6  call    cs:__imp_ReleaseSRWLockExclusive
0x1800553cc  mov     rcx, [rdi+0A8h]; hObject
0x1800553d3  test    rcx, rcx
0x1800553d6  jz      short loc_1800553E6
0x1800553d8  call    cs:__imp_CloseHandle
0x1800553de  test    eax, eax
0x1800553e0  jz      loc_18005547F
0x1800553e6  mov     rcx, [rdi+50h]; hObject
0x1800553ea  test    rcx, rcx
0x1800553ed  jz      short loc_1800553F9
0x1800553ef  call    cs:__imp_CloseHandle
0x1800553f5  test    eax, eax
0x1800553f7  jz      short loc_18005545F
0x1800553f9  lea     rbx, [rdi+10h]
0x1800553fd  mov     rcx, [rbx+38h]
0x180055401  test    rcx, rcx
0x180055404  jz      short loc_180055420
0x180055406  mov     rax, [rcx]
0x180055409  cmp     rcx, rbx
0x18005540c  setnz   dl
0x18005540f  mov     rax, [rax+20h]
0x180055413  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055418  mov     qword ptr [rbx+38h], 0
0x180055420  mov     rbx, [rdi+8]
0x180055424  test    rbx, rbx
0x180055427  jz      short loc_18005544F
0x180055429  xor     r8d, r8d; pftTimeout
0x18005542c  xor     edx, edx; h
0x18005542e  mov     rcx, rbx; pwa
0x180055431  call    cs:__imp_SetThreadpoolWait
0x180055437  mov     edx, 1; fCancelPendingCallbacks
0x18005543c  mov     rcx, rbx; pwa
0x18005543f  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180055445  mov     rcx, rbx; pwa
0x180055448  call    cs:__imp_CloseThreadpoolWait
0x18005544e  nop
0x18005544f  mov     rbx, [rsp+38h+arg_8]
0x180055454  mov     rsi, [rsp+38h+arg_10]
0x180055459  add     rsp, 30h
0x18005545d  pop     rdi
0x18005545e  retn
0x18005545f  mov     rcx, [rsp+38h]; this
0x180055464  mov     edx, 0A0Bh; void *
0x180055469  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005546f  mov     rcx, [rsp+38h]; this
0x180055474  mov     edx, 0A0Bh; void *
0x180055479  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x18005547f  mov     rcx, [rsp+38h]; this
0x180055484  mov     edx, 0A0Bh; void *
0x180055489  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
