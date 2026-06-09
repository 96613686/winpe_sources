# UiaManagerImpl::GetCrossMachineServices(_GUID,IUiaCrossMachineServices * *)

- ea: `0x18006f6c0`
- end: `0x18006f7f2`
- name: `?GetCrossMachineServices@UiaManagerImpl@@UEAAJU_GUID@@PEAPEAUIUiaCrossMachineServices@@@Z`
- size: `306`
- prototype: `__int64 __fastcall(UiaManagerImpl *this, struct _GUID *, struct IUiaCrossMachineServices **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x1800065c4`
- `0x18000dc9c`
- `0x18000e3f0`
- `0x18000ec30`
- `0x180010c50`
- `0x1800114c4`
- `0x180018868`
- `0x180031540`
- `0x180044188`
- `0x18006eba0`
- `0x18006f6c0`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x18006f789`
- `msvcp_win!_Mtx_unlock` at `0x18006f789`

## string_xrefs

- `0x18006f7c8`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`
- `0x18006f7df`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagerimpl.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall UiaManagerImpl::GetCrossMachineServices(
        UiaManagerImpl *this,
        struct _GUID *a2,
        struct IUiaCrossMachineServices **a3)
{
  const struct _tlgProvider_t *v6; // rax
  int v7; // r8d
  int v8; // r9d
  std::_Mutex_base *v9; // rbx
  __int64 v10; // rcx
  __int64 v11; // rax
  __int64 v12; // rax
  struct IUiaCrossMachineServices *v13; // rax
  const char *v14; // r9
  __int64 result; // rax
  int v16; // [rsp+20h] [rbp-48h]
  struct _GUID *v17; // [rsp+30h] [rbp-38h] BYREF
  struct IUiaCrossMachineServices *v18; // [rsp+38h] [rbp-30h] BYREF
  char v19; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *a3 = 0;
  try
  {
    if ( !UiaManagerSecurityUtils::IsAccessAllowed(1) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x287,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80070005LL,
        v16);
    if ( !memcmp_0(a2, &GUID_NULL, 0x10u) )
      wil::details::in1diag3::Throw_Hr(
        retaddr,
        (void *)0x289,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
        (const char *)0x80070057LL,
        v16);
    v6 = UiaManagerTraceLoggingProvider::Provider();
    if ( *(_DWORD *)v6 > 4u )
    {
      v17 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(
        (_DWORD)v6,
        (unsigned int)byte_1800AD649,
        v7,
        v8,
        (__int64)&v17);
    }
    v9 = (UiaManagerImpl *)((char *)this + 584);
    std::_Mutex_base::lock(v9);
    v11 = std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(v10, a2);
    v12 = std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>>>,0>>::_Find<_GUID>(
            (char *)v9 + 80,
            a2,
            v11);
    if ( v12 == *((_QWORD *)v9 + 11) )
    {
      v19 = 0;
    }
    else
    {
      wil::com_ptr_t<IMessageSession,wil::err_exception_policy>::com_ptr_t<IMessageSession,wil::err_exception_policy>(
        &v18,
        *(_QWORD *)(v12 + 32));
      v19 = 1;
    }
    _Mtx_unlock(v9);
    if ( v19 )
    {
      v13 = v18;
      v18 = 0;
      *a3 = v13;
    }
    std::optional<wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::~optional<wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>(&v18);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x297,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagerimpl.cpp",
                           v14);
  }
  return result;
}

