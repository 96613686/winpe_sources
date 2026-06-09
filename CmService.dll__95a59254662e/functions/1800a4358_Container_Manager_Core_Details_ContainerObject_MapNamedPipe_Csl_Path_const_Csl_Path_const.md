# Container::Manager::Core::Details::ContainerObject::MapNamedPipe(Csl::Path const &,Csl::Path const &)

- ea: `0x1800a4358`
- end: `0x1800a4695`
- name: `?MapNamedPipe@ContainerObject@Details@Core@Manager@Container@@AEAAJAEBVPath@Csl@@0@Z`
- size: `829`
- prototype: `__int64 __fastcall(Container::Manager::Core::Details::ContainerObject *__hidden this, const struct Path *, const struct Path *)`
- caller_count: `1`
- callee_count: `9`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180067474`

## callees

- `0x180004fc4`
- `0x18000da88`
- `0x180016774`
- `0x180098bb8`
- `0x18009b018`
- `0x1800a4358`
- `0x1800ac950`
- `0x1800ba5ac`
- `0x180123744`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a4418`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a45a7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a4418`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800a45a7`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a447e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a44f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a4554`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a45fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a4647`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a447e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a44f3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a4554`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a45fb`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800a4647`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a4424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a45b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a4424`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a45b3`

## pseudocode

```c
__int64 __fastcall Container::Manager::Core::Details::ContainerObject::MapNamedPipe(
        RTL_SRWLOCK *this,
        const struct Path *a2,
        const struct Path *a3)
{
  __int64 v5; // r8
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  DWORD CurrentThreadId; // eax
  RTL_SRWLOCK *v12; // rcx
  __int128 v13; // xmm0
  PVOID Ptr; // rcx
  int v15; // esi
  __int128 v16; // [rsp+20h] [rbp-58h] BYREF
  void *v17[2]; // [rsp+30h] [rbp-48h] BYREF
  _WORD v18[8]; // [rsp+40h] [rbp-38h] BYREF
  void *v19[2]; // [rsp+50h] [rbp-28h] BYREF
  _WORD v20[12]; // [rsp+60h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+A8h] [rbp+30h]
  PSRWLOCK SRWLock; // [rsp+B8h] [rbp+40h] BYREF

  v5 = *((_QWORD *)a2 + 1) - *(_QWORD *)a2;
  v7 = *(_QWORD *)a2;
  v17[0] = v18;
  v17[1] = v18;
  v18[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v17,
                           v7,
                           v5 >> 1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC92,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v16);
LABEL_9:
    if ( v17[0] != v18 )
      operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942414LL;
  }
  v8 = *((_QWORD *)a3 + 1) - *(_QWORD *)a3;
  v9 = *(_QWORD *)a3;
  v19[0] = v20;
  v19[1] = v20;
  v20[0] = 0;
  if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(
                           v19,
                           v9,
                           v8 >> 1) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC95,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      v16);
    goto LABEL_7;
  }
  AcquireSRWLockExclusive(this + 57);
  CurrentThreadId = GetCurrentThreadId();
  SRWLock = this + 57;
  LODWORD(this[58].Ptr) = CurrentThreadId;
  utl::_Tree<Csl::Path,utl::pair<Csl::Path const,Csl::Path>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,Csl::Path>>,0>::emplace<Csl::Path,Csl::Path,0>(
    &this[81],
    &v16,
    v17,
    v19);
  if ( !(_QWORD)v16 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9C,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x8007000ELL,
      0);
    LODWORD(this[58].Ptr) = 0;
    ReleaseSRWLockExclusive(this + 57);
