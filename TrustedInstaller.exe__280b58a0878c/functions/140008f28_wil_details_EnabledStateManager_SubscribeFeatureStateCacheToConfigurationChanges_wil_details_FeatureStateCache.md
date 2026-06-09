# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140008f28`
- end: `0x140008fb2`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `138`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1400078c4`
- `0x1400158c8`

## callees

- `0x1400066cc`
- `0x140008f28`
- `0x14000aee0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008f4c`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x140008f4c`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  int v9; // eax
  RTL_SRWLOCK *v10; // [rsp+20h] [rbp-48h] BYREF
  _DWORD v11[2]; // [rsp+28h] [rbp-40h] BYREF
  volatile signed __int32 *v12; // [rsp+30h] [rbp-38h]

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v9 = *(_DWORD *)(a1 + 28);
    v10 = v8;
    if ( !a4
      || a4 != v9
      || (v11[1] = 0,
          v11[0] = a3,
          v12 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v11, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v10);
  }
}

```

## disassembly

```asm
0x140008f28  push    rbx
0x140008f2a  push    rbp
0x140008f2b  push    rsi
0x140008f2c  push    rdi
0x140008f2d  push    r14
0x140008f2f  sub     rsp, 40h
0x140008f33  mov     eax, [rcx]
0x140008f35  mov     ebp, r9d
0x140008f38  mov     esi, r8d
0x140008f3b  mov     rdi, rdx
0x140008f3e  mov     r14, rcx
0x140008f41  test    eax, eax
0x140008f43  jz      short loc_140008FA7
0x140008f45  lea     rbx, [rcx+8]
0x140008f49  mov     rcx, rbx; SRWLock
0x140008f4c  call    cs:__imp_AcquireSRWLockExclusive
0x140008f52  mov     eax, [r14+1Ch]
0x140008f56  mov     [rsp+68h+var_48], rbx
0x140008f5b  test    ebp, ebp
0x140008f5d  jz      short loc_140008F8C
0x140008f5f  cmp     ebp, eax
0x140008f61  jnz     short loc_140008F8C
0x140008f63  lea     rcx, [r14+40h]; this
0x140008f67  mov     [rsp+68h+var_3C], 0
0x140008f6f  mov     r8d, 10h; unsigned __int64
0x140008f75  mov     [rsp+68h+var_40], esi
0x140008f79  lea     rdx, [rsp+68h+var_40]; void *
0x140008f7e  mov     [rsp+68h+var_38], rdi
0x140008f83  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140008f88  test    al, al
0x140008f8a  jnz     short loc_140008F9D
0x140008f8c  neg     esi
0x140008f8e  sbb     eax, eax
0x140008f90  and     eax, 83Ah
0x140008f95  add     eax, 0FFFFF7C1h
0x140008f9a  lock and [rdi], eax
0x140008f9d  lea     rcx, [rsp+68h+var_48]
0x140008fa2  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140008fa7  add     rsp, 40h
0x140008fab  pop     r14
0x140008fad  pop     rdi
0x140008fae  pop     rsi
0x140008faf  pop     rbp
0x140008fb0  pop     rbx
0x140008fb1  retn
```
