# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x18002ab30`
- end: `0x18002ac70`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c854`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x18002ab30`
- `0x18002b320`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002abee`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002abee`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_02_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_02_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_02_NonSec__descriptor, 0xFFFFFFFB);
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
0x18002ab30  mov     [rsp+arg_10], rbx
0x18002ab35  mov     [rsp+arg_18], rbp
0x18002ab3a  mov     [rsp+arg_0], rcx
0x18002ab3f  push    rsi
0x18002ab40  push    rdi
0x18002ab41  push    r14
0x18002ab43  sub     rsp, 30h
0x18002ab47  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x18002ab4e  mov     rdi, rdx
0x18002ab51  mov     qword ptr [rdx], 0
0x18002ab58  mov     eax, [rsi]
0x18002ab5a  mov     [rdx], eax
0x18002ab5c  and     eax, 6
0x18002ab5f  cmp     al, 6
0x18002ab61  jz      loc_18002AC59
0x18002ab67  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002ab6c  lea     r8, [rsp+48h+arg_0]
0x18002ab71  mov     dword ptr [rsp+48h+arg_0], 0
0x18002ab79  lea     rdx, [rsp+48h+arg_8]
0x18002ab7e  mov     ebp, eax
0x18002ab80  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x18002ab85  mov     eax, [rdi]
0x18002ab87  mov     rbx, [rsp+48h+arg_8]
0x18002ab8c  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002ab91  mov     edx, eax
0x18002ab93  mov     [rdi], eax
0x18002ab95  mov     ecx, eax
0x18002ab97  jz      short loc_18002ABB2
0x18002ab99  test    dl, 2
0x18002ab9c  jnz     short loc_18002ABB2
0x18002ab9e  and     ecx, 0FFFFF63Eh
0x18002aba4  mov     eax, ebx
0x18002aba6  and     eax, 9C1h
0x18002abab  or      ecx, eax
0x18002abad  or      ecx, 2
0x18002abb0  mov     [rdi], ecx
0x18002abb2  mov     r8d, edx
0x18002abb5  and     r8d, 4
0x18002abb9  jnz     short loc_18002ABCD
0x18002abbb  btr     ecx, 0Ah
0x18002abbf  mov     eax, ebx
0x18002abc1  and     eax, 400h
0x18002abc6  or      ecx, eax
0x18002abc8  or      ecx, 4
0x18002abcb  mov     [rdi], ecx
0x18002abcd  mov     eax, edx
0x18002abcf  lock cmpxchg [rsi], ecx
0x18002abd3  jnz     short loc_18002AB8C
0x18002abd5  test    r8d, r8d
0x18002abd8  jnz     short loc_18002AC44
0x18002abda  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002abe0  test    eax, eax
0x18002abe2  jz      short loc_18002AC44
0x18002abe4  lea     r14, SRWLock
0x18002abeb  mov     rcx, r14; SRWLock
0x18002abee  call    cs:__imp_AcquireSRWLockExclusive
0x18002abf5  nop     dword ptr [rax+rax+00h]
0x18002abfa  mov     eax, cs:dword_1800578F4
0x18002ac00  mov     [rsp+48h+arg_8], r14
0x18002ac05  test    ebp, ebp
0x18002ac07  jz      short loc_18002AC36
0x18002ac09  cmp     ebp, eax
0x18002ac0b  jnz     short loc_18002AC36
0x18002ac0d  mov     r8d, 10h; unsigned __int64
0x18002ac13  mov     [rsp+48h+var_28], 3
0x18002ac1c  lea     rdx, [rsp+48h+var_28]; void *
0x18002ac21  mov     [rsp+48h+var_20], rsi
0x18002ac26  lea     rcx, qword_180057928; this
0x18002ac2d  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002ac32  test    al, al
0x18002ac34  jnz     short loc_18002AC3A
0x18002ac36  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002ac3a  lea     rcx, [rsp+48h+arg_8]
0x18002ac3f  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ac44  mov     eax, [rdi]
0x18002ac46  test    al, 2
0x18002ac48  jnz     short loc_18002AC59
0x18002ac4a  and     eax, 0FFFFF63Eh
0x18002ac4f  and     ebx, 9C1h
0x18002ac55  or      eax, ebx
0x18002ac57  mov     [rdi], eax
0x18002ac59  mov     rbx, [rsp+48h+arg_10]
0x18002ac5e  mov     rax, rdi
0x18002ac61  mov     rbp, [rsp+48h+arg_18]
0x18002ac66  add     rsp, 30h
0x18002ac6a  pop     r14
0x18002ac6c  pop     rdi
0x18002ac6d  pop     rsi
0x18002ac6e  retn
```
