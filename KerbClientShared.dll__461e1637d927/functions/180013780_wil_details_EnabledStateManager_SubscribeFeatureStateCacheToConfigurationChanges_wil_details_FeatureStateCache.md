# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180013780`
- end: `0x180013819`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180011b40`

## callees

- `0x18000db40`
- `0x180013780`
- `0x18001433c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800137ab`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800137ab`

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
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[8], v11, 0x10u)) )
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
0x180013780  mov     [rsp+arg_8], rbx
0x180013785  mov     [rsp+arg_10], rbp
0x18001378a  push    rsi
0x18001378b  push    rdi
0x18001378c  push    r14
0x18001378e  sub     rsp, 30h
0x180013792  mov     eax, [rcx]
0x180013794  mov     ebp, r9d
0x180013797  mov     edi, r8d
0x18001379a  mov     rsi, rdx
0x18001379d  mov     r14, rcx
0x1800137a0  test    eax, eax
0x1800137a2  jz      short loc_180013806
0x1800137a4  lea     rbx, [rcx+8]
0x1800137a8  mov     rcx, rbx; SRWLock
0x1800137ab  call    cs:__imp_AcquireSRWLockExclusive
0x1800137b1  mov     eax, [r14+1Ch]
0x1800137b5  mov     [rsp+48h+arg_0], rbx
0x1800137ba  test    ebp, ebp
0x1800137bc  jz      short loc_1800137EB
0x1800137be  cmp     ebp, eax
0x1800137c0  jnz     short loc_1800137EB
0x1800137c2  lea     rcx, [r14+40h]; this
0x1800137c6  mov     [rsp+48h+var_24], 0
0x1800137ce  mov     r8d, 10h; unsigned __int64
0x1800137d4  mov     [rsp+48h+var_28], edi
0x1800137d8  lea     rdx, [rsp+48h+var_28]; void *
0x1800137dd  mov     [rsp+48h+var_20], rsi
0x1800137e2  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800137e7  test    al, al
0x1800137e9  jnz     short loc_1800137FC
0x1800137eb  neg     edi
0x1800137ed  sbb     eax, eax
0x1800137ef  and     eax, 83Ah
0x1800137f4  add     eax, 0FFFFF7C1h
0x1800137f9  lock and [rsi], eax
0x1800137fc  lea     rcx, [rsp+48h+arg_0]
0x180013801  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013806  mov     rbx, [rsp+48h+arg_8]
0x18001380b  mov     rbp, [rsp+48h+arg_10]
0x180013810  add     rsp, 30h
0x180013814  pop     r14
0x180013816  pop     rdi
0x180013817  pop     rsi
0x180013818  retn
```
