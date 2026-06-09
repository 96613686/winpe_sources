# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x140003998`
- end: `0x140003a1b`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `131`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140003c24`
- `0x14000572c`
- `0x1400068b4`

## callees

- `0x140002d14`
- `0x140002fd4`
- `0x1400032a8`
- `0x140003998`
- `0x140004384`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400039d9`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400039d9`

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
0x140003998  mov     [rsp+arg_10], rbx
0x14000399d  mov     [rsp+arg_18], rsi
0x1400039a2  push    rdi
0x1400039a3  sub     rsp, 20h
0x1400039a7  cmp     qword ptr [rcx+18h], 0
0x1400039ac  mov     rdi, rcx
0x1400039af  jnz     short loc_140003A03
0x1400039b1  lea     rcx, [rsp+28h+arg_8]; this
0x1400039b6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400039bb  cmp     qword ptr [rdi+18h], 0
0x1400039c0  jz      short loc_1400039C6
0x1400039c2  xor     esi, esi
0x1400039c4  jmp     short loc_1400039D2
0x1400039c6  lea     rcx, [rdi+8]
0x1400039ca  call    ?GetShared@?$ProcessLocalStorage@VFeatureStateData@details_abi@wil@@@details_abi@wil@@QEAAPEAVFeatureStateData@23@XZ; wil::details_abi::ProcessLocalStorage<wil::details_abi::FeatureStateData>::GetShared(void)
0x1400039cf  mov     rsi, rax
0x1400039d2  lea     rbx, [rdi+20h]
0x1400039d6  mov     rcx, rbx; SRWLock
0x1400039d9  call    cs:__imp_AcquireSRWLockExclusive
0x1400039df  cmp     qword ptr [rdi+18h], 0
0x1400039e4  mov     [rsp+28h+arg_0], rbx
0x1400039e9  jnz     short loc_1400039EF
0x1400039eb  mov     [rdi+18h], rsi
0x1400039ef  lea     rcx, [rsp+28h+arg_0]
0x1400039f4  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1400039f9  lea     rcx, [rsp+28h+arg_8]; this
0x1400039fe  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x140003a03  cmp     qword ptr [rdi+18h], 0
0x140003a08  mov     rbx, [rsp+28h+arg_10]
0x140003a0d  mov     rsi, [rsp+28h+arg_18]
0x140003a12  setnz   al
0x140003a15  add     rsp, 20h
0x140003a19  pop     rdi
0x140003a1a  retn
```
