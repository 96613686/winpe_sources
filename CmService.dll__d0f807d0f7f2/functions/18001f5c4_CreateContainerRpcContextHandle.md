# CreateContainerRpcContextHandle

- ea: `0x18001f5c4`
- end: `0x18001f965`
- name: `CreateContainerRpcContextHandle`
- size: `929`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, loader_planting, service_task`

## callers

- `0x180018120`
- `0x18001fd1c`

## callees

- `0x180004bd0`
- `0x180004bf4`
- `0x180004fc4`
- `0x180007fec`
- `0x180008414`
- `0x180009884`
- `0x18000da68`
- `0x18000da88`
- `0x18001f5c4`
- `0x18004b318`

## import_xrefs

- `ntdll!NtDeleteWnfStateName` at `0x18001f6df`
- `ntdll!NtDeleteWnfStateName` at `0x18001f7c2`
- `ntdll!NtDeleteWnfStateName` at `0x18001f7e5`
- `ntdll!NtDeleteWnfStateName` at `0x18001f6df`
- `ntdll!NtDeleteWnfStateName` at `0x18001f7c2`
- `ntdll!NtDeleteWnfStateName` at `0x18001f7e5`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f664`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f664`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f6ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f776`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f7fb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f6ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f776`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f7fb`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7b1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f765`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001f7b1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f784`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f7d0`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f784`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001f7d0`

## string_xrefs

- `0x18001f6ff`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001f8d0`: `onecore\base\gendrv\silos\clem\service\api.cpp`
- `0x18001f903`: `onecore\base\gendrv\silos\clem\service\api.cpp`

## pseudocode

