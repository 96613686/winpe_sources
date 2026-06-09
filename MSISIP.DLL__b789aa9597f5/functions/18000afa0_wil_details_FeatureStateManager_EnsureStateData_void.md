# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x18000afa0`
- end: `0x18000b023`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `131`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x1800083d4`
- `0x18000b02c`
- `0x18000be04`

## callees

- `0x1800084c8`
- `0x18000ac30`
- `0x18000aec0`
- `0x18000afa0`
- `0x18000b4e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000afe1`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000afe1`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  __int64 Shared; // rsi
  bool v3; // zf
  RTL_SRWLOCK *v5; // [rsp+30h] [rbp+8h] BYREF
  char v6; // [rsp+38h] [rbp+10h] BYREF

  if ( !this[3].Ptr )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v6);
    if ( this[3].Ptr )
      Shared = 0;
    else
      Shared = wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(&this[1]);
    AcquireSRWLockExclusive(this + 4);
    v3 = this[3].Ptr == 0;
    v5 = this + 4;
    if ( v3 )
      this[3].Ptr = (PVOID)Shared;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v6);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x18000afa0  mov     [rsp+arg_10], rbx
0x18000afa5  mov     [rsp+arg_18], rsi
0x18000afaa  push    rdi
0x18000afab  sub     rsp, 20h
0x18000afaf  cmp     qword ptr [rcx+18h], 0
0x18000afb4  mov     rdi, rcx
0x18000afb7  jnz     short loc_18000B00B
0x18000afb9  lea     rcx, [rsp+28h+arg_8]; this
0x18000afbe  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x18000afc3  cmp     qword ptr [rdi+18h], 0
0x18000afc8  jz      short loc_18000AFCE
0x18000afca  xor     esi, esi
0x18000afcc  jmp     short loc_18000AFDA
0x18000afce  lea     rcx, [rdi+8]
0x18000afd2  call    ?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)
0x18000afd7  mov     rsi, rax
0x18000afda  lea     rbx, [rdi+20h]
0x18000afde  mov     rcx, rbx; SRWLock
0x18000afe1  call    cs:__imp_AcquireSRWLockExclusive
0x18000afe7  cmp     qword ptr [rdi+18h], 0
0x18000afec  mov     [rsp+28h+arg_0], rbx
0x18000aff1  jnz     short loc_18000AFF7
0x18000aff3  mov     [rdi+18h], rsi
0x18000aff7  lea     rcx, [rsp+28h+arg_0]
0x18000affc  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000b001  lea     rcx, [rsp+28h+arg_8]; this
0x18000b006  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x18000b00b  cmp     qword ptr [rdi+18h], 0
0x18000b010  mov     rbx, [rsp+28h+arg_10]
0x18000b015  mov     rsi, [rsp+28h+arg_18]
0x18000b01a  setnz   al
0x18000b01d  add     rsp, 20h
0x18000b021  pop     rdi
0x18000b022  retn
```
