# UiaManagerCrossMachineProxyFactory::CreateProxy(_GUID,IUiaManagerCrossMachineConnection * *)

- ea: `0x180071330`
- end: `0x1800714dc`
- name: `?CreateProxy@UiaManagerCrossMachineProxyFactory@@UEAAJU_GUID@@PEAPEAUIUiaManagerCrossMachineConnection@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(UiaManagerCrossMachineProxyFactory *__hidden this, struct _GUID *__struct_ptr, struct IUiaManagerCrossMachineConnection **)`
- caller_count: `0`
- callee_count: `15`
- tags: `registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x1800054f8`
- `0x1800065c4`
- `0x1800067f8`
- `0x180006edc`
- `0x1800092c0`
- `0x1800114c4`
- `0x180018868`
- `0x180018b1c`
- `0x18002a0a8`
- `0x18002ab8c`
- `0x18002ac10`
- `0x180030a2c`
- `0x180031540`
- `0x18003a15c`
- `0x180071330`

## import_xrefs

- `msvcp_win!_Mtx_unlock` at `0x1800714c1`
- `msvcp_win!_Mtx_unlock` at `0x1800714c1`

## string_xrefs

- `0x180071363`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxyfactory.cpp`
- `0x180071386`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxyfactory.cpp`
- `0x1800714ac`: `onecore\windows\accessibletech\uiamanager\dll\uiamanagercrossmachineproxyfactory.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall UiaManagerCrossMachineProxyFactory::CreateProxy(
        UiaManagerCrossMachineProxyFactory *this,
        struct _GUID *a2,
        struct IUiaManagerCrossMachineConnection **a3)
{
  const char *v6; // r9
  __int64 result; // rax
  __int64 v8; // rcx
  __int64 v9; // rax
  __int64 v10; // rdx
  struct IUiaManagerCrossMachineConnection *v11; // rax
  __int64 Server; // rax
  __int64 v13; // rax
  __int64 *v14; // rcx
  __int64 v15; // rax
  struct IUiaManagerCrossMachineConnection *v16; // rax
  int v17[2]; // [rsp+20h] [rbp-68h] BYREF
  _BYTE v18[8]; // [rsp+28h] [rbp-60h] BYREF
  _BYTE v19[8]; // [rsp+30h] [rbp-58h] BYREF
  _BYTE v20[16]; // [rsp+38h] [rbp-50h] BYREF
  char *v21; // [rsp+48h] [rbp-40h]
  _BYTE v22[56]; // [rsp+50h] [rbp-38h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  try
  {
    if ( UiaManagerSecurityUtils::IsAccessAllowed(1) )
    {
      if ( !a3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x12,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxyfactory.cpp",
          (const char *)0x80070057LL,
          v17[0]);
      *a3 = 0;
      v21 = (char *)this + 80;
      std::_Mutex_base::lock((UiaManagerCrossMachineProxyFactory *)((char *)this + 80));
      v9 = std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(v8, a2);
      v10 = *(_QWORD *)(std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::_Find_last<_GUID>(
                          (char *)this + 16,
                          v20,
                          a2,
                          v9)
                      + 8);
      if ( !v10 )
        v10 = *((_QWORD *)this + 3);
      if ( v10 == *((_QWORD *)this + 3) )
      {
        Server = IoDispatcher::CreateServer(v18, a2);
        v13 = std::shared_ptr<IoDispatcher>::shared_ptr<IoDispatcher>(v20, Server);
        v14 = (__int64 *)UiaManagerCrossMachineProxy::New(v19, a2, v13);
        v15 = *v14;
        *v14 = 0;
        if ( v15 )
          *(_QWORD *)v17 = v15 + 32;
        else
          *(_QWORD *)v17 = 0;
        Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(v19);
        std::unique_ptr<IoDispatcher>::~unique_ptr<IoDispatcher>(v18);
        std::unordered_map<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>::_Insert_or_assign<_GUID const &,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy> &>(
          (char *)this + 16,
          v22,
          a2,
          v17);
        v16 = *(struct IUiaManagerCrossMachineConnection **)v17;
        *(_QWORD *)v17 = 0;
        *a3 = v16;
      }
      else
      {
        wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>(
          v17,
          v10 + 32);
        v11 = *(struct IUiaManagerCrossMachineConnection **)v17;
        *(_QWORD *)v17 = 0;
        *a3 = v11;
      }
      wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(v17);
      if ( !*a3 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x26,
          (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxyfactory.cpp",
          (const char *)0x8000FFFFLL,
          v17[0]);
      _Mtx_unlock((UiaManagerCrossMachineProxyFactory *)((char *)this + 80));
      result = 0;
    }
    else
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxyfactory.cpp",
        (const char *)0x80070005LL,
        v17[0]);
      result = 2147942405LL;
    }
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0x2A,
                           (unsigned int)"onecore\\windows\\accessibletech\\uiamanager\\dll\\uiamanagercrossmachineproxyfactory.cpp",
                           v6);
  }
  return result;
}

```

