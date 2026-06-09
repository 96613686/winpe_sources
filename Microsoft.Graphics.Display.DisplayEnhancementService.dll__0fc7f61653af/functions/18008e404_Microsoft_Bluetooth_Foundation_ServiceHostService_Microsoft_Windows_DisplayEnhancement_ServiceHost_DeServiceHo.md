# Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::GetServiceRegistryStateKey(SERVICE_REGISTRY_STATE_TYPE,ulong)

- ea: `0x18008e404`
- end: `0x18008e4f0`
- name: `?GetServiceRegistryStateKey@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@SA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@W4SERVICE_REGISTRY_STATE_TYPE@@K@Z`
- size: `236`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18008f294`
- `0x1800ae29c`

## callees

- `0x180009a84`
- `0x18000fa0c`
- `0x18001f890`
- `0x18001f9d8`
- `0x18008e404`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008e42b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008e448`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008e42b`
- `api-ms-win-core-synch-l1-1-0!AcquireSRWLockExclusive` at `0x18008e448`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18008e485`
- `api-ms-win-service-core-l1-1-3!GetServiceRegistryStateKey` at `0x18008e485`

## string_xrefs

- `0x18008e496`: `onecore\private\drivers\inc\bluetooth\foundation\ServiceHost.h`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
_QWORD *__fastcall Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::GetServiceRegistryStateKey(
        _QWORD *a1)
{
  char *v2; // rbx
  __int64 v3; // rcx
  unsigned int ServiceRegistryStateKey; // eax
  unsigned int v6; // [rsp+20h] [rbp-30h]
  char *v7; // [rsp+28h] [rbp-28h] BYREF
  RTL_SRWLOCK *v8; // [rsp+30h] [rbp-20h] BYREF
  __int64 *v9; // [rsp+38h] [rbp-18h] BYREF
  __int64 v10; // [rsp+40h] [rbp-10h] BYREF
  char v11; // [rsp+48h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+8h]
  __int64 v13; // [rsp+78h] [rbp+28h] BYREF

  v13 = 0;
  AcquireSRWLockExclusive(&Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::m_serviceStaticsLock);
  v8 = &Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::m_serviceStaticsLock;
  if ( Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service )
  {
    v2 = (char *)Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service
       + 64;
    AcquireSRWLockExclusive(
      (PSRWLOCK)Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service
    + 8);
    v7 = v2;
    v3 = *((_QWORD *)Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service
         + 9);
    if ( v3 )
    {
      v9 = &v13;
      v10 = 0;
      v11 = 1;
      ServiceRegistryStateKey = GetServiceRegistryStateKey(v3, 1, 3221356575LL, &v10);
      if ( ServiceRegistryStateKey )
        wil::details::in1diag3::Throw_Win32(
          retaddr,
          (void *)0x63,
          (unsigned int)"onecore\\private\\drivers\\inc\\bluetooth\\foundation\\ServiceHost.h",
          (const char *)ServiceRegistryStateKey,
          v6);
      wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(&v9);
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v7);
  }
  *a1 = v13;
  v13 = 0;
  wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&void ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(&v8);
  wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v13);
  return a1;
}

```

## disassembly

```asm
0x18008e404  mov     [rsp-8+arg_0], rbx
0x18008e409  mov     [rsp-8+arg_8], rdi
0x18008e40e  push    rbp
0x18008e40f  mov     rbp, rsp
0x18008e412  sub     rsp, 50h
0x18008e416  mov     rdi, rcx
0x18008e419  mov     [rbp+arg_18], 0
0x18008e421  lea     rbx, ?m_serviceStaticsLock@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0Vsrwlock@wil@@A; wil::srwlock Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::m_serviceStaticsLock
0x18008e428  mov     rcx, rbx; SRWLock
0x18008e42b  call    cs:__imp_AcquireSRWLockExclusive
0x18008e431  mov     [rbp+var_20], rbx
0x18008e435  mov     rbx, cs:?s_service@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0V?$shared_ptr@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@@std@@A; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost> Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service
0x18008e43c  test    rbx, rbx
0x18008e43f  jz      short loc_18008E4BB
0x18008e441  add     rbx, 40h ; '@'
0x18008e445  mov     rcx, rbx; SRWLock
0x18008e448  call    cs:__imp_AcquireSRWLockExclusive
0x18008e44e  mov     [rbp+var_28], rbx
0x18008e452  mov     rax, cs:?s_service@?$ServiceHostService@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@$00@Foundation@Bluetooth@Microsoft@@0V?$shared_ptr@VDeServiceHost@ServiceHost@DisplayEnhancement@Windows@Microsoft@@@std@@A; std::shared_ptr<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost> Microsoft::Bluetooth::Foundation::ServiceHostService<Microsoft::Windows::DisplayEnhancement::ServiceHost::DeServiceHost,1>::s_service
0x18008e459  mov     rcx, [rax+48h]
0x18008e45d  test    rcx, rcx
0x18008e460  jz      short loc_18008E4B2
0x18008e462  lea     rax, [rbp+arg_18]
0x18008e466  mov     [rbp+var_18], rax
0x18008e46a  mov     [rbp+var_10], 0
0x18008e472  mov     [rbp+var_8], 1
0x18008e476  lea     r9, [rbp+var_10]
0x18008e47a  mov     edx, 1
0x18008e47f  mov     r8d, 0C002001Fh
0x18008e485  call    cs:__imp_GetServiceRegistryStateKey
0x18008e48b  mov     rcx, [rbp+8]; this
0x18008e48f  test    eax, eax
0x18008e491  jz      short loc_18008E4A8
0x18008e493  mov     r9d, eax; char *
0x18008e496  lea     r8, aOnecorePrivate_3; "onecore\\private\\drivers\\inc\\bluetoo"...
0x18008e49d  mov     edx, 63h ; 'c'; void *
0x18008e4a2  call    ?Throw_Win32@in1diag3@details@wil@@YAXPEAXIPEBDK@Z; wil::details::in1diag3::Throw_Win32(void *,uint,char const *,ulong)
0x18008e4a8  lea     rcx, [rbp+var_18]
0x18008e4ac  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>>>(void)
0x18008e4b1  nop
0x18008e4b2  lea     rcx, [rbp+var_28]
0x18008e4b6  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18008e4bb  mov     rax, [rbp+arg_18]
0x18008e4bf  mov     [rdi], rax
0x18008e4c2  mov     [rbp+arg_18], 0
0x18008e4ca  lea     rcx, [rbp+var_20]
0x18008e4ce  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_SRWLOCK@@P6AXPEAU1@@Z$1?ReleaseSRWLockExclusive@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_SRWLOCK *,void (*)(_RTL_SRWLOCK *),&ReleaseSRWLockExclusive(_RTL_SRWLOCK *),wistd::integral_constant<unsigned __int64,1>,_RTL_SRWLOCK *,_RTL_SRWLOCK *,0,std::nullptr_t>>(void)
0x18008e4d3  nop
0x18008e4d4  lea     rcx, [rbp+arg_18]
0x18008e4d8  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18008e4dd  mov     rax, rdi
0x18008e4e0  mov     rbx, [rsp+50h+arg_0]
0x18008e4e5  mov     rdi, [rsp+50h+arg_8]
0x18008e4ea  add     rsp, 50h
0x18008e4ee  pop     rbp
0x18008e4ef  retn
```
