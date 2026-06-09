# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x18002adc0`
- end: `0x18002af00`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18002c95c`
- `0x18002d4b0`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x18002adc0`
- `0x18002b410`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae7e`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002ae7e`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Ten2Loc__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Ten2Loc__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Ten2Loc__descriptor, 0xFFFFFFFB);
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
0x18002adc0  mov     [rsp+arg_10], rbx
0x18002adc5  mov     [rsp+arg_18], rbp
0x18002adca  mov     [rsp+arg_0], rcx
0x18002adcf  push    rsi
0x18002add0  push    rdi
0x18002add1  push    r14
0x18002add3  sub     rsp, 30h
0x18002add7  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x18002adde  mov     rdi, rdx
0x18002ade1  mov     qword ptr [rdx], 0
0x18002ade8  mov     eax, [rsi]
0x18002adea  mov     [rdx], eax
0x18002adec  and     eax, 6
0x18002adef  cmp     al, 6
0x18002adf1  jz      loc_18002AEE9
0x18002adf7  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x18002adfc  lea     r8, [rsp+48h+arg_0]
0x18002ae01  mov     dword ptr [rsp+48h+arg_0], 0
0x18002ae09  lea     rdx, [rsp+48h+arg_8]
0x18002ae0e  mov     ebp, eax
0x18002ae10  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x18002ae15  mov     eax, [rdi]
0x18002ae17  mov     rbx, [rsp+48h+arg_8]
0x18002ae1c  cmp     dword ptr [rsp+48h+arg_0], 0
0x18002ae21  mov     edx, eax
0x18002ae23  mov     [rdi], eax
0x18002ae25  mov     ecx, eax
0x18002ae27  jz      short loc_18002AE42
0x18002ae29  test    dl, 2
0x18002ae2c  jnz     short loc_18002AE42
0x18002ae2e  and     ecx, 0FFFFF63Eh
0x18002ae34  mov     eax, ebx
0x18002ae36  and     eax, 9C1h
0x18002ae3b  or      ecx, eax
0x18002ae3d  or      ecx, 2
0x18002ae40  mov     [rdi], ecx
0x18002ae42  mov     r8d, edx
0x18002ae45  and     r8d, 4
0x18002ae49  jnz     short loc_18002AE5D
0x18002ae4b  btr     ecx, 0Ah
0x18002ae4f  mov     eax, ebx
0x18002ae51  and     eax, 400h
0x18002ae56  or      ecx, eax
0x18002ae58  or      ecx, 4
0x18002ae5b  mov     [rdi], ecx
0x18002ae5d  mov     eax, edx
0x18002ae5f  lock cmpxchg [rsi], ecx
0x18002ae63  jnz     short loc_18002AE1C
0x18002ae65  test    r8d, r8d
0x18002ae68  jnz     short loc_18002AED4
0x18002ae6a  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18002ae70  test    eax, eax
0x18002ae72  jz      short loc_18002AED4
0x18002ae74  lea     r14, SRWLock
0x18002ae7b  mov     rcx, r14; SRWLock
0x18002ae7e  call    cs:__imp_AcquireSRWLockExclusive
0x18002ae85  nop     dword ptr [rax+rax+00h]
0x18002ae8a  mov     eax, cs:dword_1800578F4
0x18002ae90  mov     [rsp+48h+arg_8], r14
0x18002ae95  test    ebp, ebp
0x18002ae97  jz      short loc_18002AEC6
0x18002ae99  cmp     ebp, eax
0x18002ae9b  jnz     short loc_18002AEC6
0x18002ae9d  mov     r8d, 10h; unsigned __int64
0x18002aea3  mov     [rsp+48h+var_28], 3
0x18002aeac  lea     rdx, [rsp+48h+var_28]; void *
0x18002aeb1  mov     [rsp+48h+var_20], rsi
0x18002aeb6  lea     rcx, qword_180057928; this
0x18002aebd  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x18002aec2  test    al, al
0x18002aec4  jnz     short loc_18002AECA
0x18002aec6  lock and dword ptr [rsi], 0FFFFFFFBh
0x18002aeca  lea     rcx, [rsp+48h+arg_8]
0x18002aecf  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002aed4  mov     eax, [rdi]
0x18002aed6  test    al, 2
0x18002aed8  jnz     short loc_18002AEE9
0x18002aeda  and     eax, 0FFFFF63Eh
0x18002aedf  and     ebx, 9C1h
0x18002aee5  or      eax, ebx
0x18002aee7  mov     [rdi], eax
0x18002aee9  mov     rbx, [rsp+48h+arg_10]
0x18002aeee  mov     rax, rdi
0x18002aef1  mov     rbp, [rsp+48h+arg_18]
0x18002aef6  add     rsp, 30h
0x18002aefa  pop     r14
0x18002aefc  pop     rdi
0x18002aefd  pop     rsi
0x18002aefe  retn
```
