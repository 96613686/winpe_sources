# SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::InitializeSourceProvider(void)

- ea: `0x18002fe20`
- end: `0x18002fec8`
- name: `?InitializeSourceProvider@?$SourceProviderController@UIDsmDeviceSoftwareInstaller@@VDSICSoftwareInstaller@@@@SAJXZ`
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
- `0x18002fe20`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fe30`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18002fe30`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fe91`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18002fe91`

## string_xrefs

- `0x18002fe49`: `onecoreuap\base\devices\setup\dsm\service\JobBase.h`

## pseudocode

```c
__int64 SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::InitializeSourceProvider()
{
  unsigned int v0; // ebx
  HRESULT Instance; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  RTL_SRWLOCK *v5; // [rsp+40h] [rbp+8h] BYREF

  AcquireSRWLockExclusive(&SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_lock);
  v5 = &SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_lock;
  if ( SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerAvailable )
  {
    if ( SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerInitialized )
    {
      v0 = 0;
    }
    else
    {
      Instance = CoCreateInstance(
                   &GUID_b0a38a0c_0437_4e02_9b96_27f998020f46,
                   0,
                   1u,
                   &GUID_515bcd5f_f599_4123_8a2b_60025c903c44,
                   &SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_sourceProvider);
      if ( Instance < 0 )
      {
        if ( Instance == -2147221164 )
          SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerAvailable = 0;
      }
      else
      {
        SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerInitialized = 1;
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
0x18002fe20  push    rbx
0x18002fe22  sub     rsp, 30h
0x18002fe26  lea     rbx, ?_lock@?$SourceProviderController@UIDsmDeviceSoftwareInstaller@@VDSICSoftwareInstaller@@@@0Vsrwlock@wil@@A; wil::srwlock SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_lock
0x18002fe2d  mov     rcx, rbx; SRWLock
0x18002fe30  call    cs:__imp_AcquireSRWLockExclusive
0x18002fe36  cmp     cs:?_providerAvailable@?$SourceProviderController@UIDsmDeviceSoftwareInstaller@@VDSICSoftwareInstaller@@@@0_NA, 0; bool SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerAvailable
0x18002fe3d  mov     [rsp+38h+arg_0], rbx
0x18002fe42  jnz     short loc_18002FE64
0x18002fe44  mov     rcx, [rsp+38h]; this
0x18002fe49  lea     r8, aOnecoreuapBase_10; "onecoreuap\\base\\devices\\setup\\dsm\\"...
0x18002fe50  mov     ebx, 80040154h
0x18002fe55  mov     edx, 89h; void *
0x18002fe5a  mov     r9d, ebx; char *
0x18002fe5d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002fe62  jmp     short loc_18002FEB6
0x18002fe64  cmp     cs:?_providerInitialized@?$SourceProviderController@UIDsmDeviceSoftwareInstaller@@VDSICSoftwareInstaller@@@@0_NA, 0; bool SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerInitialized
0x18002fe6b  jz      short loc_18002FE71
0x18002fe6d  xor     ebx, ebx
0x18002fe6f  jmp     short loc_18002FEB6
0x18002fe71  xor     edx, edx; pUnkOuter
0x18002fe73  lea     rax, ?_sourceProvider@?$SourceProviderController@UIDsmDeviceSoftwareInstaller@@VDSICSoftwareInstaller@@@@1V?$ComPtr@UIDsmDeviceSoftwareInstaller@@@WRL@Microsoft@@A; Microsoft::WRL::ComPtr<IDsmDeviceSoftwareInstaller> SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_sourceProvider
0x18002fe7a  lea     r9, _GUID_515bcd5f_f599_4123_8a2b_60025c903c44; riid
0x18002fe81  mov     qword ptr [rsp+38h+ppv], rax; ppv
0x18002fe86  lea     rcx, _GUID_b0a38a0c_0437_4e02_9b96_27f998020f46; rclsid
0x18002fe8d  lea     r8d, [rdx+1]; dwClsContext
0x18002fe91  call    cs:__imp_CoCreateInstance
0x18002fe97  test    eax, eax
0x18002fe99  js      short loc_18002FEA4
0x18002fe9b  mov     cs:?_providerInitialized@?$SourceProviderController@UIDsmDeviceSoftwareInstaller@@VDSICSoftwareInstaller@@@@0_NA, 1; bool SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerInitialized
0x18002fea2  jmp     short loc_18002FEB4
0x18002fea4  mov     ebx, 80040154h
0x18002fea9  cmp     eax, ebx
0x18002feab  jnz     short loc_18002FEB4
0x18002fead  mov     cs:?_providerAvailable@?$SourceProviderController@UIDsmDeviceSoftwareInstaller@@VDSICSoftwareInstaller@@@@0_NA, 0; bool SourceProviderController<IDsmDeviceSoftwareInstaller,DSICSoftwareInstaller>::_providerAvailable
0x18002feb4  mov     ebx, eax
0x18002feb6  lea     rcx, [rsp+38h+arg_0]
0x18002febb  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18002fec0  mov     eax, ebx
0x18002fec2  add     rsp, 30h
0x18002fec6  pop     rbx
0x18002fec7  retn
```
