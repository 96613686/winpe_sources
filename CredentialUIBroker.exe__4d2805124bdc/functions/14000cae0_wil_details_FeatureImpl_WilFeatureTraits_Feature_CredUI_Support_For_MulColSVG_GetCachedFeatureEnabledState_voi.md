# wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetCachedFeatureEnabledState(void)

- ea: `0x14000cae0`
- end: `0x14000cc19`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x140013244`
- `0x140018f1c`

## callees

- `0x140009158`
- `0x14000b9f4`
- `0x14000cae0`
- `0x14000d154`
- `0x14001a930`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000cb9e`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000cb9e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_CredUI_Support_For_MulColSVG__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_CredUI_Support_For_MulColSVG__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange(
             (volatile signed __int32 *)Feature_CredUI_Support_For_MulColSVG__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_14002A814
        || (v14[0] = 3,
            v14[1] = Feature_CredUI_Support_For_MulColSVG__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002A838, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_CredUI_Support_For_MulColSVG__descriptor, 0xFFFFFFFB);
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
0x14000cae0  mov     [rsp+arg_10], rbx
0x14000cae5  mov     [rsp+arg_18], rbp
0x14000caea  mov     [rsp+arg_0], rcx
0x14000caef  push    rsi
0x14000caf0  push    rdi
0x14000caf1  push    r14
0x14000caf3  sub     rsp, 30h
0x14000caf7  mov     rsi, cs:Feature_CredUI_Support_For_MulColSVG__descriptor
0x14000cafe  mov     rdi, rdx
0x14000cb01  mov     qword ptr [rdx], 0
0x14000cb08  mov     eax, [rsi]
0x14000cb0a  mov     [rdx], eax
0x14000cb0c  and     eax, 6
0x14000cb0f  cmp     al, 6
0x14000cb11  jz      loc_14000CC03
0x14000cb17  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000cb1c  lea     r8, [rsp+48h+arg_0]
0x14000cb21  mov     dword ptr [rsp+48h+arg_0], 0
0x14000cb29  lea     rdx, [rsp+48h+arg_8]
0x14000cb2e  mov     ebp, eax
0x14000cb30  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_CredUI_Support_For_MulColSVG>::GetCurrentFeatureEnabledState(int *)
0x14000cb35  mov     eax, [rdi]
0x14000cb37  mov     rbx, [rsp+48h+arg_8]
0x14000cb3c  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000cb41  mov     edx, eax
0x14000cb43  mov     [rdi], eax
0x14000cb45  mov     ecx, eax
0x14000cb47  jz      short loc_14000CB62
0x14000cb49  test    dl, 2
0x14000cb4c  jnz     short loc_14000CB62
0x14000cb4e  and     ecx, 0FFFFF63Eh
0x14000cb54  mov     eax, ebx
0x14000cb56  and     eax, 9C1h
0x14000cb5b  or      ecx, eax
0x14000cb5d  or      ecx, 2
0x14000cb60  mov     [rdi], ecx
0x14000cb62  mov     r8d, edx
0x14000cb65  and     r8d, 4
0x14000cb69  jnz     short loc_14000CB7D
0x14000cb6b  btr     ecx, 0Ah
0x14000cb6f  mov     eax, ebx
0x14000cb71  and     eax, 400h
0x14000cb76  or      ecx, eax
0x14000cb78  or      ecx, 4
0x14000cb7b  mov     [rdi], ecx
0x14000cb7d  mov     eax, edx
0x14000cb7f  lock cmpxchg [rsi], ecx
0x14000cb83  jnz     short loc_14000CB3C
0x14000cb85  test    r8d, r8d
0x14000cb88  jnz     short loc_14000CBEE
0x14000cb8a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000cb90  test    eax, eax
0x14000cb92  jz      short loc_14000CBEE
0x14000cb94  lea     r14, SRWLock
0x14000cb9b  mov     rcx, r14; SRWLock
0x14000cb9e  call    cs:__imp_AcquireSRWLockExclusive
0x14000cba4  mov     eax, cs:dword_14002A814
0x14000cbaa  mov     [rsp+48h+arg_8], r14
0x14000cbaf  test    ebp, ebp
0x14000cbb1  jz      short loc_14000CBE0
0x14000cbb3  cmp     ebp, eax
0x14000cbb5  jnz     short loc_14000CBE0
0x14000cbb7  mov     r8d, 10h; unsigned __int64
0x14000cbbd  mov     [rsp+48h+var_28], 3
0x14000cbc6  lea     rdx, [rsp+48h+var_28]; void *
0x14000cbcb  mov     [rsp+48h+var_20], rsi
0x14000cbd0  lea     rcx, qword_14002A838; this
0x14000cbd7  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000cbdc  test    al, al
0x14000cbde  jnz     short loc_14000CBE4
0x14000cbe0  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000cbe4  lea     rcx, [rsp+48h+arg_8]
0x14000cbe9  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000cbee  mov     eax, [rdi]
0x14000cbf0  test    al, 2
0x14000cbf2  jnz     short loc_14000CC03
0x14000cbf4  and     eax, 0FFFFF63Eh
0x14000cbf9  and     ebx, 9C1h
0x14000cbff  or      eax, ebx
0x14000cc01  mov     [rdi], eax
0x14000cc03  mov     rbx, [rsp+48h+arg_10]
0x14000cc08  mov     rax, rdi
0x14000cc0b  mov     rbp, [rsp+48h+arg_18]
0x14000cc10  add     rsp, 30h
0x14000cc14  pop     r14
0x14000cc16  pop     rdi
0x14000cc17  pop     rsi
0x14000cc18  retn
```
