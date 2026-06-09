# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCachedVariantState(void)

- ea: `0x180019b04`
- end: `0x180019c66`
- name: `?GetCachedVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_64kEtwBufferSize@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `354`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ae38`
- `0x18001c54c`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x180019b04`
- `0x180019e50`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019c05`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180019c05`

## pseudocode

```c
__int64 *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCachedVariantState(
        wil::details *a1,
        signed __int64 *a2)
{
  __int64 v3; // rax
  unsigned int v4; // esi
  __int64 v5; // rcx
  __int64 v6; // r9
  int v7; // ecx
  signed __int64 v8; // rax
  int v9; // r11d
  signed __int64 v10; // r10
  int v11; // r8d
  bool v12; // zf
  _QWORD v14[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+20h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+28h] BYREF

  v15 = a1;
  v3 = *Feature_GPM_64kEtwBufferSize__descriptor;
  *a2 = *Feature_GPM_64kEtwBufferSize__descriptor;
  if ( (v3 & 0xC) != 0xC )
  {
    LODWORD(v15) = 0;
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCurrentVariantState(v5, &v16, &v15);
    v6 = *a2;
    v7 = (int)v16;
    v8 = *a2;
    v9 = HIDWORD(v16);
    v10 = *a2;
    while ( 1 )
    {
      *(_DWORD *)a2 = v6;
      *((_DWORD *)a2 + 1) = HIDWORD(v8);
      if ( (v6 & 8) != 0 )
      {
        v11 = v6;
      }
      else
      {
        *((_DWORD *)a2 + 1) = v9;
        v11 = v7 & 0x800 | ((_DWORD)v15 != 0 ? 8 : 0) | v6 & 0xFFFC07F7 | v7 & 0x3F000;
        *(_DWORD *)a2 = v11;
      }
      if ( (v6 & 4) == 0 )
        *(_DWORD *)a2 = v7 & 0x400 | v11 & 0xFFFFFBFF | 4;
      v8 = _InterlockedCompareExchange64(Feature_GPM_64kEtwBufferSize__descriptor, *a2, v10);
      v12 = v10 == v8;
      v10 = v8;
      if ( v12 )
        break;
      LODWORD(v6) = v8;
    }
    if ( (v6 & 4) == 0 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v4
        || v4 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_64kEtwBufferSize__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_64kEtwBufferSize__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
  }
  return a2;
}

```

## disassembly

```asm
0x180019b04  mov     [rsp-18h+arg_10], rbx
0x180019b09  mov     [rsp-18h+arg_18], rsi
0x180019b0e  mov     [rsp-18h+arg_0], rcx
0x180019b13  push    rbp
0x180019b14  push    rdi
0x180019b15  push    r14
0x180019b17  mov     rbp, rsp
0x180019b1a  sub     rsp, 30h
0x180019b1e  mov     rdi, cs:Feature_GPM_64kEtwBufferSize__descriptor
0x180019b25  mov     rbx, rdx
0x180019b28  mov     rax, [rdi]
0x180019b2b  mov     [rdx], rax
0x180019b2e  and     eax, 0Ch
0x180019b31  cmp     al, 0Ch
0x180019b33  jz      loc_180019C50
0x180019b39  mov     dword ptr [rbp+arg_0], 0
0x180019b40  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180019b45  lea     r8, [rbp+arg_0]
0x180019b49  mov     esi, eax
0x180019b4b  lea     rdx, [rbp+arg_8]
0x180019b4f  call    ?GetCurrentVariantState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_64kEtwBufferSize@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCurrentVariantState(int *)
0x180019b54  mov     r9, [rbx]
0x180019b57  mov     rcx, [rbp+arg_8]
0x180019b5b  mov     rax, r9
0x180019b5e  mov     r11d, dword ptr [rbp+arg_8+4]
0x180019b62  mov     r10, r9
0x180019b65  shr     rax, 20h
0x180019b69  mov     [rbx], r9d
0x180019b6c  mov     [rbx+4], eax
0x180019b6f  test    r9b, 8
0x180019b73  jnz     short loc_180019BB3
0x180019b75  mov     r8d, ecx
0x180019b78  mov     [rbx+4], r11d
0x180019b7c  and     r8d, 3F000h
0x180019b83  mov     eax, r9d
0x180019b86  and     eax, 0FFFC0FFFh
0x180019b8b  or      r8d, eax
0x180019b8e  mov     eax, dword ptr [rbp+arg_0]
0x180019b91  neg     eax
0x180019b93  mov     eax, ecx
0x180019b95  sbb     edx, edx
0x180019b97  and     r8d, 0FFFFFFF7h
0x180019b9b  and     edx, 8
0x180019b9e  and     eax, 800h
0x180019ba3  or      r8d, edx
0x180019ba6  btr     r8d, 0Bh
0x180019bab  or      r8d, eax
0x180019bae  mov     [rbx], r8d
0x180019bb1  jmp     short loc_180019BB6
0x180019bb3  mov     r8d, r9d
0x180019bb6  test    r9b, 4
0x180019bba  jnz     short loc_180019BD3
0x180019bbc  btr     r8d, 0Ah
0x180019bc1  mov     edx, ecx
0x180019bc3  and     edx, 400h
0x180019bc9  or      r8d, edx
0x180019bcc  or      r8d, 4
0x180019bd0  mov     [rbx], r8d
0x180019bd3  mov     rdx, [rbx]
0x180019bd6  mov     rax, r10
0x180019bd9  lock cmpxchg [rdi], rdx
0x180019bde  mov     r10, rax
0x180019be1  jz      short loc_180019BEB
0x180019be3  mov     r9d, eax
0x180019be6  jmp     loc_180019B65
0x180019beb  test    r9b, 4
0x180019bef  jnz     short loc_180019C50
0x180019bf1  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180019bf7  test    eax, eax
0x180019bf9  jz      short loc_180019C50
0x180019bfb  lea     r14, stru_180042F88
0x180019c02  mov     rcx, r14; SRWLock
0x180019c05  call    cs:__imp_AcquireSRWLockExclusive
0x180019c0b  mov     eax, cs:dword_180042F9C
0x180019c11  mov     [rbp+arg_8], r14
0x180019c15  test    esi, esi
0x180019c17  jz      short loc_180019C43
0x180019c19  cmp     esi, eax
0x180019c1b  jnz     short loc_180019C43
0x180019c1d  mov     r8d, 10h; unsigned __int64
0x180019c23  mov     [rbp+var_10], 1
0x180019c2b  lea     rdx, [rbp+var_10]; void *
0x180019c2f  mov     [rbp+var_8], rdi
0x180019c33  lea     rcx, qword_180042FC0; this
0x180019c3a  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180019c3f  test    al, al
0x180019c41  jnz     short loc_180019C47
0x180019c43  lock and dword ptr [rdi], 0FFFFFFFBh
0x180019c47  lea     rcx, [rbp+arg_8]
0x180019c4b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180019c50  mov     rsi, [rsp+30h+arg_18]
0x180019c55  mov     rax, rbx
0x180019c58  mov     rbx, [rsp+30h+arg_10]
0x180019c5d  add     rsp, 30h
0x180019c61  pop     r14
0x180019c63  pop     rdi
0x180019c64  pop     rbp
0x180019c65  retn
```
