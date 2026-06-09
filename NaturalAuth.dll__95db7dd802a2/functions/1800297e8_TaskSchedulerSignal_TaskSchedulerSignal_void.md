# TaskSchedulerSignal::~TaskSchedulerSignal(void)

- ea: `0x1800297e8`
- end: `0x1800298af`
- name: `??1TaskSchedulerSignal@@UEAA@XZ`
- size: `199`
- prototype: `void __fastcall(TaskSchedulerSignal *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callers

- `0x180029bc0`

## callees

- `0x18000b5b0`
- `0x18002072c`
- `0x180029738`
- `0x180029774`
- `0x1800297e8`
- `0x18002b17c`
- `0x18002cd64`
- `0x18002cdf8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002980b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002980b`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180029871`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180029871`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029883`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x180029883`

## pseudocode

```c
void __fastcall TaskSchedulerSignal::~TaskSchedulerSignal(TaskSchedulerSignal *this)
{
  __int64 v2; // rcx
  __int64 **v3; // rax
  __int64 *v4; // rbp
  __int64 *i; // rbx
  __int64 v6; // rax
  __int64 v7; // rcx
  __int64 v8; // [rsp+40h] [rbp+8h] BYREF
  __int64 v9; // [rsp+48h] [rbp+10h] BYREF
  RTL_SRWLOCK *v10; // [rsp+50h] [rbp+18h] BYREF

  *(_QWORD *)this = &TaskSchedulerSignal::`vftable';
  AcquireSRWLockExclusive(&stru_18005FCC8);
  v10 = &stru_18005FCC8;
  v3 = (__int64 **)*((_QWORD *)this + 6);
  v4 = v3[1];
  for ( i = *v3; i != v4; ++i )
  {
    v6 = *i;
    v8 = v6;
    if ( v6 )
      _InterlockedIncrement((volatile signed __int32 *)(v6 + 16));
    std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::find(
      v2,
      &v9,
      &v8);
    std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Erase_unchecked(
      v7,
      v9);
    _bstr_t::_Free((_bstr_t *)&v8);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  if ( CoInitializeEx(0, 0) >= 0 )
  {
    DeleteTasks(*((__int64 ****)this + 6));
    CoUninitialize();
  }
  std::unique_ptr<TaskSchedulerSignal::Impl>::~unique_ptr<TaskSchedulerSignal::Impl>((_QWORD *)this + 6);
  *(_QWORD *)this = &TimeSignal::`vftable';
  GenericPlugin::DefaultSignal::~DefaultSignal((void **)this);
}

```

## disassembly

```asm
0x1800297e8  mov     [rsp+arg_18], rbx
0x1800297ed  push    rbp
0x1800297ee  push    rsi
0x1800297ef  push    rdi
0x1800297f0  sub     rsp, 20h
0x1800297f4  mov     rdi, rcx
0x1800297f7  lea     rax, ??_7TaskSchedulerSignal@@6B@; const TaskSchedulerSignal::`vftable'
0x1800297fe  mov     [rcx], rax
0x180029801  lea     rbx, stru_18005FCC8
0x180029808  mov     rcx, rbx; SRWLock
0x18002980b  call    cs:__imp_AcquireSRWLockExclusive
0x180029811  mov     [rsp+38h+arg_10], rbx
0x180029816  lea     rsi, [rdi+30h]
0x18002981a  mov     rax, [rsi]
0x18002981d  mov     rbp, [rax+8]
0x180029821  mov     rbx, [rax]
0x180029824  jmp     short loc_18002985E
0x180029826  mov     rax, [rbx]
0x180029829  mov     [rsp+38h+arg_0], rax
0x18002982e  test    rax, rax
0x180029831  jz      short loc_180029837
0x180029833  lock inc dword ptr [rax+10h]
0x180029837  lea     r8, [rsp+38h+arg_0]
0x18002983c  lea     rdx, [rsp+38h+arg_8]
0x180029841  call    ?find@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@std@@@std@@@2@AEBV_bstr_t@@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::find(_bstr_t const &)
0x180029846  mov     rdx, [rsp+38h+arg_8]
0x18002984b  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@V_bstr_t@@PEAVTaskSchedulerSignal@@U?$less@V_bstr_t@@@std@@V?$allocator@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@4@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBV_bstr_t@@PEAVTaskSchedulerSignal@@@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<_bstr_t,TaskSchedulerSignal *,std::less<_bstr_t>,std::allocator<std::pair<_bstr_t const,TaskSchedulerSignal *>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<_bstr_t const,TaskSchedulerSignal *>>>,std::_Iterator_base0>)
0x180029850  lea     rcx, [rsp+38h+arg_0]; this
0x180029855  call    ?_Free@_bstr_t@@AEAAXXZ; _bstr_t::_Free(void)
0x18002985a  add     rbx, 8
0x18002985e  cmp     rbx, rbp
0x180029861  jnz     short loc_180029826
0x180029863  lea     rcx, [rsp+38h+arg_10]
0x180029868  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002986d  xor     edx, edx; dwCoInit
0x18002986f  xor     ecx, ecx; pvReserved
0x180029871  call    cs:__imp_CoInitializeEx
0x180029877  test    eax, eax
0x180029879  js      short loc_180029889
0x18002987b  mov     rcx, [rsi]
0x18002987e  call    DeleteTasks
0x180029883  call    cs:__imp_CoUninitialize
0x180029889  mov     rcx, rsi
0x18002988c  call    ??1?$unique_ptr@VImpl@TaskSchedulerSignal@@U?$default_delete@VImpl@TaskSchedulerSignal@@@std@@@std@@QEAA@XZ; std::unique_ptr<TaskSchedulerSignal::Impl>::~unique_ptr<TaskSchedulerSignal::Impl>(void)
0x180029891  lea     rax, ??_7TimeSignal@@6B@; const TimeSignal::`vftable'
0x180029898  mov     [rdi], rax
0x18002989b  mov     rcx, rdi; this
0x18002989e  mov     rbx, [rsp+38h+arg_18]
0x1800298a3  add     rsp, 20h
0x1800298a7  pop     rdi
0x1800298a8  pop     rsi
0x1800298a9  pop     rbp
0x1800298aa  jmp     ??1DefaultSignal@GenericPlugin@@UEAA@XZ; GenericPlugin::DefaultSignal::~DefaultSignal(void)
```
