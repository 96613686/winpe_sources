# CRequestQueue::DoWork(int &,void *)

- ea: `0x1800683a0`
- end: `0x180068840`
- name: `?DoWork@CRequestQueue@@QEAAXAEAHPEAX@Z`
- size: `1184`
- prototype: `void __fastcall(CRequestQueue *__hidden this, int *, void *)`
- caller_count: `2`
- callee_count: `20`
- tags: `registry_config`

## callers

- `0x180119280`
- `0x180204134`

## callees

- `0x180038f08`
- `0x1800683a0`
- `0x180068848`
- `0x180068900`
- `0x180068b14`
- `0x1800698ec`
- `0x1800699a0`
- `0x180072768`
- `0x180076d10`
- `0x180096740`
- `0x1800ab5b0`
- `0x1801085d8`
- `0x180147154`
- `0x180153688`
- `0x18015aa68`
- `0x180175458`
- `0x1801ff8d0`
- `0x1801ffab4`
- `0x180202df8`
- `0x180203a3c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068433`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006857e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068704`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068433`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006857e`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180068704`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006855f`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x18006855f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068471`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006858d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068738`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068471`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006858d`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180068738`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800684da`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802b8d7a`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1800684da`
- `api-ms-win-core-synch-l1-1-0!WaitForMultipleObjectsEx` at `0x1802b8d7a`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1802b8e40`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1802b8e40`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180068484`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount` at `0x180068484`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18006871a`
- `api-ms-win-core-io-l1-1-1!CancelIo` at `0x18006871a`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x180068672`
- `api-ms-win-containers-cmclient-l1-2-0!CmsCreateActivity` at `0x180068672`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x18006869a`
- `api-ms-win-containers-cmclient-l1-2-0!CmsStartActivityAsync` at `0x18006869a`
- `api-ms-win-containers-cmclient-l1-1-0!CmsMapNamedPipeToContainer` at `0x18006878e`
- `api-ms-win-containers-cmclient-l1-1-0!CmsMapNamedPipeToContainer` at `0x18006878e`

## string_xrefs

