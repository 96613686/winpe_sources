# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1800048d0`
- end: `0x18000498e`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `190`
- prototype: `bool __fastcall(RTL_SRWLOCK *this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180004b20`
- `0x1800068ac`
- `0x180007f44`

## callees

- `0x180003364`
- `0x180003698`
- `0x180003a38`
- `0x180003e80`
- `0x1800048d0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000494c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000494c`

## pseudocode

```c
bool __fastcall wil::details::FeatureStateManager::EnsureStateData(RTL_SRWLOCK *this)
{
  __int64 v2; // rsi
  __int64 Ptr; // rcx
  bool v4; // zf
  RTL_SRWLOCK *v6; // [rsp+30h] [rbp+8h] BYREF
  char v7; // [rsp+38h] [rbp+10h] BYREF

  if ( !this[3].Ptr )
  {
    wil::last_error_context::last_error_context((wil::last_error_context *)&v7);
    if ( this[3].Ptr )
    {
      v2 = 0;
    }
    else
    {
      if ( !this[2].Ptr )
      {
        Ptr = (__int64)this[1].Ptr;
        v6 = 0;
        if ( (int)wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(
                    Ptr,
                    (void **)&v6) >= 0
          && !this[2].Ptr )
        {
          this[2].Ptr = v6;
        }
      }
      v2 = ((__int64)this[2].Ptr + 32) & -(__int64)(this[2].Ptr != 0);
    }
    AcquireSRWLockExclusive(this + 4);
    v4 = this[3].Ptr == 0;
    v6 = this + 4;
    if ( v4 )
      this[3].Ptr = (PVOID)v2;
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v6);
    wil::last_error_context::~last_error_context((wil::last_error_context *)&v7);
  }
  return this[3].Ptr != 0;
}

```

## disassembly

```asm
0x1800048d0  mov     [rsp+arg_10], rbx
0x1800048d5  mov     [rsp+arg_18], rsi
0x1800048da  push    rdi
0x1800048db  sub     rsp, 20h
0x1800048df  cmp     qword ptr [rcx+18h], 0
0x1800048e4  mov     rdi, rcx
0x1800048e7  jnz     loc_180004976
0x1800048ed  lea     rcx, [rsp+28h+arg_8]; this
0x1800048f2  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1800048f7  cmp     qword ptr [rdi+18h], 0
0x1800048fc  jz      short loc_180004902
0x1800048fe  xor     esi, esi
0x180004900  jmp     short loc_180004945
0x180004902  cmp     qword ptr [rdi+10h], 0
0x180004907  jnz     short loc_180004934
0x180004909  mov     rcx, [rdi+8]
0x18000490d  lea     rdx, [rsp+28h+arg_0]
0x180004912  mov     [rsp+28h+arg_0], 0
0x18000491b  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x180004920  test    eax, eax
0x180004922  js      short loc_180004934
0x180004924  cmp     qword ptr [rdi+10h], 0
0x180004929  jnz     short loc_180004934
0x18000492b  mov     rax, [rsp+28h+arg_0]
0x180004930  mov     [rdi+10h], rax
0x180004934  mov     rax, [rdi+10h]
0x180004938  lea     rcx, [rax+20h]
0x18000493c  neg     rax
0x18000493f  sbb     rsi, rsi
0x180004942  and     rsi, rcx
0x180004945  lea     rbx, [rdi+20h]
0x180004949  mov     rcx, rbx; SRWLock
0x18000494c  call    cs:__imp_AcquireSRWLockExclusive
0x180004952  cmp     qword ptr [rdi+18h], 0
0x180004957  mov     [rsp+28h+arg_0], rbx
0x18000495c  jnz     short loc_180004962
0x18000495e  mov     [rdi+18h], rsi
0x180004962  lea     rcx, [rsp+28h+arg_0]
0x180004967  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000496c  lea     rcx, [rsp+28h+arg_8]; this
0x180004971  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180004976  cmp     qword ptr [rdi+18h], 0
0x18000497b  mov     rbx, [rsp+28h+arg_10]
0x180004980  mov     rsi, [rsp+28h+arg_18]
0x180004985  setnz   al
0x180004988  add     rsp, 20h
0x18000498c  pop     rdi
0x18000498d  retn
```
