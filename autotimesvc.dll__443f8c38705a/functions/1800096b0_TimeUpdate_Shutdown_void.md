# TimeUpdate::Shutdown(void)

- ea: `0x1800096b0`
- end: `0x1800098cc`
- name: `?Shutdown@TimeUpdate@@QEAAXXZ`
- size: `540`
- prototype: `void __fastcall(TimeUpdate *__hidden this)`
- caller_count: `2`
- callee_count: `13`
- tags: `registry_config, service_task, installer_update`

## callers

- `0x18000591c`
- `0x18000a108`

## callees

- `0x180001010`
- `0x1800012f0`
- `0x180005840`
- `0x180005860`
- `0x1800096b0`
- `0x18000a9e4`
- `0x18000aa38`
- `0x18000aa8c`
- `0x18000b86c`
- `0x18000b910`
- `0x18000b9f0`
- `0x18000bea8`
- `0x180010800`

## import_xrefs

- `msvcp_win!_Thrd_id` at `0x18000980a`
- `msvcp_win!_Thrd_id` at `0x18000980a`
- `msvcp_win!_Thrd_join` at `0x180009838`
- `msvcp_win!_Thrd_join` at `0x180009838`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000981d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180009847`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x18000981d`
- `msvcp_win!?_Throw_Cpp_error@std@@YAXH@Z` at `0x180009847`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009748`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180009748`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009732`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180009732`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18000971d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800097e0`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x18000971d`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x1800097e0`

## pseudocode

```c
void __fastcall TimeUpdate::Shutdown(TimeUpdate *this)
{
  char v2; // al
  void *v3; // rcx
  struct _TP_TIMER **v4; // rbx
  bool v5; // dl
  WnfSubscription *i; // rbx
  struct _TP_TIMER *v7[2]; // [rsp+20h] [rbp-48h] BYREF
  _Thrd_t v8; // [rsp+30h] [rbp-38h] BYREF
  struct _RTL_CRITICAL_SECTION *v9; // [rsp+70h] [rbp+8h] BYREF

  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      (__int64)&dword_18001C010,
      (__int64)&word_180016756,
      0,
      0);
  v2 = *((_BYTE *)this + 56);
  *((_BYTE *)this + 56) = 0;
  if ( v2 )
  {
    *((_DWORD *)this + 15) = 1;
    WakeByAddressAll((char *)this + 60);
    v3 = (void *)*((_QWORD *)this + 73);
    if ( v3 )
      SetEvent(v3);
    v7[0] = 0;
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
    v9 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 16);
    v4 = (struct _TP_TIMER **)((char *)this + 248);
    if ( v7 != (struct _TP_TIMER **)((char *)this + 248) )
    {
      wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
        v7,
        *v4);
      *v4 = 0;
    }
    wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&void LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(&v9);
    WNFNotificationDispatcher::Stop((TimeUpdate *)((char *)this + 64), 1);
    WNFNotificationDispatcher::Stop((TimeUpdate *)((char *)this + 144), 1);
    for ( i = (TimeUpdate *)((char *)this + 256);
          i != (TimeUpdate *)((char *)this + 480);
          i = (WnfSubscription *)((char *)i + 56) )
    {
      WnfSubscription::Unsubscribe(i, v5);
    }
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(
      v7,
      0);
    WNFNotificationDispatcher::Shutdown((TimeUpdate *)((char *)this + 64));
    *((_DWORD *)this + 15) = 1;
    WakeByAddressAll((char *)this + 60);
    if ( !WNFNotificationDispatcher::IsQueueEmpty((TimeUpdate *)((char *)this + 144)) )
      WpW32TimeStopService(0);
    WNFNotificationDispatcher::Shutdown((TimeUpdate *)((char *)this + 144));
    if ( *((_DWORD *)this + 122) )
    {
      if ( *((_DWORD *)this + 122) == _Thrd_id() )
      {
        std::_Throw_Cpp_error(5);
        __debugbreak();
      }
      v8 = (_Thrd_t)*((_OWORD *)this + 30);
      if ( _Thrd_join(&v8, 0) )
      {
        std::_Throw_Cpp_error(2);
        __debugbreak();
      }
      *((_OWORD *)this + 30) = 0;
    }
    _reset___unique_storage_U__resource_policy_PEAXP6AXPEAX__E_1_CloseHandle_details_wil__YAX0_ZU__integral_constant__K_0A__wistd__PEAXPEAX_0A___T_details_wil___details_wil__QEAAXPEAX_Z(
      (wil::details **)this + 73,
      0);
    wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&int CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(
      (SC_HANDLE *)this + 80,
      0);
    if ( (unsigned int)dword_18001C010 > 4 )
    {
      if ( (unsigned __int8)tlgKeywordOn(&dword_18001C010, 1) )
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
          (__int64)&dword_18001C010,
          (__int64)word_180016502,
          0,
          0);
    }
    wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&public: static void wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(v7);
  }
}

