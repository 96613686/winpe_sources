# wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(void)

- ea: `0x180016e2c`
- end: `0x180016f6c`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `320`
- prototype: ``
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001d17c`
- `0x180020f60`

## callees

- `0x180008fc0`
- `0x180009790`
- `0x18000c1f4`
- `0x180016e2c`
- `0x1800173d8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016eea`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180016eea`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_TestAccPerf__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(v6, &v16, &v15);
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
      v7 = _InterlockedCompareExchange((volatile signed __int32 *)Feature_TestAccPerf__descriptor, v11, v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_1800578F4
        || (v14[0] = 3,
            v14[1] = Feature_TestAccPerf__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180057928, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_TestAccPerf__descriptor, 0xFFFFFFFB);
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
0x180016e2c  mov     [rsp+arg_10], rbx
0x180016e31  mov     [rsp+arg_18], rbp
0x180016e36  mov     [rsp+arg_0], rcx
0x180016e3b  push    rsi
0x180016e3c  push    rdi
0x180016e3d  push    r14
0x180016e3f  sub     rsp, 30h
0x180016e43  mov     rsi, cs:Feature_TestAccPerf__descriptor
0x180016e4a  mov     rdi, rdx
0x180016e4d  mov     qword ptr [rdx], 0
0x180016e54  mov     eax, [rsi]
0x180016e56  mov     [rdx], eax
0x180016e58  and     eax, 6
0x180016e5b  cmp     al, 6
0x180016e5d  jz      loc_180016F55
0x180016e63  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180016e68  lea     r8, [rsp+48h+arg_0]
0x180016e6d  mov     dword ptr [rsp+48h+arg_0], 0
0x180016e75  lea     rdx, [rsp+48h+arg_8]
0x180016e7a  mov     ebp, eax
0x180016e7c  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TestAccPerf@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TestAccPerf>::GetCurrentFeatureEnabledState(int *)
0x180016e81  mov     eax, [rdi]
0x180016e83  mov     rbx, [rsp+48h+arg_8]
0x180016e88  cmp     dword ptr [rsp+48h+arg_0], 0
0x180016e8d  mov     edx, eax
0x180016e8f  mov     [rdi], eax
0x180016e91  mov     ecx, eax
0x180016e93  jz      short loc_180016EAE
0x180016e95  test    dl, 2
0x180016e98  jnz     short loc_180016EAE
0x180016e9a  and     ecx, 0FFFFF63Eh
0x180016ea0  mov     eax, ebx
0x180016ea2  and     eax, 9C1h
0x180016ea7  or      ecx, eax
0x180016ea9  or      ecx, 2
0x180016eac  mov     [rdi], ecx
0x180016eae  mov     r8d, edx
0x180016eb1  and     r8d, 4
0x180016eb5  jnz     short loc_180016EC9
0x180016eb7  btr     ecx, 0Ah
0x180016ebb  mov     eax, ebx
0x180016ebd  and     eax, 400h
0x180016ec2  or      ecx, eax
0x180016ec4  or      ecx, 4
0x180016ec7  mov     [rdi], ecx
0x180016ec9  mov     eax, edx
0x180016ecb  lock cmpxchg [rsi], ecx
0x180016ecf  jnz     short loc_180016E88
0x180016ed1  test    r8d, r8d
0x180016ed4  jnz     short loc_180016F40
0x180016ed6  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180016edc  test    eax, eax
0x180016ede  jz      short loc_180016F40
0x180016ee0  lea     r14, SRWLock
0x180016ee7  mov     rcx, r14; SRWLock
0x180016eea  call    cs:__imp_AcquireSRWLockExclusive
0x180016ef1  nop     dword ptr [rax+rax+00h]
0x180016ef6  mov     eax, cs:dword_1800578F4
0x180016efc  mov     [rsp+48h+arg_8], r14
0x180016f01  test    ebp, ebp
0x180016f03  jz      short loc_180016F32
0x180016f05  cmp     ebp, eax
0x180016f07  jnz     short loc_180016F32
0x180016f09  mov     r8d, 10h; unsigned __int64
0x180016f0f  mov     [rsp+48h+var_28], 3
0x180016f18  lea     rdx, [rsp+48h+var_28]; void *
0x180016f1d  mov     [rsp+48h+var_20], rsi
0x180016f22  lea     rcx, qword_180057928; this
0x180016f29  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180016f2e  test    al, al
0x180016f30  jnz     short loc_180016F36
0x180016f32  lock and dword ptr [rsi], 0FFFFFFFBh
0x180016f36  lea     rcx, [rsp+48h+arg_8]
0x180016f3b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180016f40  mov     eax, [rdi]
0x180016f42  test    al, 2
0x180016f44  jnz     short loc_180016F55
0x180016f46  and     eax, 0FFFFF63Eh
0x180016f4b  and     ebx, 9C1h
0x180016f51  or      eax, ebx
0x180016f53  mov     [rdi], eax
0x180016f55  mov     rbx, [rsp+48h+arg_10]
0x180016f5a  mov     rax, rdi
0x180016f5d  mov     rbp, [rsp+48h+arg_18]
0x180016f62  add     rsp, 30h
0x180016f66  pop     r14
0x180016f68  pop     rdi
0x180016f69  pop     rsi
0x180016f6a  retn
```
