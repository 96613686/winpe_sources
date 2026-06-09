# CreateProcessRpcContextHandle

- ea: `0x18001f96c`
- end: `0x18001fd13`
- name: `CreateProcessRpcContextHandle`
- size: `935`
- prototype: ``
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x180019360`
- `0x18001ce20`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x1800080ac`
- `0x1800088c8`
- `0x180009884`
- `0x18000da68`
- `0x18000da88`
- `0x18001f96c`
- `0x18002c110`
- `0x1801908d0`
- `0x180190e1c`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18001fafb`
- `ntdll!NtDeleteWnfStateName` at `0x18001fbcb`
- `ntdll!NtDeleteWnfStateName` at `0x18001fbed`
- `ntdll!NtDeleteWnfStateName` at `0x18001fafb`
- `ntdll!NtDeleteWnfStateName` at `0x18001fbcb`
- `ntdll!NtDeleteWnfStateName` at `0x18001fbed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001fa8d`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001fa8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fb0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fb82`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fc04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fb0a`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fb82`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fc04`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbba`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fb71`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001fbba`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fb90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fbd9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fb90`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001fbd9`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fb49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fc78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fce4`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fa10`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fb49`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fc78`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18001fce4`

## string_xrefs

- `0x18001f9b3`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001f9ea`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001fb1a`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001fc8c`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001fcc4`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
__int64 __fastcall CreateProcessRpcContextHandle(Container::Manager::Service::ProcessRpcContextHandle **a1, void *a2)
{
  int v3; // eax
  unsigned int v4; // ebx
  int CurrentThreadUserSid; // eax
  char *v7; // r15
  HLOCAL v8; // rsi
  PTP_WORK ThreadpoolWork; // rax
  const char *v10; // r9
  HLOCAL v11; // rbx
  struct _TP_WORK *v12; // rdi
  int v13; // esi
  int WnfStateName; // eax
  struct _TP_WORK **v15; // r14
  struct _TP_WORK *v16; // r12
  DWORD LastError; // esi
  __int64 v18; // r14
  DWORD v19; // esi
  Container::Manager::Service::ProcessRpcContextHandle *v20; // rax
  Container::Manager::Service::ProcessRpcContextHandle *v21; // rsi
  HLOCAL v22; // rcx
  HLOCAL hMem; // [rsp+20h] [rbp-38h] BYREF
  __int64 v24; // [rsp+28h] [rbp-30h] BYREF
  char v25; // [rsp+30h] [rbp-28h]
  char v26; // [rsp+38h] [rbp-20h] BYREF
  __int64 v27; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]

  hMem = 0;
  v24 = 0;
  v25 = 0;
  v3 = Container::Manager::Rpc::Impersonator::Impersonate((Container::Manager::Rpc::Impersonator *)&v24, a2);
  v4 = v3;
  if ( v3 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D1,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)(unsigned int)v3,
      (int)hMem);
    Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v24);
    return v4;
  }
  CurrentThreadUserSid = Csl::GetCurrentThreadUserSid(&hMem);
  v4 = CurrentThreadUserSid;
  if ( CurrentThreadUserSid < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D3,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)(unsigned int)CurrentThreadUserSid,
      (int)hMem);
    Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v24);
    if ( hMem )
      LocalFree(hMem);
    return v4;
  }
  Container::Manager::Rpc::Impersonator::~Impersonator((Container::Manager::Rpc::Impersonator *)&v24);
  v7 = (char *)operator new(0x68u, (const struct std::nothrow_t *)&std::nothrow);
  if ( !v7 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7DB,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)0x8007000ELL,
      (int)hMem);
    v22 = hMem;
    if ( hMem )
      goto LABEL_33;
    return 2147942414LL;
  }
  *(_QWORD *)v7 = 0;
  *((_QWORD *)v7 + 1) = 0;
  *((_QWORD *)v7 + 2) = 0;
  *((_QWORD *)v7 + 4) = 0;
  *((_QWORD *)v7 + 5) = 0;
  *((_QWORD *)v7 + 6) = 0;
  *((_QWORD *)v7 + 7) = 0;
  *((_QWORD *)v7 + 8) = 0;
  *((_QWORD *)v7 + 9) = 0;
  *((_QWORD *)v7 + 11) = 0;
  v7[96] = 0;
  *((_QWORD *)v7 + 10) = 0;
  v8 = pSid;
  ThreadpoolWork = CreateThreadpoolWork(
                     Csl::OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>::WnfPublisherThread,
                     v7,
                     0);
  v11 = hMem;
  v12 = ThreadpoolWork;
  if ( ThreadpoolWork )
  {
    v27 = 0;
    WnfStateName = Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(v8, hMem);
    v13 = WnfStateName;
    if ( WnfStateName < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2B4,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
        (const char *)(unsigned int)WnfStateName,
        (int)hMem);
      NtDeleteWnfStateName(&v27);
      CloseThreadpoolWork(v12);
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x7DE,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
        (const char *)(unsigned int)v13,
        (int)hMem);
      Csl::OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>(v7);
      operator delete(v7, (const struct std::nothrow_t *)0x68);
      if ( v11 )
        LocalFree(v11);
      return (unsigned int)v13;
    }
    v15 = (struct _TP_WORK **)(v7 + 88);
    if ( v7 + 88 != &v26 )
    {
      v16 = *v15;
      if ( *v15 )
      {
        LastError = GetLastError();
        CloseThreadpoolWork(v16);
        SetLastError(LastError);
      }
      *v15 = v12;
      v12 = 0;
    }
    if ( v7 + 80 != (char *)&v27 )
    {
      v18 = v27;
      v27 = 0;
      v19 = GetLastError();
      NtDeleteWnfStateName(v7 + 80);
      SetLastError(v19);
      *((_QWORD *)v7 + 10) = v18;
    }
    NtDeleteWnfStateName(&v27);
    if ( v12 )
      CloseThreadpoolWork(v12);
  }
  else
  {
    v13 = wil::details::in1diag3::Return_GetLastError(
            retaddr,
            (void *)0x2B0,
            (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
            v10);
    if ( v13 < 0 )
      goto LABEL_13;
  }
  v20 = (Container::Manager::Service::ProcessRpcContextHandle *)operator new(
                                                                  0x10u,
                                                                  (const struct std::nothrow_t *)&std::nothrow);
  if ( !v20 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7E4,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)0x8007000ELL,
      (int)hMem);
    Csl::OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>(v7);
    operator delete(v7, (const struct std::nothrow_t *)0x68);
    if ( v11 )
    {
      v22 = v11;
LABEL_33:
      LocalFree(v22);
    }
    return 2147942414LL;
  }
  *(_QWORD *)v20 = 0;
  *((_QWORD *)v20 + 1) = v7;
  v21 = *a1;
  *a1 = v20;
  if ( v21 )
  {
    Container::Manager::Service::ProcessRpcContextHandle::~ProcessRpcContextHandle(v21);
    operator delete(v21, (const struct std::nothrow_t *)0x10);
  }
  if ( v11 )
    LocalFree(v11);
  return 0;
}

```

