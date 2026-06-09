# UiaManagerImpl::CreateAutomationConnection(uint,ushort const *,uint)

- ea: `0x18006f310`
- end: `0x18006f62c`
- name: `?CreateAutomationConnection@UiaManagerImpl@@UEAAJIPEBGI@Z`
- size: `796`
- prototype: `__int64 __fastcall(UiaManagerImpl *this, unsigned int, const unsigned __int16 *, DWORD)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001748`
- `0x1800067f8`
- `0x180006edc`
- `0x18000dc9c`
- `0x18000e448`
- `0x18000f070`
- `0x180010974`
- `0x1800114c4`
- `0x180018b1c`
- `0x18001d9c4`
- `0x180026158`
- `0x180031540`
- `0x18004471c`
- `0x18006dbd0`
- `0x18006f310`
- `0x180091010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f3eb`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18006f3eb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f438`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18006f438`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006f46e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18006f46e`
- `ext-ms-onecore-shellchromeapi-l1-1-2!Shell_CreateAutomationByViewId` at `0x18006f59c`
- `ext-ms-onecore-shellchromeapi-l1-1-2!Shell_CreateAutomationByViewId` at `0x18006f59c`

## string_xrefs

- `0x18006f34f`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006f3c4`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006f485`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006f506`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006f5b3`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006f619`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
__int64 __fastcall UiaManagerImpl::CreateAutomationConnection(
        UiaManagerImpl *this,
        unsigned int a2,
        const unsigned __int16 *a3,
        DWORD a4)
{
  __int64 result; // rax
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  const char *v12; // r9
  struct _RTL_CRITICAL_SECTION *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // r15
  char v17; // si
  HSTRING *v18; // rax
  __int64 v19; // rdx
  HRESULT String; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  int v23; // eax
  unsigned int v24; // ebx
  int AutomationByViewId; // eax
  unsigned int v26; // ebx
  int v27; // [rsp+20h] [rbp-68h]
  __int64 v28; // [rsp+30h] [rbp-58h] BYREF
  __int128 v29; // [rsp+38h] [rbp-50h] BYREF
  _BYTE v30[8]; // [rsp+48h] [rbp-40h] BYREF
  __int128 v31; // [rsp+50h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  unsigned int v33; // [rsp+98h] [rbp+10h] BYREF
  char *v34; // [rsp+A0h] [rbp+18h] BYREF

  v33 = a2;
  if ( !a3 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9D,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      v27);
    return 2147942487LL;
  }
  v9 = UiaManagerTraceLoggingProvider::Provider();
  if ( *(_DWORD *)v9 > 4u )
  {
    *(_QWORD *)&v29 = a3;
    LODWORD(v34) = a2;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>>(
      (_DWORD)v9,
      (unsigned int)byte_1800ADA3B,
      v10,
      v11,
      (__int64)&v34,
      (__int64)&v29);
  }
  try
  {
    if ( !UiaManagerSecurityUtils::IsAccessAllowed(1) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA3,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80070005LL,
        v27);
      return 2147942405LL;
    }
    v28 = 0;
    v13 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 776);
    EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 776));
    v34 = (char *)this + 776;
    v15 = std::_Uhash_compare<enum PeerVersionDependentFeature,std::hash<enum PeerVersionDependentFeature>,std::equal_to<enum PeerVersionDependentFeature>>::operator()<enum PeerVersionDependentFeature>(
            v14,
            &v33);
    v16 = std::_Hash<std::_Umap_traits<unsigned int,std::vector<WinEventsManager::ListenerEntry>,std::_Uhash_compare<unsigned int,std::hash<unsigned int>,std::equal_to<unsigned int>>,std::allocator<std::pair<unsigned int const,std::vector<WinEventsManager::ListenerEntry>>>,0>>::_Find<unsigned int>(
            (char *)this + 136,
            &v33,
            v15);
    if ( v16 == *((_QWORD *)this + 18) )
    {
      v17 = 0;
    }
    else
    {
      v28 = 0;
      wil::details::weak_query_policy::query<IUiaWindowRegistration>(*(_QWORD *)(v16 + 24), &v28);
      v17 = 1;
      if ( !v28 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0xB1,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
          (const char *)0x80004005LL,
          v27);
    }
    if ( v13 )
      LeaveCriticalSection(v13);
    if ( v17 )
    {
      v29 = 0;
      v18 = (HSTRING *)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::put(&v29);
      v19 = -1;
      do
        ++v19;
      while ( a3[v19] );
      String = WindowsCreateString(a3, v19, v18);
      v21 = String;
      if ( String < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xBC,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
          (const char *)(unsigned int)String,
          v27);
        std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v29);
        wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v28);
        return v21;
      }
      wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>(
        v30,
        &v28);
      v31 = 0;
      v22 = *((_QWORD *)&v29 + 1);
      if ( *((_QWORD *)&v29 + 1) )
        _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v29 + 1) + 8LL));
      *(_QWORD *)&v31 = v29;
      *((_QWORD *)&v31 + 1) = v22;
      v23 = anonymous_namespace_::DispatchOntoThreadPool__lambda_7763cbfcec9d715fcbad5d3514f50224___(a4);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xC4,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
          (const char *)(unsigned int)v23,
          v27);
        std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v29);
        wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v28);
        return v24;
      }
      std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v29);
