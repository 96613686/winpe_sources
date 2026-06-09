# MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense(void)

- ea: `0x18004e0e0`
- end: `0x18004e4a7`
- name: `?RemovePackageLicense@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `967`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048920`

## callees

- `0x18000d3dc`
- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180041770`
- `0x180043fb4`
- `0x18004ba8c`
- `0x18004c420`
- `0x18004e0e0`
- `0x18006c910`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004e18d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004e218`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004e452`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004e46f`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004e18d`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004e218`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004e452`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004e46f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e349`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004e349`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e2de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e2de`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e35e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e37a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e35e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004e37a`

## string_xrefs

- `0x18004e3bb`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004e3f2`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004e16e`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e1f9`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e270`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e2c3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e433`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e2a0`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e1ea`: `Failed to check install status of package'%ws'`
- `0x18004e299`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense`
- `0x18004e250`: `Choosing not to remove license for package '%s' because it is installed/staged by other users`
- `0x18004e3ac`: `Unable to GetProcAddress 'HrRemoveAppxLicense'`
- `0x18004e33e`: `HrRemoveAppxLicense`

## pseudocode

```c
// Hidden C++ exception states: #wind=2 #try_helpers=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this)
{
  char *v2; // rbx
  char *v3; // rdx
  int PackageFamilyFromFullName; // edi
  __int64 v6; // rax
  const unsigned __int16 *v7; // rdx
  int IsPackageInstalled; // edi
  char **v9; // r8
  int v10; // eax
  void *v11; // rbx
  int v12; // eax
  __int64 v13; // rax
  __int64 v14; // rdi
  unsigned int v15; // r14d
  __int64 v16; // r15
  char **v17; // rsi
  int Dynamic; // eax
  unsigned int v19; // ebx
  __int64 v20; // rdx
  FARPROC ProcAddress; // rax
  signed int LastError; // eax
  bool v23; // sf
  signed int v24; // eax
  const char *v25; // rax
  int v26; // [rsp+20h] [rbp-68h]
  char *v27; // [rsp+28h] [rbp-60h]
  int v28; // [rsp+30h] [rbp-58h] BYREF
  LPVOID pv; // [rsp+38h] [rbp-50h] BYREF
  char *v30[3]; // [rsp+40h] [rbp-48h] BYREF
  unsigned __int64 v31; // [rsp+58h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]

  v28 = 0;
  v31 = 7;
  v30[2] = 0;
  LOWORD(v30[0]) = 0;
  v2 = (char *)this + 48;
  if ( *((_QWORD *)this + 9) < 8u )
    v3 = (char *)this + 48;
  else
    v3 = *(char **)v2;
  PackageFamilyFromFullName = MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(
                                this,
                                v3,
                                v30);
  if ( PackageFamilyFromFullName < 0 )
  {
    if ( *((_QWORD *)v2 + 3) >= 8u )
      v2 = *(char **)v2;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x73F,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)PackageFamilyFromFullName,
      (int)"Failed to translate package moniker to'%ws' package family moniker",
      v2);
    if ( v31 >= 8 )
      operator delete(v30[0]);
    return (unsigned int)PackageFamilyFromFullName;
  }
  v6 = *((_QWORD *)this + 2);
  if ( *(_DWORD *)(v6 + 600) )
  {
    v7 = *((_QWORD *)v2 + 3) < 8u ? (const unsigned __int16 *)v2 : *(const unsigned __int16 **)v2;
    IsPackageInstalled = MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::IsPackageInstalled(
                           (MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *)(v6 + 320),
                           v7,
                           &v28);
    if ( IsPackageInstalled < 0 )
    {
      if ( *((_QWORD *)v2 + 3) >= 8u )
        v2 = *(char **)v2;
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x748,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)IsPackageInstalled,
        (int)"Failed to check install status of package'%ws'",
        v2);
      if ( v31 >= 8 )
        operator delete(v30[0]);
      return (unsigned int)IsPackageInstalled;
    }
  }
  if ( v28 )
  {
    pv = 0;
    v9 = v30;
    if ( v31 >= 8 )
      v9 = (char **)v30[0];
    v10 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
            (char *)&pv,
            L"Choosing not to remove license for package '%s' because it is installed/staged by other users",
            v9);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x754,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v10,
        v26);
    v11 = pv;
    v12 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            L"MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense",
            1884);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x75C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v12,
        2);
    if ( v11 )
      CoTaskMemFree(v11);
    goto LABEL_52;
  }
  v13 = *((_QWORD *)this + 2);
  v14 = v13 + 456;
  v15 = *(_DWORD *)(v13 + 600);
  v16 = *(_QWORD *)(v13 + 568);
  v17 = v30;
  if ( v31 >= 8 )
    v17 = (char **)v30[0];
  Dynamic = MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::COemLicense>::LoadDynamic(v13 + 456);
  v19 = Dynamic;
  if ( Dynamic < 0 )
  {
    v20 = 599;
LABEL_46:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v20,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
      (const char *)(unsigned int)Dynamic,
      v26);
    goto LABEL_47;
  }
  ProcAddress = *(FARPROC *)(v14 + 64);
  if ( ProcAddress
    || (ProcAddress = GetProcAddress(*(HMODULE *)(v14 + 8), "HrRemoveAppxLicense"),
        (*(_QWORD *)(v14 + 64) = ProcAddress) != 0) )
  {
    Dynamic = ((__int64 (__fastcall *)(char **, __int64, _QWORD))ProcAddress)(v17, v16, v15);
    v19 = Dynamic;
    if ( Dynamic >= 0 )
    {
LABEL_52:
      if ( v31 >= 8 )
        operator delete(v30[0]);
      return 0;
    }
    v20 = 611;
    goto LABEL_46;
  }
  LastError = GetLastError();
  v23 = LastError < 0;
  if ( LastError > 0 )
    v23 = 1;
  if ( v23 )
  {
    v24 = GetLastError();
    v19 = v24;
    if ( v24 > 0 )
      v19 = (unsigned __int16)v24 | 0x80070000;
    if ( (v19 & 0x80000000) == 0 )
      goto LABEL_52;
  }
  else
  {
    v19 = -2147467259;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x25F,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\MsixModules.h",
    (const char *)v19,
    (int)"Unable to GetProcAddress 'HrRemoveAppxLicense'",
    v27);
