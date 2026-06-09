# Container::Manager::Core::Details::Globals::CreateComputeReaper(void)

- ea: `0x1800739d4`
- end: `0x180073c72`
- name: `?CreateComputeReaper@Globals@Details@Core@Manager@Container@@QEAAJXZ`
- size: `670`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::Globals *__hidden this)`
- caller_count: `3`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180073dd8`
- `0x1800748e0`
- `0x180074f90`

## callees

- `0x180004bf4`
- `0x18000da68`
- `0x18000da88`
- `0x1800471dc`
- `0x180073848`
- `0x1800739d4`
- `0x1800d5364`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073a72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x180073a72`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180073aad`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x180073aad`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180073b8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180073beb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180073b8d`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolTimer` at `0x180073beb`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073adc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073b44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073bff`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073adc`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073b44`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x180073bff`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180073b7c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073b52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073b9b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073b52`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180073b9b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Container::Manager::Core::Details::Globals::CreateComputeReaper(
        Container::Manager::Core::Details::Globals *this)
{
  int started; // eax
  unsigned int v2; // ebx
  struct _TP_WORK **v4; // rax
  struct _TP_WORK **v5; // r14
  struct _TP_WORK *ThreadpoolWork; // rbx
  const char *v7; // r9
  int LastError; // edi
  struct _TP_TIMER *ThreadpoolTimer; // rdi
  const char *v10; // r9
  struct _TP_WORK **v11; // r15
  struct _TP_WORK *v12; // r12
  DWORD v13; // esi
  struct _TP_TIMER **v14; // r15
  struct _TP_TIMER *v15; // r12
  DWORD v16; // esi
  Container::Manager::Core::Details::PolicyManager *v17; // rcx
  utl::_RefCountBase *v18; // rax
  utl::_RefCountBase *v19; // rcx
  utl::_RefCountBase *v20; // rcx
  int v21; // [rsp+20h] [rbp-48h] BYREF
  char v22; // [rsp+28h] [rbp-40h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( Container::Manager::Core::g_computeReaper )
    return 0;
  started = Container::Manager::Core::Details::Globals::CreateAndStartPolicyManager(this);
  v2 = started;
  if ( started < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1ED,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
      (const char *)(unsigned int)started,
      v21);
    return v2;
  }
  v4 = (struct _TP_WORK **)operator new(0xC8u, (const struct std::nothrow_t *)&std::nothrow);
  v5 = v4;
  if ( !v4 )
  {
    v5 = 0;
LABEL_33:
    v2 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1F0,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
      (const char *)0x8007000ELL,
      v21);
    if ( v5 )
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v5);
    return v2;
  }
  *((_DWORD *)v4 + 2) = 1;
  *((_DWORD *)v4 + 3) = 1;
  *v4 = (struct _TP_WORK *)&utl::_RefCountVtable<utl::_RefCountStored<Container::Manager::Core::Details::ComputeReaper,utl::allocator<int>,0>,0>::`vftable';
  Container::Manager::Core::Details::ComputeReaper::ComputeReaper((Container::Manager::Core::Details::ComputeReaper *)(v4 + 2));
  if ( v5 == (struct _TP_WORK **)-16LL )
    goto LABEL_33;
  ThreadpoolWork = CreateThreadpoolWork(Container::Manager::Core::Details::ComputeReaper::ExecuteReaping, v5 + 2, 0);
  if ( !ThreadpoolWork )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0xFB,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\reaper.cpp",
                  v7);
    goto LABEL_11;
  }
  ThreadpoolTimer = CreateThreadpoolTimer(
                      Container::Manager::Core::Details::ComputeReaper::FailedReapingTimer,
                      v5 + 2,
                      0);
  if ( !ThreadpoolTimer )
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x100,
                  (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\reaper.cpp",
                  v10);
    CloseThreadpoolWork(ThreadpoolWork);
LABEL_11:
    if ( LastError < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1F2,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\globals.cpp",
        (const char *)(unsigned int)LastError,
        v21);
      utl::_RefCountBase::_DecStrong((utl::_RefCountBase *)v5);
      return (unsigned int)LastError;
    }
    goto LABEL_29;
  }
  v11 = v5 + 18;
  if ( v5 + 18 != (struct _TP_WORK **)&v21 )
  {
    v12 = *v11;
    if ( *v11 )
    {
      v13 = GetLastError();
      CloseThreadpoolWork(v12);
      SetLastError(v13);
    }
    *v11 = ThreadpoolWork;
    ThreadpoolWork = 0;
  }
  v14 = v5 + 19;
  if ( v5 + 19 != (struct _TP_WORK **)&v22 )
  {
    v15 = *v14;
    if ( *v14 )
    {
      v16 = GetLastError();
      CloseThreadpoolTimer(v15);
      SetLastError(v16);
    }
    *v14 = ThreadpoolTimer;
    ThreadpoolTimer = 0;
  }
  v17 = Container::Manager::Core::g_policyManager;
  v18 = qword_18021F478;
  if ( qword_18021F478 )
    _InterlockedIncrement((volatile signed __int32 *)qword_18021F478 + 2);
  v5[20] = v17;
  v19 = v5[21];
  v5[21] = v18;
  if ( v19 )
    utl::_RefCountBase::_DecStrong(v19);
  if ( ThreadpoolTimer )
    CloseThreadpoolTimer(ThreadpoolTimer);
  if ( ThreadpoolWork )
    CloseThreadpoolWork(ThreadpoolWork);
LABEL_29:
  Container::Manager::Core::g_computeReaper = (__int64)(v5 + 2);
  v20 = qword_18021F498;
  qword_18021F498 = (utl::_RefCountBase *)v5;
  if ( v20 )
    utl::_RefCountBase::_DecStrong(v20);
  return 0;
}

```

