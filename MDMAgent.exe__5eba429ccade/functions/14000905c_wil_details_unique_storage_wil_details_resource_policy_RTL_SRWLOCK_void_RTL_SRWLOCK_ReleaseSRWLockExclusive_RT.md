# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x14000905c`
- end: `0x140009073`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x1400089c0`
- `0x14000b36c`
- `0x14000c5b8`
- `0x14000c680`
- `0x14000c714`
- `0x14000c9a8`
- `0x14000cb50`
- `0x140010298`
- `0x140010db8`
- `0x140010f40`
- `0x140015ad4`
- `0x140015d98`
- `0x140015f70`
- `0x140016010`
- `0x140016bbc`
- `0x14001750c`
- `0x140017568`

## callees

- `0x14000905c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009068`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009068`

## pseudocode

```c
void __fastcall wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(
        RTL_SRWLOCK **a1)
{
  RTL_SRWLOCK *v1; // rcx

  v1 = *a1;
  if ( v1 )
    ReleaseSRWLockExclusive(v1);
}

```

## disassembly

```asm
0x14000905c  sub     rsp, 28h
0x140009060  mov     rcx, [rcx]; SRWLock
0x140009063  test    rcx, rcx
0x140009066  jz      short loc_14000906E
0x140009068  call    cs:__imp_ReleaseSRWLockExclusive
0x14000906e  add     rsp, 28h
0x140009072  retn
```
