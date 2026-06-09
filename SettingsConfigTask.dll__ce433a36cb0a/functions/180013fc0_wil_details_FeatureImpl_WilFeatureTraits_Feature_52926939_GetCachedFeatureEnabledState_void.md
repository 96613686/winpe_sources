# wil::details::FeatureImpl<__WilFeatureTraits_Feature_52926939>::GetCachedFeatureEnabledState(void)

- ea: `0x180013fc0`
- end: `0x1800140f9`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_52926939@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001a8cc`
- `0x18001cb60`
- `0x18001cba0`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180013fc0`
- `0x1800164bc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001407e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18001407e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_52926939>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_52926939__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_52926939__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_52926939>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_52926939__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 1,
            v14[1] = Feature_52926939__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_52926939__descriptor, 0xFFFFFFFB);
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
0x180013fc0  mov     [rsp+arg_10], rbx
0x180013fc5  mov     [rsp+arg_18], rbp
0x180013fca  mov     [rsp+arg_0], rcx
0x180013fcf  push    rsi
0x180013fd0  push    rdi
0x180013fd1  push    r14
0x180013fd3  sub     rsp, 30h
0x180013fd7  mov     rsi, cs:Feature_52926939__descriptor
0x180013fde  mov     rdi, rdx
0x180013fe1  mov     qword ptr [rdx], 0
0x180013fe8  mov     eax, [rsi]
0x180013fea  mov     [rdx], eax
0x180013fec  and     eax, 6
0x180013fef  cmp     al, 6
0x180013ff1  jz      loc_1800140E3
0x180013ff7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180013ffc  lea     r8, [rsp+48h+arg_0]
0x180014001  mov     dword ptr [rsp+48h+arg_0], 0
0x180014009  lea     rdx, [rsp+48h+arg_8]
0x18001400e  mov     ebp, eax
0x180014010  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_52926939@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_52926939>::GetCurrentFeatureEnabledState(int *)
0x180014015  mov     eax, [rdi]
0x180014017  mov     rbx, [rsp+48h+arg_8]
0x18001401c  cmp     dword ptr [rsp+48h+arg_0], 0
0x180014021  mov     edx, eax
0x180014023  mov     [rdi], eax
0x180014025  mov     ecx, eax
0x180014027  jz      short loc_180014042
0x180014029  test    dl, 2
0x18001402c  jnz     short loc_180014042
0x18001402e  and     ecx, 0FFFFF63Eh
0x180014034  mov     eax, ebx
0x180014036  and     eax, 9C1h
0x18001403b  or      ecx, eax
0x18001403d  or      ecx, 2
0x180014040  mov     [rdi], ecx
0x180014042  mov     r8d, edx
0x180014045  and     r8d, 4
0x180014049  jnz     short loc_18001405D
0x18001404b  btr     ecx, 0Ah
0x18001404f  mov     eax, ebx
0x180014051  and     eax, 400h
0x180014056  or      ecx, eax
0x180014058  or      ecx, 4
0x18001405b  mov     [rdi], ecx
0x18001405d  mov     eax, edx
0x18001405f  lock cmpxchg [rsi], ecx
0x180014063  jnz     short loc_18001401C
0x180014065  test    r8d, r8d
0x180014068  jnz     short loc_1800140CE
0x18001406a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014070  test    eax, eax
0x180014072  jz      short loc_1800140CE
0x180014074  lea     r14, SRWLock
0x18001407b  mov     rcx, r14; SRWLock
0x18001407e  call    cs:__imp_AcquireSRWLockExclusive
0x180014084  mov     eax, cs:dword_18002EED4
0x18001408a  mov     [rsp+48h+arg_8], r14
0x18001408f  test    ebp, ebp
0x180014091  jz      short loc_1800140C0
0x180014093  cmp     ebp, eax
0x180014095  jnz     short loc_1800140C0
0x180014097  mov     r8d, 10h; unsigned __int64
0x18001409d  mov     [rsp+48h+var_28], 1
0x1800140a6  lea     rdx, [rsp+48h+var_28]; void *
0x1800140ab  mov     [rsp+48h+var_20], rsi
0x1800140b0  lea     rcx, qword_18002EEF8; this
0x1800140b7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800140bc  test    al, al
0x1800140be  jnz     short loc_1800140C4
0x1800140c0  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800140c4  lea     rcx, [rsp+48h+arg_8]
0x1800140c9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800140ce  mov     eax, [rdi]
0x1800140d0  test    al, 2
0x1800140d2  jnz     short loc_1800140E3
0x1800140d4  and     eax, 0FFFFF63Eh
0x1800140d9  and     ebx, 9C1h
0x1800140df  or      eax, ebx
0x1800140e1  mov     [rdi], eax
0x1800140e3  mov     rbx, [rsp+48h+arg_10]
0x1800140e8  mov     rax, rdi
0x1800140eb  mov     rbp, [rsp+48h+arg_18]
0x1800140f0  add     rsp, 30h
0x1800140f4  pop     r14
0x1800140f6  pop     rdi
0x1800140f7  pop     rsi
0x1800140f8  retn
```