## disassembly

```asm
0x180071330  push    rbx
0x180071332  push    rsi
0x180071333  push    rdi
0x180071334  push    r14
0x180071336  push    r15
0x180071338  sub     rsp, 60h
0x18007133c  mov     rbx, r8
0x18007133f  mov     r14, rdx
0x180071342  mov     rsi, rcx
0x180071345  mov     ecx, 1
0x18007134a  call    ?IsAccessAllowed@UiaManagerSecurityUtils@@CA_NW4AppContainerAccessCapability@1@@Z; UiaManagerSecurityUtils::IsAccessAllowed(UiaManagerSecurityUtils::AppContainerAccessCapability)
0x18007134f  mov     rcx, [rsp+88h]; this
0x180071357  test    al, al
0x180071359  jnz     short loc_18007137B
0x18007135b  mov     ebx, 80070005h
0x180071360  mov     r9d, ebx; char *
0x180071363  lea     r8, aOnecoreWindows_1; "onecore\\windows\\accessibletech\\uiama"...
0x18007136a  mov     edx, 10h; void *
0x18007136f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180071374  mov     eax, ebx
0x180071376  jmp     loc_1800714CF
0x18007137b  test    rbx, rbx
0x18007137e  jnz     short loc_180071395
0x180071380  mov     r9d, 80070057h; char *
0x180071386  lea     r8, aOnecoreWindows_1; "onecore\\windows\\accessibletech\\uiama"...
0x18007138d  lea     edx, [rbx+12h]; void *
0x180071390  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x180071395  mov     qword ptr [rbx], 0
0x18007139c  lea     rdi, [rsi+50h]
0x1800713a0  mov     [rsp+88h+var_40], rdi
0x1800713a5  mov     rcx, rdi; this
0x1800713a8  call    ?lock@_Mutex_base@std@@QEAAXXZ; std::_Mutex_base::lock(void)
0x1800713ad  nop
0x1800713ae  mov     rdx, r14
0x1800713b1  call    ??$?RU_GUID@@@?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@QEBA_KAEBU_GUID@@@Z; std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>::operator()<_GUID>(_GUID const &)
0x1800713b6  mov     r9, rax
0x1800713b9  mov     r8, r14
0x1800713bc  lea     rdx, [rsp+88h+var_50]
0x1800713c1  lea     rcx, [rsi+10h]
0x1800713c5  call    ??$_Find_last@U_GUID@@@?$_Hash@V?$_Umap_traits@U_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@V?$_Uhash_compare@U_GUID@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@3@@std@@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@@5@$0A@@std@@@std@@IEBA?AU?$_Hash_find_last_result@PEAU?$_List_node@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@PEAX@std@@@1@AEBU_GUID@@_K@Z; std::_Hash<std::_Umap_traits<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>,std::_Uhash_compare<_GUID,std::hash<_GUID>,std::equal_to<_GUID>>,std::allocator<std::pair<_GUID const,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>>,0>>::_Find_last<_GUID>(_GUID const &,unsigned __int64)
0x1800713ca  mov     rdx, [rax+8]
0x1800713ce  test    rdx, rdx
0x1800713d1  jnz     short loc_1800713D7
0x1800713d3  mov     rdx, [rsi+18h]
0x1800713d7  cmp     rdx, [rsi+18h]
0x1800713db  jz      short loc_180071401
0x1800713dd  add     rdx, 20h ; ' '
0x1800713e1  lea     rcx, [rsp+88h+var_68]
0x1800713e6  call    ??0?$com_ptr_t@UIUiaWindowRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@AEBV01@@Z; wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy>(wil::com_ptr_t<IUiaWindowRegistration,wil::err_exception_policy> const &)
0x1800713eb  mov     rax, qword ptr [rsp+88h+var_68]
0x1800713f0  mov     qword ptr [rsp+88h+var_68], 0
0x1800713f9  mov     [rbx], rax
0x1800713fc  jmp     loc_18007148E
0x180071401  mov     rdx, r14
0x180071404  lea     rcx, [rsp+88h+var_60]
0x180071409  call    ?CreateServer@IoDispatcher@@SA?AV?$unique_ptr@VIoDispatcher@@U?$default_delete@VIoDispatcher@@@std@@@std@@AEBU_GUID@@@Z; IoDispatcher::CreateServer(_GUID const &)
0x18007140e  nop
0x18007140f  mov     rdx, rax
0x180071412  lea     rcx, [rsp+88h+var_50]
0x180071417  call    ??$?0VIoDispatcher@@U?$default_delete@VIoDispatcher@@@std@@$0A@@?$shared_ptr@VIoDispatcher@@@std@@QEAA@$$QEAV?$unique_ptr@VIoDispatcher@@U?$default_delete@VIoDispatcher@@@std@@@1@@Z; std::shared_ptr<IoDispatcher>::shared_ptr<IoDispatcher>(std::unique_ptr<IoDispatcher> &&)
0x18007141c  mov     r8, rax
0x18007141f  mov     rdx, r14
0x180071422  lea     rcx, [rsp+88h+var_58]
0x180071427  call    ?New@UiaManagerCrossMachineProxy@@SA?AV?$ComPtr@VUiaManagerCrossMachineProxy@@@WRL@Microsoft@@AEBU_GUID@@V?$shared_ptr@VIoDispatcher@@@std@@@Z; UiaManagerCrossMachineProxy::New(_GUID const &,std::shared_ptr<IoDispatcher>)
0x18007142c  mov     rcx, rax
0x18007142f  mov     rax, [rax]
0x180071432  mov     qword ptr [rcx], 0
0x180071439  test    rax, rax
0x18007143c  jz      short loc_180071449
0x18007143e  add     rax, 20h ; ' '
0x180071442  mov     qword ptr [rsp+88h+var_68], rax
0x180071447  jmp     short loc_180071452
0x180071449  mov     qword ptr [rsp+88h+var_68], 0
0x180071452  lea     rcx, [rsp+88h+var_58]
0x180071457  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x18007145c  nop
0x18007145d  lea     rcx, [rsp+88h+var_60]
0x180071462  call    ??1?$unique_ptr@VIoDispatcher@@U?$default_delete@VIoDispatcher@@@std@@@std@@QEAA@XZ; std::unique_ptr<IoDispatcher>::~unique_ptr<IoDispatcher>(void)
0x180071467  lea     r9, [rsp+88h+var_68]
0x18007146c  mov     r8, r14
0x18007146f  lea     rdx, [rsp+88h+var_38]
0x180071474  lea     rcx, [rsi+10h]
0x180071478  call    ??$_Insert_or_assign@AEBU_GUID@@AEAV?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@?$unordered_map@U_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@U?$hash@U_GUID@@@std@@U?$equal_to@U_GUID@@@5@V?$allocator@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@@5@@std@@AEAA?AU?$pair@V?$_List_iterator@V?$_List_val@U?$_List_simple_types@U?$pair@$$CBU_GUID@@V?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@std@@@std@@@std@@@std@@_N@1@AEBU_GUID@@AEAV?$com_ptr_t@UIUiaManagerCrossMachineConnection@@Uerr_exception_policy@wil@@@wil@@@Z; std::unordered_map<_GUID,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy>>::_Insert_or_assign<_GUID const &,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy> &>(_GUID const &,wil::com_ptr_t<IUiaManagerCrossMachineConnection,wil::err_exception_policy> &)
0x18007147d  mov     rax, qword ptr [rsp+88h+var_68]
0x180071482  mov     qword ptr [rsp+88h+var_68], 0; int
0x18007148b  mov     [rbx], rax
0x18007148e  lea     rcx, [rsp+88h+var_68]
0x180071493  call    ??1?$com_ptr_t@UIUiaManagerEndpointRegistration@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>::~com_ptr_t<IUiaManagerEndpointRegistration,wil::err_exception_policy>(void)
0x180071498  mov     rcx, [rsp+88h]; this
0x1800714a0  cmp     qword ptr [rbx], 0
0x1800714a4  jnz     short loc_1800714BE
0x1800714a6  mov     r9d, 8000FFFFh; char *
0x1800714ac  lea     r8, aOnecoreWindows_1; "onecore\\windows\\accessibletech\\uiama"...
0x1800714b3  mov     edx, 26h ; '&'; void *
0x1800714b8  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x1800714be  mov     rcx, rdi; _Mtx_t
0x1800714c1  call    cs:__imp__Mtx_unlock
0x1800714c7  xor     eax, eax
0x1800714c9  jmp     short loc_1800714CF
0x1800714cb  mov     eax, [rsp+88h+var_68]
0x1800714cf  add     rsp, 60h
0x1800714d3  pop     r15
0x1800714d5  pop     r14
0x1800714d7  pop     rdi
0x1800714d8  pop     rsi
0x1800714d9  pop     rbx
0x1800714da  retn
```
