# wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCachedFeatureEnabledState(void)

- ea: `0x180013e80`
- end: `0x180013fb9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a844`
- `0x18001cb24`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180013e80`
- `0x1800163ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013f3e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180013f3e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_51718004__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_51718004__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_51718004__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_51718004__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_51718004__descriptor, 0xFFFFFFFB);
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
0x180013e80  mov     [rsp+arg_10], rbx
0x180013e85  mov     [rsp+arg_18], rbp
0x180013e8a  mov     [rsp+arg_0], rcx
0x180013e8f  push    rsi
0x180013e90  push    rdi
0x180013e91  push    r14
0x180013e93  sub     rsp, 30h
0x180013e97  mov     rsi, cs:Feature_51718004__descriptor
0x180013e9e  mov     rdi, rdx
0x180013ea1  mov     qword ptr [rdx], 0
0x180013ea8  mov     eax, [rsi]
0x180013eaa  mov     [rdx], eax
0x180013eac  and     eax, 6
0x180013eaf  cmp     al, 6
0x180013eb1  jz      loc_180013FA3
0x180013eb7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013ebc  lea     r8, [rsp+48h+arg_0]
0x180013ec1  mov     dword ptr [rsp+48h+arg_0], 0
0x180013ec9  lea     rdx, [rsp+48h+arg_8]
0x180013ece  mov     ebp, eax
0x180013ed0  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_51718004@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_51718004>::GetCurrentFeatureEnabledState(int *)
0x180013ed5  mov     eax, [rdi]
0x180013ed7  mov     rbx, [rsp+48h+arg_8]
0x180013edc  cmp     dword ptr [rsp+48h+arg_0], 0
0x180013ee1  mov     edx, eax
0x180013ee3  mov     [rdi], eax
0x180013ee5  mov     ecx, eax
0x180013ee7  jz      short loc_180013F02
0x180013ee9  test    dl, 2
0x180013eec  jnz     short loc_180013F02
0x180013eee  and     ecx, 0FFFFF63Eh
0x180013ef4  mov     eax, ebx
0x180013ef6  and     eax, 9C1h
0x180013efb  or      ecx, eax
0x180013efd  or      ecx, 2
0x180013f00  mov     [rdi], ecx
0x180013f02  mov     r8d, edx
0x180013f05  and     r8d, 4
0x180013f09  jnz     short loc_180013F1D
0x180013f0b  btr     ecx, 0Ah
0x180013f0f  mov     eax, ebx
0x180013f11  and     eax, 400h
0x180013f16  or      ecx, eax
0x180013f18  or      ecx, 4
0x180013f1b  mov     [rdi], ecx
0x180013f1d  mov     eax, edx
0x180013f1f  lock cmpxchg [rsi], ecx
0x180013f23  jnz     short loc_180013EDC
0x180013f25  test    r8d, r8d
0x180013f28  jnz     short loc_180013F8E
0x180013f2a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180013f30  test    eax, eax
0x180013f32  jz      short loc_180013F8E
0x180013f34  lea     r14, SRWLock
0x180013f3b  mov     rcx, r14; SRWLock
0x180013f3e  call    cs:__imp_AcquireSRWLockExclusive
0x180013f44  mov     eax, cs:dword_18002EED4
0x180013f4a  mov     [rsp+48h+arg_8], r14
0x180013f4f  test    ebp, ebp
0x180013f51  jz      short loc_180013F80
0x180013f53  cmp     ebp, eax
0x180013f55  jnz     short loc_180013F80
0x180013f57  mov     r8d, 10h; unsigned __int64
0x180013f5d  mov     [rsp+48h+var_28], 3
0x180013f66  lea     rdx, [rsp+48h+var_28]; void *
0x180013f6b  mov     [rsp+48h+var_20], rsi
0x180013f70  lea     rcx, qword_18002EEF8; this
0x180013f77  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180013f7c  test    al, al
0x180013f7e  jnz     short loc_180013F84
0x180013f80  lock and dword ptr [rsi], 0FFFFFFFBh
0x180013f84  lea     rcx, [rsp+48h+arg_8]
0x180013f89  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180013f8e  mov     eax, [rdi]
0x180013f90  test    al, 2
0x180013f92  jnz     short loc_180013FA3
0x180013f94  and     eax, 0FFFFF63Eh
0x180013f99  and     ebx, 9C1h
0x180013f9f  or      eax, ebx
0x180013fa1  mov     [rdi], eax
0x180013fa3  mov     rbx, [rsp+48h+arg_10]
0x180013fa8  mov     rax, rdi
0x180013fab  mov     rbp, [rsp+48h+arg_18]
0x180013fb0  add     rsp, 30h
0x180013fb4  pop     r14
0x180013fb6  pop     rdi
0x180013fb7  pop     rsi
0x180013fb8  retn
```
