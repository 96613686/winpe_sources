# Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay(Windows::Internal::WiFiCloudStore::TaskTrigger)

- ea: `0x18003c954`
- end: `0x18003ca76`
- name: `?TriggerTaskWithDelay@WiFiCloudStore@Internal@Windows@@YAJW4TaskTrigger@123@@Z`
- size: `290`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800242a0`

## callees

- `0x180028a70`
- `0x180029058`
- `0x18002ca28`
- `0x18003c884`
- `0x18003c954`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003c982`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18003c982`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ca42`
- `api-ms-win-core-threadpool-l1-2-0!SetThreadpoolTimer` at `0x18003ca42`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003c9b4`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolTimer` at `0x18003c9b4`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c9ed`
- `api-ms-win-core-sysinfo-l1-1-0!GetTickCount64` at `0x18003c9ed`

## string_xrefs

- `0x18003c990`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`
- `0x18003c9ca`: `onecore\net\wificloudstore\registry\lib\cdsproducercommonreg.cpp`

## pseudocode

```c
__int64 Windows::Internal::WiFiCloudStore::TriggerTaskWithDelay()
{
  const char *v0; // r9
  unsigned int LastError; // ebx
  const char *v2; // r9
  struct _TP_TIMER *v3; // rbx
  struct _FILETIME v4; // rdi
  __int64 v5; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+18h]
  HMODULE phModule; // [rsp+48h] [rbp+28h] BYREF
  PTP_TIMER ThreadpoolTimer; // [rsp+50h] [rbp+30h] BYREF
  struct _FILETIME pftDueTime; // [rsp+58h] [rbp+38h] BYREF

  phModule = 0;
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(
    &phModule,
    0);
  if ( GetModuleHandleExW(4u, L"\\Microsoft\\Windows\\WlanSvc", &phModule) )
  {
    ThreadpoolTimer = CreateThreadpoolTimer(
                        Windows::Internal::WiFiCloudStore::TriggerTaskTimerCallbackDusmSvc,
                        phModule,
                        0);
    v3 = ThreadpoolTimer;
    if ( ThreadpoolTimer )
    {
      v4 = (struct _FILETIME)-600000000LL;
      v5 = (__int64)GetTickCount64() / 60000;
      if ( (int)v5 < 15 )
        v4 = (struct _FILETIME)(-600000000LL * (15 - (int)v5));
      pftDueTime = v4;
      SetThreadpoolTimer(v3, &pftDueTime, 0, 0x989680u);
      phModule = 0;
      ThreadpoolTimer = 0;
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&ThreadpoolTimer);
      LastError = 0;
    }
    else
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x73,
                    (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                    v2);
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(&ThreadpoolTimer);
    }
  }
  else
  {
    LastError = wil::details::in1diag3::Return_GetLastError(
                  retaddr,
                  (void *)0x6E,
                  (unsigned int)"onecore\\net\\wificloudstore\\registry\\lib\\cdsproducercommonreg.cpp",
                  v0);
  }
  wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&int FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(&phModule);
  return LastError;
}

```

## disassembly

```asm
0x18003c954  push    rbp
0x18003c956  push    rbx
0x18003c957  push    rdi
0x18003c958  mov     rbp, rsp
0x18003c95b  sub     rsp, 20h
0x18003c95f  xor     edx, edx
0x18003c961  mov     [rbp+phModule], 0
0x18003c969  lea     rcx, [rbp+phModule]
0x18003c96d  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHINSTANCE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::reset(HINSTANCE__ *)
0x18003c972  lea     r8, [rbp+phModule]; phModule
0x18003c976  mov     ecx, 4; dwFlags
0x18003c97b  lea     rdx, psz; "\\Microsoft\\Windows\\WlanSvc"
0x18003c982  call    cs:__imp_GetModuleHandleExW
0x18003c988  test    eax, eax
0x18003c98a  jnz     short loc_18003C9A6
0x18003c98c  mov     rcx, [rbp+18h]; this
0x18003c990  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18003c997  lea     edx, [rax+6Eh]; void *
0x18003c99a  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c99f  mov     ebx, eax
0x18003c9a1  jmp     loc_18003CA63
0x18003c9a6  mov     rdx, [rbp+phModule]; pv
0x18003c9aa  lea     rcx, ?TriggerTaskTimerCallbackDusmSvc@WiFiCloudStore@Internal@Windows@@YAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_TIMER@@@Z; pfnti
0x18003c9b1  xor     r8d, r8d; pcbe
0x18003c9b4  call    cs:__imp_CreateThreadpoolTimer
0x18003c9ba  mov     [rbp+arg_10], rax
0x18003c9be  mov     rbx, rax
0x18003c9c1  test    rax, rax
0x18003c9c4  jnz     short loc_18003C9E6
0x18003c9c6  mov     rcx, [rbp+18h]; this
0x18003c9ca  lea     r8, aOnecoreNetWifi_2; "onecore\\net\\wificloudstore\\registry"...
0x18003c9d1  lea     edx, [rax+73h]; void *
0x18003c9d4  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003c9d9  lea     rcx, [rbp+arg_10]
0x18003c9dd  mov     ebx, eax
0x18003c9df  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18003c9e4  jmp     short loc_18003CA63
0x18003c9e6  mov     rdi, 0FFFFFFFFDC3CBA00h
0x18003c9ed  call    cs:__imp_GetTickCount64
0x18003c9f3  mov     rcx, rax
0x18003c9f6  mov     rax, 45E7B272F608770Fh
0x18003ca00  imul    rcx
0x18003ca03  sar     rdx, 0Eh
0x18003ca07  mov     rax, rdx
0x18003ca0a  shr     rax, 3Fh
0x18003ca0e  add     rdx, rax
0x18003ca11  mov     eax, 0Fh
0x18003ca16  cmp     edx, eax
0x18003ca18  jge     short loc_18003CA25
0x18003ca1a  sub     eax, edx
0x18003ca1c  cdqe
0x18003ca1e  imul    rdi, rax, 0FFFFFFFFDC3CBA00h
0x18003ca25  mov     rax, rdi
0x18003ca28  mov     [rbp+pftDueTime.dwLowDateTime], edi
0x18003ca2b  shr     rax, 20h
0x18003ca2f  lea     rdx, [rbp+pftDueTime]; pftDueTime
0x18003ca33  mov     r9d, 989680h; msWindowLength
0x18003ca39  mov     [rbp+pftDueTime.dwHighDateTime], eax
0x18003ca3c  xor     r8d, r8d; msPeriod
0x18003ca3f  mov     rcx, rbx; pti
0x18003ca42  call    cs:__imp_SetThreadpoolTimer
0x18003ca48  lea     rcx, [rbp+arg_10]
0x18003ca4c  mov     [rbp+phModule], 0
0x18003ca54  mov     [rbp+arg_10], 0
0x18003ca5c  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$01@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,2>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x18003ca61  xor     ebx, ebx
0x18003ca63  lea     rcx, [rbp+phModule]
0x18003ca67  call    ??1?$unique_storage@U?$resource_policy@PEAUHINSTANCE__@@P6AHPEAU1@@Z$1?FreeLibrary@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HINSTANCE__ *,int (*)(HINSTANCE__ *),&FreeLibrary(HINSTANCE__ *),wistd::integral_constant<unsigned __int64,0>,HINSTANCE__ *,HINSTANCE__ *,0,std::nullptr_t>>(void)
0x18003ca6c  mov     eax, ebx
0x18003ca6e  add     rsp, 20h
0x18003ca72  pop     rdi
0x18003ca73  pop     rbx
0x18003ca74  pop     rbp
0x18003ca75  retn
```
