# CommonLibraryDllProcessDetach

- ea: `0x18000bd38`
- end: `0x18000bdf9`
- name: `CommonLibraryDllProcessDetach`
- size: `193`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18000acb0`

## callees

- `0x18000bd38`
- `0x18000be3c`
- `0x18000be8c`
- `0x18000beac`
- `0x18000bf28`

## import_xrefs

- `ntdll!RtlDeleteCriticalSection` at `0x18000bdbf`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bdd8`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bdbf`
- `ntdll!RtlDeleteCriticalSection` at `0x18000bdd8`

## pseudocode

```c
NTSTATUS __fastcall CommonLibraryDllProcessDetach(char a1)
{
  PVOID v2; // rbx
  NTSTATUS result; // eax
  PRTL_CRITICAL_SECTION i; // rbx
  char v5; // [rsp+38h] [rbp+10h] BYREF

  wil::RtlAcquireSRWLockExclusive(&v5, qword_18002B290);
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  wil::RtlAcquireSRWLockExclusive(&v5, &qword_18002B280);
  if ( P )
  {
    Common::GenericMap<unsigned short const *,unsigned short const *>::RemoveAll((PRTL_AVL_TABLE)P);
    v2 = P;
    if ( P )
    {
      Common::GenericMap<unsigned short const *,unsigned short const *>::RemoveAll((PRTL_AVL_TABLE)P);
      Common::GlobalHeap::Free(v2);
    }
    P = 0;
  }
  result = wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  if ( !a1 )
  {
    result = RtlDeleteCriticalSection(&Common::mainLock);
    for ( i = Common::StaticLock::head; i; i = *(PRTL_CRITICAL_SECTION *)&i[1].LockCount )
    {
      result = (NTSTATUS)i[1].DebugInfo;
      if ( result )
        result = RtlDeleteCriticalSection(i);
    }
    Common::StaticLock::head = 0;
  }
  return result;
}

```

## disassembly

```asm
0x18000bd38  mov     [rsp+arg_0], rbx
0x18000bd3d  push    rdi
0x18000bd3e  sub     rsp, 20h
0x18000bd42  mov     dil, cl
0x18000bd45  lea     rdx, qword_18002B290
0x18000bd4c  lea     rcx, [rsp+28h+arg_8]
0x18000bd51  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000bd56  lea     rcx, [rsp+28h+arg_8]
0x18000bd5b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bd60  lea     rdx, qword_18002B280
0x18000bd67  lea     rcx, [rsp+28h+arg_8]
0x18000bd6c  call    ?RtlAcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::RtlAcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x18000bd71  mov     rcx, cs:P; Table
0x18000bd78  test    rcx, rcx
0x18000bd7b  jz      short loc_18000BDA9
0x18000bd7d  call    ?RemoveAll@?$GenericMap@PEBGPEBG@Common@@QEAAXXZ; Common::GenericMap<ushort const *,ushort const *>::RemoveAll(void)
0x18000bd82  mov     rbx, cs:P
0x18000bd89  test    rbx, rbx
0x18000bd8c  jz      short loc_18000BD9E
0x18000bd8e  mov     rcx, rbx; Table
0x18000bd91  call    ?RemoveAll@?$GenericMap@PEBGPEBG@Common@@QEAAXXZ; Common::GenericMap<ushort const *,ushort const *>::RemoveAll(void)
0x18000bd96  mov     rcx, rbx; P
0x18000bd99  call    ?Free@GlobalHeap@Common@@SAXPEAX@Z; Common::GlobalHeap::Free(void *)
0x18000bd9e  mov     cs:P, 0
0x18000bda9  lea     rcx, [rsp+28h+arg_8]
0x18000bdae  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?RtlReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&RtlReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,2>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000bdb3  test    dil, dil
0x18000bdb6  jnz     short loc_18000BDEE
0x18000bdb8  lea     rcx, ?mainLock@Common@@3U_RTL_CRITICAL_SECTION@@A; CriticalSection
0x18000bdbf  call    cs:__imp_RtlDeleteCriticalSection
0x18000bdc5  mov     rbx, cs:?head@StaticLock@Common@@0PEAV12@EA; Common::StaticLock * Common::StaticLock::head
0x18000bdcc  jmp     short loc_18000BDE2
0x18000bdce  mov     eax, [rbx+28h]
0x18000bdd1  test    eax, eax
0x18000bdd3  jz      short loc_18000BDDE
0x18000bdd5  mov     rcx, rbx; CriticalSection
0x18000bdd8  call    cs:__imp_RtlDeleteCriticalSection
0x18000bdde  mov     rbx, [rbx+30h]
0x18000bde2  test    rbx, rbx
0x18000bde5  jnz     short loc_18000BDCE
0x18000bde7  mov     cs:?head@StaticLock@Common@@0PEAV12@EA, rbx; Common::StaticLock * Common::StaticLock::head
0x18000bdee  mov     rbx, [rsp+28h+arg_0]
0x18000bdf3  add     rsp, 20h
0x18000bdf7  pop     rdi
0x18000bdf8  retn
```
