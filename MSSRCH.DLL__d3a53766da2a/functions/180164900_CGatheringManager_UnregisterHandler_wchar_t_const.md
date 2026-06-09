# CGatheringManager::UnregisterHandler(wchar_t const *)

- ea: `0x180164900`
- end: `0x180164b2d`
- name: `?UnregisterHandler@CGatheringManager@@UEAAJPEB_W@Z`
- size: `557`
- prototype: `__int64 __fastcall(CGatheringManager *__hidden this, const wchar_t *)`
- caller_count: `0`
- callee_count: `12`
- tags: `authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

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
- `0x180164900`
- `0x180165b7c`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180164a03`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180164a03`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801649e3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180164aa0`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801649e3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180164aa0`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180164975`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180164975`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180164a3c`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x180164a3c`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180164a60`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180164a60`

## string_xrefs

- `0x180164a7e`: `onecoreuap\base\appmodel\Search\common\include\UserSidHelper.h`

## pseudocode

```c
__int64 __fastcall CGatheringManager::UnregisterHandler(CGatheringManager *this, const wchar_t *a2)
{
  int Error; // ebx
  __int64 v4; // rdx
  HRESULT v5; // eax
  unsigned __int64 v6; // r9
  __int64 v7; // rdx
  __int64 v8; // rdx
  HLOCAL v9; // rbx
  __int64 v10; // rdx
  int v11; // eax
  int ReturnLength; // [rsp+20h] [rbp-49h]
  int ReturnLengtha; // [rsp+20h] [rbp-49h]
  HANDLE TokenHandle; // [rsp+30h] [rbp-39h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-31h] BYREF
  DWORD v17; // [rsp+40h] [rbp-29h] BYREF
  HANDLE *p_TokenHandle; // [rsp+48h] [rbp-21h] BYREF
  __int64 v19; // [rsp+50h] [rbp-19h] BYREF
  char v20; // [rsp+58h] [rbp-11h]
  PSID TokenInformation[10]; // [rsp+60h] [rbp-9h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  if ( (unsigned int)CGatheringManager::IsClientAuthenticated((CGatheringManager *)((char *)this - 24)) )
  {
    if ( !g_pGatheringService )
    {
      Error = -2147218141;
      v4 = 1703;
      goto LABEL_3;
    }
    hMem = 0;
    v5 = CoImpersonateClient();
    Error = v5;
    if ( v5 < 0 )
    {
      v6 = (unsigned int)v5;
      v7 = 1708;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v7,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gathermgr.cxx",
        (const char *)v6,
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
      v9 = hMem;
      if ( hMem )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v17);
        LocalFree(v9);
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
          v11 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL, const wchar_t *))(**((_QWORD **)g_pGatheringService + 914)
                                                                           + 72LL))(
                  *((_QWORD *)g_pGatheringService + 914),
                  hMem,
                  a2);
          Error = v11;
          if ( v11 >= 0 )
          {
            Error = 0;
            goto LABEL_24;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD61,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)v11,
            ReturnLengtha);
          v6 = (unsigned int)Error;
          v7 = 1719;
          goto LABEL_22;
        }
        v10 = 18;
      }
      else
      {
        v10 = 16;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v10,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\UserSidHelper.h",
        (const char *)(unsigned int)Error,
        ReturnLengtha);
      v8 = 1716;
    }
    else
    {
      v8 = 1714;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v8,
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
  v4 = 1701;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v4,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gathermgr.cxx",
    (const char *)(unsigned int)Error,
    ReturnLength);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180164900  mov     [rsp-8+arg_10], rbx
