# Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample_::_2_::_lambda_1__&_

- ea: `0x180053fb4`
- end: `0x180054185`
- name: `Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void_(__cdecl_)(_TP_WAIT__)_&Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample_::_2_::_lambda_1__&_`
- size: `465`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180053e7c`

## callees

- `0x180006580`
- `0x18000b07c`
- `0x18000e82c`
- `0x180053fb4`
- `0x180057cc0`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800540a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800540f2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800540a9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800540f2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005407a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540d1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005407a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800540d1`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800540dd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1800540dd`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800540a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005413a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x1800540a1`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x18005413a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005408a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005410f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180054123`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005408a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x18005410f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolWait` at `0x180054123`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054098`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054131`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054098`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x180054131`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180053ff0`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWait` at `0x180053ff0`

## string_xrefs

- `0x180054173`: `onecoreuap\termsrv\rdp_bin\win\common\inc\ThreadPoolWait.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Rdp::Utils::TP::details::CThreadPoolWait_wil::unique_any_t_wil::details::unique_storage_wil::details::resource_policy__TP_WAIT___void____cdecl____TP_WAIT_____Rdp::Utils::TP::details::DestroyThreadpoolWait_wistd::integral_constant_unsigned___int64_0___TP_WAIT____TP_WAIT___0_std::nullptr_t_______::RegisterWait__Rdp::Avenc::Ic3::CDsStreamSample::CDsStreamSample_::_2_::_lambda_1____(
        PFILETIME *pv,
        void **a2,
        __int128 *a3,
        struct _TP_CALLBACK_ENVIRON_V3 *a4)
{
  struct _TP_WAIT *ThreadpoolWait; // rdi
  const char *v8; // r9
  __int64 (__fastcall ***v9)(); // rdx
  PTP_WAIT *v10; // rsi
  struct _TP_WAIT *v11; // rbp
  DWORD LastError; // ebx
  HANDLE *v13; // rbx
  void *v14; // r12
  HANDLE v15; // rbp
  DWORD v16; // r13d
  unsigned int v17; // r8d
  const char *v18; // r9
  struct _TP_WAIT *v19; // [rsp+20h] [rbp-98h] BYREF
  __int64 (__fastcall **v20)(); // [rsp+30h] [rbp-88h] BYREF
  __int128 v21; // [rsp+38h] [rbp-80h]
  __int64 (__fastcall ***v22)(); // [rsp+68h] [rbp-50h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+0h]

  ThreadpoolWait = CreateThreadpoolWait(
                     Rdp::Utils::TP::details::CThreadPoolWait<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<_TP_WAIT *,void (*)(_TP_WAIT *),&void Rdp::Utils::TP::details::DestroyThreadpoolWait(_TP_WAIT *),wistd::integral_constant<unsigned __int64,0>,_TP_WAIT *,_TP_WAIT *,0,std::nullptr_t>>>>::OnWaitCallback,
                     pv,
                     a4);
  v19 = ThreadpoolWait;
  if ( !ThreadpoolWait )
    wil::details::in1diag3::Throw_GetLastError(
      retaddr,
      (void *)0x14A,
      (unsigned int)"onecoreuap\\termsrv\\rdp_bin\\win\\common\\inc\\ThreadPoolWait.h",
      v8);
  v20 = off_18008BF30;
  v21 = *a3;
  v22 = &v20;
  std::function<bool (long)>::swap(&v20, pv + 2);
  if ( v22 )
  {
    v9 = &v20;
    LOBYTE(v9) = v22 != &v20;
    ((void (__fastcall *)(__int64 (__fastcall ***)(), __int64 (__fastcall ***)()))(*v22)[4])(v22, v9);
  }
  v10 = (PTP_WAIT *)(pv + 1);
  if ( pv + 1 != (PFILETIME *)&v19 )
  {
    v11 = *v10;
    if ( *v10 )
    {
      LastError = GetLastError();
      SetThreadpoolWait(v11, 0, 0);
      WaitForThreadpoolWaitCallbacks(v11, 1);
      CloseThreadpoolWait(v11);
      SetLastError(LastError);
    }
    *v10 = ThreadpoolWait;
    v19 = 0;
    ThreadpoolWait = 0;
  }
  v13 = (HANDLE *)(pv + 10);
  if ( pv + 10 != (PFILETIME *)a2 )
  {
    v14 = *a2;
    v15 = *v13;
    if ( *v13 )
    {
      v16 = GetLastError();
      if ( !CloseHandle(v15) )
        wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v17, v18);
      SetLastError(v16);
    }
    *v13 = v14;
    *a2 = 0;
  }
  SetThreadpoolWait(*v10, *v13, pv[24]);
  if ( ThreadpoolWait )
  {
    SetThreadpoolWait(ThreadpoolWait, 0, 0);
    WaitForThreadpoolWaitCallbacks(ThreadpoolWait, 1);
    CloseThreadpoolWait(ThreadpoolWait);
  }
}

```

## disassembly

