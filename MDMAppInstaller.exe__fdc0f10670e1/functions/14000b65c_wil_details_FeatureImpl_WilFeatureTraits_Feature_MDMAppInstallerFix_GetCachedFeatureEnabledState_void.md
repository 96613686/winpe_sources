# wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCachedFeatureEnabledState(void)

- ea: `0x14000b65c`
- end: `0x14000b795`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x14000fbf0`
- `0x140011b64`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000b65c`
- `0x14000c3c8`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b71a`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000b71a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_MDMAppInstallerFix__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_MDMAppInstallerFix__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_MDMAppInstallerFix__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 1,
            v14[1] = Feature_MDMAppInstallerFix__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_MDMAppInstallerFix__descriptor, 0xFFFFFFFB);
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
0x14000b65c  mov     [rsp+arg_10], rbx
0x14000b661  mov     [rsp+arg_18], rbp
0x14000b666  mov     [rsp+arg_0], rcx
0x14000b66b  push    rsi
0x14000b66c  push    rdi
0x14000b66d  push    r14
0x14000b66f  sub     rsp, 30h
0x14000b673  mov     rsi, cs:Feature_MDMAppInstallerFix__descriptor
0x14000b67a  mov     rdi, rdx
0x14000b67d  mov     qword ptr [rdx], 0
0x14000b684  mov     eax, [rsi]
0x14000b686  mov     [rdx], eax
0x14000b688  and     eax, 6
0x14000b68b  cmp     al, 6
0x14000b68d  jz      loc_14000B77F
0x14000b693  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000b698  lea     r8, [rsp+48h+arg_0]
0x14000b69d  mov     dword ptr [rsp+48h+arg_0], 0
0x14000b6a5  lea     rdx, [rsp+48h+arg_8]
0x14000b6aa  mov     ebp, eax
0x14000b6ac  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_MDMAppInstallerFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_MDMAppInstallerFix>::GetCurrentFeatureEnabledState(int *)
0x14000b6b1  mov     eax, [rdi]
0x14000b6b3  mov     rbx, [rsp+48h+arg_8]
0x14000b6b8  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000b6bd  mov     edx, eax
0x14000b6bf  mov     [rdi], eax
0x14000b6c1  mov     ecx, eax
0x14000b6c3  jz      short loc_14000B6DE
0x14000b6c5  test    dl, 2
0x14000b6c8  jnz     short loc_14000B6DE
0x14000b6ca  and     ecx, 0FFFFF63Eh
0x14000b6d0  mov     eax, ebx
0x14000b6d2  and     eax, 9C1h
0x14000b6d7  or      ecx, eax
0x14000b6d9  or      ecx, 2
0x14000b6dc  mov     [rdi], ecx
0x14000b6de  mov     r8d, edx
0x14000b6e1  and     r8d, 4
0x14000b6e5  jnz     short loc_14000B6F9
0x14000b6e7  btr     ecx, 0Ah
0x14000b6eb  mov     eax, ebx
0x14000b6ed  and     eax, 400h
0x14000b6f2  or      ecx, eax
0x14000b6f4  or      ecx, 4
0x14000b6f7  mov     [rdi], ecx
0x14000b6f9  mov     eax, edx
0x14000b6fb  lock cmpxchg [rsi], ecx
0x14000b6ff  jnz     short loc_14000B6B8
0x14000b701  test    r8d, r8d
0x14000b704  jnz     short loc_14000B76A
0x14000b706  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000b70c  test    eax, eax
0x14000b70e  jz      short loc_14000B76A
0x14000b710  lea     r14, stru_14002BCD0
0x14000b717  mov     rcx, r14; SRWLock
0x14000b71a  call    cs:__imp_AcquireSRWLockExclusive
0x14000b720  mov     eax, cs:dword_14002BCE4
0x14000b726  mov     [rsp+48h+arg_8], r14
0x14000b72b  test    ebp, ebp
0x14000b72d  jz      short loc_14000B75C
0x14000b72f  cmp     ebp, eax
0x14000b731  jnz     short loc_14000B75C
0x14000b733  mov     r8d, 10h; unsigned __int64
0x14000b739  mov     [rsp+48h+var_28], 1
0x14000b742  lea     rdx, [rsp+48h+var_28]; void *
0x14000b747  mov     [rsp+48h+var_20], rsi
0x14000b74c  lea     rcx, qword_14002BD08; this
0x14000b753  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000b758  test    al, al
0x14000b75a  jnz     short loc_14000B760
0x14000b75c  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000b760  lea     rcx, [rsp+48h+arg_8]
0x14000b765  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000b76a  mov     eax, [rdi]
0x14000b76c  test    al, 2
0x14000b76e  jnz     short loc_14000B77F
0x14000b770  and     eax, 0FFFFF63Eh
0x14000b775  and     ebx, 9C1h
0x14000b77b  or      eax, ebx
0x14000b77d  mov     [rdi], eax
0x14000b77f  mov     rbx, [rsp+48h+arg_10]
0x14000b784  mov     rax, rdi
0x14000b787  mov     rbp, [rsp+48h+arg_18]
0x14000b78c  add     rsp, 30h
0x14000b790  pop     r14
0x14000b792  pop     rdi
0x14000b793  pop     rsi
0x14000b794  retn
```
