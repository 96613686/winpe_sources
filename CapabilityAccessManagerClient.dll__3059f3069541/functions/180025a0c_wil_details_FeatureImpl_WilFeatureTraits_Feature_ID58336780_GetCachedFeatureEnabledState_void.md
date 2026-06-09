# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCachedFeatureEnabledState(void)

- ea: `0x180025a0c`
- end: `0x180025b45`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180027a60`
- `0x1800283d4`
- `0x180034750`

## callees

- `0x18000aa04`
- `0x18000b598`
- `0x18000fc44`
- `0x180025a0c`
- `0x180026bb4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025aca`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180025aca`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ID58336780__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ID58336780__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ID58336780__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_180061260);
      v16 = &stru_180061260;
      if ( !v5
        || v5 != dword_180061274
        || (v14[0] = 3,
            v14[1] = Feature_ID58336780__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180061298, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ID58336780__descriptor, 0xFFFFFFFB);
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
0x180025a0c  mov     [rsp+arg_10], rbx
0x180025a11  mov     [rsp+arg_18], rbp
0x180025a16  mov     [rsp+arg_0], rcx
0x180025a1b  push    rsi
0x180025a1c  push    rdi
0x180025a1d  push    r14
0x180025a1f  sub     rsp, 30h
0x180025a23  mov     rsi, cs:Feature_ID58336780__descriptor
0x180025a2a  mov     rdi, rdx
0x180025a2d  mov     qword ptr [rdx], 0
0x180025a34  mov     eax, [rsi]
0x180025a36  mov     [rdx], eax
0x180025a38  and     eax, 6
0x180025a3b  cmp     al, 6
0x180025a3d  jz      loc_180025B2F
0x180025a43  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180025a48  lea     r8, [rsp+48h+arg_0]
0x180025a4d  mov     dword ptr [rsp+48h+arg_0], 0
0x180025a55  lea     rdx, [rsp+48h+arg_8]
0x180025a5a  mov     ebp, eax
0x180025a5c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ID58336780@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ID58336780>::GetCurrentFeatureEnabledState(int *)
0x180025a61  mov     eax, [rdi]
0x180025a63  mov     rbx, [rsp+48h+arg_8]
0x180025a68  cmp     dword ptr [rsp+48h+arg_0], 0
0x180025a6d  mov     edx, eax
0x180025a6f  mov     [rdi], eax
0x180025a71  mov     ecx, eax
0x180025a73  jz      short loc_180025A8E
0x180025a75  test    dl, 2
0x180025a78  jnz     short loc_180025A8E
0x180025a7a  and     ecx, 0FFFFF63Eh
0x180025a80  mov     eax, ebx
0x180025a82  and     eax, 9C1h
0x180025a87  or      ecx, eax
0x180025a89  or      ecx, 2
0x180025a8c  mov     [rdi], ecx
0x180025a8e  mov     r8d, edx
0x180025a91  and     r8d, 4
0x180025a95  jnz     short loc_180025AA9
0x180025a97  btr     ecx, 0Ah
0x180025a9b  mov     eax, ebx
0x180025a9d  and     eax, 400h
0x180025aa2  or      ecx, eax
0x180025aa4  or      ecx, 4
0x180025aa7  mov     [rdi], ecx
0x180025aa9  mov     eax, edx
0x180025aab  lock cmpxchg [rsi], ecx
0x180025aaf  jnz     short loc_180025A68
0x180025ab1  test    r8d, r8d
0x180025ab4  jnz     short loc_180025B1A
0x180025ab6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180025abc  test    eax, eax
0x180025abe  jz      short loc_180025B1A
0x180025ac0  lea     r14, stru_180061260
0x180025ac7  mov     rcx, r14; SRWLock
0x180025aca  call    cs:__imp_AcquireSRWLockExclusive
0x180025ad0  mov     eax, cs:dword_180061274
0x180025ad6  mov     [rsp+48h+arg_8], r14
0x180025adb  test    ebp, ebp
0x180025add  jz      short loc_180025B0C
0x180025adf  cmp     ebp, eax
0x180025ae1  jnz     short loc_180025B0C
0x180025ae3  mov     r8d, 10h; unsigned __int64
0x180025ae9  mov     [rsp+48h+var_28], 3
0x180025af2  lea     rdx, [rsp+48h+var_28]; void *
0x180025af7  mov     [rsp+48h+var_20], rsi
0x180025afc  lea     rcx, qword_180061298; this
0x180025b03  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180025b08  test    al, al
0x180025b0a  jnz     short loc_180025B10
0x180025b0c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180025b10  lea     rcx, [rsp+48h+arg_8]
0x180025b15  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180025b1a  mov     eax, [rdi]
0x180025b1c  test    al, 2
0x180025b1e  jnz     short loc_180025B2F
0x180025b20  and     eax, 0FFFFF63Eh
0x180025b25  and     ebx, 9C1h
0x180025b2b  or      eax, ebx
0x180025b2d  mov     [rdi], eax
0x180025b2f  mov     rbx, [rsp+48h+arg_10]
0x180025b34  mov     rax, rdi
0x180025b37  mov     rbp, [rsp+48h+arg_18]
0x180025b3c  add     rsp, 30h
0x180025b40  pop     r14
0x180025b42  pop     rdi
0x180025b43  pop     rsi
0x180025b44  retn
```
