# CWebserviceProxy::InitializeHandlesForImpersonation(std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,std::allocator<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &,std::_List_const_iterator<std::_List_val<std::_List_simple_types<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>>> &)

- ea: `0x18011f6a4`
- end: `0x18011f82d`
- name: `?InitializeHandlesForImpersonation@CWebserviceProxy@@AEAAJAEAV?$list@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@AEAV?$_List_const_iterator@V?$_List_val@U?$_List_simple_types@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@@3@@Z`
- size: `393`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18011f91c`

## callees

- `0x180012398`
- `0x180046ca4`
- `0x18009c310`
- `0x1800a98c0`
- `0x18011b6b0`
- `0x18011f6a4`
- `0x18015e010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f72e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f79a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f7bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f801`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f72e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f79a`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f7bc`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18011f801`

## string_xrefs

- `0x18011f70c`: `onecoreuap\drivers\mobilepc\location\product\core\webserviceproxy\webserviceproxy.cpp`
- `0x18011f778`: `onecoreuap\drivers\mobilepc\location\product\core\webserviceproxy\webserviceproxy.cpp`
- `0x18011f6f9`: `LocationHelper::CreateLocationComponent(LOCATION_COMPONENT_LOCATIONUSERHANDLES, &locationUserHandles)`
- `0x18011f705`: `CWebserviceProxy::InitializeHandlesForImpersonation`
- `0x18011f771`: `CWebserviceProxy::InitializeHandlesForImpersonation`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall CWebserviceProxy::InitializeHandlesForImpersonation(__int64 a1, _QWORD **a2, _QWORD *a3)
{
  int v5; // eax
  unsigned int v6; // ebx
  int v8; // eax
  unsigned int v9; // ebx
  unsigned int v10; // eax
  __int64 v11; // rbx
  _QWORD *v12; // rdx
  wil::details *v13; // [rsp+28h] [rbp-30h]
  __int64 v14; // [rsp+30h] [rbp-28h] BYREF
  void *Block; // [rsp+38h] [rbp-20h] BYREF
  unsigned int v16; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+58h] [rbp+0h]

  v16 = 0;
  Block = 0;
  v14 = 0;
  v5 = LocationHelper::CreateLocationComponent<ILocationUserHandles>(a1, &v14);
  v6 = v5;
  if ( v5 >= 0 )
  {
    v8 = (*(__int64 (__fastcall **)(__int64, unsigned int *, void **))(*(_QWORD *)v14 + 40LL))(v14, &v16, &Block);
    v9 = v8;
    if ( v8 >= 0 )
    {
      v10 = v16;
      if ( v16 )
      {
        v11 = 0;
        while ( 1 )
        {
          v12 = *a2;
          if ( (unsigned int)v11 >= v10 )
            break;
          std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::_Emplace<void * &>(
            a2,
            v12,
            (char *)Block + 8 * v11);
          v11 = (unsigned int)(v11 + 1);
          v10 = v16;
        }
        *a3 = *v12;
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
        free(Block);
        return 0;
      }
      else
      {
        ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
        free(Block);
        return 2147942632LL;
      }
    }
    else
    {
      LODWORD(v13) = v8;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x54D,
        (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\webserviceproxy\\webserviceproxy.cpp",
        "CWebserviceProxy::InitializeHandlesForImpersonation",
        "locationUserHandles->GetUserHandles(&countUserHandles, reinterpret_cast<HANDLE_PTR**>(&handlesBuffer.m_pData))",
        v13,
        v14);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
      free(Block);
      return v9;
    }
  }
  else
  {
    LODWORD(v13) = v5;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x54C,
      (unsigned int)"onecoreuap\\drivers\\mobilepc\\location\\product\\core\\webserviceproxy\\webserviceproxy.cpp",
      "CWebserviceProxy::InitializeHandlesForImpersonation",
      "LocationHelper::CreateLocationComponent(LOCATION_COMPONENT_LOCATIONUSERHANDLES, &locationUserHandles)",
      v13,
      v14);
    ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v14);
    free(Block);
    return v6;
  }
}

