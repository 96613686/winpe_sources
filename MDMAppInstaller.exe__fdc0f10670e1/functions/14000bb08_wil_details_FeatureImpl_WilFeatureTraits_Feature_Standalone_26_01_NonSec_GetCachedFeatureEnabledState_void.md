# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x14000bb08`
- end: `0x14000bc41`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fe10`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000bb08`
- `0x14000c600`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000bbc6`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000bbc6`

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
  RTL_SRWLOCK *v16; // [rsp+58h] [rbp+10h] BYREF

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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_Standalone_26_01_NonSec__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_26_01_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
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
0x14000bb08  mov     [rsp+arg_10], rbx
0x14000bb0d  mov     [rsp+arg_18], rbp
0x14000bb12  mov     [rsp+arg_0], rcx
0x14000bb17  push    rsi
0x14000bb18  push    rdi
0x14000bb19  push    r14
0x14000bb1b  sub     rsp, 30h
0x14000bb1f  mov     rsi, cs:Feature_Standalone_26_01_NonSec__descriptor
0x14000bb26  mov     rdi, rdx
0x14000bb29  mov     qword ptr [rdx], 0
0x14000bb30  mov     eax, [rsi]
0x14000bb32  mov     [rdx], eax
0x14000bb34  and     eax, 6
0x14000bb37  cmp     al, 6
0x14000bb39  jz      loc_14000BC2B
0x14000bb3f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000bb44  lea     r8, [rsp+48h+arg_0]
0x14000bb49  mov     dword ptr [rsp+48h+arg_0], 0
0x14000bb51  lea     rdx, [rsp+48h+arg_8]
0x14000bb56  mov     ebp, eax
0x14000bb58  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_26_01_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_26_01_NonSec>::GetCurrentFeatureEnabledState(int *)
0x14000bb5d  mov     eax, [rdi]
0x14000bb5f  mov     rbx, [rsp+48h+arg_8]
0x14000bb64  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000bb69  mov     edx, eax
0x14000bb6b  mov     [rdi], eax
0x14000bb6d  mov     ecx, eax
0x14000bb6f  jz      short loc_14000BB8A
0x14000bb71  test    dl, 2
0x14000bb74  jnz     short loc_14000BB8A
0x14000bb76  and     ecx, 0FFFFF63Eh
0x14000bb7c  mov     eax, ebx
0x14000bb7e  and     eax, 9C1h
0x14000bb83  or      ecx, eax
0x14000bb85  or      ecx, 2
0x14000bb88  mov     [rdi], ecx
0x14000bb8a  mov     r8d, edx
0x14000bb8d  and     r8d, 4
0x14000bb91  jnz     short loc_14000BBA5
0x14000bb93  btr     ecx, 0Ah
0x14000bb97  mov     eax, ebx
0x14000bb99  and     eax, 400h
0x14000bb9e  or      ecx, eax
0x14000bba0  or      ecx, 4
0x14000bba3  mov     [rdi], ecx
0x14000bba5  mov     eax, edx
0x14000bba7  lock cmpxchg [rsi], ecx
0x14000bbab  jnz     short loc_14000BB64
0x14000bbad  test    r8d, r8d
0x14000bbb0  jnz     short loc_14000BC16
0x14000bbb2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000bbb8  test    eax, eax
0x14000bbba  jz      short loc_14000BC16
0x14000bbbc  lea     r14, stru_14002BCD0
0x14000bbc3  mov     rcx, r14; SRWLock
0x14000bbc6  call    cs:__imp_AcquireSRWLockExclusive
0x14000bbcc  mov     eax, cs:dword_14002BCE4
0x14000bbd2  mov     [rsp+48h+arg_8], r14
0x14000bbd7  test    ebp, ebp
0x14000bbd9  jz      short loc_14000BC08
0x14000bbdb  cmp     ebp, eax
0x14000bbdd  jnz     short loc_14000BC08
0x14000bbdf  mov     r8d, 10h; unsigned __int64
0x14000bbe5  mov     [rsp+48h+var_28], 3
0x14000bbee  lea     rdx, [rsp+48h+var_28]; void *
0x14000bbf3  mov     [rsp+48h+var_20], rsi
0x14000bbf8  lea     rcx, qword_14002BD08; this
0x14000bbff  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000bc04  test    al, al
0x14000bc06  jnz     short loc_14000BC0C
0x14000bc08  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000bc0c  lea     rcx, [rsp+48h+arg_8]
0x14000bc11  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000bc16  mov     eax, [rdi]
0x14000bc18  test    al, 2
0x14000bc1a  jnz     short loc_14000BC2B
0x14000bc1c  and     eax, 0FFFFF63Eh
0x14000bc21  and     ebx, 9C1h
0x14000bc27  or      eax, ebx
0x14000bc29  mov     [rdi], eax
0x14000bc2b  mov     rbx, [rsp+48h+arg_10]
0x14000bc30  mov     rax, rdi
0x14000bc33  mov     rbp, [rsp+48h+arg_18]
0x14000bc38  add     rsp, 30h
0x14000bc3c  pop     r14
0x14000bc3e  pop     rdi
0x14000bc3f  pop     rsi
0x14000bc40  retn
```
