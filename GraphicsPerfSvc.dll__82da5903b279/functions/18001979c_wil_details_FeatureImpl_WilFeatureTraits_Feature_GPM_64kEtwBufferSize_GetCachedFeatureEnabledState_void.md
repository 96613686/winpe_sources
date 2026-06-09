# wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCachedFeatureEnabledState(void)

- ea: `0x18001979c`
- end: `0x1800198d5`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_64kEtwBufferSize@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ac94`
- `0x18001c594`

## callees

- `0x180005c8c`
- `0x180006744`
- `0x18000a96c`
- `0x18001979c`
- `0x180019cd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001985a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001985a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCachedFeatureEnabledState(
        wil::details *a1,
        _QWORD *a2)
{
  int v3; // eax
  unsigned int v4; // eax
  unsigned int v5; // ebp
  __int64 v6; // rcx
  signed __int32 v7; // eax
  __int16 v8; // bx
  bool v9; // zf
  signed __int32 v10; // edx
  unsigned int v11; // ecx
  int v12; // r8d
  _QWORD v14[5]; // [rsp+20h] [rbp-28h] BYREF
  wil::details *v15; // [rsp+50h] [rbp+8h] BYREF
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

  v15 = a1;
  *a2 = 0;
  v3 = *(_DWORD *)Feature_GPM_64kEtwBufferSize__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_GPM_64kEtwBufferSize__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCurrentFeatureEnabledState(
      v6,
      &v16,
      &v15);
    v7 = *(_DWORD *)a2;
    v8 = (__int16)v16;
    do
    {
      v9 = (_DWORD)v15 == 0;
      v10 = v7;
      *(_DWORD *)a2 = v7;
      v11 = v7;
      if ( !v9 && (v7 & 2) == 0 )
      {
        v11 = v8 & 0x9C1 | v7 & 0xFFFFF63E | 2;
        *(_DWORD *)a2 = v11;
      }
      v12 = v7 & 4;
      if ( (v7 & 4) == 0 )
      {
        v11 = v8 & 0x400 | v11 & 0xFFFFFBFF | 4;
        *(_DWORD *)a2 = v11;
      }
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_GPM_64kEtwBufferSize__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180042F88);
      v16 = &stru_180042F88;
      if ( !v5
        || v5 != dword_180042F9C
        || (v14[0] = 1,
            v14[1] = Feature_GPM_64kEtwBufferSize__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180042FC0, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_GPM_64kEtwBufferSize__descriptor, 0xFFFFFFFB);
      }
      wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v16);
    }
    if ( (*(_DWORD *)a2 & 2) == 0 )
      *(_DWORD *)a2 = v8 & 0x9C1 | *(_DWORD *)a2 & 0xFFFFF63E;
  }
  return a2;
}

```

## disassembly

```asm
0x18001979c  mov     [rsp+arg_10], rbx
0x1800197a1  mov     [rsp+arg_18], rbp
0x1800197a6  mov     [rsp+arg_0], rcx
0x1800197ab  push    rsi
0x1800197ac  push    rdi
0x1800197ad  push    r14
0x1800197af  sub     rsp, 30h
0x1800197b3  mov     rsi, cs:Feature_GPM_64kEtwBufferSize__descriptor
0x1800197ba  mov     rdi, rdx
0x1800197bd  mov     qword ptr [rdx], 0
0x1800197c4  mov     eax, [rsi]
0x1800197c6  mov     [rdx], eax
0x1800197c8  and     eax, 6
0x1800197cb  cmp     al, 6
0x1800197cd  jz      loc_1800198BF
0x1800197d3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800197d8  lea     r8, [rsp+48h+arg_0]
0x1800197dd  mov     dword ptr [rsp+48h+arg_0], 0
0x1800197e5  lea     rdx, [rsp+48h+arg_8]
0x1800197ea  mov     ebp, eax
0x1800197ec  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_GPM_64kEtwBufferSize@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_GPM_64kEtwBufferSize>::GetCurrentFeatureEnabledState(int *)
0x1800197f1  mov     eax, [rdi]
0x1800197f3  mov     rbx, [rsp+48h+arg_8]
0x1800197f8  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800197fd  mov     edx, eax
0x1800197ff  mov     [rdi], eax
0x180019801  mov     ecx, eax
0x180019803  jz      short loc_18001981E
0x180019805  test    dl, 2
0x180019808  jnz     short loc_18001981E
0x18001980a  and     ecx, 0FFFFF63Eh
0x180019810  mov     eax, ebx
0x180019812  and     eax, 9C1h
0x180019817  or      ecx, eax
0x180019819  or      ecx, 2
0x18001981c  mov     [rdi], ecx
0x18001981e  mov     r8d, edx
0x180019821  and     r8d, 4
0x180019825  jnz     short loc_180019839
0x180019827  btr     ecx, 0Ah
0x18001982b  mov     eax, ebx
0x18001982d  and     eax, 400h
0x180019832  or      ecx, eax
0x180019834  or      ecx, 4
0x180019837  mov     [rdi], ecx
0x180019839  mov     eax, edx
0x18001983b  lock cmpxchg [rsi], ecx
0x18001983f  jnz     short loc_1800197F8
0x180019841  test    r8d, r8d
0x180019844  jnz     short loc_1800198AA
0x180019846  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18001984c  test    eax, eax
0x18001984e  jz      short loc_1800198AA
0x180019850  lea     r14, stru_180042F88
0x180019857  mov     rcx, r14; SRWLock
0x18001985a  call    cs:__imp_AcquireSRWLockExclusive
0x180019860  mov     eax, cs:dword_180042F9C
0x180019866  mov     [rsp+48h+arg_8], r14
0x18001986b  test    ebp, ebp
0x18001986d  jz      short loc_18001989C
0x18001986f  cmp     ebp, eax
0x180019871  jnz     short loc_18001989C
0x180019873  mov     r8d, 10h; unsigned __int64
0x180019879  mov     [rsp+48h+var_28], 1
0x180019882  lea     rdx, [rsp+48h+var_28]; void *
0x180019887  mov     [rsp+48h+var_20], rsi
0x18001988c  lea     rcx, qword_180042FC0; this
0x180019893  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180019898  test    al, al
0x18001989a  jnz     short loc_1800198A0
0x18001989c  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800198a0  lea     rcx, [rsp+48h+arg_8]
0x1800198a5  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800198aa  mov     eax, [rdi]
0x1800198ac  test    al, 2
0x1800198ae  jnz     short loc_1800198BF
0x1800198b0  and     eax, 0FFFFF63Eh
0x1800198b5  and     ebx, 9C1h
0x1800198bb  or      eax, ebx
0x1800198bd  mov     [rdi], eax
0x1800198bf  mov     rbx, [rsp+48h+arg_10]
0x1800198c4  mov     rax, rdi
0x1800198c7  mov     rbp, [rsp+48h+arg_18]
0x1800198cc  add     rsp, 30h
0x1800198d0  pop     r14
0x1800198d2  pop     rdi
0x1800198d3  pop     rsi
0x1800198d4  retn
```