```

## disassembly

```asm
0x1800096b0  mov     [rsp+arg_8], rbx
0x1800096b5  mov     [rsp+arg_10], rbp
0x1800096ba  push    rsi
0x1800096bb  push    rdi
0x1800096bc  push    r12
0x1800096be  push    r14
0x1800096c0  push    r15
0x1800096c2  sub     rsp, 40h
0x1800096c6  mov     rdi, rcx
0x1800096c9  mov     eax, cs:dword_18001C010
0x1800096cf  mov     r15d, 1
0x1800096d5  cmp     eax, 4
0x1800096d8  jbe     short loc_180009706
0x1800096da  mov     edx, r15d
0x1800096dd  lea     rcx, dword_18001C010
0x1800096e4  call    _tlgKeywordOn
0x1800096e9  test    al, al
0x1800096eb  jz      short loc_180009706
0x1800096ed  xor     r9d, r9d
0x1800096f0  xor     r8d, r8d
0x1800096f3  lea     rdx, word_180016756
0x1800096fa  lea     rcx, dword_18001C010
0x180009701  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180009706  xor     eax, eax
0x180009708  xchg    al, [rdi+38h]
0x18000970b  test    al, al
0x18000970d  jz      loc_1800098B3
0x180009713  lea     rsi, [rdi+3Ch]
0x180009717  mov     [rsi], r15d
0x18000971a  mov     rcx, rsi; Address
0x18000971d  call    cs:__imp_WakeByAddressAll
0x180009723  lea     r14, [rdi+248h]
0x18000972a  mov     rcx, [r14]; hEvent
0x18000972d  test    rcx, rcx
0x180009730  jz      short loc_180009738
0x180009732  call    cs:__imp_SetEvent
0x180009738  mov     [rsp+68h+var_48], 0
0x180009741  lea     rbx, [rdi+10h]
0x180009745  mov     rcx, rbx; lpCriticalSection
0x180009748  call    cs:__imp_EnterCriticalSection
0x18000974e  mov     [rsp+68h+arg_0], rbx
0x180009753  lea     rbx, [rdi+0F8h]
0x18000975a  lea     rax, [rsp+68h+var_48]
0x18000975f  cmp     rax, rbx
0x180009762  jz      short loc_180009778
0x180009764  mov     rdx, [rbx]
0x180009767  lea     rcx, [rsp+68h+var_48]
0x18000976c  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x180009771  mov     qword ptr [rbx], 0
0x180009778  lea     rcx, [rsp+68h+arg_0]
0x18000977d  call    ??1?$unique_storage@U?$resource_policy@PEAU_RTL_CRITICAL_SECTION@@P6AXPEAU1@@Z$1?LeaveCriticalSection@@YAX0@ZU?$integral_constant@_K$00@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_RTL_CRITICAL_SECTION *,void (*)(_RTL_CRITICAL_SECTION *),&LeaveCriticalSection(_RTL_CRITICAL_SECTION *),wistd::integral_constant<unsigned __int64,1>,_RTL_CRITICAL_SECTION *,_RTL_CRITICAL_SECTION *,0,std::nullptr_t>>(void)
0x180009782  mov     dl, r15b; bool
0x180009785  lea     rcx, [rdi+40h]; this
0x180009789  call    ?Stop@WNFNotificationDispatcher@@QEAAX_N@Z; WNFNotificationDispatcher::Stop(bool)
0x18000978e  lea     rbp, [rdi+90h]
0x180009795  mov     dl, r15b; bool
0x180009798  mov     rcx, rbp; this
0x18000979b  call    ?Stop@WNFNotificationDispatcher@@QEAAX_N@Z; WNFNotificationDispatcher::Stop(bool)
0x1800097a0  lea     rbx, [rdi+100h]
0x1800097a7  lea     r15, [rbx+0E0h]
0x1800097ae  jmp     short loc_1800097BC
0x1800097b0  mov     rcx, rbx; this
0x1800097b3  call    ?Unsubscribe@WnfSubscription@@QEAAX_N@Z; WnfSubscription::Unsubscribe(bool)
0x1800097b8  add     rbx, 38h ; '8'
0x1800097bc  cmp     rbx, r15
0x1800097bf  jnz     short loc_1800097B0
0x1800097c1  xor     edx, edx
0x1800097c3  lea     rcx, [rsp+68h+var_48]
0x1800097c8  call    ?reset@?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAU_TP_TIMER@@@Z; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::reset(_TP_TIMER *)
0x1800097cd  lea     rcx, [rdi+40h]; this
0x1800097d1  call    ?Shutdown@WNFNotificationDispatcher@@QEAAXXZ; WNFNotificationDispatcher::Shutdown(void)
0x1800097d6  mov     ebx, 1
0x1800097db  mov     [rsi], ebx
0x1800097dd  mov     rcx, rsi; Address
0x1800097e0  call    cs:__imp_WakeByAddressAll
0x1800097e6  mov     rcx, rbp; this
0x1800097e9  call    ?IsQueueEmpty@WNFNotificationDispatcher@@QEBA_NXZ; WNFNotificationDispatcher::IsQueueEmpty(void)
0x1800097ee  test    al, al
0x1800097f0  jnz     short loc_1800097F9
0x1800097f2  xor     ecx, ecx
0x1800097f4  call    WpW32TimeStopService
0x1800097f9  mov     rcx, rbp; this
0x1800097fc  call    ?Shutdown@WNFNotificationDispatcher@@QEAAXXZ; WNFNotificationDispatcher::Shutdown(void)
0x180009801  cmp     dword ptr [rdi+1E8h], 0
0x180009808  jz      short loc_180009859
0x18000980a  call    cs:__imp__Thrd_id
0x180009810  cmp     [rdi+1E8h], eax
0x180009816  jnz     short loc_180009824
0x180009818  mov     ecx, 5
0x18000981d  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x180009823  int     3; Trap to Debugger
0x180009824  movups  xmm0, xmmword ptr [rdi+1E0h]
0x18000982b  movdqu  xmmword ptr [rsp+68h+var_38._Hnd], xmm0
0x180009831  xor     edx, edx; int *
0x180009833  lea     rcx, [rsp+68h+var_38]; _Thrd_t
0x180009838  call    cs:__imp__Thrd_join
0x18000983e  test    eax, eax
0x180009840  jz      short loc_18000984E
0x180009842  mov     ecx, 2
0x180009847  call    cs:__imp_?_Throw_Cpp_error@std@@YAXH@Z; std::_Throw_Cpp_error(int)
0x18000984d  int     3; Trap to Debugger
0x18000984e  xorps   xmm0, xmm0
0x180009851  movdqu  xmmword ptr [rdi+1E0h], xmm0
0x180009859  xor     edx, edx
0x18000985b  mov     rcx, r14
0x18000985e  call    ?reset@?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@_E$1?CloseHandle@details@wil@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAXPEAX$0A@$$T@details@wil@@@details@wil@@QEAAXPEAX@Z
0x180009863  lea     rcx, [rdi+280h]
0x18000986a  xor     edx, edx
0x18000986c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUSC_HANDLE__@@P6AHPEAU1@@Z$1?CloseServiceHandle@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUSC_HANDLE__@@@Z; wil::details::unique_storage<wil::details::resource_policy<SC_HANDLE__ *,int (*)(SC_HANDLE__ *),&CloseServiceHandle(SC_HANDLE__ *),wistd::integral_constant<unsigned __int64,0>,SC_HANDLE__ *,SC_HANDLE__ *,0,std::nullptr_t>>::reset(SC_HANDLE__ *)
0x180009871  mov     eax, cs:dword_18001C010
0x180009877  cmp     eax, 4
0x18000987a  jbe     short loc_1800098A8
0x18000987c  mov     rdx, rbx
0x18000987f  lea     rcx, dword_18001C010
0x180009886  call    _tlgKeywordOn
0x18000988b  test    al, al
0x18000988d  jz      short loc_1800098A8
0x18000988f  xor     r9d, r9d
0x180009892  xor     r8d, r8d
0x180009895  lea     rdx, word_180016502
0x18000989c  lea     rcx, dword_18001C010
0x1800098a3  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x1800098a8  lea     rcx, [rsp+68h+var_48]
0x1800098ad  call    ??1?$unique_storage@U?$resource_policy@PEAU_TP_TIMER@@P6AXPEAU1@@Z$1?Destroy@?$DestroyThreadPoolTimer@USystemThreadPoolMethods@details@wil@@$0A@@details@wil@@SAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<_TP_TIMER *,void (*)(_TP_TIMER *),&wil::details::DestroyThreadPoolTimer<wil::details::SystemThreadPoolMethods,0>::Destroy(_TP_TIMER *),wistd::integral_constant<unsigned __int64,0>,_TP_TIMER *,_TP_TIMER *,0,std::nullptr_t>>(void)
0x1800098b2  nop
0x1800098b3  lea     r11, [rsp+68h+var_28]
0x1800098b8  mov     rbx, [r11+38h]
0x1800098bc  mov     rbp, [r11+40h]
0x1800098c0  mov     rsp, r11
0x1800098c3  pop     r15
0x1800098c5  pop     r14
0x1800098c7  pop     r12
0x1800098c9  pop     rdi
0x1800098ca  pop     rsi
0x1800098cb  retn
```
