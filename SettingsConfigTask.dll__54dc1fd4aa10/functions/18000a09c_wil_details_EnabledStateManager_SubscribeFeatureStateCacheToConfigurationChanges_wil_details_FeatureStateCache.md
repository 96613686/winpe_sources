# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x18000a09c`
- end: `0x18000a135`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `13`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006070`
- `0x180006158`
- `0x180006240`
- `0x18000711c`
- `0x180014240`
- `0x18001446c`
- `0x180014554`
- `0x18001463c`
- `0x180014724`
- `0x18001480c`
- `0x1800148f4`
- `0x1800149dc`
- `0x180015248`

## callees

- `0x18000460c`
- `0x18000a09c`
- `0x18000b230`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a0c7`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18000a0c7`

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
0x18000a09c  mov     [rsp+arg_8], rbx
0x18000a0a1  mov     [rsp+arg_10], rbp
0x18000a0a6  push    rsi
0x18000a0a7  push    rdi
0x18000a0a8  push    r14
0x18000a0aa  sub     rsp, 30h
0x18000a0ae  mov     eax, [rcx]
0x18000a0b0  mov     ebp, r9d
0x18000a0b3  mov     edi, r8d
0x18000a0b6  mov     rsi, rdx
0x18000a0b9  mov     r14, rcx
0x18000a0bc  test    eax, eax
0x18000a0be  jz      short loc_18000A122
0x18000a0c0  lea     rbx, [rcx+8]
0x18000a0c4  mov     rcx, rbx; SRWLock
0x18000a0c7  call    cs:__imp_AcquireSRWLockExclusive
0x18000a0cd  mov     eax, [r14+1Ch]
0x18000a0d1  mov     [rsp+48h+arg_0], rbx
0x18000a0d6  test    ebp, ebp
0x18000a0d8  jz      short loc_18000A107
0x18000a0da  cmp     ebp, eax
0x18000a0dc  jnz     short loc_18000A107
0x18000a0de  lea     rcx, [r14+40h]; this
0x18000a0e2  mov     [rsp+48h+var_24], 0
0x18000a0ea  mov     r8d, 10h; unsigned __int64
0x18000a0f0  mov     [rsp+48h+var_28], edi
0x18000a0f4  lea     rdx, [rsp+48h+var_28]; void *
0x18000a0f9  mov     [rsp+48h+var_20], rsi
0x18000a0fe  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18000a103  test    al, al
0x18000a105  jnz     short loc_18000A118
0x18000a107  neg     edi
0x18000a109  sbb     eax, eax
0x18000a10b  and     eax, 83Ah
0x18000a110  add     eax, 0FFFFF7C1h
0x18000a115  lock and [rsi], eax
0x18000a118  lea     rcx, [rsp+48h+arg_0]
0x18000a11d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18000a122  mov     rbx, [rsp+48h+arg_8]
0x18000a127  mov     rbp, [rsp+48h+arg_10]
0x18000a12c  add     rsp, 30h
0x18000a130  pop     r14
0x18000a132  pop     rdi
0x18000a133  pop     rsi
0x18000a134  retn
```
