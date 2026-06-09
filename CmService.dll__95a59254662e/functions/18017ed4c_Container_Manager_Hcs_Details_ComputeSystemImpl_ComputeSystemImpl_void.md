# Container::Manager::Hcs::Details::ComputeSystemImpl::~ComputeSystemImpl(void)

- ea: `0x18017ed4c`
- end: `0x18017ef75`
- name: `??1ComputeSystemImpl@Details@Hcs@Manager@Container@@QEAA@XZ`
- size: `553`
- prototype: `void __fastcall(Container::Manager::Hcs::Details::ComputeSystemImpl *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18011e8f0`
- `0x18012309c`

## callees

- `0x180004fc4`
- `0x1800051b0`
- `0x18003de70`
- `0x1800471dc`
- `0x180053ea0`
- `0x180175b9c`
- `0x180175c18`
- `0x180175f38`
- `0x18017ed4c`
- `0x18017ef7c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017ed93`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18017ed93`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ee3e`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x18017ee3e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ee80`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18017ee80`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017ee9f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18017ee9f`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ee91`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ef56`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ee91`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseComputeSystem` at `0x18017ef56`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017edf2`
- `ext-ms-win-hyperv-compute-l1-2-0!HcsCloseOperation` at `0x18017edf2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall Container::Manager::Hcs::Details::ComputeSystemImpl::~ComputeSystemImpl(RTL_SRWLOCK *this)
{
  _QWORD *v2; // rax
  RTL_SRWLOCK *v3; // r14
  _QWORD *v4; // rbx
  _QWORD *v5; // rsi
  void *v6; // r12
  _QWORD *v7; // r13
  utl::_RefCountBase *v8; // rcx
  HCS_OPERATION v9; // rcx
  _QWORD *v10; // rdx
  __int64 v11; // rbx
  HCS_SYSTEM v12; // rsi
  DWORD LastError; // ebx
  utl::_RefCountBase *v14; // rcx
  utl::_RefCountBase *v15; // rcx
  RTL_SRWLOCK *v16; // rcx
  utl::_RefCountBase *v17; // rcx
  HCS_SYSTEM v18; // rcx
  _QWORD *Ptr; // [rsp+20h] [rbp-18h] BYREF
  PVOID v20; // [rsp+28h] [rbp-10h]
  char v21; // [rsp+88h] [rbp+50h] BYREF

  v20 = 0;
  v2 = operator new(0x40u);
  *v2 = v2;
  v2[1] = v2;
  v2[2] = v2;
  *((_WORD *)v2 + 12) = 257;
  Ptr = v2;
  AcquireSRWLockExclusive(this + 4);
  v3 = this + 34;
  if ( &Ptr != (_QWORD **)&this[34] )
  {
    v4 = Ptr;
    v5 = (_QWORD *)Ptr[1];
    while ( !*((_BYTE *)v5 + 25) )
    {
      std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *>>>(
        &Ptr,
        &Ptr,
        v5[2]);
      v6 = v5;
      v7 = v5;
      v5 = (_QWORD *)*v5;
      v8 = (utl::_RefCountBase *)v7[7];
      if ( v8 )
        utl::_RefCountBase::_DecStrong(v8);
      v9 = (HCS_OPERATION)v7[5];
      if ( v9 )
        HcsCloseOperation(v9);
      operator delete(v6, (const struct std::nothrow_t *)0x40);
    }
    v4[1] = v4;
    *v4 = v4;
    v4[2] = v4;
    v10 = Ptr;
    Ptr = v3->Ptr;
    v3->Ptr = v10;
    v20 = this[35].Ptr;
    this[35].Ptr = 0;
  }
  if ( this != (RTL_SRWLOCK *)-32LL )
    ReleaseSRWLockExclusive(this + 4);
  while ( v20 )
  {
    v11 = *Ptr;
    Csl::CompletionEvent<void>::CompleteInternal(*(_QWORD *)(*Ptr + 48LL), 2147943623LL);
    std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>>>,0>(
      &Ptr,
      &v21,
      v11);
  }
  v12 = (HCS_SYSTEM)this[3].Ptr;
  if ( v12 )
  {
    LastError = GetLastError();
    HcsCloseComputeSystem(v12);
    SetLastError(LastError);
  }
  this[3].Ptr = 0;
  std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(&Ptr);
  std::wstring::~wstring(&this[117]);
  std::wstring::~wstring(&this[113]);
  v14 = (utl::_RefCountBase *)this[112].Ptr;
  if ( v14 )
    utl::_RefCountBase::_DecStrong(v14);
  v15 = (utl::_RefCountBase *)this[110].Ptr;
  if ( v15 )
    utl::_RefCountBase::_DecStrong(v15);
  std::wstring::~wstring(&this[105]);
  Schema::Responses::System::CrashReport::~CrashReport((Schema::Responses::System::CrashReport *)&this[37]);
  std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(&this[34]);
  if ( LOBYTE(this[31].Ptr) )
  {
    v16 = (RTL_SRWLOCK *)this[24].Ptr;
    if ( v16 != &this[26] )
      operator delete(v16, (const struct std::nothrow_t *)&std::nothrow);
  }
  v17 = (utl::_RefCountBase *)this[8].Ptr;
  if ( v17 )
    utl::_RefCountBase::_DecStrong(v17);
  v18 = (HCS_SYSTEM)this[3].Ptr;
  if ( v18 )
    HcsCloseComputeSystem(v18);
}

```

