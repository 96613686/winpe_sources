# AiRegistrySync(void *,void *)

- ea: `0x180040c70`
- end: `0x180041037`
- name: `?AiRegistrySync@@YAJPEAX0@Z`
- size: `967`
- prototype: `int(void *, void *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180041040`

## callees

- `0x180007c78`
- `0x180010850`
- `0x180012634`
- `0x1800182bc`
- `0x180018400`
- `0x180018530`
- `0x18001b494`
- `0x18001dfd8`
- `0x18001fd94`
- `0x1800272d0`
- `0x1800341c0`
- `0x18003a260`
- `0x1800407b0`
- `0x180040818`
- `0x180040954`
- `0x180040c70`
- `0x1800410c0`
- `0x1800411e0`
- `0x1800414ec`
- `0x180044a20`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180040e2c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x180040e2c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040eb0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040fd2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040eb0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040fd2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040e79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040eeb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040e79`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040eeb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180040f33`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x180040f33`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040d7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040de6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040d7f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x180040de6`

## string_xrefs

- `0x180040ca2`: `RegistrySyncActivity`
- `0x180040cef`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040d25`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040d96`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040e02`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040e90`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040f02`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

## pseudocode

```c
__int64 __fastcall AiRegistrySync(void *a1, void *a2)
{
  int v4; // r15d
  int token_information; // eax
  unsigned int LastError; // esi
  int v7; // eax
  void *v8; // rcx
  void *v9; // rbx
  const char *v10; // r9
  void *v11; // rcx
  void *v12; // rdi
  const char *v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // eax
  unsigned int v16; // eax
  LPCWSTR *v17; // rsi
  LSTATUS v18; // eax
  unsigned __int64 v19; // rdx
  unsigned __int8 v20; // cl
  unsigned int v21; // r14d
  LUATelemetry *v22; // rcx
  int phkResult; // [rsp+20h] [rbp-E0h]
  unsigned int phkResulta; // [rsp+20h] [rbp-E0h]
  unsigned int phkResultb; // [rsp+20h] [rbp-E0h]
  LPWSTR StringSid; // [rsp+30h] [rbp-D0h] BYREF
  LPWSTR v28; // [rsp+38h] [rbp-C8h] BYREF
  void *v29; // [rsp+40h] [rbp-C0h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-B8h] BYREF
  HKEY v31; // [rsp+50h] [rbp-B0h] BYREF
  void *Block; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v33[42]; // [rsp+60h] [rbp-A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+1E8h] [rbp+E8h]

  wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>((struct wil::details::IFailureCallback *)v33);
  v33[0] = &LUATelemetry::RegistrySyncActivity::`vftable';
  LUATelemetry::RegistrySyncActivity::StartActivity((LUATelemetry::RegistrySyncActivity *)v33);
  v29 = 0;
  v4 = 1;
  token_information = wil::get_token_information_nothrow<_TOKEN_USER,0>(&v29, a1);
  LastError = token_information;
  if ( token_information < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xAD,
      (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
      (const char *)(unsigned int)token_information,
      phkResult);
    goto LABEL_6;
  }
  Block = 0;
  v7 = wil::get_token_information_nothrow<_TOKEN_USER,0>(&Block, a2);
  LastError = v7;
  if ( v7 >= 0 )
  {
    StringSid = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &StringSid,
      0);
    v9 = v29;
    if ( !ConvertSidToStringSidW(*(PSID *)v29, &StringSid) )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0xB3,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                    v10);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      v11 = Block;
      if ( !Block )
      {
LABEL_11:
        v8 = v9;
        goto LABEL_7;
      }
LABEL_10:
      operator delete(v11);
      goto LABEL_11;
    }
    v28 = 0;
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::reset(
      &v28,
      0);
    v12 = Block;
    if ( !ConvertSidToStringSidW(*(PSID *)Block, &v28) )
    {
      v14 = 182;
LABEL_14:
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)v14,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                    v13);
LABEL_15:
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
      wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
      v11 = v12;
      goto LABEL_10;
    }
    if ( !ImpersonateLoggedOnUser(a2) )
    {
      v14 = 185;
      goto LABEL_14;
    }
    v31 = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &v31,
      0);
    v15 = RegOpenKeyExW(HKEY_USERS, StringSid, 0, 0xF003Fu, &v31);
    if ( v15 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xBE,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                    (const char *)v15,
                    phkResulta);
LABEL_20:
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
      RevertToSelf();
      goto LABEL_15;
    }
    hKey = 0;
    wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(
      &hKey,
      0);
    v16 = RegOpenKeyExW(HKEY_USERS, v28, 0, 0xF003Fu, &hKey);
    if ( v16 )
    {
      LastError = wil::details::in1diag3::Return_Win32(
                    retaddr,
                    (void *)0xC1,
                    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
                    (const char *)v16,
                    phkResultb);
      wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
      goto LABEL_20;
    }
    v17 = (LPCWSTR *)off_180049988;
    while ( 1 )
    {
      v18 = RegDeleteTreeW(hKey, *v17);
      v21 = v18;
      if ( (v18 & 0xFFFFFFFD) != 0 )
        break;
      LODWORD(v29) = AiCopyRegistry(v31, hKey, (unsigned __int16 *)*v17);
      if ( (int)v29 < 0 )
      {
        LUATelemetry::SettingsSyncErrorContext<long &,unsigned short * const &>(&v29, v17);
LABEL_31:
        v4 = 0;
      }
      if ( ++v17 == (LPCWSTR *)&load_config_used )
      {
        LUATelemetry::RegistrySyncActivity::Stop((LUATelemetry::RegistrySyncActivity *)v33, v4);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&hKey);
        wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&long RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(&v31);
        RevertToSelf();
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v28);
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&StringSid);
        operator delete(v12);
        operator delete(v9);
        LastError = 0;
        goto LABEL_34;
      }
    }
    if ( v18 > 0 )
      v21 = (unsigned __int16)v18 | 0x80070000;
    if ( LUATelemetry::IsEnabled(v20, v19) )
    {
      LUATelemetry::Instance();
      LUATelemetry::SettingsSyncErrorContext_(v22, v21, (unsigned __int16 *)*v17);
    }
    goto LABEL_31;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xB0,
    (unsigned int)"onecoreuap\\ds\\security\\services\\lua\\appinfo\\sync.cxx",
    (const char *)(unsigned int)v7,
    phkResult);
  if ( Block )
    operator delete(Block);
LABEL_6:
  v8 = v29;
  if ( v29 )
LABEL_7:
    operator delete(v8);
LABEL_34:
  LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity((LUATelemetry::RegistrySyncActivity *)v33);
  return LastError;
}

```

## disassembly

```asm
0x180040c70  mov     [rsp-8+arg_10], rbx
0x180040c75  push    rbp
0x180040c76  push    rsi
0x180040c77  push    rdi
0x180040c78  push    r14
0x180040c7a  push    r15
0x180040c7c  lea     rbp, [rsp-0C0h]
0x180040c84  sub     rsp, 1C0h
0x180040c8b  mov     rax, cs:__security_cookie
0x180040c92  xor     rax, rsp
0x180040c95  mov     [rbp+0E0h+var_30], rax
0x180040c9c  mov     r14, rdx
0x180040c9f  mov     rbx, rcx
0x180040ca2  lea     rdx, aRegistrysyncac; "RegistrySyncActivity"
0x180040ca9  lea     rcx, [rsp+1E0h+var_180]; struct wil::details::IFailureCallback *
0x180040cae  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040cb3  lea     rax, ??_7RegistrySyncActivity@LUATelemetry@@6B@; const LUATelemetry::RegistrySyncActivity::`vftable'
0x180040cba  lea     rcx, [rsp+1E0h+var_180]; this
0x180040cbf  mov     [rsp+1E0h+var_180], rax
0x180040cc4  call    ?StartActivity@RegistrySyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::RegistrySyncActivity::StartActivity(void)
0x180040cc9  and     [rsp+1E0h+var_1A0], 0
0x180040ccf  lea     rcx, [rsp+1E0h+var_1A0]
0x180040cd4  mov     rdx, rbx
0x180040cd7  mov     r15d, 1
0x180040cdd  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180040ce2  mov     esi, eax
0x180040ce4  test    eax, eax
0x180040ce6  jns     short loc_180040D05
0x180040ce8  mov     rcx, [rbp+0E8h]; this
0x180040cef  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040cf6  mov     r9d, eax; char *
0x180040cf9  mov     edx, 0ADh; void *
0x180040cfe  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040d03  jmp     short loc_180040D48
0x180040d05  and     [rsp+1E0h+Block], 0
0x180040d0b  lea     rcx, [rsp+1E0h+Block]
0x180040d10  mov     rdx, r14
0x180040d13  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x180040d18  mov     esi, eax
0x180040d1a  test    eax, eax
0x180040d1c  jns     short loc_180040D60
0x180040d1e  mov     rcx, [rbp+0E8h]; this
0x180040d25  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040d2c  mov     r9d, eax; char *
0x180040d2f  mov     edx, 0B0h; void *
0x180040d34  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180040d39  mov     rcx, [rsp+1E0h+Block]; Block
0x180040d3e  test    rcx, rcx
0x180040d41  jz      short loc_180040D48
0x180040d43  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040d48  mov     rcx, [rsp+1E0h+var_1A0]; Block
0x180040d4d  test    rcx, rcx
0x180040d50  jz      loc_180041004
0x180040d56  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040d5b  jmp     loc_180041004
0x180040d60  and     [rsp+1E0h+StringSid], 0
0x180040d66  lea     rcx, [rsp+1E0h+StringSid]
0x180040d6b  xor     edx, edx
0x180040d6d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180040d72  mov     rbx, [rsp+1E0h+var_1A0]
0x180040d77  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x180040d7c  mov     rcx, [rbx]; Sid
0x180040d7f  call    cs:__imp_ConvertSidToStringSidW
0x180040d86  nop     dword ptr [rax+rax+00h]
0x180040d8b  test    eax, eax
0x180040d8d  jnz     short loc_180040DC7
0x180040d8f  mov     rcx, [rbp+0E8h]; this
0x180040d96  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040d9d  mov     edx, 0B3h; void *
0x180040da2  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040da7  lea     rcx, [rsp+1E0h+StringSid]
0x180040dac  mov     esi, eax
0x180040dae  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040db3  mov     rcx, [rsp+1E0h+Block]; Block
0x180040db8  test    rcx, rcx
0x180040dbb  jz      short loc_180040DC2
0x180040dbd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040dc2  mov     rcx, rbx
0x180040dc5  jmp     short loc_180040D56
0x180040dc7  and     [rsp+1E0h+var_1A8], 0
0x180040dcd  lea     rcx, [rsp+1E0h+var_1A8]
0x180040dd2  xor     edx, edx
0x180040dd4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180040dd9  mov     rdi, [rsp+1E0h+Block]
0x180040dde  lea     rdx, [rsp+1E0h+var_1A8]; StringSid
0x180040de3  mov     rcx, [rdi]; Sid
0x180040de6  call    cs:__imp_ConvertSidToStringSidW
0x180040ded  nop     dword ptr [rax+rax+00h]
0x180040df2  test    eax, eax
0x180040df4  jnz     short loc_180040E29
0x180040df6  mov     edx, 0B6h; void *
0x180040dfb  mov     rcx, [rbp+0E8h]; this
0x180040e02  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040e09  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040e0e  mov     esi, eax
0x180040e10  lea     rcx, [rsp+1E0h+var_1A8]
0x180040e15  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040e1a  lea     rcx, [rsp+1E0h+StringSid]
0x180040e1f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040e24  mov     rcx, rdi
0x180040e27  jmp     short loc_180040DBD
0x180040e29  mov     rcx, r14; hToken
0x180040e2c  call    cs:__imp_ImpersonateLoggedOnUser
0x180040e33  nop     dword ptr [rax+rax+00h]
0x180040e38  test    eax, eax
0x180040e3a  jnz     short loc_180040E43
0x180040e3c  mov     edx, 0B9h
0x180040e41  jmp     short loc_180040DFB
0x180040e43  and     [rsp+1E0h+var_190], 0
0x180040e49  lea     rcx, [rsp+1E0h+var_190]
0x180040e4e  xor     edx, edx
0x180040e50  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040e55  mov     rdx, [rsp+1E0h+StringSid]; lpSubKey
0x180040e5a  lea     rax, [rsp+1E0h+var_190]
0x180040e5f  mov     esi, 0F003Fh
0x180040e64  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x180040e69  mov     r14, 0FFFFFFFF80000003h
0x180040e70  mov     r9d, esi; samDesired
0x180040e73  mov     rcx, r14; hKey
0x180040e76  xor     r8d, r8d; ulOptions
0x180040e79  call    cs:__imp_RegOpenKeyExW
0x180040e80  nop     dword ptr [rax+rax+00h]
0x180040e85  test    eax, eax
0x180040e87  jz      short loc_180040EC1
0x180040e89  mov     rcx, [rbp+0E8h]; this
0x180040e90  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040e97  mov     r9d, eax; char *
0x180040e9a  mov     edx, 0BEh; void *
0x180040e9f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040ea4  mov     esi, eax
0x180040ea6  lea     rcx, [rsp+1E0h+var_190]
0x180040eab  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040eb0  call    cs:__imp_RevertToSelf
0x180040eb7  nop     dword ptr [rax+rax+00h]
0x180040ebc  jmp     loc_180040E10
0x180040ec1  and     [rsp+1E0h+hKey], 0
0x180040ec7  lea     rcx, [rsp+1E0h+hKey]
0x180040ecc  xor     edx, edx
0x180040ece  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040ed3  mov     rdx, [rsp+1E0h+var_1A8]; lpSubKey
0x180040ed8  lea     rax, [rsp+1E0h+hKey]
0x180040edd  mov     r9d, esi; samDesired
0x180040ee0  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x180040ee5  xor     r8d, r8d; ulOptions
0x180040ee8  mov     rcx, r14; hKey
0x180040eeb  call    cs:__imp_RegOpenKeyExW
0x180040ef2  nop     dword ptr [rax+rax+00h]
0x180040ef7  test    eax, eax
0x180040ef9  jz      short loc_180040F24
0x180040efb  mov     rcx, [rbp+0E8h]; this
0x180040f02  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040f09  mov     r9d, eax; char *
0x180040f0c  mov     edx, 0C1h; void *
0x180040f11  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040f16  lea     rcx, [rsp+1E0h+hKey]
0x180040f1b  mov     esi, eax
0x180040f1d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040f22  jmp     short loc_180040EA6
0x180040f24  lea     rsi, off_180049988; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180040f2b  mov     rdx, [rsi]; lpSubKey
0x180040f2e  mov     rcx, [rsp+1E0h+hKey]; hKey
0x180040f33  call    cs:__imp_RegDeleteTreeW
0x180040f3a  nop     dword ptr [rax+rax+00h]
0x180040f3f  mov     r14d, eax
0x180040f42  test    eax, 0FFFFFFFDh
0x180040f47  jz      short loc_180040F73
0x180040f49  test    eax, eax
0x180040f4b  jle     short loc_180040F58
0x180040f4d  movzx   r14d, ax
0x180040f51  or      r14d, 80070000h
0x180040f58  call    ?IsEnabled@LUATelemetry@@SA_NE_K@Z; LUATelemetry::IsEnabled(uchar,unsigned __int64)
0x180040f5d  test    al, al
0x180040f5f  jz      short loc_180040F9A
0x180040f61  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180040f66  mov     r8, [rsi]; unsigned __int16 *
0x180040f69  mov     edx, r14d; int
0x180040f6c  call    ?SettingsSyncErrorContext_@LUATelemetry@@QEAAXJPEAG@Z; LUATelemetry::SettingsSyncErrorContext_(long,ushort *)
0x180040f71  jmp     short loc_180040F9A
0x180040f73  mov     r8, [rsi]; unsigned __int16 *
0x180040f76  mov     rdx, [rsp+1E0h+hKey]; HKEY
0x180040f7b  mov     rcx, [rsp+1E0h+var_190]; HKEY
0x180040f80  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x180040f85  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x180040f89  test    eax, eax
0x180040f8b  jns     short loc_180040F9D
0x180040f8d  mov     rdx, rsi
0x180040f90  lea     rcx, [rsp+1E0h+var_1A0]
0x180040f95  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x180040f9a  xor     r15d, r15d
0x180040f9d  add     rsi, 8
0x180040fa1  lea     rax, _load_config_used
0x180040fa8  cmp     rsi, rax
0x180040fab  jnz     loc_180040F2B
0x180040fb1  mov     edx, r15d; int
0x180040fb4  lea     rcx, [rsp+1E0h+var_180]; this
0x180040fb9  call    ?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::RegistrySyncActivity::Stop(int)
0x180040fbe  lea     rcx, [rsp+1E0h+hKey]
0x180040fc3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040fc8  lea     rcx, [rsp+1E0h+var_190]
0x180040fcd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040fd2  call    cs:__imp_RevertToSelf
0x180040fd9  nop     dword ptr [rax+rax+00h]
0x180040fde  lea     rcx, [rsp+1E0h+var_1A8]
0x180040fe3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040fe8  lea     rcx, [rsp+1E0h+StringSid]
0x180040fed  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040ff2  mov     rcx, rdi; Block
0x180040ff5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040ffa  mov     rcx, rbx; Block
0x180040ffd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180041002  xor     esi, esi
0x180041004  lea     rcx, [rsp+1E0h+var_180]; this
0x180041009  call    ??1RegistrySyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity(void)
0x18004100e  mov     eax, esi
0x180041010  mov     rcx, [rbp+0E0h+var_30]
0x180041017  xor     rcx, rsp; StackCookie
0x18004101a  call    __security_check_cookie
0x18004101f  mov     rbx, [rsp+1E0h+arg_10]
0x180041027  add     rsp, 1C0h
0x18004102e  pop     r15
0x180041030  pop     r14
0x180041032  pop     rdi
0x180041033  pop     rsi
0x180041034  pop     rbp
0x180041035  retn
```
