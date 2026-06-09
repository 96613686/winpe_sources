# CGatheringManager::RegisterHandler(wchar_t const *,_GUID *,_GUID *)

- ea: `0x180163630`
- end: `0x180163860`
- name: `?RegisterHandler@CGatheringManager@@UEAAJPEB_WPEAU_GUID@@1@Z`
- size: `560`
- prototype: `int(CGatheringManager *__hidden this, const wchar_t *, struct _GUID *, struct _GUID *)`
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
- `0x180163630`
- `0x180165b7c`
- `0x180241010`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180163735`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180163735`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180163715`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801637d2`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180163715`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x1801637d2`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1801636a7`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x1801636a7`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18016376e`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18016376e`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180163792`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180163792`

## string_xrefs

- `0x1801637b0`: `onecoreuap\base\appmodel\Search\common\include\UserSidHelper.h`

## pseudocode

```c
__int64 __fastcall CGatheringManager::RegisterHandler(
        CGatheringManager *this,
        const wchar_t *a2,
        struct _GUID *a3,
        struct _GUID *a4)
{
  int v4; // r14d
  int Error; // ebx
  __int64 v8; // rdx
  HRESULT v9; // eax
  unsigned __int64 v10; // r9
  __int64 v11; // rdx
  __int64 v12; // rdx
  HLOCAL v13; // rbx
  __int64 v14; // rdx
  int v15; // eax
  int ReturnLength; // [rsp+20h] [rbp-69h]
  int ReturnLengtha; // [rsp+20h] [rbp-69h]
  HANDLE TokenHandle; // [rsp+30h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-51h] BYREF
  DWORD v21; // [rsp+40h] [rbp-49h] BYREF
  HANDLE *p_TokenHandle; // [rsp+48h] [rbp-41h] BYREF
  __int64 v23; // [rsp+50h] [rbp-39h] BYREF
  char v24; // [rsp+58h] [rbp-31h]
  PSID TokenInformation[10]; // [rsp+60h] [rbp-29h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+E8h] [rbp+5Fh]

  v4 = (int)a4;
  if ( CGatheringManager::IsClientAuthenticated((CGatheringManager *)((char *)this - 24)) )
  {
    if ( !g_pGatheringService )
    {
      Error = -2147218141;
      v8 = 1678;
      goto LABEL_3;
    }
    hMem = 0;
    v9 = CoImpersonateClient();
    Error = v9;
    if ( v9 < 0 )
    {
      v10 = (unsigned int)v9;
      v11 = 1683;
LABEL_22:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v11,
        (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gathermgr.cxx",
        (const char *)v10,
        ReturnLength);
      goto LABEL_24;
    }
    TokenHandle = 0;
    p_TokenHandle = &TokenHandle;
    v23 = 0;
    v24 = 1;
    Error = wil::open_current_access_token_nothrow(&v23);
    wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>>>(&p_TokenHandle);
    if ( Error >= 0 )
    {
      v13 = hMem;
      if ( hMem )
      {
        wil::last_error_context::last_error_context((wil::last_error_context *)&v21);
        LocalFree(v13);
        wil::last_error_context::~last_error_context((wil::last_error_context *)&v21);
      }
      hMem = 0;
      v21 = 0;
      if ( GetTokenInformation(TokenHandle, TokenUser, TokenInformation, 0x44u, &v21)
        || (Error = ResultFromKnownLastError(), Error >= 0) )
      {
        if ( ConvertSidToStringSidW(TokenInformation[0], (LPWSTR *)&hMem)
          || (Error = ResultFromKnownLastError(), Error >= 0) )
        {
          wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&TokenHandle);
          CoRevertToSelf();
          v15 = (*(__int64 (__fastcall **)(_QWORD, HLOCAL, const wchar_t *, struct _GUID *))(**((_QWORD **)g_pGatheringService
                                                                                              + 914)
                                                                                           + 64LL))(
                  *((_QWORD *)g_pGatheringService + 914),
                  hMem,
                  a2,
                  a3);
          Error = v15;
          if ( v15 >= 0 )
          {
            Error = 0;
            goto LABEL_24;
          }
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0xD5B,
            (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\cgathersvc.cxx",
            (const char *)(unsigned int)v15,
            v4);
          v10 = (unsigned int)Error;
          v11 = 1694;
          goto LABEL_22;
        }
        v14 = 18;
      }
      else
      {
        v14 = 16;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v14,
        (unsigned int)"onecoreuap\\base\\appmodel\\Search\\common\\include\\UserSidHelper.h",
        (const char *)(unsigned int)Error,
        ReturnLengtha);
      v12 = 1691;
    }
    else
    {
      v12 = 1689;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v12,
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
  v8 = 1676;
LABEL_3:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v8,
    (unsigned int)"onecoreuap\\base\\appmodel\\search\\mssrch\\gather\\gthrsvc\\gathermgr.cxx",
    (const char *)(unsigned int)Error,
    ReturnLength);
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x180163630  push    rbp
0x180163632  push    rbx
0x180163633  push    rsi
0x180163634  push    rdi
0x180163635  push    r14
0x180163637  lea     rbp, [rsp-37h]
0x18016363c  sub     rsp, 0C0h
0x180163643  mov     rax, cs:__security_cookie
0x18016364a  xor     rax, rsp
0x18016364d  mov     [rbp+57h+var_30], rax
0x180163651  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180163655  mov     r14, r9
0x180163658  mov     rsi, r8
0x18016365b  mov     rdi, rdx
0x18016365e  call    ?IsClientAuthenticated@CGatheringManager@@AEAAHXZ; CGatheringManager::IsClientAuthenticated(void)
0x180163663  test    eax, eax
0x180163665  jnz     short loc_180163689
0x180163667  mov     ebx, 80070005h
0x18016366c  mov     edx, 68Ch; void *
0x180163671  mov     rcx, [rbp+5Fh]; this
0x180163675  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x18016367c  mov     r9d, ebx; char *
0x18016367f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163684  jmp     loc_180163844
0x180163689  cmp     cs:?g_pGatheringService@@3PEAVCGatheringService@@EA, 0; CGatheringService * g_pGatheringService
0x180163691  jnz     short loc_18016369F
0x180163693  mov     ebx, 80040D23h
0x180163698  mov     edx, 68Eh
0x18016369d  jmp     short loc_180163671
0x18016369f  mov     [rbp+57h+hMem], 0
0x1801636a7  call    cs:__imp_CoImpersonateClient
0x1801636ad  mov     ebx, eax
0x1801636af  test    eax, eax
0x1801636b1  jns     short loc_1801636C0
0x1801636b3  mov     r9d, eax
0x1801636b6  mov     edx, 693h
0x1801636bb  jmp     loc_180163827
0x1801636c0  lea     rax, [rbp+57h+TokenHandle]
0x1801636c4  mov     [rbp+57h+TokenHandle], 0
0x1801636cc  lea     rcx, [rbp+57h+var_90]
0x1801636d0  mov     [rbp+57h+var_98], rax
0x1801636d4  mov     [rbp+57h+var_90], 0
0x1801636dc  mov     [rbp+57h+var_88], 1
0x1801636e0  call    ?open_current_access_token_nothrow@wil@@YAJPEAPEAXKW4OpenThreadTokenAs@1@@Z; wil::open_current_access_token_nothrow(void * *,ulong,wil::OpenThreadTokenAs)
0x1801636e5  lea     rcx, [rbp+57h+var_98]
0x1801636e9  mov     ebx, eax
0x1801636eb  call    ??1?$out_param_t@V?$unique_any_t@V?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@@wil@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>::~out_param_t<wil::unique_any_t<wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>>>(void)
0x1801636f0  test    ebx, ebx
0x1801636f2  jns     short loc_180163720
0x1801636f4  mov     edx, 699h; void *
0x1801636f9  mov     rcx, [rbp+5Fh]; this
0x1801636fd  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180163704  mov     r9d, ebx; char *
0x180163707  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016370c  lea     rcx, [rbp+57h+TokenHandle]
0x180163710  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x180163715  call    cs:__imp_CoRevertToSelf
0x18016371b  jmp     loc_18016383B
0x180163720  mov     rbx, [rbp+57h+hMem]
0x180163724  test    rbx, rbx
0x180163727  jz      short loc_180163744
0x180163729  lea     rcx, [rbp+57h+var_A0]; this
0x18016372d  call    ??0last_error_context@wil@@QEAA@XZ; wil::last_error_context::last_error_context(void)
0x180163732  mov     rcx, rbx; hMem
0x180163735  call    cs:__imp_LocalFree
0x18016373b  lea     rcx, [rbp+57h+var_A0]; this
0x18016373f  call    ??1last_error_context@wil@@QEAA@XZ; wil::last_error_context::~last_error_context(void)
0x180163744  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x180163748  lea     rax, [rbp+57h+var_A0]
0x18016374c  mov     r9d, 44h ; 'D'; TokenInformationLength
0x180163752  mov     [rbp+57h+hMem], 0
0x18016375a  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18016375e  mov     [rbp+57h+var_A0], 0
0x180163765  mov     qword ptr [rsp+0E0h+ReturnLength], rax; int
0x18016376a  lea     edx, [r9-43h]; TokenInformationClass
0x18016376e  call    cs:__imp_GetTokenInformation
0x180163774  test    eax, eax
0x180163776  jnz     short loc_18016378A
0x180163778  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18016377d  mov     ebx, eax
0x18016377f  test    eax, eax
0x180163781  jns     short loc_18016378A
0x180163783  mov     edx, 10h
0x180163788  jmp     short loc_1801637AC
0x18016378a  mov     rcx, [rbp+57h+TokenInformation]; Sid
0x18016378e  lea     rdx, [rbp+57h+hMem]; StringSid
0x180163792  call    cs:__imp_ConvertSidToStringSidW
0x180163798  test    eax, eax
0x18016379a  jnz     short loc_1801637C9
0x18016379c  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1801637a1  mov     ebx, eax
0x1801637a3  test    eax, eax
0x1801637a5  jns     short loc_1801637C9
0x1801637a7  mov     edx, 12h; void *
0x1801637ac  mov     rcx, [rbp+5Fh]; this
0x1801637b0  lea     r8, aOnecoreuapBase_123; "onecoreuap\\base\\appmodel\\Search\\com"...
0x1801637b7  mov     r9d, ebx; char *
0x1801637ba  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801637bf  mov     edx, 69Bh
0x1801637c4  jmp     loc_1801636F9
0x1801637c9  lea     rcx, [rbp+57h+TokenHandle]
0x1801637cd  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1801637d2  call    cs:__imp_CoRevertToSelf
0x1801637d8  mov     rax, cs:?g_pGatheringService@@3PEAVCGatheringService@@EA; CGatheringService * g_pGatheringService
0x1801637df  mov     r9, rsi
0x1801637e2  mov     rdx, [rbp+57h+hMem]
0x1801637e6  mov     r8, rdi
0x1801637e9  mov     qword ptr [rsp+0E0h+ReturnLength], r14; int
0x1801637ee  mov     rcx, [rax+1C90h]
0x1801637f5  mov     rax, [rcx]
0x1801637f8  mov     rax, [rax+40h]
0x1801637fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163801  mov     ebx, eax
0x180163803  test    eax, eax
0x180163805  jns     short loc_180163839
0x180163807  mov     rcx, [rbp+5Fh]; this
0x18016380b  lea     r8, aOnecoreuapBase_133; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180163812  mov     r9d, eax; char *
0x180163815  mov     edx, 0D5Bh; void *
0x18016381a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18016381f  mov     r9d, ebx; char *
0x180163822  mov     edx, 69Eh; void *
0x180163827  mov     rcx, [rbp+5Fh]; this
0x18016382b  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\search\\mss"...
0x180163832  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180163837  jmp     short loc_18016383B
0x180163839  xor     ebx, ebx
0x18016383b  lea     rcx, [rbp+57h+hMem]
0x18016383f  call    ??1?$unique_storage@U?$resource_policy@PEA_WP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEA_WPEA_W$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<wchar_t *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,wchar_t *,wchar_t *,0,std::nullptr_t>>(void)
0x180163844  mov     eax, ebx
0x180163846  mov     rcx, [rbp+57h+var_30]
0x18016384a  xor     rcx, rsp; StackCookie
0x18016384d  call    __security_check_cookie
0x180163852  add     rsp, 0C0h
0x180163859  pop     r14
0x18016385b  pop     rdi
0x18016385c  pop     rsi
0x18016385d  pop     rbx
0x18016385e  pop     rbp
0x18016385f  retn
```