```asm
0x180053fb4  mov     [rsp+arg_10], rbx
0x180053fb9  push    rbp
0x180053fba  push    rsi
0x180053fbb  push    rdi
0x180053fbc  push    r12
0x180053fbe  push    r13
0x180053fc0  push    r14
0x180053fc2  push    r15
0x180053fc4  sub     rsp, 80h
0x180053fcb  mov     rax, cs:__security_cookie
0x180053fd2  xor     rax, rsp
0x180053fd5  mov     [rsp+0B8h+var_48], rax
0x180053fda  mov     rbx, r8
0x180053fdd  mov     r15, rdx
0x180053fe0  mov     r14, rcx
0x180053fe3  mov     r8, r9; pcbe
0x180053fe6  mov     rdx, rcx; pv
0x180053fe9  lea     rcx, ?OnWaitCallback@?$CThreadPoolWait@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_TP_WAIT@@P6AXPEAU1@@Z$1?DestroyThreadpoolWait@details@TP@Utils@Rdp@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@TP@Utils@Rdp@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WAIT@@J@Z; pfnwa
0x180053ff0  call    cs:__imp_CreateThreadpoolWait
0x180053ff6  mov     rdi, rax
0x180053ff9  mov     [rsp+0B8h+var_98], rax
0x180053ffe  xor     eax, eax
0x180054000  test    rdi, rdi
0x180054003  setnz   al
0x180054006  mov     rcx, [rsp+0B8h]; this
0x18005400e  test    eax, eax
0x180054010  jz      loc_180054173
0x180054016  lea     rax, off_18008BF30
0x18005401d  mov     [rsp+0B8h+var_88], rax
0x180054022  movups  xmm0, xmmword ptr [rbx]
0x180054025  movdqu  [rsp+0B8h+var_80], xmm0
0x18005402b  lea     rax, [rsp+0B8h+var_88]
0x180054030  mov     [rsp+0B8h+var_50], rax
0x180054035  lea     rdx, [r14+10h]
0x180054039  lea     rcx, [rsp+0B8h+var_88]
0x18005403e  call    ?swap@?$function@$$A6A_NJ@Z@std@@QEAAXAEAV12@@Z; std::function<bool (long)>::swap(std::function<bool (long)> &)
0x180054043  mov     rcx, [rsp+0B8h+var_50]
0x180054048  test    rcx, rcx
0x18005404b  jz      short loc_180054064
0x18005404d  mov     rax, [rcx]
0x180054050  lea     rdx, [rsp+0B8h+var_88]
0x180054055  cmp     rcx, rdx
0x180054058  setnz   dl
0x18005405b  mov     rax, [rax+20h]
0x18005405f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054064  lea     rsi, [r14+8]
0x180054068  lea     rax, [rsp+0B8h+var_98]
0x18005406d  cmp     rsi, rax
0x180054070  jz      short loc_1800540BD
0x180054072  mov     rbp, [rsi]
0x180054075  test    rbp, rbp
0x180054078  jz      short loc_1800540AF
0x18005407a  call    cs:__imp_GetLastError
0x180054080  mov     ebx, eax
0x180054082  xor     r8d, r8d; pftTimeout
0x180054085  xor     edx, edx; h
0x180054087  mov     rcx, rbp; pwa
0x18005408a  call    cs:__imp_SetThreadpoolWait
0x180054090  mov     edx, 1; fCancelPendingCallbacks
0x180054095  mov     rcx, rbp; pwa
0x180054098  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x18005409e  mov     rcx, rbp; pwa
0x1800540a1  call    cs:__imp_CloseThreadpoolWait
0x1800540a7  mov     ecx, ebx; dwErrCode
0x1800540a9  call    cs:__imp_SetLastError
0x1800540af  mov     [rsi], rdi
0x1800540b2  mov     [rsp+0B8h+var_98], 0
0x1800540bb  xor     edi, edi
0x1800540bd  lea     rbx, [r14+50h]
0x1800540c1  cmp     rbx, r15
0x1800540c4  jz      short loc_180054102
0x1800540c6  mov     r12, [r15]
0x1800540c9  mov     rbp, [rbx]
0x1800540cc  test    rbp, rbp
0x1800540cf  jz      short loc_1800540F8
0x1800540d1  call    cs:__imp_GetLastError
0x1800540d7  mov     r13d, eax
0x1800540da  mov     rcx, rbp; hObject
0x1800540dd  call    cs:__imp_CloseHandle
0x1800540e3  mov     rcx, [rsp+0B8h]; this
0x1800540eb  test    eax, eax
0x1800540ed  jz      short loc_180054168
0x1800540ef  mov     ecx, r13d; dwErrCode
0x1800540f2  call    cs:__imp_SetLastError
0x1800540f8  mov     [rbx], r12
0x1800540fb  mov     qword ptr [r15], 0
0x180054102  mov     r8, [r14+0C0h]; pftTimeout
0x180054109  mov     rdx, [rbx]; h
0x18005410c  mov     rcx, [rsi]; pwa
0x18005410f  call    cs:__imp_SetThreadpoolWait
0x180054115  nop
0x180054116  test    rdi, rdi
0x180054119  jz      short loc_180054140
0x18005411b  xor     r8d, r8d; pftTimeout
0x18005411e  xor     edx, edx; h
0x180054120  mov     rcx, rdi; pwa
0x180054123  call    cs:__imp_SetThreadpoolWait
0x180054129  mov     edx, 1; fCancelPendingCallbacks
0x18005412e  mov     rcx, rdi; pwa
0x180054131  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x180054137  mov     rcx, rdi; pwa
0x18005413a  call    cs:__imp_CloseThreadpoolWait
0x180054140  mov     rcx, [rsp+0B8h+var_48]
0x180054145  xor     rcx, rsp; StackCookie
0x180054148  call    __security_check_cookie
0x18005414d  mov     rbx, [rsp+0B8h+arg_10]
0x180054155  add     rsp, 80h
0x18005415c  pop     r15
0x18005415e  pop     r14
0x180054160  pop     r13
0x180054162  pop     r12
0x180054164  pop     rdi
0x180054165  pop     rsi
0x180054166  pop     rbp
0x180054167  retn
0x180054168  mov     edx, 0A0Bh; void *
0x18005416d  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
0x180054173  lea     r8, aOnecoreuapTerm_21; "onecoreuap\\termsrv\\rdp_bin\\win\\comm"...
0x18005417a  mov     edx, 14Ah; void *
0x18005417f  call    ?Throw_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::Throw_GetLastError(void *,uint,char const *)
```