## disassembly

```asm
0x18001f96c  push    rbp
0x18001f96e  push    rbx
0x18001f96f  push    rsi
0x18001f970  push    rdi
0x18001f971  push    r12
0x18001f973  push    r13
0x18001f975  push    r14
0x18001f977  push    r15
0x18001f979  mov     rbp, rsp
0x18001f97c  sub     rsp, 58h
0x18001f980  mov     rax, cs:__security_cookie
0x18001f987  xor     rax, rsp
0x18001f98a  mov     [rbp+var_10], rax
0x18001f98e  xor     r14d, r14d
0x18001f991  mov     r13, rcx
0x18001f994  lea     rcx, [rbp+var_30]; this
0x18001f998  mov     [rbp+hMem], r14
0x18001f99c  mov     [rbp+var_30], r14
0x18001f9a0  mov     [rbp+var_28], r14b
0x18001f9a4  call    ?Impersonate@Impersonator@Rpc@Manager@Container@@QEAAJPEAX@Z; Container::Manager::Rpc::Impersonator::Impersonate(void *)
0x18001f9a9  mov     ebx, eax
0x18001f9ab  test    eax, eax
0x18001f9ad  jns     short loc_18001F9D7
0x18001f9af  mov     rcx, [rbp+40h]; this
0x18001f9b3  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001f9ba  mov     r9d, eax; char *
0x18001f9bd  mov     edx, 7D1h; void *
0x18001f9c2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9c7  lea     rcx, [rbp+var_30]; this
0x18001f9cb  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x18001f9d0  mov     eax, ebx
0x18001f9d2  jmp     loc_18001FCF5
0x18001f9d7  lea     rcx, [rbp+hMem]
0x18001f9db  call    ?GetCurrentThreadUserSid@Csl@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@@wil@@@Z; Csl::GetCurrentThreadUserSid(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<void *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,void *,void *,0,std::nullptr_t>>> &)
0x18001f9e0  mov     ebx, eax
0x18001f9e2  test    eax, eax
0x18001f9e4  jns     short loc_18001FA1E
0x18001f9e6  mov     rcx, [rbp+40h]; this
0x18001f9ea  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001f9f1  mov     r9d, eax; char *
0x18001f9f4  mov     edx, 7D3h; void *
0x18001f9f9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9fe  lea     rcx, [rbp+var_30]; this
0x18001fa02  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x18001fa07  mov     rcx, [rbp+hMem]; hMem
0x18001fa0b  test    rcx, rcx
0x18001fa0e  jz      short loc_18001F9D0
0x18001fa10  call    cs:__imp_LocalFree
0x18001fa17  nop     dword ptr [rax+rax+00h]
0x18001fa1c  jmp     short loc_18001F9D0
0x18001fa1e  lea     rcx, [rbp+var_30]; this
0x18001fa22  call    ??1Impersonator@Rpc@Manager@Container@@QEAA@XZ; Container::Manager::Rpc::Impersonator::~Impersonator(void)
0x18001fa27  mov     r12d, 68h ; 'h'
0x18001fa2d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fa34  mov     ecx, r12d; unsigned __int64
0x18001fa37  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fa3c  mov     r15, rax
0x18001fa3f  test    rax, rax
0x18001fa42  jz      loc_18001FCC0
0x18001fa48  xor     eax, eax
0x18001fa4a  lea     rcx, ?WnfPublisherThread@?$OutOfProcNotificationRelay@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001fa51  mov     [r15], rax
0x18001fa54  xor     r8d, r8d; pcbe
0x18001fa57  mov     [r15+8], rax
0x18001fa5b  mov     rdx, r15; pv
0x18001fa5e  mov     [r15+10h], rax
0x18001fa62  mov     [r15+20h], r14
0x18001fa66  mov     [r15+28h], r14
0x18001fa6a  mov     [r15+30h], r14
0x18001fa6e  mov     [r15+38h], r14
0x18001fa72  mov     [r15+40h], r14
0x18001fa76  mov     [r15+48h], rax
0x18001fa7a  mov     [r15+58h], r14
0x18001fa7e  mov     [r15+60h], r14b
0x18001fa82  mov     [r15+50h], rax
0x18001fa86  mov     rsi, cs:pSid
0x18001fa8d  call    cs:__imp_CreateThreadpoolWork
0x18001fa94  nop     dword ptr [rax+rax+00h]
0x18001fa99  mov     rbx, [rbp+hMem]
0x18001fa9d  mov     rdi, rax
0x18001faa0  test    rax, rax
0x18001faa3  jnz     short loc_18001FAC6
0x18001faa5  mov     rcx, [rbp+40h]; this
0x18001faa9  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001fab0  mov     edx, 2B0h; void *
0x18001fab5  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001faba  mov     esi, eax
0x18001fabc  test    eax, eax
0x18001fabe  jns     loc_18001FC16
0x18001fac4  jmp     short loc_18001FB16
0x18001fac6  lea     r8, [rbp+var_18]
0x18001faca  mov     [rbp+var_18], r14
0x18001face  mov     rdx, rbx; PSID
0x18001fad1  mov     rcx, rsi; pSid
0x18001fad4  call    ?CreateWnfStateName@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAJPEAX0AEAV?$unique_struct@U_WNF_STATE_NAME@@P6AJPEBU1@@Z$1?NtDeleteWnfStateName@@YAJ0@Z$$T$0A@@wil@@@Z; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(void *,void *,wil::unique_struct<_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME const *),&NtDeleteWnfStateName(_WNF_STATE_NAME const *),std::nullptr_t,0> &)
0x18001fad9  mov     esi, eax
0x18001fadb  test    eax, eax
0x18001fadd  jns     short loc_18001FB5C
0x18001fadf  mov     rcx, [rbp+40h]; this
0x18001fae3  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001faea  mov     r9d, eax; char *
0x18001faed  mov     edx, 2B4h; void *
0x18001faf2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001faf7  lea     rcx, [rbp+var_18]
0x18001fafb  call    cs:__imp_NtDeleteWnfStateName
0x18001fb02  nop     dword ptr [rax+rax+00h]
0x18001fb07  mov     rcx, rdi; pwk
0x18001fb0a  call    cs:__imp_CloseThreadpoolWork
0x18001fb11  nop     dword ptr [rax+rax+00h]
0x18001fb16  mov     rcx, [rbp+40h]; this
0x18001fb1a  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fb21  mov     r9d, esi; char *
0x18001fb24  mov     edx, 7DEh; void *
0x18001fb29  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fb2e  mov     rcx, r15
0x18001fb31  call    ??1?$OutOfProcNotificationRelay@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>(void)
0x18001fb36  mov     rdx, r12; struct std::nothrow_t *
0x18001fb39  mov     rcx, r15; void *
0x18001fb3c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fb41  test    rbx, rbx
0x18001fb44  jz      short loc_18001FB55
0x18001fb46  mov     rcx, rbx; hMem
0x18001fb49  call    cs:__imp_LocalFree
0x18001fb50  nop     dword ptr [rax+rax+00h]
0x18001fb55  mov     eax, esi
0x18001fb57  jmp     loc_18001FCF5
0x18001fb5c  lea     r14, [r15+58h]
0x18001fb60  lea     rax, [rbp+var_20]
0x18001fb64  cmp     r14, rax
0x18001fb67  jz      short loc_18001FBA1
0x18001fb69  mov     r12, [r14]
0x18001fb6c  test    r12, r12
0x18001fb6f  jz      short loc_18001FB9C
0x18001fb71  call    cs:__imp_GetLastError
0x18001fb78  nop     dword ptr [rax+rax+00h]
0x18001fb7d  mov     rcx, r12; pwk
0x18001fb80  mov     esi, eax
0x18001fb82  call    cs:__imp_CloseThreadpoolWork
0x18001fb89  nop     dword ptr [rax+rax+00h]
0x18001fb8e  mov     ecx, esi; dwErrCode
0x18001fb90  call    cs:__imp_SetLastError
0x18001fb97  nop     dword ptr [rax+rax+00h]
0x18001fb9c  mov     [r14], rdi
0x18001fb9f  xor     edi, edi
0x18001fba1  lea     r12, [r15+50h]
0x18001fba5  lea     rax, [rbp+var_18]
0x18001fba9  cmp     r12, rax
0x18001fbac  jz      short loc_18001FBE9
0x18001fbae  mov     r14, [rbp+var_18]
0x18001fbb2  mov     [rbp+var_18], 0
0x18001fbba  call    cs:__imp_GetLastError
0x18001fbc1  nop     dword ptr [rax+rax+00h]
0x18001fbc6  mov     rcx, r12
0x18001fbc9  mov     esi, eax
0x18001fbcb  call    cs:__imp_NtDeleteWnfStateName
0x18001fbd2  nop     dword ptr [rax+rax+00h]
0x18001fbd7  mov     ecx, esi; dwErrCode
0x18001fbd9  call    cs:__imp_SetLastError
0x18001fbe0  nop     dword ptr [rax+rax+00h]
0x18001fbe5  mov     [r12], r14
0x18001fbe9  lea     rcx, [rbp+var_18]
0x18001fbed  call    cs:__imp_NtDeleteWnfStateName
0x18001fbf4  nop     dword ptr [rax+rax+00h]
0x18001fbf9  xor     r14d, r14d
0x18001fbfc  test    rdi, rdi
0x18001fbff  jz      short loc_18001FC10
0x18001fc01  mov     rcx, rdi; pwk
0x18001fc04  call    cs:__imp_CloseThreadpoolWork
0x18001fc0b  nop     dword ptr [rax+rax+00h]
0x18001fc10  mov     r12d, 68h ; 'h'
0x18001fc16  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001fc1d  mov     ecx, 10h; unsigned __int64
0x18001fc22  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001fc27  mov     rdi, rax
0x18001fc2a  test    rax, rax
0x18001fc2d  jz      short loc_18001FC88
0x18001fc2f  mov     [rax], r14
0x18001fc32  mov     [rax+8], r15
0x18001fc36  test    r14, r14
0x18001fc39  jz      short loc_18001FC4E
0x18001fc3b  mov     rcx, r14
0x18001fc3e  call    ??1?$OutOfProcNotificationRelay@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>(void)
0x18001fc43  mov     rdx, r12; struct std::nothrow_t *
0x18001fc46  mov     rcx, r14; void *
0x18001fc49  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc4e  mov     rsi, [r13+0]
0x18001fc52  mov     [r13+0], rdi
0x18001fc56  test    rsi, rsi
0x18001fc59  jz      short loc_18001FC70
0x18001fc5b  mov     rcx, rsi; this
0x18001fc5e  call    ??1ProcessRpcContextHandle@Service@Manager@Container@@QEAA@XZ; Container::Manager::Service::ProcessRpcContextHandle::~ProcessRpcContextHandle(void)
0x18001fc63  mov     edx, 10h; struct std::nothrow_t *
0x18001fc68  mov     rcx, rsi; void *
0x18001fc6b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fc70  test    rbx, rbx
0x18001fc73  jz      short loc_18001FC84
0x18001fc75  mov     rcx, rbx; hMem
0x18001fc78  call    cs:__imp_LocalFree
0x18001fc7f  nop     dword ptr [rax+rax+00h]
0x18001fc84  xor     eax, eax
0x18001fc86  jmp     short loc_18001FCF5
0x18001fc88  mov     rcx, [rbp+40h]; this
0x18001fc8c  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fc93  mov     r9d, 8007000Eh; char *
0x18001fc99  mov     edx, 7E4h; void *
0x18001fc9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fca3  mov     rcx, r15
0x18001fca6  call    ??1?$OutOfProcNotificationRelay@U_CMS_PROCESS_NOTIFICATION@@$00@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>::~OutOfProcNotificationRelay<_CMS_PROCESS_NOTIFICATION,1>(void)
0x18001fcab  mov     rdx, r12; struct std::nothrow_t *
0x18001fcae  mov     rcx, r15; void *
0x18001fcb1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001fcb6  test    rbx, rbx
0x18001fcb9  jz      short loc_18001FCF0
0x18001fcbb  mov     rcx, rbx
0x18001fcbe  jmp     short loc_18001FCE4
0x18001fcc0  mov     rcx, [rbp+40h]; this
0x18001fcc4  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001fccb  mov     r9d, 8007000Eh; char *
0x18001fcd1  mov     edx, 7DBh; void *
0x18001fcd6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001fcdb  mov     rcx, [rbp+hMem]; hMem
0x18001fcdf  test    rcx, rcx
0x18001fce2  jz      short loc_18001FCF0
0x18001fce4  call    cs:__imp_LocalFree
0x18001fceb  nop     dword ptr [rax+rax+00h]
0x18001fcf0  mov     eax, 8007000Eh
0x18001fcf5  mov     rcx, [rbp+var_10]
0x18001fcf9  xor     rcx, rsp; StackCookie
0x18001fcfc  call    __security_check_cookie
0x18001fd01  add     rsp, 58h
0x18001fd05  pop     r15
0x18001fd07  pop     r14
0x18001fd09  pop     r13
0x18001fd0b  pop     r12
0x18001fd0d  pop     rdi
0x18001fd0e  pop     rsi
0x18001fd0f  pop     rbx
0x18001fd10  pop     rbp
0x18001fd11  retn
```