```c
__int64 __fastcall CreateContainerRpcContextHandle(
        Container::Manager::Core::ContainerHandle **a1,
        void *a2,
        int a3,
        char a4,
        Container::Manager::Service::ContainerRpcContextHandle **a5)
{
  int v8; // ebp
  char *v9; // r14
  HLOCAL v10; // rsi
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v12; // r9
  int v13; // edi
  int v14; // eax
  Container::Manager::Core::ContainerHandle *v15; // rbx
  struct _TP_WORK **v17; // rsi
  struct _TP_WORK *v18; // rbp
  DWORD LastError; // edi
  __int64 v20; // rsi
  DWORD v21; // edi
  Container::Manager::Core::ContainerHandle **v22; // rax
  Container::Manager::Core::ContainerHandle **v23; // rbx
  Container::Manager::Core::ContainerHandle *v24; // rdx
  Container::Manager::Core::ContainerHandle *v25; // rdi
  Container::Manager::Core::ContainerHandle *v26; // rdi
  Container::Manager::Service::ContainerRpcContextHandle *v27; // rdi
  Container::Manager::Core::ContainerHandle *v28; // rbx
  Container::Manager::Core::ContainerHandle *v29; // rbx
  int v30; // [rsp+20h] [rbp-58h]
  char v31; // [rsp+28h] [rbp-50h] BYREF
  __int64 v32; // [rsp+30h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]

  v30 = a3;
  v8 = a3;
  v9 = (char *)operator new(0x70u, (const struct std::nothrow_t *)&std::nothrow);
  if ( v9 )
  {
    *(_QWORD *)v9 = 0;
    *((_QWORD *)v9 + 1) = 0;
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 5) = 0;
    *((_QWORD *)v9 + 6) = 0;
    *((_QWORD *)v9 + 7) = 0;
    *((_QWORD *)v9 + 8) = 0;
    *((_QWORD *)v9 + 9) = 0;
    *((_QWORD *)v9 + 10) = 0;
    *((_QWORD *)v9 + 12) = 0;
    v9[104] = 0;
    *((_QWORD *)v9 + 11) = 0;
    v10 = pSid;
    ThreadpoolWork = CreateThreadpoolWork(
                       Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::WnfPublisherThread,
                       v9,
                       0);
    if ( ThreadpoolWork )
    {
      v32 = 0;
      v14 = Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(v10, a2, &v32);
      v13 = v14;
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2B4,
          (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
          (const char *)(unsigned int)v14,
          v30);
        NtDeleteWnfStateName(&v32);
        CloseThreadpoolWork(ThreadpoolWork);
LABEL_7:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x66,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
          (const char *)(unsigned int)v13,
          v30);
        Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(v9);
        operator delete(v9, (const struct std::nothrow_t *)0x70);
        v15 = *a1;
        *a1 = 0;
        if ( v15 )
        {
          Container::Manager::Core::ContainerHandle::~ContainerHandle(v15);
          operator delete(v15, (const struct std::nothrow_t *)0x58);
        }
        return (unsigned int)v13;
      }
      v17 = (struct _TP_WORK **)(v9 + 96);
      if ( v9 + 96 != &v31 )
      {
        v18 = *v17;
        if ( *v17 )
        {
          LastError = GetLastError();
          CloseThreadpoolWork(v18);
          SetLastError(LastError);
        }
        *v17 = ThreadpoolWork;
        ThreadpoolWork = 0;
      }
      if ( v9 + 88 != (char *)&v32 )
      {
        v20 = v32;
        v32 = 0;
        v21 = GetLastError();
        NtDeleteWnfStateName(v9 + 88);
        SetLastError(v21);
        *((_QWORD *)v9 + 11) = v20;
      }
      NtDeleteWnfStateName(&v32);
      if ( ThreadpoolWork )
        CloseThreadpoolWork(ThreadpoolWork);
      v8 = v30;
    }
    else
    {
      v13 = wil::details::in1diag3::Return_GetLastError(
              retaddr,
              (void *)0x2B0,
              (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\CslNotification.h",
              v12);
      if ( v13 < 0 )
        goto LABEL_7;
    }
    v22 = (Container::Manager::Core::ContainerHandle **)operator new(
                                                          0x18u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
    v23 = v22;
    if ( v22 )
    {
      *v22 = 0;
      v22[1] = 0;
      *((_DWORD *)v22 + 4) = 0;
      *((_BYTE *)v22 + 20) = 0;
      v24 = *a1;
      *a1 = 0;
      v25 = *v22;
      *v22 = v24;
      if ( v25 )
      {
        Container::Manager::Core::ContainerHandle::~ContainerHandle(v25);
        operator delete(v25, (const struct std::nothrow_t *)0x58);
      }
      v26 = v23[1];
      v23[1] = (Container::Manager::Core::ContainerHandle *)v9;
      if ( v26 )
      {
        Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(v26);
        operator delete(v26, (const struct std::nothrow_t *)0x70);
      }
      *((_DWORD *)v23 + 4) = v8;
      *((_BYTE *)v23 + 20) = a4;
      v27 = *a5;
      *a5 = (Container::Manager::Service::ContainerRpcContextHandle *)v23;
      if ( v27 )
      {
        Container::Manager::Service::ContainerRpcContextHandle::~ContainerRpcContextHandle(v27);
        operator delete(v27, (const struct std::nothrow_t *)0x18);
      }
      v28 = *a1;
      *a1 = 0;
      if ( v28 )
      {
        Container::Manager::Core::ContainerHandle::~ContainerHandle(v28);
        operator delete(v28, (const struct std::nothrow_t *)0x58);
      }
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x6C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)0x8007000ELL,
      v30);
    Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(v9);
    operator delete(v9, (const struct std::nothrow_t *)0x70);
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x63,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\service\\api.cpp",
      (const char *)0x8007000ELL,
      v30);
  }
  v29 = *a1;
  *a1 = 0;
  if ( v29 )
  {
    Container::Manager::Core::ContainerHandle::~ContainerHandle(v29);
    operator delete(v29, (const struct std::nothrow_t *)0x58);
  }
  return 2147942414LL;
}

```

## disassembly

