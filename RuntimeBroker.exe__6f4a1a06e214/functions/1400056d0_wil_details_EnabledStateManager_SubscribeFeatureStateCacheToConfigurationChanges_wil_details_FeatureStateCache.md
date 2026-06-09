# wil::details::EnabledStateManager::SubscribeFeatureStateCacheToConfigurationChanges(wil_details_FeatureStateCache *,wil_FeatureChangeTime,uint)

- ea: `0x1400056d0`
- end: `0x140005769`
- name: `?SubscribeFeatureStateCacheToConfigurationChanges@EnabledStateManager@details@wil@@QEAAXPEATwil_details_FeatureStateCache@@W4wil_FeatureChangeTime@@I@Z`
- size: `153`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x140005350`
- `0x14000548c`

## callees

- `0x140003e30`
- `0x1400056d0`
- `0x1400085c4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400056fb`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1400056fb`

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
0x1400056d0  mov     [rsp+arg_8], rbx
0x1400056d5  mov     [rsp+arg_10], rbp
0x1400056da  push    rsi
0x1400056db  push    rdi
0x1400056dc  push    r14
0x1400056de  sub     rsp, 30h
0x1400056e2  mov     eax, [rcx]
0x1400056e4  mov     ebp, r9d
0x1400056e7  mov     edi, r8d
0x1400056ea  mov     rsi, rdx
0x1400056ed  mov     r14, rcx
0x1400056f0  test    eax, eax
0x1400056f2  jz      short loc_140005756
0x1400056f4  lea     rbx, [rcx+8]
0x1400056f8  mov     rcx, rbx; SRWLock
0x1400056fb  call    cs:__imp_AcquireSRWLockExclusive
0x140005701  mov     eax, [r14+1Ch]
0x140005705  mov     [rsp+48h+arg_0], rbx
0x14000570a  test    ebp, ebp
0x14000570c  jz      short loc_14000573B
0x14000570e  cmp     ebp, eax
0x140005710  jnz     short loc_14000573B
0x140005712  lea     rcx, [r14+40h]; this
0x140005716  mov     [rsp+48h+var_24], 0
0x14000571e  mov     r8d, 10h; unsigned __int64
0x140005724  mov     [rsp+48h+var_28], edi
0x140005728  lea     rdx, [rsp+48h+var_28]; void *
0x14000572d  mov     [rsp+48h+var_20], rsi
0x140005732  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x140005737  test    al, al
0x140005739  jnz     short loc_14000574C
0x14000573b  neg     edi
0x14000573d  sbb     eax, eax
0x14000573f  and     eax, 83Ah
0x140005744  add     eax, 0FFFFF7C1h
0x140005749  lock and [rsi], eax
0x14000574c  lea     rcx, [rsp+48h+arg_0]
0x140005751  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x140005756  mov     rbx, [rsp+48h+arg_8]
0x14000575b  mov     rbp, [rsp+48h+arg_10]
0x140005760  add     rsp, 30h
0x140005764  pop     r14
0x140005766  pop     rdi
0x140005767  pop     rsi
0x140005768  retn
```
