# InstantiatePasskeyManagerAsync$_ResumeCoro$1

- ea: `0x18011ea40`
- end: `0x18011ef34`
- name: `InstantiatePasskeyManagerAsync$_ResumeCoro$1`
- size: `1268`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `16`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18011ef3c`

## callees

- `0x18001ee7c`
- `0x180024340`
- `0x180042e40`
- `0x180052dfc`
- `0x1800537e0`
- `0x18006b260`
- `0x18006f750`
- `0x18008f570`
- `0x1800d8ab0`
- `0x18011d238`
- `0x18011dd78`
- `0x18011ea40`
- `0x18011fc2c`
- `0x18011fc40`
- `0x18013c090`
- `0x180149010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18011ebd9`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x18011ebd9`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011eb93`
- `api-ms-win-core-com-l1-1-0!CLSIDFromString` at `0x18011eb93`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ec2f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ecc6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ed5d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ee31`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ec2f`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ecc6`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ed5d`
- `api-ms-win-core-com-l1-1-0!CoSetProxyBlanket` at `0x18011ee31`

## string_xrefs

- `0x18011eada`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011eba8`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011ebee`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011ec44`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011ec8a`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011ecdb`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011ed20`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011ed72`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011edb5`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011edf3`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`
- `0x18011ee46`: `onecore\ds\security\fido\ctap\transports_modern\ctaputils.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=17
void __fastcall InstantiatePasskeyManagerAsync__ResumeCoro_1(__int64 a1)
{
  _WORD *v2; // rsi
  int DuplicateHandle; // eax
  __int64 v4; // rdx
  HRESULT v5; // eax
  IUnknown **v6; // r13
  HRESULT ClassObject; // eax
  HRESULT v8; // eax
  int v9; // eax
  HRESULT v10; // eax
  IUnknown **v11; // r12
  int v12; // eax
  HRESULT v13; // eax
  int v14; // eax
  int v15; // eax
  HRESULT v16; // eax
  IUnknown *v17; // rcx
  int ppv; // [rsp+20h] [rbp-C8h]
  int ppva; // [rsp+20h] [rbp-C8h]
  int ppvb; // [rsp+20h] [rbp-C8h]
  int ppvc; // [rsp+20h] [rbp-C8h]
  int ppvd; // [rsp+20h] [rbp-C8h]
  int ppve; // [rsp+20h] [rbp-C8h]
  _BYTE pExceptionObject[56]; // [rsp+78h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+0h]

  v2 = (_WORD *)(a1 + 8);
  switch ( *(_WORD *)(a1 + 8) )
  {
    case 0xFFFF:
    case 1:
    case 3:
      goto LABEL_34;
    case 2:
      *(_QWORD *)(a1 + 16) = 0;
      *(_QWORD *)(a1 + 24) = 0;
      DuplicateHandle = CtapUtilsGetDuplicateHandle(*(HANDLE *)(a1 + 120));
      if ( DuplicateHandle < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2CF,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)DuplicateHandle,
          ppv);
      *(_BYTE *)(a1 + 32) = 0;
      if ( *(_DWORD *)(a1 - 16) == 2 )
      {
        *(_DWORD *)(a1 + 88) = 5672;
        *(_QWORD *)(a1 + 96) = "OneCoreUap\\Internal\\BuildMetadata\\internal\\cppwinrt\\winrt\\windows.foundation.h";
        *(_QWORD *)(a1 + 104) = 0;
        winrt::hresult_canceled::hresult_canceled(
          (winrt::hresult_canceled *)pExceptionObject,
          (const struct winrt::impl::slim_source_location *)(a1 + 88));
        throw (winrt::hresult_canceled *)pExceptionObject;
      }
      *v2 = 4;
      `winrt::resume_background'::`2'::awaitable::await_suspend(retaddr, a1);
      return;
    case 4:
      if ( *(_QWORD *)(a1 + 16) )
        v4 = **(_QWORD **)(a1 + 16);
      else
        v4 = 0;
      wil::impersonate_token(a1 + 40, v4);
      *(_OWORD *)(a1 + 48) = 0;
      v5 = CLSIDFromString(L"{45C7DF48-9B57-4042-98A0-50D84DE24127}", (LPCLSID)(a1 + 48));
      if ( v5 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2D5,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v5,
          ppv);
      v6 = (IUnknown **)(a1 + 64);
      *(_QWORD *)(a1 + 64) = 0;
      ClassObject = CoGetClassObject(
                      (const IID *const)(a1 + 48),
                      0x110004u,
                      0,
                      &GUID_00000001_0000_0000_c000_000000000046,
                      (LPVOID *)(a1 + 64));
      if ( ClassObject < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2DD,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)ClassObject,
          ppva);
      v8 = CoSetProxyBlanket(*v6, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
      if ( v8 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2E5,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v8,
          ppvb);
      v9 = ((__int64 (__fastcall *)(IUnknown *, _QWORD, GUID *, __int64))(*v6)->lpVtbl[1].QueryInterface)(
             *v6,
             0,
             &GUID_00000000_0000_0000_c000_000000000046,
             *(_QWORD *)(a1 + 160) + 8LL);
      if ( v9 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2EA,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v9,
          ppvb);
      v10 = CoSetProxyBlanket(
              *(IUnknown **)(*(_QWORD *)(a1 + 160) + 8LL),
              0xFFFFFFFF,
              0xFFFFFFFF,
              (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
              0,
              3u,
              0,
              0x20u);
      if ( v10 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F2,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v10,
          ppvc);
      v11 = (IUnknown **)(a1 + 72);
      *(_QWORD *)(a1 + 72) = 0;
      v12 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(*(_QWORD *)(a1 + 160) + 8LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 160) + 8LL),
              &GUID_2a5f74ab_6876_4f3e_9643_05fa7070175d,
              a1 + 72);
      if ( v12 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2F7,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v12,
          ppvc);
      v13 = CoSetProxyBlanket(*v11, 0xFFFFFFFF, 0xFFFFFFFF, (OLECHAR *)0xFFFFFFFFFFFFFFFFLL, 0, 3u, 0, 0x20u);
      if ( v13 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x2FF,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v13,
          ppvd);
      v14 = ((__int64 (__fastcall *)(IUnknown *))(*v11)->lpVtbl[1].QueryInterface)(*v11);
      if ( v14 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x301,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v14,
          ppvd);
      v15 = (***(__int64 (__fastcall ****)(_QWORD, GUID *, __int64))(*(_QWORD *)(a1 + 160) + 8LL))(
              *(_QWORD *)(*(_QWORD *)(a1 + 160) + 8LL),
              &GUID_d26bcf6f_b54c_43ff_9f06_d5bf148625f7,
              *(_QWORD *)(a1 + 160) + 24LL);
      if ( v15 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x305,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v15,
          ppvd);
      v16 = CoSetProxyBlanket(
              *(IUnknown **)(*(_QWORD *)(a1 + 160) + 24LL),
              0xFFFFFFFF,
              0xFFFFFFFF,
              (OLECHAR *)0xFFFFFFFFFFFFFFFFLL,
              0,
              2u,
              0,
              0x20u);
      if ( v16 < 0 )
        wil::details::in1diag3::Throw_Hr(
          retaddr,
          (void *)0x30D,
          (unsigned int)"onecore\\ds\\security\\fido\\ctap\\transports_modern\\ctaputils.cpp",
          (const char *)(unsigned int)v16,
          ppve);
      v17 = *v11;
      if ( *v11 )
      {
        *v11 = 0;
        ((void (__fastcall *)(IUnknown *))v17->lpVtbl->Release)(v17);
      }
      wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(a1 + 64);
      wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&void wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(a1 + 40);
      std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a1 + 16);
      *(_QWORD *)(a1 + 80) = a1 - 112;
      *v2 = 0;
      if ( !(unsigned __int8)winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,void *,std::wstring,std::shared_ptr<PluginAuthenticatorInstance>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend() )
        goto LABEL_34;
      return;
    case 5:
      std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(a1 + 16);
