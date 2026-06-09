# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140010e28`
- end: `0x140010ec1`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x14000b79c`
- `0x14000dbf4`

## callees

- `0x1400092f0`
- `0x140010e28`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x140010e53`
- `KERNEL32!AcquireSRWLockExclusive` at `0x140010e53`

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
  _DWORD v10[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v11; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v12; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v9 = *(_DWORD *)(a1 + 28);
    v12 = v8;
    if ( !a4
      || a4 != v9
      || (v10[1] = 0, v10[0] = a3, v11 = a2, !wil::details_abi::heap_buffer::push_back((void **)(a1 + 64), v10, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x140010e28  mov     [rsp+arg_8], rbx
0x140010e2d  mov     [rsp+arg_10], rbp
0x140010e32  push    rsi
0x140010e33  push    rdi
0x140010e34  push    r14
0x140010e36  sub     rsp, 30h
0x140010e3a  mov     eax, [rcx]
0x140010e3c  mov     ebp, r9d
0x140010e3f  mov     edi, r8d
0x140010e42  mov     rsi, rdx
0x140010e45  mov     r14, rcx
0x140010e48  test    eax, eax
0x140010e4a  jz      short loc_140010EAE
0x140010e4c  lea     rbx, [rcx+8]
0x140010e50  mov     rcx, rbx; SRWLock
0x140010e53  call    cs:__imp_AcquireSRWLockExclusive
0x140010e59  mov     eax, [r14+1Ch]
0x140010e5d  mov     [rsp+48h+arg_0], rbx
0x140010e62  test    ebp, ebp
0x140010e64  jz      short loc_140010E93
0x140010e66  cmp     ebp, eax
0x140010e68  jnz     short loc_140010E93
0x140010e6a  lea     rcx, [r14+40h]; this
0x140010e6e  mov     [rsp+48h+var_24], 0
0x140010e76  mov     r8d, 10h; unsigned __int64
0x140010e7c  mov     [rsp+48h+var_28], edi
0x140010e80  lea     rdx, [rsp+48h+var_28]; void *
0x140010e85  mov     [rsp+48h+var_20], rsi
0x140010e8a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140010e8f  test    al, al
0x140010e91  jnz     short loc_140010EA4
0x140010e93  neg     edi
0x140010e95  sbb     eax, eax
0x140010e97  and     eax, 83Ah
0x140010e9c  add     eax, 0FFFFF7C1h
0x140010ea1  lock and [rsi], eax
0x140010ea4  lea     rcx, [rsp+48h+arg_0]
0x140010ea9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140010eae  mov     rbx, [rsp+48h+arg_8]
0x140010eb3  mov     rbp, [rsp+48h+arg_10]
0x140010eb8  add     rsp, 30h
0x140010ebc  pop     r14
0x140010ebe  pop     rdi
0x140010ebf  pop     rsi
0x140010ec0  retn
```
