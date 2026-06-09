# wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)

- ea: `0x140009434`
- end: `0x140009452`
- name: `??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ`
- size: `30`
- prototype: ``
- caller_count: `17`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140008db0`
- `0x14000b888`
- `0x14000cb60`
- `0x14000cc38`
- `0x14000ccd4`
- `0x14000cf74`
- `0x14000d130`
- `0x140010abc`
- `0x140011620`
- `0x1400117b0`
- `0x140016740`
- `0x140016a28`
- `0x140016c14`
- `0x140016cb0`
- `0x140017878`
- `0x1400181d8`
- `0x14001823c`

## callees

- `0x140009434`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009440`
- `api-ms-win-core-synch-l1-1-0!ReleaseSRWLockExclusive` at `0x140009440`

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
0x140009434  sub     rsp, 28h
0x140009438  mov     rcx, [rcx]; SRWLock
0x14000943b  test    rcx, rcx
0x14000943e  jz      short loc_14000944C
0x140009440  call    cs:__imp_ReleaseSRWLockExclusive
0x140009447  nop     dword ptr [rax+rax+00h]
0x14000944c  add     rsp, 28h
0x140009450  retn
```
