# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180004f74`
- end: `0x18000509d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008c20`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x180004f74`
- `0x180005d74`
- `0x18000ad18`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_Standalone_26_01_NonSec__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      wil::AcquireSRWLockExclusive(&v16, &unk_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)&unk_180018258, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, 0xFFFFFFFB);
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
0x180004f74  mov     [rsp+arg_10], rbx
0x180004f79  mov     [rsp+arg_0], rcx
0x180004f7e  push    rbp
0x180004f7f  push    rsi
0x180004f80  push    rdi
0x180004f81  sub     rsp, 30h
0x180004f85  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x180004f8c  mov     rdi, rdx
0x180004f8f  mov     qword ptr [rdx], 0
0x180004f96  mov     eax, [rsi]
0x180004f98  mov     [rdx], eax
0x180004f9a  and     eax, 6
0x180004f9d  cmp     al, 6
0x180004f9f  jz      loc_18000508D
0x180004fa5  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004faa  lea     r8, [rsp+48h+arg_0]
0x180004faf  mov     dword ptr [rsp+48h+arg_0], 0
0x180004fb7  lea     rdx, [rsp+48h+arg_8]
0x180004fbc  mov     ebp, eax
0x180004fbe  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180004fc3  mov     eax, [rdi]
0x180004fc5  mov     rbx, [rsp+48h+arg_8]
0x180004fca  cmp     dword ptr [rsp+48h+arg_0], 0
0x180004fcf  mov     edx, eax
0x180004fd1  mov     [rdi], eax
0x180004fd3  mov     ecx, eax
0x180004fd5  jz      short loc_180004FF0
0x180004fd7  test    dl, 2
0x180004fda  jnz     short loc_180004FF0
0x180004fdc  and     ecx, 0FFFFF63Eh
0x180004fe2  mov     eax, ebx
0x180004fe4  and     eax, 9C1h
0x180004fe9  or      ecx, eax
0x180004feb  or      ecx, 2
0x180004fee  mov     [rdi], ecx
0x180004ff0  mov     r8d, edx
0x180004ff3  and     r8d, 4
0x180004ff7  jnz     short loc_18000500B
0x180004ff9  btr     ecx, 0Ah
0x180004ffd  mov     eax, ebx
0x180004fff  and     eax, 400h
0x180005004  or      ecx, eax
0x180005006  or      ecx, 4
0x180005009  mov     [rdi], ecx
0x18000500b  mov     eax, edx
0x18000500d  lock cmpxchg [rsi], ecx
0x180005011  jnz     short loc_180004FCA
0x180005013  test    r8d, r8d
0x180005016  jnz     short loc_180005078
0x180005018  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x18000501e  test    eax, eax
0x180005020  jz      short loc_180005078
0x180005022  lea     rdx, unk_180018220
0x180005029  lea     rcx, [rsp+48h+arg_8]
0x18000502e  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180005033  mov     eax, cs:dword_180018234
0x180005039  test    ebp, ebp
0x18000503b  jz      short loc_18000506A
0x18000503d  cmp     ebp, eax
0x18000503f  jnz     short loc_18000506A
0x180005041  mov     r8d, 10h; unsigned __int64
0x180005047  mov     [rsp+48h+var_28], 3
0x180005050  lea     rdx, [rsp+48h+var_28]; void *
0x180005055  mov     [rsp+48h+var_20], rsi
0x18000505a  lea     rcx, unk_180018258; this
0x180005061  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180005066  test    al, al
0x180005068  jnz     short loc_18000506E
0x18000506a  lock and dword ptr [rsi], 0FFFFFFFBh
0x18000506e  lea     rcx, [rsp+48h+arg_8]
0x180005073  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180005078  mov     eax, [rdi]
0x18000507a  test    al, 2
0x18000507c  jnz     short loc_18000508D
0x18000507e  and     eax, 0FFFFF63Eh
0x180005083  and     ebx, 9C1h
0x180005089  or      eax, ebx
0x18000508b  mov     [rdi], eax
0x18000508d  mov     rbx, [rsp+48h+arg_10]
0x180005092  mov     rax, rdi
0x180005095  add     rsp, 30h
0x180005099  pop     rdi
0x18000509a  pop     rsi
0x18000509b  pop     rbp
0x18000509c  retn
```
