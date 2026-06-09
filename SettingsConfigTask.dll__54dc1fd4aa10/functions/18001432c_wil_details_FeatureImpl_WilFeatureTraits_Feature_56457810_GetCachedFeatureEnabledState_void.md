# wil::details::FeatureImpl<__WilFeatureTraits_Feature_56457810>::GetCachedFeatureEnabledState(void)

- ea: `0x18001432c`
- end: `0x180014465`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56457810@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aa74`
- `0x18001cc5c`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x18001432c`
- `0x1800166e4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800143ea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x1800143ea`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_56457810>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_56457810__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_56457810__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_56457810>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_56457810__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_56457810__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_56457810__descriptor, 0xFFFFFFFB);
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
0x18001432c  mov     [rsp+arg_10], rbx
0x180014331  mov     [rsp+arg_18], rbp
0x180014336  mov     [rsp+arg_0], rcx
0x18001433b  push    rsi
0x18001433c  push    rdi
0x18001433d  push    r14
0x18001433f  sub     rsp, 30h
0x180014343  mov     rsi, cs:Feature_56457810__descriptor
0x18001434a  mov     rdi, rdx
0x18001434d  mov     qword ptr [rdx], 0
0x180014354  mov     eax, [rsi]
0x180014356  mov     [rdx], eax
0x180014358  and     eax, 6
0x18001435b  cmp     al, 6
0x18001435d  jz      loc_18001444F
0x180014363  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014368  lea     r8, [rsp+48h+arg_0]
0x18001436d  mov     dword ptr [rsp+48h+arg_0], 0
0x180014375  lea     rdx, [rsp+48h+arg_8]
0x18001437a  mov     ebp, eax
0x18001437c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_56457810@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_56457810>::GetCurrentFeatureEnabledState(int *)
0x180014381  mov     eax, [rdi]
0x180014383  mov     rbx, [rsp+48h+arg_8]
0x180014388  cmp     dword ptr [rsp+48h+arg_0], 0
0x18001438d  mov     edx, eax
0x18001438f  mov     [rdi], eax
0x180014391  mov     ecx, eax
0x180014393  jz      short loc_1800143AE
0x180014395  test    dl, 2
0x180014398  jnz     short loc_1800143AE
0x18001439a  and     ecx, 0FFFFF63Eh
0x1800143a0  mov     eax, ebx
0x1800143a2  and     eax, 9C1h
0x1800143a7  or      ecx, eax
0x1800143a9  or      ecx, 2
0x1800143ac  mov     [rdi], ecx
0x1800143ae  mov     r8d, edx
0x1800143b1  and     r8d, 4
0x1800143b5  jnz     short loc_1800143C9
0x1800143b7  btr     ecx, 0Ah
0x1800143bb  mov     eax, ebx
0x1800143bd  and     eax, 400h
0x1800143c2  or      ecx, eax
0x1800143c4  or      ecx, 4
0x1800143c7  mov     [rdi], ecx
0x1800143c9  mov     eax, edx
0x1800143cb  lock cmpxchg [rsi], ecx
0x1800143cf  jnz     short loc_180014388
0x1800143d1  test    r8d, r8d
0x1800143d4  jnz     short loc_18001443A
0x1800143d6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x1800143dc  test    eax, eax
0x1800143de  jz      short loc_18001443A
0x1800143e0  lea     r14, SRWLock
0x1800143e7  mov     rcx, r14; SRWLock
0x1800143ea  call    cs:__imp_AcquireSRWLockExclusive
0x1800143f0  mov     eax, cs:dword_18002EED4
0x1800143f6  mov     [rsp+48h+arg_8], r14
0x1800143fb  test    ebp, ebp
0x1800143fd  jz      short loc_18001442C
0x1800143ff  cmp     ebp, eax
0x180014401  jnz     short loc_18001442C
0x180014403  mov     r8d, 10h; unsigned __int64
0x180014409  mov     [rsp+48h+var_28], 3
0x180014412  lea     rdx, [rsp+48h+var_28]; void *
0x180014417  mov     [rsp+48h+var_20], rsi
0x18001441c  lea     rcx, qword_18002EEF8; this
0x180014423  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014428  test    al, al
0x18001442a  jnz     short loc_180014430
0x18001442c  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014430  lea     rcx, [rsp+48h+arg_8]
0x180014435  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18001443a  mov     eax, [rdi]
0x18001443c  test    al, 2
0x18001443e  jnz     short loc_18001444F
0x180014440  and     eax, 0FFFFF63Eh
0x180014445  and     ebx, 9C1h
0x18001444b  or      eax, ebx
0x18001444d  mov     [rdi], eax
0x18001444f  mov     rbx, [rsp+48h+arg_10]
0x180014454  mov     rax, rdi
0x180014457  mov     rbp, [rsp+48h+arg_18]
0x18001445c  add     rsp, 30h
0x180014460  pop     r14
0x180014462  pop     rdi
0x180014463  pop     rsi
0x180014464  retn
```
