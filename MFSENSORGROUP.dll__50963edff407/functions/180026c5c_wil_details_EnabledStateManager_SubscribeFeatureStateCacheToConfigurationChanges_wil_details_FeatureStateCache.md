# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180026c5c`
- end: `0x180026cef`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `147`
- prototype: ``
- caller_count: `11`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1800263f0`
- `0x180026a1c`
- `0x18003d0a0`
- `0x18003de9c`
- `0x180051f4c`
- `0x1800522ac`
- `0x18005260c`
- `0x180052774`
- `0x180052c90`
- `0x180052eb4`
- `0x18005fa28`

## callees

- `0x180026c5c`
- `0x1800282b4`
- `0x180031a18`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026c87`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180026c87`

## pseudocode

```c
void __fastcall wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(
        __int64 a1,
        volatile signed __int32 *a2,
        int a3,
        int a4)
{
  RTL_SRWLOCK *v8; // rbx
  unsigned __int64 v9; // r8
  int v10; // eax
  _DWORD v11[2]; // [rsp+20h] [rbp-28h] BYREF
  volatile signed __int32 *v12; // [rsp+28h] [rbp-20h]
  RTL_SRWLOCK *v13; // [rsp+50h] [rbp+8h] BYREF

  if ( *(_DWORD *)a1 )
  {
    v8 = (RTL_SRWLOCK *)(a1 + 8);
    AcquireSRWLockExclusive((PSRWLOCK)(a1 + 8));
    v10 = *(_DWORD *)(a1 + 28);
    v13 = v8;
    if ( !a4
      || a4 != v10
      || (v11[1] = 0,
          v11[0] = a3,
          v12 = a2,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)(a1 + 64), v11, v9)) )
    {
      _InterlockedAnd(a2, a3 != 0 ? -5 : -2111);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v13);
  }
}

```

## disassembly

```asm
0x180026c5c  mov     [rsp+arg_8], rbx
0x180026c61  mov     [rsp+arg_10], rbp
0x180026c66  push    rsi
0x180026c67  push    rdi
0x180026c68  push    r14
0x180026c6a  sub     rsp, 30h
0x180026c6e  mov     eax, [rcx]
0x180026c70  mov     ebp, r9d
0x180026c73  mov     edi, r8d
0x180026c76  mov     rsi, rdx
0x180026c79  mov     r14, rcx
0x180026c7c  test    eax, eax
0x180026c7e  jz      short loc_180026CDC
0x180026c80  lea     rbx, [rcx+8]
0x180026c84  mov     rcx, rbx; SRWLock
0x180026c87  call    cs:__imp_AcquireSRWLockExclusive
0x180026c8d  mov     eax, [r14+1Ch]
0x180026c91  mov     [rsp+48h+arg_0], rbx
0x180026c96  test    ebp, ebp
0x180026c98  jz      short loc_180026CC1
0x180026c9a  cmp     ebp, eax
0x180026c9c  jnz     short loc_180026CC1
0x180026c9e  lea     rcx, [r14+40h]; this
0x180026ca2  mov     [rsp+48h+var_24], 0
0x180026caa  lea     rdx, [rsp+48h+var_28]; void *
0x180026caf  mov     [rsp+48h+var_28], edi
0x180026cb3  mov     [rsp+48h+var_20], rsi
0x180026cb8  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180026cbd  test    al, al
0x180026cbf  jnz     short loc_180026CD2
0x180026cc1  neg     edi
0x180026cc3  sbb     eax, eax
0x180026cc5  and     eax, 83Ah
0x180026cca  add     eax, 0FFFFF7C1h
0x180026ccf  lock and [rsi], eax
0x180026cd2  lea     rcx, [rsp+48h+arg_0]
0x180026cd7  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180026cdc  mov     rbx, [rsp+48h+arg_8]
0x180026ce1  mov     rbp, [rsp+48h+arg_10]
0x180026ce6  add     rsp, 30h
0x180026cea  pop     r14
0x180026cec  pop     rdi
0x180026ced  pop     rsi
0x180026cee  retn
```