- `0x180068418`: `[Proxy] cached/busy items: %d / %d\n`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CRequestQueue::DoWork(CRequestQueue *this, int *a2, void *a3)
{
  unsigned int v5; // r14d
  CRequestServer *v6; // rbx
  int v7; // eax
  unsigned int v8; // eax
  __int64 v9; // rcx
  __int64 v10; // rax
  const wchar_t *v11; // r9
  DWORD v12; // eax
  const char *v13; // r9
  int v14; // eax
  __int64 v15; // rax
  int started; // eax
  _QWORD *v17; // r8
  unsigned int v18; // eax
  char v19; // cl
  DWORD v20; // r9d
  const wchar_t *v21; // r15
  const char *v22; // r9
  BOOL bAlertable[2]; // [rsp+20h] [rbp-98h]
  CRequestServer *v24; // [rsp+48h] [rbp-70h] BYREF
  wchar_t *v25; // [rsp+50h] [rbp-68h] BYREF
  int v26; // [rsp+58h] [rbp-60h]
  int v27; // [rsp+5Ch] [rbp-5Ch]
  int v28; // [rsp+60h] [rbp-58h] BYREF
  char v29; // [rsp+64h] [rbp-54h]
  HANDLE Handles; // [rsp+68h] [rbp-50h] BYREF
  __int64 v31; // [rsp+70h] [rbp-48h]
  CRequestQueue *v32; // [rsp+78h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  v32 = this;
  v31 = 0;
  Handles = (HANDLE)*((_QWORD *)this + 43);
  v26 = 0;
  v5 = 0;
  v27 = 1;
  while ( 1 )
  {
    v6 = 0;
    v24 = 0;
    bAlertable[0] = *((_DWORD *)this + 28);
    SearchIndexerDebug::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const wchar_t *)0x1A6D,
      (unsigned int)L"[Proxy] cached/busy items: %d / %d\n",
      (const wchar_t *)*((unsigned int *)this + 34),
      *(_QWORD *)bAlertable);
    EnterCriticalSection((LPCRITICAL_SECTION)this);
    v7 = *((_DWORD *)this + 34);
    if ( v7 )
    {
      v8 = v7 - 1;
      *((_DWORD *)this + 34) = v8;
      v9 = v8;
      v10 = *((_QWORD *)this + 15);
      v24 = *(CRequestServer **)(v10 + 8 * v9);
      v6 = v24;
      *(_QWORD *)(v10 + 8 * v9) = 0;
      *((_DWORD *)v6 + 76) = 0;
    }
    if ( v27 )
      *((_DWORD *)this + 35) = 1;
    LeaveCriticalSection((LPCRITICAL_SECTION)this);
    v27 = 0;
    if ( v6 )
      break;
    if ( *((_DWORD *)this + 28) < *((_DWORD *)this + 44) )
    {
      CServerItem::Create(
        (CServerItem *)&v24,
        *((const wchar_t **)this + 46),
        *((_DWORD *)this + 43),
        this,
        (CRequestQueue *)((char *)this + 200),
        *((struct CEventSem **)this + 44),
        a2);
      if ( *((_QWORD *)this + 51) && !*((_BYTE *)this + 432) )
      {
        v28 = 0;
        v29 = 0;
        v25 = 0;
        v14 = CmsCreateActivity(a3, 22001, &v25);
        if ( v14 < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A89,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
            (const char *)(unsigned int)v14,
            bAlertable[0]);
        v15 = lambda_091d258e7c64cc5df55390d9ad9943cc_::operator_void____cdecl____CMS_ACTIVITY_NOTIFICATION___void___(retaddr);
        started = CmsStartActivityAsync(v25, v15, &v28);
        if ( started < 0 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1A98,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
            (const char *)(unsigned int)started,
            bAlertable[0]);
        if ( !(unsigned __int8)wil::slim_event_t<1>::wait(&v28) )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AA9,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
            (const char *)0x800705B4LL,
            bAlertable[0]);
        if ( !v29 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AA4,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
            (const char *)0x800703E3LL,
            bAlertable[0]);
        v17 = (_QWORD *)((char *)this + 392);
        if ( *((_QWORD *)this + 52) > 7u )
          v17 = (_QWORD *)*v17;
        v18 = CmsMapNamedPipeToContainer(v25, *((_QWORD *)this + 46), v17);
        if ( (int)(v18 + 0x80000000) < 0 || (v19 = 1, v18 == -2147024713) )
          v19 = 0;
        if ( v19 )
          wil::details::in1diag3::Throw_Hr(
            retaddr,
            (void *)0x1AA0,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
            (const char *)v18,
            bAlertable[0]);
        *((_BYTE *)this + 432) = 1;
        v5 = 0;
        wil::details::unique_storage<wil::details::resource_policy<void *,void (void * &),&void ContainerHelperDetails::CloseContainerActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void * &),&void ContainerHelperDetails::CloseContainerActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(&v25);
      }
      v6 = v24;
    }
    if ( v6 )
      break;
    SearchIndexerDebug::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const wchar_t *)0x1AFB,
      (unsigned int)L"[Proxy] wait for RequestServer\n",
      v11);
    v31 = *((_QWORD *)this + 42);
    v20 = 10000;
    if ( *((_DWORD *)this + 28) != *((_DWORD *)this + 44) )
      v20 = -1;
    v21 = (const wchar_t *)WaitForMultipleObjectsEx(2u, &Handles, 0, v20, 0);
    SearchIndexerDebug::Verbose(
      (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
      (const wchar_t *)0x1B02,
      (unsigned int)L"[Proxy] wfsoex wakeup: %d\n",
      v21);
    if ( (_DWORD)v21 == 258 )
      goto LABEL_12;
    if ( !(_DWORD)v21 )
    {
      v5 = 3;
      CServerItem::Free((CServerItem *)&v24);
LABEL_16:
      EnterCriticalSection((LPCRITICAL_SECTION)this);
      *((_DWORD *)this + 35) = 0;
      LeaveCriticalSection((LPCRITICAL_SECTION)this);
      goto LABEL_18;
    }
    if ( (_DWORD)v21 != 1 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1B11,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        v22);
LABEL_13:
    v26 = 0;
    if ( *((_DWORD *)this + 40) || *((_DWORD *)this + 41) )
      goto LABEL_16;
  }
  *((_DWORD *)v6 + 72) = GetTickCount();
  _InterlockedIncrement((volatile signed __int32 *)this + 28);
  if ( (unsigned int)CPipeServer::Connect((LPOVERLAPPED)((char *)v6 + 24)) )
  {
LABEL_11:
    CWorkQueue::Add((CRequestQueue *)((char *)this + 200), v6);
    v24 = 0;
    if ( *((_DWORD *)this + 28) != *((_DWORD *)this + 44) )
      goto LABEL_13;
LABEL_12:
    CRequestQueue::WrestReqServerFromIdleClient((LPCRITICAL_SECTION)this);
    goto LABEL_13;
  }
  SearchIndexerDebug::Verbose(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
    (const wchar_t *)0x1AC2,
    (unsigned int)L"[Proxy] waiting for connect of pipe %#x\n",
    *((const wchar_t **)v6 + 7));
  v31 = *((_QWORD *)v6 + 8);
  v12 = WaitForMultipleObjectsEx(2u, &Handles, 0, 0xFFFFFFFF, 0);
  if ( v12 )
  {
    if ( v12 != 1 )
      wil::details::in1diag3::Throw_GetLastError(
        retaddr,
        (void *)0x1ADF,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
        v13);
    CEventSem::Reset((CRequestServer *)((char *)v6 + 64));
    goto LABEL_11;
  }
  v25 = (wchar_t *)this;
  EnterCriticalSection((LPCRITICAL_SECTION)this);
  v5 = 2;
  CancelIo(*((HANDLE *)v6 + 7));
  CRequestQueue::LokTryToAddToCache(this, (struct CServerItem *)&v24, 1);
  _InterlockedDecrement((volatile signed __int32 *)this + 28);
  LeaveCriticalSection((LPCRITICAL_SECTION)this);
  if ( v24 )
  {
    CRequestServer::Release(v24);
    v24 = 0;
  }