0x180164905  mov     [rsp-8+arg_18], rdi
0x18016490a  push    rbp
0x18016490b  lea     rbp, [rsp-57h]
0x180164910  sub     rsp, 0C0h
0x180164917  mov     rax, cs:__security_cookie
0x18016491e  xor     rax, rsp
0x180164921  mov     [rbp+57h+var_10], rax
0x180164925  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180164929  mov     rdi, rdx
0x18016492c  call    ?IsClientAuthenticated@CGatheringManager@@AEAAHXZ; CGatheringManager::IsClientAuthenticated(void)
0x180164931  test    eax, eax
0x180164933  jnz     short loc_180164957
0x180164935  mov     ebx, 80070005h
0x18016493a  mov     edx, 6A5h; void *
0x18016493f  mov     rcx, [rbp+5Fh]; this
0x180164943  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18016494a  mov     r9d, ebx; char *
0x18016494d  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164952  jmp     loc_180164B0A
0x180164957  cmp     cs:?g_pGatheringService@@3PEAVCGatheringService@@EA, 0; CGatheringService * g_pGatheringService
0x18016495f  jnz     short loc_18016496D
0x180164961  mov     ebx, 80040D23h
0x180164966  mov     edx, 6A7h
0x18016496b  jmp     short loc_18016493F
0x18016496d  mov     [rbp+57h+hMem], 0
0x180164975  call    cs:__imp_CoImpersonateClient
0x18016497b  mov     ebx, eax
0x18016497d  test    eax, eax
0x18016497f  jns     short loc_18016498E
0x180164981  mov     r9d, eax
0x180164984  mov     edx, 6ACh
0x180164989  jmp     loc_180164AED
0x18016498e  lea     rax, [rbp+57h+TokenHandle]
0x180164992  mov     [rbp+57h+TokenHandle], 0
0x18016499a  lea     rcx, [rbp+57h+var_70]
0x18016499e  mov     [rbp+57h+var_78], rax
0x1801649a2  mov     [rbp+57h+var_70], 0
0x1801649aa  mov     [rbp+57h+var_68], 1
0x1801649ae  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x1801649b3  lea     rcx, [rbp+57h+var_78]
0x1801649b7  mov     ebx, eax
0x1801649b9  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1801649be  test    ebx, ebx
0x1801649c0  jns     short loc_1801649EE
0x1801649c2  mov     edx, 6B2h; void *
0x1801649c7  mov     rcx, [rbp+5Fh]; this
0x1801649cb  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x1801649d2  mov     r9d, ebx; char *
0x1801649d5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801649da  lea     rcx, [rbp+57h+TokenHandle]
0x1801649de  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801649e3  call    cs:__imp_CoRevertToSelf
0x1801649e9  jmp     loc_180164B01
0x1801649ee  mov     rbx, [rbp+57h+hMem]
0x1801649f2  test    rbx, rbx
0x1801649f5  jz      short loc_180164A12
0x1801649f7  lea     rcx, [rbp+57h+var_80]; this
0x1801649fb  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180164a00  mov     rcx, rbx; hMem
0x180164a03  call    cs:__imp_LocalFree
0x180164a09  lea     rcx, [rbp+57h+var_80]; this
0x180164a0d  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180164a12  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180164a16  lea     rax, [rbp+57h+var_80]
0x180164a1a  mov     r9d, 44h ; 'D'; TokenInformationLength
0x180164a20  mov     [rbp+57h+hMem], 0
0x180164a28  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x180164a2c  mov     [rbp+57h+var_80], 0
0x180164a33  mov     qword ptr [rsp+0C0h+ReturnLength], rax; int
0x180164a38  lea     edx, [r9-43h]; TokenInformationClass
0x180164a3c  call    cs:__imp_GetTokenInformation
0x180164a42  test    eax, eax
0x180164a44  jnz     short loc_180164A58
0x180164a46  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180164a4b  mov     ebx, eax
0x180164a4d  test    eax, eax
0x180164a4f  jns     short loc_180164A58
0x180164a51  mov     edx, 10h
0x180164a56  jmp     short loc_180164A7A
0x180164a58  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x180164a5c  lea     rdx, [rbp+57h+hMem]; StringSid
0x180164a60  call    cs:__imp_ConvertSidToStringSidW
0x180164a66  test    eax, eax
0x180164a68  jnz     short loc_180164A97
0x180164a6a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180164a6f  mov     ebx, eax
0x180164a71  test    eax, eax
0x180164a73  jns     short loc_180164A97
0x180164a75  mov     edx, 12h; void *
0x180164a7a  mov     rcx, [rbp+5Fh]; this
0x180164a7e  lea     r8, aOnecoreuapBase_123; "onecoreuap\\base\\appmodel\\Search\\com"...
0x180164a85  mov     r9d, ebx; char *
0x180164a88  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164a8d  mov     edx, 6B4h
0x180164a92  jmp     loc_1801649C7
0x180164a97  lea     rcx, [rbp+57h+TokenHandle]
0x180164a9b  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180164aa0  call    cs:__imp_CoRevertToSelf
0x180164aa6  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x180164aad  mov     r8, rdi
0x180164ab0  mov     rdx, [rbp+57h+hMem]
0x180164ab4  mov     rcx, [rax+1C90h]
0x180164abb  mov     rax, [rcx]
0x180164abe  mov     rax, [rax+48h]
0x180164ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180164ac7  mov     ebx, eax
0x180164ac9  test    eax, eax
0x180164acb  jns     short loc_180164AFF
0x180164acd  mov     rcx, [rbp+5Fh]; this
0x180164ad1  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180164ad8  mov     r9d, eax; char *
0x180164adb  mov     edx, 0D61h; void *
0x180164ae0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164ae5  mov     r9d, ebx; char *
0x180164ae8  mov     edx, 6B7h; void *
0x180164aed  mov     rcx, [rbp+5Fh]; this
0x180164af1  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180164af8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180164afd  jmp     short loc_180164B01
0x180164aff  xor     ebx, ebx
0x180164b01  lea     rcx, [rbp+57h+hMem]
0x180164b05  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180164b0a  mov     eax, ebx
0x180164b0c  mov     rcx, [rbp+57h+var_10]
0x180164b10  xor     rcx, rsp; StackCookie
0x180164b13  call    __security_check_cookie
0x180164b18  lea     r11, [rsp+0C0h+var_s0]
0x180164b20  mov     rbx, [r11+20h]
0x180164b24  mov     rdi, [r11+28h]
0x180164b28  mov     rsp, r11
0x180164b2b  pop     rbp
0x180164b2c  retn
```