LABEL_47:
  v25 = (const char *)v30;
  if ( v31 >= 8 )
    v25 = v30[0];
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x766,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)v19,
    (int)"Failed while removing license for family moniker '%ws'",
    v25);
  if ( v31 >= 8 )
    operator delete(v30[0]);
  return v19;
}

```

## disassembly

```asm
0x18004e0e0  mov     r11, rsp
0x18004e0e3  mov     [r11+10h], rbx
0x18004e0e7  mov     [r11+18h], rsi
0x18004e0eb  push    rdi
0x18004e0ec  push    r14
0x18004e0ee  push    r15
0x18004e0f0  sub     rsp, 70h
0x18004e0f4  mov     rax, cs:__security_cookie
0x18004e0fb  xor     rax, rsp
0x18004e0fe  mov     [rsp+88h+var_28], rax
0x18004e103  mov     rsi, rcx
0x18004e106  mov     [rsp+88h+var_58], 0
0x18004e10e  mov     qword ptr [r11-30h], 7
0x18004e116  mov     qword ptr [r11-38h], 0
0x18004e11e  xor     eax, eax
0x18004e120  mov     word ptr [rsp+88h+var_48], ax
0x18004e125  lea     rbx, [rcx+30h]
0x18004e129  cmp     qword ptr [rbx+18h], 8
0x18004e12e  jb      short loc_18004E135
0x18004e130  mov     rdx, [rbx]
0x18004e133  jmp     short loc_18004E138
0x18004e135  mov     rdx, rbx
0x18004e138  lea     r8, [rsp+88h+var_48]
0x18004e13d  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x18004e142  mov     edi, eax
0x18004e144  test    eax, eax
0x18004e146  jns     short loc_18004E1A0
0x18004e148  cmp     qword ptr [rbx+18h], 8
0x18004e14d  jb      short loc_18004E152
0x18004e14f  mov     rbx, [rbx]
0x18004e152  mov     rcx, [rsp+88h]; this
0x18004e15a  mov     [rsp+88h+var_60], rbx; char *
0x18004e15f  lea     rax, aFailedToTransl; "Failed to translate package moniker to'"...
0x18004e166  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004e16b  mov     r9d, edi; char *
0x18004e16e  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e175  mov     edx, 73Fh; void *
0x18004e17a  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e17f  nop
0x18004e180  cmp     [rsp+88h+var_30], 8
0x18004e186  jb      short loc_18004E199
0x18004e188  mov     rcx, [rsp+88h+var_48]
0x18004e18d  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004e194  nop     dword ptr [rax+rax+00h]
0x18004e199  mov     eax, edi
0x18004e19b  jmp     loc_18004E483
0x18004e1a0  mov     rax, [rsi+10h]
0x18004e1a4  cmp     dword ptr [rax+258h], 0
0x18004e1ab  jz      short loc_18004E22B
0x18004e1ad  lea     rcx, [rax+140h]; this
0x18004e1b4  cmp     qword ptr [rbx+18h], 8
0x18004e1b9  jb      short loc_18004E1C0
0x18004e1bb  mov     rdx, [rbx]
0x18004e1be  jmp     short loc_18004E1C3
0x18004e1c0  mov     rdx, rbx; unsigned __int16 *
0x18004e1c3  lea     r8, [rsp+88h+var_58]; int *
0x18004e1c8  call    ?IsPackageInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::IsPackageInstalled(ushort const *,int *)
0x18004e1cd  mov     edi, eax
0x18004e1cf  test    eax, eax
0x18004e1d1  jns     short loc_18004E22B
0x18004e1d3  cmp     qword ptr [rbx+18h], 8
0x18004e1d8  jb      short loc_18004E1DD
0x18004e1da  mov     rbx, [rbx]
0x18004e1dd  mov     rcx, [rsp+88h]; this
0x18004e1e5  mov     [rsp+88h+var_60], rbx; char *
0x18004e1ea  lea     rax, aFailedToCheckI; "Failed to check install status of packa"...
0x18004e1f1  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004e1f6  mov     r9d, edi; char *
0x18004e1f9  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e200  mov     edx, 748h; void *
0x18004e205  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e20a  nop
0x18004e20b  cmp     [rsp+88h+var_30], 8
0x18004e211  jb      short loc_18004E224
0x18004e213  mov     rcx, [rsp+88h+var_48]
0x18004e218  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004e21f  nop     dword ptr [rax+rax+00h]
0x18004e224  mov     eax, edi
0x18004e226  jmp     loc_18004E483
0x18004e22b  cmp     [rsp+88h+var_58], 0
0x18004e230  jz      loc_18004E2EF
0x18004e236  mov     [rsp+88h+pv], 0
0x18004e23f  lea     r8, [rsp+88h+var_48]
0x18004e244  cmp     [rsp+88h+var_30], 8
0x18004e24a  cmovnb  r8, [rsp+88h+var_48]
0x18004e250  lea     rdx, aChoosingNotToR; "Choosing not to remove license for pack"...
0x18004e257  lea     rcx, [rsp+88h+pv]
0x18004e25c  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004e261  mov     rcx, [rsp+88h]; this
0x18004e269  test    eax, eax
0x18004e26b  jns     short loc_18004E281
0x18004e26d  mov     r9d, eax; char *
0x18004e270  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e277  mov     edx, 754h; void *
0x18004e27c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e281  mov     dword ptr [rsp+88h+var_60], 0
0x18004e289  mov     [rsp+88h+var_68], 2; int
0x18004e291  mov     edi, 75Ch
0x18004e296  mov     r9d, edi
0x18004e299  lea     r8, aMsixpackagePro_22; "MsixPackage::Provisioning::Library::Msi"...
0x18004e2a0  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e2a7  mov     rbx, [rsp+88h+pv]
0x18004e2ac  mov     rcx, rbx
0x18004e2af  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004e2b4  mov     rcx, [rsp+88h]; this
0x18004e2bc  test    eax, eax
0x18004e2be  jns     short loc_18004E2D2
0x18004e2c0  mov     r9d, eax; char *
0x18004e2c3  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e2ca  mov     edx, edi; void *
0x18004e2cc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e2d1  nop
0x18004e2d2  test    rbx, rbx
0x18004e2d5  jz      loc_18004E462
0x18004e2db  mov     rcx, rbx; pv
0x18004e2de  call    cs:__imp_CoTaskMemFree
0x18004e2e5  nop     dword ptr [rax+rax+00h]
0x18004e2ea  jmp     loc_18004E462
0x18004e2ef  mov     rax, [rsi+10h]
0x18004e2f3  lea     rdi, [rax+1C8h]
0x18004e2fa  mov     r14d, [rax+258h]
0x18004e301  mov     r15, [rax+238h]
0x18004e308  lea     rsi, [rsp+88h+var_48]
0x18004e30d  cmp     [rsp+88h+var_30], 8
0x18004e313  cmovnb  rsi, [rsp+88h+var_48]
0x18004e319  mov     rcx, rdi
0x18004e31c  call    ?LoadDynamic@?$MsixProvisioningModule@VCOemLicense@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::COemLicense>::LoadDynamic(void)
0x18004e321  mov     ebx, eax
0x18004e323  test    eax, eax
0x18004e325  jns     short loc_18004E331
0x18004e327  mov     edx, 257h
0x18004e32c  jmp     loc_18004E3EF
0x18004e331  mov     rax, [rdi+40h]
0x18004e335  test    rax, rax
0x18004e338  jnz     loc_18004E3D6
0x18004e33e  lea     rdx, aHrremoveappxli; "HrRemoveAppxLicense"
0x18004e345  mov     rcx, [rdi+8]; hModule
0x18004e349  call    cs:__imp_GetProcAddress
0x18004e350  nop     dword ptr [rax+rax+00h]
0x18004e355  mov     [rdi+40h], rax
0x18004e359  test    rax, rax
0x18004e35c  jnz     short loc_18004E3D6
0x18004e35e  call    cs:__imp_GetLastError
0x18004e365  nop     dword ptr [rax+rax+00h]
0x18004e36a  test    eax, eax
0x18004e36c  jle     short loc_18004E378
0x18004e36e  movzx   eax, ax
0x18004e371  or      eax, 80070000h
0x18004e376  test    eax, eax
0x18004e378  jns     short loc_18004E39F
0x18004e37a  call    cs:__imp_GetLastError
0x18004e381  nop     dword ptr [rax+rax+00h]
0x18004e386  mov     ebx, eax
0x18004e388  test    eax, eax
0x18004e38a  jle     short loc_18004E395
0x18004e38c  movzx   ebx, ax
0x18004e38f  or      ebx, 80070000h
0x18004e395  test    ebx, ebx
0x18004e397  jns     loc_18004E462
0x18004e39d  jmp     short loc_18004E3A4
0x18004e39f  mov     ebx, 80004005h
0x18004e3a4  mov     rcx, [rsp+88h]; this
0x18004e3ac  lea     rax, aUnableToGetpro_3; "Unable to GetProcAddress 'HrRemoveAppxL"...
0x18004e3b3  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004e3b8  mov     r9d, ebx; char *
0x18004e3bb  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e3c2  mov     edx, 25Fh; void *
0x18004e3c7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e3cc  test    ebx, ebx
0x18004e3ce  jns     loc_18004E462
0x18004e3d4  jmp     short loc_18004E406
0x18004e3d6  mov     r8d, r14d
0x18004e3d9  mov     rdx, r15
0x18004e3dc  mov     rcx, rsi
0x18004e3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e3e4  mov     ebx, eax
0x18004e3e6  test    eax, eax
0x18004e3e8  jns     short loc_18004E462
0x18004e3ea  mov     edx, 263h; void *
0x18004e3ef  mov     r9d, eax; char *
0x18004e3f2  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e3f9  mov     rcx, [rsp+88h]; this
0x18004e401  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e406  lea     rax, [rsp+88h+var_48]
0x18004e40b  cmp     [rsp+88h+var_30], 8
0x18004e411  cmovnb  rax, [rsp+88h+var_48]
0x18004e417  mov     rcx, [rsp+88h]; this
0x18004e41f  mov     [rsp+88h+var_60], rax; char *
0x18004e424  lea     rax, aFailedWhileRem; "Failed while removing license for famil"...
0x18004e42b  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004e430  mov     r9d, ebx; char *
0x18004e433  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e43a  mov     edx, 766h; void *
0x18004e43f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e444  nop
0x18004e445  cmp     [rsp+88h+var_30], 8
0x18004e44b  jb      short loc_18004E45E
0x18004e44d  mov     rcx, [rsp+88h+var_48]
0x18004e452  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004e459  nop     dword ptr [rax+rax+00h]
0x18004e45e  mov     eax, ebx
0x18004e460  jmp     short loc_18004E483
0x18004e462  cmp     [rsp+88h+var_30], 8
0x18004e468  jb      short loc_18004E47B
0x18004e46a  mov     rcx, [rsp+88h+var_48]
0x18004e46f  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004e476  nop     dword ptr [rax+rax+00h]
0x18004e47b  xor     eax, eax
0x18004e47d  jmp     short loc_18004E483
0x18004e47f  mov     eax, [rsp+88h+var_58]
0x18004e483  mov     rcx, [rsp+88h+var_28]
0x18004e488  xor     rcx, rsp; StackCookie
0x18004e48b  call    __security_check_cookie
0x18004e490  lea     r11, [rsp+88h+var_18]
0x18004e495  mov     rbx, [r11+28h]
0x18004e499  mov     rsi, [r11+30h]
0x18004e49d  mov     rsp, r11
0x18004e4a0  pop     r15
0x18004e4a2  pop     r14
0x18004e4a4  pop     rdi
0x18004e4a5  retn
```
