# UiaManagerImpl::CreateAutomationConnection(_GUID,ushort const *,uint)

- ea: `0x1800136f0`
- end: `0x180013992`
- name: `?CreateAutomationConnection@UiaManagerImpl@@UEAAJU_GUID@@PEBGI@Z`
- size: `674`
- prototype: `__int64 __fastcall(UiaManagerImpl *this, struct _GUID *, const unsigned __int16 *, DWORD)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x180001e34`
- `0x18000656c`
- `0x1800065c4`
- `0x1800067f8`
- `0x180006edc`
- `0x18000dc9c`
- `0x1800114c4`
- `0x1800136f0`
- `0x180018868`
- `0x180018b1c`
- `0x18001d9c4`
- `0x180026158`
- `0x180044188`
- `0x18006df9c`
- `0x18006ed68`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18001383f`
- `msvcp_win!_Mtx_unlock` at `0x18001394b`
- `msvcp_win!_Mtx_unlock` at `0x18001383f`
- `msvcp_win!_Mtx_unlock` at `0x18001394b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001386c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001386c`

## string_xrefs

- `0x180013720`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013761`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x1800137d0`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013883`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013904`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x180013961`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall UiaManagerImpl::CreateAutomationConnection(
        UiaManagerImpl *this,
        struct _GUID *a2,
        const unsigned __int16 *a3,
        DWORD a4)
{
  __int64 result; // rax
  const struct _tlgProvider_t *v9; // rax
  int v10; // r8d
  int v11; // r9d
  const char *v12; // r9
  std::_Mutex_base *v13; // rbx
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rax
  HSTRING *v17; // rax
  __int64 v18; // rdx
  HRESULT String; // eax
  unsigned int v20; // ebx
  unsigned __int64 v21; // rdx
  int v22; // eax
  unsigned int v23; // ebx
  int v24; // [rsp+20h] [rbp-78h]
  __int64 v25; // [rsp+30h] [rbp-68h] BYREF
  __int128 v26; // [rsp+38h] [rbp-60h] BYREF
  int v27[2]; // [rsp+48h] [rbp-50h] BYREF
  _BYTE v28[8]; // [rsp+50h] [rbp-48h] BYREF
  unsigned __int128 v29; // [rsp+58h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( a3 )
  {
    if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x1A4,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80070057LL,
        v24);
      return 2147942487LL;
    }
    else
    {
      v9 = UiaManagerTraceLoggingProvider::Provider();
      if ( *(_DWORD *)v9 > 4u )
      {
        *(_QWORD *)&v26 = a3;
        *(_QWORD *)v27 = a2;
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<unsigned short>>(
          (_DWORD)v9,
          (unsigned int)&unk_1800AD7F8,
          v10,
          v11,
          (__int64)v27,
          (__int64)&v26);
      }
      try
      {
        if ( UiaManagerSecurityUtils::IsAccessAllowed(1) )
        {
          v25 = 0;
          v13 = (UiaManagerImpl *)((char *)this + 176);
          *(_QWORD *)v27 = &v25;
          *(_QWORD *)&v26 = v13;
          std::_Mutex_base::lock(v13);
          v15 = std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(v14, a2);
          v16 = std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Find<_GUID>(
                  (char *)v13 + 80,
                  a2,
                  v15);
          if ( v16 == *((_QWORD *)v13 + 11) )
          {
            _Mtx_unlock(v13);
            wil::details::in1diag3::Return_Hr(
              retaddr,
              (void *)0x1B2,
              (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
              (const char *)0x80004005LL,
              v24);
            wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v25);
            result = 2147500037LL;
          }
          else
          {
            lambda_1412af96d7ce195e535fa64f49a367fe_::operator()(v27, v16 + 32);
            _Mtx_unlock(v13);
            v26 = 0;
            v17 = (HSTRING *)wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&long WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::put(&v26);
            v18 = -1;
            do
              ++v18;
            while ( a3[v18] );
            String = WindowsCreateString(a3, v18, v17);
            v20 = String;
            if ( String >= 0 )
            {
              wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>(
                v28,
                &v25);
              v29 = 0;
              v21 = *((_QWORD *)&v26 + 1);
              if ( *((_QWORD *)&v26 + 1) )
                _InterlockedIncrement((volatile signed __int32 *)(*((_QWORD *)&v26 + 1) + 8LL));
              v29 = __PAIR128__(v21, v26);
              v22 = anonymous_namespace_::DispatchOntoThreadPool__lambda_c3b9f7a6bf3a675a648bda1db91c274b___(a4);
              v23 = v22;
              if ( v22 >= 0 )
              {
                std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v26);
                wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v25);
                result = 0;
              }
              else
              {
                wil::details::in1diag3::Return_Hr(
                  retaddr,
                  (void *)0x1BE,
                  (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                  (const char *)(unsigned int)v22,
                  v24);
                std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v26);
                wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v25);
                result = v23;
              }
            }
            else
            {
              wil::details::in1diag3::Return_Hr(
                retaddr,
                (void *)0x1B8,
                (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                (const char *)(unsigned int)String,
                v24);
              std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(&v26);
              wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(&v25);
              result = v20;
            }
          }
        }
        else
        {
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x1AA,
            (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
            (const char *)0x80070005LL,
            v24);
          result = 2147942405LL;
        }
      }
      catch ( ... )
      {
        return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                               retaddr,
                               (void *)0x1C2,
                               (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                               v12);
      }
    }
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x1A3,
      (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
      (const char *)0x80070057LL,
      v24);
    return 2147942487LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800136f0  push    rbx
