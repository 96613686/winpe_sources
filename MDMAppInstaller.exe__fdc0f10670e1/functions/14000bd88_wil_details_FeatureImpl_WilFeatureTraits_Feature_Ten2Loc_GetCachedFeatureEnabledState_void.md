# wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCachedFeatureEnabledState(void)

- ea: `0x14000bd88`
- end: `0x14000bec1`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x14000ff18`
- `0x140011ba0`

## callees

- `0x1400092f0`
- `0x14000b36c`
- `0x14000bd88`
- `0x14000c6f8`
- `0x140012af8`

## import_xrefs

- `KERNEL32!AcquireSRWLockExclusive` at `0x14000be46`
- `KERNEL32!AcquireSRWLockExclusive` at `0x14000be46`

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
      AcquireSRWLockExclusive(&stru_14002BCD0);
      v16 = &stru_14002BCD0;
      if ( !v5
        || v5 != dword_14002BCE4
        || (v14[0] = 3,
            v14[1] = Feature_Ten2Loc__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_14002BD08, v14, 0x10u)) )
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
0x14000bd88  mov     [rsp+arg_10], rbx
0x14000bd8d  mov     [rsp+arg_18], rbp
0x14000bd92  mov     [rsp+arg_0], rcx
0x14000bd97  push    rsi
0x14000bd98  push    rdi
0x14000bd99  push    r14
0x14000bd9b  sub     rsp, 30h
0x14000bd9f  mov     rsi, cs:Feature_Ten2Loc__descriptor
0x14000bda6  mov     rdi, rdx
0x14000bda9  mov     qword ptr [rdx], 0
0x14000bdb0  mov     eax, [rsi]
0x14000bdb2  mov     [rdx], eax
0x14000bdb4  and     eax, 6
0x14000bdb7  cmp     al, 6
0x14000bdb9  jz      loc_14000BEAB
0x14000bdbf  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x14000bdc4  lea     r8, [rsp+48h+arg_0]
0x14000bdc9  mov     dword ptr [rsp+48h+arg_0], 0
0x14000bdd1  lea     rdx, [rsp+48h+arg_8]
0x14000bdd6  mov     ebp, eax
0x14000bdd8  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_Ten2Loc@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Ten2Loc>::GetCurrentFeatureEnabledState(int *)
0x14000bddd  mov     eax, [rdi]
0x14000bddf  mov     rbx, [rsp+48h+arg_8]
0x14000bde4  cmp     dword ptr [rsp+48h+arg_0], 0
0x14000bde9  mov     edx, eax
0x14000bdeb  mov     [rdi], eax
0x14000bded  mov     ecx, eax
0x14000bdef  jz      short loc_14000BE0A
0x14000bdf1  test    dl, 2
0x14000bdf4  jnz     short loc_14000BE0A
0x14000bdf6  and     ecx, 0FFFFF63Eh
0x14000bdfc  mov     eax, ebx
0x14000bdfe  and     eax, 9C1h
0x14000be03  or      ecx, eax
0x14000be05  or      ecx, 2
0x14000be08  mov     [rdi], ecx
0x14000be0a  mov     r8d, edx
0x14000be0d  and     r8d, 4
0x14000be11  jnz     short loc_14000BE25
0x14000be13  btr     ecx, 0Ah
0x14000be17  mov     eax, ebx
0x14000be19  and     eax, 400h
0x14000be1e  or      ecx, eax
0x14000be20  or      ecx, 4
0x14000be23  mov     [rdi], ecx
0x14000be25  mov     eax, edx
0x14000be27  lock cmpxchg [rsi], ecx
0x14000be2b  jnz     short loc_14000BDE4
0x14000be2d  test    r8d, r8d
0x14000be30  jnz     short loc_14000BE96
0x14000be32  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x14000be38  test    eax, eax
0x14000be3a  jz      short loc_14000BE96
0x14000be3c  lea     r14, stru_14002BCD0
0x14000be43  mov     rcx, r14; SRWLock
0x14000be46  call    cs:__imp_AcquireSRWLockExclusive
0x14000be4c  mov     eax, cs:dword_14002BCE4
0x14000be52  mov     [rsp+48h+arg_8], r14
0x14000be57  test    ebp, ebp
0x14000be59  jz      short loc_14000BE88
0x14000be5b  cmp     ebp, eax
0x14000be5d  jnz     short loc_14000BE88
0x14000be5f  mov     r8d, 10h; unsigned __int64
0x14000be65  mov     [rsp+48h+var_28], 3
0x14000be6e  lea     rdx, [rsp+48h+var_28]; void *
0x14000be73  mov     [rsp+48h+var_20], rsi
0x14000be78  lea     rcx, qword_14002BD08; this
0x14000be7f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x14000be84  test    al, al
0x14000be86  jnz     short loc_14000BE8C
0x14000be88  lock and dword ptr [rsi], 0FFFFFFFBh
0x14000be8c  lea     rcx, [rsp+48h+arg_8]
0x14000be91  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x14000be96  mov     eax, [rdi]
0x14000be98  test    al, 2
0x14000be9a  jnz     short loc_14000BEAB
0x14000be9c  and     eax, 0FFFFF63Eh
0x14000bea1  and     ebx, 9C1h
0x14000bea7  or      eax, ebx
0x14000bea9  mov     [rdi], eax
0x14000beab  mov     rbx, [rsp+48h+arg_10]
0x14000beb0  mov     rax, rdi
0x14000beb3  mov     rbp, [rsp+48h+arg_18]
0x14000beb8  add     rsp, 30h
0x14000bebc  pop     r14
0x14000bebe  pop     rdi
0x14000bebf  pop     rsi
0x14000bec0  retn
```
