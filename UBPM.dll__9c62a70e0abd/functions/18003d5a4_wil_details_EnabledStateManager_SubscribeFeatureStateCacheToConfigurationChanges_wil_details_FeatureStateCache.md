# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18003d5a4`
- end: `0x18003d644`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `160`
- prototype: ``
- caller_count: `12`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180031aac`
- `0x18003a688`
- `0x18003a770`
- `0x18003a8d4`
- `0x18003aa38`
- `0x18003ab9c`
- `0x18003acf8`
- `0x18003ade0`
- `0x18003aec8`
- `0x18003afb0`
- `0x18003b098`
- `0x18003bd28`

## callees

- `0x180032040`
- `0x18003d5a4`
- `0x18003e1fc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d5cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003d5cf`

## pseudocode

```c
__int64 __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        RTL_SRWLOCK *a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  __int64 result; // rax
  unsigned int *v9; // rbx
  unsigned int Ptr_high; // eax
  _DWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v12; // [rsp+28h] [rbp-20h]
  unsigned int *v13; // [rsp+50h] [rbp+8h] BYREF

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v13 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (v11[1] = 0,
          v11[0] = a3,
          v12 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[10], v11, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
  return result;
}

```

## disassembly

```asm
0x18003d5a4  mov     [rsp+arg_8], rbx
0x18003d5a9  mov     [rsp+arg_10], rbp
0x18003d5ae  push    rsi
0x18003d5af  push    rdi
0x18003d5b0  push    r14
0x18003d5b2  sub     rsp, 30h
0x18003d5b6  mov     eax, [rcx]
0x18003d5b8  mov     ebp, r9d
0x18003d5bb  mov     edi, r8d
0x18003d5be  mov     rsi, rdx
0x18003d5c1  mov     r14, rcx
0x18003d5c4  test    eax, eax
0x18003d5c6  jz      short loc_18003D630
0x18003d5c8  lea     rbx, [rcx+8]
0x18003d5cc  mov     rcx, rbx; SRWLock
0x18003d5cf  call    cs:__imp_AcquireSRWLockExclusive
0x18003d5d6  nop     dword ptr [rax+rax+00h]
0x18003d5db  mov     eax, [r14+1Ch]
0x18003d5df  mov     [rsp+48h+arg_0], rbx
0x18003d5e4  test    ebp, ebp
0x18003d5e6  jz      short loc_18003D615
0x18003d5e8  cmp     ebp, eax
0x18003d5ea  jnz     short loc_18003D615
0x18003d5ec  lea     rcx, [r14+50h]; this
0x18003d5f0  mov     [rsp+48h+var_24], 0
0x18003d5f8  mov     r8d, 10h; unsigned __int64
0x18003d5fe  mov     [rsp+48h+var_28], edi
0x18003d602  lea     rdx, [rsp+48h+var_28]; void *
0x18003d607  mov     [rsp+48h+var_20], rsi
0x18003d60c  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18003d611  test    al, al
0x18003d613  jnz     short loc_18003D626
0x18003d615  neg     edi
0x18003d617  sbb     eax, eax
0x18003d619  and     eax, 83Ah
0x18003d61e  add     eax, 0FFFFF7C1h
0x18003d623  lock and [rsi], eax
0x18003d626  lea     rcx, [rsp+48h+arg_0]
0x18003d62b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18003d630  mov     rbx, [rsp+48h+arg_8]
0x18003d635  mov     rbp, [rsp+48h+arg_10]
0x18003d63a  add     rsp, 30h
0x18003d63e  pop     r14
0x18003d640  pop     rdi
0x18003d641  pop     rsi
0x18003d642  retn
```