0x1800136f2  push    rsi
0x1800136f3  push    rdi
0x1800136f4  push    r14
0x1800136f6  push    r15
0x1800136f8  sub     rsp, 70h
0x1800136fc  mov     r14d, r9d
0x1800136ff  mov     rdi, r8
0x180013702  mov     rsi, rdx
0x180013705  mov     rbx, rcx
0x180013708  xor     r15d, r15d
0x18001370b  test    r8, r8
0x18001370e  jnz     short loc_180013738
0x180013710  mov     rcx, [rsp+98h]; this
0x180013718  mov     ebx, 80070057h
0x18001371d  mov     r9d, ebx; char *
0x180013720  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013727  mov     edx, 1A3h; void *
0x18001372c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013731  mov     eax, ebx
0x180013733  jmp     loc_180013985
0x180013738  mov     r8d, 10h; Size
0x18001373e  lea     rdx, GUID_NULL; Buf2
0x180013745  mov     rcx, rsi; Buf1
0x180013748  call    memcmp_0
0x18001374d  test    eax, eax
0x18001374f  jnz     short loc_180013779
0x180013751  mov     rcx, [rsp+98h]; this
0x180013759  mov     ebx, 80070057h
0x18001375e  mov     r9d, ebx; char *
0x180013761  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013768  mov     edx, 1A4h; void *
0x18001376d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013772  mov     eax, ebx
0x180013774  jmp     loc_180013985
0x180013779  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x18001377e  mov     ecx, [rax]
0x180013780  cmp     ecx, 4
0x180013783  jbe     short loc_1800137B2
0x180013785  mov     qword ptr [rsp+98h+var_60], rdi
0x18001378a  mov     qword ptr [rsp+98h+var_50], rsi
0x18001378f  lea     rcx, [rsp+98h+var_60]
0x180013794  mov     [rsp+98h+var_70], rcx
0x180013799  lea     rcx, [rsp+98h+var_50]
0x18001379e  mov     qword ptr [rsp+98h+var_78], rcx; int
0x1800137a3  lea     rdx, unk_1800AD7F8
0x1800137aa  mov     rcx, rax
0x1800137ad  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &,_tlgWrapSz<ushort> const &)
0x1800137b2  mov     ecx, 1
0x1800137b7  call    ?IsAccessAllowed@UiaManagerSecurityUtils@@CA_NW4AppContainerAccessCapability@1@@Z; UiaManagerSecurityUtils::IsAccessAllowed(UiaManagerSecurityUtils::AppContainerAccessCapability)
0x1800137bc  test    al, al
0x1800137be  jnz     short loc_1800137E8
0x1800137c0  mov     rcx, [rsp+98h]; this
0x1800137c8  mov     ebx, 80070005h
0x1800137cd  mov     r9d, ebx; char *
0x1800137d0  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x1800137d7  mov     edx, 1AAh; void *
0x1800137dc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800137e1  mov     eax, ebx
0x1800137e3  jmp     loc_180013985
0x1800137e8  mov     [rsp+98h+var_68], r15
0x1800137ed  add     rbx, 0B0h
0x1800137f4  lea     rax, [rsp+98h+var_68]
0x1800137f9  mov     qword ptr [rsp+98h+var_50], rax
0x1800137fe  mov     qword ptr [rsp+98h+var_60], rbx
0x180013803  mov     rcx, rbx; this
0x180013806  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18001380b  nop
0x18001380c  mov     rdx, rsi
0x18001380f  call    ??$?RU_GUID@@@?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@QEBA_KAEBU_GUID@@@Z; std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(_GUID const &)
0x180013814  mov     r8, rax
0x180013817  lea     rcx, [rbx+50h]
0x18001381b  mov     rdx, rsi
0x18001381e  call    ??$_Find@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>>,0>>::_Find<_GUID>(_GUID const &,unsigned __int64)
0x180013823  cmp     rax, [rbx+58h]
0x180013827  jz      loc_180013948
0x18001382d  lea     rdx, [rax+20h]
0x180013831  lea     rcx, [rsp+98h+var_50]
0x180013836  call    _lambda_1412af96d7ce195e535fa64f49a367fe___operator__
0x18001383b  nop
0x18001383c  mov     rcx, rbx; _Mtx_t
0x18001383f  call    cs:__imp__Mtx_unlock
0x180013845  xorps   xmm1, xmm1
0x180013848  movdqu  [rsp+98h+var_60], xmm1
0x18001384e  lea     rcx, [rsp+98h+var_60]
0x180013853  call    ?put@?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHSTRING__@@P6AJPEAU1@@Z$1?WindowsDeleteString@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@QEAAPEAPEAUHSTRING__@@XZ; wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<HSTRING__ *,long (*)(HSTRING__ *),&WindowsDeleteString(HSTRING__ *),wistd::integral_constant<unsigned __int64,0>,HSTRING__ *,HSTRING__ *,0,std::nullptr_t>>>>>::put(void)
0x180013858  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001385c  inc     rdx; length
0x18001385f  cmp     [rdi+rdx*2], r15w
0x180013864  jnz     short loc_18001385C
0x180013866  mov     r8, rax; string
0x180013869  mov     rcx, rdi; sourceString
0x18001386c  call    cs:__imp_WindowsCreateString
0x180013872  mov     ebx, eax
0x180013874  test    eax, eax
0x180013876  jns     short loc_1800138B1
0x180013878  mov     rcx, [rsp+98h]; this
0x180013880  mov     r9d, eax; char *
0x180013883  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18001388a  mov     edx, 1B8h; void *
0x18001388f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013894  nop
0x180013895  lea     rcx, [rsp+98h+var_60]
0x18001389a  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x18001389f  nop
0x1800138a0  lea     rcx, [rsp+98h+var_68]
0x1800138a5  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x1800138aa  mov     eax, ebx
0x1800138ac  jmp     loc_180013985
0x1800138b1  lea     rdx, [rsp+98h+var_68]
0x1800138b6  lea     rcx, [rsp+98h+var_48]
0x1800138bb  call    ??0?$com_ptr_t@UIUiaWindowRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>(wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy> const &)
0x1800138c0  xorps   xmm0, xmm0
0x1800138c3  movdqu  [rsp+98h+var_40], xmm0
0x1800138c9  mov     rdx, qword ptr [rsp+98h+var_60+8]
0x1800138ce  test    rdx, rdx
0x1800138d1  jz      short loc_1800138D7
0x1800138d3  lock inc dword ptr [rdx+8]
0x1800138d7  mov     rax, qword ptr [rsp+98h+var_60]
0x1800138dc  mov     qword ptr [rsp+98h+var_40], rax
0x1800138e1  mov     qword ptr [rsp+98h+var_40+8], rdx
0x1800138e6  lea     rdx, [rsp+98h+var_48]
0x1800138eb  mov     ecx, r14d; dwMilliseconds
0x1800138ee  call    _anonymous_namespace___DispatchOntoThreadPool__lambda_c3b9f7a6bf3a675a648bda1db91c274b___
0x1800138f3  mov     ebx, eax
0x1800138f5  test    eax, eax
0x1800138f7  jns     short loc_18001392F
0x1800138f9  mov     rcx, [rsp+98h]; this
0x180013901  mov     r9d, eax; char *
0x180013904  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18001390b  mov     edx, 1BEh; void *
0x180013910  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013915  nop
0x180013916  lea     rcx, [rsp+98h+var_60]
0x18001391b  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180013920  nop
0x180013921  lea     rcx, [rsp+98h+var_68]
0x180013926  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18001392b  mov     eax, ebx
0x18001392d  jmp     short loc_180013985
0x18001392f  lea     rcx, [rsp+98h+var_60]
0x180013934  call    ??1?$shared_ptr@U?$HrResponse@UResponsePayload@SetFocusService@@@@@std@@QEAA@XZ; std::shared_ptr<HrResponse<SetFocusService::ResponsePayload>>::~shared_ptr<HrResponse<SetFocusService::ResponsePayload>>(void)
0x180013939  nop
0x18001393a  lea     rcx, [rsp+98h+var_68]
0x18001393f  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180013944  xor     eax, eax
0x180013946  jmp     short loc_180013985
0x180013948  mov     rcx, rbx; _Mtx_t
0x18001394b  call    cs:__imp__Mtx_unlock
0x180013951  mov     rcx, [rsp+98h]; this
0x180013959  mov     ebx, 80004005h
0x18001395e  mov     r9d, ebx; char *
0x180013961  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x180013968  mov     edx, 1B2h; void *
0x18001396d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180013972  nop
0x180013973  lea     rcx, [rsp+98h+var_68]
0x180013978  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x18001397d  mov     eax, ebx
0x18001397f  jmp     short loc_180013985
0x180013981  mov     eax, dword ptr [rsp+98h+var_68]
0x180013985  add     rsp, 70h
0x180013989  pop     r15
0x18001398b  pop     r14
0x18001398d  pop     rdi
0x18001398e  pop     rsi
0x18001398f  pop     rbx
0x180013990  retn
```
