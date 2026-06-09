# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x180003d78`
- end: `0x180003d8f`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `35`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180002c90`
- `0x1800048c8`
- `0x18000496c`
- `0x180004a04`
- `0x180004d14`
- `0x180004e44`
- `0x180004f74`
- `0x1800050a4`
- `0x1800051d4`
- `0x180005304`
- `0x180005434`
- `0x180005564`
- `0x180005694`
- `0x1800057c4`
- `0x1800058f4`
- `0x180005a24`
- `0x18000797c`
- `0x180007a40`
- `0x180007ac0`
- `0x180007b08`
- `0x180007bec`
- `0x180007ccc`
- `0x180007d50`
- `0x1800080d4`
- `0x1800082cc`
- `0x180009cf0`
- `0x180009d78`
- `0x18000a23c`
- `0x18000a430`
- `0x18000bfac`
- `0x18000ca10`
- `0x18000de90`
- `0x18000e4c0`
- `0x18000e55c`
- `0x18000e6d8`

## callees

- `0x180003d78`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003d84`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180003d84`

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
0x180003d78  sub     rsp, 28h
0x180003d7c  mov     rcx, [rcx]; SRWLock
0x180003d7f  test    rcx, rcx
0x180003d82  jz      short loc_180003D8A
0x180003d84  call    cs:__imp_ReleaseSRWLockExclusive
0x180003d8a  add     rsp, 28h
0x180003d8e  retn
```