LABEL_26:
      wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v28);
      return 0;
    }
    if ( (unsigned __int8)IsShell_CreateAutomationByViewIdPresent() )
    {
      AutomationByViewId = Shell_CreateAutomationByViewId(a2, a3);
      v26 = AutomationByViewId;
      if ( AutomationByViewId < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xCC,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
          (const char *)(unsigned int)AutomationByViewId,
          v27);
        wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v28);
        return v26;
      }
      goto LABEL_26;
    }
    wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v28);
    result = 2147943568LL;
  }
  catch ( ... )
  {
    LODWORD(v34) = wil::details::in1diag3::Return_CaughtException(
                     retaddr,
                     (void *)0xD6,
                     (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                     v12);
    return (unsigned int)v34;
  }
  return result;
}

```

## disassembly

```asm
0x18006f310  mov     [rsp+arg_0], rbx
0x18006f315  mov     [rsp+arg_18], rsi
0x18006f31a  mov     [rsp+arg_8], edx
0x18006f31e  push    rdi
0x18006f31f  push    r12
0x18006f321  push    r13
0x18006f323  push    r14
0x18006f325  push    r15
0x18006f327  sub     rsp, 60h
0x18006f32b  mov     r12d, r9d
0x18006f32e  mov     rdi, r8
0x18006f331  mov     r14d, edx
0x18006f334  mov     rsi, rcx
0x18006f337  xor     r13d, r13d
0x18006f33a  test    r8, r8
0x18006f33d  jnz     short loc_18006F367
0x18006f33f  mov     rcx, [rsp+88h]; this
0x18006f347  mov     ebx, 80070057h
0x18006f34c  mov     r9d, ebx; char *
0x18006f34f  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f356  mov     edx, 9Dh; void *
0x18006f35b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f360  mov     eax, ebx
0x18006f362  jmp     loc_18006F5F9
0x18006f367  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x18006f36c  mov     ecx, [rax]
0x18006f36e  cmp     ecx, 4
0x18006f371  jbe     short loc_18006F3A6
0x18006f373  mov     qword ptr [rsp+88h+var_50], rdi
0x18006f378  mov     dword ptr [rsp+88h+arg_10], r14d
0x18006f380  lea     rcx, [rsp+88h+var_50]
0x18006f385  mov     [rsp+88h+var_60], rcx
0x18006f38a  lea     rcx, [rsp+88h+arg_10]
0x18006f392  mov     qword ptr [rsp+88h+var_68], rcx; int
0x18006f397  lea     rdx, byte_1800ADA3B
0x18006f39e  mov     rcx, rax
0x18006f3a1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &)
0x18006f3a6  mov     ecx, 1
0x18006f3ab  call    ?IsAccessAllowed@UiaManagerSecurityUtils@@CA_NW4AppContainerAccessCapability@1@@Z; UiaManagerSecurityUtils::IsAccessAllowed(UiaManagerSecurityUtils::AppContainerAccessCapability)
0x18006f3b0  test    al, al
0x18006f3b2  jnz     short loc_18006F3DC
0x18006f3b4  mov     rcx, [rsp+88h]; this
0x18006f3bc  mov     ebx, 80070005h
0x18006f3c1  mov     r9d, ebx; char *
0x18006f3c4  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f3cb  mov     edx, 0A3h; void *
0x18006f3d0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f3d5  mov     eax, ebx
0x18006f3d7  jmp     loc_18006F5F9
0x18006f3dc  mov     [rsp+88h+var_58], r13
0x18006f3e1  lea     rbx, [rsi+308h]
0x18006f3e8  mov     rcx, rbx; lpCriticalSection
0x18006f3eb  call    cs:__imp_EnterCriticalSection
0x18006f3f1  mov     [rsp+88h+arg_10], rbx
0x18006f3f9  lea     rdx, [rsp+88h+arg_8]
0x18006f401  call    ??$?RW4PeerVersionDependentFeature@@@?$_Uhash_compare@W4PeerVersionDependentFeature@@U?$hash@W4PeerVersionDependentFeature@@@std@@U?$equal_to@W4PeerVersionDependentFeature@@@3@@std@@QEBA_KAEBW4PeerVersionDependentFeature@@@Z; std::_Uhash_compare<PeerVersionDependentFeature,std::hash<PeerVersionDependentFeature>,std::equal_to<PeerVersionDependentFeature>>::operator()<PeerVersionDependentFeature>(PeerVersionDependentFeature const &)
0x18006f406  mov     r8, rax
0x18006f409  lea     rcx, [rsi+88h]
0x18006f410  lea     rdx, [rsp+88h+arg_8]
0x18006f418  call    ??$_Find@I@?$_Hash@V?$_Umap_traits@IV?$vector@UListenerEntry@WinEventsManager@@V?$allocator@UListenerEntry@WinEventsManager@@@std@@@std@@V?$_Uhash_compare@IU?$hash@I@std@@U?$equal_to@I@2@@2@V?$allocator@U?$pair@$$CBIV?$vector@UListenerEntry@WinEventsManager@@V?$allocator@UListenerEntry@WinEventsManager@@@std@@@std@@@std@@@2@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBIV?$vector@UListenerEntry@WinEventsManager@@V?$allocator@UListenerEntry@WinEventsManager@@@std@@@std@@@std@@PEAX@1@AEBI_K@Z; std::_Hash<std::_Umap_traits<uint,std::vector<WinEventsManager::ListenerEntry>,std::_Uhash_compare<uint,std::hash<uint>,std::equal_to<uint>>,std::allocator<std::pair<uint const,std::vector<WinEventsManager::ListenerEntry>>>,0>>::_Find<uint>(uint const &,unsigned __int64)
0x18006f41d  mov     r15, rax
0x18006f420  cmp     rax, [rsi+90h]
0x18006f427  jnz     loc_18006F543
0x18006f42d  mov     sil, r13b
0x18006f430  test    rbx, rbx
0x18006f433  jz      short loc_18006F43E
0x18006f435  mov     rcx, rbx; lpCriticalSection
0x18006f438  call    cs:__imp_LeaveCriticalSection
0x18006f43e  test    sil, sil
0x18006f441  jz      loc_18006F58D
0x18006f447  xorps   xmm1, xmm1
0x18006f44a  movdqu  [rsp+88h+var_50], xmm1
0x18006f450  lea     rcx, [rsp+88h+var_50]
0x18006f455  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::put(void)
0x18006f45a  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18006f45e  inc     rdx; length
0x18006f461  cmp     [rdi+rdx*2], r13w
0x18006f466  jnz     short loc_18006F45E
0x18006f468  mov     r8, rax; string
0x18006f46b  mov     rcx, rdi; sourceString
0x18006f46e  call    cs:__imp_WindowsCreateString
0x18006f474  mov     ebx, eax
0x18006f476  test    eax, eax
0x18006f478  jns     short loc_18006F4B3
0x18006f47a  mov     rcx, [rsp+88h]; this
0x18006f482  mov     r9d, eax; char *
0x18006f485  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f48c  mov     edx, 0BCh; void *
0x18006f491  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f496  nop
0x18006f497  lea     rcx, [rsp+88h+var_50]
0x18006f49c  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006f4a1  nop
0x18006f4a2  lea     rcx, [rsp+88h+var_58]
0x18006f4a7  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18006f4ac  mov     eax, ebx
0x18006f4ae  jmp     loc_18006F5F9
0x18006f4b3  lea     rdx, [rsp+88h+var_58]
0x18006f4b8  lea     rcx, [rsp+88h+var_40]
0x18006f4bd  call    ??0?$com_ptr_t@UIUiaWindowRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>(wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy> const &)
0x18006f4c2  xorps   xmm0, xmm0
0x18006f4c5  movdqu  [rsp+88h+var_38], xmm0
0x18006f4cb  mov     rcx, qword ptr [rsp+88h+var_50+8]
0x18006f4d0  test    rcx, rcx
0x18006f4d3  jz      short loc_18006F4D9
0x18006f4d5  lock inc dword ptr [rcx+8]
0x18006f4d9  mov     rax, qword ptr [rsp+88h+var_50]
0x18006f4de  mov     qword ptr [rsp+88h+var_38], rax
0x18006f4e3  mov     qword ptr [rsp+88h+var_38+8], rcx
0x18006f4e8  lea     rdx, [rsp+88h+var_40]
0x18006f4ed  mov     ecx, r12d; dwMilliseconds
0x18006f4f0  call    _anonymous_namespace___DispatchOntoThreadPool__lambda_7763cbfcec9d715fcbad5d3514f50224___
0x18006f4f5  mov     ebx, eax
0x18006f4f7  test    eax, eax
0x18006f4f9  jns     short loc_18006F534
0x18006f4fb  mov     rcx, [rsp+88h]; this
0x18006f503  mov     r9d, eax; char *
0x18006f506  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f50d  mov     edx, 0C4h; void *
0x18006f512  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f517  nop
0x18006f518  lea     rcx, [rsp+88h+var_50]
0x18006f51d  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006f522  nop
0x18006f523  lea     rcx, [rsp+88h+var_58]
0x18006f528  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18006f52d  mov     eax, ebx
0x18006f52f  jmp     loc_18006F5F9
0x18006f534  lea     rcx, [rsp+88h+var_50]
0x18006f539  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18006f53e  jmp     loc_18006F5D3
0x18006f543  mov     rcx, [rsp+88h+var_58]
0x18006f548  mov     [rsp+88h+var_58], r13
0x18006f54d  test    rcx, rcx
0x18006f550  jz      short loc_18006F55F
0x18006f552  mov     rax, [rcx]
0x18006f555  mov     rax, [rax+10h]
0x18006f559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006f55e  nop
0x18006f55f  lea     rdx, [rsp+88h+var_58]
0x18006f564  mov     rcx, [r15+18h]
0x18006f568  call    ??$query@UIUiaWindowRegistration@@@weak_query_policy@details@wil@@SAJPEAUIWeakReference@@PEAPEAUIUiaWindowRegistration@@@Z; wil::details::weak_query_policy::query<IUiaWindowRegistration>(IWeakReference *,IUiaWindowRegistration * *)
0x18006f56d  cmp     [rsp+88h+var_58], r13
0x18006f572  setz    al
0x18006f575  mov     sil, 1
0x18006f578  mov     rcx, [rsp+88h]; this
0x18006f580  test    al, al
0x18006f582  jnz     loc_18006F613
0x18006f588  jmp     loc_18006F430
0x18006f58d  call    IsShell_CreateAutomationByViewIdPresent
0x18006f592  test    al, al
0x18006f594  jz      short loc_18006F5E1
0x18006f596  mov     rdx, rdi
0x18006f599  mov     ecx, r14d
0x18006f59c  call    cs:__imp_Shell_CreateAutomationByViewId
0x18006f5a2  mov     ebx, eax
0x18006f5a4  test    eax, eax
0x18006f5a6  jns     short loc_18006F5D3
0x18006f5a8  mov     rcx, [rsp+88h]; this
0x18006f5b0  mov     r9d, eax; char *
0x18006f5b3  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f5ba  mov     edx, 0CCh; void *
0x18006f5bf  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18006f5c4  nop
0x18006f5c5  lea     rcx, [rsp+88h+var_58]
0x18006f5ca  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18006f5cf  mov     eax, ebx
0x18006f5d1  jmp     short loc_18006F5F9
0x18006f5d3  lea     rcx, [rsp+88h+var_58]
0x18006f5d8  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18006f5dd  xor     eax, eax
0x18006f5df  jmp     short loc_18006F5F9
0x18006f5e1  lea     rcx, [rsp+88h+var_58]
0x18006f5e6  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18006f5eb  mov     eax, 80070490h
0x18006f5f0  jmp     short loc_18006F5F9
0x18006f5f2  mov     eax, dword ptr [rsp+88h+arg_10]
0x18006f5f9  lea     r11, [rsp+88h+var_28]
0x18006f5fe  mov     rbx, [r11+30h]
0x18006f602  mov     rsi, [r11+48h]
0x18006f606  mov     rsp, r11
0x18006f609  pop     r15
0x18006f60b  pop     r14
0x18006f60d  pop     r13
0x18006f60f  pop     r12
0x18006f611  pop     rdi
0x18006f612  retn
0x18006f613  mov     r9d, 80004005h; char *
0x18006f619  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f620  mov     edx, 0B1h; void *
0x18006f625  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