LABEL_34:
      winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>> const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>> const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<unsigned char>>,void>(a1 - 112);
      InstantiatePasskeyManagerAsync_::_3_::_parameters_::__parameters_(v2 + 56);
      if ( *(_WORD *)(a1 + 10) )
        operator delete((void *)(a1 - 112));
      break;
    default:
      __debugbreak();
      break;
  }
}

```

## disassembly

```asm
0x18011ea40  mov     r11, rsp
0x18011ea43  mov     [r11+10h], rbx
0x18011ea47  mov     [r11+18h], rsi
0x18011ea4b  mov     [r11+8], rcx
0x18011ea4f  push    rdi
0x18011ea50  push    r12
0x18011ea52  push    r13
0x18011ea54  push    r14
0x18011ea56  push    r15
0x18011ea58  sub     rsp, 0C0h
0x18011ea5f  mov     rax, cs:__security_cookie
0x18011ea66  xor     rax, rsp
0x18011ea69  mov     [rsp+0E8h+var_38], rax
0x18011ea71  mov     rdi, rcx
0x18011ea74  mov     [rsp+0E8h+var_98], rcx
0x18011ea79  lea     rsi, [rdi+8]
0x18011ea7d  mov     [rsp+0E8h+var_88], rsi
0x18011ea82  movzx   eax, word ptr [rsi]
0x18011ea85  mov     [rsp+0E8h+var_A8], ax
0x18011ea8a  inc     ax; switch 7 cases
0x18011ea8d  cmp     ax, 6
0x18011ea91  ja      def_18011EAAC; jumptable 000000018011EAAC default case, case 0
0x18011ea97  movsx   rax, ax
0x18011ea9b  lea     rdx, __ImageBase
0x18011eaa2  mov     ecx, ds:(jpt_18011EAAC - 180000000h)[rdx+rax*4]
0x18011eaa9  add     rcx, rdx
0x18011eaac  jmp     rcx; switch jump
0x18011eaae  xor     ebx, ebx; jumptable 000000018011EAAC case 3
0x18011eab0  jmp     loc_18011EEBE
0x18011eab5  lea     rdx, [rdi+10h]; jumptable 000000018011EAAC case 2
0x18011eab9  xor     ebx, ebx
0x18011eabb  mov     [rdx], rbx
0x18011eabe  mov     [rdi+18h], rbx
0x18011eac2  mov     rcx, [rsi+70h]; hExistingToken
0x18011eac6  call    ?CtapUtilsGetDuplicateHandle@@YAJQEAXAEAV?$shared_any_t@V?$shared_storage@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@@wil@@@Z; CtapUtilsGetDuplicateHandle(void * const,wil::shared_any_t<wil::details::shared_storage<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>> &)
0x18011eacb  mov     rcx, [rsp+0E8h]; this
0x18011ead3  test    eax, eax
0x18011ead5  jns     short loc_18011EAEB
0x18011ead7  mov     r9d, eax; char *
0x18011eada  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011eae1  mov     edx, 2CFh; void *
0x18011eae6  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011eaeb  mov     [rdi+20h], bl
0x18011eaee  mov     eax, [rdi-10h]
0x18011eaf1  nop
0x18011eaf2  cmp     eax, 2
0x18011eaf5  jnz     short loc_18011EB2B
0x18011eaf7  lea     rdx, [rdi+58h]; struct winrt::impl::slim_source_location *
0x18011eafb  mov     dword ptr [rdx], 1628h
0x18011eb01  lea     rax, aOnecoreuapInte_4; "OneCoreUap\\Internal\\BuildMetadata\\in"...
0x18011eb08  mov     [rdi+60h], rax
0x18011eb0c  mov     [rdi+68h], rbx
0x18011eb10  lea     rcx, [rsp+0E8h+pExceptionObject]; this
0x18011eb15  call    ??0hresult_canceled@winrt@@QEAA@AEBUslim_source_location@impl@1@@Z; winrt::hresult_canceled::hresult_canceled(winrt::impl::slim_source_location const &)
0x18011eb1a  lea     rdx, _TI2?AUhresult_canceled@winrt@@; pThrowInfo
0x18011eb21  lea     rcx, [rsp+0E8h+pExceptionObject]; pExceptionObject
0x18011eb26  call    _CxxThrowException_0
0x18011eb2b  mov     eax, 4
0x18011eb30  mov     [rsi], ax
0x18011eb33  mov     rdx, rdi
0x18011eb36  call    ?await_suspend@awaitable@?1??resume_background@winrt@@YA@XZ@QEBAXU?$coroutine_handle@X@experimental@std@@@Z; `winrt::resume_background(void)'::`2'::awaitable::await_suspend(std::experimental::coroutine_handle<void>)
0x18011eb3b  jmp     loc_18011EEE7
0x18011eb40  lea     rcx, [rdi+10h]; jumptable 000000018011EAAC case 5
0x18011eb44  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18011eb49  nop
0x18011eb4a  xor     ebx, ebx
0x18011eb4c  jmp     loc_18011EEBE
0x18011eb51  lea     r15, [rdi+10h]; jumptable 000000018011EAAC case 4
0x18011eb55  mov     rax, [r15]
0x18011eb58  mov     [rsp+0E8h+var_80], rax
0x18011eb5d  xor     ebx, ebx
0x18011eb5f  test    rax, rax
0x18011eb62  jz      short loc_18011EB71
0x18011eb64  mov     rax, [r15]
0x18011eb67  mov     [rsp+0E8h+var_80], rax
0x18011eb6c  mov     rdx, [rax]
0x18011eb6f  jmp     short loc_18011EB74
0x18011eb71  mov     rdx, rbx
0x18011eb74  lea     rcx, [rdi+28h]
0x18011eb78  call    ?impersonate_token@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@@1@PEAX@Z; wil::impersonate_token(void *)
0x18011eb7d  nop
0x18011eb7e  lea     r14, [rdi+30h]
0x18011eb82  xorps   xmm0, xmm0
0x18011eb85  movups  xmmword ptr [r14], xmm0
0x18011eb89  mov     rdx, r14; pclsid
0x18011eb8c  lea     rcx, sz; "{45C7DF48-9B57-4042-98A0-50D84DE24127}"
0x18011eb93  call    cs:__imp_CLSIDFromString
0x18011eb99  mov     rcx, [rsp+0E8h]; this
0x18011eba1  test    eax, eax
0x18011eba3  jns     short loc_18011EBBA
0x18011eba5  mov     r9d, eax; char *
0x18011eba8  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ebaf  mov     edx, 2D5h; void *
0x18011ebb4  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ebba  lea     r13, [rdi+40h]
0x18011ebbe  mov     [r13+0], rbx
0x18011ebc2  mov     [rsp+0E8h+ppv], r13; int
0x18011ebc7  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x18011ebce  xor     r8d, r8d; pvReserved
0x18011ebd1  mov     edx, 110004h; dwClsContext
0x18011ebd6  mov     rcx, r14; rclsid
0x18011ebd9  call    cs:__imp_CoGetClassObject
0x18011ebdf  mov     rcx, [rsp+0E8h]; this
0x18011ebe7  test    eax, eax
0x18011ebe9  jns     short loc_18011EBFF
0x18011ebeb  mov     r9d, eax; char *
0x18011ebee  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ebf5  mov     edx, 2DDh; void *
0x18011ebfa  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ebff  mov     rcx, [r13+0]; pProxy
0x18011ec03  mov     [rsp+0E8h+var_90], rcx
0x18011ec08  mov     [rsp+0E8h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18011ec10  mov     [rsp+0E8h+pAuthInfo], rbx; pAuthInfo
0x18011ec15  mov     [rsp+0E8h+dwImpLevel], 3; dwImpLevel
0x18011ec1d  mov     dword ptr [rsp+0E8h+ppv], ebx; int
0x18011ec21  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011ec25  or      r12d, 0FFFFFFFFh
0x18011ec29  mov     r8d, r12d; dwAuthzSvc
0x18011ec2c  mov     edx, r12d; dwAuthnSvc
0x18011ec2f  call    cs:__imp_CoSetProxyBlanket
0x18011ec35  mov     rcx, [rsp+0E8h]; this
0x18011ec3d  test    eax, eax
0x18011ec3f  jns     short loc_18011EC55
0x18011ec41  mov     r9d, eax; char *
0x18011ec44  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ec4b  mov     edx, 2E5h; void *
0x18011ec50  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ec55  mov     rcx, [r13+0]
0x18011ec59  mov     [rsp+0E8h+var_90], rcx
0x18011ec5e  mov     rax, [rcx]
0x18011ec61  mov     r9, [r14+70h]
0x18011ec65  add     r9, 8
0x18011ec69  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x18011ec70  xor     edx, edx
0x18011ec72  mov     rax, [rax+18h]
0x18011ec76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ec7b  mov     rcx, [rsp+0E8h]; this
0x18011ec83  test    eax, eax
0x18011ec85  jns     short loc_18011EC9B
0x18011ec87  mov     r9d, eax; char *
0x18011ec8a  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ec91  mov     edx, 2EAh; void *
0x18011ec96  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ec9b  mov     rcx, [r14+70h]
0x18011ec9f  mov     [rsp+0E8h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18011eca7  mov     [rsp+0E8h+pAuthInfo], rbx; pAuthInfo
0x18011ecac  mov     [rsp+0E8h+dwImpLevel], 3; dwImpLevel
0x18011ecb4  mov     dword ptr [rsp+0E8h+ppv], ebx; int
0x18011ecb8  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011ecbc  mov     r8d, r12d; dwAuthzSvc
0x18011ecbf  mov     edx, r12d; dwAuthnSvc
0x18011ecc2  mov     rcx, [rcx+8]; pProxy
0x18011ecc6  call    cs:__imp_CoSetProxyBlanket
0x18011eccc  mov     rcx, [rsp+0E8h]; this
0x18011ecd4  test    eax, eax
0x18011ecd6  jns     short loc_18011ECEC
0x18011ecd8  mov     r9d, eax; char *
0x18011ecdb  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ece2  mov     edx, 2F2h; void *
0x18011ece7  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ecec  lea     r12, [rdi+48h]
0x18011ecf0  mov     [r12], rbx
0x18011ecf4  mov     rax, [r14+70h]
0x18011ecf8  mov     rcx, [rax+8]
0x18011ecfc  mov     rax, [rcx]
0x18011ecff  mov     r8, r12
0x18011ed02  lea     rdx, _GUID_2a5f74ab_6876_4f3e_9643_05fa7070175d
0x18011ed09  mov     rax, [rax]
0x18011ed0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ed11  mov     rcx, [rsp+0E8h]; this
0x18011ed19  test    eax, eax
0x18011ed1b  jns     short loc_18011ED31
0x18011ed1d  mov     r9d, eax; char *
0x18011ed20  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ed27  mov     edx, 2F7h; void *
0x18011ed2c  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ed31  mov     rcx, [r12]; pProxy
0x18011ed35  mov     [rsp+0E8h+var_A0], rcx
0x18011ed3a  mov     [rsp+0E8h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18011ed42  mov     [rsp+0E8h+pAuthInfo], rbx; pAuthInfo
0x18011ed47  mov     [rsp+0E8h+dwImpLevel], 3; dwImpLevel
0x18011ed4f  mov     dword ptr [rsp+0E8h+ppv], ebx; int
0x18011ed53  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011ed57  or      edx, 0FFFFFFFFh; dwAuthnSvc
0x18011ed5a  mov     r8d, edx; dwAuthzSvc
0x18011ed5d  call    cs:__imp_CoSetProxyBlanket
0x18011ed63  mov     rcx, [rsp+0E8h]; this
0x18011ed6b  test    eax, eax
0x18011ed6d  jns     short loc_18011ED83
0x18011ed6f  mov     r9d, eax; char *
0x18011ed72  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ed79  mov     edx, 2FFh; void *
0x18011ed7e  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ed83  mov     rcx, [r12]
0x18011ed87  mov     [rsp+0E8h+var_A0], rcx
0x18011ed8c  mov     rax, [rcx]
0x18011ed8f  lea     rdx, [r15+70h]
0x18011ed93  cmp     qword ptr [rdx+18h], 7
0x18011ed98  jbe     short loc_18011ED9D
0x18011ed9a  mov     rdx, [rdx]
0x18011ed9d  mov     rax, [rax+18h]
0x18011eda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011eda6  mov     rcx, [rsp+0E8h]; this
0x18011edae  test    eax, eax
0x18011edb0  jns     short loc_18011EDC6
0x18011edb2  mov     r9d, eax; char *
0x18011edb5  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011edbc  mov     edx, 301h; void *
0x18011edc1  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011edc6  mov     r8, [r14+70h]
0x18011edca  mov     rcx, [r8+8]
0x18011edce  mov     rax, [rcx]
0x18011edd1  add     r8, 18h
0x18011edd5  lea     rdx, _GUID_d26bcf6f_b54c_43ff_9f06_d5bf148625f7
0x18011eddc  mov     rax, [rax]
0x18011eddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ede4  mov     rcx, [rsp+0E8h]; this
0x18011edec  test    eax, eax
0x18011edee  jns     short loc_18011EE04
0x18011edf0  mov     r9d, eax; char *
0x18011edf3  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011edfa  mov     edx, 305h; void *
0x18011edff  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ee04  mov     rcx, [r14+70h]
0x18011ee08  mov     [rsp+0E8h+dwCapabilities], 20h ; ' '; dwCapabilities
0x18011ee10  mov     [rsp+0E8h+pAuthInfo], rbx; pAuthInfo
0x18011ee15  mov     [rsp+0E8h+dwImpLevel], 2; dwImpLevel
0x18011ee1d  mov     dword ptr [rsp+0E8h+ppv], ebx; int
0x18011ee21  or      r9, 0FFFFFFFFFFFFFFFFh; pServerPrincName
0x18011ee25  or      eax, 0FFFFFFFFh
0x18011ee28  mov     r8d, eax; dwAuthzSvc
0x18011ee2b  mov     edx, eax; dwAuthnSvc
0x18011ee2d  mov     rcx, [rcx+18h]; pProxy
0x18011ee31  call    cs:__imp_CoSetProxyBlanket
0x18011ee37  mov     rcx, [rsp+0E8h]; this
0x18011ee3f  test    eax, eax
0x18011ee41  jns     short loc_18011EE58
0x18011ee43  mov     r9d, eax; char *
0x18011ee46  lea     r8, aOnecoreDsSecur_9; "onecore\\ds\\security\\fido\\ctap\\tran"...
0x18011ee4d  mov     edx, 30Dh; void *
0x18011ee52  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18011ee58  mov     rcx, [r12]
0x18011ee5c  mov     [rsp+0E8h+var_A0], rcx
0x18011ee61  test    rcx, rcx
0x18011ee64  jz      short loc_18011EE77
0x18011ee66  mov     [r12], rbx
0x18011ee6a  mov     rax, [rcx]
0x18011ee6d  mov     rax, [rax+10h]
0x18011ee71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18011ee76  nop
0x18011ee77  mov     rcx, r13
0x18011ee7a  call    ??1?$com_ptr_t@UICapabilityUsage@Management@CapabilityAccess@Internal@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>::~com_ptr_t<Windows::Internal::CapabilityAccess::Management::ICapabilityUsage,wil::err_returncode_policy>(void)
0x18011ee7f  nop
0x18011ee80  lea     rcx, [rdi+28h]
0x18011ee84  call    ??1?$unique_storage@U?$resource_policy@PEAXP6AXPEAX@Z$1?RevertImpersonateToken@details@wil@@YAX0@ZU?$integral_constant@_K$01@wistd@@PEAX_J$0?0PEAX@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>::~unique_storage<wil::details::resource_policy<void *,void (*)(void *),&wil::details::RevertImpersonateToken(void *),wistd::integral_constant<unsigned __int64,2>,void *,__int64,-1,void *>>(void)
0x18011ee89  nop
0x18011ee8a  mov     rcx, r15
0x18011ee8d  call    ??1?$shared_ptr@UCredentialInfo@@@std@@QEAA@XZ; std::shared_ptr<CredentialInfo>::~shared_ptr<CredentialInfo>(void)
0x18011ee92  nop
0x18011ee93  jmp     short loc_18011EEA1
0x18011ee95  xor     ebx, ebx
0x18011ee97  mov     rsi, [rsp+0E8h+var_88]
0x18011ee9c  mov     rdi, [rsp+0E8h+var_98]
0x18011eea1  lea     rcx, [rdi+50h]
0x18011eea5  lea     rax, [rdi-70h]
0x18011eea9  mov     [rcx], rax
0x18011eeac  xor     eax, eax
0x18011eeae  mov     [rsi], ax
0x18011eeb1  call    ?await_suspend@final_suspend_awaiter@?$promise_base@Upromise_type@?$coroutine_traits@UIAsyncAction@Foundation@Windows@winrt@@PEAXV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$shared_ptr@UPluginAuthenticatorInstance@@@6@@experimental@std@@UIAsyncAction@Foundation@Windows@winrt@@X@impl@winrt@@QEBA_NU?$coroutine_handle@X@experimental@std@@@Z; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncAction,void *,std::wstring,std::shared_ptr<PluginAuthenticatorInstance>>::promise_type,winrt::Windows::Foundation::IAsyncAction,void>::final_suspend_awaiter::await_suspend(std::experimental::coroutine_handle<void>)
0x18011eeb6  test    al, al
0x18011eeb8  jz      short loc_18011EEBE
0x18011eeba  jmp     short loc_18011EEE7
0x18011eebc  xor     ebx, ebx; jumptable 000000018011EAAC cases -1,1
0x18011eebe  lea     rcx, [rdi-70h]
0x18011eec2  call    ??1?$promise_base@Upromise_type@?$coroutine_traits@U?$IAsyncOperation@U?$IVector@E@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@AEBU1234@AEBU1234@@experimental@std@@U?$IAsyncOperation@U?$IVector@E@Collections@Foundation@Windows@winrt@@@Foundation@Windows@winrt@@X@impl@winrt@@UEAA@XZ; winrt::impl::promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>> const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>>,void>::~promise_base<std::experimental::coroutine_traits<winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>>,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>> const &,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>> const &>::promise_type,winrt::Windows::Foundation::IAsyncOperation<winrt::Windows::Foundation::Collections::IVector<uchar>>,void>(void)
0x18011eec7  lea     rcx, [rsi+70h]
0x18011eecb  call    _InstantiatePasskeyManagerAsync____3____parameters_____parameters_
0x18011eed0  cmp     [rdi+0Ah], bx
0x18011eed4  jz      short loc_18011EEE7
0x18011eed6  mov     edx, 120h
0x18011eedb  lea     rcx, [rdi-70h]; Block
0x18011eedf  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18011eee4  jmp     short loc_18011EEE7
0x18011eee6  int     3; Trap to Debugger
0x18011eee7  mov     rcx, [rsp+0E8h+var_38]
0x18011eeef  xor     rcx, rsp; StackCookie
0x18011eef2  call    __security_check_cookie
0x18011eef7  lea     r11, [rsp+0E8h+var_28]
0x18011eeff  mov     rbx, [r11+38h]
0x18011ef03  mov     rsi, [r11+40h]
0x18011ef07  mov     rsp, r11
0x18011ef0a  pop     r15
0x18011ef0c  pop     r14
0x18011ef0e  pop     r13
0x18011ef10  pop     r12
0x18011ef12  pop     rdi
0x18011ef13  retn
```
