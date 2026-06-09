# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x140005e18`
- end: `0x140005e2f`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `16`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140003ea0`
- `0x140006b80`
- `0x140006d68`
- `0x140008578`
- `0x140008e10`
- `0x14000922c`
- `0x1400092f4`
- `0x14000948c`
- `0x1400097a4`
- `0x140009984`
- `0x14000b5fc`
- `0x14000cdac`
- `0x14000d280`
- `0x14000d530`
- `0x14000ef38`
- `0x14000efa8`

## callees

- `0x140005e18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005e24`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140005e24`

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
0x140005e18  sub     rsp, 28h
0x140005e1c  mov     rcx, [rcx]; SRWLock
0x140005e1f  test    rcx, rcx
0x140005e22  jz      short loc_140005E2A
0x140005e24  call    cs:__imp_ReleaseSRWLockExclusive
0x140005e2a  add     rsp, 28h
0x140005e2e  retn
```
