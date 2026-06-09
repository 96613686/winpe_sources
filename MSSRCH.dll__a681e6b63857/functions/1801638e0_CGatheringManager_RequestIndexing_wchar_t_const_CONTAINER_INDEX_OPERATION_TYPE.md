# CGatheringManager::RequestIndexing(wchar_t const *,_CONTAINER_INDEX_OPERATION_TYPE)

- ea: `0x1801638e0`
- end: `0x180163ade`
- name: `?RequestIndexing@CGatheringManager@@UEAAJPEB_WW4_CONTAINER_INDEX_OPERATION_TYPE@@@Z`
- size: `510`
- prototype: `__int64 __fastcall(__int64, __int64, unsigned int)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x18000f880`
- `0x18005e788`
- `0x180079bf0`
- `0x18008a0c0`
- `0x1800fe17c`
- `0x18010ff58`
- `0x1801244c0`
- `0x18014694c`
- `0x180162c7c`
- `0x1801638e0`
- `0x180165b7c`
- `0x180180a64`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801639e0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1801639e0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801639c0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180163a7d`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801639c0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180163a7d`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180163955`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180163955`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180163a19`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180163a19`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180163a3d`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180163a3d`

## string_xrefs

- `0x180163a5b`: `onecoreuap\base\appmodel\Search\common\include\UserSidHelper.h`

## pseudocode

