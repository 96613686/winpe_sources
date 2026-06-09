# Container::Manager::Core::Details::ResourceOperation::~ResourceOperation(void)

- ea: `0x18004ff1c`
- end: `0x1800500e8`
- name: `??1ResourceOperation@Details@Core@Manager@Container@@QEAA@XZ`
- size: `460`
- prototype: `void(Container::Manager::Core::Details::ResourceOperation *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180065cf0`

## callees

- `0x180004fc4`
- `0x180007dd4`
- `0x180009ba0`
- `0x180016658`
- `0x180016718`
- `0x1800471dc`
- `0x18004f52c`
- `0x18004feb4`
- `0x18004ff1c`
- `0x180052dfc`
- `0x1800662a0`
- `0x180066670`

## import_xrefs

- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004ffb8`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x18004ffb8`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004ffde`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005008e`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18004ffde`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18005008e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ff3f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18004ff3f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ffcd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004ffcd`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ffec`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18004ffec`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ff4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004ff4b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050075`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180050075`

## string_xrefs

- `0x18004ff7f`: `onecore\base\gendrv\silos\clem\core\lib\resourcebroker.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Core::Details::ResourceOperation::~ResourceOperation(RTL_SRWLOCK *this)
{
  RTL_SRWLOCK *v2; // rbx
  int v3; // eax
  struct _TP_WORK *Ptr; // rcx
  struct _TP_WORK *v5; // rsi
  DWORD LastError; // ebx
  utl::_RefCountBase *v7; // rcx
  utl::_RefCountBase *v8; // rcx
  PVOID v9; // rcx
  unsigned int v10; // r8d
  const char *v11; // r9
  struct _TP_WORK *v12; // rcx
  Container::Manager::Core::ResourceHandle *v13; // rbx
  int v14; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  RTL_SRWLOCK *v16; // [rsp+30h] [rbp+8h] BYREF

  if ( LODWORD(this[8].Ptr) )
  {
    v2 = this + 6;
    AcquireSRWLockExclusive(this + 6);
    LODWORD(v2[1].Ptr) = GetCurrentThreadId();
    BYTE1(this[20].Ptr) = 1;
    v16 = v2;
    v3 = Container::Manager::Core::Details::ResourceOperation::CancelLocked(this, &v16);
    if ( v3 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x221D,
        (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\core\\lib\\resourcebroker.cpp",
        (const char *)(unsigned int)v3,
        v14);
    wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&this[37], 0);
    utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&this[16]);
    Ptr = (struct _TP_WORK *)this[10].Ptr;
    if ( Ptr )
    {
      WaitForThreadpoolWorkCallbacks(Ptr, 1);
      v5 = (struct _TP_WORK *)this[10].Ptr;
      if ( v5 )
      {
        LastError = GetLastError();
        CloseThreadpoolWork(v5);
        SetLastError(LastError);
      }
      this[10].Ptr = 0;
    }
  }
  this[39].Ptr = &CmTraceProvider::ResourceOperation::`vftable';
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(&this[39]);
  wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(&this[39]);
  wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(&this[37], 0);
  if ( LOBYTE(this[36].Ptr) )
    Container::Manager::Core::Details::MaterializeContext::~MaterializeContext((Container::Manager::Core::Details::MaterializeContext *)&this[21]);
  utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(&this[16]);
  v7 = (utl::_RefCountBase *)this[15].Ptr;
  if ( v7 )
    utl::_RefCountBase::_DecStrong(v7);
  v8 = (utl::_RefCountBase *)this[13].Ptr;
  if ( v8 )
    utl::_RefCountBase::_DecStrong(v8);
  v9 = this[11].Ptr;
  if ( v9 && !CloseHandle(v9) )
    wil::details::in1diag3::_FailFast_GetLastError(retaddr, (void *)0xA0B, v10, v11);
  v12 = (struct _TP_WORK *)this[10].Ptr;
  if ( v12 )
    CloseThreadpoolWork(v12);
  if ( LOBYTE(this[3].Ptr) )
  {
    v13 = (Container::Manager::Core::ResourceHandle *)this[2].Ptr;
    this[2].Ptr = 0;
    if ( v13 )
    {
      Container::Manager::Core::ResourceHandle::~ResourceHandle(v13);
      operator delete(v13, (const struct std::nothrow_t *)0x58);
    }
  }
}

