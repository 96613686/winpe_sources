# MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(int,int,int *)

- ea: `0x18004a334`
- end: `0x18004a65d`
- name: `?RemovePackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHHPEAH@Z`
- size: `809`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int, int, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003925c`
- `0x18004a664`
- `0x18004d82c`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e9c`
- `0x180040400`
- `0x180041940`
- `0x180041b58`
- `0x180044cd8`
- `0x18004a334`
- `0x180066df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a40b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a40b`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a4e1`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004a4e1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a4f6`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004a4f6`

## string_xrefs

- `0x18004a3d4`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a439`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a531`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a5b3`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a363`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a553`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a5d5`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a630`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a64c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a5ba`: `Failed to remove package for all users.`
- `0x18004a645`: `Failed to remove package for all users.`
- `0x18004a3cd`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        int a2,
        int a3,
        int *a4)
{
  int v8; // eax
  void *v9; // rbx
  int v10; // eax
  int v11; // ebx
  int v12; // eax
  __int64 v13; // r15
  const unsigned __int16 *v14; // rbx
  const WCHAR *v15; // rbp
  unsigned __int64 v17; // rdi
  int v18; // edi
  int v19; // eax
  int v20; // eax
  int v21; // eax
  LPVOID pv; // [rsp+30h] [rbp-68h] BYREF
  HSTRING string; // [rsp+38h] [rbp-60h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+40h] [rbp-58h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]

  if ( *((_DWORD *)this + 67) )
  {
    pv = 0;
    v8 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           (char *)&pv,
           L"Allowing online deprovision of framework %s that was provisioned by itself");
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x3A,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v8);
    v9 = pv;
    v10 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            pv,
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            L"MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline",
            66);
    if ( v10 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v10);
    if ( v9 )
      CoTaskMemFree(v9);
  }
  v11 = MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterPackageOnline(this);
  if ( v11 < 0 )
  {
    if ( !a2 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x4A,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v11,
        (int)"%ws",
        L"Failed to deregister packages.");
      return (unsigned int)v11;
    }
    v12 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            L"Failed to deregister packages.",
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            74);
    if ( v12 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4A,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v12);
  }
  v13 = *((_QWORD *)this + 2);
  v14 = (const unsigned __int16 *)((char *)this + 48);
  if ( *((_QWORD *)this + 9) < 8u )
    v15 = (const WCHAR *)((char *)this + 48);
  else
    v15 = *(const WCHAR **)v14;
  v17 = -1;
  do
    ++v17;
  while ( v15[v17] );
  if ( v17 > 0xFFFFFFFF )
  {
    LODWORD(v17) = -1;
    RaiseException(0xC000000D, 1u, 0, 0);
  }
  WindowsCreateStringReference(v15, v17, &hstringHeader, &string);
  v18 = MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxDestagePackage(
          (MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *)(v13 + 320),
          string);
  if ( v18 >= 0 )
  {
LABEL_25:
    if ( !a3 )
      return 0;
    if ( *((_QWORD *)this + 9) >= 8u )
      v14 = *(const unsigned __int16 **)v14;
    v20 = MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxRemovePackageForAllUsers(
            (MsixPackage::Provisioning::Library::MsixAppxDeploymentClient *)(*((_QWORD *)this + 2) + 320LL),
            v14,
            a4);
    v11 = 0;
    if ( v20 != -2147009295 )
      v11 = v20;
    if ( v11 >= 0 )
      return 0;
    if ( a2 )
    {
      v21 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              L"Failed to remove package for all users.",
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
              0,
              98);
      if ( v21 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x62,
          (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v21);
      return 0;
    }
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x62,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v11,
      (int)"%ws",
      (const char *)L"Failed to remove package for all users.");
    return (unsigned int)v11;
  }
  if ( a2 )
  {
    v19 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
            L"Failed to destage packages.",
            L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            0,
            79);
    if ( v19 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x4F,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v19);
    goto LABEL_25;
  }
  wil::details::in1diag3::Return_HrMsg(
    retaddr,
    (void *)0x4F,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v18,
    (int)"%ws",
    L"Failed to destage packages.");
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18004a334  mov     [rsp+arg_8], rbx
0x18004a339  push    rbp
0x18004a33a  push    rsi
0x18004a33b  push    rdi
0x18004a33c  push    r12
0x18004a33e  push    r13
0x18004a340  push    r14
0x18004a342  push    r15
0x18004a344  sub     rsp, 60h
0x18004a348  mov     rax, cs:__security_cookie
0x18004a34f  xor     rax, rsp
0x18004a352  mov     [rsp+98h+var_40], rax
0x18004a357  mov     r13, r9
0x18004a35a  mov     r12d, r8d
0x18004a35d  mov     r14d, edx
0x18004a360  mov     rsi, rcx
0x18004a363  lea     rbp, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a36a  xor     edi, edi
0x18004a36c  cmp     [rcx+10Ch], edi
0x18004a372  jz      loc_18004A411
0x18004a378  mov     [rsp+98h+pv], rdi
0x18004a37d  lea     r8, [rcx+30h]
0x18004a381  cmp     qword ptr [r8+18h], 8
0x18004a386  jb      short loc_18004A38B
0x18004a388  mov     r8, [r8]
0x18004a38b  lea     rdx, aAllowingOnline; "Allowing online deprovision of framewor"...
0x18004a392  lea     rcx, [rsp+98h+pv]
0x18004a397  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004a39c  mov     rcx, [rsp+98h]; this
0x18004a3a4  test    eax, eax
0x18004a3a6  jns     short loc_18004A3B8
0x18004a3a8  mov     r9d, eax; char *
0x18004a3ab  mov     r8, rbp; unsigned int
0x18004a3ae  mov     edx, 3Ah ; ':'; void *
0x18004a3b3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a3b8  mov     dword ptr [rsp+98h+var_70], edi
0x18004a3bc  mov     [rsp+98h+var_78], 2; int
0x18004a3c4  mov     r15d, 42h ; 'B'
0x18004a3ca  mov     r9d, r15d
0x18004a3cd  lea     r8, aMsixpackagePro_16; "MsixPackage::Provisioning::Library::Msi"...
0x18004a3d4  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a3db  mov     rbx, [rsp+98h+pv]
0x18004a3e0  mov     rcx, rbx
0x18004a3e3  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004a3e8  mov     rcx, [rsp+98h]; this
0x18004a3f0  test    eax, eax
0x18004a3f2  jns     short loc_18004A403
0x18004a3f4  mov     r9d, eax; char *
0x18004a3f7  mov     r8, rbp; unsigned int
0x18004a3fa  mov     edx, r15d; void *
0x18004a3fd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a402  nop
0x18004a403  test    rbx, rbx
0x18004a406  jz      short loc_18004A411
0x18004a408  mov     rcx, rbx; pv
0x18004a40b  call    cs:__imp_CoTaskMemFree
0x18004a411  mov     rcx, rsi; this
0x18004a414  call    ?DeregisterPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterPackageOnline(int)
0x18004a419  mov     ebx, eax
0x18004a41b  test    eax, eax
0x18004a41d  jns     short loc_18004A468
0x18004a41f  test    r14d, r14d
0x18004a422  jz      short loc_18004A47C
0x18004a424  mov     dword ptr [rsp+98h+var_70], eax
0x18004a428  mov     [rsp+98h+var_78], 1; int
0x18004a430  mov     r9d, 4Ah ; 'J'
0x18004a436  xor     r8d, r8d
0x18004a439  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a440  lea     rcx, aFailedToDeregi_0; "Failed to deregister packages."
0x18004a447  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004a44c  test    eax, eax
0x18004a44e  jns     short loc_18004A468
0x18004a450  mov     rcx, [rsp+98h]; this
0x18004a458  mov     r9d, eax; char *
0x18004a45b  mov     r8, rbp; unsigned int
0x18004a45e  mov     edx, 4Ah ; 'J'; void *
0x18004a463  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a468  mov     r15, [rsi+10h]
0x18004a46c  lea     rbx, [rsi+30h]
0x18004a470  cmp     qword ptr [rbx+18h], 8
0x18004a475  jb      short loc_18004A4B3
0x18004a477  mov     rbp, [rbx]
0x18004a47a  jmp     short loc_18004A4B6
0x18004a47c  lea     rax, aFailedToDeregi_0; "Failed to deregister packages."
0x18004a483  mov     r8, rbp; unsigned int
0x18004a486  mov     edx, 4Ah ; 'J'; void *
0x18004a48b  mov     [rsp+98h+var_70], rax; char *
0x18004a490  lea     rax, aWs; "%ws"
0x18004a497  mov     r9d, ebx; char *
0x18004a49a  mov     qword ptr [rsp+98h+var_78], rax; int
0x18004a49f  mov     rcx, [rsp+98h]; this
0x18004a4a7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a4ac  mov     eax, ebx
0x18004a4ae  jmp     loc_18004A5E8
0x18004a4b3  mov     rbp, rbx
0x18004a4b6  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004a4ba  xor     eax, eax
0x18004a4bc  inc     rdi
0x18004a4bf  cmp     [rbp+rdi*2+0], ax
0x18004a4c4  jnz     short loc_18004A4BC
0x18004a4c6  mov     eax, 0FFFFFFFFh
0x18004a4cb  cmp     rdi, rax
0x18004a4ce  jbe     short loc_18004A4E7
0x18004a4d0  mov     edi, eax
0x18004a4d2  xor     r9d, r9d; lpArguments
0x18004a4d5  xor     r8d, r8d; nNumberOfArguments
0x18004a4d8  lea     edx, [r9+1]; dwExceptionFlags
0x18004a4dc  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004a4e1  call    cs:__imp_RaiseException
0x18004a4e7  lea     r9, [rsp+98h+string]; string
0x18004a4ec  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18004a4f1  mov     edx, edi; length
0x18004a4f3  mov     rcx, rbp; sourceString
0x18004a4f6  call    cs:__imp_WindowsCreateStringReference
0x18004a4fc  mov     rdx, [rsp+98h+string]; HSTRING
0x18004a501  lea     rcx, [r15+140h]; this
0x18004a508  call    ?AppxDestagePackage@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEAUHSTRING__@@@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxDestagePackage(HSTRING__ *)
0x18004a50d  mov     edi, eax
0x18004a50f  xor     ebp, ebp
0x18004a511  test    eax, eax
0x18004a513  jns     short loc_18004A562
0x18004a515  test    r14d, r14d
0x18004a518  jz      loc_18004A60D
0x18004a51e  mov     dword ptr [rsp+98h+var_70], eax
0x18004a522  mov     [rsp+98h+var_78], 1; int
0x18004a52a  lea     r9d, [rbp+4Fh]
0x18004a52e  xor     r8d, r8d
0x18004a531  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a538  lea     rcx, aFailedToDestag_0; "Failed to destage packages."
0x18004a53f  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004a544  test    eax, eax
0x18004a546  jns     short loc_18004A562
0x18004a548  mov     rcx, [rsp+98h]; this
0x18004a550  mov     r9d, eax; char *
0x18004a553  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a55a  lea     edx, [rbp+4Fh]; void *
0x18004a55d  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a562  test    r12d, r12d
0x18004a565  jz      short loc_18004A5E6
0x18004a567  mov     rcx, [rsi+10h]
0x18004a56b  add     rcx, 140h; this
0x18004a572  cmp     qword ptr [rbx+18h], 8
0x18004a577  jb      short loc_18004A57C
0x18004a579  mov     rbx, [rbx]
0x18004a57c  mov     r8, r13; int *
0x18004a57f  mov     rdx, rbx; unsigned __int16 *
0x18004a582  call    ?AppxRemovePackageForAllUsers@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxRemovePackageForAllUsers(ushort const *,int *)
0x18004a587  mov     ebx, ebp
0x18004a589  cmp     eax, 80073CF1h
0x18004a58e  cmovnz  ebx, eax
0x18004a591  test    ebx, ebx
0x18004a593  jns     short loc_18004A5E6
0x18004a595  test    r14d, r14d
0x18004a598  jz      loc_18004A645
0x18004a59e  mov     dword ptr [rsp+98h+var_70], ebx
0x18004a5a2  mov     [rsp+98h+var_78], 1; int
0x18004a5aa  mov     r9d, 62h ; 'b'
0x18004a5b0  xor     r8d, r8d
0x18004a5b3  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a5ba  lea     rcx, aFailedToRemove_7; "Failed to remove package for all users."
0x18004a5c1  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004a5c6  test    eax, eax
0x18004a5c8  jns     short loc_18004A5E6
0x18004a5ca  mov     rcx, [rsp+98h]; this
0x18004a5d2  mov     r9d, eax; char *
0x18004a5d5  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a5dc  mov     edx, 62h ; 'b'; void *
0x18004a5e1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004a5e6  xor     eax, eax
0x18004a5e8  mov     rcx, [rsp+98h+var_40]
0x18004a5ed  xor     rcx, rsp; StackCookie
0x18004a5f0  call    __security_check_cookie
0x18004a5f5  mov     rbx, [rsp+98h+arg_8]
0x18004a5fd  add     rsp, 60h
0x18004a601  pop     r15
0x18004a603  pop     r14
0x18004a605  pop     r13
0x18004a607  pop     r12
0x18004a609  pop     rdi
0x18004a60a  pop     rsi
0x18004a60b  pop     rbp
0x18004a60c  retn
0x18004a60d  mov     rcx, [rsp+98h]; this
0x18004a615  lea     rax, aFailedToDestag_0; "Failed to destage packages."
0x18004a61c  mov     [rsp+98h+var_70], rax; char *
0x18004a621  lea     rax, aWs; "%ws"
0x18004a628  mov     qword ptr [rsp+98h+var_78], rax; int
0x18004a62d  mov     r9d, edi; char *
0x18004a630  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a637  mov     edx, 4Fh ; 'O'; void *
0x18004a63c  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a641  mov     eax, edi
0x18004a643  jmp     short loc_18004A5E8
0x18004a645  lea     rax, aFailedToRemove_7; "Failed to remove package for all users."
0x18004a64c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a653  mov     edx, 62h ; 'b'
0x18004a658  jmp     loc_18004A48B
```
