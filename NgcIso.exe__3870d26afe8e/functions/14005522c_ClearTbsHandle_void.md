# ClearTbsHandle(void)

- ea: `0x14005522c`
- end: `0x1400552d3`
- name: `?ClearTbsHandle@@YAXXZ`
- size: `167`
- prototype: `void(void)`
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140056000`
- `0x140056068`
- `0x140056174`
- `0x140056650`
- `0x140056a48`
- `0x140056fb4`
- `0x140057c94`
- `0x140057fd0`
- `0x1400589bc`
- `0x14005a36c`
- `0x14005c700`
- `0x14005cb94`

## callees

- `0x14000cbe4`
- `0x14005522c`
- `0x140055e6c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140055247`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140055247`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005523c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x14005523c`

## pseudocode

```c
void ClearTbsHandle(void)
{
  DWORD CurrentThreadId; // eax
  void *v1; // r9
  _BYTE *v2; // rdx
  _QWORD *v3; // rcx
  _QWORD *i; // r8
  _QWORD v5[3]; // [rsp+20h] [rbp-18h] BYREF
  RTL_SRWLOCK *v6; // [rsp+40h] [rbp+8h] BYREF

  AcquireSRWLockExclusive(&stru_14009D940);
  v6 = &stru_14009D940;
  CurrentThreadId = GetCurrentThreadId();
  v1 = qword_14009DBB0;
  v2 = qword_14009DBB0;
  v3 = (_QWORD *)*((_QWORD *)qword_14009DBB0 + 1);
  for ( i = v3; !*((_BYTE *)i + 25); i = (_QWORD *)*i )
  {
    if ( *((_DWORD *)i + 8) >= CurrentThreadId )
    {
      if ( v2[25] && CurrentThreadId < *((_DWORD *)i + 8) )
        v2 = i;
      v1 = i;
    }
    else
    {
      i += 2;
    }
  }
  if ( !v2[25] )
    v3 = *(_QWORD **)v2;
  while ( !*((_BYTE *)v3 + 25) )
  {
    if ( CurrentThreadId >= *((_DWORD *)v3 + 8) )
    {
      v3 = (_QWORD *)v3[2];
    }
    else
    {
      v2 = v3;
      v3 = (_QWORD *)*v3;
    }
  }
  v5[1] = v2;
  v5[0] = v1;
  std::_Tree<std::_Tmap_traits<unsigned long,unsigned __int64,std::less<unsigned long>,std::allocator<std::pair<unsigned long const,unsigned __int64>>,0>>::_Erase(
    v3,
    v5,
    i);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
}

```

## disassembly

```asm
0x14005522c  push    rbx
0x14005522e  sub     rsp, 30h
0x140055232  lea     rbx, stru_14009D940
0x140055239  mov     rcx, rbx; SRWLock
0x14005523c  call    cs:__imp_AcquireSRWLockExclusive
0x140055242  mov     [rsp+38h+arg_0], rbx
0x140055247  call    cs:__imp_GetCurrentThreadId
0x14005524d  mov     r9, cs:qword_14009DBB0
0x140055254  xor     r10d, r10d
0x140055257  mov     rdx, r9
0x14005525a  mov     rcx, [r9+8]
0x14005525e  mov     r8, rcx
0x140055261  cmp     [rcx+19h], r10b
0x140055265  jnz     short loc_14005528D
0x140055267  cmp     [r8+20h], eax
0x14005526b  jnb     short loc_140055273
0x14005526d  add     r8, 10h
0x140055271  jmp     short loc_140055284
0x140055273  cmp     [rdx+19h], r10b
0x140055277  jz      short loc_140055281
0x140055279  cmp     eax, [r8+20h]
0x14005527d  cmovb   rdx, r8
0x140055281  mov     r9, r8
0x140055284  mov     r8, [r8]
0x140055287  cmp     [r8+19h], r10b
0x14005528b  jz      short loc_140055267
0x14005528d  cmp     [rdx+19h], r10b
0x140055291  jnz     short loc_1400552A9
0x140055293  mov     rcx, [rdx]
0x140055296  jmp     short loc_1400552A9
0x140055298  cmp     eax, [rcx+20h]
0x14005529b  jnb     short loc_1400552A5
0x14005529d  mov     rdx, rcx
0x1400552a0  mov     rcx, [rcx]
0x1400552a3  jmp     short loc_1400552A9
0x1400552a5  mov     rcx, [rcx+10h]
0x1400552a9  cmp     [rcx+19h], r10b
0x1400552ad  jz      short loc_140055298
0x1400552af  mov     [rsp+38h+var_10], rdx
0x1400552b4  lea     rdx, [rsp+38h+var_18]
0x1400552b9  mov     [rsp+38h+var_18], r9
0x1400552be  call    ?_Erase@?$_Tree@V?$_Tmap_traits@K_KU?$less@K@std@@V?$allocator@U?$pair@$$CBK_K@std@@@2@$0A@@std@@@std@@AEAA_KU?$pair@PEAU?$_Tree_node@U?$pair@$$CBK_K@std@@PEAX@std@@PEAU12@@2@@Z; std::_Tree<std::_Tmap_traits<ulong,unsigned __int64,std::less<ulong>,std::allocator<std::pair<ulong const,unsigned __int64>>,0>>::_Erase(std::pair<std::_Tree_node<std::pair<ulong const,unsigned __int64>,void *> *,std::_Tree_node<std::pair<ulong const,unsigned __int64>,void *> *>)
0x1400552c3  lea     rcx, [rsp+38h+arg_0]
0x1400552c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400552cd  add     rsp, 30h
0x1400552d1  pop     rbx
0x1400552d2  retn
```