```

## disassembly

```asm
0x18004ff1c  mov     [rsp+arg_8], rbx
0x18004ff21  mov     [rsp+arg_10], rsi
0x18004ff26  push    rdi; int
0x18004ff27  sub     rsp, 20h
0x18004ff2b  mov     rdi, rcx
0x18004ff2e  cmp     dword ptr [rcx+40h], 0
0x18004ff32  jz      loc_180050000
0x18004ff38  lea     rbx, [rcx+30h]
0x18004ff3c  mov     rcx, rbx; SRWLock
0x18004ff3f  call    cs:__imp_AcquireSRWLockExclusive
0x18004ff46  nop     dword ptr [rax+rax+00h]
0x18004ff4b  call    cs:__imp_GetCurrentThreadId
0x18004ff52  nop     dword ptr [rax+rax+00h]
0x18004ff57  mov     [rbx+8], eax
0x18004ff5a  mov     byte ptr [rdi+0A1h], 1
0x18004ff61  mov     [rsp+28h+arg_0], rbx
0x18004ff66  lea     rdx, [rsp+28h+arg_0]
0x18004ff6b  mov     rcx, rdi
0x18004ff6e  call    ?CancelLocked@ResourceOperation@Details@Core@Manager@Container@@AEAAJV?$ReleaseOnScopeExit@$0A@@SrwLock@Csl@@@Z; Container::Manager::Core::Details::ResourceOperation::CancelLocked(Csl::SrwLock::ReleaseOnScopeExit<0>)
0x18004ff73  mov     rcx, [rsp+28h]; this
0x18004ff78  test    eax, eax
0x18004ff7a  jns     short loc_18004FF90
0x18004ff7c  mov     r9d, eax; char *
0x18004ff7f  lea     r8, aOnecoreBaseGen_73; "onecore\\base\\gendrv\\silos\\clem\\cor"...
0x18004ff86  mov     edx, 221Dh; void *
0x18004ff8b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004ff90  lea     rcx, [rdi+128h]
0x18004ff97  xor     edx, edx
0x18004ff99  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18004ff9e  lea     rcx, [rdi+80h]
0x18004ffa5  call    ?clear@?$_Tree@PEAVResourceOperation@Details@Core@Manager@Container@@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@PEAVResourceOperation@Details@Core@Manager@Container@@@7@V?$allocator@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(void)
0x18004ffaa  mov     rcx, [rdi+50h]; pwk
0x18004ffae  test    rcx, rcx
0x18004ffb1  jz      short loc_180050000
0x18004ffb3  mov     edx, 1; fCancelPendingCallbacks
0x18004ffb8  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x18004ffbf  nop     dword ptr [rax+rax+00h]
0x18004ffc4  mov     rsi, [rdi+50h]
0x18004ffc8  test    rsi, rsi
0x18004ffcb  jz      short loc_18004FFF8
0x18004ffcd  call    cs:__imp_GetLastError
0x18004ffd4  nop     dword ptr [rax+rax+00h]
0x18004ffd9  mov     ebx, eax
0x18004ffdb  mov     rcx, rsi; pwk
0x18004ffde  call    cs:__imp_CloseThreadpoolWork
0x18004ffe5  nop     dword ptr [rax+rax+00h]
0x18004ffea  mov     ecx, ebx; dwErrCode
0x18004ffec  call    cs:__imp_SetLastError
0x18004fff3  nop     dword ptr [rax+rax+00h]
0x18004fff8  mov     qword ptr [rdi+50h], 0
0x180050000  lea     rbx, [rdi+138h]
0x180050007  lea     rax, ??_7ResourceOperation@CmTraceProvider@@6B@; const CmTraceProvider::ResourceOperation::`vftable'
0x18005000e  mov     [rbx], rax
0x180050011  mov     rcx, rbx
0x180050014  call    ?Destroy@?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@IEAAXXZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::Destroy(void)
0x180050019  mov     rcx, rbx
0x18005001c  call    ??1?$ActivityBase@VCmTraceProvider@@$00$0EAAAAAAAAAAA@$04$0BAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@XZ; wil::ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>::~ActivityBase<CmTraceProvider,1,70368744177664,5,16777216,_TlgReflectorTag_Param0IsProviderType>(void)
0x180050021  lea     rcx, [rdi+128h]
0x180050028  xor     edx, edx
0x18005002a  call    ?reset@?$unique_ptr@V?$AsyncOperation@X@Csl@@U?$default_delete@V?$AsyncOperation@X@Csl@@@wistd@@@wistd@@QEAAXPEAV?$AsyncOperation@X@Csl@@@Z; wistd::unique_ptr<Csl::AsyncOperation<void>,wistd::default_delete<Csl::AsyncOperation<void>>>::reset(Csl::AsyncOperation<void> *)
0x18005002f  lea     rcx, [rdi+0A8h]; this
0x180050036  cmp     byte ptr [rcx+78h], 0
0x18005003a  jz      short loc_180050041
0x18005003c  call    ??1MaterializeContext@Details@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::Details::MaterializeContext::~MaterializeContext(void)
0x180050041  lea     rcx, [rdi+80h]
0x180050048  call    ?clear@?$_Tree@PEAVResourceOperation@Details@Core@Manager@Container@@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@U?$less@PEAVResourceOperation@Details@Core@Manager@Container@@@7@V?$allocator@U?$pair@QEAVResourceOperation@Details@Core@Manager@Container@@V?$unique_ptr@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@U?$default_delete@UDependencyContext@ResourceOperation@Details@Core@Manager@Container@@@wistd@@@wistd@@@utl@@@7@$0A@@utl@@QEAAXXZ; utl::_Tree<Container::Manager::Core::Details::ResourceOperation *,utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>,utl::less<Container::Manager::Core::Details::ResourceOperation *>,utl::allocator<utl::pair<Container::Manager::Core::Details::ResourceOperation * const,wistd::unique_ptr<Container::Manager::Core::Details::ResourceOperation::DependencyContext,wistd::default_delete<Container::Manager::Core::Details::ResourceOperation::DependencyContext>>>>,0>::clear(void)
0x18005004d  nop
0x18005004e  mov     rcx, [rdi+78h]; this
0x180050052  test    rcx, rcx
0x180050055  jz      short loc_18005005D
0x180050057  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005005c  nop
0x18005005d  mov     rcx, [rdi+68h]; this
0x180050061  test    rcx, rcx
0x180050064  jz      short loc_18005006C
0x180050066  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18005006b  nop
0x18005006c  mov     rcx, [rdi+58h]; hObject
0x180050070  test    rcx, rcx
0x180050073  jz      short loc_180050085
0x180050075  call    cs:__imp_CloseHandle
0x18005007c  nop     dword ptr [rax+rax+00h]
0x180050081  test    eax, eax
0x180050083  jz      short loc_1800500D8
0x180050085  mov     rcx, [rdi+50h]; pwk
0x180050089  test    rcx, rcx
0x18005008c  jz      short loc_18005009A
0x18005008e  call    cs:__imp_CloseThreadpoolWork
0x180050095  nop     dword ptr [rax+rax+00h]
0x18005009a  cmp     byte ptr [rdi+18h], 0
0x18005009e  jz      short loc_1800500C7
0x1800500a0  mov     rbx, [rdi+10h]
0x1800500a4  mov     qword ptr [rdi+10h], 0
0x1800500ac  test    rbx, rbx
0x1800500af  jz      short loc_1800500C7
0x1800500b1  mov     rcx, rbx; this
0x1800500b4  call    ??1ResourceHandle@Core@Manager@Container@@QEAA@XZ; Container::Manager::Core::ResourceHandle::~ResourceHandle(void)
0x1800500b9  mov     edx, 58h ; 'X'; struct std::nothrow_t *
0x1800500be  mov     rcx, rbx; void *
0x1800500c1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800500c6  nop
0x1800500c7  mov     rbx, [rsp+28h+arg_8]
0x1800500cc  mov     rsi, [rsp+28h+arg_10]
0x1800500d1  add     rsp, 20h
0x1800500d5  pop     rdi
0x1800500d6  retn
0x1800500d8  mov     rcx, [rsp+28h]; this
0x1800500dd  mov     edx, 0A0Bh; void *
0x1800500e2  call    ?_FailFast_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_GetLastError(void *,uint,char const *)
```
