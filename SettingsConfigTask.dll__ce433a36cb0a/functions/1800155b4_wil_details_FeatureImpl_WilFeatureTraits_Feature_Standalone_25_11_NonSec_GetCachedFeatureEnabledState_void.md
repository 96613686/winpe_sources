# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800155b4`
- end: `0x1800156ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b3b0`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x1800155b4`
- `0x1800173a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015672`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015672`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_25_11_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_25_11_NonSec__descriptor, 0xFFFFFFFB);
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
0x1800155b4  mov     [rsp+arg_10], rbx
0x1800155b9  mov     [rsp+arg_18], rbp
0x1800155be  mov     [rsp+arg_0], rcx
0x1800155c3  push    rsi
0x1800155c4  push    rdi
0x1800155c5  push    r14
0x1800155c7  sub     rsp, 30h
0x1800155cb  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x1800155d2  mov     rdi, rdx
0x1800155d5  mov     qword ptr [rdx], 0
0x1800155dc  mov     eax, [rsi]
0x1800155de  mov     [rdx], eax
0x1800155e0  and     eax, 6
0x1800155e3  cmp     al, 6
0x1800155e5  jz      loc_1800156D7
0x1800155eb  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800155f0  lea     r8, [rsp+48h+arg_0]
0x1800155f5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800155fd  lea     rdx, [rsp+48h+arg_8]
0x180015602  mov     ebp, eax
0x180015604  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180015609  mov     eax, [rdi]
0x18001560b  mov     rbx, [rsp+48h+arg_8]
0x180015610  cmp     dword ptr [rsp+48h+arg_0], 0
0x180015615  mov     edx, eax
0x180015617  mov     [rdi], eax
0x180015619  mov     ecx, eax
0x18001561b  jz      short loc_180015636
0x18001561d  test    dl, 2
0x180015620  jnz     short loc_180015636
0x180015622  and     ecx, 0FFFFF63Eh
0x180015628  mov     eax, ebx
0x18001562a  and     eax, 9C1h
0x18001562f  or      ecx, eax
0x180015631  or      ecx, 2
0x180015634  mov     [rdi], ecx
0x180015636  mov     r8d, edx
0x180015639  and     r8d, 4
0x18001563d  jnz     short loc_180015651
0x18001563f  btr     ecx, 0Ah
0x180015643  mov     eax, ebx
0x180015645  and     eax, 400h
0x18001564a  or      ecx, eax
0x18001564c  or      ecx, 4
0x18001564f  mov     [rdi], ecx
0x180015651  mov     eax, edx
0x180015653  lock cmpxchg [rsi], ecx
0x180015657  jnz     short loc_180015610
0x180015659  test    r8d, r8d
0x18001565c  jnz     short loc_1800156C2
0x18001565e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015664  test    eax, eax
0x180015666  jz      short loc_1800156C2
0x180015668  lea     r14, SRWLock
0x18001566f  mov     rcx, r14; SRWLock
0x180015672  call    cs:__imp_AcquireSRWLockExclusive
0x180015678  mov     eax, cs:dword_18002EED4
0x18001567e  mov     [rsp+48h+arg_8], r14
0x180015683  test    ebp, ebp
0x180015685  jz      short loc_1800156B4
0x180015687  cmp     ebp, eax
0x180015689  jnz     short loc_1800156B4
0x18001568b  mov     r8d, 10h; unsigned __int64
0x180015691  mov     [rsp+48h+var_28], 3
0x18001569a  lea     rdx, [rsp+48h+var_28]; void *
0x18001569f  mov     [rsp+48h+var_20], rsi
0x1800156a4  lea     rcx, qword_18002EEF8; this
0x1800156ab  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800156b0  test    al, al
0x1800156b2  jnz     short loc_1800156B8
0x1800156b4  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800156b8  lea     rcx, [rsp+48h+arg_8]
0x1800156bd  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800156c2  mov     eax, [rdi]
0x1800156c4  test    al, 2
0x1800156c6  jnz     short loc_1800156D7
0x1800156c8  and     eax, 0FFFFF63Eh
0x1800156cd  and     ebx, 9C1h
0x1800156d3  or      eax, ebx
0x1800156d5  mov     [rdi], eax
0x1800156d7  mov     rbx, [rsp+48h+arg_10]
0x1800156dc  mov     rax, rdi
0x1800156df  mov     rbp, [rsp+48h+arg_18]
0x1800156e4  add     rsp, 30h
0x1800156e8  pop     r14
0x1800156ea  pop     rdi
0x1800156eb  pop     rsi
0x1800156ec  retn
```
