# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180009a60`
- end: `0x180009af9`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800076b8`
- `0x18000ed78`
- `0x180012040`
- `0x1800121a0`
- `0x180019a1c`

## callees

- `0x180005c8c`
- `0x180009a60`
- `0x18000a96c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a8b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180009a8b`

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
      || (v10[1] = 0,
          v10[0] = a3,
          v11 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v10, 0x10u)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v12);
  }
}

```

## disassembly

```asm
0x180009a60  mov     [rsp+arg_8], rbx
0x180009a65  mov     [rsp+arg_10], rbp
0x180009a6a  push    rsi
0x180009a6b  push    rdi
0x180009a6c  push    r14
0x180009a6e  sub     rsp, 30h
0x180009a72  mov     eax, [rcx]
0x180009a74  mov     ebp, r9d
0x180009a77  mov     edi, r8d
0x180009a7a  mov     rsi, rdx
0x180009a7d  mov     r14, rcx
0x180009a80  test    eax, eax
0x180009a82  jz      short loc_180009AE6
0x180009a84  lea     rbx, [rcx+8]
0x180009a88  mov     rcx, rbx; SRWLock
0x180009a8b  call    cs:__imp_AcquireSRWLockExclusive
0x180009a91  mov     eax, [r14+1Ch]
0x180009a95  mov     [rsp+48h+arg_0], rbx
0x180009a9a  test    ebp, ebp
0x180009a9c  jz      short loc_180009ACB
0x180009a9e  cmp     ebp, eax
0x180009aa0  jnz     short loc_180009ACB
0x180009aa2  lea     rcx, [r14+40h]; this
0x180009aa6  mov     [rsp+48h+var_24], 0
0x180009aae  mov     r8d, 10h; unsigned __int64
0x180009ab4  mov     [rsp+48h+var_28], edi
0x180009ab8  lea     rdx, [rsp+48h+var_28]; void *
0x180009abd  mov     [rsp+48h+var_20], rsi
0x180009ac2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180009ac7  test    al, al
0x180009ac9  jnz     short loc_180009ADC
0x180009acb  neg     edi
0x180009acd  sbb     eax, eax
0x180009acf  and     eax, 83Ah
0x180009ad4  add     eax, 0FFFFF7C1h
0x180009ad9  lock and [rsi], eax
0x180009adc  lea     rcx, [rsp+48h+arg_0]
0x180009ae1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180009ae6  mov     rbx, [rsp+48h+arg_8]
0x180009aeb  mov     rbp, [rsp+48h+arg_10]
0x180009af0  add     rsp, 30h
0x180009af4  pop     r14
0x180009af6  pop     rdi
0x180009af7  pop     rsi
0x180009af8  retn
```
