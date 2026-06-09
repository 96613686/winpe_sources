# SystemSettings::Prov::CProvisioningPackageItemSetting::CreateInstance(ProvPackageInfo *,SystemSettings::Prov::ActionButtonType,SystemSettings::Prov::CProvisioningPackageItemSetting * *)

- ea: `0x18001314c`
- end: `0x18001357b`
- name: `?CreateInstance@CProvisioningPackageItemSetting@Prov@SystemSettings@@SAJPEAVProvPackageInfo@@UActionButtonType@23@PEAPEAV123@@Z`
- size: `1071`
- prototype: ``
- caller_count: `2`
- callee_count: `19`
- tags: `registry_config, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x180014640`
- `0x180017c00`

## callees

- `0x1800034b8`
- `0x1800067fc`
- `0x1800087ec`
- `0x18000ccb8`
- `0x180010238`
- `0x18001085c`
- `0x18001314c`
- `0x18001e504`
- `0x18001fb98`
- `0x18001fbb8`
- `0x18001fbfc`
- `0x18002019c`
- `0x180021d10`
- `0x180021d3c`
- `0x1800230d8`
- `0x18002341c`
- `0x1800247cc`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x1800132a2`
- `msvcrt!_wcsicmp` at `0x1800132a2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800134b4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800134b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
__int64 __fastcall SystemSettings::Prov::CProvisioningPackageItemSetting::CreateInstance(
        const struct ProvPackageInfo *a1,
        char *a2,
        _QWORD *a3)
{
  unsigned int v6; // ebx
  __int64 v7; // rdi
  ProvPackageInfo *v8; // rax
  char v9; // di
  char v10; // r14
  char v11; // si
  __int64 v12; // rcx
  int ProvisioningProvider; // eax
  __int64 v14; // rdx
  __int64 v15; // rdx
  const wchar_t *v16; // rcx
  __int64 v17; // rax
  __int64 *PackageId; // rax
  __int64 v20; // rcx
  int InstalledPackageDetails; // eax
  __int64 v22; // rdx
  const char *v23; // r9
  __int64 v24; // rax
  int v25; // eax
  void *v26; // rdx
  unsigned int v27; // r8d
  _DWORD *v28; // rcx
  __int64 v29; // rbx
  __int64 v30; // rax
  int v31; // r8d
  int v32; // r8d
  int v33; // r8d
  int v34; // r8d
  PCWSTR StringRawBuffer; // rax
  const char *v36; // r9
  __int64 v37; // rdx
  __int64 v38; // [rsp+20h] [rbp-A8h] BYREF
  unsigned int v39; // [rsp+28h] [rbp-A0h] BYREF
  ProvPackageInfo *v40; // [rsp+30h] [rbp-98h] BYREF
  _DWORD *v41; // [rsp+38h] [rbp-90h] BYREF
  wchar_t *String1[3]; // [rsp+40h] [rbp-88h] BYREF
  unsigned __int64 v43; // [rsp+58h] [rbp-70h]
  void **v44; // [rsp+60h] [rbp-68h] BYREF
  __int64 v45; // [rsp+68h] [rbp-60h] BYREF
  char v46; // [rsp+70h] [rbp-58h]
  _WORD v47[8]; // [rsp+80h] [rbp-48h] BYREF
  __int64 v48; // [rsp+90h] [rbp-38h]
  __int64 v49; // [rsp+98h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+0h]

  *a3 = 0;
  Microsoft::WRL::Details::Make<SystemSettings::Prov::CProvisioningPackageItemSetting,>(&v38);
  if ( !v38 )
  {
    v6 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x308,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)0x8007000ELL,
      0);
    goto LABEL_43;
  }
  v7 = v38 + 256;
  v8 = (ProvPackageInfo *)operator new(0x60u, (const struct std::nothrow_t *)std::nothrow);
  v40 = v8;
  if ( v8 )
    v8 = ProvPackageInfo::ProvPackageInfo(v8, a1);
  std::unique_ptr<ProvPackageInfo>::reset(v7, v8);
  v9 = a2[2];
  *(_BYTE *)(v38 + 249) = v9;
  v10 = a2[1];
  *(_BYTE *)(v38 + 250) = v10;
  v11 = *a2;
  *(_BYTE *)(v38 + 251) = v11;
  v43 = 7;
  String1[2] = 0;
  LOWORD(String1[0]) = 0;
  ProvisioningProvider = CProvisioningSingleton::GetProvisioningProvider(v12, String1);
  v6 = ProvisioningProvider;
  if ( ProvisioningProvider < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x313,
      (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
      (const char *)(unsigned int)ProvisioningProvider,
      v38);
    LOBYTE(v15) = 1;
    std::wstring::_Tidy(String1, v15, 0);
    goto LABEL_43;
  }
  if ( v9 )
  {
    v16 = (const wchar_t *)String1;
    if ( v43 >= 8 )
      v16 = String1[0];
    if ( !_wcsicmp(v16, L"{FF1A3258-FC24-4168-B0E1-76E1EB1555A5}") )
    {
      *(_DWORD *)(v38 + 264) = 0;
      goto LABEL_12;
    }
  }
  if ( v10 && v11 )
  {
    v40 = 0;
    Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
    try
    {
      PackageId = (__int64 *)ProvPackageInfo::GetPackageId(*(_QWORD *)(v38 + 256), &v44);
      InstalledPackageDetails = CProvisioningSingleton::GetInstalledPackageDetails(v20, PackageId, &v40);
      if ( InstalledPackageDetails < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x31D,
          (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
          (const char *)(unsigned int)InstalledPackageDetails,
          v38);
      LOBYTE(v22) = 1;
      std::wstring::_Tidy(&v44, v22, 0);
      if ( !v40 )
        wil::details::in1diag3::_Throw_NullAlloc(
          retaddr,
          (void *)0x31E,
          (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
          v23);
      v39 = 0;
      v41 = 0;
      v24 = *(_QWORD *)v40;
      v44 = (void **)&v41;
      v45 = 0;
      v46 = 1;
      v25 = (*(__int64 (__fastcall **)(ProvPackageInfo *, unsigned int *, __int64 *))(v24 + 104))(v40, &v39, &v45);
      if ( v25 < 0 )
        wil::details::in1diag3::_Throw_Hr(
          retaddr,
          (void *)0x322,
          (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
          (const char *)(unsigned int)v25,
          v38);
      wil::details::out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(&v44);
      v28 = v41;
      if ( !v41 && v39 )
        wil::details::in1diag3::Throw_Hr(retaddr, v26, v27, (const char *)0x80070057LL, v38);
      v49 = 7;
      v48 = 0;
      v47[0] = 0;
      v29 = 0;
      v30 = v38;
      while ( 1 )
      {
        if ( (unsigned int)v29 >= v39 )
        {
LABEL_42:
          LOBYTE(v26) = 1;
          std::wstring::_Tidy(v47, v26, 0);
          wistd::unique_ptr<unsigned int,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
            (void **)&v41,
            0);
          Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v40);
          goto LABEL_46;
        }
        v31 = v28[6 * v29 + 4];
        if ( !v31 )
          goto LABEL_41;
        v32 = v31 - 1;
        if ( !v32 )
        {
          *(_DWORD *)(v30 + 264) = 3;
          goto LABEL_42;
        }
        v33 = v32 - 1;
        if ( !v33 )
        {
LABEL_41:
          *(_DWORD *)(v30 + 264) = 4;
          goto LABEL_42;
        }
        v34 = v33 - 1;
        if ( !v34 )
        {
          *(_DWORD *)(v30 + 264) = 5;
          goto LABEL_42;
        }
        if ( v34 == 1 )
        {
          StringRawBuffer = WindowsGetStringRawBuffer(*(HSTRING *)&v28[6 * v29 + 2], 0);
          std::wstring::assign(v47, StringRawBuffer);
          v30 = v38;
          if ( v48 )
          {
            *(_DWORD *)(v38 + 264) = 2;
            goto LABEL_37;
          }
          if ( *(_DWORD *)(v38 + 264) == 2 )
            goto LABEL_38;
        }
        *(_DWORD *)(v30 + 264) = 1;
LABEL_37:
        v30 = v38;
LABEL_38:
        v29 = (unsigned int)(v29 + 1);
        v28 = v41;
      }
    }
    catch ( ... )
    {
      v39 = wil::details::in1diag3::Return_CaughtException(
              retaddr,
              (void *)0x353,
              (unsigned int)"onecoreuap\\admin\\prov\\systemsettingshandlers\\lib\\provisioning.cpp",
              v36);
      LOBYTE(v37) = 1;
      std::wstring::_Tidy(String1, v37, 0);
      v6 = v39;
LABEL_43:
      Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v38);
      return v6;
    }
LABEL_46:
    ;
  }
