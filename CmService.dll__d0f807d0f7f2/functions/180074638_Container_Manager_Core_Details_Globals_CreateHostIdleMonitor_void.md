# Container::Manager::Core::Details::Globals::CreateHostIdleMonitor(void)

- ea: `0x180074638`
- end: `0x1800748d9`
- name: `?CreateHostIdleMonitor@Globals@Details@Core@Manager@Container@@QEAAJXZ`
- size: `673`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::Globals *__hidden this)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180073dd8`
- `0x1800748e0`

## callees

- `0x180004bf4`
- `0x18000da68`
- `0x18000da88`
- `0x18000dab0`
- `0x1800471dc`
- `0x180074638`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800746ed`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x1800746ed`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074779`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800747da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074867`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074779`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x1800747da`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180074867`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800747c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074811`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800747c9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180074811`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800747e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180074830`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800747e8`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180074830`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x180074735`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmRegister` at `0x180074735`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18007476a`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180074822`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180074853`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x18007476a`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180074822`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmUnregister` at `0x180074853`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::Globals::CreateHostIdleMonitor(
        Container::Manager::Core::Details::Globals *this)
{
  char *v1; // rax
  RTL_SRWLOCK *v2; // r14
  int *v3; // rbp
  char *v4; // r15
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v6; // r9
  int v7; // edi
  int v8; // eax
  struct _TP_WORK *v10; // r12
  DWORD LastError; // edi
  __int64 v12; // r12
  __int64 v13; // r15
  DWORD v14; // edi
  __int64 v15; // rcx
  utl::_RefCountBase *v16; // rcx
  int v17[2]; // [rsp+20h] [rbp-48h] BYREF
  char v18; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( Container::Manager::Core::g_hostIdleMonitor )
    return 0;
  v1 = (char *)operator new(0x60u, (const struct std::nothrow_t *)&std::nothrow);
  v2 = (RTL_SRWLOCK *)v1;
  if ( v1 )
  {
    *((_DWORD *)v1 + 2) = 1;
    *((_DWORD *)v1 + 3) = 1;
    *(_QWORD *)v1 = &utl::_RefCountVtable<utl::_RefCountStored<Container::Manager::Core::Details::HostIdleMonitor,utl::allocator<int>,0>,0>::`vftable';
    *((_QWORD *)v1 + 2) = 0;
    *((_DWORD *)v1 + 6) = 0;
    v3 = (int *)(v1 + 32);
    *((_QWORD *)v1 + 4) = 0;
    *((_QWORD *)v1 + 5) = 0;
    *((_QWORD *)v1 + 7) = v1 + 48;
    *((_QWORD *)v1 + 6) = v1 + 48;
    v4 = v1 + 64;
    *((_QWORD *)v1 + 8) = 0;
    v1[72] = 0;
    *((_QWORD *)v1 + 10) = 0;
    *((_WORD *)v1 + 44) = 0;
    if ( v1 != (char *)-16LL )
    {
      ThreadpoolWork = CreateThreadpoolWork(
                         Container::Manager::Core::Details::HostIdleMonitor::HostIdleUnsubscriptionThread,
                         v1 + 16,
                         0);
      if ( ThreadpoolWork )
      {
        *(_QWORD *)v17 = 0;
        v8 = CrmRegister(v17, 306, L"CrmClient_ContainerManager");
        if ( v8 >= 0 )
        {
          if ( v4 != &v18 )
          {
            v10 = *(struct _TP_WORK **)v4;
            if ( *(_QWORD *)v4 )
            {
              LastError = GetLastError();
              CloseThreadpoolWork(v10);
              SetLastError(LastError);
            }
            *(_QWORD *)v4 = ThreadpoolWork;
            ThreadpoolWork = 0;
          }
          if ( v3 == v17 )
          {
            v15 = *(_QWORD *)v17;
          }
          else
          {
            v12 = *(_QWORD *)v17;
            v13 = *(_QWORD *)v3;
            if ( *(_QWORD *)v3 )
            {
              v14 = GetLastError();
              CrmUnregister(v13);
              SetLastError(v14);
            }
            *(_QWORD *)v3 = v12;
            v15 = 0;
            *(_QWORD *)v17 = 0;
          }
          if ( v15 )
            CrmUnregister(v15);
          if ( ThreadpoolWork )
            CloseThreadpoolWork(ThreadpoolWork);
LABEL_25:
          Container::Manager::Core::g_hostIdleMonitor = v2 + 2;
          v16 = qword_18021F4B8;
          qword_18021F4B8 = (utl::_RefCountBase *)v2;
          if ( v16 )
            utl::_RefCountBase::_DecStrong(v16);
          return 0;
        }
        v7 = wil::details::in1diag3::Return_NtStatus(
               retaddr,
               (void *)0x8C,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\hostidlemonitor.cpp",
               (const char *)(unsigned int)v8,
               v17[0]);
        if ( *(_QWORD *)v17 )
          CrmUnregister(*(_QWORD *)v17);
        CloseThreadpoolWork(ThreadpoolWork);
      }
      else
      {
        v7 = wil::details::in1diag3::Return_GetLastError(
               retaddr,
               (void *)0x86,
               (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\hostidlemonitor.cpp",
               v6);
      }
      if ( v7 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x2DC,
          (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
          (const char *)(unsigned int)v7,
          v17[0]);
        utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v2);
        return (unsigned int)v7;
      }
      goto LABEL_25;
    }
  }
  else
  {
    v2 = 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2DA,
    (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
    (const char *)0x8007000ELL,
    v17[0]);
  if ( v2 )
    utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v2);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180074638  push    rbx
