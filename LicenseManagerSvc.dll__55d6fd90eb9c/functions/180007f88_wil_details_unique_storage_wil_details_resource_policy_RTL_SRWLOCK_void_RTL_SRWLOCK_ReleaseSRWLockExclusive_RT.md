# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x180007f88`
- end: `0x180007f9f`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: ``
- caller_count: `19`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x180007c30`
- `0x180007cc0`
- `0x180008528`
- `0x1800085dc`
- `0x180008678`
- `0x1800086f0`
- `0x18000951c`
- `0x1800095e8`
- `0x180009674`
- `0x1800096c8`
- `0x1800097e8`
- `0x1800098d4`
- `0x180009c18`
- `0x180009cc0`
- `0x180009e0c`
- `0x18000ab04`
- `0x18000ab98`
- `0x18000ac30`
- `0x18000ae10`

## callees

- `0x180007f88`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f94`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x180007f94`

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
0x180007f88  sub     rsp, 28h
0x180007f8c  mov     rcx, [rcx]; SRWLock
0x180007f8f  test    rcx, rcx
0x180007f92  jz      short loc_180007F9A
0x180007f94  call    cs:__imp_ReleaseSRWLockExclusive
0x180007f9a  add     rsp, 28h
0x180007f9e  retn
```
