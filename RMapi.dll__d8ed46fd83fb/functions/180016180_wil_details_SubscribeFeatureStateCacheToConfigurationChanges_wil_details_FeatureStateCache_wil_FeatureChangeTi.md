# wil::details::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180016180`
- end: `0x180016215`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@details@wil@@YAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `149`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18001244c`
- `0x180012540`
- `0x180012634`
- `0x180012728`
- `0x18001281c`
- `0x180012910`
- `0x180012a04`
- `0x180012af8`
- `0x18001379c`
- `0x18001e994`
- `0x1800241d0`
- `0x1800242c8`
- `0x1800243bc`

## callees

- `0x180011904`
- `0x180016180`
- `0x180016c0c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800161a8`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800161a8`

## pseudocode

```c
__int64 __fastcall wil::details::SubscribeFeatureStateCacheToConfigurationChanges(
        volatile signed __int32 *a1,
        int a2,
        int a3)
{
  __int64 result; // rax
  RTL_SRWLOCK *v7; // [rsp+20h] [rbp-38h] BYREF
  _DWORD v8[2]; // [rsp+28h] [rbp-30h] BYREF
  volatile signed __int32 *v9; // [rsp+30h] [rbp-28h]

  result = wil::details::g_enabledStateManager;
  if ( wil::details::g_enabledStateManager )
  {
    AcquireSRWLockExclusive(&SRWLock);
    v7 = &SRWLock;
    if ( !a3
      || a3 != dword_180037A14
      || (v8[1] = 0,
          v8[0] = a2,
          v9 = a1,
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180037A38, v8, 0x10u)) )
    {
      _InterlockedAnd(a1, a2 != 0 ? -5 : -2111);
    }
    return wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  }
  return result;
}

```

## disassembly

```asm
0x180016180  mov     [rsp+arg_10], rbx
0x180016185  push    rbp
0x180016186  push    rsi
0x180016187  push    rdi
0x180016188  sub     rsp, 40h
0x18001618c  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016192  mov     esi, r8d
0x180016195  mov     edi, edx
0x180016197  mov     rbx, rcx
0x18001619a  test    eax, eax
0x18001619c  jz      short loc_180016208
0x18001619e  lea     rbp, SRWLock
0x1800161a5  mov     rcx, rbp; SRWLock
0x1800161a8  call    cs:__imp_AcquireSRWLockExclusive
0x1800161ae  mov     eax, cs:dword_180037A14
0x1800161b4  mov     [rsp+58h+var_38], rbp
0x1800161b9  test    esi, esi
0x1800161bb  jz      short loc_1800161ED
0x1800161bd  cmp     esi, eax
0x1800161bf  jnz     short loc_1800161ED
0x1800161c1  mov     r8d, 10h; unsigned __int64
0x1800161c7  mov     [rsp+58h+var_2C], 0
0x1800161cf  lea     rdx, [rsp+58h+var_30]; void *
0x1800161d4  mov     [rsp+58h+var_30], edi
0x1800161d8  lea     rcx, qword_180037A38; this
0x1800161df  mov     [rsp+58h+var_28], rbx
0x1800161e4  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800161e9  test    al, al
0x1800161eb  jnz     short loc_1800161FE
0x1800161ed  neg     edi
0x1800161ef  sbb     eax, eax
0x1800161f1  and     eax, 83Ah
0x1800161f6  add     eax, 0FFFFF7C1h
0x1800161fb  lock and [rbx], eax
0x1800161fe  lea     rcx, [rsp+58h+var_38]
0x180016203  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016208  mov     rbx, [rsp+58h+arg_10]
0x18001620d  add     rsp, 40h
0x180016211  pop     rdi
0x180016212  pop     rsi
0x180016213  pop     rbp
0x180016214  retn
```