LABEL_7:
    if ( v19[0] != v20 )
      operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
    goto LABEL_9;
  }
  if ( BYTE8(v16) )
  {
    Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(
      this,
      &SRWLock);
    v12 = SRWLock;
    if ( SRWLock )
    {
      LODWORD(SRWLock[1].Ptr) = 0;
      ReleaseSRWLockExclusive(v12);
    }
    v13 = 0;
    if ( LODWORD(this[11].Ptr) == 1 )
    {
      if ( !LOBYTE(this[21].Ptr) )
        __int2c();
      *(RTL_SRWLOCK *)&v16 = this[20];
      BYTE8(v16) = 1;
      v13 = v16;
    }
    Ptr = this[157].Ptr;
    v16 = v13;
    v15 = Container::Manager::Hcs::ComputeSystem::MapNamedPipe(Ptr, a2, a3, &v16);
    AcquireSRWLockExclusive(this + 57);
    LODWORD(this[58].Ptr) = GetCurrentThreadId();
    Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference((Container::Manager::Core::Details::ContainerObject *)this);
    if ( v15 >= 0 )
    {
      LODWORD(this[58].Ptr) = 0;
      ReleaseSRWLockExclusive(this + 57);
      if ( v19[0] != v20 )
        operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v17[0] != v18 )
        operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
      return 0;
    }
    else
    {
      utl::_Tree<Csl::Path,utl::pair<Csl::Path const,Csl::Path>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,Csl::Path>>,0>::erase(&this[81]);
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xCCA,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
        (const char *)(unsigned int)v15,
        v16);
      LODWORD(this[58].Ptr) = 0;
      ReleaseSRWLockExclusive(this + 57);
      if ( v19[0] != v20 )
        operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
      if ( v17[0] != v18 )
        operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
      return (unsigned int)v15;
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xC9F,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\container.cpp",
      (const char *)0x800700B7LL,
      v16);
    LODWORD(this[58].Ptr) = 0;
    ReleaseSRWLockExclusive(this + 57);
    if ( v19[0] != v20 )
      operator delete(v19[0], (const struct std::nothrow_t *)&std::nothrow);
    if ( v17[0] != v18 )
      operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
    return 2147942583LL;
  }
}