```

## disassembly

```asm
0x18006f6c0  push    rbx
0x18006f6c2  push    rsi
0x18006f6c3  push    rdi
0x18006f6c4  sub     rsp, 50h
0x18006f6c8  mov     rsi, r8
0x18006f6cb  mov     rdi, rdx
0x18006f6ce  mov     rbx, rcx
0x18006f6d1  mov     qword ptr [r8], 0
0x18006f6d8  mov     ecx, 1
0x18006f6dd  call    ?IsAccessAllowed@UiaManagerSecurityUtils@@CA_NW4AppContainerAccessCapability@1@@Z; UiaManagerSecurityUtils::IsAccessAllowed(UiaManagerSecurityUtils::AppContainerAccessCapability)
0x18006f6e2  mov     rcx, [rsp+68h]; this
0x18006f6e7  test    al, al
0x18006f6e9  jz      loc_18006F7C2
0x18006f6ef  mov     r8d, 10h; Size
0x18006f6f5  lea     rdx, GUID_NULL; Buf2
0x18006f6fc  mov     rcx, rdi; Buf1
0x18006f6ff  call    memcmp_0
0x18006f704  test    eax, eax
0x18006f706  setz    al
0x18006f709  mov     rcx, [rsp+68h]; this
0x18006f70e  test    al, al
0x18006f710  jnz     loc_18006F7D9
0x18006f716  call    ?Provider@UiaManagerTraceLoggingProvider@@SAPEBU_tlgProvider_t@@XZ; UiaManagerTraceLoggingProvider::Provider(void)
0x18006f71b  mov     ecx, [rax]
0x18006f71d  cmp     ecx, 4
0x18006f720  jbe     short loc_18006F740
0x18006f722  mov     [rsp+68h+var_38], rdi
0x18006f727  lea     rcx, [rsp+68h+var_38]
0x18006f72c  mov     qword ptr [rsp+68h+var_48], rcx
0x18006f731  lea     rdx, byte_1800AD649
0x18006f738  mov     rcx, rax
0x18006f73b  call    ??$Write@U?$_tlgWrapperByRef@$0BA@@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByRef@$0BA@@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByRef<16>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByRef<16> const &)
0x18006f740  add     rbx, 248h
0x18006f747  mov     rcx, rbx; this
0x18006f74a  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x18006f74f  mov     rdx, rdi
0x18006f752  call    ??$?RU_GUID@@@?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@QEBA_KAEBU_GUID@@@Z; std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(_GUID const &)
0x18006f757  mov     r8, rax
0x18006f75a  lea     rcx, [rbx+50h]
0x18006f75e  mov     rdx, rdi
0x18006f761  call    ??$_Find@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIUiaCrossMachineServices@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaCrossMachineServices@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@AEBAPEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaCrossMachineServices@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaCrossMachineServices,wil::err_exception_policy>>>,0>>::_Find<_GUID>(_GUID const &,unsigned __int64)
0x18006f766  cmp     rax, [rbx+58h]
0x18006f76a  jnz     short loc_18006F773
0x18006f76c  mov     [rsp+68h+var_28], 0
0x18006f771  jmp     short loc_18006F786
0x18006f773  mov     rdx, [rax+20h]
0x18006f777  lea     rcx, [rsp+68h+var_30]
0x18006f77c  call    ??0?$com_ptr_t@UIMessageSession@@Uerr_exception_policy@wil@@@wil@@QEAA@PEAUIMessageSession@@@Z; wil::com_ptr_t<IMessageSession,wil::err_exception_policy>::com_ptr_t<IMessageSession,wil::err_exception_policy>(IMessageSession *)
0x18006f781  mov     [rsp+68h+var_28], 1
0x18006f786  mov     rcx, rbx; _Mtx_t
0x18006f789  call    cs:__imp__Mtx_unlock
0x18006f78f  nop
0x18006f790  cmp     [rsp+68h+var_28], 0
0x18006f795  jz      short loc_18006F7A8
0x18006f797  mov     rax, [rsp+68h+var_30]
0x18006f79c  mov     [rsp+68h+var_30], 0
0x18006f7a5  mov     [rsi], rax
0x18006f7a8  lea     rcx, [rsp+68h+var_30]
0x18006f7ad  call    ??1?$optional@V?$com_ptr_t@UIWeakReference@@Uerr_exception_policy@wil@@@wil@@@std@@QEAA@XZ; std::optional<wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>::~optional<wil::com_ptr_t<IWeakReference,wil::err_exception_policy>>(void)
0x18006f7b2  xor     eax, eax
0x18006f7b4  jmp     short loc_18006F7BA
0x18006f7b6  mov     eax, dword ptr [rsp+68h+var_38]
0x18006f7ba  add     rsp, 50h
0x18006f7be  pop     rdi
0x18006f7bf  pop     rsi
0x18006f7c0  pop     rbx
0x18006f7c1  retn
0x18006f7c2  mov     r9d, 80070005h; char *
0x18006f7c8  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f7cf  mov     edx, 287h; void *
0x18006f7d4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18006f7d9  mov     r9d, 80070057h; char *
0x18006f7df  lea     r8, aOnecoreWindows_0; "onecore\\windows\\accessibletech\\uiama"...
0x18006f7e6  mov     edx, 289h; void *
0x18006f7eb  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
