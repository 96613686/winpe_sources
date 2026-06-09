# BfeTimerTracking::InitializeThreadpool(void)

- ea: `0x18005c314`
- end: `0x18005c487`
- name: `?InitializeThreadpool@BfeTimerTracking@@QEAAJXZ`
- size: `371`
- prototype: `__int64 __fastcall(BfeTimerTracking *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x18005f004`

## callees

- `0x1800558e8`
- `0x180055904`
- `0x18005c314`
- `0x18005d444`
- `0x18005ea54`
- `0x18005eaa8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005c38f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005c38f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005c450`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005c450`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005c43e`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005c43e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005c3cd`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005c3cd`

## pseudocode

```c
__int64 __fastcall BfeTimerTracking::InitializeThreadpool(BfeTimerTracking *this)
{
  const char *v1; // r9
  unsigned int LastError; // ebx
  const char *v3; // r9
  PTP_WORK ThreadpoolWork; // [rsp+20h] [rbp-18h] BYREF
  PTP_POOL Threadpool; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  qword_1800EF318 = 0;
  xmmword_1800EF320 = 0;
  xmmword_1800EF330 = 0;
  *(_OWORD *)&pcbe.CleanupGroup = 0;
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.Version = 3;
  pcbe.Pool = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  Threadpool = CreateThreadpool(0);
  if ( Threadpool )
  {
    ThreadpoolWork = CreateThreadpoolWork(_lambda_7557b36167dd5542a5aea2ec9582f86b_::_lambda_invoker_cdecl_, 0, &pcbe);
    if ( ThreadpoolWork )
    {
      wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
        &ptpp,
        Threadpool);
      Threadpool = 0;
      wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(
        &pwk,
        ThreadpoolWork);
      ThreadpoolWork = 0;
      SetThreadpoolThreadMinimum(ptpp, 1u);
      SetThreadpoolThreadMaximum(ptpp, 1u);
      pcbe.Pool = ptpp;
      wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&ThreadpoolWork);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x67,
                    (unsigned int)"onecore\\net\\netio\\wfp\\bfe\\svc\\bfe_timer\\lib\\bfe_timer.cpp",
                    v3);
      wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&public: static void wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(&ThreadpoolWork);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x5D,
                  (unsigned int)"onecore\\net\\netio\\wfp\\bfe\\svc\\bfe_timer\\lib\\bfe_timer.cpp",
                  v1);
  }
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(&Threadpool);
  return LastError;
}

```

## disassembly

```asm
0x18005c314  mov     [rsp+arg_0], rbx
0x18005c319  push    rdi
0x18005c31a  sub     rsp, 30h
0x18005c31e  xorps   xmm0, xmm0
0x18005c321  mov     cs:qword_1800EF318, 0
0x18005c32c  xorps   xmm1, xmm1
0x18005c32f  movdqa  cs:xmmword_1800EF320, xmm0
0x18005c337  xor     ecx, ecx; reserved
0x18005c339  movdqa  cs:xmmword_1800EF330, xmm1
0x18005c341  movdqa  xmmword ptr cs:pcbe.CleanupGroup, xmm0
0x18005c349  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm1
0x18005c351  mov     cs:pcbe.Version, 3
0x18005c35b  mov     cs:pcbe.Pool, 0
0x18005c366  mov     cs:pcbe.FinalizationCallback, 0
0x18005c371  mov     dword ptr cs:pcbe.u, 0
0x18005c37b  mov     cs:pcbe.CallbackPriority, 1
0x18005c385  mov     cs:pcbe.Size, 48h ; 'H'
0x18005c38f  call    cs:__imp_CreateThreadpool
0x18005c395  mov     [rsp+38h+var_10], rax
0x18005c39a  mov     rdi, rax
0x18005c39d  test    rax, rax
0x18005c3a0  jnz     short loc_18005C3BD
0x18005c3a2  mov     rcx, [rsp+38h]; this
0x18005c3a7  lea     r8, aOnecoreNetNeti; "onecore\\net\\netio\\wfp\\bfe\\svc\\bfe"...
0x18005c3ae  lea     edx, [rax+5Dh]; void *
0x18005c3b1  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c3b6  mov     ebx, eax
0x18005c3b8  jmp     loc_18005C470
0x18005c3bd  lea     r8, pcbe; pcbe
0x18005c3c4  xor     edx, edx; pv
0x18005c3c6  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7557b36167dd5542a5aea2ec9582f86b_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005c3cd  call    cs:__imp_CreateThreadpoolWork
0x18005c3d3  mov     [rsp+38h+var_18], rax
0x18005c3d8  mov     rbx, rax
0x18005c3db  test    rax, rax
0x18005c3de  jnz     short loc_18005C402
0x18005c3e0  mov     rcx, [rsp+38h]; this
0x18005c3e5  lea     r8, aOnecoreNetNeti; "onecore\\net\\netio\\wfp\\bfe\\svc\\bfe"...
0x18005c3ec  lea     edx, [rax+67h]; void *
0x18005c3ef  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005c3f4  lea     rcx, [rsp+38h+var_18]
0x18005c3f9  mov     ebx, eax
0x18005c3fb  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18005c400  jmp     short loc_18005C470
0x18005c402  mov     rdx, rdi
0x18005c405  lea     rcx, ptpp
0x18005c40c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18005c411  mov     rdx, rbx
0x18005c414  mov     [rsp+38h+var_10], 0
0x18005c41d  lea     rcx, pwk
0x18005c424  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18005c429  mov     rcx, cs:ptpp; ptpp
0x18005c430  mov     edx, 1; cthrdMic
0x18005c435  mov     [rsp+38h+var_18], 0
0x18005c43e  call    cs:__imp_SetThreadpoolThreadMinimum
0x18005c444  mov     rcx, cs:ptpp; ptpp
0x18005c44b  mov     edx, 1; cthrdMost
0x18005c450  call    cs:__imp_SetThreadpoolThreadMaximum
0x18005c456  mov     rax, cs:ptpp
0x18005c45d  lea     rcx, [rsp+38h+var_18]
0x18005c462  mov     cs:pcbe.Pool, rax
0x18005c469  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18005c46e  xor     ebx, ebx
0x18005c470  lea     rcx, [rsp+38h+var_10]
0x18005c475  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)
0x18005c47a  mov     eax, ebx
0x18005c47c  mov     rbx, [rsp+38h+arg_0]
0x18005c481  add     rsp, 30h
0x18005c485  pop     rdi
0x18005c486  retn
```
