# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x180015974`
- end: `0x180015aad`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001b53c`
- `0x18001cfe8`

## callees

- `0x18000460c`
- `0x180005ac4`
- `0x18000b230`
- `0x180015974`
- `0x18001751c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a32`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180015a32`

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
        || v5 != dword_18002EED4
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_18002EEF8, v14, 0x10u)) )
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
0x180015974  mov     [rsp+arg_10], rbx
0x180015979  mov     [rsp+arg_18], rbp
0x18001597e  mov     [rsp+arg_0], rcx
0x180015983  push    rsi
0x180015984  push    rdi
0x180015985  push    r14
0x180015987  sub     rsp, 30h
0x18001598b  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x180015992  mov     rdi, rdx
0x180015995  mov     qword ptr [rdx], 0
0x18001599c  mov     eax, [rsi]
0x18001599e  mov     [rdx], eax
0x1800159a0  and     eax, 6
0x1800159a3  cmp     al, 6
0x1800159a5  jz      loc_180015A97
0x1800159ab  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x1800159b0  lea     r8, [rsp+48h+arg_0]
0x1800159b5  mov     dword ptr [rsp+48h+arg_0], 0
0x1800159bd  lea     rdx, [rsp+48h+arg_8]
0x1800159c2  mov     ebp, eax
0x1800159c4  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x1800159c9  mov     eax, [rdi]
0x1800159cb  mov     rbx, [rsp+48h+arg_8]
0x1800159d0  cmp     dword ptr [rsp+48h+arg_0], 0
0x1800159d5  mov     edx, eax
0x1800159d7  mov     [rdi], eax
0x1800159d9  mov     ecx, eax
0x1800159db  jz      short loc_1800159F6
0x1800159dd  test    dl, 2
0x1800159e0  jnz     short loc_1800159F6
0x1800159e2  and     ecx, 0FFFFF63Eh
0x1800159e8  mov     eax, ebx
0x1800159ea  and     eax, 9C1h
0x1800159ef  or      ecx, eax
0x1800159f1  or      ecx, 2
0x1800159f4  mov     [rdi], ecx
0x1800159f6  mov     r8d, edx
0x1800159f9  and     r8d, 4
0x1800159fd  jnz     short loc_180015A11
0x1800159ff  btr     ecx, 0Ah
0x180015a03  mov     eax, ebx
0x180015a05  and     eax, 400h
0x180015a0a  or      ecx, eax
0x180015a0c  or      ecx, 4
0x180015a0f  mov     [rdi], ecx
0x180015a11  mov     eax, edx
0x180015a13  lock cmpxchg [rsi], ecx
0x180015a17  jnz     short loc_1800159D0
0x180015a19  test    r8d, r8d
0x180015a1c  jnz     short loc_180015A82
0x180015a1e  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180015a24  test    eax, eax
0x180015a26  jz      short loc_180015A82
0x180015a28  lea     r14, SRWLock
0x180015a2f  mov     rcx, r14; SRWLock
0x180015a32  call    cs:__imp_AcquireSRWLockExclusive
0x180015a38  mov     eax, cs:dword_18002EED4
0x180015a3e  mov     [rsp+48h+arg_8], r14
0x180015a43  test    ebp, ebp
0x180015a45  jz      short loc_180015A74
0x180015a47  cmp     ebp, eax
0x180015a49  jnz     short loc_180015A74
0x180015a4b  mov     r8d, 10h; unsigned __int64
0x180015a51  mov     [rsp+48h+var_28], 3
0x180015a5a  lea     rdx, [rsp+48h+var_28]; void *
0x180015a5f  mov     [rsp+48h+var_20], rsi
0x180015a64  lea     rcx, qword_18002EEF8; this
0x180015a6b  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180015a70  test    al, al
0x180015a72  jnz     short loc_180015A78
0x180015a74  lock and dword ptr [rsi], 0FFFFFFFBh
0x180015a78  lea     rcx, [rsp+48h+arg_8]
0x180015a7d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180015a82  mov     eax, [rdi]
0x180015a84  test    al, 2
0x180015a86  jnz     short loc_180015A97
0x180015a88  and     eax, 0FFFFF63Eh
0x180015a8d  and     ebx, 9C1h
0x180015a93  or      eax, ebx
0x180015a95  mov     [rdi], eax
0x180015a97  mov     rbx, [rsp+48h+arg_10]
0x180015a9c  mov     rax, rdi
0x180015a9f  mov     rbp, [rsp+48h+arg_18]
0x180015aa4  add     rsp, 30h
0x180015aa8  pop     r14
0x180015aaa  pop     rdi
0x180015aab  pop     rsi
0x180015aac  retn
```
