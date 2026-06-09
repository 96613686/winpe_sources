# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000d3b8`
- end: `0x18000d44b`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `147`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800148a8`
- `0x180014a0c`

## callees

- `0x18000b850`
- `0x18000d3b8`
- `0x18000d968`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d3e3`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000d3e3`

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
  unsigned __int64 v10; // r8
  unsigned int Ptr_high; // eax
  _DWORD Source[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v13; // [rsp+28h] [rbp-20h]
  unsigned int *v14; // [rsp+50h] [rbp+8h] BYREF

  result = LODWORD(a1->Ptr);
  if ( (_DWORD)result )
  {
    v9 = (unsigned int *)&a1[1];
    AcquireSRWLockExclusive(a1 + 1);
    Ptr_high = HIDWORD(a1[3].Ptr);
    v14 = v9;
    if ( !a4
      || a4 != Ptr_high
      || (Source[1] = 0,
          Source[0] = a3,
          v13 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], Source, v10)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v14);
  }
  return result;
}

```

## disassembly

```asm
0x18000d3b8  mov     [rsp+arg_8], rbx
0x18000d3bd  mov     [rsp+arg_10], rbp
0x18000d3c2  push    rsi
0x18000d3c3  push    rdi
0x18000d3c4  push    r14
0x18000d3c6  sub     rsp, 30h
0x18000d3ca  mov     eax, [rcx]
0x18000d3cc  mov     ebp, r9d
0x18000d3cf  mov     edi, r8d
0x18000d3d2  mov     rsi, rdx
0x18000d3d5  mov     r14, rcx
0x18000d3d8  test    eax, eax
0x18000d3da  jz      short loc_18000D438
0x18000d3dc  lea     rbx, [rcx+8]
0x18000d3e0  mov     rcx, rbx; SRWLock
0x18000d3e3  call    cs:__imp_AcquireSRWLockExclusive
0x18000d3e9  mov     eax, [r14+1Ch]
0x18000d3ed  mov     [rsp+48h+arg_0], rbx
0x18000d3f2  test    ebp, ebp
0x18000d3f4  jz      short loc_18000D41D
0x18000d3f6  cmp     ebp, eax
0x18000d3f8  jnz     short loc_18000D41D
0x18000d3fa  lea     rcx, [r14+40h]; this
0x18000d3fe  mov     [rsp+48h+var_24], 0
0x18000d406  lea     rdx, [rsp+48h+Source]; Source
0x18000d40b  mov     [rsp+48h+Source], edi
0x18000d40f  mov     [rsp+48h+var_20], rsi
0x18000d414  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000d419  test    al, al
0x18000d41b  jnz     short loc_18000D42E
0x18000d41d  neg     edi
0x18000d41f  sbb     eax, eax
0x18000d421  and     eax, 83Ah
0x18000d426  add     eax, 0FFFFF7C1h
0x18000d42b  lock and [rsi], eax
0x18000d42e  lea     rcx, [rsp+48h+arg_0]
0x18000d433  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000d438  mov     rbx, [rsp+48h+arg_8]
0x18000d43d  mov     rbp, [rsp+48h+arg_10]
0x18000d442  add     rsp, 30h
0x18000d446  pop     r14
0x18000d448  pop     rdi
0x18000d449  pop     rsi
0x18000d44a  retn
```