LABEL_12:
  v17 = v38;
  v38 = 0;
  *a3 = v17;
  LOBYTE(v14) = 1;
  std::wstring::_Tidy(String1, v14, 0);
  Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(&v38);
  return 0;
}

```

## disassembly

```asm
0x18001314c  mov     [rsp+arg_8], rbx
0x180013151  mov     [rsp+arg_18], rsi
0x180013156  push    rdi
0x180013157  push    r14
0x180013159  push    r15
0x18001315b  sub     rsp, 0B0h
0x180013162  mov     rax, cs:__security_cookie
0x180013169  xor     rax, rsp
0x18001316c  mov     [rsp+0C8h+var_28], rax
0x180013174  mov     r15, r8
0x180013177  mov     rsi, rdx
0x18001317a  mov     rbx, rcx
0x18001317d  mov     qword ptr [r8], 0
0x180013184  lea     rcx, [rsp+0C8h+var_A8]
0x180013189  call    ??$Make@VCProvisioningPackageItemSetting@Prov@SystemSettings@@$$V@Details@WRL@Microsoft@@YA?AV?$ComPtr@VCProvisioningPackageItemSetting@Prov@SystemSettings@@@12@XZ; Microsoft::WRL::Details::Make<SystemSettings::Prov::CProvisioningPackageItemSetting,>(void)
0x18001318e  nop
0x18001318f  mov     rax, [rsp+0C8h+var_A8]
0x180013194  test    rax, rax
0x180013197  jnz     short loc_1800131BF
0x180013199  mov     rcx, [rsp+0C8h]; this
0x1800131a1  mov     ebx, 8007000Eh
0x1800131a6  mov     r9d, ebx; char *
0x1800131a9  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800131b0  mov     edx, 308h; void *
0x1800131b5  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800131ba  jmp     loc_18001356A
0x1800131bf  lea     rdi, [rax+100h]
0x1800131c6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800131cd  mov     ecx, 60h ; '`'; unsigned __int64
0x1800131d2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1800131d7  mov     [rsp+0C8h+var_98], rax
0x1800131dc  test    rax, rax
0x1800131df  jz      short loc_1800131ED
0x1800131e1  mov     rdx, rbx; struct ProvPackageInfo *
0x1800131e4  mov     rcx, rax; this
0x1800131e7  call    ??0ProvPackageInfo@@QEAA@AEBV0@@Z; ProvPackageInfo::ProvPackageInfo(ProvPackageInfo const &)
0x1800131ec  nop
0x1800131ed  mov     rdx, rax
0x1800131f0  mov     rcx, rdi
0x1800131f3  call    ?reset@?$unique_ptr@VProvPackageInfo@@U?$default_delete@VProvPackageInfo@@@std@@@std@@QEAAXPEAVProvPackageInfo@@@Z; std::unique_ptr<ProvPackageInfo>::reset(ProvPackageInfo *)
0x1800131f8  mov     dil, [rsi+2]
0x1800131fc  mov     rax, [rsp+0C8h+var_A8]
0x180013201  mov     [rax+0F9h], dil
0x180013208  mov     r14b, [rsi+1]
0x18001320c  mov     rax, [rsp+0C8h+var_A8]
0x180013211  mov     [rax+0FAh], r14b
0x180013218  mov     sil, [rsi]
0x18001321b  mov     rax, [rsp+0C8h+var_A8]
0x180013220  mov     [rax+0FBh], sil
0x180013227  mov     [rsp+0C8h+var_70], 7
0x180013230  mov     [rsp+0C8h+var_78], 0
0x180013239  xor     eax, eax
0x18001323b  mov     word ptr [rsp+0C8h+String1], ax
0x180013240  lea     rdx, [rsp+0C8h+String1]
0x180013245  call    ?GetProvisioningProvider@CProvisioningSingleton@@QEAAJAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; CProvisioningSingleton::GetProvisioningProvider(std::wstring &)
0x18001324a  mov     ebx, eax
0x18001324c  test    eax, eax
0x18001324e  jns     short loc_180013281
0x180013250  mov     rcx, [rsp+0C8h]; this
0x180013258  mov     r9d, eax; char *
0x18001325b  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180013262  mov     edx, 313h; void *
0x180013267  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001326c  nop
0x18001326d  xor     r8d, r8d
0x180013270  mov     dl, 1
0x180013272  lea     rcx, [rsp+0C8h+String1]
0x180013277  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001327c  jmp     loc_18001356A
0x180013281  test    dil, dil
0x180013284  jz      loc_180013318
0x18001328a  lea     rcx, [rsp+0C8h+String1]
0x18001328f  cmp     [rsp+0C8h+var_70], 8
0x180013295  cmovnb  rcx, [rsp+0C8h+String1]; String1
0x18001329b  lea     rdx, aFf1a3258Fc2441_0; "{FF1A3258-FC24-4168-B0E1-76E1EB1555A5}"
0x1800132a2  call    cs:__imp__wcsicmp
0x1800132a9  nop     dword ptr [rax+rax+00h]
0x1800132ae  test    eax, eax
0x1800132b0  jnz     short loc_180013318
0x1800132b2  mov     rax, [rsp+0C8h+var_A8]
0x1800132b7  mov     dword ptr [rax+108h], 0
0x1800132c1  mov     rax, [rsp+0C8h+var_A8]
0x1800132c6  mov     [rsp+0C8h+var_A8], 0
0x1800132cf  mov     [r15], rax
0x1800132d2  xor     r8d, r8d
0x1800132d5  mov     dl, 1
0x1800132d7  lea     rcx, [rsp+0C8h+String1]
0x1800132dc  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x1800132e1  nop
0x1800132e2  lea     rcx, [rsp+0C8h+var_A8]
0x1800132e7  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x1800132ec  xor     eax, eax
0x1800132ee  mov     rcx, [rsp+0C8h+var_28]
0x1800132f6  xor     rcx, rsp; StackCookie
0x1800132f9  call    __security_check_cookie
0x1800132fe  lea     r11, [rsp+0C8h+var_18]
0x180013306  mov     rbx, [r11+28h]
0x18001330a  mov     rsi, [r11+38h]
0x18001330e  mov     rsp, r11
0x180013311  pop     r15
0x180013313  pop     r14
0x180013315  pop     rdi
0x180013316  retn
0x180013318  test    r14b, r14b
0x18001331b  jz      short loc_1800132C1
0x18001331d  test    sil, sil
0x180013320  jz      short loc_1800132C1
0x180013322  mov     [rsp+0C8h+var_98], 0
0x18001332b  lea     rcx, [rsp+0C8h+var_98]
0x180013330  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180013335  lea     rdx, [rsp+0C8h+var_68]
0x18001333a  mov     rcx, [rsp+0C8h+var_A8]
0x18001333f  mov     rcx, [rcx+100h]
0x180013346  call    ?GetPackageId@ProvPackageInfo@@QEBA?AV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@XZ; ProvPackageInfo::GetPackageId(void)
0x18001334b  nop
0x18001334c  lea     r8, [rsp+0C8h+var_98]
0x180013351  mov     rdx, rax
0x180013354  call    ?GetInstalledPackageDetails@CProvisioningSingleton@@QEAAJAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@PEAPEAUIPackage@Provisioning@Management@Windows@@@Z; CProvisioningSingleton::GetInstalledPackageDetails(std::wstring const &,Windows::Management::Provisioning::IPackage * *)
0x180013359  mov     rcx, [rsp+0C8h]; this
0x180013361  test    eax, eax
0x180013363  jns     short loc_18001337A
0x180013365  mov     r9d, eax; char *
0x180013368  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x18001336f  mov     edx, 31Dh; void *
0x180013374  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001337a  xor     r8d, r8d
0x18001337d  mov     dl, 1
0x18001337f  lea     rcx, [rsp+0C8h+var_68]
0x180013384  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013389  mov     rax, [rsp+0C8h]
0x180013391  mov     rcx, [rsp+0C8h+var_98]
0x180013396  test    rcx, rcx
0x180013399  jnz     short loc_1800133AF
0x18001339b  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x1800133a2  mov     edx, 31Eh; void *
0x1800133a7  mov     rcx, rax; this
0x1800133aa  call    ?_Throw_NullAlloc@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_Throw_NullAlloc(void *,uint,char const *)
0x1800133af  mov     [rsp+0C8h+var_A0], 0
0x1800133b7  mov     [rsp+0C8h+var_90], 0
0x1800133c0  mov     rax, [rcx]
0x1800133c3  lea     rdx, [rsp+0C8h+var_90]
0x1800133c8  mov     [rsp+0C8h+var_68], rdx
0x1800133cd  mov     [rsp+0C8h+var_60], 0
0x1800133d6  mov     [rsp+0C8h+var_58], 1
0x1800133db  lea     r8, [rsp+0C8h+var_60]
0x1800133e0  lea     rdx, [rsp+0C8h+var_A0]
0x1800133e5  mov     rax, [rax+68h]
0x1800133e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800133ee  mov     rcx, [rsp+0C8h]; this
0x1800133f6  test    eax, eax
0x1800133f8  jns     short loc_18001340F
0x1800133fa  mov     r9d, eax; char *
0x1800133fd  lea     r8, aOnecoreuapAdmi_1; "onecoreuap\\admin\\prov\\systemsettings"...
0x180013404  mov     edx, 322h; void *
0x180013409  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x18001340f  lea     rcx, [rsp+0C8h+var_68]
0x180013414  call    ??1?$out_param_t@V?$unique_ptr@UProvisioningResult@Provisioning@Management@Windows@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::~out_param_t<wistd::unique_ptr<Windows::Management::Provisioning::ProvisioningResult,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(void)
0x180013419  mov     rcx, [rsp+0C8h+var_90]
0x18001341e  test    rcx, rcx
0x180013421  jnz     short loc_18001343C
0x180013423  cmp     [rsp+0C8h+var_A0], ecx
0x180013427  jz      short loc_18001343C
0x180013429  mov     rcx, [rsp+0C8h]; this
0x180013431  mov     r9d, 80070057h; char *
0x180013437  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
0x18001343c  mov     [rsp+0C8h+var_30], 7
0x180013448  mov     [rsp+0C8h+var_38], 0
0x180013454  xor     eax, eax
0x180013456  mov     [rsp+0C8h+var_48], ax
0x18001345e  xor     ebx, ebx
0x180013460  mov     rax, [rsp+0C8h+var_A8]
0x180013465  cmp     ebx, [rsp+0C8h+var_A0]
0x180013469  jnb     loc_180013528
0x18001346f  lea     r9, [rbx+rbx*2]
0x180013473  mov     r8d, [rcx+r9*8+10h]
0x180013478  test    r8d, r8d
0x18001347b  jz      loc_18001351E
0x180013481  sub     r8d, 1
0x180013485  jz      loc_180013512
0x18001348b  sub     r8d, 1
0x18001348f  jz      loc_18001351E
0x180013495  sub     r8d, 1
0x180013499  jz      short loc_180013506
0x18001349b  cmp     r8d, 1
0x18001349f  jz      short loc_1800134AD
0x1800134a1  mov     dword ptr [rax+108h], 1
0x1800134ab  jmp     short loc_1800134F5
0x1800134ad  xor     edx, edx; length
0x1800134af  mov     rcx, [rcx+r9*8+8]; string
0x1800134b4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800134bb  nop     dword ptr [rax+rax+00h]
0x1800134c0  mov     rdx, rax
0x1800134c3  lea     rcx, [rsp+0C8h+var_48]
0x1800134cb  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG@Z; std::wstring::assign(ushort const *)
0x1800134d0  mov     rax, [rsp+0C8h+var_A8]
0x1800134d5  cmp     [rsp+0C8h+var_38], 0
0x1800134de  jnz     short loc_1800134EB
0x1800134e0  cmp     dword ptr [rax+108h], 2
0x1800134e7  jz      short loc_1800134FA
0x1800134e9  jmp     short loc_1800134A1
0x1800134eb  mov     dword ptr [rax+108h], 2
0x1800134f5  mov     rax, [rsp+0C8h+var_A8]
0x1800134fa  inc     ebx
0x1800134fc  mov     rcx, [rsp+0C8h+var_90]
0x180013501  jmp     loc_180013465
0x180013506  mov     dword ptr [rax+108h], 5
0x180013510  jmp     short loc_180013528
0x180013512  mov     dword ptr [rax+108h], 3
0x18001351c  jmp     short loc_180013528
0x18001351e  mov     dword ptr [rax+108h], 4
0x180013528  xor     r8d, r8d
0x18001352b  mov     dl, 1
0x18001352d  lea     rcx, [rsp+0C8h+var_48]
0x180013535  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x18001353a  nop
0x18001353b  xor     edx, edx
0x18001353d  lea     rcx, [rsp+0C8h+var_90]
0x180013542  call    ?reset@?$unique_ptr@IU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAI@Z; wistd::unique_ptr<uint,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(uint *)
0x180013547  nop
0x180013548  lea     rcx, [rsp+0C8h+var_98]
0x18001354d  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180013552  jmp     loc_1800132C1
0x180013557  xor     r8d, r8d
0x18001355a  mov     dl, 1
0x18001355c  lea     rcx, [rsp+0C8h+String1]
0x180013561  call    ?_Tidy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_N_K@Z; std::wstring::_Tidy(bool,unsigned __int64)
0x180013566  mov     ebx, [rsp+0C8h+var_A0]
0x18001356a  lea     rcx, [rsp+0C8h+var_A8]
0x18001356f  call    ?InternalRelease@?$ComPtr@VCProvisioningDeleteSetting@Prov@SystemSettings@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<SystemSettings::Prov::CProvisioningDeleteSetting>::InternalRelease(void)
0x180013574  mov     eax, ebx
0x180013576  jmp     loc_1800132EE
```