0x18007463a  push    rbp
0x18007463b  push    rsi
0x18007463c  push    rdi
0x18007463d  push    r12
0x18007463f  push    r14
0x180074641  push    r15
0x180074643  sub     rsp, 30h
0x180074647  cmp     cs:?g_hostIdleMonitor@Core@Manager@Container@@3V?$shared_ptr@VHostIdleMonitor@Details@Core@Manager@Container@@@utl@@A, 0; utl::shared_ptr<Container::Manager::Core::Details::HostIdleMonitor> Container::Manager::Core::g_hostIdleMonitor
0x18007464f  jnz     loc_180074893
0x180074655  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18007465c  mov     ecx, 60h ; '`'; unsigned __int64
0x180074661  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180074666  mov     r14, rax
0x180074669  test    rax, rax
0x18007466c  jz      loc_1800748A5
0x180074672  mov     eax, 1
0x180074677  mov     [r14+8], eax
0x18007467b  mov     [r14+0Ch], eax
0x18007467f  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountStored@VHostIdleMonitor@Details@Core@Manager@Container@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountStored<Container::Manager::Core::Details::HostIdleMonitor,utl::allocator<int>,0>,0>::`vftable'
0x180074686  mov     [r14], rax
0x180074689  lea     rsi, [r14+10h]
0x18007468d  mov     qword ptr [rsi], 0
0x180074694  mov     dword ptr [rsi+8], 0
0x18007469b  lea     rbp, [rsi+10h]
0x18007469f  mov     qword ptr [rbp+0], 0
0x1800746a7  mov     qword ptr [rsi+18h], 0
0x1800746af  lea     rax, [rsi+20h]
0x1800746b3  mov     [rax+8], rax
0x1800746b7  mov     [rax], rax
0x1800746ba  lea     r15, [rsi+30h]
0x1800746be  mov     qword ptr [r15], 0
0x1800746c5  mov     byte ptr [rsi+38h], 0
0x1800746c9  mov     qword ptr [rsi+40h], 0
0x1800746d1  mov     word ptr [rsi+48h], 0
0x1800746d7  test    rsi, rsi
0x1800746da  jz      loc_1800748A8
0x1800746e0  xor     r8d, r8d; pcbe
0x1800746e3  mov     rdx, rsi; pv
0x1800746e6  lea     rcx, ?HostIdleUnsubscriptionThread@HostIdleMonitor@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x1800746ed  call    cs:__imp_CreateThreadpoolWork
0x1800746f4  nop     dword ptr [rax+rax+00h]
0x1800746f9  mov     rbx, rax
0x1800746fc  test    rax, rax
0x1800746ff  jnz     short loc_18007471B
0x180074701  mov     rcx, [rsp+68h]; this
0x180074706  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007470d  mov     edx, 86h; void *
0x180074712  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180074717  mov     edi, eax
0x180074719  jmp     short loc_180074785
0x18007471b  mov     qword ptr [rsp+68h+var_48], 0; int
0x180074724  lea     r8, aCrmclientConta; "CrmClient_ContainerManager"
0x18007472b  mov     edx, 132h
0x180074730  lea     rcx, [rsp+68h+var_48]
0x180074735  call    cs:__imp_CrmRegister
0x18007473c  nop     dword ptr [rax+rax+00h]
0x180074741  test    eax, eax
0x180074743  jns     short loc_1800747B7
0x180074745  mov     rcx, [rsp+68h]; this
0x18007474a  mov     r9d, eax; char *
0x18007474d  lea     r8, aOnecoreBaseGen_6; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180074754  mov     edx, 8Ch; void *
0x180074759  call    ?Return_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Return_NtStatus(void *,uint,char const *,long)
0x18007475e  mov     edi, eax
0x180074760  mov     rcx, qword ptr [rsp+68h+var_48]
0x180074765  test    rcx, rcx
0x180074768  jz      short loc_180074776
0x18007476a  call    cs:__imp_CrmUnregister
0x180074771  nop     dword ptr [rax+rax+00h]
0x180074776  mov     rcx, rbx; pwk
0x180074779  call    cs:__imp_CloseThreadpoolWork
0x180074780  nop     dword ptr [rax+rax+00h]
0x180074785  test    edi, edi
0x180074787  jns     loc_180074873
0x18007478d  mov     rcx, [rsp+68h]; this
0x180074792  mov     r9d, edi; char *
0x180074795  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18007479c  mov     edx, 2DCh; void *
0x1800747a1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800747a6  nop
0x1800747a7  mov     rcx, r14; this
0x1800747aa  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800747af  nop
0x1800747b0  mov     eax, edi
0x1800747b2  jmp     loc_180074895
0x1800747b7  lea     rax, [rsp+68h+var_40]
0x1800747bc  cmp     r15, rax
0x1800747bf  jz      short loc_1800747F9
0x1800747c1  mov     r12, [r15]
0x1800747c4  test    r12, r12
0x1800747c7  jz      short loc_1800747F4
0x1800747c9  call    cs:__imp_GetLastError
0x1800747d0  nop     dword ptr [rax+rax+00h]
0x1800747d5  mov     edi, eax
0x1800747d7  mov     rcx, r12; pwk
0x1800747da  call    cs:__imp_CloseThreadpoolWork
0x1800747e1  nop     dword ptr [rax+rax+00h]
0x1800747e6  mov     ecx, edi; dwErrCode
0x1800747e8  call    cs:__imp_SetLastError
0x1800747ef  nop     dword ptr [rax+rax+00h]
0x1800747f4  mov     [r15], rbx
0x1800747f7  xor     ebx, ebx
0x1800747f9  lea     rax, [rsp+68h+var_48]
0x1800747fe  cmp     rbp, rax
0x180074801  jz      short loc_180074849
0x180074803  mov     r12, qword ptr [rsp+68h+var_48]
0x180074808  mov     r15, [rbp+0]
0x18007480c  test    r15, r15
0x18007480f  jz      short loc_18007483C
0x180074811  call    cs:__imp_GetLastError
0x180074818  nop     dword ptr [rax+rax+00h]
0x18007481d  mov     edi, eax
0x18007481f  mov     rcx, r15
0x180074822  call    cs:__imp_CrmUnregister
0x180074829  nop     dword ptr [rax+rax+00h]
0x18007482e  mov     ecx, edi; dwErrCode
0x180074830  call    cs:__imp_SetLastError
0x180074837  nop     dword ptr [rax+rax+00h]
0x18007483c  mov     [rbp+0], r12
0x180074840  xor     ecx, ecx
0x180074842  mov     qword ptr [rsp+68h+var_48], rcx
0x180074847  jmp     short loc_18007484E
0x180074849  mov     rcx, qword ptr [rsp+68h+var_48]
0x18007484e  test    rcx, rcx
0x180074851  jz      short loc_18007485F
0x180074853  call    cs:__imp_CrmUnregister
0x18007485a  nop     dword ptr [rax+rax+00h]
0x18007485f  test    rbx, rbx
0x180074862  jz      short loc_180074873
0x180074864  mov     rcx, rbx; pwk
0x180074867  call    cs:__imp_CloseThreadpoolWork
0x18007486e  nop     dword ptr [rax+rax+00h]
0x180074873  mov     cs:?g_hostIdleMonitor@Core@Manager@Container@@3V?$shared_ptr@VHostIdleMonitor@Details@Core@Manager@Container@@@utl@@A, rsi; utl::shared_ptr<Container::Manager::Core::Details::HostIdleMonitor> Container::Manager::Core::g_hostIdleMonitor
0x18007487a  mov     rcx, cs:qword_18021F4B8; this
0x180074881  mov     cs:qword_18021F4B8, r14
0x180074888  test    rcx, rcx
0x18007488b  jz      short loc_180074893
0x18007488d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180074892  nop
0x180074893  xor     eax, eax
0x180074895  add     rsp, 30h
0x180074899  pop     r15
0x18007489b  pop     r14
0x18007489d  pop     r12
0x18007489f  pop     rdi
0x1800748a0  pop     rsi
0x1800748a1  pop     rbp
0x1800748a2  pop     rbx
0x1800748a3  retn
0x1800748a5  xor     r14d, r14d
0x1800748a8  mov     rcx, [rsp+68h]; this
0x1800748ad  mov     ebx, 8007000Eh
0x1800748b2  mov     r9d, ebx; char *
0x1800748b5  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800748bc  mov     edx, 2DAh; void *
0x1800748c1  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800748c6  nop
0x1800748c7  test    r14, r14
0x1800748ca  jz      short loc_1800748D5
0x1800748cc  mov     rcx, r14; this
0x1800748cf  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x1800748d4  nop
0x1800748d5  mov     eax, ebx
0x1800748d7  jmp     short loc_180074895
```
