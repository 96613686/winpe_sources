# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140005818`
- end: `0x14000589b`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `131`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140005e84`
- `0x140007744`
- `0x140008b88`

## callees

- `0x140004d20`
- `0x140004ec8`
- `0x1400050ac`
- `0x140005818`
- `0x140006510`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005859`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140005859`

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
0x140005818  mov     [rsp+arg_10], rbx
0x14000581d  mov     [rsp+arg_18], rsi
0x140005822  push    rdi
0x140005823  sub     rsp, 20h
0x140005827  cmp     qword ptr [rcx+18h], 0
0x14000582c  mov     rdi, rcx
0x14000582f  jnz     short loc_140005883
0x140005831  lea     rcx, [rsp+28h+arg_8]; this
0x140005836  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x14000583b  cmp     qword ptr [rdi+18h], 0
0x140005840  jz      short loc_140005846
0x140005842  xor     esi, esi
0x140005844  jmp     short loc_140005852
0x140005846  lea     rcx, [rdi+8]
0x14000584a  call    ?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)
0x14000584f  mov     rsi, rax
0x140005852  lea     rbx, [rdi+20h]
0x140005856  mov     rcx, rbx; SRWLock
0x140005859  call    cs:__imp_AcquireSRWLockExclusive
0x14000585f  cmp     qword ptr [rdi+18h], 0
0x140005864  mov     [rsp+28h+arg_0], rbx
0x140005869  jnz     short loc_14000586F
0x14000586b  mov     [rdi+18h], rsi
0x14000586f  lea     rcx, [rsp+28h+arg_0]
0x140005874  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140005879  lea     rcx, [rsp+28h+arg_8]; this
0x14000587e  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140005883  cmp     qword ptr [rdi+18h], 0
0x140005888  mov     rbx, [rsp+28h+arg_10]
0x14000588d  mov     rsi, [rsp+28h+arg_18]
0x140005892  setnz   al
0x140005895  add     rsp, 20h
0x140005899  pop     rdi
0x14000589a  retn
```
