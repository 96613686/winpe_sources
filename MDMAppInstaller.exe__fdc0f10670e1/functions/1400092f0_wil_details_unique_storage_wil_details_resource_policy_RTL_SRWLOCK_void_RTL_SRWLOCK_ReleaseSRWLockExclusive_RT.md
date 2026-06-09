# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x1400092f0`
- end: `0x140009307`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `23`
- prototype: `void __fastcall(RTL_SRWLOCK **)`
- caller_count: `28`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140007d60`
- `0x14000b2e0`
- `0x14000b394`
- `0x14000b430`
- `0x14000b65c`
- `0x14000b888`
- `0x14000b9c8`
- `0x14000bb08`
- `0x14000bc48`
- `0x14000bd88`
- `0x14000bec8`
- `0x14000c008`
- `0x14000c148`
- `0x14000c288`
- `0x14000e4d8`
- `0x14000e5a0`
- `0x14000e62c`
- `0x14000e680`
- `0x14000edec`
- `0x14000f00c`
- `0x14000f0b8`
- `0x14000f400`
- `0x14000f5bc`
- `0x140010e28`
- `0x140010ec8`
- `0x140011140`
- `0x140011340`
- `0x140015e3c`

## callees

- `0x1400092f0`

## import_xrefs

- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400092fc`
- `KERNEL32!ReleaseSRWLockExclusive` at `0x1400092fc`

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
0x1400092f0  sub     rsp, 28h
0x1400092f4  mov     rcx, [rcx]; SRWLock
0x1400092f7  test    rcx, rcx
0x1400092fa  jz      short loc_140009302
0x1400092fc  call    cs:__imp_ReleaseSRWLockExclusive
0x140009302  add     rsp, 28h
0x140009306  retn
```
