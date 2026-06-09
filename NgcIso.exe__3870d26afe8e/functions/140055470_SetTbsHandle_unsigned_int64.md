# SetTbsHandle(unsigned __int64)

- ea: `0x140055470`
- end: `0x1400554f2`
- name: `?SetTbsHandle@@YAX_K@Z`
- size: `130`
- prototype: `void __fastcall(unsigned __int64)`
- caller_count: `15`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1400551fc`
- `0x140055ca0`
- `0x140056174`
- `0x140056650`
- `0x140056a48`
- `0x140056b28`
- `0x140056fb4`
- `0x140057c94`
- `0x140057fd0`
- `0x14005833c`
- `0x1400589bc`
- `0x140059204`
- `0x14005a36c`
- `0x14005c700`
- `0x14005cb94`

## callees

- `0x14000cbe4`
- `0x140055018`
- `0x140055470`
- `0x140055f24`
- `0x140055f6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140055492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400554be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140055492`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400554be`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140055487`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140055487`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall SetTbsHandle(__int64 a1)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  DWORD v4; // [rsp+20h] [rbp-28h] BYREF
  __int64 v5; // [rsp+28h] [rbp-20h]
  _BYTE v6[24]; // [rsp+30h] [rbp-18h] BYREF
  DWORD CurrentThreadId; // [rsp+58h] [rbp+10h] BYREF
  void *v8; // [rsp+60h] [rbp+18h] BYREF
  RTL_SRWLOCK *v9; // [rsp+68h] [rbp+20h] BYREF

  AcquireSRWLockExclusive(&stru_14009D940);
  v9 = &stru_14009D940;
  CurrentThreadId = GetCurrentThreadId();
  std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::find(
    v2,
    &v8,
    &CurrentThreadId);
  if ( v8 != qword_14009DBB0 )
    std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::_Erase_unchecked();
  v4 = GetCurrentThreadId();
  v5 = a1;
  std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::_Emplace<std::pair<unsigned long,unsigned __int64>>(
    v3,
    v6,
    &v4);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
}

```

## disassembly

```asm
0x140055470  mov     [rsp+arg_0], rbx
0x140055475  push    rdi
0x140055476  sub     rsp, 40h
0x14005547a  mov     rbx, rcx
0x14005547d  lea     rdi, stru_14009D940
0x140055484  mov     rcx, rdi; SRWLock
0x140055487  call    cs:__imp_AcquireSRWLockExclusive
0x14005548d  mov     [rsp+48h+arg_18], rdi
0x140055492  call    cs:__imp_GetCurrentThreadId
0x140055498  mov     [rsp+48h+arg_8], eax
0x14005549c  lea     r8, [rsp+48h+arg_8]
0x1400554a1  lea     rdx, [rsp+48h+arg_10]
0x1400554a6  call    ?find@?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::find(ulong const &)
0x1400554ab  mov     rdx, [rsp+48h+arg_10]
0x1400554b0  cmp     rdx, cs:qword_14009DBB0
0x1400554b7  jz      short loc_1400554BE
0x1400554b9  call    ?_Erase_unchecked@?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@AEAAPEAU?$_Tree_node@U?$pair@$$CBK_K@std@@PEAX@2@V?$_Tree_unchecked_const_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@U_Iterator_base0@2@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::_Erase_unchecked(std::_Tree_unchecked_const_iterator<std::_Tree_val<std::_Tree_simple_types<std::pair<ulong const,unsigned __int64>>>,std::_Iterator_base0>)
0x1400554be  call    cs:__imp_GetCurrentThreadId
0x1400554c4  mov     [rsp+48h+var_28], eax
0x1400554c8  mov     [rsp+48h+var_20], rbx
0x1400554cd  lea     r8, [rsp+48h+var_28]
0x1400554d2  lea     rdx, [rsp+48h+var_18]
0x1400554d7  call    ??$_Emplace@U?$pair@K_K@std@@@?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBK_K@std@@PEAX@std@@_N@1@$$QEAU?$pair@K_K@1@@Z; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::_Emplace<std::pair<ulong,unsigned __int64>>(std::pair<ulong,unsigned __int64> &&)
0x1400554dc  nop
0x1400554dd  lea     rcx, [rsp+48h+arg_18]
0x1400554e2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400554e7  mov     rbx, [rsp+48h+arg_0]
0x1400554ec  add     rsp, 40h
0x1400554f0  pop     rdi
0x1400554f1  retn
```
