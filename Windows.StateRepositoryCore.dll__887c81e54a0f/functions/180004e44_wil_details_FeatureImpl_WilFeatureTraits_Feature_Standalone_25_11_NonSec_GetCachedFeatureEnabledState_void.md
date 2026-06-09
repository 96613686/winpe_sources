# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x180004e44`
- end: `0x180004f6d`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `297`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180008b9c`

## callees

- `0x180003d78`
- `0x180004650`
- `0x180004944`
- `0x180004e44`
- `0x180005d00`
- `0x18000ad18`

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
      wil::AcquireSRWLockExclusive(&v16, (RTL_SRWLOCK *)qword_180018220);
      if ( !v5
        || v5 != dword_180018234
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180018258, v14, 0x10u)) )
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
0x180004e44  mov     [rsp+arg_10], rbx
0x180004e49  mov     [rsp+arg_0], rcx
0x180004e4e  push    rbp
0x180004e4f  push    rsi
0x180004e50  push    rdi
0x180004e51  sub     rsp, 30h
0x180004e55  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x180004e5c  mov     rdi, rdx
0x180004e5f  mov     qword ptr [rdx], 0
0x180004e66  mov     eax, [rsi]
0x180004e68  mov     [rdx], eax
0x180004e6a  and     eax, 6
0x180004e6d  cmp     al, 6
0x180004e6f  jz      loc_180004F5D
0x180004e75  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180004e7a  lea     r8, [rsp+48h+arg_0]
0x180004e7f  mov     dword ptr [rsp+48h+arg_0], 0
0x180004e87  lea     rdx, [rsp+48h+arg_8]
0x180004e8c  mov     ebp, eax
0x180004e8e  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x180004e93  mov     eax, [rdi]
0x180004e95  mov     rbx, [rsp+48h+arg_8]
0x180004e9a  cmp     dword ptr [rsp+48h+arg_0], 0
0x180004e9f  mov     edx, eax
0x180004ea1  mov     [rdi], eax
0x180004ea3  mov     ecx, eax
0x180004ea5  jz      short loc_180004EC0
0x180004ea7  test    dl, 2
0x180004eaa  jnz     short loc_180004EC0
0x180004eac  and     ecx, 0FFFFF63Eh
0x180004eb2  mov     eax, ebx
0x180004eb4  and     eax, 9C1h
0x180004eb9  or      ecx, eax
0x180004ebb  or      ecx, 2
0x180004ebe  mov     [rdi], ecx
0x180004ec0  mov     r8d, edx
0x180004ec3  and     r8d, 4
0x180004ec7  jnz     short loc_180004EDB
0x180004ec9  btr     ecx, 0Ah
0x180004ecd  mov     eax, ebx
0x180004ecf  and     eax, 400h
0x180004ed4  or      ecx, eax
0x180004ed6  or      ecx, 4
0x180004ed9  mov     [rdi], ecx
0x180004edb  mov     eax, edx
0x180004edd  lock cmpxchg [rsi], ecx
0x180004ee1  jnz     short loc_180004E9A
0x180004ee3  test    r8d, r8d
0x180004ee6  jnz     short loc_180004F48
0x180004ee8  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180004eee  test    eax, eax
0x180004ef0  jz      short loc_180004F48
0x180004ef2  lea     rdx, qword_180018220
0x180004ef9  lea     rcx, [rsp+48h+arg_8]
0x180004efe  call    ?AcquireSRWLockExclusive@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@1@PEAU_RTL_SRWLOCK@@@Z; wil::AcquireSRWLockExclusive(_RTL_SRWLOCK *)
0x180004f03  mov     eax, cs:dword_180018234
0x180004f09  test    ebp, ebp
0x180004f0b  jz      short loc_180004F3A
0x180004f0d  cmp     ebp, eax
0x180004f0f  jnz     short loc_180004F3A
0x180004f11  mov     r8d, 10h; unsigned __int64
0x180004f17  mov     [rsp+48h+var_28], 3
0x180004f20  lea     rdx, [rsp+48h+var_28]; void *
0x180004f25  mov     [rsp+48h+var_20], rsi
0x180004f2a  lea     rcx, qword_180018258; this
0x180004f31  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180004f36  test    al, al
0x180004f38  jnz     short loc_180004F3E
0x180004f3a  lock and dword ptr [rsi], 0FFFFFFFBh
0x180004f3e  lea     rcx, [rsp+48h+arg_8]
0x180004f43  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180004f48  mov     eax, [rdi]
0x180004f4a  test    al, 2
0x180004f4c  jnz     short loc_180004F5D
0x180004f4e  and     eax, 0FFFFF63Eh
0x180004f53  and     ebx, 9C1h
0x180004f59  or      eax, ebx
0x180004f5b  mov     [rdi], eax
0x180004f5d  mov     rbx, [rsp+48h+arg_10]
0x180004f62  mov     rax, rdi
0x180004f65  add     rsp, 30h
0x180004f69  pop     rdi
0x180004f6a  pop     rsi
0x180004f6b  pop     rbp
0x180004f6c  retn
```
