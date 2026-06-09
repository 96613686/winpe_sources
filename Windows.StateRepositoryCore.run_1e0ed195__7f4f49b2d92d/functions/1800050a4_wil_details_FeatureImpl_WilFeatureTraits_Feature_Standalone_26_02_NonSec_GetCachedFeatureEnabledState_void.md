# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x1800050a4`
- end: `0x1800051cd`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008ca4`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x1800050a4`
- `0x180005de8`
- `0x18000ad18`

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
  __int64 v16; // [rsp+58h] [rbp+10h] BYREF

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
    v8 = v16;
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
      wil::AcquireSRWLockExclusive(&v16, qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_02_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
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
0x1800050a4  mov     [rsp+arg_10], rbx
0x1800050a9  mov     [rsp+arg_0], rcx
0x1800050ae  push    rbp
0x1800050af  push    rsi
0x1800050b0  push    rdi
0x1800050b1  sub     rsp, 30h
0x1800050b5  mov     rsi, cs:Feature_Standalone_26_02_NonSec__descriptor
0x1800050bc  mov     rdi, rdx
0x1800050bf  mov     qword ptr [rdx], 0
0x1800050c6  mov     eax, [rsi]
0x1800050c8  mov     [rdx], eax
0x1800050ca  and     eax, 6
0x1800050cd  cmp     al, 6
0x1800050cf  jz      loc_1800051BD
0x1800050d5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800050da  lea     r8, [rsp+48h+arg_0]
0x1800050df  mov     dword ptr [rsp+48h+arg_0], 0
0x1800050e7  lea     rdx, [rsp+48h+arg_8]
0x1800050ec  mov     ebp, eax
0x1800050ee  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_02_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_02_NonSec>::GetCurrentFeatureEnabledState(int *)
0x1800050f3  mov     eax, [rdi]
0x1800050f5  mov     rbx, [rsp+48h+arg_8]
0x1800050fa  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800050ff  mov     edx, eax
0x180005101  mov     [rdi], eax
0x180005103  mov     ecx, eax
0x180005105  jz      short loc_180005120
0x180005107  test    dl, 2
0x18000510a  jnz     short loc_180005120
0x18000510c  and     ecx, 0FFFFF63Eh
0x180005112  mov     eax, ebx
0x180005114  and     eax, 9C1h
0x180005119  or      ecx, eax
0x18000511b  or      ecx, 2
0x18000511e  mov     [rdi], ecx
0x180005120  mov     r8d, edx
0x180005123  and     r8d, 4
0x180005127  jnz     short loc_18000513B
0x180005129  btr     ecx, 0Ah
0x18000512d  mov     eax, ebx
0x18000512f  and     eax, 400h
0x180005134  or      ecx, eax
0x180005136  or      ecx, 4
0x180005139  mov     [rdi], ecx
0x18000513b  mov     eax, edx
0x18000513d  lock cmpxchg [rsi], ecx
0x180005141  jnz     short loc_1800050FA
0x180005143  test    r8d, r8d
0x180005146  jnz     short loc_1800051A8
0x180005148  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000514e  test    eax, eax
0x180005150  jz      short loc_1800051A8
0x180005152  lea     rdx, qword_180018220
0x180005159  lea     rcx, [rsp+48h+arg_8]
0x18000515e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180005163  mov     eax, cs:dword_180018234
0x180005169  test    ebp, ebp
0x18000516b  jz      short loc_18000519A
0x18000516d  cmp     ebp, eax
0x18000516f  jnz     short loc_18000519A
0x180005171  mov     r8d, 10h; unsigned __int64
0x180005177  mov     [rsp+48h+var_28], 3
0x180005180  lea     rdx, [rsp+48h+var_28]; void *
0x180005185  mov     [rsp+48h+var_20], rsi
0x18000518a  lea     rcx, qword_180018258; this
0x180005191  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005196  test    al, al
0x180005198  jnz     short loc_18000519E
0x18000519a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000519e  lea     rcx, [rsp+48h+arg_8]
0x1800051a3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800051a8  mov     eax, [rdi]
0x1800051aa  test    al, 2
0x1800051ac  jnz     short loc_1800051BD
0x1800051ae  and     eax, 0FFFFF63Eh
0x1800051b3  and     ebx, 9C1h
0x1800051b9  or      eax, ebx
0x1800051bb  mov     [rdi], eax
0x1800051bd  mov     rbx, [rsp+48h+arg_10]
0x1800051c2  mov     rax, rdi
0x1800051c5  add     rsp, 30h
0x1800051c9  pop     rdi
0x1800051ca  pop     rsi
0x1800051cb  pop     rbp
0x1800051cc  retn
```
