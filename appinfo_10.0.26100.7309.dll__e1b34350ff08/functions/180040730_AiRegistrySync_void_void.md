# AiRegistrySync(void *,void *)

- ea: `0x180040730`
- end: `0x180040af7`
- name: `?AiRegistrySync@@YAJPEAX0@Z`
- size: `967`
- prototype: `int(void *, void *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x180040b00`

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
- `0x180027200`
- `0x180033f00`
- `0x180039ee0`
- `0x180040270`
- `0x1800402d8`
- `0x180040414`
- `0x180040730`
- `0x180040b80`
- `0x180040ca0`
- `0x180040fac`
- `0x1800444e0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800408ec`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x1800408ec`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040970`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040a92`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040970`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x180040a92`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040939`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800409ab`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180040939`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x1800409ab`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800409f3`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x1800409f3`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004083f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800408a6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18004083f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x1800408a6`

## string_xrefs

- `0x180040762`: `RegistrySyncActivity`
- `0x1800407af`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x1800407e5`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040856`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x1800408c2`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x180040950`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x1800409c2`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

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
    v17 = (LPCWSTR *)off_180048988;
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
0x180040730  mov     [rsp-8+arg_10], rbx
0x180040735  push    rbp
0x180040736  push    rsi
0x180040737  push    rdi
0x180040738  push    r14
0x18004073a  push    r15
0x18004073c  lea     rbp, [rsp-0C0h]
0x180040744  sub     rsp, 1C0h
0x18004074b  mov     rax, cs:__security_cookie
0x180040752  xor     rax, rsp
0x180040755  mov     [rbp+0E0h+var_30], rax
0x18004075c  mov     r14, rdx
0x18004075f  mov     rbx, rcx
0x180040762  lea     rdx, aRegistrysyncac; "RegistrySyncActivity"
0x180040769  lea     rcx, [rsp+1E0h+var_180]; struct wil::details::IFailureCallback *
0x18004076e  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x180040773  lea     rax, ??_7RegistrySyncActivity@LUATelemetry@@6B@; const LUATelemetry::RegistrySyncActivity::`vftable'
0x18004077a  lea     rcx, [rsp+1E0h+var_180]; this
0x18004077f  mov     [rsp+1E0h+var_180], rax
0x180040784  call    ?StartActivity@RegistrySyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::RegistrySyncActivity::StartActivity(void)
0x180040789  and     [rsp+1E0h+var_1A0], 0
0x18004078f  lea     rcx, [rsp+1E0h+var_1A0]
0x180040794  mov     rdx, rbx
0x180040797  mov     r15d, 1
0x18004079d  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800407a2  mov     esi, eax
0x1800407a4  test    eax, eax
0x1800407a6  jns     short loc_1800407C5
0x1800407a8  mov     rcx, [rbp+0E8h]; this
0x1800407af  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800407b6  mov     r9d, eax; char *
0x1800407b9  mov     edx, 0ADh; void *
0x1800407be  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800407c3  jmp     short loc_180040808
0x1800407c5  and     [rsp+1E0h+Block], 0
0x1800407cb  lea     rcx, [rsp+1E0h+Block]
0x1800407d0  mov     rdx, r14
0x1800407d3  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x1800407d8  mov     esi, eax
0x1800407da  test    eax, eax
0x1800407dc  jns     short loc_180040820
0x1800407de  mov     rcx, [rbp+0E8h]; this
0x1800407e5  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800407ec  mov     r9d, eax; char *
0x1800407ef  mov     edx, 0B0h; void *
0x1800407f4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800407f9  mov     rcx, [rsp+1E0h+Block]; Block
0x1800407fe  test    rcx, rcx
0x180040801  jz      short loc_180040808
0x180040803  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040808  mov     rcx, [rsp+1E0h+var_1A0]; Block
0x18004080d  test    rcx, rcx
0x180040810  jz      loc_180040AC4
0x180040816  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18004081b  jmp     loc_180040AC4
0x180040820  and     [rsp+1E0h+StringSid], 0
0x180040826  lea     rcx, [rsp+1E0h+StringSid]
0x18004082b  xor     edx, edx
0x18004082d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180040832  mov     rbx, [rsp+1E0h+var_1A0]
0x180040837  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x18004083c  mov     rcx, [rbx]; Sid
0x18004083f  call    cs:__imp_ConvertSidToStringSidW
0x180040846  nop     dword ptr [rax+rax+00h]
0x18004084b  test    eax, eax
0x18004084d  jnz     short loc_180040887
0x18004084f  mov     rcx, [rbp+0E8h]; this
0x180040856  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18004085d  mov     edx, 0B3h; void *
0x180040862  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x180040867  lea     rcx, [rsp+1E0h+StringSid]
0x18004086c  mov     esi, eax
0x18004086e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040873  mov     rcx, [rsp+1E0h+Block]; Block
0x180040878  test    rcx, rcx
0x18004087b  jz      short loc_180040882
0x18004087d  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040882  mov     rcx, rbx
0x180040885  jmp     short loc_180040816
0x180040887  and     [rsp+1E0h+var_1A8], 0
0x18004088d  lea     rcx, [rsp+1E0h+var_1A8]
0x180040892  xor     edx, edx
0x180040894  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x180040899  mov     rdi, [rsp+1E0h+Block]
0x18004089e  lea     rdx, [rsp+1E0h+var_1A8]; StringSid
0x1800408a3  mov     rcx, [rdi]; Sid
0x1800408a6  call    cs:__imp_ConvertSidToStringSidW
0x1800408ad  nop     dword ptr [rax+rax+00h]
0x1800408b2  test    eax, eax
0x1800408b4  jnz     short loc_1800408E9
0x1800408b6  mov     edx, 0B6h; void *
0x1800408bb  mov     rcx, [rbp+0E8h]; this
0x1800408c2  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800408c9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x1800408ce  mov     esi, eax
0x1800408d0  lea     rcx, [rsp+1E0h+var_1A8]
0x1800408d5  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800408da  lea     rcx, [rsp+1E0h+StringSid]
0x1800408df  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x1800408e4  mov     rcx, rdi
0x1800408e7  jmp     short loc_18004087D
0x1800408e9  mov     rcx, r14; hToken
0x1800408ec  call    cs:__imp_ImpersonateLoggedOnUser
0x1800408f3  nop     dword ptr [rax+rax+00h]
0x1800408f8  test    eax, eax
0x1800408fa  jnz     short loc_180040903
0x1800408fc  mov     edx, 0B9h
0x180040901  jmp     short loc_1800408BB
0x180040903  and     [rsp+1E0h+var_190], 0
0x180040909  lea     rcx, [rsp+1E0h+var_190]
0x18004090e  xor     edx, edx
0x180040910  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040915  mov     rdx, [rsp+1E0h+StringSid]; lpSubKey
0x18004091a  lea     rax, [rsp+1E0h+var_190]
0x18004091f  mov     esi, 0F003Fh
0x180040924  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x180040929  mov     r14, 0FFFFFFFF80000003h
0x180040930  mov     r9d, esi; samDesired
0x180040933  mov     rcx, r14; hKey
0x180040936  xor     r8d, r8d; ulOptions
0x180040939  call    cs:__imp_RegOpenKeyExW
0x180040940  nop     dword ptr [rax+rax+00h]
0x180040945  test    eax, eax
0x180040947  jz      short loc_180040981
0x180040949  mov     rcx, [rbp+0E8h]; this
0x180040950  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x180040957  mov     r9d, eax; char *
0x18004095a  mov     edx, 0BEh; void *
0x18004095f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x180040964  mov     esi, eax
0x180040966  lea     rcx, [rsp+1E0h+var_190]
0x18004096b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040970  call    cs:__imp_RevertToSelf
0x180040977  nop     dword ptr [rax+rax+00h]
0x18004097c  jmp     loc_1800408D0
0x180040981  and     [rsp+1E0h+hKey], 0
0x180040987  lea     rcx, [rsp+1E0h+hKey]
0x18004098c  xor     edx, edx
0x18004098e  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x180040993  mov     rdx, [rsp+1E0h+var_1A8]; lpSubKey
0x180040998  lea     rax, [rsp+1E0h+hKey]
0x18004099d  mov     r9d, esi; samDesired
0x1800409a0  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x1800409a5  xor     r8d, r8d; ulOptions
0x1800409a8  mov     rcx, r14; hKey
0x1800409ab  call    cs:__imp_RegOpenKeyExW
0x1800409b2  nop     dword ptr [rax+rax+00h]
0x1800409b7  test    eax, eax
0x1800409b9  jz      short loc_1800409E4
0x1800409bb  mov     rcx, [rbp+0E8h]; this
0x1800409c2  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x1800409c9  mov     r9d, eax; char *
0x1800409cc  mov     edx, 0C1h; void *
0x1800409d1  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x1800409d6  lea     rcx, [rsp+1E0h+hKey]
0x1800409db  mov     esi, eax
0x1800409dd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x1800409e2  jmp     short loc_180040966
0x1800409e4  lea     rsi, off_180048988; "Software\\Microsoft\\Windows\\CurrentVe"...
0x1800409eb  mov     rdx, [rsi]; lpSubKey
0x1800409ee  mov     rcx, [rsp+1E0h+hKey]; hKey
0x1800409f3  call    cs:__imp_RegDeleteTreeW
0x1800409fa  nop     dword ptr [rax+rax+00h]
0x1800409ff  mov     r14d, eax
0x180040a02  test    eax, 0FFFFFFFDh
0x180040a07  jz      short loc_180040A33
0x180040a09  test    eax, eax
0x180040a0b  jle     short loc_180040A18
0x180040a0d  movzx   r14d, ax
0x180040a11  or      r14d, 80070000h
0x180040a18  call    ?IsEnabled@LUATelemetry@@SA_NE_K@Z; LUATelemetry::IsEnabled(uchar,unsigned __int64)
0x180040a1d  test    al, al
0x180040a1f  jz      short loc_180040A5A
0x180040a21  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x180040a26  mov     r8, [rsi]; unsigned __int16 *
0x180040a29  mov     edx, r14d; int
0x180040a2c  call    ?SettingsSyncErrorContext_@LUATelemetry@@QEAAXJPEAG@Z; LUATelemetry::SettingsSyncErrorContext_(long,ushort *)
0x180040a31  jmp     short loc_180040A5A
0x180040a33  mov     r8, [rsi]; unsigned __int16 *
0x180040a36  mov     rdx, [rsp+1E0h+hKey]; HKEY
0x180040a3b  mov     rcx, [rsp+1E0h+var_190]; HKEY
0x180040a40  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x180040a45  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x180040a49  test    eax, eax
0x180040a4b  jns     short loc_180040A5D
0x180040a4d  mov     rdx, rsi
0x180040a50  lea     rcx, [rsp+1E0h+var_1A0]
0x180040a55  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x180040a5a  xor     r15d, r15d
0x180040a5d  add     rsi, 8
0x180040a61  lea     rax, _load_config_used
0x180040a68  cmp     rsi, rax
0x180040a6b  jnz     loc_1800409EB
0x180040a71  mov     edx, r15d; int
0x180040a74  lea     rcx, [rsp+1E0h+var_180]; this
0x180040a79  call    ?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::RegistrySyncActivity::Stop(int)
0x180040a7e  lea     rcx, [rsp+1E0h+hKey]
0x180040a83  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040a88  lea     rcx, [rsp+1E0h+var_190]
0x180040a8d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x180040a92  call    cs:__imp_RevertToSelf
0x180040a99  nop     dword ptr [rax+rax+00h]
0x180040a9e  lea     rcx, [rsp+1E0h+var_1A8]
0x180040aa3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040aa8  lea     rcx, [rsp+1E0h+StringSid]
0x180040aad  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180040ab2  mov     rcx, rdi; Block
0x180040ab5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040aba  mov     rcx, rbx; Block
0x180040abd  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180040ac2  xor     esi, esi
0x180040ac4  lea     rcx, [rsp+1E0h+var_180]; this
0x180040ac9  call    ??1RegistrySyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity(void)
0x180040ace  mov     eax, esi
0x180040ad0  mov     rcx, [rbp+0E0h+var_30]
0x180040ad7  xor     rcx, rsp; StackCookie
0x180040ada  call    __security_check_cookie
0x180040adf  mov     rbx, [rsp+1E0h+arg_10]
0x180040ae7  add     rsp, 1C0h
0x180040aee  pop     r15
0x180040af0  pop     r14
0x180040af2  pop     rdi
0x180040af3  pop     rsi
0x180040af4  pop     rbp
0x180040af5  retn
```
