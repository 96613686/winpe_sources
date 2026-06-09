# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCachedFeatureEnabledState(void)

- ea: `0x14000b9c8`
- end: `0x14000bb01`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000fd8c`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000b9c8`
- `0x14000c584`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ba86`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000ba86`

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
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 3,
            v14[1] = Feature_Standalone_25_11_NonSec__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
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
0x14000b9c8  mov     [rsp+arg_10], rbx
0x14000b9cd  mov     [rsp+arg_18], rbp
0x14000b9d2  mov     [rsp+arg_0], rcx
0x14000b9d7  push    rsi
0x14000b9d8  push    rdi
0x14000b9d9  push    r14
0x14000b9db  sub     rsp, 30h
0x14000b9df  mov     rsi, cs:Feature_Standalone_25_11_NonSec__descriptor
0x14000b9e6  mov     rdi, rdx
0x14000b9e9  mov     qword ptr [rdx], 0
0x14000b9f0  mov     eax, [rsi]
0x14000b9f2  mov     [rdx], eax
0x14000b9f4  and     eax, 6
0x14000b9f7  cmp     al, 6
0x14000b9f9  jz      loc_14000BAEB
0x14000b9ff  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000ba04  lea     r8, [rsp+48h+arg_0]
0x14000ba09  mov     dword ptr [rsp+48h+arg_0], 0
0x14000ba11  lea     rdx, [rsp+48h+arg_8]
0x14000ba16  mov     ebp, eax
0x14000ba18  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Standalone_25_11_NonSec@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Standalone_25_11_NonSec>::GetCurrentFeatureEnabledState(int *)
0x14000ba1d  mov     eax, [rdi]
0x14000ba1f  mov     rbx, [rsp+48h+arg_8]
0x14000ba24  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000ba29  mov     edx, eax
0x14000ba2b  mov     [rdi], eax
0x14000ba2d  mov     ecx, eax
0x14000ba2f  jz      short loc_14000BA4A
0x14000ba31  test    dl, 2
0x14000ba34  jnz     short loc_14000BA4A
0x14000ba36  and     ecx, 0FFFFF63Eh
0x14000ba3c  mov     eax, ebx
0x14000ba3e  and     eax, 9C1h
0x14000ba43  or      ecx, eax
0x14000ba45  or      ecx, 2
0x14000ba48  mov     [rdi], ecx
0x14000ba4a  mov     r8d, edx
0x14000ba4d  and     r8d, 4
0x14000ba51  jnz     short loc_14000BA65
0x14000ba53  btr     ecx, 0Ah
0x14000ba57  mov     eax, ebx
0x14000ba59  and     eax, 400h
0x14000ba5e  or      ecx, eax
0x14000ba60  or      ecx, 4
0x14000ba63  mov     [rdi], ecx
0x14000ba65  mov     eax, edx
0x14000ba67  lock cmpxchg [rsi], ecx
0x14000ba6b  jnz     short loc_14000BA24
0x14000ba6d  test    r8d, r8d
0x14000ba70  jnz     short loc_14000BAD6
0x14000ba72  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000ba78  test    eax, eax
0x14000ba7a  jz      short loc_14000BAD6
0x14000ba7c  lea     r14, stru_14002BCD0
0x14000ba83  mov     rcx, r14; SRWLock
0x14000ba86  call    cs:__imp_AcquireSRWLockExclusive
0x14000ba8c  mov     eax, cs:dword_14002BCE4
0x14000ba92  mov     [rsp+48h+arg_8], r14
0x14000ba97  test    ebp, ebp
0x14000ba99  jz      short loc_14000BAC8
0x14000ba9b  cmp     ebp, eax
0x14000ba9d  jnz     short loc_14000BAC8
0x14000ba9f  mov     r8d, 10h; unsigned __int64
0x14000baa5  mov     [rsp+48h+var_28], 3
0x14000baae  lea     rdx, [rsp+48h+var_28]; void *
0x14000bab3  mov     [rsp+48h+var_20], rsi
0x14000bab8  lea     rcx, qword_14002BD08; this
0x14000babf  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000bac4  test    al, al
0x14000bac6  jnz     short loc_14000BACC
0x14000bac8  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000bacc  lea     rcx, [rsp+48h+arg_8]
0x14000bad1  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000bad6  mov     eax, [rdi]
0x14000bad8  test    al, 2
0x14000bada  jnz     short loc_14000BAEB
0x14000badc  and     eax, 0FFFFF63Eh
0x14000bae1  and     ebx, 9C1h
0x14000bae7  or      eax, ebx
0x14000bae9  mov     [rdi], eax
0x14000baeb  mov     rbx, [rsp+48h+arg_10]
0x14000baf0  mov     rax, rdi
0x14000baf3  mov     rbp, [rsp+48h+arg_18]
0x14000baf8  add     rsp, 30h
0x14000bafc  pop     r14
0x14000bafe  pop     rdi
0x14000baff  pop     rsi
0x14000bb00  retn
```
