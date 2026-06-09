# Container::Manager::Support::ProxyDaemon::Shutdown(void)

- ea: `0x180113644`
- end: `0x180113867`
- name: `?Shutdown@ProxyDaemon@Support@Manager@Container@@QEAAXXZ`
- size: `547`
- prototype: `void __fastcall(Container::Manager::Support::ProxyDaemon *__hidden this)`
- caller_count: `2`
- callee_count: `9`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800786dc`
- `0x180099984`

## callees

- `0x18000a10c`
- `0x18000da68`
- `0x180016658`
- `0x180016718`
- `0x1800262c4`
- `0x18002ba5c`
- `0x180042b58`
- `0x180113644`
- `0x180113870`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18011381e`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18011381e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18011367e`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x18011367e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180113667`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180113667`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801136a4`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1801136a4`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180113727`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180113727`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180113706`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180113706`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113693`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180113693`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801136b2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1801136b2`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18011377d`
- `api-ms-win-core-processthreads-l1-1-0!SetThreadToken` at `0x18011377d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801137d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801137d1`
- `USERENV!DeleteAppContainerProfile` at `0x1801137f4`
- `USERENV!DeleteAppContainerProfile` at `0x1801137f4`

## string_xrefs

- `0x180113792`: `onecore\base\gendrv\silos\csl\lib\CslSecurity.h`
- `0x180113845`: `onecore\base\gendrv\silos\csl\lib\CslSecurity.h`

## pseudocode

```c
void __fastcall Container::Manager::Support::ProxyDaemon::Shutdown(Container::Manager::Support::ProxyDaemon *this)
{
  struct _TP_WAIT *v2; // rcx
  char v3; // si
  struct _TP_WAIT *v4; // rbp
  DWORD LastError; // ebx
  void *v6; // rbx
  __int128 v7; // xmm6
  __int64 v8; // xmm0_8
  unsigned int v9; // r8d
  const char *v10; // r9
  DWORD v11; // eax
  const char *v12; // r9
  const char *v13; // r9
  int v14; // eax
  struct _PROCESS_INFORMATION *v15; // rdx
  unsigned int v16; // r8d
  const char *v17; // r9
  int v18; // eax
  const char *v19; // r9
  int v20[4]; // [rsp+20h] [rbp-58h] BYREF
  __int64 v21; // [rsp+30h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v2 = (struct _TP_WAIT *)*((_QWORD *)this + 11);
  if ( v2 )
  {
    SetThreadpoolWait(v2, 0, 0);
    v3 = 1;
    WaitForThreadpoolWaitCallbacks(*((PTP_WAIT *)this + 11), 1);
    v4 = (struct _TP_WAIT *)*((_QWORD *)this + 11);
    if ( v4 )
    {
      LastError = GetLastError();
      CloseThreadpoolWait(v4);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 11) = 0;
    v6 = (void *)*((_QWORD *)this + 10);
    *((_QWORD *)this + 10) = 0;
    *((_QWORD *)this + 12) = 0;
    *((_QWORD *)this + 13) = 0;
    v7 = *(_OWORD *)((char *)this + 24);
    v8 = *((_QWORD *)this + 5);
    *(_OWORD *)((char *)this + 24) = 0;
    *((_QWORD *)this + 5) = 0;
    *(_OWORD *)v20 = v7;
    v21 = v8;
    if ( !SetEvent(v6) )
      wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA01, v9, v10);
    v11 = WaitForSingleObjectEx((HANDLE)v7, 0x3A98u, 0);
    if ( v11 )
    {
      if ( v11 == 258 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2E9,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
          (const char *)0x800705B4LL,
          v20[0]);
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x2EC,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
        v12);
      Container::Manager::Support::ProxyDaemon::Terminate(this);
    }
    if ( SetThreadToken(0, *((HANDLE *)this + 2))
      || (v14 = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x126,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslSecurity.h",
                  v13),
          v3 = 0,
          v14 >= 0) )
    {
      v18 = DeleteAppContainerProfile(*((_QWORD *)this + 6));
      if ( v18 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x2FA,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
          (const char *)(unsigned int)v18,
          v20[0]);
      if ( v3 && !RevertToSelf() )
        wil::details::in1diag3::_FailFast_Unexpected(
          retaddr,
          (void *)0x146,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslSecurity.h",
          v19);
    }
    else
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x2FE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\proxyd\\lib\\cmproxyd.cpp",
        (const char *)(unsigned int)v14,
        v20[0]);
    }
    wil::details::CloseProcessInformation((wil::details *)v20, v15);
    if ( v6 )
    {
      if ( !CloseHandle(v6) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v16, v17);
    }
  }
}

