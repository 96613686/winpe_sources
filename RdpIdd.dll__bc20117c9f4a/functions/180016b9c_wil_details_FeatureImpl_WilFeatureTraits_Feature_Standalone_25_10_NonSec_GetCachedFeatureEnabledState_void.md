# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180016b9c`
- end: `0x180016cdc`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d074`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x180016b9c`
- `0x1800172e8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c5a`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016c5a`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_10_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_10_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_10_NonSec__descriptor, 0xFFFFFFFB);
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
0x180016b9c  mov     [rsp+arg_10], rbx
0x180016ba1  mov     [rsp+arg_18], rbp
0x180016ba6  mov     [rsp+arg_0], rcx
0x180016bab  push    rsi
0x180016bac  push    rdi
0x180016bad  push    r14
0x180016baf  sub     rsp, 30h
0x180016bb3  mov     rsi, cs:Feature_Standalone_25_10_NonSec__descriptor
0x180016bba  mov     rdi, rdx
0x180016bbd  mov     qword ptr [rdx], 0
0x180016bc4  mov     eax, [rsi]
0x180016bc6  mov     [rdx], eax
0x180016bc8  and     eax, 6
0x180016bcb  cmp     al, 6
0x180016bcd  jz      loc_180016CC5
0x180016bd3  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016bd8  lea     r8, [rsp+48h+arg_0]
0x180016bdd  mov     dword ptr [rsp+48h+arg_0], 0
0x180016be5  lea     rdx, [rsp+48h+arg_8]
0x180016bea  mov     ebp, eax
0x180016bec  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_10_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_10_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180016bf1  mov     eax, [rdi]
0x180016bf3  mov     rbx, [rsp+48h+arg_8]
0x180016bf8  cmp     dword ptr [rsp+48h+arg_0], 0
0x180016bfd  mov     edx, eax
0x180016bff  mov     [rdi], eax
0x180016c01  mov     ecx, eax
0x180016c03  jz      short loc_180016C1E
0x180016c05  test    dl, 2
0x180016c08  jnz     short loc_180016C1E
0x180016c0a  and     ecx, 0FFFFF63Eh
0x180016c10  mov     eax, ebx
0x180016c12  and     eax, 9C1h
0x180016c17  or      ecx, eax
0x180016c19  or      ecx, 2
0x180016c1c  mov     [rdi], ecx
0x180016c1e  mov     r8d, edx
0x180016c21  and     r8d, 4
0x180016c25  jnz     short loc_180016C39
0x180016c27  btr     ecx, 0Ah
0x180016c2b  mov     eax, ebx
0x180016c2d  and     eax, 400h
0x180016c32  or      ecx, eax
0x180016c34  or      ecx, 4
0x180016c37  mov     [rdi], ecx
0x180016c39  mov     eax, edx
0x180016c3b  lock cmpxchg [rsi], ecx
0x180016c3f  jnz     short loc_180016BF8
0x180016c41  test    r8d, r8d
0x180016c44  jnz     short loc_180016CB0
0x180016c46  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016c4c  test    eax, eax
0x180016c4e  jz      short loc_180016CB0
0x180016c50  lea     r14, SRWLock
0x180016c57  mov     rcx, r14; SRWLock
0x180016c5a  call    cs:__imp_AcquireSRWLockExclusive
0x180016c61  nop     dword ptr [rax+rax+00h]
0x180016c66  mov     eax, cs:dword_1800578F4
0x180016c6c  mov     [rsp+48h+arg_8], r14
0x180016c71  test    ebp, ebp
0x180016c73  jz      short loc_180016CA2
0x180016c75  cmp     ebp, eax
0x180016c77  jnz     short loc_180016CA2
0x180016c79  mov     r8d, 10h; unsigned __int64
0x180016c7f  mov     [rsp+48h+var_28], 3
0x180016c88  lea     rdx, [rsp+48h+var_28]; void *
0x180016c8d  mov     [rsp+48h+var_20], rsi
0x180016c92  lea     rcx, qword_180057928; this
0x180016c99  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016c9e  test    al, al
0x180016ca0  jnz     short loc_180016CA6
0x180016ca2  lock and dword ptr [rsi], 0FFFFFFFBh
0x180016ca6  lea     rcx, [rsp+48h+arg_8]
0x180016cab  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016cb0  mov     eax, [rdi]
0x180016cb2  test    al, 2
0x180016cb4  jnz     short loc_180016CC5
0x180016cb6  and     eax, 0FFFFF63Eh
0x180016cbb  and     ebx, 9C1h
0x180016cc1  or      eax, ebx
0x180016cc3  mov     [rdi], eax
0x180016cc5  mov     rbx, [rsp+48h+arg_10]
0x180016cca  mov     rax, rdi
0x180016ccd  mov     rbp, [rsp+48h+arg_18]
0x180016cd2  add     rsp, 30h
0x180016cd6  pop     r14
0x180016cd8  pop     rdi
0x180016cd9  pop     rsi
0x180016cda  retn
```
