# GetTbsHandle(void)

- ea: `0x1400552dc`
- end: `0x140055339`
- name: `?GetTbsHandle@@YA_KXZ`
- size: `93`
- prototype: `unsigned __int64(void)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140055ca0`
- `0x1400575dc`
- `0x140057fd0`
- `0x14005ac70`

## callees

- `0x14000cbe4`
- `0x1400552dc`
- `0x140055f6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400552f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400552f7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400552ec`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400552ec`

## pseudocode

```c
__int64 GetTbsHandle(void)
{
  __int64 v0; // rcx
  __int64 v1; // rbx
  DWORD CurrentThreadId; // [rsp+30h] [rbp+8h] BYREF
  _QWORD *v4; // [rsp+38h] [rbp+10h] BYREF
  RTL_SRWLOCK *v5; // [rsp+40h] [rbp+18h] BYREF

  AcquireSRWLockExclusive(&stru_14009D940);
  v5 = &stru_14009D940;
  CurrentThreadId = GetCurrentThreadId();
  std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::find(
    v0,
    &v4,
    &CurrentThreadId);
  if ( v4 == qword_14009DBB0 )
    v1 = 0;
  else
    v1 = v4[5];
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  return v1;
}

```

## disassembly

```asm
0x1400552dc  push    rbx
0x1400552de  sub     rsp, 20h
0x1400552e2  lea     rbx, stru_14009D940
0x1400552e9  mov     rcx, rbx; SRWLock
0x1400552ec  call    cs:__imp_AcquireSRWLockExclusive
0x1400552f2  mov     [rsp+28h+arg_10], rbx
0x1400552f7  call    cs:__imp_GetCurrentThreadId
0x1400552fd  lea     r8, [rsp+28h+arg_0]
0x140055302  mov     [rsp+28h+arg_0], eax
0x140055306  lea     rdx, [rsp+28h+arg_8]
0x14005530b  call    ?find@?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@QEAA?AV?$_Tree_iterator@V?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBK_K@std@@@std@@@std@@@2@AEBK@Z; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::find(ulong const &)
0x140055310  mov     r8, [rsp+28h+arg_8]
0x140055315  cmp     r8, cs:qword_14009DBB0
0x14005531c  jz      short loc_140055324
0x14005531e  mov     rbx, [r8+28h]
0x140055322  jmp     short loc_140055326
0x140055324  xor     ebx, ebx
0x140055326  lea     rcx, [rsp+28h+arg_10]
0x14005532b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140055330  mov     rax, rbx
0x140055333  add     rsp, 20h
0x140055337  pop     rbx
0x140055338  retn
```
