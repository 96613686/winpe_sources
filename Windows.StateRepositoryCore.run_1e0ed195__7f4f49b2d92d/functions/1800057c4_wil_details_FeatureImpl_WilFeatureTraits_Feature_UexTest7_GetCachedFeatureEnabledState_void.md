# wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(void)

- ea: `0x1800057c4`
- end: `0x1800058ed`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008fd0`
- `0x18000aa24`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x1800057c4`
- `0x180006244`
- `0x18000ad18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_UexTest7__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_UexTest7__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_UexTest7__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::AcquireSRWLockExclusive(&v16, qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_UexTest7__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_UexTest7__descriptor, 0xFFFFFFFB);
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
0x1800057c4  mov     [rsp+arg_10], rbx
0x1800057c9  mov     [rsp+arg_0], rcx
0x1800057ce  push    rbp
0x1800057cf  push    rsi
0x1800057d0  push    rdi
0x1800057d1  sub     rsp, 30h
0x1800057d5  mov     rsi, cs:Feature_UexTest7__descriptor
0x1800057dc  mov     rdi, rdx
0x1800057df  mov     qword ptr [rdx], 0
0x1800057e6  mov     eax, [rsi]
0x1800057e8  mov     [rdx], eax
0x1800057ea  and     eax, 6
0x1800057ed  cmp     al, 6
0x1800057ef  jz      loc_1800058DD
0x1800057f5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800057fa  lea     r8, [rsp+48h+arg_0]
0x1800057ff  mov     dword ptr [rsp+48h+arg_0], 0
0x180005807  lea     rdx, [rsp+48h+arg_8]
0x18000580c  mov     ebp, eax
0x18000580e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_UexTest7@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_UexTest7>::GetCurrentFeatureEnabledState(int *)
0x180005813  mov     eax, [rdi]
0x180005815  mov     rbx, [rsp+48h+arg_8]
0x18000581a  cmp     dword ptr [rsp+48h+arg_0], 0
0x18000581f  mov     edx, eax
0x180005821  mov     [rdi], eax
0x180005823  mov     ecx, eax
0x180005825  jz      short loc_180005840
0x180005827  test    dl, 2
0x18000582a  jnz     short loc_180005840
0x18000582c  and     ecx, 0FFFFF63Eh
0x180005832  mov     eax, ebx
0x180005834  and     eax, 9C1h
0x180005839  or      ecx, eax
0x18000583b  or      ecx, 2
0x18000583e  mov     [rdi], ecx
0x180005840  mov     r8d, edx
0x180005843  and     r8d, 4
0x180005847  jnz     short loc_18000585B
0x180005849  btr     ecx, 0Ah
0x18000584d  mov     eax, ebx
0x18000584f  and     eax, 400h
0x180005854  or      ecx, eax
0x180005856  or      ecx, 4
0x180005859  mov     [rdi], ecx
0x18000585b  mov     eax, edx
0x18000585d  lock cmpxchg [rsi], ecx
0x180005861  jnz     short loc_18000581A
0x180005863  test    r8d, r8d
0x180005866  jnz     short loc_1800058C8
0x180005868  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000586e  test    eax, eax
0x180005870  jz      short loc_1800058C8
0x180005872  lea     rdx, qword_180018220
0x180005879  lea     rcx, [rsp+48h+arg_8]
0x18000587e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180005883  mov     eax, cs:dword_180018234
0x180005889  test    ebp, ebp
0x18000588b  jz      short loc_1800058BA
0x18000588d  cmp     ebp, eax
0x18000588f  jnz     short loc_1800058BA
0x180005891  mov     r8d, 10h; unsigned __int64
0x180005897  mov     [rsp+48h+var_28], 3
0x1800058a0  lea     rdx, [rsp+48h+var_28]; void *
0x1800058a5  mov     [rsp+48h+var_20], rsi
0x1800058aa  lea     rcx, qword_180018258; this
0x1800058b1  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x1800058b6  test    al, al
0x1800058b8  jnz     short loc_1800058BE
0x1800058ba  lock and dword ptr [rsi], 0FFFFFFFBh
0x1800058be  lea     rcx, [rsp+48h+arg_8]
0x1800058c3  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x1800058c8  mov     eax, [rdi]
0x1800058ca  test    al, 2
0x1800058cc  jnz     short loc_1800058DD
0x1800058ce  and     eax, 0FFFFF63Eh
0x1800058d3  and     ebx, 9C1h
0x1800058d9  or      eax, ebx
0x1800058db  mov     [rdi], eax
0x1800058dd  mov     rbx, [rsp+48h+arg_10]
0x1800058e2  mov     rax, rdi
0x1800058e5  add     rsp, 30h
0x1800058e9  pop     rdi
0x1800058ea  pop     rsi
0x1800058eb  pop     rbp
0x1800058ec  retn
```
