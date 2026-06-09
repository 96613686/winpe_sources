# AiRegistrySync(void *,void *)

- ea: `0x18003eb60`
- end: `0x18003ef27`
- name: `?AiRegistrySync@@YAJPEAX0@Z`
- size: `967`
- prototype: `int(void *, void *)`
- caller_count: `1`
- callee_count: `20`
- tags: `file_ops, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18003ef30`

## callees

- `0x180007c78`
- `0x180010710`
- `0x1800124f4`
- `0x18001800c`
- `0x180018150`
- `0x180018280`
- `0x18001b0c4`
- `0x18001dbf8`
- `0x180021008`
- `0x180028840`
- `0x180033e50`
- `0x1800396d0`
- `0x18003e6a0`
- `0x18003e708`
- `0x18003e844`
- `0x18003eb60`
- `0x18003efb0`
- `0x18003f0d0`
- `0x18003f3dc`
- `0x180042950`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003ed1c`
- `api-ms-win-security-base-l1-1-0!ImpersonateLoggedOnUser` at `0x18003ed1c`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003eda0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003eec2`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003eda0`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x18003eec2`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eddb`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003ed69`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18003eddb`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003ee23`
- `api-ms-win-core-registry-l1-1-0!RegDeleteTreeW` at `0x18003ee23`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003ec6f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003ecd6`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003ec6f`
- `api-ms-win-security-sddl-l1-1-0!ConvertSidToStringSidW` at `0x18003ecd6`

## string_xrefs

