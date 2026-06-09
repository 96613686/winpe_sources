# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1800090a4`
- end: `0x18000913d`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: `void __fastcall(__int64, volatile signed __int32 *, int, int)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000697c`

## callees

- `0x180004e64`
- `0x1800090a4`
- `0x180009f20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090cf`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800090cf`

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
0x1800090a4  mov     [rsp+arg_8], rbx
0x1800090a9  mov     [rsp+arg_10], rbp
0x1800090ae  push    rsi
0x1800090af  push    rdi
0x1800090b0  push    r14
0x1800090b2  sub     rsp, 30h
0x1800090b6  mov     eax, [rcx]
0x1800090b8  mov     ebp, r9d
0x1800090bb  mov     edi, r8d
0x1800090be  mov     rsi, rdx
0x1800090c1  mov     r14, rcx
0x1800090c4  test    eax, eax
0x1800090c6  jz      short loc_18000912A
0x1800090c8  lea     rbx, [rcx+8]
0x1800090cc  mov     rcx, rbx; SRWLock
0x1800090cf  call    cs:__imp_AcquireSRWLockExclusive
0x1800090d5  mov     eax, [r14+1Ch]
0x1800090d9  mov     [rsp+48h+arg_0], rbx
0x1800090de  test    ebp, ebp
0x1800090e0  jz      short loc_18000910F
0x1800090e2  cmp     ebp, eax
0x1800090e4  jnz     short loc_18000910F
0x1800090e6  lea     rcx, [r14+40h]; this
0x1800090ea  mov     [rsp+48h+var_24], 0
0x1800090f2  mov     r8d, 10h; unsigned __int64
0x1800090f8  mov     [rsp+48h+var_28], edi
0x1800090fc  lea     rdx, [rsp+48h+var_28]; void *
0x180009101  mov     [rsp+48h+var_20], rsi
0x180009106  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000910b  test    al, al
0x18000910d  jnz     short loc_180009120
0x18000910f  neg     edi
0x180009111  sbb     eax, eax
0x180009113  and     eax, 83Ah
0x180009118  add     eax, 0FFFFF7C1h
0x18000911d  lock and [rsi], eax
0x180009120  lea     rcx, [rsp+48h+arg_0]
0x180009125  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000912a  mov     rbx, [rsp+48h+arg_8]
0x18000912f  mov     rbp, [rsp+48h+arg_10]
0x180009134  add     rsp, 30h
0x180009138  pop     r14
0x18000913a  pop     rdi
0x18000913b  pop     rsi
0x18000913c  retn
```