LABEL_18:
  SearchIndexerDebug::Error(
    (wchar_t *)L"onecoreuap\\base\\appmodel\\search\\tquery\\cifrmwrk\\srequest.cxx",
    (const wchar_t *)0x1B4A,
    (unsigned int)L"[Proxy] Out of CRequestQueue::DoWork reason=%d",
    (const wchar_t *)v5);
  CRequestQueue::ProcessWorkitems((LPCRITICAL_SECTION)this);
}

```

## disassembly

```asm
0x1800683a0  mov     rax, rsp
0x1800683a3  mov     [rax+18h], r8
0x1800683a7  mov     [rax+10h], rdx
0x1800683ab  mov     [rax+8], rcx
0x1800683af  push    rbx
0x1800683b0  push    rsi
0x1800683b1  push    rdi
0x1800683b2  push    r13
0x1800683b4  push    r14
0x1800683b6  push    r15
0x1800683b8  sub     rsp, 88h
0x1800683bf  mov     rdi, rcx
0x1800683c2  mov     r13, rcx
0x1800683c5  mov     [rsp+0B8h+var_40], rcx
0x1800683ca  xor     esi, esi
0x1800683cc  mov     [rax-48h], rsi
0x1800683d0  mov     rcx, [rcx+158h]; hHandle
0x1800683d7  mov     [rax-50h], rcx
0x1800683db  mov     r15d, esi
0x1800683de  mov     [rsp+0B8h+var_60], esi
0x1800683e2  mov     r14d, esi
0x1800683e5  mov     [rsp+0B8h+var_78], esi
0x1800683e9  mov     [rsp+0B8h+var_5C], 1
0x1800683f1  mov     [rsp+0B8h+arg_18], sil
0x1800683f9  mov     rbx, rsi
0x1800683fc  mov     [rsp+0B8h+var_70], rbx
0x180068401  test    r15d, r15d
0x180068404  jnz     loc_180068558
0x18006840a  mov     eax, [rdi+70h]
0x18006840d  mov     [rsp+0B8h+bAlertable], eax
0x180068411  mov     r9d, [rdi+88h]; wchar_t *
0x180068418  lea     r8, aProxyCachedBus; "[Proxy] cached/busy items: %d / %d\n"
0x18006841f  mov     edx, 1A6Dh; wchar_t *
0x180068424  lea     rcx, aOnecoreuapBase_192; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18006842b  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x180068430  mov     rcx, rdi; lpCriticalSection
0x180068433  call    cs:__imp_EnterCriticalSection
0x180068439  mov     eax, [rdi+88h]
0x18006843f  test    eax, eax
0x180068441  jz      short loc_180068464
0x180068443  dec     eax
0x180068445  mov     [rdi+88h], eax
0x18006844b  mov     ecx, eax
0x18006844d  mov     rax, [rdi+78h]
0x180068451  mov     rbx, [rax+rcx*8]
0x180068455  mov     [rsp+0B8h+var_70], rbx
0x18006845a  mov     [rax+rcx*8], rsi
0x18006845e  mov     [rbx+130h], esi
0x180068464  cmp     [rsp+0B8h+var_5C], esi
0x180068468  jnz     loc_1800687D9
0x18006846e  mov     rcx, rdi; lpCriticalSection
0x180068471  call    cs:__imp_LeaveCriticalSection
0x180068477  mov     [rsp+0B8h+var_5C], esi
0x18006847b  test    rbx, rbx
0x18006847e  jz      loc_1800685CF
0x180068484  call    cs:__imp_GetTickCount
0x18006848a  mov     [rbx+120h], eax
0x180068490  lock inc dword ptr [rdi+70h]
0x180068494  lea     rcx, [rbx+18h]; lpOverlapped
0x180068498  call    ?Connect@CPipeServer@@QEAAHXZ; CPipeServer::Connect(void)
0x18006849d  test    eax, eax
0x18006849f  jnz     short loc_1800684FA
0x1800684a1  mov     r9, [rbx+38h]; wchar_t *
0x1800684a5  lea     r8, aProxyWaitingFo; "[Proxy] waiting for connect of pipe %#x"...
0x1800684ac  mov     edx, 1AC2h; wchar_t *
0x1800684b1  lea     rcx, aOnecoreuapBase_192; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800684b8  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1800684bd  mov     rax, [rbx+40h]
0x1800684c1  mov     [rsp+0B8h+var_48], rax
0x1800684c6  mov     [rsp+0B8h+bAlertable], esi; bAlertable
0x1800684ca  or      r9d, 0FFFFFFFFh; dwMilliseconds
0x1800684ce  xor     r8d, r8d; bWaitAll
0x1800684d1  lea     rdx, [rsp+0B8h+Handles]; lpHandles
0x1800684d6  lea     ecx, [r8+2]; nCount
0x1800684da  call    cs:__imp_WaitForMultipleObjectsEx
0x1800684e0  test    eax, eax
0x1800684e2  jz      loc_1800686FC
0x1800684e8  cmp     eax, 1
0x1800684eb  jnz     loc_180068825
0x1800684f1  lea     rcx, [rbx+40h]; this
0x1800684f5  call    ?Reset@CEventSem@@QEAAXXZ; CEventSem::Reset(void)
0x1800684fa  lea     rcx, [rdi+0C8h]; this
0x180068501  mov     rdx, rbx; struct PWorkItem *
0x180068504  call    ?Add@CWorkQueue@@QEAAXPEAVPWorkItem@@@Z; CWorkQueue::Add(PWorkItem *)
0x180068509  mov     rbx, rsi
0x18006850c  mov     [rsp+0B8h+var_70], rbx
0x180068511  mov     eax, [rdi+0B0h]
0x180068517  cmp     [rdi+70h], eax
0x18006851a  jnz     short loc_180068524
0x18006851c  mov     rcx, rdi; lpCriticalSection
0x18006851f  call    ?WrestReqServerFromIdleClient@CRequestQueue@@AEAAXXZ; CRequestQueue::WrestReqServerFromIdleClient(void)
0x180068524  mov     r15d, esi
0x180068527  mov     [rsp+0B8h+var_60], esi
0x18006852b  test    rbx, rbx
0x18006852e  jnz     loc_1800686C5
0x180068534  cmp     [rdi+0A0h], esi
0x18006853a  jnz     short loc_180068595
0x18006853c  cmp     [rdi+0A4h], esi
0x180068542  jnz     short loc_180068595
0x180068544  cmp     [rsp+0B8h+arg_18], sil
0x18006854c  jnz     short loc_180068595
0x18006854e  mov     rcx, [rsp+0B8h+Handles]
0x180068553  jmp     loc_1800683F9
0x180068558  xor     r8d, r8d; bAlertable
0x18006855b  lea     edx, [r8+1]; dwMilliseconds
0x18006855f  call    cs:__imp_WaitForSingleObjectEx
0x180068565  cmp     eax, 102h
0x18006856a  jz      loc_18006840A
0x180068570  mov     r14d, 1
0x180068576  mov     [rsp+0B8h+var_78], r14d
0x18006857b  mov     rcx, rdi; lpCriticalSection
0x18006857e  call    cs:__imp_EnterCriticalSection
0x180068584  mov     [rdi+8Ch], esi
0x18006858a  mov     rcx, rdi; lpCriticalSection
0x18006858d  call    cs:__imp_LeaveCriticalSection
0x180068593  jmp     short loc_18006859B
0x180068595  cmp     r14d, 2
0x180068599  jnz     short loc_18006857B
0x18006859b  mov     r9d, r14d; wchar_t *
0x18006859e  lea     r8, aProxyOutOfCreq; "[Proxy] Out of CRequestQueue::DoWork re"...
0x1800685a5  mov     edx, 1B4Ah; wchar_t *
0x1800685aa  lea     rcx, aOnecoreuapBase_192; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800685b1  call    ?Error@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Error(wchar_t const *,uint,wchar_t const *,...)
0x1800685b6  mov     rcx, rdi; lpCriticalSection
0x1800685b9  call    ?ProcessWorkitems@CRequestQueue@@AEAAXXZ; CRequestQueue::ProcessWorkitems(void)
0x1800685be  add     rsp, 88h
0x1800685c5  pop     r15
0x1800685c7  pop     r14
0x1800685c9  pop     r13
0x1800685cb  pop     rdi
0x1800685cc  pop     rsi
0x1800685cd  pop     rbx
0x1800685ce  retn
0x1800685cf  mov     eax, [rdi+0B0h]
0x1800685d5  cmp     [rdi+70h], eax
0x1800685d8  jl      short loc_1800685E8
0x1800685da  test    rbx, rbx
0x1800685dd  jnz     loc_180068484
0x1800685e3  jmp     loc_1802B8D2E
0x1800685e8  lea     rcx, [rdi+0C8h]
0x1800685ef  mov     rax, [rsp+0B8h+arg_8]
0x1800685f7  mov     [rsp+0B8h+var_88], rax; int *
0x1800685fc  mov     rax, [rdi+160h]
0x180068603  mov     [rsp+0B8h+var_90], rax; struct CEventSem *
0x180068608  mov     qword ptr [rsp+0B8h+bAlertable], rcx; int
0x18006860d  mov     r9, rdi; struct CRequestQueue *
0x180068610  mov     r8d, [rdi+0ACh]; unsigned int
0x180068617  mov     rdx, [rdi+170h]; wchar_t *
0x18006861e  lea     rcx, [rsp+0B8h+var_70]; this
0x180068623  call    ?Create@CServerItem@@QEAAXPEB_WKAEAVCRequestQueue@@AEAVCWorkQueue@@AEAVCEventSem@@AEAH@Z; CServerItem::Create(wchar_t const *,ulong,CRequestQueue &,CWorkQueue &,CEventSem &,int &)
0x180068628  cmp     [r13+198h], rsi
0x18006862f  jz      loc_1800686F2
0x180068635  cmp     [rdi+1B0h], sil
0x18006863c  jnz     loc_1800686F2
0x180068642  mov     [rsp+0B8h+arg_18], 1
0x18006864a  mov     [rsp+0B8h+var_78], 3
0x180068652  mov     [rsp+0B8h+var_58], esi
0x180068656  mov     [rsp+0B8h+var_54], sil
0x18006865b  mov     [rsp+0B8h+var_68], rsi
0x180068660  lea     r8, [rsp+0B8h+var_68]
0x180068665  mov     edx, 55F1h
0x18006866a  mov     rcx, [rsp+0B8h+arg_10]
0x180068672  call    cs:__imp_CmsCreateActivity
0x180068678  mov     rcx, [rsp+0B8h]; this
0x180068680  test    eax, eax
0x180068682  js      loc_18006875A
0x180068688  call    _lambda_091d258e7c64cc5df55390d9ad9943cc___operator_void____cdecl____CMS_ACTIVITY_NOTIFICATION___void___
0x18006868d  mov     rdx, rax
0x180068690  lea     r8, [rsp+0B8h+var_58]
0x180068695  mov     rcx, [rsp+0B8h+var_68]
0x18006869a  call    cs:__imp_CmsStartActivityAsync
0x1800686a0  mov     rcx, [rsp+0B8h]; this
0x1800686a8  test    eax, eax
0x1800686aa  jns     loc_1800687E8
0x1800686b0  mov     r9d, eax; char *
0x1800686b3  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800686ba  mov     edx, 1A98h; void *
0x1800686bf  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800686c5  mov     rcx, rbx; this
0x1800686c8  call    ?Release@CRequestServer@@UEAAXXZ; CRequestServer::Release(void)
0x1800686cd  jmp     loc_180068534
0x1800686d2  mov     byte ptr [rdi+1B0h], 1
0x1800686d9  mov     [rsp+0B8h+arg_18], sil
0x1800686e1  mov     r14d, esi
0x1800686e4  mov     [rsp+0B8h+var_78], esi
0x1800686e8  lea     rcx, [rsp+0B8h+var_68]
0x1800686ed  call    ??1?$unique_storage@U?$resource_policy@PEAX$$A6AXAEAPEAX@Z$1?CloseContainerActivity@ContainerHelperDetails@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (void * &),&ContainerHelperDetails::CloseContainerActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<void *,void (void * &),&ContainerHelperDetails::CloseContainerActivity(void * &),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>(void)
0x1800686f2  mov     rbx, [rsp+0B8h+var_70]
0x1800686f7  jmp     loc_1800685DA
0x1800686fc  mov     [rsp+0B8h+var_68], rdi
0x180068701  mov     rcx, rdi; lpCriticalSection
0x180068704  call    cs:__imp_EnterCriticalSection
0x18006870a  nop
0x18006870b  mov     r14d, 2
0x180068711  mov     [rsp+0B8h+var_78], r14d
0x180068716  mov     rcx, [rbx+38h]; hFile
0x18006871a  call    cs:__imp_CancelIo
0x180068720  lea     r8d, [r14-1]; int
0x180068724  lea     rdx, [rsp+0B8h+var_70]; struct CServerItem *
0x180068729  mov     rcx, rdi; this
0x18006872c  call    ?LokTryToAddToCache@CRequestQueue@@AEAAXAEAVCServerItem@@H@Z; CRequestQueue::LokTryToAddToCache(CServerItem &,int)
0x180068731  lock dec dword ptr [rdi+70h]
0x180068735  mov     rcx, rdi; lpCriticalSection
0x180068738  call    cs:__imp_LeaveCriticalSection
0x18006873e  nop
0x18006873f  mov     rcx, [rsp+0B8h+var_70]; this
0x180068744  test    rcx, rcx
0x180068747  jnz     short loc_18006874E
0x180068749  jmp     loc_18006859B
0x18006874e  call    ?Release@CRequestServer@@UEAAXXZ; CRequestServer::Release(void)
0x180068753  mov     [rsp+0B8h+var_70], rsi
0x180068758  jmp     short loc_180068749
0x18006875a  mov     r9d, eax; char *
0x18006875d  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180068764  mov     edx, 1A89h; void *
0x180068769  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006876e  lea     r8, [rdi+188h]
0x180068775  cmp     qword ptr [rdi+1A0h], 7
0x18006877d  jbe     short loc_180068782
0x18006877f  mov     r8, [r8]
0x180068782  mov     rdx, [rdi+170h]
0x180068789  mov     rcx, [rsp+0B8h+var_68]
0x18006878e  call    cs:__imp_CmsMapNamedPipeToContainer
0x180068794  mov     edx, 80000000h
0x180068799  lea     ecx, [rax+rdx]
0x18006879c  test    edx, ecx
0x18006879e  jnz     loc_1802B8D06
0x1800687a4  cmp     eax, 800700B7h
0x1800687a9  mov     cl, 1
0x1800687ab  jz      loc_1802B8D06
0x1800687b1  mov     r10, [rsp+0B8h]
0x1800687b9  test    cl, cl
0x1800687bb  jz      loc_1800686D2
0x1800687c1  mov     r9d, eax; char *
0x1800687c4  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1800687cb  mov     edx, 1AA0h; void *
0x1800687d0  mov     rcx, r10; this
0x1800687d3  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800687d9  mov     dword ptr [rdi+8Ch], 1
0x1800687e3  jmp     loc_18006846E
0x1800687e8  lea     rcx, [rsp+0B8h+var_58]
0x1800687ed  call    ?wait@?$slim_event_t@$00@wil@@QEAA_NK@Z; wil::slim_event_t<1>::wait(ulong)
0x1800687f2  test    al, al
0x1800687f4  jz      loc_1802B8D0E
0x1800687fa  cmp     [rsp+0B8h+var_54], sil
0x1800687ff  jnz     loc_18006876E
0x180068805  mov     rcx, [rsp+0B8h]; this
0x18006880d  mov     r9d, 800703E3h; char *
0x180068813  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x18006881a  mov     edx, 1AA4h; void *
0x18006881f  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180068825  mov     rcx, [rsp+0B8h]; this
0x18006882d  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x180068834  mov     edx, 1ADFh; void *
0x180068839  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
0x1802b8d06  mov     cl, sil
0x1802b8d09  jmp     loc_1800687B1
0x1802b8d0e  mov     rcx, [rsp+0B8h]; this
0x1802b8d16  mov     r9d, 800705B4h; char *
0x1802b8d1c  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802b8d23  mov     edx, 1AA9h; void *
0x1802b8d28  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1802b8d2e  lea     r8, aProxyWaitForRe; "[Proxy] wait for RequestServer\n"
0x1802b8d35  mov     edx, 1AFBh; wchar_t *
0x1802b8d3a  lea     rcx, aOnecoreuapBase_192; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802b8d41  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1802b8d46  mov     rax, [rdi+150h]
0x1802b8d4d  mov     [rsp+0B8h+var_48], rax
0x1802b8d52  mov     r9d, 2710h
0x1802b8d58  mov     eax, [rdi+0B0h]
0x1802b8d5e  cmp     [rdi+70h], eax
0x1802b8d61  mov     eax, 0FFFFFFFFh
0x1802b8d66  cmovnz  r9d, eax; dwMilliseconds
0x1802b8d6a  mov     [rsp+0B8h+bAlertable], esi; bAlertable
0x1802b8d6e  xor     r8d, r8d; bWaitAll
0x1802b8d71  lea     rdx, [rsp+0B8h+Handles]; lpHandles
0x1802b8d76  lea     ecx, [r8+2]; nCount
0x1802b8d7a  call    cs:__imp_WaitForMultipleObjectsEx
0x1802b8d80  mov     r15d, eax
0x1802b8d83  mov     r9d, eax; wchar_t *
0x1802b8d86  lea     r8, aProxyWfsoexWak; "[Proxy] wfsoex wakeup: %d\n"
0x1802b8d8d  mov     edx, 1B02h; wchar_t *
0x1802b8d92  lea     rcx, aOnecoreuapBase_192; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802b8d99  call    ?Verbose@SearchIndexerDebug@@YAXPEB_WI0ZZ; SearchIndexerDebug::Verbose(wchar_t const *,uint,wchar_t const *,...)
0x1802b8d9e  cmp     r15d, 102h
0x1802b8da5  jz      loc_18006851C
0x1802b8dab  test    r15d, r15d
0x1802b8dae  jnz     short loc_1802B8DC9
0x1802b8db0  lea     r14d, [r15+3]
0x1802b8db4  mov     [rsp+0B8h+var_78], r14d
0x1802b8db9  lea     rcx, [rsp+0B8h+var_70]; this
0x1802b8dbe  call    ?Free@CServerItem@@QEAAXXZ; CServerItem::Free(void)
0x1802b8dc3  nop
0x1802b8dc4  jmp     loc_18006857B
0x1802b8dc9  cmp     r15d, 1
0x1802b8dcd  jz      loc_180068524
0x1802b8dd3  mov     rcx, [rsp+0B8h]; this
0x1802b8ddb  lea     r8, aOnecoreuapBase_303; "onecoreuap\\base\\appmodel\\search\\tqu"...
0x1802b8de2  mov     edx, 1B11h; void *
0x1802b8de7  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
  ... truncated ...
```
