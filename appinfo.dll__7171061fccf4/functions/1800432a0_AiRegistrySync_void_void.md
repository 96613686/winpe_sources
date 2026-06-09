# AiRegistrySync(void *,void *)

- ea: `0x1800432a0`
- end: `0x1800436a0`
- name: `?AiRegistrySync@@YAJPEAX0@Z`
- size: `1024`
- prototype: `__int64 __fastcall(void *, void *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x1800436a8`

## callees

- `0x18000720c`
- `0x180010430`
- `0x180011414`
- `0x180018dbc`
- `0x180019fa0`
- `0x18001a0d4`
- `0x18001b25c`
- `0x18001e7bc`
- `0x1800212cc`
- `0x18002b0a0`
- `0x180037250`
- `0x18003c6e0`
- `0x180042e08`
- `0x180042e74`
- `0x180042fb0`
- `0x1800432a0`
- `0x180043724`
- `0x180043840`
- `0x180043b44`
- `0x180046e50`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043440`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800434a9`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180043440`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800434a9`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800434f1`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800434f1`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800433f3`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800433f3`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180043471`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180043591`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180043471`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180043591`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800433b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800433e2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800433b2`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800433e2`

## string_xrefs

- `0x1800432d2`: `RegistrySyncActivity`
- `0x18004331c`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180043355`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180043451`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x1800434ba`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x1800435e2`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180043635`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

## pseudocode

```c
__int64 __fastcall AiRegistrySync(void *a1, void *a2)
{
  int token_information; // eax
  unsigned int v5; // ebx
  int v6; // eax
  void *v7; // rbx
  const char *v8; // r9
  void *v9; // rdi
  const char *v10; // r9
  __int64 v11; // rdx
  unsigned int v12; // eax
  unsigned int LastError; // esi
  unsigned int v14; // eax
  int v15; // r15d
  LPCWSTR *v16; // rsi
  LSTATUS v17; // eax
  unsigned __int64 v18; // rdx
  unsigned __int8 v19; // cl
  unsigned int v20; // r14d
  __int64 v21; // rcx
  LUATelemetry *v22; // rcx
  unsigned int v24; // edi
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v29; // [rsp+38h] [rbp-C8h] BYREF
  void *v30; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v32; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v34[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v34);
  v34[0] = &LUATelemetry::RegistrySyncActivity::`vftable';
  LUATelemetry::RegistrySyncActivity::StartActivity((LUATelemetry::RegistrySyncActivity *)v34);
  v30 = 0;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&v30, a1);
  v5 = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAE,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
      (const char *)(unsigned int)token_information,
      phkResult);
LABEL_6:
    if ( v30 )
      operator delete(v30);
LABEL_39:
    LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity((LUATelemetry::RegistrySyncActivity *)v34);
    return v5;
  }
  Block = 0;
  v6 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a2);
  v5 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
      (const char *)(unsigned int)v6,
      phkResult);
    if ( Block )
      operator delete(Block);
    goto LABEL_6;
  }
  StringSid = 0;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
    &StringSid,
    0);
  v7 = v30;
  if ( ConvertSidToStringSidW(*(PSID *)v30, &StringSid) )
  {
    v29 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v29,
      0);
    v9 = Block;
    if ( !ConvertSidToStringSidW(*(PSID *)Block, &v29) )
    {
      v11 = 183;
      goto LABEL_33;
    }
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      v11 = 186;
LABEL_33:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v11,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                    v10);
      goto LABEL_34;
    }
    v32 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v32,
      0);
    v12 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0xF003Fu, &v32);
    if ( v12 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xBF,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                    (const char *)v12,
                    phkResulta);
LABEL_14:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
      RevertToSelf();
LABEL_34:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      if ( v9 )
        operator delete(v9);
      if ( v7 )
        operator delete(v7);
      v5 = LastError;
      goto LABEL_39;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v14 = RegOpenKeyExW(HKEY_USERS, v29, 0, 0xF003Fu, &hKey);
    if ( v14 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xC2,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                    (const char *)v14,
                    phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_14;
    }
    v15 = 1;
    v16 = (LPCWSTR *)off_18004BC20;
    while ( 1 )
    {
      v17 = RegDeleteTreeW(hKey, *v16);         // Registry sync audit: Consent UI ShadowAdmin sync copies fixed user-experience HKU subtrees under target impersonation; no IFEO/Services/COM/App Paths subtree in list.
      v20 = v17;
      if ( (v17 & 0xFFFFFFFD) != 0 )
        break;
      LODWORD(v30) = AiCopyRegistry(v32, hKey, (unsigned __int16 *)*v16);
      if ( (int)v30 < 0 )
      {
        LUATelemetry::SettingsSyncErrorContext<long &,unsigned short * const &>(&v30, v16);
LABEL_25:
        v15 = 0;
      }
      if ( ++v16 == (LPCWSTR *)&load_config_used )
      {
        LUATelemetry::RegistrySyncActivity::Stop((LUATelemetry::RegistrySyncActivity *)v34, v15);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v32);
        RevertToSelf();
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        if ( v9 )
          operator delete(v9);
        if ( v7 )
          operator delete(v7);
        LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity((LUATelemetry::RegistrySyncActivity *)v34);
        return 0;
      }
    }
    if ( v17 > 0 )
      v20 = (unsigned __int16)v17 | 0x80070000;
    if ( LUATelemetry::IsEnabled(v19, v18) )
    {
      wil::details::static_lazy<LUATelemetry>::get(
        v21,
        _lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_);
      LUATelemetry::SettingsSyncErrorContext_(v22, v20, (unsigned __int16 *)*v16);
    }
    goto LABEL_25;
  }
  v24 = wil::details::in1diag3::Return_GetLastError(
          retaddr,
          (void *)0xB4,
          (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
          v8);
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
  if ( Block )
    operator delete(Block);
  if ( v7 )
    operator delete(v7);
  LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity((LUATelemetry::RegistrySyncActivity *)v34);
  return v24;
}

```

## disassembly

```asm
0x1800432a0  mov     [rsp-8+arg_10], rbx
0x1800432a5  push    rbp
0x1800432a6  push    rsi
0x1800432a7  push    rdi
0x1800432a8  push    r14
0x1800432aa  push    r15
0x1800432ac  lea     rbp, [rsp-0C0h]
0x1800432b4  sub     rsp, 1C0h
0x1800432bb  mov     rax, cs:__security_cookie
0x1800432c2  xor     rax, rsp
0x1800432c5  mov     [rbp+0E0h+var_30], rax
0x1800432cc  mov     rsi, rdx
0x1800432cf  mov     rbx, rcx
0x1800432d2  lea     rdx, aRegistrysyncac; "RegistrySyncActivity"
0x1800432d9  lea     rcx, [rsp+1E0h+var_180]; struct wil::details::IFailureCallback *
0x1800432de  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x1800432e3  lea     rax, ??_7RegistrySyncActivity@LUATelemetry@@6B@; const LUATelemetry::RegistrySyncActivity::`vftable'
0x1800432ea  lea     rcx, [rsp+1E0h+var_180]; this
0x1800432ef  mov     [rsp+1E0h+var_180], rax
0x1800432f4  call    ?StartActivity@RegistrySyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::RegistrySyncActivity::StartActivity(void)
0x1800432f9  mov     rdx, rbx
0x1800432fc  mov     [rsp+1E0h+var_1A0], 0
0x180043305  lea     rcx, [rsp+1E0h+var_1A0]
0x18004330a  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18004330f  mov     ebx, eax
0x180043311  test    eax, eax
0x180043313  jns     short loc_180043332
0x180043315  mov     rcx, [rbp+0E8h]; this
0x18004331c  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180043323  mov     r9d, eax; char *
0x180043326  mov     edx, 0AEh; void *
0x18004332b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043330  jmp     short loc_180043378
0x180043332  mov     rdx, rsi
0x180043335  mov     [rsp+1E0h+Block], 0
0x18004333e  lea     rcx, [rsp+1E0h+Block]
0x180043343  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180043348  mov     ebx, eax
0x18004334a  test    eax, eax
0x18004334c  jns     short loc_180043390
0x18004334e  mov     rcx, [rbp+0E8h]; this
0x180043355  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18004335c  mov     r9d, eax; char *
0x18004335f  mov     edx, 0B1h; void *
0x180043364  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180043369  mov     rcx, [rsp+1E0h+Block]; Block
0x18004336e  test    rcx, rcx
0x180043371  jz      short loc_180043378
0x180043373  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180043378  mov     rcx, [rsp+1E0h+var_1A0]; Block
0x18004337d  test    rcx, rcx
0x180043380  jz      loc_180043620
0x180043386  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004338b  jmp     loc_180043620
0x180043390  xor     edx, edx
0x180043392  mov     [rsp+1E0h+StringSid], 0
0x18004339b  lea     rcx, [rsp+1E0h+StringSid]
0x1800433a0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800433a5  mov     rbx, [rsp+1E0h+var_1A0]
0x1800433aa  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x1800433af  mov     rcx, [rbx]; Sid
0x1800433b2  call    cs:__imp_ConvertSidToStringSidW
0x1800433b8  test    eax, eax
0x1800433ba  jz      loc_18004362E
0x1800433c0  xor     edx, edx
0x1800433c2  mov     [rsp+1E0h+var_1A8], 0
0x1800433cb  lea     rcx, [rsp+1E0h+var_1A8]
0x1800433d0  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x1800433d5  mov     rdi, [rsp+1E0h+Block]
0x1800433da  lea     rdx, [rsp+1E0h+var_1A8]; StringSid
0x1800433df  mov     rcx, [rdi]; Sid
0x1800433e2  call    cs:__imp_ConvertSidToStringSidW
0x1800433e8  test    eax, eax
0x1800433ea  jz      loc_1800435D6
0x1800433f0  mov     rcx, rsi; hToken
0x1800433f3  call    cs:__imp_ImpersonateLoggedOnUser
0x1800433f9  test    eax, eax
0x1800433fb  jnz     short loc_180043407
0x1800433fd  mov     edx, 0BAh
0x180043402  jmp     loc_1800435DB
0x180043407  xor     edx, edx
0x180043409  mov     [rsp+1E0h+var_190], 0
0x180043412  lea     rcx, [rsp+1E0h+var_190]
0x180043417  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18004341c  mov     rdx, [rsp+1E0h+StringSid]; lpSubKey
0x180043421  lea     rax, [rsp+1E0h+var_190]
0x180043426  mov     esi, 0F003Fh
0x18004342b  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x180043430  mov     r14, 0FFFFFFFF80000003h
0x180043437  mov     r9d, esi; samDesired
0x18004343a  mov     rcx, r14; hKey
0x18004343d  xor     r8d, r8d; ulOptions
0x180043440  call    cs:__imp_RegOpenKeyExW
0x180043446  test    eax, eax
0x180043448  jz      short loc_18004347C
0x18004344a  mov     rcx, [rbp+0E8h]; this
0x180043451  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180043458  mov     r9d, eax; char *
0x18004345b  mov     edx, 0BFh; void *
0x180043460  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180043465  mov     esi, eax
0x180043467  lea     rcx, [rsp+1E0h+var_190]
0x18004346c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043471  call    cs:__imp_RevertToSelf
0x180043477  jmp     loc_1800435F0
0x18004347c  xor     edx, edx
0x18004347e  mov     [rsp+1E0h+hKey], 0
0x180043487  lea     rcx, [rsp+1E0h+hKey]
0x18004348c  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180043491  mov     rdx, [rsp+1E0h+var_1A8]; lpSubKey
0x180043496  lea     rax, [rsp+1E0h+hKey]
0x18004349b  mov     r9d, esi; samDesired
0x18004349e  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x1800434a3  xor     r8d, r8d; ulOptions
0x1800434a6  mov     rcx, r14; hKey
0x1800434a9  call    cs:__imp_RegOpenKeyExW
0x1800434af  test    eax, eax
0x1800434b1  jz      short loc_1800434DC
0x1800434b3  mov     rcx, [rbp+0E8h]; this
0x1800434ba  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800434c1  mov     r9d, eax; char *
0x1800434c4  mov     edx, 0C2h; void *
0x1800434c9  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800434ce  lea     rcx, [rsp+1E0h+hKey]
0x1800434d3  mov     esi, eax
0x1800434d5  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800434da  jmp     short loc_180043467
0x1800434dc  mov     r15d, 1
0x1800434e2  lea     rsi, off_18004BC20; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800434e9  mov     rdx, [rsi]; lpSubKey
0x1800434ec  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800434f1  call    cs:__imp_RegDeleteTreeW; Registry sync audit: Consent UI ShadowAdmin sync copies fixed user-experience HKU subtrees under target impersonation; no IFEO/Services/COM/App Paths subtree in list.
0x1800434f7  mov     r14d, eax
0x1800434fa  test    eax, 0FFFFFFFDh
0x1800434ff  jz      short loc_180043532
0x180043501  test    eax, eax
0x180043503  jle     short loc_180043510
0x180043505  movzx   r14d, ax
0x180043509  or      r14d, 80070000h
0x180043510  call    ?IsEnabled@LUATelemetry@@SA_NE_K@Z; LUATelemetry::IsEnabled(uchar,unsigned __int64)
0x180043515  test    al, al
0x180043517  jz      short loc_180043559
0x180043519  lea     rdx, ?_lambda_invoker_cdecl_@_lambda_8fd1dd6eff698f29c42c633fb94303b5_@@CA@XZ; _lambda_8fd1dd6eff698f29c42c633fb94303b5_::_lambda_invoker_cdecl_(void)
0x180043520  call    ?get@?$static_lazy@VLUATelemetry@@@details@wil@@QEAAPEAVLUATelemetry@@P6AXXZ@Z; wil::details::static_lazy<LUATelemetry>::get(void (*)(void))
0x180043525  mov     r8, [rsi]; unsigned __int16 *
0x180043528  mov     edx, r14d; int
0x18004352b  call    ?SettingsSyncErrorContext_@LUATelemetry@@QEAAXJPEAG@Z; LUATelemetry::SettingsSyncErrorContext_(long,ushort *)
0x180043530  jmp     short loc_180043559
0x180043532  mov     r8, [rsi]; unsigned __int16 *
0x180043535  mov     rdx, [rsp+1E0h+hKey]; HKEY
0x18004353a  mov     rcx, [rsp+1E0h+var_190]; HKEY
0x18004353f  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x180043544  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x180043548  test    eax, eax
0x18004354a  jns     short loc_18004355C
0x18004354c  mov     rdx, rsi
0x18004354f  lea     rcx, [rsp+1E0h+var_1A0]
0x180043554  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x180043559  xor     r15d, r15d
0x18004355c  add     rsi, 8
0x180043560  lea     rax, _load_config_used
0x180043567  cmp     rsi, rax
0x18004356a  jnz     loc_1800434E9
0x180043570  mov     edx, r15d; int
0x180043573  lea     rcx, [rsp+1E0h+var_180]; this
0x180043578  call    ?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::RegistrySyncActivity::Stop(int)
0x18004357d  lea     rcx, [rsp+1E0h+hKey]
0x180043582  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043587  lea     rcx, [rsp+1E0h+var_190]
0x18004358c  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180043591  call    cs:__imp_RevertToSelf
0x180043597  lea     rcx, [rsp+1E0h+var_1A8]
0x18004359c  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800435a1  lea     rcx, [rsp+1E0h+StringSid]
0x1800435a6  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800435ab  test    rdi, rdi
0x1800435ae  jz      short loc_1800435B8
0x1800435b0  mov     rcx, rdi; Block
0x1800435b3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800435b8  test    rbx, rbx
0x1800435bb  jz      short loc_1800435C5
0x1800435bd  mov     rcx, rbx; Block
0x1800435c0  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800435c5  lea     rcx, [rsp+1E0h+var_180]; this
0x1800435ca  call    ??1RegistrySyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity(void)
0x1800435cf  xor     eax, eax
0x1800435d1  jmp     loc_18004367A
0x1800435d6  mov     edx, 0B7h; void *
0x1800435db  mov     rcx, [rbp+0E8h]; this
0x1800435e2  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800435e9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800435ee  mov     esi, eax
0x1800435f0  lea     rcx, [rsp+1E0h+var_1A8]
0x1800435f5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800435fa  lea     rcx, [rsp+1E0h+StringSid]
0x1800435ff  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043604  test    rdi, rdi
0x180043607  jz      short loc_180043611
0x180043609  mov     rcx, rdi; Block
0x18004360c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180043611  test    rbx, rbx
0x180043614  jz      short loc_18004361E
0x180043616  mov     rcx, rbx; Block
0x180043619  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004361e  mov     ebx, esi
0x180043620  lea     rcx, [rsp+1E0h+var_180]; this
0x180043625  call    ??1RegistrySyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity(void)
0x18004362a  mov     eax, ebx
0x18004362c  jmp     short loc_18004367A
0x18004362e  mov     rcx, [rbp+0E8h]; this
0x180043635  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18004363c  mov     edx, 0B4h; void *
0x180043641  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180043646  lea     rcx, [rsp+1E0h+StringSid]
0x18004364b  mov     edi, eax
0x18004364d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180043652  mov     rcx, [rsp+1E0h+Block]; Block
0x180043657  test    rcx, rcx
0x18004365a  jz      short loc_180043661
0x18004365c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180043661  test    rbx, rbx
0x180043664  jz      short loc_18004366E
0x180043666  mov     rcx, rbx; Block
0x180043669  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004366e  lea     rcx, [rsp+1E0h+var_180]; this
0x180043673  call    ??1RegistrySyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity(void)
0x180043678  mov     eax, edi
0x18004367a  mov     rcx, [rbp+0E0h+var_30]
0x180043681  xor     rcx, rsp; StackCookie
0x180043684  call    __security_check_cookie
0x180043689  mov     rbx, [rsp+1E0h+arg_10]
0x180043691  add     rsp, 1C0h
0x180043698  pop     r15
0x18004369a  pop     r14
0x18004369c  pop     rdi
0x18004369d  pop     rsi
0x18004369e  pop     rbp
0x18004369f  retn
```