```

## disassembly

```asm
0x180113644  push    rbx
0x180113646  push    rbp
0x180113647  push    rsi
0x180113648  push    rdi
0x180113649  sub     rsp, 58h
0x18011364d  mov     rdi, rcx
0x180113650  movaps  [rsp+78h+var_38], xmm6
0x180113655  mov     rcx, [rcx+58h]; pwa
0x180113659  test    rcx, rcx
0x18011365c  jz      loc_1801137E1
0x180113662  xor     r8d, r8d; pftTimeout
0x180113665  xor     edx, edx; h
0x180113667  call    cs:__imp_SetThreadpoolWait
0x18011366e  nop     dword ptr [rax+rax+00h]
0x180113673  mov     rcx, [rdi+58h]; pwa
0x180113677  mov     esi, 1
0x18011367c  mov     edx, esi; fCancelPendingCallbacks
0x18011367e  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180113685  nop     dword ptr [rax+rax+00h]
0x18011368a  mov     rbp, [rdi+58h]
0x18011368e  test    rbp, rbp
0x180113691  jz      short loc_1801136BE
0x180113693  call    cs:__imp_GetLastError
0x18011369a  nop     dword ptr [rax+rax+00h]
0x18011369f  mov     rcx, rbp; pwa
0x1801136a2  mov     ebx, eax
0x1801136a4  call    cs:__imp_CloseThreadpoolWait
0x1801136ab  nop     dword ptr [rax+rax+00h]
0x1801136b0  mov     ecx, ebx; dwErrCode
0x1801136b2  call    cs:__imp_SetLastError
0x1801136b9  nop     dword ptr [rax+rax+00h]
0x1801136be  mov     qword ptr [rdi+58h], 0
0x1801136c6  xorps   xmm1, xmm1
0x1801136c9  mov     rbx, [rdi+50h]
0x1801136cd  xor     eax, eax
0x1801136cf  mov     qword ptr [rdi+50h], 0
0x1801136d7  mov     rcx, rbx; hEvent
0x1801136da  mov     qword ptr [rdi+60h], 0
0x1801136e2  mov     qword ptr [rdi+68h], 0
0x1801136ea  movups  xmm6, xmmword ptr [rdi+18h]
0x1801136ee  movsd   xmm0, qword ptr [rdi+28h]
0x1801136f3  movups  xmmword ptr [rdi+18h], xmm1
0x1801136f7  mov     [rdi+28h], rax
0x1801136fb  movups  xmmword ptr [rsp+78h+var_58], xmm6; int
0x180113700  movsd   [rsp+78h+var_48], xmm0
0x180113706  call    cs:__imp_SetEvent
0x18011370d  nop     dword ptr [rax+rax+00h]
0x180113712  test    eax, eax
0x180113714  jz      loc_180113857
0x18011371a  xor     r8d, r8d; bAlertable
0x18011371d  mov     edx, 3A98h; dwMilliseconds
0x180113722  movq    rcx, xmm6; hHandle
0x180113727  call    cs:__imp_WaitForSingleObjectEx
0x18011372e  nop     dword ptr [rax+rax+00h]
0x180113733  lea     rbp, aOnecoreBaseGen_3; "onecore\\base\\gendrv\\silos\\clem\\pro"...
0x18011373a  test    eax, eax
0x18011373c  jz      short loc_180113777
0x18011373e  cmp     eax, 102h
0x180113743  jnz     short loc_18011375D
0x180113745  mov     rcx, [rsp+78h]; this
0x18011374a  mov     r9d, 800705B4h; char *
0x180113750  mov     r8, rbp; unsigned int
0x180113753  mov     edx, 2E9h; void *
0x180113758  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18011375d  mov     rcx, [rsp+78h]; this
0x180113762  mov     r8, rbp; unsigned int
0x180113765  mov     edx, 2ECh; void *
0x18011376a  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Log_GetLastError(void *,uint,char const *)
0x18011376f  mov     rcx, rdi; this
0x180113772  call    ?Terminate@ProxyDaemon@Support@Manager@Container@@AEAAXXZ; Container::Manager::Support::ProxyDaemon::Terminate(void)
0x180113777  mov     rdx, [rdi+10h]; Token
0x18011377b  xor     ecx, ecx; Thread
0x18011377d  call    cs:__imp_SetThreadToken
0x180113784  nop     dword ptr [rax+rax+00h]
0x180113789  test    eax, eax
0x18011378b  jnz     short loc_1801137F0
0x18011378d  mov     rcx, [rsp+78h]; this
0x180113792  lea     r8, aOnecoreBaseGen_35; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x180113799  mov     edx, 126h; void *
0x18011379e  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1801137a3  xor     sil, sil
0x1801137a6  test    eax, eax
0x1801137a8  jns     short loc_1801137F0
0x1801137aa  mov     rcx, [rsp+78h]; this
0x1801137af  mov     r9d, eax; char *
0x1801137b2  mov     r8, rbp; unsigned int
0x1801137b5  mov     edx, 2FEh; void *
0x1801137ba  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x1801137bf  lea     rcx, [rsp+78h+var_58]; this
0x1801137c4  call    ?CloseProcessInformation@details@wil@@YAXPEAU_PROCESS_INFORMATION@@@Z; wil::details::CloseProcessInformation(_PROCESS_INFORMATION *)
0x1801137c9  test    rbx, rbx
0x1801137cc  jz      short loc_1801137E1
0x1801137ce  mov     rcx, rbx; hObject
0x1801137d1  call    cs:__imp_CloseHandle
0x1801137d8  nop     dword ptr [rax+rax+00h]
0x1801137dd  test    eax, eax
0x1801137df  jz      short loc_180113830
0x1801137e1  movaps  xmm6, [rsp+78h+var_38]
0x1801137e6  add     rsp, 58h
0x1801137ea  pop     rdi
0x1801137eb  pop     rsi
0x1801137ec  pop     rbp
0x1801137ed  pop     rbx
0x1801137ee  retn
0x1801137f0  mov     rcx, [rdi+30h]
0x1801137f4  call    cs:__imp_DeleteAppContainerProfile
0x1801137fb  nop     dword ptr [rax+rax+00h]
0x180113800  test    eax, eax
0x180113802  jns     short loc_180113819
0x180113804  mov     rcx, [rsp+78h]; this
0x180113809  mov     r9d, eax; char *
0x18011380c  mov     r8, rbp; unsigned int
0x18011380f  mov     edx, 2FAh; void *
0x180113814  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180113819  test    sil, sil
0x18011381c  jz      short loc_1801137BF
0x18011381e  call    cs:__imp_RevertToSelf
0x180113825  nop     dword ptr [rax+rax+00h]
0x18011382a  test    eax, eax
0x18011382c  jz      short loc_180113840
0x18011382e  jmp     short loc_1801137BF
0x180113830  mov     rcx, [rsp+78h]; this
0x180113835  mov     edx, 0A0Bh; void *
0x18011383a  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180113840  mov     rcx, [rsp+78h]; this
0x180113845  lea     r8, aOnecoreBaseGen_35; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18011384c  mov     edx, 146h; void *
0x180113851  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180113857  mov     rcx, [rsp+78h]; this
0x18011385c  mov     edx, 0A01h; void *
0x180113861  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
