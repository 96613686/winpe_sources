# Container::Manager::Core::Details::ResourceBroker::CleanupWorkThread(_TP_CALLBACK_INSTANCE *,void *,_TP_WORK *)

- ea: `0x180053150`
- end: `0x1800532cd`
- name: `?CleanupWorkThread@ResourceBroker@Details@Core@Manager@Container@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z`
- size: `381`
- prototype: `void __stdcall(PTP_CALLBACK_INSTANCE Instance, PVOID Context, PTP_WORK Work)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180004fc4`
- `0x180042b58`
- `0x18004f0e4`
- `0x180053150`
- `0x180058424`
- `0x18006032c`
- `0x1800603fc`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18005315f`
- `api-ms-win-core-threadpool-l1-2-0!CallbackMayRunLong` at `0x18005315f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053192`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005320e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180053192`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18005320e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800531f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800532b3`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800531f0`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x1800532b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005319e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005321a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005319e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005321a`

## string_xrefs

- `0x180053174`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`
- `0x18005323c`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
void __fastcall Container::Manager::Core::Details::ResourceBroker::CleanupWorkThread(
        PTP_CALLBACK_INSTANCE Instance,
        RTL_SRWLOCK *Context,
        PTP_WORK Work)
{
  __int64 v4; // rax
  int v5; // esi
  __int64 v6; // rax
  void *v7; // rsi
  void *v8[2]; // [rsp+20h] [rbp-38h] BYREF
  int v9; // [rsp+30h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  char v11; // [rsp+68h] [rbp+10h] BYREF
  char v12; // [rsp+78h] [rbp+20h] BYREF

  if ( !CallbackMayRunLong(Instance) )
    wil::details::in1diag3::Log_Hr(
      retaddr,
      (void *)0x2055,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
      (const char *)0x8007000ELL,
      (int)v8[0]);
  AcquireSRWLockExclusive(Context + 2);
  LODWORD(Context[3].Ptr) = GetCurrentThreadId();
  do
  {
    v9 = 0;
    *(_OWORD *)v8 = 0;
    while ( LODWORD(Context[8].Ptr) )
    {
      v4 = Csl::List<Container::Manager::Core::Details::Resource *>::PopFront(&Context[6], &v11);
      Csl::List<Container::Manager::Core::Details::Resource *>::EmplaceBack(v8, v4);
    }
    if ( Context != (RTL_SRWLOCK *)-16LL )
    {
      LODWORD(Context[3].Ptr) = 0;
      ReleaseSRWLockExclusive(Context + 2);
    }
    v5 = Container::Manager::Core::Details::ResourceBroker::ProcessCleanupList(Context, v8);
    AcquireSRWLockExclusive(Context + 2);
    LODWORD(Context[3].Ptr) = GetCurrentThreadId();
    if ( !LODWORD(Context[8].Ptr) )
      BYTE1(Context[4].Ptr) = 0;
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Log_Hr(
        retaddr,
        (void *)0x2091,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v5,
        (int)v8[0]);
      while ( v9 )
      {
        v6 = Csl::List<Container::Manager::Core::Details::Resource *>::PopFront(v8, &v12);
        Csl::List<Container::Manager::Core::Details::Resource *>::EmplaceBack(&Context[6], v6);
      }
    }
    v7 = v8[0];
    if ( v8[0] )
    {
      wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>::~unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>((char *)v8[0] + 24);
      operator delete(v7, (const struct std::nothrow_t *)0x20);
    }
  }
  while ( BYTE1(Context[4].Ptr) && LOBYTE(Context[4].Ptr) );
  if ( Context != (RTL_SRWLOCK *)-16LL )
  {
    LODWORD(Context[3].Ptr) = 0;
    ReleaseSRWLockExclusive(Context + 2);
  }
}

