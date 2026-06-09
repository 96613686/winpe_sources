# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x180010064`
- end: `0x180010104`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `160`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x18000ad74`
- `0x180016f24`

## callees

- `0x180007630`
- `0x180010064`
- `0x18001171c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001008f`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001008f`

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
          !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&a1[10], v11, 0x10u)) )
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
0x180010064  mov     [rsp+arg_8], rbx
0x180010069  mov     [rsp+arg_10], rbp
0x18001006e  push    rsi
0x18001006f  push    rdi
0x180010070  push    r14
0x180010072  sub     rsp, 30h
0x180010076  mov     eax, [rcx]
0x180010078  mov     ebp, r9d
0x18001007b  mov     edi, r8d
0x18001007e  mov     rsi, rdx
0x180010081  mov     r14, rcx
0x180010084  test    eax, eax
0x180010086  jz      short loc_1800100F0
0x180010088  lea     rbx, [rcx+8]
0x18001008c  mov     rcx, rbx; SRWLock
0x18001008f  call    cs:__imp_AcquireSRWLockExclusive
0x180010096  nop     dword ptr [rax+rax+00h]
0x18001009b  mov     eax, [r14+1Ch]
0x18001009f  mov     [rsp+48h+arg_0], rbx
0x1800100a4  test    ebp, ebp
0x1800100a6  jz      short loc_1800100D5
0x1800100a8  cmp     ebp, eax
0x1800100aa  jnz     short loc_1800100D5
0x1800100ac  lea     rcx, [r14+50h]; this
0x1800100b0  mov     [rsp+48h+var_24], 0
0x1800100b8  mov     r8d, 10h; unsigned __int64
0x1800100be  mov     [rsp+48h+var_28], edi
0x1800100c2  lea     rdx, [rsp+48h+var_28]; void *
0x1800100c7  mov     [rsp+48h+var_20], rsi
0x1800100cc  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800100d1  test    al, al
0x1800100d3  jnz     short loc_1800100E6
0x1800100d5  neg     edi
0x1800100d7  sbb     eax, eax
0x1800100d9  and     eax, 83Ah
0x1800100de  add     eax, 0FFFFF7C1h
0x1800100e3  lock and [rsi], eax
0x1800100e6  lea     rcx, [rsp+48h+arg_0]
0x1800100eb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800100f0  mov     rbx, [rsp+48h+arg_8]
0x1800100f5  mov     rbp, [rsp+48h+arg_10]
0x1800100fa  add     rsp, 30h
0x1800100fe  pop     r14
0x180010100  pop     rdi
0x180010101  pop     rsi
0x180010102  retn
```