## disassembly

```asm
0x18017ed4c  push    rbp
0x18017ed4e  push    rbx
0x18017ed4f  push    rsi
0x18017ed50  push    rdi
0x18017ed51  push    r12
0x18017ed53  push    r13
0x18017ed55  push    r14
0x18017ed57  push    r15
0x18017ed59  mov     rbp, rsp
0x18017ed5c  sub     rsp, 38h
0x18017ed60  mov     rdi, rcx
0x18017ed63  xor     r13d, r13d
0x18017ed66  mov     [rbp+var_18], r13
0x18017ed6a  mov     [rbp+var_10], r13
0x18017ed6e  lea     ecx, [r13+40h]; Size
0x18017ed72  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18017ed77  mov     [rax], rax
0x18017ed7a  mov     [rax+8], rax
0x18017ed7e  mov     [rax+10h], rax
0x18017ed82  mov     word ptr [rax+18h], 101h
0x18017ed88  mov     [rbp+var_18], rax
0x18017ed8c  lea     r15, [rdi+20h]
0x18017ed90  mov     rcx, r15; SRWLock
0x18017ed93  call    cs:__imp_AcquireSRWLockExclusive
0x18017ed9a  nop     dword ptr [rax+rax+00h]
0x18017ed9f  lea     r14, [rdi+110h]
0x18017eda6  lea     rax, [rbp+var_18]
0x18017edaa  cmp     rax, r14
0x18017edad  jz      loc_18017EE36
0x18017edb3  mov     rbx, [rbp+var_18]
0x18017edb7  mov     rsi, [rbx+8]
0x18017edbb  jmp     short loc_18017EE0B
0x18017edbd  mov     r8, [rsi+10h]
0x18017edc1  lea     rdx, [rbp+var_18]
0x18017edc5  lea     rcx, [rbp+var_18]
0x18017edc9  call    ??$_Erase_tree@V?$allocator@U?$_Tree_node@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAX@std@@@std@@@?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@@std@@@std@@QEAAXAEAV?$allocator@U?$_Tree_node@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAX@std@@@1@PEAU?$_Tree_node@U?$pair@QEAUHCS_OPERATION__@@UOperationContext@ComputeSystemImpl@Details@Hcs@Manager@Container@@@std@@PEAX@1@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>>>::_Erase_tree<std::allocator<std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *>>>(std::allocator<std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *>> &,std::_Tree_node<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemImpl::OperationContext>,void *> *)
0x18017edce  mov     r12, rsi
0x18017edd1  mov     r13, rsi
0x18017edd4  mov     rsi, [rsi]
0x18017edd7  mov     rcx, [r13+38h]; this
0x18017eddb  test    rcx, rcx
0x18017edde  jz      short loc_18017EDE6
0x18017ede0  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017ede5  nop
0x18017ede6  mov     rcx, [r13+28h]; operation
0x18017edea  xor     r13d, r13d
0x18017eded  test    rcx, rcx
0x18017edf0  jz      short loc_18017EDFE
0x18017edf2  call    cs:__imp_HcsCloseOperation
0x18017edf9  nop     dword ptr [rax+rax+00h]
0x18017edfe  mov     edx, 40h ; '@'; struct std::nothrow_t *
0x18017ee03  mov     rcx, r12; void *
0x18017ee06  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017ee0b  cmp     [rsi+19h], r13b
0x18017ee0f  jz      short loc_18017EDBD
0x18017ee11  mov     [rbx+8], rbx
0x18017ee15  mov     [rbx], rbx
0x18017ee18  mov     [rbx+10h], rbx
0x18017ee1c  mov     rdx, [rbp+var_18]
0x18017ee20  mov     rax, [r14]
0x18017ee23  mov     [rbp+var_18], rax
0x18017ee27  mov     [r14], rdx
0x18017ee2a  mov     rax, [r14+8]
0x18017ee2e  mov     [rbp+var_10], rax
0x18017ee32  mov     [r14+8], r13
0x18017ee36  test    r15, r15
0x18017ee39  jz      short loc_18017EE4A
0x18017ee3b  mov     rcx, r15; SRWLock
0x18017ee3e  call    cs:__imp_ReleaseSRWLockExclusive
0x18017ee45  nop     dword ptr [rax+rax+00h]
0x18017ee4a  cmp     [rbp+var_10], r13
0x18017ee4e  jz      short loc_18017EE77
0x18017ee50  mov     rbx, [rbp+var_18]
0x18017ee54  mov     rbx, [rbx]
0x18017ee57  mov     edx, 800704C7h
0x18017ee5c  mov     rcx, [rbx+30h]
0x18017ee60  call    ?CompleteInternal@?$CompletionEvent@X@Csl@@AEAAXJ@Z; Csl::CompletionEvent<void>::CompleteInternal(long)
0x18017ee65  mov     r8, rbx
0x18017ee68  lea     rdx, [rbp+arg_8]
0x18017ee6c  lea     rcx, [rbp+var_18]
0x18017ee70  call    ??$erase@V?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@std@@@std@@@std@@$0A@@?$_Tree@V?$_Tmap_traits@PEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@U?$less@PEAUHCS_OPERATION__@@@std@@V?$allocator@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@9@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@std@@@std@@@1@V21@@Z; std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::erase<std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>>>,0>(std::_Tree_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>>>)
0x18017ee75  jmp     short loc_18017EE4A
0x18017ee77  mov     rsi, [rdi+18h]
0x18017ee7b  test    rsi, rsi
0x18017ee7e  jz      short loc_18017EEAB
0x18017ee80  call    cs:__imp_GetLastError
0x18017ee87  nop     dword ptr [rax+rax+00h]
0x18017ee8c  mov     ebx, eax
0x18017ee8e  mov     rcx, rsi; computeSystem
0x18017ee91  call    cs:__imp_HcsCloseComputeSystem
0x18017ee98  nop     dword ptr [rax+rax+00h]
0x18017ee9d  mov     ecx, ebx; dwErrCode
0x18017ee9f  call    cs:__imp_SetLastError
0x18017eea6  nop     dword ptr [rax+rax+00h]
0x18017eeab  mov     [rdi+18h], r13
0x18017eeaf  lea     rcx, [rbp+var_18]
0x18017eeb3  call    ??1?$_Tree@V?$_Tmap_traits@PEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@U?$less@PEAUHCS_OPERATION__@@@std@@V?$allocator@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@9@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(void)
0x18017eeb8  lea     rcx, [rdi+3A8h]; void *
0x18017eebf  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017eec4  lea     rcx, [rdi+388h]; void *
0x18017eecb  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017eed0  nop
0x18017eed1  mov     rcx, [rdi+380h]; this
0x18017eed8  test    rcx, rcx
0x18017eedb  jz      short loc_18017EEE3
0x18017eedd  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017eee2  nop
0x18017eee3  mov     rcx, [rdi+370h]; this
0x18017eeea  test    rcx, rcx
0x18017eeed  jz      short loc_18017EEF5
0x18017eeef  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017eef4  nop
0x18017eef5  lea     rcx, [rdi+348h]; void *
0x18017eefc  call    ??1?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@XZ; std::wstring::~wstring(void)
0x18017ef01  lea     rcx, [rdi+128h]; this
0x18017ef08  call    ??1CrashReport@System@Responses@Schema@@QEAA@XZ; Schema::Responses::System::CrashReport::~CrashReport(void)
0x18017ef0d  mov     rcx, r14
0x18017ef10  call    ??1?$_Tree@V?$_Tmap_traits@PEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@U?$less@PEAUHCS_OPERATION__@@@std@@V?$allocator@U?$pair@QEAUHCS_OPERATION__@@UTerminateOperationContext@ComputeSystemProcessImpl@Details@Hcs@Manager@Container@@@std@@@9@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>::~_Tree<std::_Tmap_traits<HCS_OPERATION__ *,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext,std::less<HCS_OPERATION__ *>,std::allocator<std::pair<HCS_OPERATION__ * const,Container::Manager::Hcs::Details::ComputeSystemProcessImpl::TerminateOperationContext>>,0>>(void)
0x18017ef15  cmp     [rdi+0F8h], r13b
0x18017ef1c  jz      short loc_18017EF3E
0x18017ef1e  mov     rcx, [rdi+0C0h]; void *
0x18017ef25  lea     rax, [rdi+0D0h]
0x18017ef2c  cmp     rcx, rax
0x18017ef2f  jz      short loc_18017EF3E
0x18017ef31  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18017ef38  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18017ef3d  nop
0x18017ef3e  mov     rcx, [rdi+40h]; this
0x18017ef42  test    rcx, rcx
0x18017ef45  jz      short loc_18017EF4D
0x18017ef47  call    ?_DecStrong@_RefCountBase@utl@@QEAAXXZ; utl::_RefCountBase::_DecStrong(void)
0x18017ef4c  nop
0x18017ef4d  mov     rcx, [rdi+18h]; computeSystem
0x18017ef51  test    rcx, rcx
0x18017ef54  jz      short loc_18017EF63
0x18017ef56  call    cs:__imp_HcsCloseComputeSystem
0x18017ef5d  nop     dword ptr [rax+rax+00h]
0x18017ef62  nop
0x18017ef63  add     rsp, 38h
0x18017ef67  pop     r15
0x18017ef69  pop     r14
0x18017ef6b  pop     r13
0x18017ef6d  pop     r12
0x18017ef6f  pop     rdi
0x18017ef70  pop     rsi
0x18017ef71  pop     rbx
0x18017ef72  pop     rbp
0x18017ef73  retn
```
