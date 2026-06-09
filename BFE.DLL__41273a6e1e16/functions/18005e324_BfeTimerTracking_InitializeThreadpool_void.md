# BfeTimerTracking::InitializeThreadpool(void)

- ea: `0x18005e324`
- end: `0x18005e4b0`
- name: `?InitializeThreadpool@BfeTimerTracking@@QEAAJXZ`
- size: `396`
- prototype: `__int64 __fastcall(BfeTimerTracking *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, loader_planting`

## callers

- `0x180061294`

## callees

- `0x18005772c`
- `0x18005774c`
- `0x18005e324`
- `0x18005f4e4`
- `0x180060c8c`
- `0x180060ce8`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005e39f`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpool` at `0x18005e39f`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005e472`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMaximum` at `0x18005e472`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005e45a`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolThreadMinimum` at `0x18005e45a`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005e3e3`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18005e3e3`

## pseudocode

```c
__int64 __fastcall BfeTimerTracking::InitializeThreadpool(BfeTimerTracking *this)
{
  const char *v1; // r9
  unsigned int LastError; // ebx
  const char *v3; // r9
  PTP_WORK ThreadpoolWork; // [rsp+20h] [rbp-18h] BYREF
  PTP_POOL v6[2]; // [rsp+28h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  qword_1800F2428 = 0;
  xmmword_1800F2430 = 0;
  xmmword_1800F2440 = 0;
  *(_OWORD *)&pcbe.CleanupGroup = 0;
  *(_OWORD *)&pcbe.RaceDll = 0;
  pcbe.Version = 3;
  pcbe.Pool = 0;
  pcbe.FinalizationCallback = 0;
  pcbe.u.Flags = 0;
  pcbe.CallbackPriority = TP_CALLBACK_PRIORITY_NORMAL;
  pcbe.Size = 72;
  v6[0] = CreateThreadpool(0);
  if ( v6[0] )
  {
    ThreadpoolWork = CreateThreadpoolWork(_lambda_7557b36167dd5542a5aea2ec9582f86b_::_lambda_invoker_cdecl_, 0, &pcbe);
    if ( ThreadpoolWork )
    {
      wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(
        &ptpp,
        v6[0]);
      v6[0] = 0;
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
  wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&void CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(v6);
  return LastError;
}

```

## disassembly

```asm
0x18005e324  mov     [rsp+arg_0], rbx
0x18005e329  push    rdi
0x18005e32a  sub     rsp, 30h
0x18005e32e  xorps   xmm0, xmm0
0x18005e331  mov     cs:qword_1800F2428, 0
0x18005e33c  xorps   xmm1, xmm1
0x18005e33f  movdqa  cs:xmmword_1800F2430, xmm0
0x18005e347  xor     ecx, ecx; reserved
0x18005e349  movdqa  cs:xmmword_1800F2440, xmm1
0x18005e351  movdqa  xmmword ptr cs:pcbe.CleanupGroup, xmm0
0x18005e359  movdqa  xmmword ptr cs:pcbe.RaceDll, xmm1
0x18005e361  mov     cs:pcbe.Version, 3
0x18005e36b  mov     cs:pcbe.Pool, 0
0x18005e376  mov     cs:pcbe.FinalizationCallback, 0
0x18005e381  mov     dword ptr cs:pcbe.u, 0
0x18005e38b  mov     cs:pcbe.CallbackPriority, 1
0x18005e395  mov     cs:pcbe.Size, 48h ; 'H'
0x18005e39f  call    cs:__imp_CreateThreadpool
0x18005e3a6  nop     dword ptr [rax+rax+00h]
0x18005e3ab  mov     [rsp+38h+var_10], rax
0x18005e3b0  mov     rdi, rax
0x18005e3b3  test    rax, rax
0x18005e3b6  jnz     short loc_18005E3D3
0x18005e3b8  mov     rcx, [rsp+38h]; this
0x18005e3bd  lea     r8, aOnecoreNetNeti; "onecore\\net\\netio\\wfp\\bfe\\svc\\bfe"...
0x18005e3c4  lea     edx, [rax+5Dh]; void *
0x18005e3c7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e3cc  mov     ebx, eax
0x18005e3ce  jmp     loc_18005E498
0x18005e3d3  lea     r8, pcbe; pcbe
0x18005e3da  xor     edx, edx; pv
0x18005e3dc  lea     rcx, ?_lambda_invoker_cdecl_@_lambda_7557b36167dd5542a5aea2ec9582f86b_@@CA@PEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18005e3e3  call    cs:__imp_CreateThreadpoolWork
0x18005e3ea  nop     dword ptr [rax+rax+00h]
0x18005e3ef  mov     [rsp+38h+var_18], rax
0x18005e3f4  mov     rbx, rax
0x18005e3f7  test    rax, rax
0x18005e3fa  jnz     short loc_18005E41E
0x18005e3fc  mov     rcx, [rsp+38h]; this
0x18005e401  lea     r8, aOnecoreNetNeti; "onecore\\net\\netio\\wfp\\bfe\\svc\\bfe"...
0x18005e408  lea     edx, [rax+67h]; void *
0x18005e40b  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18005e410  lea     rcx, [rsp+38h+var_18]
0x18005e415  mov     ebx, eax
0x18005e417  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18005e41c  jmp     short loc_18005E498
0x18005e41e  mov     rdx, rdi
0x18005e421  lea     rcx, ptpp
0x18005e428  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_POOL@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::reset(_TP_POOL *)
0x18005e42d  mov     rdx, rbx
0x18005e430  mov     [rsp+38h+var_10], 0
0x18005e439  lea     rcx, pwk
0x18005e440  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_WORK@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::reset(_TP_WORK *)
0x18005e445  mov     rcx, cs:ptpp; ptpp
0x18005e44c  mov     edx, 1; cthrdMic
0x18005e451  mov     [rsp+38h+var_18], 0
0x18005e45a  call    cs:__imp_SetThreadpoolThreadMinimum
0x18005e461  nop     dword ptr [rax+rax+00h]
0x18005e466  mov     rcx, cs:ptpp; ptpp
0x18005e46d  mov     edx, 1; cthrdMost
0x18005e472  call    cs:__imp_SetThreadpoolThreadMaximum
0x18005e479  nop     dword ptr [rax+rax+00h]
0x18005e47e  mov     rax, cs:ptpp
0x18005e485  lea     rcx, [rsp+38h+var_18]
0x18005e48a  mov     cs:pcbe.Pool, rax
0x18005e491  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_WORK@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolWork@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_WORK *,void (*)(_TP_WORK *),&wil::details::DestroyThreadPoolWork<0>::Destroy(_TP_WORK *),wistd::integral_constant<unsigned __int64,0>,_TP_WORK *,_TP_WORK *,0,std::nullptr_t>>(void)
0x18005e496  xor     ebx, ebx
0x18005e498  lea     rcx, [rsp+38h+var_10]
0x18005e49d  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_POOL@@P6AXPEAU1@@Z$1?CloseThreadpool@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_POOL *,void (*)(_TP_POOL *),&CloseThreadpool(_TP_POOL *),wistd::integral_constant<unsigned __int64,0>,_TP_POOL *,_TP_POOL *,0,std::nullptr_t>>(void)
0x18005e4a2  mov     eax, ebx
0x18005e4a4  mov     rbx, [rsp+38h+arg_0]
0x18005e4a9  add     rsp, 30h
0x18005e4ad  pop     rdi
0x18005e4ae  retn
```
