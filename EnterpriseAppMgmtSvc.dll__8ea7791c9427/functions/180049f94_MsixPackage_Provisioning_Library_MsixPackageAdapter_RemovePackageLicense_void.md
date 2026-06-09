# MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense(void)

- ea: `0x180049f94`
- end: `0x18004a32b`
- name: `?RemovePackageLicense@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJXZ`
- size: `919`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this)`
- caller_count: `1`
- callee_count: `11`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044a3c`

## callees

- `0x18000cfe8`
- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x18003de34`
- `0x180040400`
- `0x180047a30`
- `0x18004838c`
- `0x180049f94`
- `0x180066df0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18004a041`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a0c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a2e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a2f9`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a041`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a0c6`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a2e2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18004a2f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a1eb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18004a1eb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a186`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a186`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a210`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a1fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18004a210`

## string_xrefs

- `0x18004a24b`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004a282`: `onecore\admin\appmodel\utilities\provisionhelper\MsixModules.h`
- `0x18004a148`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a022`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a0a7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a118`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a16b`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a2c3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a098`: `Failed to check install status of package'%ws'`
- `0x18004a141`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageLicense`
- `0x18004a0f8`: `Choosing not to remove license for package '%s' because it is installed/staged by other users`
- `0x18004a1e0`: `HrRemoveAppxLicense`
- `0x18004a23c`: `Unable to GetProcAddress 'HrRemoveAppxLicense'`

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
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v10);
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
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v12);
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
0x180049f94  mov     r11, rsp
0x180049f97  mov     [r11+10h], rbx
0x180049f9b  mov     [r11+18h], rsi
0x180049f9f  push    rdi
0x180049fa0  push    r14
0x180049fa2  push    r15
0x180049fa4  sub     rsp, 70h
0x180049fa8  mov     rax, cs:__security_cookie
0x180049faf  xor     rax, rsp
0x180049fb2  mov     [rsp+88h+var_28], rax
0x180049fb7  mov     rsi, rcx
0x180049fba  mov     [rsp+88h+var_58], 0
0x180049fc2  mov     qword ptr [r11-30h], 7
0x180049fca  mov     qword ptr [r11-38h], 0
0x180049fd2  xor     eax, eax
0x180049fd4  mov     word ptr [rsp+88h+var_48], ax
0x180049fd9  lea     rbx, [rcx+30h]
0x180049fdd  cmp     qword ptr [rbx+18h], 8
0x180049fe2  jb      short loc_180049FE9
0x180049fe4  mov     rdx, [rbx]
0x180049fe7  jmp     short loc_180049FEC
0x180049fe9  mov     rdx, rbx
0x180049fec  lea     r8, [rsp+88h+var_48]
0x180049ff1  call    ?GetPackageFamilyFromFullName@MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAAJPEBGAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z; MsixPackage::Provisioning::Library::MsixProvisioningContext::GetPackageFamilyFromFullName(ushort const *,std::wstring &)
0x180049ff6  mov     edi, eax
0x180049ff8  test    eax, eax
0x180049ffa  jns     short loc_18004A04E
0x180049ffc  cmp     qword ptr [rbx+18h], 8
0x18004a001  jb      short loc_18004A006
0x18004a003  mov     rbx, [rbx]
0x18004a006  mov     rcx, [rsp+88h]; this
0x18004a00e  mov     [rsp+88h+var_60], rbx; char *
0x18004a013  lea     rax, aFailedToTransl; "Failed to translate package moniker to'"...
0x18004a01a  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004a01f  mov     r9d, edi; char *
0x18004a022  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a029  mov     edx, 73Fh; void *
0x18004a02e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a033  nop
0x18004a034  cmp     [rsp+88h+var_30], 8
0x18004a03a  jb      short loc_18004A047
0x18004a03c  mov     rcx, [rsp+88h+var_48]
0x18004a041  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004a047  mov     eax, edi
0x18004a049  jmp     loc_18004A307
0x18004a04e  mov     rax, [rsi+10h]
0x18004a052  cmp     dword ptr [rax+258h], 0
0x18004a059  jz      short loc_18004A0D3
0x18004a05b  lea     rcx, [rax+140h]; this
0x18004a062  cmp     qword ptr [rbx+18h], 8
0x18004a067  jb      short loc_18004A06E
0x18004a069  mov     rdx, [rbx]
0x18004a06c  jmp     short loc_18004A071
0x18004a06e  mov     rdx, rbx; unsigned __int16 *
0x18004a071  lea     r8, [rsp+88h+var_58]; int *
0x18004a076  call    ?IsPackageInstalled@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::IsPackageInstalled(ushort const *,int *)
0x18004a07b  mov     edi, eax
0x18004a07d  test    eax, eax
0x18004a07f  jns     short loc_18004A0D3
0x18004a081  cmp     qword ptr [rbx+18h], 8
0x18004a086  jb      short loc_18004A08B
0x18004a088  mov     rbx, [rbx]
0x18004a08b  mov     rcx, [rsp+88h]; this
0x18004a093  mov     [rsp+88h+var_60], rbx; char *
0x18004a098  lea     rax, aFailedToCheckI; "Failed to check install status of packa"...
0x18004a09f  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004a0a4  mov     r9d, edi; char *
0x18004a0a7  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a0ae  mov     edx, 748h; void *
0x18004a0b3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a0b8  nop
0x18004a0b9  cmp     [rsp+88h+var_30], 8
0x18004a0bf  jb      short loc_18004A0CC
0x18004a0c1  mov     rcx, [rsp+88h+var_48]
0x18004a0c6  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004a0cc  mov     eax, edi
0x18004a0ce  jmp     loc_18004A307
0x18004a0d3  cmp     [rsp+88h+var_58], 0
0x18004a0d8  jz      loc_18004A191
0x18004a0de  mov     [rsp+88h+pv], 0
0x18004a0e7  lea     r8, [rsp+88h+var_48]
0x18004a0ec  cmp     [rsp+88h+var_30], 8
0x18004a0f2  cmovnb  r8, [rsp+88h+var_48]
0x18004a0f8  lea     rdx, aChoosingNotToR; "Choosing not to remove license for pack"...
0x18004a0ff  lea     rcx, [rsp+88h+pv]
0x18004a104  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004a109  mov     rcx, [rsp+88h]; this
0x18004a111  test    eax, eax
0x18004a113  jns     short loc_18004A129
0x18004a115  mov     r9d, eax; char *
0x18004a118  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a11f  mov     edx, 754h; void *
0x18004a124  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a129  mov     dword ptr [rsp+88h+var_60], 0
0x18004a131  mov     [rsp+88h+var_68], 2; int
0x18004a139  mov     edi, 75Ch
0x18004a13e  mov     r9d, edi
0x18004a141  lea     r8, aMsixpackagePro_22; "MsixPackage::Provisioning::Library::Msi"...
0x18004a148  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a14f  mov     rbx, [rsp+88h+pv]
0x18004a154  mov     rcx, rbx
0x18004a157  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004a15c  mov     rcx, [rsp+88h]; this
0x18004a164  test    eax, eax
0x18004a166  jns     short loc_18004A17A
0x18004a168  mov     r9d, eax; char *
0x18004a16b  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a172  mov     edx, edi; void *
0x18004a174  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a179  nop
0x18004a17a  test    rbx, rbx
0x18004a17d  jz      loc_18004A2EC
0x18004a183  mov     rcx, rbx; pv
0x18004a186  call    cs:__imp_CoTaskMemFree
0x18004a18c  jmp     loc_18004A2EC
0x18004a191  mov     rax, [rsi+10h]
0x18004a195  lea     rdi, [rax+1C8h]
0x18004a19c  mov     r14d, [rax+258h]
0x18004a1a3  mov     r15, [rax+238h]
0x18004a1aa  lea     rsi, [rsp+88h+var_48]
0x18004a1af  cmp     [rsp+88h+var_30], 8
0x18004a1b5  cmovnb  rsi, [rsp+88h+var_48]
0x18004a1bb  mov     rcx, rdi
0x18004a1be  call    ?LoadDynamic@?$MsixProvisioningModule@VCOemLicense@Library@Provisioning@MsixPackage@@@Library@Provisioning@MsixPackage@@IEAAJXZ; MsixPackage::Provisioning::Library::MsixProvisioningModule<MsixPackage::Provisioning::Library::COemLicense>::LoadDynamic(void)
0x18004a1c3  mov     ebx, eax
0x18004a1c5  test    eax, eax
0x18004a1c7  jns     short loc_18004A1D3
0x18004a1c9  mov     edx, 257h
0x18004a1ce  jmp     loc_18004A27F
0x18004a1d3  mov     rax, [rdi+40h]
0x18004a1d7  test    rax, rax
0x18004a1da  jnz     loc_18004A266
0x18004a1e0  lea     rdx, aHrremoveappxli; "HrRemoveAppxLicense"
0x18004a1e7  mov     rcx, [rdi+8]; hModule
0x18004a1eb  call    cs:__imp_GetProcAddress
0x18004a1f1  mov     [rdi+40h], rax
0x18004a1f5  test    rax, rax
0x18004a1f8  jnz     short loc_18004A266
0x18004a1fa  call    cs:__imp_GetLastError
0x18004a200  test    eax, eax
0x18004a202  jle     short loc_18004A20E
0x18004a204  movzx   eax, ax
0x18004a207  or      eax, 80070000h
0x18004a20c  test    eax, eax
0x18004a20e  jns     short loc_18004A22F
0x18004a210  call    cs:__imp_GetLastError
0x18004a216  mov     ebx, eax
0x18004a218  test    eax, eax
0x18004a21a  jle     short loc_18004A225
0x18004a21c  movzx   ebx, ax
0x18004a21f  or      ebx, 80070000h
0x18004a225  test    ebx, ebx
0x18004a227  jns     loc_18004A2EC
0x18004a22d  jmp     short loc_18004A234
0x18004a22f  mov     ebx, 80004005h
0x18004a234  mov     rcx, [rsp+88h]; this
0x18004a23c  lea     rax, aUnableToGetpro_3; "Unable to GetProcAddress 'HrRemoveAppxL"...
0x18004a243  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004a248  mov     r9d, ebx; char *
0x18004a24b  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a252  mov     edx, 25Fh; void *
0x18004a257  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a25c  test    ebx, ebx
0x18004a25e  jns     loc_18004A2EC
0x18004a264  jmp     short loc_18004A296
0x18004a266  mov     r8d, r14d
0x18004a269  mov     rdx, r15
0x18004a26c  mov     rcx, rsi
0x18004a26f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a274  mov     ebx, eax
0x18004a276  test    eax, eax
0x18004a278  jns     short loc_18004A2EC
0x18004a27a  mov     edx, 263h; void *
0x18004a27f  mov     r9d, eax; char *
0x18004a282  lea     r8, aOnecoreAdminAp_2; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a289  mov     rcx, [rsp+88h]; this
0x18004a291  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004a296  lea     rax, [rsp+88h+var_48]
0x18004a29b  cmp     [rsp+88h+var_30], 8
0x18004a2a1  cmovnb  rax, [rsp+88h+var_48]
0x18004a2a7  mov     rcx, [rsp+88h]; this
0x18004a2af  mov     [rsp+88h+var_60], rax; char *
0x18004a2b4  lea     rax, aFailedWhileRem; "Failed while removing license for famil"...
0x18004a2bb  mov     qword ptr [rsp+88h+var_68], rax; int
0x18004a2c0  mov     r9d, ebx; char *
0x18004a2c3  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a2ca  mov     edx, 766h; void *
0x18004a2cf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a2d4  nop
0x18004a2d5  cmp     [rsp+88h+var_30], 8
0x18004a2db  jb      short loc_18004A2E8
0x18004a2dd  mov     rcx, [rsp+88h+var_48]
0x18004a2e2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004a2e8  mov     eax, ebx
0x18004a2ea  jmp     short loc_18004A307
0x18004a2ec  cmp     [rsp+88h+var_30], 8
0x18004a2f2  jb      short loc_18004A2FF
0x18004a2f4  mov     rcx, [rsp+88h+var_48]
0x18004a2f9  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18004a2ff  xor     eax, eax
0x18004a301  jmp     short loc_18004A307
0x18004a303  mov     eax, [rsp+88h+var_58]
0x18004a307  mov     rcx, [rsp+88h+var_28]
0x18004a30c  xor     rcx, rsp; StackCookie
0x18004a30f  call    __security_check_cookie
0x18004a314  lea     r11, [rsp+88h+var_18]
0x18004a319  mov     rbx, [r11+28h]
0x18004a31d  mov     rsi, [r11+30h]
0x18004a321  mov     rsp, r11
0x18004a324  pop     r15
0x18004a326  pop     r14
0x18004a328  pop     rdi
0x18004a329  retn
```