```asm
0x18001f5c4  mov     [rsp+arg_10], rbx
0x18001f5c9  push    rbp
0x18001f5ca  push    rsi
0x18001f5cb  push    rdi
0x18001f5cc  push    r12
0x18001f5ce  push    r13
0x18001f5d0  push    r14
0x18001f5d2  push    r15
0x18001f5d4  sub     rsp, 40h
0x18001f5d8  mov     rax, cs:__security_cookie
0x18001f5df  xor     rax, rsp
0x18001f5e2  mov     [rsp+78h+var_40], rax
0x18001f5e7  mov     r12, [rsp+78h+arg_20]
0x18001f5ef  mov     rdi, rdx
0x18001f5f2  mov     r15, rcx
0x18001f5f5  mov     [rsp+78h+var_58], r8d; int
0x18001f5fa  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f601  mov     ecx, 70h ; 'p'; unsigned __int64
0x18001f606  mov     r13b, r9b
0x18001f609  mov     ebp, r8d
0x18001f60c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f611  xor     esi, esi
0x18001f613  mov     r14, rax
0x18001f616  test    rax, rax
0x18001f619  jz      loc_18001F8FE
0x18001f61f  xor     eax, eax
0x18001f621  lea     rcx, ?WnfPublisherThread@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001f628  mov     [r14], rax
0x18001f62b  xor     r8d, r8d; pcbe
0x18001f62e  mov     [r14+8], rax
0x18001f632  mov     rdx, r14; pv
0x18001f635  mov     [r14+10h], rax
0x18001f639  mov     [r14+28h], rsi
0x18001f63d  mov     [r14+30h], rsi
0x18001f641  mov     [r14+38h], rsi
0x18001f645  mov     [r14+40h], rsi
0x18001f649  mov     [r14+48h], rsi
0x18001f64d  mov     [r14+50h], rax
0x18001f651  mov     [r14+60h], rsi
0x18001f655  mov     [r14+68h], sil
0x18001f659  mov     [r14+58h], rax
0x18001f65d  mov     rsi, cs:pSid
0x18001f664  call    cs:__imp_CreateThreadpoolWork
0x18001f66b  nop     dword ptr [rax+rax+00h]
0x18001f670  mov     rbx, rax
0x18001f673  test    rax, rax
0x18001f676  jnz     short loc_18001F69C
0x18001f678  mov     rcx, [rsp+78h]; this
0x18001f67d  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001f684  mov     edx, 2B0h; void *
0x18001f689  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18001f68e  xor     esi, esi
0x18001f690  mov     edi, eax
0x18001f692  test    eax, eax
0x18001f694  jns     loc_18001F80B
0x18001f69a  jmp     short loc_18001F6FA
0x18001f69c  lea     r8, [rsp+78h+var_48]
0x18001f6a1  mov     [rsp+78h+var_48], 0
0x18001f6aa  mov     rdx, rdi; PSID
0x18001f6ad  mov     rcx, rsi; pSid
0x18001f6b0  call    ?CreateWnfStateName@?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@CAJPEAX0AEAV?$unique_struct@U_WNF_STATE_NAME@@P6AJPEBU1@@Z$1?NtDeleteWnfStateName@@YAJ0@Z$$T$0A@@wil@@@Z; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::CreateWnfStateName(void *,void *,wil::unique_struct<_WNF_STATE_NAME,long (*)(_WNF_STATE_NAME const *),&NtDeleteWnfStateName(_WNF_STATE_NAME const *),std::nullptr_t,0> &)
0x18001f6b5  xor     esi, esi
0x18001f6b7  mov     edi, eax
0x18001f6b9  test    eax, eax
0x18001f6bb  jns     loc_18001F74F
0x18001f6c1  mov     rcx, [rsp+78h]; this
0x18001f6c6  lea     r8, aOnecoreBaseGen_5; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18001f6cd  mov     r9d, eax; char *
0x18001f6d0  mov     edx, 2B4h; void *
0x18001f6d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f6da  lea     rcx, [rsp+78h+var_48]
0x18001f6df  call    cs:__imp_NtDeleteWnfStateName
0x18001f6e6  nop     dword ptr [rax+rax+00h]
0x18001f6eb  mov     rcx, rbx; pwk
0x18001f6ee  call    cs:__imp_CloseThreadpoolWork
0x18001f6f5  nop     dword ptr [rax+rax+00h]
0x18001f6fa  mov     rcx, [rsp+78h]; this
0x18001f6ff  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001f706  mov     r9d, edi; char *
0x18001f709  mov     edx, 66h ; 'f'; void *
0x18001f70e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f713  mov     rcx, r14
0x18001f716  call    ??1?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x18001f71b  mov     edx, 70h ; 'p'; struct std::nothrow_t *
0x18001f720  mov     rcx, r14; void *
0x18001f723  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f728  mov     rbx, [r15]
0x18001f72b  mov     [r15], rsi
0x18001f72e  test    rbx, rbx
0x18001f731  jz      short loc_18001F748
0x18001f733  mov     rcx, rbx; this
0x18001f736  call    ??1ContainerHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ContainerHandle::~ContainerHandle(void)
0x18001f73b  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18001f740  mov     rcx, rbx; void *
0x18001f743  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f748  mov     eax, edi
0x18001f74a  jmp     loc_18001F93F
0x18001f74f  lea     rsi, [r14+60h]
0x18001f753  lea     rax, [rsp+78h+var_50]
0x18001f758  cmp     rsi, rax
0x18001f75b  jz      short loc_18001F795
0x18001f75d  mov     rbp, [rsi]
0x18001f760  test    rbp, rbp
0x18001f763  jz      short loc_18001F790
0x18001f765  call    cs:__imp_GetLastError
0x18001f76c  nop     dword ptr [rax+rax+00h]
0x18001f771  mov     rcx, rbp; pwk
0x18001f774  mov     edi, eax
0x18001f776  call    cs:__imp_CloseThreadpoolWork
0x18001f77d  nop     dword ptr [rax+rax+00h]
0x18001f782  mov     ecx, edi; dwErrCode
0x18001f784  call    cs:__imp_SetLastError
0x18001f78b  nop     dword ptr [rax+rax+00h]
0x18001f790  mov     [rsi], rbx
0x18001f793  xor     ebx, ebx
0x18001f795  lea     rbp, [r14+58h]
0x18001f799  lea     rax, [rsp+78h+var_48]
0x18001f79e  cmp     rbp, rax
0x18001f7a1  jz      short loc_18001F7E0
0x18001f7a3  mov     rsi, [rsp+78h+var_48]
0x18001f7a8  mov     [rsp+78h+var_48], 0
0x18001f7b1  call    cs:__imp_GetLastError
0x18001f7b8  nop     dword ptr [rax+rax+00h]
0x18001f7bd  mov     rcx, rbp
0x18001f7c0  mov     edi, eax
0x18001f7c2  call    cs:__imp_NtDeleteWnfStateName
0x18001f7c9  nop     dword ptr [rax+rax+00h]
0x18001f7ce  mov     ecx, edi; dwErrCode
0x18001f7d0  call    cs:__imp_SetLastError
0x18001f7d7  nop     dword ptr [rax+rax+00h]
0x18001f7dc  mov     [rbp+0], rsi
0x18001f7e0  lea     rcx, [rsp+78h+var_48]
0x18001f7e5  call    cs:__imp_NtDeleteWnfStateName
0x18001f7ec  nop     dword ptr [rax+rax+00h]
0x18001f7f1  xor     esi, esi
0x18001f7f3  test    rbx, rbx
0x18001f7f6  jz      short loc_18001F807
0x18001f7f8  mov     rcx, rbx; pwk
0x18001f7fb  call    cs:__imp_CloseThreadpoolWork
0x18001f802  nop     dword ptr [rax+rax+00h]
0x18001f807  mov     ebp, [rsp+78h+var_58]
0x18001f80b  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f812  mov     ecx, 18h; unsigned __int64
0x18001f817  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f81c  mov     rbx, rax
0x18001f81f  test    rax, rax
0x18001f822  jz      loc_18001F8CB
0x18001f828  mov     [rax], rsi
0x18001f82b  mov     [rax+8], rsi
0x18001f82f  mov     [rax+10h], esi
0x18001f832  mov     [rax+14h], sil
0x18001f836  mov     rdx, [r15]
0x18001f839  mov     [r15], rsi
0x18001f83c  mov     rdi, [rax]
0x18001f83f  mov     [rax], rdx
0x18001f842  test    rdi, rdi
0x18001f845  jz      short loc_18001F85C
0x18001f847  mov     rcx, rdi; this
0x18001f84a  call    ??1ContainerHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ContainerHandle::~ContainerHandle(void)
0x18001f84f  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18001f854  mov     rcx, rdi; void *
0x18001f857  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f85c  mov     rdi, [rbx+8]
0x18001f860  mov     [rbx+8], r14
0x18001f864  test    rdi, rdi
0x18001f867  jz      short loc_18001F87E
0x18001f869  mov     rcx, rdi
0x18001f86c  call    ??1?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x18001f871  mov     edx, 70h ; 'p'; struct std::nothrow_t *
0x18001f876  mov     rcx, rdi; void *
0x18001f879  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f87e  mov     [rbx+10h], ebp
0x18001f881  mov     [rbx+14h], r13b
0x18001f885  mov     rdi, [r12]
0x18001f889  mov     [r12], rbx
0x18001f88d  test    rdi, rdi
0x18001f890  jz      short loc_18001F8A7
0x18001f892  mov     rcx, rdi; this
0x18001f895  call    ??1ContainerRpcContextHandle@Service@Manager@Container@@QEAA@XZ; Container::Manager::Service::ContainerRpcContextHandle::~ContainerRpcContextHandle(void)
0x18001f89a  mov     edx, 18h; struct std::nothrow_t *
0x18001f89f  mov     rcx, rdi; void *
0x18001f8a2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f8a7  mov     rbx, [r15]
0x18001f8aa  mov     [r15], rsi
0x18001f8ad  test    rbx, rbx
0x18001f8b0  jz      short loc_18001F8C7
0x18001f8b2  mov     rcx, rbx; this
0x18001f8b5  call    ??1ContainerHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ContainerHandle::~ContainerHandle(void)
0x18001f8ba  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18001f8bf  mov     rcx, rbx; void *
0x18001f8c2  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f8c7  xor     eax, eax
0x18001f8c9  jmp     short loc_18001F93F
0x18001f8cb  mov     rcx, [rsp+78h]; this
0x18001f8d0  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001f8d7  mov     r9d, 8007000Eh; char *
0x18001f8dd  mov     edx, 6Ch ; 'l'; void *
0x18001f8e2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f8e7  mov     rcx, r14
0x18001f8ea  call    ??1?$OutOfProcNotificationRelay@U_CMS_ACTIVITY_NOTIFICATION@@$01@Csl@@QEAA@XZ; Csl::OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>::~OutOfProcNotificationRelay<_CMS_ACTIVITY_NOTIFICATION,2>(void)
0x18001f8ef  mov     edx, 70h ; 'p'; struct std::nothrow_t *
0x18001f8f4  mov     rcx, r14; void *
0x18001f8f7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f8fc  jmp     short loc_18001F91A
0x18001f8fe  mov     rcx, [rsp+78h]; this
0x18001f903  lea     r8, aOnecoreBaseGen_70; "onecore\\base\\gendrv\\silos\\clem\\ser"...
0x18001f90a  mov     r9d, 8007000Eh; char *
0x18001f910  mov     edx, 63h ; 'c'; void *
0x18001f915  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f91a  mov     rbx, [r15]
0x18001f91d  mov     [r15], rsi
0x18001f920  test    rbx, rbx
0x18001f923  jz      short loc_18001F93A
0x18001f925  mov     rcx, rbx; this
0x18001f928  call    ??1ContainerHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ContainerHandle::~ContainerHandle(void)
0x18001f92d  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x18001f932  mov     rcx, rbx; void *
0x18001f935  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001f93a  mov     eax, 8007000Eh
0x18001f93f  mov     rcx, [rsp+78h+var_40]
0x18001f944  xor     rcx, rsp; StackCookie
0x18001f947  call    __security_check_cookie
0x18001f94c  mov     rbx, [rsp+78h+arg_10]
0x18001f954  add     rsp, 40h
0x18001f958  pop     r15
0x18001f95a  pop     r14
0x18001f95c  pop     r13
0x18001f95e  pop     r12
0x18001f960  pop     rdi
0x18001f961  pop     rsi
0x18001f962  pop     rbp
0x18001f963  retn
```
