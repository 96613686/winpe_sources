# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180036148`
- end: `0x1800361d6`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `142`
- prototype: ``
- caller_count: `14`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18002096c`
- `0x180023810`
- `0x18002e5f0`
- `0x18003af00`
- `0x18003b05c`
- `0x18003b1b8`
- `0x18003b314`
- `0x18003b470`
- `0x18003b5cc`
- `0x18003b6ac`
- `0x18003b78c`
- `0x18003b86c`
- `0x18003b94c`
- `0x18003ba2c`

## callees

- `0x180029458`
- `0x180036148`
- `0x180036b0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003616d`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18003616d`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  _DWORD v7[2]; // [rsp+20h] [rbp-38h] BYREF
  volatile signed __int32 *v8; // [rsp+28h] [rbp-30h]
  RTL_SRWLOCK *v9; // [rsp+78h] [rbp+20h] BYREF

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v9 = &SRWLock;
    if ( !a3
      || a3 != dword_180063DA4
      || (v7[1] = 0,
          v7[0] = a2,
          v8 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&unk_180063DC8, v7, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v9);
  }
  return result;
}

```

## disassembly

```asm
0x180036148  push    rbx
0x18003614a  push    rbp
0x18003614b  push    rsi
0x18003614c  push    rdi
0x18003614d  sub     rsp, 38h
0x180036151  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180036157  mov     esi, r8d
0x18003615a  mov     ebx, edx
0x18003615c  mov     rdi, rcx
0x18003615f  test    eax, eax
0x180036161  jz      short loc_1800361CD
0x180036163  lea     rbp, SRWLock
0x18003616a  mov     rcx, rbp; SRWLock
0x18003616d  call    cs:__imp_AcquireSRWLockExclusive
0x180036173  mov     eax, cs:dword_180063DA4
0x180036179  mov     [rsp+58h+arg_18], rbp
0x18003617e  test    esi, esi
0x180036180  jz      short loc_1800361B2
0x180036182  cmp     esi, eax
0x180036184  jnz     short loc_1800361B2
0x180036186  mov     r8d, 10h; unsigned __int64
0x18003618c  mov     [rsp+58h+var_34], 0
0x180036194  lea     rdx, [rsp+58h+var_38]; void *
0x180036199  mov     [rsp+58h+var_38], ebx
0x18003619d  lea     rcx, unk_180063DC8; this
0x1800361a4  mov     [rsp+58h+var_30], rdi
0x1800361a9  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800361ae  test    al, al
0x1800361b0  jnz     short loc_1800361C3
0x1800361b2  neg     ebx
0x1800361b4  sbb     eax, eax
0x1800361b6  and     eax, 83Ah
0x1800361bb  add     eax, 0FFFFF7C1h
0x1800361c0  lock and [rdi], eax
0x1800361c3  lea     rcx, [rsp+58h+arg_18]
0x1800361c8  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800361cd  add     rsp, 38h
0x1800361d1  pop     rdi
0x1800361d2  pop     rsi
0x1800361d3  pop     rbp
0x1800361d4  pop     rbx
0x1800361d5  retn
```