```c
__int64 __fastcall CGatheringManager::RequestIndexing(__int64 a1, __int64 a2, unsigned int a3)
{
  int Error; // ebx
  __int64 v6; // rdx
  HRESULT v7; // eax
  __int64 v8; // rdx
  __int64 v9; // rdx
  HLOCAL v10; // rbx
  __int64 v11; // rdx
  __int64 v12; // rcx
  int ReturnLength; // [rsp+20h] [rbp-59h]
  HANDLE TokenHandle; // [rsp+30h] [rbp-49h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-41h] BYREF
  DWORD v17; // [rsp+40h] [rbp-39h] BYREF
  HANDLE *p_TokenHandle; // [rsp+48h] [rbp-31h] BYREF
  __int64 v19; // [rsp+50h] [rbp-29h] BYREF
  char v20; // [rsp+58h] [rbp-21h]
  PSID TokenInformation[10]; // [rsp+60h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+D8h] [rbp+5Fh]

  if ( (unsigned int)CGatheringManager::IsClientAuthenticated((CGatheringManager *)(a1 - 24)) )
  {
    if ( !g_pGatheringService )
    {
      Error = -2147218141;
      v6 = 1728;
      goto LABEL_3;
    }
    hMem = 0;
    v7 = CoImpersonateClient();
    Error = v7;
    if ( v7 < 0 )
    {
      v8 = 1733;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v8,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gathermgr.cxx",
        (const char *)(unsigned int)v7,
        ReturnLength);
      goto LABEL_24;
    }
    TokenHandle = 0;
    p_TokenHandle = &TokenHandle;
    v19 = 0;
    v20 = 1;
    Error = wil::open_current_access_token_nothrow(&v19);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
    if ( Error >= 0 )
    {
      v10 = hMem;
      if ( hMem )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
        LocalFree(v10);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v17);
      }
      hMem = 0;
      v17 = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x44u, &v17)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        if ( ConvertSidToStringSidW(TokenInformation[0], (LPWSTR *)&hMem)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          CoRevertToSelf();
          v7 = CGatheringService::RequestIndexingFromContainer(v12, hMem, a2, a3);
          Error = v7;
          if ( v7 >= 0 )
          {
            Error = 0;
            goto LABEL_24;
          }
          v8 = 1744;
          goto LABEL_22;
        }
        v11 = 18;
      }
      else
      {
        v11 = 16;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\UserSidHelper.h",
        (const char *)(unsigned int)Error,
        ReturnLength);
      v9 = 1741;
    }
    else
    {
      v9 = 1739;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v9,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gathermgr.cxx",
      (const char *)(unsigned int)Error,
      ReturnLength);
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
    CoRevertToSelf();
LABEL_24:
    wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(&hMem);
    return (unsigned int)Error;
  }
  Error = -2147024891;
  v6 = 1726;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v6,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gathermgr.cxx",
    (const char *)(unsigned int)Error,
    ReturnLength);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1801638e0  mov     [rsp-8+arg_18], rbx
0x1801638e5  push    rbp
0x1801638e6  push    rsi
0x1801638e7  push    rdi
0x1801638e8  lea     rbp, [rsp-47h]
0x1801638ed  sub     rsp, 0C0h
0x1801638f4  mov     rax, cs:__security_cookie
0x1801638fb  xor     rax, rsp
0x1801638fe  mov     [rbp+57h+var_20], rax
0x180163902  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180163906  mov     esi, r8d
0x180163909  mov     rdi, rdx
0x18016390c  call    ?IsClientAuthenticated@CGatheringManager@@AEAAHXZ; CGatheringManager::IsClientAuthenticated(void)
0x180163911  test    eax, eax
0x180163913  jnz     short loc_180163937
0x180163915  mov     ebx, 80070005h
0x18016391a  mov     edx, 6BEh; void *
0x18016391f  mov     rcx, [rbp+5Fh]; this
0x180163923  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18016392a  mov     r9d, ebx; char *
0x18016392d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163932  jmp     loc_180163ABD
0x180163937  cmp     cs:?g_pGatheringService@@3PEAVCGatheringService@@EA, 0; CGatheringService * g_pGatheringService
0x18016393f  jnz     short loc_18016394D
0x180163941  mov     ebx, 80040D23h
0x180163946  mov     edx, 6C0h
0x18016394b  jmp     short loc_18016391F
0x18016394d  mov     [rbp+57h+hMem], 0
0x180163955  call    cs:__imp_CoImpersonateClient
0x18016395b  mov     ebx, eax
0x18016395d  test    eax, eax
0x18016395f  jns     short loc_18016396B
0x180163961  mov     edx, 6C5h
0x180163966  jmp     loc_180163A9D
0x18016396b  lea     rax, [rbp+57h+TokenHandle]
0x18016396f  mov     [rbp+57h+TokenHandle], 0
0x180163977  lea     rcx, [rbp+57h+var_80]
0x18016397b  mov     [rbp+57h+var_88], rax
0x18016397f  mov     [rbp+57h+var_80], 0
0x180163987  mov     [rbp+57h+var_78], 1
0x18016398b  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x180163990  lea     rcx, [rbp+57h+var_88]
0x180163994  mov     ebx, eax
0x180163996  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x18016399b  test    ebx, ebx
0x18016399d  jns     short loc_1801639CB
0x18016399f  mov     edx, 6CBh; void *
0x1801639a4  mov     rcx, [rbp+5Fh]; this
0x1801639a8  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801639af  mov     r9d, ebx; char *
0x1801639b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801639b7  lea     rcx, [rbp+57h+TokenHandle]
0x1801639bb  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801639c0  call    cs:__imp_CoRevertToSelf
0x1801639c6  jmp     loc_180163AB4
0x1801639cb  mov     rbx, [rbp+57h+hMem]
0x1801639cf  test    rbx, rbx
0x1801639d2  jz      short loc_1801639EF
0x1801639d4  lea     rcx, [rbp+57h+var_90]; this
0x1801639d8  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x1801639dd  mov     rcx, rbx; hMem
0x1801639e0  call    cs:__imp_LocalFree
0x1801639e6  lea     rcx, [rbp+57h+var_90]; this
0x1801639ea  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x1801639ef  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x1801639f3  lea     rax, [rbp+57h+var_90]
0x1801639f7  mov     r9d, 44h ; 'D'; TokenInformationLength
0x1801639fd  mov     [rbp+57h+hMem], 0
0x180163a05  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180163a09  mov     [rbp+57h+var_90], 0
0x180163a10  mov     qword ptr [rsp+0D0h+ReturnLength], rax; int
0x180163a15  lea     edx, [r9-43h]; TokenInformationClass
0x180163a19  call    cs:__imp_GetTokenInformation
0x180163a1f  test    eax, eax
0x180163a21  jnz     short loc_180163A35
0x180163a23  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180163a28  mov     ebx, eax
0x180163a2a  test    eax, eax
0x180163a2c  jns     short loc_180163A35
0x180163a2e  mov     edx, 10h
0x180163a33  jmp     short loc_180163A57
0x180163a35  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x180163a39  lea     rdx, [rbp+57h+hMem]; StringSid
0x180163a3d  call    cs:__imp_ConvertSidToStringSidW
0x180163a43  test    eax, eax
0x180163a45  jnz     short loc_180163A74
0x180163a47  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180163a4c  mov     ebx, eax
0x180163a4e  test    eax, eax
0x180163a50  jns     short loc_180163A74
0x180163a52  mov     edx, 12h; void *
0x180163a57  mov     rcx, [rbp+5Fh]; this
0x180163a5b  lea     r8, aOnecoreuapBase_123; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180163a62  mov     r9d, ebx; char *
0x180163a65  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163a6a  mov     edx, 6CDh
0x180163a6f  jmp     loc_1801639A4
0x180163a74  lea     rcx, [rbp+57h+TokenHandle]
0x180163a78  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180163a7d  call    cs:__imp_CoRevertToSelf
0x180163a83  mov     rdx, [rbp+57h+hMem]
0x180163a87  mov     r9d, esi
0x180163a8a  mov     r8, rdi
0x180163a8d  call    ?RequestIndexingFromContainer@CGatheringService@@QEAAJPEB_W0W4_CONTAINER_INDEX_OPERATION_TYPE@@@Z; CGatheringService::RequestIndexingFromContainer(wchar_t const *,wchar_t const *,_CONTAINER_INDEX_OPERATION_TYPE)
0x180163a92  mov     ebx, eax
0x180163a94  test    eax, eax
0x180163a96  jns     short loc_180163AB2
0x180163a98  mov     edx, 6D0h; void *
0x180163a9d  mov     rcx, [rbp+5Fh]; this
0x180163aa1  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180163aa8  mov     r9d, eax; char *
0x180163aab  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163ab0  jmp     short loc_180163AB4
0x180163ab2  xor     ebx, ebx
0x180163ab4  lea     rcx, [rbp+57h+hMem]
0x180163ab8  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180163abd  mov     eax, ebx
0x180163abf  mov     rcx, [rbp+57h+var_20]
0x180163ac3  xor     rcx, rsp; StackCookie
0x180163ac6  call    __security_check_cookie
0x180163acb  mov     rbx, [rsp+0D0h+arg_18]
0x180163ad3  add     rsp, 0C0h
0x180163ada  pop     rdi
0x180163adb  pop     rsi
0x180163adc  pop     rbp
0x180163add  retn
```
