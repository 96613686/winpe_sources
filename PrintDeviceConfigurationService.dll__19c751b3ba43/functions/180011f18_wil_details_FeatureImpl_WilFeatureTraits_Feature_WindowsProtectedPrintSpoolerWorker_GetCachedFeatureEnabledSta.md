# wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCachedFeatureEnabledState(void)

- ea: `0x180011f18`
- end: `0x180012051`
- name: `?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ`
- size: `313`
- prototype: `_QWORD *__fastcall(wil::details *, _QWORD *)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180012420`
- `0x180014114`

## callees

- `0x180004e64`
- `0x180005a7c`
- `0x180009f20`
- `0x180011f18`
- `0x1800120e0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011fd6`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x180011fd6`

## pseudocode

```c
_QWORD *__fastcall wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCachedFeatureEnabledState(
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
  v3 = *(_DWORD *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor;
  *(_DWORD *)a2 = *(_DWORD *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor;
  if ( (v3 & 6) != 6 )
  {
    v4 = wil::details::EnsureSubscribedToFeatureConfigurationChanges(a1);
    LODWORD(v15) = 0;
    v5 = v4;
    wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(
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
             (volatile signed __int32 *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor,
             v11,
             v7);
    }
    while ( v10 != v7 );
    if ( !v12 && wil::details::g_enabledStateManager )
    {
      AcquireSRWLockExclusive(&SRWLock);
      v16 = &SRWLock;
      if ( !v5
        || v5 != dword_180024B2C
        || (v14[0] = 3,
            v14[1] = Feature_WindowsProtectedPrintSpoolerWorker__descriptor,
            !wil::details_abi::heap_buffer::push_back((wil::details_abi::heap_buffer *)qword_180024B50, v14, 0x10u)) )
      {
        _InterlockedAnd((volatile signed __int32 *)Feature_WindowsProtectedPrintSpoolerWorker__descriptor, 0xFFFFFFFB);
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
0x180011f18  mov     [rsp+arg_10], rbx
0x180011f1d  mov     [rsp+arg_18], rbp
0x180011f22  mov     [rsp+arg_0], rcx
0x180011f27  push    rsi
0x180011f28  push    rdi
0x180011f29  push    r14
0x180011f2b  sub     rsp, 30h
0x180011f2f  mov     rsi, cs:Feature_WindowsProtectedPrintSpoolerWorker__descriptor
0x180011f36  mov     rdi, rdx
0x180011f39  mov     qword ptr [rdx], 0
0x180011f40  mov     eax, [rsi]
0x180011f42  mov     [rdx], eax
0x180011f44  and     eax, 6
0x180011f47  cmp     al, 6
0x180011f49  jz      loc_18001203B
0x180011f4f  call    ?EnsureSubscribedToFeatureConfigurationChanges@details@wil@@YAIXZ; wil::details::EnsureSubscribedToFeatureConfigurationChanges(void)
0x180011f54  lea     r8, [rsp+48h+arg_0]
0x180011f59  mov     dword ptr [rsp+48h+arg_0], 0
0x180011f61  lea     rdx, [rsp+48h+arg_8]
0x180011f66  mov     ebp, eax
0x180011f68  call    ?GetCurrentFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@PEAH@Z; wil::details::FeatureImpl<__WilFeatureTraits_Feature_WindowsProtectedPrintSpoolerWorker>::GetCurrentFeatureEnabledState(int *)
0x180011f6d  mov     eax, [rdi]
0x180011f6f  mov     rbx, [rsp+48h+arg_8]
0x180011f74  cmp     dword ptr [rsp+48h+arg_0], 0
0x180011f79  mov     edx, eax
0x180011f7b  mov     [rdi], eax
0x180011f7d  mov     ecx, eax
0x180011f7f  jz      short loc_180011F9A
0x180011f81  test    dl, 2
0x180011f84  jnz     short loc_180011F9A
0x180011f86  and     ecx, 0FFFFF63Eh
0x180011f8c  mov     eax, ebx
0x180011f8e  and     eax, 9C1h
0x180011f93  or      ecx, eax
0x180011f95  or      ecx, 2
0x180011f98  mov     [rdi], ecx
0x180011f9a  mov     r8d, edx
0x180011f9d  and     r8d, 4
0x180011fa1  jnz     short loc_180011FB5
0x180011fa3  btr     ecx, 0Ah
0x180011fa7  mov     eax, ebx
0x180011fa9  and     eax, 400h
0x180011fae  or      ecx, eax
0x180011fb0  or      ecx, 4
0x180011fb3  mov     [rdi], ecx
0x180011fb5  mov     eax, edx
0x180011fb7  lock cmpxchg [rsi], ecx
0x180011fbb  jnz     short loc_180011F74
0x180011fbd  test    r8d, r8d
0x180011fc0  jnz     short loc_180012026
0x180011fc2  mov     eax, cs:?g_enabledStateManager@details@wil@@3V?$shutdown_aware_object@VEnabledStateManager@details@wil@@@2@A; wil::shutdown_aware_object<wil::details::EnabledStateManager> wil::details::g_enabledStateManager
0x180011fc8  test    eax, eax
0x180011fca  jz      short loc_180012026
0x180011fcc  lea     r14, SRWLock
0x180011fd3  mov     rcx, r14; SRWLock
0x180011fd6  call    cs:__imp_AcquireSRWLockExclusive
0x180011fdc  mov     eax, cs:dword_180024B2C
0x180011fe2  mov     [rsp+48h+arg_8], r14
0x180011fe7  test    ebp, ebp
0x180011fe9  jz      short loc_180012018
0x180011feb  cmp     ebp, eax
0x180011fed  jnz     short loc_180012018
0x180011fef  mov     r8d, 10h; unsigned __int64
0x180011ff5  mov     [rsp+48h+var_28], 3
0x180011ffe  lea     rdx, [rsp+48h+var_28]; void *
0x180012003  mov     [rsp+48h+var_20], rsi
0x180012008  lea     rcx, qword_180024B50; this
0x18001200f  call    ?push_back@heap_buffer@details_abi@wil@@QEAA_NPEBX_K@Z; wil::details_abi::heap_buffer::push_back(void const *,unsigned __int64)
0x180012014  test    al, al
0x180012016  jnz     short loc_18001201C
0x180012018  lock and dword ptr [rsi], 0FFFFFFFBh
0x18001201c  lea     rcx, [rsp+48h+arg_8]
0x180012021  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x180012026  mov     eax, [rdi]
0x180012028  test    al, 2
0x18001202a  jnz     short loc_18001203B
0x18001202c  and     eax, 0FFFFF63Eh
0x180012031  and     ebx, 9C1h
0x180012037  or      eax, ebx
0x180012039  mov     [rdi], eax
0x18001203b  mov     rbx, [rsp+48h+arg_10]
0x180012040  mov     rax, rdi
0x180012043  mov     rbp, [rsp+48h+arg_18]
0x180012048  add     rsp, 30h
0x18001204c  pop     r14
0x18001204e  pop     rdi
0x18001204f  pop     rsi
0x180012050  retn
```
