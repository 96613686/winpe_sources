# wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(void)

- ea: `0x1800058f4`
- end: `0x180005a1d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180009058`
- `0x18000aa60`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x1800058f4`
- `0x180006328`
- `0x18000ad18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_ValAccTest__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_ValAccTest__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_ValAccTest__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::AcquireSRWLockExclusive(&v16, (RTL_SRWLOCK *)qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_ValAccTest__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_ValAccTest__descriptor, 0xFFFFFFFB);
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
0x1800058f4  mov     [rsp+arg_10], rbx
0x1800058f9  mov     [rsp+arg_0], rcx
0x1800058fe  push    rbp
0x1800058ff  push    rsi
0x180005900  push    rdi
0x180005901  sub     rsp, 30h
0x180005905  mov     rsi, cs:Feature_ValAccTest__descriptor
0x18000590c  mov     rdi, rdx
0x18000590f  mov     qword ptr [rdx], 0
0x180005916  mov     eax, [rsi]
0x180005918  mov     [rdx], eax
0x18000591a  and     eax, 6
0x18000591d  cmp     al, 6
0x18000591f  jz      loc_180005A0D
0x180005925  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18000592a  lea     r8, [rsp+48h+arg_0]
0x18000592f  mov     dword ptr [rsp+48h+arg_0], 0
0x180005937  lea     rdx, [rsp+48h+arg_8]
0x18000593c  mov     ebp, eax
0x18000593e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_ValAccTest@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_ValAccTest>::GetCurrentFeatureEnabledState(int *)
0x180005943  mov     eax, [rdi]
0x180005945  mov     rbx, [rsp+48h+arg_8]
0x18000594a  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000594f  mov     edx, eax
0x180005951  mov     [rdi], eax
0x180005953  mov     ecx, eax
0x180005955  jz      short loc_180005970
0x180005957  test    dl, 2
0x18000595a  jnz     short loc_180005970
0x18000595c  and     ecx, 0FFFFF63Eh
0x180005962  mov     eax, ebx
0x180005964  and     eax, 9C1h
0x180005969  or      ecx, eax
0x18000596b  or      ecx, 2
0x18000596e  mov     [rdi], ecx
0x180005970  mov     r8d, edx
0x180005973  and     r8d, 4
0x180005977  jnz     short loc_18000598B
0x180005979  btr     ecx, 0Ah
0x18000597d  mov     eax, ebx
0x18000597f  and     eax, 400h
0x180005984  or      ecx, eax
0x180005986  or      ecx, 4
0x180005989  mov     [rdi], ecx
0x18000598b  mov     eax, edx
0x18000598d  lock cmpxchg [rsi], ecx
0x180005991  jnz     short loc_18000594A
0x180005993  test    r8d, r8d
0x180005996  jnz     short loc_1800059F8
0x180005998  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000599e  test    eax, eax
0x1800059a0  jz      short loc_1800059F8
0x1800059a2  lea     rdx, qword_180018220
0x1800059a9  lea     rcx, [rsp+48h+arg_8]
0x1800059ae  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x1800059b3  mov     eax, cs:dword_180018234
0x1800059b9  test    ebp, ebp
0x1800059bb  jz      short loc_1800059EA
0x1800059bd  cmp     ebp, eax
0x1800059bf  jnz     short loc_1800059EA
0x1800059c1  mov     r8d, 10h; unsigned __int64
0x1800059c7  mov     [rsp+48h+var_28], 3
0x1800059d0  lea     rdx, [rsp+48h+var_28]; void *
0x1800059d5  mov     [rsp+48h+var_20], rsi
0x1800059da  lea     rcx, qword_180018258; this
0x1800059e1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800059e6  test    al, al
0x1800059e8  jnz     short loc_1800059EE
0x1800059ea  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800059ee  lea     rcx, [rsp+48h+arg_8]
0x1800059f3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800059f8  mov     eax, [rdi]
0x1800059fa  test    al, 2
0x1800059fc  jnz     short loc_180005A0D
0x1800059fe  and     eax, 0FFFFF63Eh
0x180005a03  and     ebx, 9C1h
0x180005a09  or      eax, ebx
0x180005a0b  mov     [rdi], eax
0x180005a0d  mov     rbx, [rsp+48h+arg_10]
0x180005a12  mov     rax, rdi
0x180005a15  add     rsp, 30h
0x180005a19  pop     rdi
0x180005a1a  pop     rsi
0x180005a1b  pop     rbp
0x180005a1c  retn
```