```

## disassembly

```asm
0x18011f6a4  mov     r11, rsp
0x18011f6a7  mov     [r11+8], rbx
0x18011f6ab  mov     [r11+20h], rsi
0x18011f6af  push    rdi
0x18011f6b0  sub     rsp, 50h
0x18011f6b4  mov     rax, cs:__security_cookie
0x18011f6bb  xor     rax, rsp
0x18011f6be  mov     [rsp+58h+var_10], rax
0x18011f6c3  mov     rsi, r8
0x18011f6c6  mov     rdi, rdx
0x18011f6c9  mov     [rsp+58h+var_18], 0
0x18011f6d1  mov     qword ptr [r11-20h], 0
0x18011f6d9  mov     qword ptr [r11-28h], 0
0x18011f6e1  lea     rdx, [r11-28h]
0x18011f6e5  call    ??$CreateLocationComponent@UILocationUserHandles@@@LocationHelper@@SAJW4__MIDL___MIDL_itf_locationframework_0000_0000_0001@@PEAPEAUILocationUserHandles@@@Z; LocationHelper::CreateLocationComponent<ILocationUserHandles>(__MIDL___MIDL_itf_locationframework_0000_0000_0001,ILocationUserHandles * *)
0x18011f6ea  mov     ebx, eax
0x18011f6ec  test    eax, eax
0x18011f6ee  jns     short loc_18011F73B
0x18011f6f0  mov     rcx, [rsp+58h]; this
0x18011f6f5  mov     dword ptr [rsp+58h+var_30], eax; wil::details *
0x18011f6f9  lea     rax, aLocationhelper_8; "LocationHelper::CreateLocationComponent"...
0x18011f700  mov     [rsp+58h+var_38], rax; char *
0x18011f705  lea     r9, aCwebservicepro_2; "CWebserviceProxy::InitializeHandlesForI"...
0x18011f70c  lea     r8, aOnecoreuapDriv_101; "onecoreuap\\drivers\\mobilepc\\location"...
0x18011f713  mov     edx, 54Ch; void *
0x18011f718  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18011f71d  nop
0x18011f71e  lea     rcx, [rsp+58h+var_28]
0x18011f723  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18011f728  nop
0x18011f729  mov     rcx, [rsp+58h+Block]; Block
0x18011f72e  call    cs:__imp_free
0x18011f734  mov     eax, ebx
0x18011f736  jmp     loc_18011F80F
0x18011f73b  mov     rcx, [rsp+58h+var_28]
0x18011f740  mov     rax, [rcx]
0x18011f743  lea     r8, [rsp+58h+Block]
0x18011f748  lea     rdx, [rsp+58h+var_18]
0x18011f74d  mov     rax, [rax+28h]
0x18011f751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011f756  mov     ebx, eax
0x18011f758  test    eax, eax
0x18011f75a  jns     short loc_18011F7A4
0x18011f75c  mov     rcx, [rsp+58h]; this
0x18011f761  mov     dword ptr [rsp+58h+var_30], eax; wil::details *
0x18011f765  lea     rax, aLocationuserha_1; "locationUserHandles->GetUserHandles(&co"...
0x18011f76c  mov     [rsp+58h+var_38], rax; char *
0x18011f771  lea     r9, aCwebservicepro_2; "CWebserviceProxy::InitializeHandlesForI"...
0x18011f778  lea     r8, aOnecoreuapDriv_101; "onecoreuap\\drivers\\mobilepc\\location"...
0x18011f77f  mov     edx, 54Dh; void *
0x18011f784  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18011f789  nop
0x18011f78a  lea     rcx, [rsp+58h+var_28]
0x18011f78f  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18011f794  nop
0x18011f795  mov     rcx, [rsp+58h+Block]; Block
0x18011f79a  call    cs:__imp_free
0x18011f7a0  mov     eax, ebx
0x18011f7a2  jmp     short loc_18011F80F
0x18011f7a4  mov     eax, [rsp+58h+var_18]
0x18011f7a8  test    eax, eax
0x18011f7aa  jnz     short loc_18011F7C9
0x18011f7ac  lea     rcx, [rsp+58h+var_28]
0x18011f7b1  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18011f7b6  nop
0x18011f7b7  mov     rcx, [rsp+58h+Block]; Block
0x18011f7bc  call    cs:__imp_free
0x18011f7c2  mov     eax, 800700E8h
0x18011f7c7  jmp     short loc_18011F80F
0x18011f7c9  xor     ebx, ebx
0x18011f7cb  mov     rdx, [rdi]
0x18011f7ce  cmp     ebx, eax
0x18011f7d0  jnb     short loc_18011F7EB
0x18011f7d2  mov     rax, [rsp+58h+Block]
0x18011f7d7  lea     r8, [rax+rbx*8]
0x18011f7db  mov     rcx, rdi
0x18011f7de  call    ??$_Emplace@AEAPEAX@?$list@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@V?$allocator@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@std@@@std@@QEAAPEAU?$_List_node@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@PEAX@1@QEAU21@AEAPEAX@Z; std::list<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::_Emplace<void * &>(std::_List_node<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>,void *> * const,void * &)
0x18011f7e3  inc     ebx
0x18011f7e5  mov     eax, [rsp+58h+var_18]
0x18011f7e9  jmp     short loc_18011F7CB
0x18011f7eb  mov     rax, [rdx]
0x18011f7ee  mov     [rsi], rax
0x18011f7f1  lea     rcx, [rsp+58h+var_28]
0x18011f7f6  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18011f7fb  nop
0x18011f7fc  mov     rcx, [rsp+58h+Block]; Block
0x18011f801  call    cs:__imp_free
0x18011f807  xor     eax, eax
0x18011f809  jmp     short loc_18011F80F
0x18011f80b  mov     eax, [rsp+58h+var_18]
0x18011f80f  mov     rcx, [rsp+58h+var_10]
0x18011f814  xor     rcx, rsp; StackCookie
0x18011f817  call    __security_check_cookie
0x18011f81c  mov     rbx, [rsp+58h+arg_0]
0x18011f821  mov     rsi, [rsp+58h+arg_18]
0x18011f826  add     rsp, 50h
0x18011f82a  pop     rdi
0x18011f82b  retn
```