## disassembly

```asm
0x1800739d4  push    rbx
0x1800739d6  push    rbp
0x1800739d7  push    rsi
0x1800739d8  push    rdi
0x1800739d9  push    r12
0x1800739db  push    r14
0x1800739dd  push    r15
0x1800739df  sub     rsp, 30h
0x1800739e3  cmp     cs:?g_computeReaper@Core@Manager@Container@@3V?$shared_ptr@VComputeReaper@Details@Core@Manager@Container@@@utl@@A, 0; utl::shared_ptr<Container::Manager::Core::Details::ComputeReaper> Container::Manager::Core::g_computeReaper
0x1800739eb  jnz     loc_180073C2B
0x1800739f1  call    ?CreateAndStartPolicyManager@Globals@Details@Core@Manager@Container@@QEAAJXZ; Container::Manager::Core::Details::Globals::CreateAndStartPolicyManager(void)
0x1800739f6  mov     ebx, eax
0x1800739f8  test    eax, eax
0x1800739fa  jns     short loc_180073A1C
0x1800739fc  mov     rcx, [rsp+68h]; this
0x180073a01  mov     r9d, eax; char *
0x180073a04  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180073a0b  mov     edx, 1EDh; void *
0x180073a10  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073a15  mov     eax, ebx
0x180073a17  jmp     loc_180073C2D
0x180073a1c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180073a23  mov     ecx, 0C8h; unsigned __int64
0x180073a28  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180073a2d  mov     r14, rax
0x180073a30  test    rax, rax
0x180073a33  jz      loc_180073C3D
0x180073a39  mov     eax, 1
0x180073a3e  mov     [r14+8], eax
0x180073a42  mov     [r14+0Ch], eax
0x180073a46  lea     rax, ??_7?$_RefCountVtable@V?$_RefCountStored@VComputeReaper@Details@Core@Manager@Container@@V?$allocator@H@utl@@$0A@@utl@@$0A@@utl@@6B@; const utl::_RefCountVtable<utl::_RefCountStored<Container::Manager::Core::Details::ComputeReaper,utl::allocator<int>,0>,0>::`vftable'
0x180073a4d  mov     [r14], rax
0x180073a50  lea     rbp, [r14+10h]
0x180073a54  mov     rcx, rbp; this
0x180073a57  call    ??0ComputeReaper@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::ComputeReaper::ComputeReaper(void)
0x180073a5c  test    rbp, rbp
0x180073a5f  jz      loc_180073C40
0x180073a65  xor     r8d, r8d; pcbe
0x180073a68  mov     rdx, rbp; pv
0x180073a6b  lea     rcx, ?ExecuteReaping@ComputeReaper@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x180073a72  call    cs:__imp_CreateThreadpoolWork
0x180073a79  nop     dword ptr [rax+rax+00h]
0x180073a7e  mov     rbx, rax
0x180073a81  test    rax, rax
0x180073a84  jnz     short loc_180073AA0
0x180073a86  mov     rcx, [rsp+68h]; this
0x180073a8b  lea     r8, aOnecoreBaseGen_56; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180073a92  mov     edx, 0FBh; void *
0x180073a97  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180073a9c  mov     edi, eax
0x180073a9e  jmp     short loc_180073AE8
0x180073aa0  xor     r8d, r8d; pcbe
0x180073aa3  mov     rdx, rbp; pv
0x180073aa6  lea     rcx, ?FailedReapingTimer@ComputeReaper@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x180073aad  call    cs:__imp_CreateThreadpoolTimer
0x180073ab4  nop     dword ptr [rax+rax+00h]
0x180073ab9  mov     rdi, rax
0x180073abc  test    rax, rax
0x180073abf  jnz     short loc_180073B1A
0x180073ac1  mov     rcx, [rsp+68h]; this
0x180073ac6  lea     r8, aOnecoreBaseGen_56; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180073acd  mov     edx, 100h; void *
0x180073ad2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180073ad7  mov     edi, eax
0x180073ad9  mov     rcx, rbx; pwk
0x180073adc  call    cs:__imp_CloseThreadpoolWork
0x180073ae3  nop     dword ptr [rax+rax+00h]
0x180073ae8  test    edi, edi
0x180073aea  jns     loc_180073C0B
0x180073af0  mov     rcx, [rsp+68h]; this
0x180073af5  mov     r9d, edi; char *
0x180073af8  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180073aff  mov     edx, 1F2h; void *
0x180073b04  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073b09  nop
0x180073b0a  mov     rcx, r14; this
0x180073b0d  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180073b12  nop
0x180073b13  mov     eax, edi
0x180073b15  jmp     loc_180073C2D
0x180073b1a  lea     r15, [rbp+80h]
0x180073b21  lea     rax, [rsp+68h+var_48]
0x180073b26  cmp     r15, rax
0x180073b29  jz      short loc_180073B63
0x180073b2b  mov     r12, [r15]
0x180073b2e  test    r12, r12
0x180073b31  jz      short loc_180073B5E
0x180073b33  call    cs:__imp_GetLastError
0x180073b3a  nop     dword ptr [rax+rax+00h]
0x180073b3f  mov     esi, eax
0x180073b41  mov     rcx, r12; pwk
0x180073b44  call    cs:__imp_CloseThreadpoolWork
0x180073b4b  nop     dword ptr [rax+rax+00h]
0x180073b50  mov     ecx, esi; dwErrCode
0x180073b52  call    cs:__imp_SetLastError
0x180073b59  nop     dword ptr [rax+rax+00h]
0x180073b5e  mov     [r15], rbx
0x180073b61  xor     ebx, ebx
0x180073b63  lea     r15, [rbp+88h]
0x180073b6a  lea     rax, [rsp+68h+var_40]
0x180073b6f  cmp     r15, rax
0x180073b72  jz      short loc_180073BAC
0x180073b74  mov     r12, [r15]
0x180073b77  test    r12, r12
0x180073b7a  jz      short loc_180073BA7
0x180073b7c  call    cs:__imp_GetLastError
0x180073b83  nop     dword ptr [rax+rax+00h]
0x180073b88  mov     esi, eax
0x180073b8a  mov     rcx, r12; pti
0x180073b8d  call    cs:__imp_CloseThreadpoolTimer
0x180073b94  nop     dword ptr [rax+rax+00h]
0x180073b99  mov     ecx, esi; dwErrCode
0x180073b9b  call    cs:__imp_SetLastError
0x180073ba2  nop     dword ptr [rax+rax+00h]
0x180073ba7  mov     [r15], rdi
0x180073baa  xor     edi, edi
0x180073bac  mov     rcx, cs:?g_policyManager@Core@Manager@Container@@3V?$shared_ptr@VPolicyManager@Details@Core@Manager@Container@@@utl@@A; utl::shared_ptr<Container::Manager::Core::Details::PolicyManager> Container::Manager::Core::g_policyManager
0x180073bb3  mov     rax, cs:qword_18021F478
0x180073bba  test    rax, rax
0x180073bbd  jz      short loc_180073BC3
0x180073bbf  lock inc dword ptr [rax+8]
0x180073bc3  mov     [rbp+90h], rcx
0x180073bca  mov     rcx, [rbp+98h]; this
0x180073bd1  mov     [rbp+98h], rax
0x180073bd8  test    rcx, rcx
0x180073bdb  jz      short loc_180073BE3
0x180073bdd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180073be2  nop
0x180073be3  test    rdi, rdi
0x180073be6  jz      short loc_180073BF7
0x180073be8  mov     rcx, rdi; pti
0x180073beb  call    cs:__imp_CloseThreadpoolTimer
0x180073bf2  nop     dword ptr [rax+rax+00h]
0x180073bf7  test    rbx, rbx
0x180073bfa  jz      short loc_180073C0B
0x180073bfc  mov     rcx, rbx; pwk
0x180073bff  call    cs:__imp_CloseThreadpoolWork
0x180073c06  nop     dword ptr [rax+rax+00h]
0x180073c0b  mov     cs:?g_computeReaper@Core@Manager@Container@@3V?$shared_ptr@VComputeReaper@Details@Core@Manager@Container@@@utl@@A, rbp; utl::shared_ptr<Container::Manager::Core::Details::ComputeReaper> Container::Manager::Core::g_computeReaper
0x180073c12  mov     rcx, cs:qword_18021F498; this
0x180073c19  mov     cs:qword_18021F498, r14
0x180073c20  test    rcx, rcx
0x180073c23  jz      short loc_180073C2B
0x180073c25  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180073c2a  nop
0x180073c2b  xor     eax, eax
0x180073c2d  add     rsp, 30h
0x180073c31  pop     r15
0x180073c33  pop     r14
0x180073c35  pop     r12
0x180073c37  pop     rdi
0x180073c38  pop     rsi
0x180073c39  pop     rbp
0x180073c3a  pop     rbx
0x180073c3b  retn
0x180073c3d  xor     r14d, r14d
0x180073c40  mov     rcx, [rsp+68h]; this
0x180073c45  mov     ebx, 8007000Eh
0x180073c4a  mov     r9d, ebx; char *
0x180073c4d  lea     r8, aOnecoreBaseGen_29; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180073c54  mov     edx, 1F0h; void *
0x180073c59  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180073c5e  nop
0x180073c5f  test    r14, r14
0x180073c62  jz      short loc_180073C6D
0x180073c64  mov     rcx, r14; this
0x180073c67  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x180073c6c  nop
0x180073c6d  jmp     loc_180073A15
```