- `0x18003eb92`: `RegistrySyncActivity`
- `0x18003ebdf`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003ec15`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003ec86`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003ecf2`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003ed80`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`
- `0x18003edf2`: `onecoreuap\ds\security\services\lua\appinfo\sync.cxx`

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
    v17 = (LPCWSTR *)off_180046958;
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
      if ( ++v17 == (LPCWSTR *)Feature_ValAccTest__private_requiresFeatures )
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
0x18003eb60  mov     [rsp-8+arg_10], rbx
0x18003eb65  push    rbp
0x18003eb66  push    rsi
0x18003eb67  push    rdi
0x18003eb68  push    r14
0x18003eb6a  push    r15
0x18003eb6c  lea     rbp, [rsp-0C0h]
0x18003eb74  sub     rsp, 1C0h
0x18003eb7b  mov     rax, cs:__security_cookie
0x18003eb82  xor     rax, rsp
0x18003eb85  mov     [rbp+0E0h+var_30], rax
0x18003eb8c  mov     r14, rdx
0x18003eb8f  mov     rbx, rcx
0x18003eb92  lea     rdx, aRegistrysyncac; "RegistrySyncActivity"
0x18003eb99  lea     rcx, [rsp+1E0h+var_180]; struct wil::details::IFailureCallback *
0x18003eb9e  call    ??0?$ActivityBase@VLUATelemetry@@$00$0EAAAAAAAAAAA@$04$0DAAAAAA@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAA@PEBD_N@Z; wil::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>::ActivityBase<LUATelemetry,1,70368744177664,5,50331648,_TlgReflectorTag_Param0IsProviderType>(char const *,bool)
0x18003eba3  lea     rax, ??_7RegistrySyncActivity@LUATelemetry@@6B@; const LUATelemetry::RegistrySyncActivity::`vftable'
0x18003ebaa  lea     rcx, [rsp+1E0h+var_180]; this
0x18003ebaf  mov     [rsp+1E0h+var_180], rax
0x18003ebb4  call    ?StartActivity@RegistrySyncActivity@LUATelemetry@@QEAAXXZ; LUATelemetry::RegistrySyncActivity::StartActivity(void)
0x18003ebb9  and     [rsp+1E0h+var_1A0], 0
0x18003ebbf  lea     rcx, [rsp+1E0h+var_1A0]
0x18003ebc4  mov     rdx, rbx
0x18003ebc7  mov     r15d, 1
0x18003ebcd  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18003ebd2  mov     esi, eax
0x18003ebd4  test    eax, eax
0x18003ebd6  jns     short loc_18003EBF5
0x18003ebd8  mov     rcx, [rbp+0E8h]; this
0x18003ebdf  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003ebe6  mov     r9d, eax; char *
0x18003ebe9  mov     edx, 0ADh; void *
0x18003ebee  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ebf3  jmp     short loc_18003EC38
0x18003ebf5  and     [rsp+1E0h+Block], 0
0x18003ebfb  lea     rcx, [rsp+1E0h+Block]
0x18003ec00  mov     rdx, r14
0x18003ec03  call    ??$get_token_information_nothrow@U_TOKEN_USER@@$0A@@wil@@YAJAEAV?$unique_ptr@U_TOKEN_USER@@Utoken_info_deleter@details@wil@@@wistd@@PEAX@Z; wil::get_token_information_nothrow<_TOKEN_USER,0>(wistd::unique_ptr<_TOKEN_USER,wil::details::token_info_deleter> &,void *)
0x18003ec08  mov     esi, eax
0x18003ec0a  test    eax, eax
0x18003ec0c  jns     short loc_18003EC50
0x18003ec0e  mov     rcx, [rbp+0E8h]; this
0x18003ec15  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003ec1c  mov     r9d, eax; char *
0x18003ec1f  mov     edx, 0B0h; void *
0x18003ec24  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003ec29  mov     rcx, [rsp+1E0h+Block]; Block
0x18003ec2e  test    rcx, rcx
0x18003ec31  jz      short loc_18003EC38
0x18003ec33  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ec38  mov     rcx, [rsp+1E0h+var_1A0]; Block
0x18003ec3d  test    rcx, rcx
0x18003ec40  jz      loc_18003EEF4
0x18003ec46  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ec4b  jmp     loc_18003EEF4
0x18003ec50  and     [rsp+1E0h+StringSid], 0
0x18003ec56  lea     rcx, [rsp+1E0h+StringSid]
0x18003ec5b  xor     edx, edx
0x18003ec5d  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003ec62  mov     rbx, [rsp+1E0h+var_1A0]
0x18003ec67  lea     rdx, [rsp+1E0h+StringSid]; StringSid
0x18003ec6c  mov     rcx, [rbx]; Sid
0x18003ec6f  call    cs:__imp_ConvertSidToStringSidW
0x18003ec76  nop     dword ptr [rax+rax+00h]
0x18003ec7b  test    eax, eax
0x18003ec7d  jnz     short loc_18003ECB7
0x18003ec7f  mov     rcx, [rbp+0E8h]; this
0x18003ec86  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003ec8d  mov     edx, 0B3h; void *
0x18003ec92  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ec97  lea     rcx, [rsp+1E0h+StringSid]
0x18003ec9c  mov     esi, eax
0x18003ec9e  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003eca3  mov     rcx, [rsp+1E0h+Block]; Block
0x18003eca8  test    rcx, rcx
0x18003ecab  jz      short loc_18003ECB2
0x18003ecad  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003ecb2  mov     rcx, rbx
0x18003ecb5  jmp     short loc_18003EC46
0x18003ecb7  and     [rsp+1E0h+var_1A8], 0
0x18003ecbd  lea     rcx, [rsp+1E0h+var_1A8]
0x18003ecc2  xor     edx, edx
0x18003ecc4  call    ?reset@?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAAXPEAG@Z; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::reset(ushort *)
0x18003ecc9  mov     rdi, [rsp+1E0h+Block]
0x18003ecce  lea     rdx, [rsp+1E0h+var_1A8]; StringSid
0x18003ecd3  mov     rcx, [rdi]; Sid
0x18003ecd6  call    cs:__imp_ConvertSidToStringSidW
0x18003ecdd  nop     dword ptr [rax+rax+00h]
0x18003ece2  test    eax, eax
0x18003ece4  jnz     short loc_18003ED19
0x18003ece6  mov     edx, 0B6h; void *
0x18003eceb  mov     rcx, [rbp+0E8h]; this
0x18003ecf2  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003ecf9  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18003ecfe  mov     esi, eax
0x18003ed00  lea     rcx, [rsp+1E0h+var_1A8]
0x18003ed05  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ed0a  lea     rcx, [rsp+1E0h+StringSid]
0x18003ed0f  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003ed14  mov     rcx, rdi
0x18003ed17  jmp     short loc_18003ECAD
0x18003ed19  mov     rcx, r14; hToken
0x18003ed1c  call    cs:__imp_ImpersonateLoggedOnUser
0x18003ed23  nop     dword ptr [rax+rax+00h]
0x18003ed28  test    eax, eax
0x18003ed2a  jnz     short loc_18003ED33
0x18003ed2c  mov     edx, 0B9h
0x18003ed31  jmp     short loc_18003ECEB
0x18003ed33  and     [rsp+1E0h+var_190], 0
0x18003ed39  lea     rcx, [rsp+1E0h+var_190]
0x18003ed3e  xor     edx, edx
0x18003ed40  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003ed45  mov     rdx, [rsp+1E0h+StringSid]; lpSubKey
0x18003ed4a  lea     rax, [rsp+1E0h+var_190]
0x18003ed4f  mov     esi, 0F003Fh
0x18003ed54  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x18003ed59  mov     r14, 0FFFFFFFF80000003h
0x18003ed60  mov     r9d, esi; samDesired
0x18003ed63  mov     rcx, r14; hKey
0x18003ed66  xor     r8d, r8d; ulOptions
0x18003ed69  call    cs:__imp_RegOpenKeyExW
0x18003ed70  nop     dword ptr [rax+rax+00h]
0x18003ed75  test    eax, eax
0x18003ed77  jz      short loc_18003EDB1
0x18003ed79  mov     rcx, [rbp+0E8h]; this
0x18003ed80  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003ed87  mov     r9d, eax; char *
0x18003ed8a  mov     edx, 0BEh; void *
0x18003ed8f  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ed94  mov     esi, eax
0x18003ed96  lea     rcx, [rsp+1E0h+var_190]
0x18003ed9b  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003eda0  call    cs:__imp_RevertToSelf
0x18003eda7  nop     dword ptr [rax+rax+00h]
0x18003edac  jmp     loc_18003ED00
0x18003edb1  and     [rsp+1E0h+hKey], 0
0x18003edb7  lea     rcx, [rsp+1E0h+hKey]
0x18003edbc  xor     edx, edx
0x18003edbe  call    ?reset@?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAAXPEAUHKEY__@@@Z; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::reset(HKEY__ *)
0x18003edc3  mov     rdx, [rsp+1E0h+var_1A8]; lpSubKey
0x18003edc8  lea     rax, [rsp+1E0h+hKey]
0x18003edcd  mov     r9d, esi; samDesired
0x18003edd0  mov     qword ptr [rsp+1E0h+phkResult], rax; unsigned int
0x18003edd5  xor     r8d, r8d; ulOptions
0x18003edd8  mov     rcx, r14; hKey
0x18003eddb  call    cs:__imp_RegOpenKeyExW
0x18003ede2  nop     dword ptr [rax+rax+00h]
0x18003ede7  test    eax, eax
0x18003ede9  jz      short loc_18003EE14
0x18003edeb  mov     rcx, [rbp+0E8h]; this
0x18003edf2  lea     r8, aOnecoreuapDsSe; "onecoreuap\\ds\\security\\services\\lua"...
0x18003edf9  mov     r9d, eax; char *
0x18003edfc  mov     edx, 0C1h; void *
0x18003ee01  call    ?Return_Win32@in1diag3@details@wil@@YAJPEAXIPEBDK@Z; wil::details::in1diag3::Return_Win32(void *,uint,char const *,ulong)
0x18003ee06  lea     rcx, [rsp+1E0h+hKey]
0x18003ee0b  mov     esi, eax
0x18003ee0d  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003ee12  jmp     short loc_18003ED96
0x18003ee14  lea     rsi, off_180046958; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18003ee1b  mov     rdx, [rsi]; lpSubKey
0x18003ee1e  mov     rcx, [rsp+1E0h+hKey]; hKey
0x18003ee23  call    cs:__imp_RegDeleteTreeW
0x18003ee2a  nop     dword ptr [rax+rax+00h]
0x18003ee2f  mov     r14d, eax
0x18003ee32  test    eax, 0FFFFFFFDh
0x18003ee37  jz      short loc_18003EE63
0x18003ee39  test    eax, eax
0x18003ee3b  jle     short loc_18003EE48
0x18003ee3d  movzx   r14d, ax
0x18003ee41  or      r14d, 80070000h
0x18003ee48  call    ?IsEnabled@LUATelemetry@@SA_NE_K@Z; LUATelemetry::IsEnabled(uchar,unsigned __int64)
0x18003ee4d  test    al, al
0x18003ee4f  jz      short loc_18003EE8A
0x18003ee51  call    ?Instance@LUATelemetry@@KAPEAV1@XZ; LUATelemetry::Instance(void)
0x18003ee56  mov     r8, [rsi]; unsigned __int16 *
0x18003ee59  mov     edx, r14d; int
0x18003ee5c  call    ?SettingsSyncErrorContext_@LUATelemetry@@QEAAXJPEAG@Z; LUATelemetry::SettingsSyncErrorContext_(long,ushort *)
0x18003ee61  jmp     short loc_18003EE8A
0x18003ee63  mov     r8, [rsi]; unsigned __int16 *
0x18003ee66  mov     rdx, [rsp+1E0h+hKey]; HKEY
0x18003ee6b  mov     rcx, [rsp+1E0h+var_190]; HKEY
0x18003ee70  call    ?AiCopyRegistry@@YAJPEAUHKEY__@@0PEAG@Z; AiCopyRegistry(HKEY__ *,HKEY__ *,ushort *)
0x18003ee75  mov     dword ptr [rsp+1E0h+var_1A0], eax
0x18003ee79  test    eax, eax
0x18003ee7b  jns     short loc_18003EE8D
0x18003ee7d  mov     rdx, rsi
0x18003ee80  lea     rcx, [rsp+1E0h+var_1A0]
0x18003ee85  call    ??$SettingsSyncErrorContext@AEAJAEBQEAG@LUATelemetry@@SAXAEAJAEBQEAG@Z; LUATelemetry::SettingsSyncErrorContext<long &,ushort * const &>(long &,ushort * const &)
0x18003ee8a  xor     r15d, r15d
0x18003ee8d  add     rsi, 8
0x18003ee91  lea     rax, Feature_ValAccTest__private_requiresFeatures
0x18003ee98  cmp     rsi, rax
0x18003ee9b  jnz     loc_18003EE1B
0x18003eea1  mov     edx, r15d; int
0x18003eea4  lea     rcx, [rsp+1E0h+var_180]; this
0x18003eea9  call    ?Stop@RegistrySyncActivity@LUATelemetry@@QEAAXH@Z; LUATelemetry::RegistrySyncActivity::Stop(int)
0x18003eeae  lea     rcx, [rsp+1E0h+hKey]
0x18003eeb3  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003eeb8  lea     rcx, [rsp+1E0h+var_190]
0x18003eebd  call    ??1?$unique_storage@U?$resource_policy@PEAUHKEY__@@P6AJPEAU1@@Z$1?RegCloseKey@@YAJ0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<HKEY__ *,long (*)(HKEY__ *),&RegCloseKey(HKEY__ *),wistd::integral_constant<unsigned __int64,0>,HKEY__ *,HKEY__ *,0,std::nullptr_t>>(void)
0x18003eec2  call    cs:__imp_RevertToSelf
0x18003eec9  nop     dword ptr [rax+rax+00h]
0x18003eece  lea     rcx, [rsp+1E0h+var_1A8]
0x18003eed3  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003eed8  lea     rcx, [rsp+1E0h+StringSid]
0x18003eedd  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void * (*)(void *),&LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x18003eee2  mov     rcx, rdi; Block
0x18003eee5  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003eeea  mov     rcx, rbx; Block
0x18003eeed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18003eef2  xor     esi, esi
0x18003eef4  lea     rcx, [rsp+1E0h+var_180]; this
0x18003eef9  call    ??1RegistrySyncActivity@LUATelemetry@@QEAA@XZ; LUATelemetry::RegistrySyncActivity::~RegistrySyncActivity(void)
0x18003eefe  mov     eax, esi
0x18003ef00  mov     rcx, [rbp+0E0h+var_30]
0x18003ef07  xor     rcx, rsp; StackCookie
0x18003ef0a  call    __security_check_cookie
0x18003ef0f  mov     rbx, [rsp+1E0h+arg_10]
0x18003ef17  add     rsp, 1C0h
0x18003ef1e  pop     r15
0x18003ef20  pop     r14
0x18003ef22  pop     rdi
0x18003ef23  pop     rsi
0x18003ef24  pop     rbp
0x18003ef25  retn
```