```

## disassembly

```asm
0x180053150  mov     [rsp+arg_0], rbx
0x180053155  push    rbp
0x180053156  push    rsi
0x180053157  push    rdi
0x180053158  sub     rsp, 40h
0x18005315c  mov     rdi, rdx
0x18005315f  call    cs:__imp_CallbackMayRunLong
0x180053166  nop     dword ptr [rax+rax+00h]
0x18005316b  test    eax, eax
0x18005316d  jnz     short loc_18005318B
0x18005316f  mov     rcx, [rsp+58h]; this
0x180053174  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18005317b  mov     r9d, 8007000Eh; char *
0x180053181  mov     edx, 2055h; void *
0x180053186  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18005318b  lea     rbx, [rdi+10h]
0x18005318f  mov     rcx, rbx; SRWLock
0x180053192  call    cs:__imp_AcquireSRWLockExclusive
0x180053199  nop     dword ptr [rax+rax+00h]
0x18005319e  call    cs:__imp_GetCurrentThreadId
0x1800531a5  nop     dword ptr [rax+rax+00h]
0x1800531aa  mov     [rbx+8], eax
0x1800531ad  xorps   xmm0, xmm0
0x1800531b0  mov     [rsp+58h+var_28], 0
0x1800531b8  movdqu  xmmword ptr [rsp+58h+var_38], xmm0; int
0x1800531be  cmp     dword ptr [rdi+40h], 0
0x1800531c2  jz      short loc_1800531E1
0x1800531c4  lea     rdx, [rsp+58h+arg_8]
0x1800531c9  lea     rcx, [rdi+30h]
0x1800531cd  call    ?PopFront@?$List@PEAVResource@Details@Core@Manager@Container@@@Csl@@QEAA?AV?$unique_ptr@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@U?$default_delete@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@@wistd@@@wistd@@XZ; Csl::List<Container::Manager::Core::Details::Resource *>::PopFront(void)
0x1800531d2  mov     rdx, rax
0x1800531d5  lea     rcx, [rsp+58h+var_38]
0x1800531da  call    ?EmplaceBack@?$List@PEAVResource@Details@Core@Manager@Container@@@Csl@@QEAAXV?$unique_ptr@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@U?$default_delete@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@@wistd@@@wistd@@@Z; Csl::List<Container::Manager::Core::Details::Resource *>::EmplaceBack(wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::Resource *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::Resource *>>>)
0x1800531df  jmp     short loc_1800531BE
0x1800531e1  test    rbx, rbx
0x1800531e4  jz      short loc_1800531FC
0x1800531e6  mov     rcx, rbx; SRWLock
0x1800531e9  mov     dword ptr [rbx+8], 0
0x1800531f0  call    cs:__imp_ReleaseSRWLockExclusive
0x1800531f7  nop     dword ptr [rax+rax+00h]
0x1800531fc  lea     rdx, [rsp+58h+var_38]
0x180053201  mov     rcx, rdi
0x180053204  call    ?ProcessCleanupList@ResourceBroker@Details@Core@Manager@Container@@AEAAJAEBV?$List@PEAVResource@Details@Core@Manager@Container@@@Csl@@@Z; Container::Manager::Core::Details::ResourceBroker::ProcessCleanupList(Csl::List<Container::Manager::Core::Details::Resource *> const &)
0x180053209  mov     rcx, rbx; SRWLock
0x18005320c  mov     esi, eax
0x18005320e  call    cs:__imp_AcquireSRWLockExclusive
0x180053215  nop     dword ptr [rax+rax+00h]
0x18005321a  call    cs:__imp_GetCurrentThreadId
0x180053221  nop     dword ptr [rax+rax+00h]
0x180053226  mov     [rbx+8], eax
0x180053229  cmp     dword ptr [rdi+40h], 0
0x18005322d  jnz     short loc_180053233
0x18005322f  mov     byte ptr [rdi+21h], 0
0x180053233  test    esi, esi
0x180053235  jns     short loc_180053274
0x180053237  mov     rcx, [rsp+58h]; this
0x18005323c  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x180053243  mov     r9d, esi; char *
0x180053246  mov     edx, 2091h; void *
0x18005324b  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x180053250  cmp     [rsp+58h+var_28], 0
0x180053255  jz      short loc_180053274
0x180053257  lea     rdx, [rsp+58h+arg_18]
0x18005325c  lea     rcx, [rsp+58h+var_38]
0x180053261  call    ?PopFront@?$List@PEAVResource@Details@Core@Manager@Container@@@Csl@@QEAA?AV?$unique_ptr@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@U?$default_delete@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@@wistd@@@wistd@@XZ; Csl::List<Container::Manager::Core::Details::Resource *>::PopFront(void)
0x180053266  mov     rdx, rax
0x180053269  lea     rcx, [rdi+30h]
0x18005326d  call    ?EmplaceBack@?$List@PEAVResource@Details@Core@Manager@Container@@@Csl@@QEAAXV?$unique_ptr@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@U?$default_delete@V?$ListEntry@PEAVResource@Details@Core@Manager@Container@@@Csl@@@wistd@@@wistd@@@Z; Csl::List<Container::Manager::Core::Details::Resource *>::EmplaceBack(wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::Resource *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::Resource *>>>)
0x180053272  jmp     short loc_180053250
0x180053274  mov     rsi, [rsp+58h+var_38]
0x180053279  test    rsi, rsi
0x18005327c  jz      short loc_180053294
0x18005327e  lea     rcx, [rsi+18h]
0x180053282  call    ??1?$unique_ptr@V?$ListEntry@PEAVComputeSystemReaperContext@Details@Core@Manager@Container@@@Csl@@U?$default_delete@V?$ListEntry@PEAVComputeSystemReaperContext@Details@Core@Manager@Container@@@Csl@@@wistd@@@wistd@@QEAA@XZ; wistd::unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>::~unique_ptr<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>,wistd::default_delete<Csl::ListEntry<Container::Manager::Core::Details::ComputeSystemReaperContext *>>>(void)
0x180053287  mov     edx, 20h ; ' '; struct std::nothrow_t *
0x18005328c  mov     rcx, rsi; void *
0x18005328f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180053294  cmp     byte ptr [rdi+21h], 0
0x180053298  jz      short loc_1800532A4
0x18005329a  cmp     byte ptr [rdi+20h], 0
0x18005329e  jnz     loc_1800531AD
0x1800532a4  test    rbx, rbx
0x1800532a7  jz      short loc_1800532BF
0x1800532a9  mov     rcx, rbx; SRWLock
0x1800532ac  mov     dword ptr [rbx+8], 0
0x1800532b3  call    cs:__imp_ReleaseSRWLockExclusive
0x1800532ba  nop     dword ptr [rax+rax+00h]
0x1800532bf  mov     rbx, [rsp+58h+arg_0]
0x1800532c4  add     rsp, 40h
0x1800532c8  pop     rdi
0x1800532c9  pop     rsi
0x1800532ca  pop     rbp
0x1800532cb  retn
```
