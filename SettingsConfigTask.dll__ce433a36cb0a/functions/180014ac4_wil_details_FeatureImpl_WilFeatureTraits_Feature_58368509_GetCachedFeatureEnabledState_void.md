# wil::details::FeatureImpl<__WilFeatureTraits_Feature_58368509>::GetCachedFeatureEnabledState(void)

- ea: `0x180014ac4`
- end: `0x180014bfd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58368509@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001aee0`
- `0x18001ce80`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180014ac4`
- `0x180016d40`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014b82`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180014b82`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_58368509>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_58368509__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_58368509__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_58368509>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_58368509__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_58368509__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_58368509__descriptor, 0xFFFFFFFB);
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
0x180014ac4  mov     [rsp+arg_10], rbx
0x180014ac9  mov     [rsp+arg_18], rbp
0x180014ace  mov     [rsp+arg_0], rcx
0x180014ad3  push    rsi
0x180014ad4  push    rdi
0x180014ad5  push    r14
0x180014ad7  sub     rsp, 30h
0x180014adb  mov     rsi, cs:Feature_58368509__descriptor
0x180014ae2  mov     rdi, rdx
0x180014ae5  mov     qword ptr [rdx], 0
0x180014aec  mov     eax, [rsi]
0x180014aee  mov     [rdx], eax
0x180014af0  and     eax, 6
0x180014af3  cmp     al, 6
0x180014af5  jz      loc_180014BE7
0x180014afb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180014b00  lea     r8, [rsp+48h+arg_0]
0x180014b05  mov     dword ptr [rsp+48h+arg_0], 0
0x180014b0d  lea     rdx, [rsp+48h+arg_8]
0x180014b12  mov     ebp, eax
0x180014b14  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_58368509@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_58368509>::GetCurrentFeatureEnabledState(int *)
0x180014b19  mov     eax, [rdi]
0x180014b1b  mov     rbx, [rsp+48h+arg_8]
0x180014b20  cmp     dword ptr [rsp+48h+arg_0], 0
0x180014b25  mov     edx, eax
0x180014b27  mov     [rdi], eax
0x180014b29  mov     ecx, eax
0x180014b2b  jz      short loc_180014B46
0x180014b2d  test    dl, 2
0x180014b30  jnz     short loc_180014B46
0x180014b32  and     ecx, 0FFFFF63Eh
0x180014b38  mov     eax, ebx
0x180014b3a  and     eax, 9C1h
0x180014b3f  or      ecx, eax
0x180014b41  or      ecx, 2
0x180014b44  mov     [rdi], ecx
0x180014b46  mov     r8d, edx
0x180014b49  and     r8d, 4
0x180014b4d  jnz     short loc_180014B61
0x180014b4f  btr     ecx, 0Ah
0x180014b53  mov     eax, ebx
0x180014b55  and     eax, 400h
0x180014b5a  or      ecx, eax
0x180014b5c  or      ecx, 4
0x180014b5f  mov     [rdi], ecx
0x180014b61  mov     eax, edx
0x180014b63  lock cmpxchg [rsi], ecx
0x180014b67  jnz     short loc_180014B20
0x180014b69  test    r8d, r8d
0x180014b6c  jnz     short loc_180014BD2
0x180014b6e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180014b74  test    eax, eax
0x180014b76  jz      short loc_180014BD2
0x180014b78  lea     r14, SRWLock
0x180014b7f  mov     rcx, r14; SRWLock
0x180014b82  call    cs:__imp_AcquireSRWLockExclusive
0x180014b88  mov     eax, cs:dword_18002EED4
0x180014b8e  mov     [rsp+48h+arg_8], r14
0x180014b93  test    ebp, ebp
0x180014b95  jz      short loc_180014BC4
0x180014b97  cmp     ebp, eax
0x180014b99  jnz     short loc_180014BC4
0x180014b9b  mov     r8d, 10h; unsigned __int64
0x180014ba1  mov     [rsp+48h+var_28], 3
0x180014baa  lea     rdx, [rsp+48h+var_28]; void *
0x180014baf  mov     [rsp+48h+var_20], rsi
0x180014bb4  lea     rcx, qword_18002EEF8; this
0x180014bbb  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180014bc0  test    al, al
0x180014bc2  jnz     short loc_180014BC8
0x180014bc4  lock and dword ptr [rsi], 0FFFFFFFBh
0x180014bc8  lea     rcx, [rsp+48h+arg_8]
0x180014bcd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180014bd2  mov     eax, [rdi]
0x180014bd4  test    al, 2
0x180014bd6  jnz     short loc_180014BE7
0x180014bd8  and     eax, 0FFFFF63Eh
0x180014bdd  and     ebx, 9C1h
0x180014be3  or      eax, ebx
0x180014be5  mov     [rdi], eax
0x180014be7  mov     rbx, [rsp+48h+arg_10]
0x180014bec  mov     rax, rdi
0x180014bef  mov     rbp, [rsp+48h+arg_18]
0x180014bf4  add     rsp, 30h
0x180014bf8  pop     r14
0x180014bfa  pop     rdi
0x180014bfb  pop     rsi
0x180014bfc  retn
```
