# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x140008798`
- end: `0x140008831`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140006100`

## callees

- `0x140004604`
- `0x140008798`
- `0x14000949c`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x1400087c3`
- `KERNEL32!AcquireSRWLockExclusive` at `0x1400087c3`

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
0x140008798  mov     [rsp+arg_8], rbx
0x14000879d  mov     [rsp+arg_10], rbp
0x1400087a2  push    rsi
0x1400087a3  push    rdi
0x1400087a4  push    r14
0x1400087a6  sub     rsp, 30h
0x1400087aa  mov     eax, [rcx]
0x1400087ac  mov     ebp, r9d
0x1400087af  mov     edi, r8d
0x1400087b2  mov     rsi, rdx
0x1400087b5  mov     r14, rcx
0x1400087b8  test    eax, eax
0x1400087ba  jz      short loc_14000881E
0x1400087bc  lea     rbx, [rcx+8]
0x1400087c0  mov     rcx, rbx; SRWLock
0x1400087c3  call    cs:__imp_AcquireSRWLockExclusive
0x1400087c9  mov     eax, [r14+1Ch]
0x1400087cd  mov     [rsp+48h+arg_0], rbx
0x1400087d2  test    ebp, ebp
0x1400087d4  jz      short loc_140008803
0x1400087d6  cmp     ebp, eax
0x1400087d8  jnz     short loc_140008803
0x1400087da  lea     rcx, [r14+40h]; this
0x1400087de  mov     [rsp+48h+var_24], 0
0x1400087e6  mov     r8d, 10h; unsigned __int64
0x1400087ec  mov     [rsp+48h+var_28], edi
0x1400087f0  lea     rdx, [rsp+48h+var_28]; void *
0x1400087f5  mov     [rsp+48h+var_20], rsi
0x1400087fa  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1400087ff  test    al, al
0x140008801  jnz     short loc_140008814
0x140008803  neg     edi
0x140008805  sbb     eax, eax
0x140008807  and     eax, 83Ah
0x14000880c  add     eax, 0FFFFF7C1h
0x140008811  lock and [rsi], eax
0x140008814  lea     rcx, [rsp+48h+arg_0]
0x140008819  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000881e  mov     rbx, [rsp+48h+arg_8]
0x140008823  mov     rbp, [rsp+48h+arg_10]
0x140008828  add     rsp, 30h
0x14000882c  pop     r14
0x14000882e  pop     rdi
0x14000882f  pop     rsi
0x140008830  retn
```
