# wil::details::FeatureStateManager::EnsureStateData(void)

- ea: `0x1400043a4`
- end: `0x140004462`
- name: `?EnsureStateData@FeatureStateManager@details@wil@@AEAA_NXZ`
- size: `190`
- prototype: `bool __fastcall(wil::details::FeatureStateManager *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140001b18`
- `0x1400045f4`
- `0x140006778`

## callees

- `0x140001be0`
- `0x140001c44`
- `0x140001c64`
- `0x14000404c`
- `0x1400043a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004420`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140004420`

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
0x1400043a4  mov     [rsp+arg_10], rbx
0x1400043a9  mov     [rsp+arg_18], rsi
0x1400043ae  push    rdi
0x1400043af  sub     rsp, 20h
0x1400043b3  cmp     qword ptr [rcx+18h], 0
0x1400043b8  mov     rdi, rcx
0x1400043bb  jnz     loc_14000444A
0x1400043c1  lea     rcx, [rsp+28h+arg_8]; this
0x1400043c6  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1400043cb  cmp     qword ptr [rdi+18h], 0
0x1400043d0  jz      short loc_1400043D6
0x1400043d2  xor     esi, esi
0x1400043d4  jmp     short loc_140004419
0x1400043d6  cmp     qword ptr [rdi+10h], 0
0x1400043db  jnz     short loc_140004408
0x1400043dd  mov     rcx, [rdi+8]
0x1400043e1  lea     rdx, [rsp+28h+arg_0]
0x1400043e6  mov     [rsp+28h+arg_0], 0
0x1400043ef  call    ?Acquire@?$ProcessLocalStorageData@VFeatureStateData@details_abi@wil@@@details_abi@wil@@SAJPEBDPEAPEAV123@@Z; wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData>::Acquire(char const *,wil::details_abi::ProcessLocalStorageData<wil::details_abi::FeatureStateData> * *)
0x1400043f4  test    eax, eax
0x1400043f6  js      short loc_140004408
0x1400043f8  cmp     qword ptr [rdi+10h], 0
0x1400043fd  jnz     short loc_140004408
0x1400043ff  mov     rax, [rsp+28h+arg_0]
0x140004404  mov     [rdi+10h], rax
0x140004408  mov     rax, [rdi+10h]
0x14000440c  lea     rcx, [rax+20h]
0x140004410  neg     rax
0x140004413  sbb     rsi, rsi
0x140004416  and     rsi, rcx
0x140004419  lea     rbx, [rdi+20h]
0x14000441d  mov     rcx, rbx; SRWLock
0x140004420  call    cs:__imp_AcquireSRWLockExclusive
0x140004426  cmp     qword ptr [rdi+18h], 0
0x14000442b  mov     [rsp+28h+arg_0], rbx
0x140004430  jnz     short loc_140004436
0x140004432  mov     [rdi+18h], rsi
0x140004436  lea     rcx, [rsp+28h+arg_0]
0x14000443b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140004440  lea     rcx, [rsp+28h+arg_8]; this
0x140004445  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x14000444a  cmp     qword ptr [rdi+18h], 0
0x14000444f  mov     rbx, [rsp+28h+arg_10]
0x140004454  mov     rsi, [rsp+28h+arg_18]
0x140004459  setnz   al
0x14000445c  add     rsp, 20h
0x140004460  pop     rdi
0x140004461  retn
```
