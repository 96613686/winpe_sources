# SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::InitializeSourceProvider(void)

- ea: `0x18002fed0`
- end: `0x18002ff78`
- name: `?InitializeSourceProvider@?$SourceProviderController@UIDsmDriverPackageSource@@VDDRCPackageSource@@@@SAJXZ`
- size: `168`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18002fc30`

## callees

- `0x1800112a4`
- `0x180015474`
- `0x18002fed0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fee0`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fee0`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ff41`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002ff41`

## string_xrefs

- `0x18002fef9`: `onecoreuap\base\devices\setup\dsm\service\JobBase.h`

## pseudocode

```c
__int64 SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::InitializeSourceProvider()
{
  unsigned int v0; // ebx
  HRESULT Instance; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v5; // [rsp+40h] [rbp+8h] BYREF

  AcquireSRWLockExclusive(&SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_lock);
  v5 = &SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_lock;
  if ( SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerAvailable )
  {
    if ( SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerInitialized )
    {
      v0 = 0;
    }
    else
    {
      Instance = CoCreateInstance(
                   &GUID_47d35bb4_71cc_4810_9669_d03d9ff7ceaf,
                   0,
                   1u,
                   &GUID_6d7120e1_a765_4413_b2a5_31d187e58dec,
                   &SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_sourceProvider);
      if ( Instance < 0 )
      {
        if ( Instance == -2147221164 )
          SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerAvailable = 0;
      }
      else
      {
        SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerInitialized = 1;
      }
      v0 = Instance;
    }
  }
  else
  {
    v0 = -2147221164;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x89,
      (unsigned int)"onecoreuap\\base\\devices\\setup\\dsm\\service\\JobBase.h",
      (const char *)0x80040154LL,
      ppv);
  }
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v5);
  return v0;
}

```

## disassembly

```asm
0x18002fed0  push    rbx
0x18002fed2  sub     rsp, 30h
0x18002fed6  lea     rbx, ?_lock@?$SourceProviderController@UIDsmDriverPackageSource@@VDDRCPackageSource@@@@0Vsrwlock@wil@@A; wil::srwlock SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_lock
0x18002fedd  mov     rcx, rbx; SRWLock
0x18002fee0  call    cs:__imp_AcquireSRWLockExclusive
0x18002fee6  cmp     cs:?_providerAvailable@?$SourceProviderController@UIDsmDriverPackageSource@@VDDRCPackageSource@@@@0_NA, 0; bool SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerAvailable
0x18002feed  mov     [rsp+38h+arg_0], rbx
0x18002fef2  jnz     short loc_18002FF14
0x18002fef4  mov     rcx, [rsp+38h]; this
0x18002fef9  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002ff00  mov     ebx, 80040154h
0x18002ff05  mov     edx, 89h; void *
0x18002ff0a  mov     r9d, ebx; char *
0x18002ff0d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ff12  jmp     short loc_18002FF66
0x18002ff14  cmp     cs:?_providerInitialized@?$SourceProviderController@UIDsmDriverPackageSource@@VDDRCPackageSource@@@@0_NA, 0; bool SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerInitialized
0x18002ff1b  jz      short loc_18002FF21
0x18002ff1d  xor     ebx, ebx
0x18002ff1f  jmp     short loc_18002FF66
0x18002ff21  xor     edx, edx; pUnkOuter
0x18002ff23  lea     rax, ?_sourceProvider@?$SourceProviderController@UIDsmDriverPackageSource@@VDDRCPackageSource@@@@1V?$ComPtr@UIDsmDriverPackageSource@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IDsmDriverPackageSource> SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_sourceProvider
0x18002ff2a  lea     r9, _GUID_6d7120e1_a765_4413_b2a5_31d187e58dec; riid
0x18002ff31  mov     qword ptr [rsp+38h+ppv], rax; ppv
0x18002ff36  lea     rcx, _GUID_47d35bb4_71cc_4810_9669_d03d9ff7ceaf; rclsid
0x18002ff3d  lea     r8d, [rdx+1]; dwClsContext
0x18002ff41  call    cs:__imp_CoCreateInstance
0x18002ff47  test    eax, eax
0x18002ff49  js      short loc_18002FF54
0x18002ff4b  mov     cs:?_providerInitialized@?$SourceProviderController@UIDsmDriverPackageSource@@VDDRCPackageSource@@@@0_NA, 1; bool SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerInitialized
0x18002ff52  jmp     short loc_18002FF64
0x18002ff54  mov     ebx, 80040154h
0x18002ff59  cmp     eax, ebx
0x18002ff5b  jnz     short loc_18002FF64
0x18002ff5d  mov     cs:?_providerAvailable@?$SourceProviderController@UIDsmDriverPackageSource@@VDDRCPackageSource@@@@0_NA, 0; bool SourceProviderController<IDsmDriverPackageSource,DDRCPackageSource>::_providerAvailable
0x18002ff64  mov     ebx, eax
0x18002ff66  lea     rcx, [rsp+38h+arg_0]
0x18002ff6b  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002ff70  mov     eax, ebx
0x18002ff72  add     rsp, 30h
0x18002ff76  pop     rbx
0x18002ff77  retn
```