```

## disassembly

```asm
0x1800a4358  push    rbp
0x1800a435a  push    rbx
0x1800a435b  push    rsi
0x1800a435c  push    rdi
0x1800a435d  push    r14
0x1800a435f  push    r15
0x1800a4361  mov     rbp, rsp
0x1800a4364  sub     rsp, 78h
0x1800a4368  mov     rsi, r8
0x1800a436b  lea     rax, [rbp+var_38]
0x1800a436f  mov     r8, [rdx+8]
0x1800a4373  mov     r15, rdx
0x1800a4376  sub     r8, [rdx]
0x1800a4379  mov     rdi, rcx
0x1800a437c  mov     rdx, [rdx]
0x1800a437f  lea     rcx, [rbp+var_48]
0x1800a4383  mov     [rbp+var_48], rax
0x1800a4387  lea     rax, [rbp+var_38]
0x1800a438b  mov     [rbp+var_40], rax
0x1800a438f  xor     eax, eax
0x1800a4391  sar     r8, 1
0x1800a4394  mov     [rbp+var_38], ax
0x1800a4398  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a439d  test    al, al
0x1800a439f  jnz     short loc_1800A43C1
0x1800a43a1  mov     rcx, [rbp+30h]; this
0x1800a43a5  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a43ac  mov     r9d, 8007000Eh; char *
0x1800a43b2  mov     edx, 0C92h; void *
0x1800a43b7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a43bc  jmp     loc_1800A44A3
0x1800a43c1  mov     r8, [rsi+8]
0x1800a43c5  lea     rax, [rbp+var_18]
0x1800a43c9  sub     r8, [rsi]
0x1800a43cc  lea     rcx, [rbp+var_28]
0x1800a43d0  mov     rdx, [rsi]
0x1800a43d3  mov     [rbp+var_28], rax
0x1800a43d7  lea     rax, [rbp+var_18]
0x1800a43db  mov     [rbp+var_20], rax
0x1800a43df  xor     eax, eax
0x1800a43e1  sar     r8, 1
0x1800a43e4  mov     [rbp+var_18], ax
0x1800a43e8  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x1800a43ed  test    al, al
0x1800a43ef  jnz     short loc_1800A440E
0x1800a43f1  mov     rcx, [rbp+30h]; this
0x1800a43f5  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a43fc  mov     r9d, 8007000Eh; char *
0x1800a4402  mov     edx, 0C95h; void *
0x1800a4407  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a440c  jmp     short loc_1800A448A
0x1800a440e  lea     rbx, [rdi+1C8h]
0x1800a4415  mov     rcx, rbx; SRWLock
0x1800a4418  call    cs:__imp_AcquireSRWLockExclusive
0x1800a441f  nop     dword ptr [rax+rax+00h]
0x1800a4424  call    cs:__imp_GetCurrentThreadId
0x1800a442b  nop     dword ptr [rax+rax+00h]
0x1800a4430  lea     r14, [rdi+288h]
0x1800a4437  mov     [rbp+SRWLock], rbx
0x1800a443b  mov     rcx, r14
0x1800a443e  mov     [rbx+8], eax
0x1800a4441  lea     r9, [rbp+var_28]
0x1800a4445  lea     r8, [rbp+var_48]
0x1800a4449  lea     rdx, [rbp+var_58]
0x1800a444d  call    ??$emplace@VPath@Csl@@V12@$0A@@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V12@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V12@@utl@@@4@$0A@@utl@@QEAA?AU?$pair@V?$_TreeIt@U?$pair@$$CBVPath@Csl@@V12@@utl@@@utl@@_N@1@$$QEAVPath@Csl@@0@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,Csl::Path>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,Csl::Path>>,0>::emplace<Csl::Path,Csl::Path,0>(Csl::Path &&,Csl::Path &&)
0x1800a4452  cmp     qword ptr [rbp+var_58], 0
0x1800a4457  jnz     short loc_1800A44C6
0x1800a4459  mov     rcx, [rbp+30h]; this
0x1800a445d  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a4464  mov     r9d, 8007000Eh; char *
0x1800a446a  mov     edx, 0C9Ch; void *
0x1800a446f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a4474  mov     rcx, rbx; SRWLock
0x1800a4477  mov     dword ptr [rbx+8], 0
0x1800a447e  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a4485  nop     dword ptr [rax+rax+00h]
0x1800a448a  mov     rcx, [rbp+var_28]; void *
0x1800a448e  lea     rax, [rbp+var_18]
0x1800a4492  cmp     rcx, rax
0x1800a4495  jz      short loc_1800A44A3
0x1800a4497  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a449e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a44a3  mov     rcx, [rbp+var_48]; void *
0x1800a44a7  lea     rax, [rbp+var_38]
0x1800a44ab  cmp     rcx, rax
0x1800a44ae  jz      short loc_1800A44BC
0x1800a44b0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a44b7  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a44bc  mov     eax, 8007000Eh
0x1800a44c1  jmp     loc_1800A4687
0x1800a44c6  cmp     byte ptr [rbp+var_58+8], 0
0x1800a44ca  jnz     short loc_1800A4538
0x1800a44cc  mov     rcx, [rbp+30h]; this
0x1800a44d0  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a44d7  mov     edi, 800700B7h
0x1800a44dc  mov     edx, 0C9Fh; void *
0x1800a44e1  mov     r9d, edi; char *
0x1800a44e4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a44e9  mov     rcx, rbx; SRWLock
0x1800a44ec  mov     dword ptr [rbx+8], 0
0x1800a44f3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a44fa  nop     dword ptr [rax+rax+00h]
0x1800a44ff  mov     rcx, [rbp+var_28]; void *
0x1800a4503  lea     rax, [rbp+var_18]
0x1800a4507  cmp     rcx, rax
0x1800a450a  jz      short loc_1800A4518
0x1800a450c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4513  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4518  mov     rcx, [rbp+var_48]; void *
0x1800a451c  lea     rdx, [rbp+var_38]
0x1800a4520  cmp     rcx, rdx
0x1800a4523  jz      short loc_1800A4531
0x1800a4525  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a452c  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4531  mov     eax, edi
0x1800a4533  jmp     loc_1800A4687
0x1800a4538  lea     rdx, [rbp+SRWLock]
0x1800a453c  mov     rcx, rdi
0x1800a453f  call    ?AcquireAndWaitForContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXAEAV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ContainerObject::AcquireAndWaitForContainerInfrastructureWakeReference(Csl::SrwLock::ReleaseOnScopeExit<0> &)
0x1800a4544  mov     rcx, [rbp+SRWLock]; SRWLock
0x1800a4548  test    rcx, rcx
0x1800a454b  jz      short loc_1800A4560
0x1800a454d  mov     dword ptr [rcx+8], 0
0x1800a4554  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a455b  nop     dword ptr [rax+rax+00h]
0x1800a4560  cmp     dword ptr [rdi+58h], 1
0x1800a4564  xorps   xmm0, xmm0
0x1800a4567  jnz     short loc_1800A4587
0x1800a4569  cmp     byte ptr [rdi+0A8h], 0
0x1800a4570  jnz     short loc_1800A4574
0x1800a4572  int     2Ch; Windows NT - assertion failure
0x1800a4574  mov     rax, [rdi+0A0h]
0x1800a457b  mov     qword ptr [rbp+var_58], rax
0x1800a457f  mov     byte ptr [rbp+var_58+8], 1
0x1800a4583  movaps  xmm0, [rbp+var_58]
0x1800a4587  mov     rcx, [rdi+4E8h]
0x1800a458e  lea     r9, [rbp+var_58]
0x1800a4592  mov     r8, rsi
0x1800a4595  movdqa  [rbp+var_58], xmm0
0x1800a459a  mov     rdx, r15
0x1800a459d  call    ?MapNamedPipe@ComputeSystem@Hcs@Manager@Container@@QEAAJAEBVPath@Csl@@0V?$optional@PEAX@utl@@@Z; Container::Manager::Hcs::ComputeSystem::MapNamedPipe(Csl::Path const &,Csl::Path const &,utl::optional<void *>)
0x1800a45a2  mov     rcx, rbx; SRWLock
0x1800a45a5  mov     esi, eax
0x1800a45a7  call    cs:__imp_AcquireSRWLockExclusive
0x1800a45ae  nop     dword ptr [rax+rax+00h]
0x1800a45b3  call    cs:__imp_GetCurrentThreadId
0x1800a45ba  nop     dword ptr [rax+rax+00h]
0x1800a45bf  mov     rcx, rdi; this
0x1800a45c2  mov     [rbx+8], eax
0x1800a45c5  call    ?ReleaseContainerInfrastructureWakeReference@ContainerObject@Details@Core@Manager@Container@@AEAAXXZ; Container::Manager::Core::Details::ContainerObject::ReleaseContainerInfrastructureWakeReference(void)
0x1800a45ca  test    esi, esi
0x1800a45cc  jns     short loc_1800A463D
0x1800a45ce  mov     rdx, r15
0x1800a45d1  mov     rcx, r14; void *
0x1800a45d4  call    ?erase@?$_Tree@VPath@Csl@@U?$pair@$$CBVPath@Csl@@V12@@utl@@U?$less@VPath@Csl@@@4@V?$allocator@U?$pair@$$CBVPath@Csl@@V12@@utl@@@4@$0A@@utl@@QEAA_KAEBVPath@Csl@@@Z; utl::_Tree<Csl::Path,utl::pair<Csl::Path const,Csl::Path>,utl::less<Csl::Path>,utl::allocator<utl::pair<Csl::Path const,Csl::Path>>,0>::erase(Csl::Path const &)
0x1800a45d9  mov     rcx, [rbp+30h]; this
0x1800a45dd  lea     r8, aOnecoreBaseGen_64; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x1800a45e4  mov     r9d, esi; char *
0x1800a45e7  mov     edx, 0CCAh; void *
0x1800a45ec  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800a45f1  mov     rcx, rbx; SRWLock
0x1800a45f4  mov     dword ptr [rbx+8], 0
0x1800a45fb  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a4602  nop     dword ptr [rax+rax+00h]
0x1800a4607  mov     rcx, [rbp+var_28]; void *
0x1800a460b  lea     rax, [rbp+var_18]
0x1800a460f  cmp     rcx, rax
0x1800a4612  jz      short loc_1800A4620
0x1800a4614  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a461b  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4620  mov     rcx, [rbp+var_48]; void *
0x1800a4624  lea     rax, [rbp+var_38]
0x1800a4628  cmp     rcx, rax
0x1800a462b  jz      short loc_1800A4639
0x1800a462d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4634  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4639  mov     eax, esi
0x1800a463b  jmp     short loc_1800A4687
0x1800a463d  mov     rcx, rbx; SRWLock
0x1800a4640  mov     dword ptr [rbx+8], 0
0x1800a4647  call    cs:__imp_ReleaseSRWLockExclusive
0x1800a464e  nop     dword ptr [rax+rax+00h]
0x1800a4653  mov     rcx, [rbp+var_28]; void *
0x1800a4657  lea     rax, [rbp+var_18]
0x1800a465b  cmp     rcx, rax
0x1800a465e  jz      short loc_1800A466C
0x1800a4660  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4667  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a466c  mov     rcx, [rbp+var_48]; void *
0x1800a4670  lea     rax, [rbp+var_38]
0x1800a4674  cmp     rcx, rax
0x1800a4677  jz      short loc_1800A4685
0x1800a4679  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800a4680  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800a4685  xor     eax, eax
0x1800a4687  add     rsp, 78h
0x1800a468b  pop     r15
0x1800a468d  pop     r14
0x1800a468f  pop     rdi
0x1800a4690  pop     rsi
0x1800a4691  pop     rbx
0x1800a4692  pop     rbp
0x1800a4693  retn
```
