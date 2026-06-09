# MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline(int,int,int *)

- ea: `0x18004e4b0`
- end: `0x18004e7ec`
- name: `?RemovePackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJHHPEAH@Z`
- size: `828`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, int, int, int *)`
- caller_count: `3`
- callee_count: `9`
- tags: `file_ops, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18003c81c`
- `0x18004e7f4`
- `0x180051ae0`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4ec`
- `0x180043fb4`
- `0x18004560c`
- `0x180045850`
- `0x180048bd8`
- `0x18004e4b0`
- `0x18006c910`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e587`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004e587`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e663`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18004e663`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e67e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateStringReference` at `0x18004e67e`

## string_xrefs

- `0x18004e4df`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e6e1`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e763`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e7bf`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e7db`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e549`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackageOnline`
- `0x18004e550`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e5bb`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e6bf`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e741`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004e748`: `Failed to remove package for all users.`
- `0x18004e7d4`: `Failed to remove package for all users.`

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
  int v22; // [rsp+20h] [rbp-78h]
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v8,
        v22);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v10,
        2);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v12,
        1);
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
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v21,
          1);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v19,
        1);
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
0x18004e4b0  mov     [rsp+arg_8], rbx
0x18004e4b5  push    rbp
0x18004e4b6  push    rsi
0x18004e4b7  push    rdi
0x18004e4b8  push    r12
0x18004e4ba  push    r13
0x18004e4bc  push    r14
0x18004e4be  push    r15
0x18004e4c0  sub     rsp, 60h
0x18004e4c4  mov     rax, cs:__security_cookie
0x18004e4cb  xor     rax, rsp
0x18004e4ce  mov     [rsp+98h+var_40], rax
0x18004e4d3  mov     r13, r9
0x18004e4d6  mov     r12d, r8d
0x18004e4d9  mov     r14d, edx
0x18004e4dc  mov     rsi, rcx
0x18004e4df  lea     rbp, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e4e6  xor     edi, edi
0x18004e4e8  cmp     [rcx+10Ch], edi
0x18004e4ee  jz      loc_18004E593
0x18004e4f4  mov     [rsp+98h+pv], rdi
0x18004e4f9  lea     r8, [rcx+30h]
0x18004e4fd  cmp     qword ptr [r8+18h], 8
0x18004e502  jb      short loc_18004E507
0x18004e504  mov     r8, [r8]
0x18004e507  lea     rdx, aAllowingOnline; "Allowing online deprovision of framewor"...
0x18004e50e  lea     rcx, [rsp+98h+pv]
0x18004e513  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004e518  mov     rcx, [rsp+98h]; this
0x18004e520  test    eax, eax
0x18004e522  jns     short loc_18004E534
0x18004e524  mov     r9d, eax; char *
0x18004e527  mov     r8, rbp; unsigned int
0x18004e52a  mov     edx, 3Ah ; ':'; void *
0x18004e52f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e534  mov     dword ptr [rsp+98h+var_70], edi
0x18004e538  mov     [rsp+98h+var_78], 2; int
0x18004e540  mov     r15d, 42h ; 'B'
0x18004e546  mov     r9d, r15d
0x18004e549  lea     r8, aMsixpackagePro_16; "MsixPackage::Provisioning::Library::Msi"...
0x18004e550  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e557  mov     rbx, [rsp+98h+pv]
0x18004e55c  mov     rcx, rbx
0x18004e55f  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004e564  mov     rcx, [rsp+98h]; this
0x18004e56c  test    eax, eax
0x18004e56e  jns     short loc_18004E57F
0x18004e570  mov     r9d, eax; char *
0x18004e573  mov     r8, rbp; unsigned int
0x18004e576  mov     edx, r15d; void *
0x18004e579  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e57e  nop
0x18004e57f  test    rbx, rbx
0x18004e582  jz      short loc_18004E593
0x18004e584  mov     rcx, rbx; pv
0x18004e587  call    cs:__imp_CoTaskMemFree
0x18004e58e  nop     dword ptr [rax+rax+00h]
0x18004e593  mov     rcx, rsi; this
0x18004e596  call    ?DeregisterPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DeregisterPackageOnline(int)
0x18004e59b  mov     ebx, eax
0x18004e59d  test    eax, eax
0x18004e59f  jns     short loc_18004E5EA
0x18004e5a1  test    r14d, r14d
0x18004e5a4  jz      short loc_18004E5FE
0x18004e5a6  mov     dword ptr [rsp+98h+var_70], eax
0x18004e5aa  mov     [rsp+98h+var_78], 1; int
0x18004e5b2  mov     r9d, 4Ah ; 'J'
0x18004e5b8  xor     r8d, r8d
0x18004e5bb  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e5c2  lea     rcx, aFailedToDeregi_0; "Failed to deregister packages."
0x18004e5c9  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004e5ce  test    eax, eax
0x18004e5d0  jns     short loc_18004E5EA
0x18004e5d2  mov     rcx, [rsp+98h]; this
0x18004e5da  mov     r9d, eax; char *
0x18004e5dd  mov     r8, rbp; unsigned int
0x18004e5e0  mov     edx, 4Ah ; 'J'; void *
0x18004e5e5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e5ea  mov     r15, [rsi+10h]
0x18004e5ee  lea     rbx, [rsi+30h]
0x18004e5f2  cmp     qword ptr [rbx+18h], 8
0x18004e5f7  jb      short loc_18004E635
0x18004e5f9  mov     rbp, [rbx]
0x18004e5fc  jmp     short loc_18004E638
0x18004e5fe  lea     rax, aFailedToDeregi_0; "Failed to deregister packages."
0x18004e605  mov     r8, rbp; unsigned int
0x18004e608  mov     edx, 4Ah ; 'J'; void *
0x18004e60d  mov     [rsp+98h+var_70], rax; char *
0x18004e612  lea     rax, aWs; "%ws"
0x18004e619  mov     r9d, ebx; char *
0x18004e61c  mov     qword ptr [rsp+98h+var_78], rax; int
0x18004e621  mov     rcx, [rsp+98h]; this
0x18004e629  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e62e  mov     eax, ebx
0x18004e630  jmp     loc_18004E776
0x18004e635  mov     rbp, rbx
0x18004e638  or      rdi, 0FFFFFFFFFFFFFFFFh
0x18004e63c  xor     eax, eax
0x18004e63e  inc     rdi
0x18004e641  cmp     [rbp+rdi*2+0], ax
0x18004e646  jnz     short loc_18004E63E
0x18004e648  mov     eax, 0FFFFFFFFh
0x18004e64d  cmp     rdi, rax
0x18004e650  jbe     short loc_18004E66F
0x18004e652  mov     edi, eax
0x18004e654  xor     r9d, r9d; lpArguments
0x18004e657  xor     r8d, r8d; nNumberOfArguments
0x18004e65a  lea     edx, [r9+1]; dwExceptionFlags
0x18004e65e  mov     ecx, 0C000000Dh; dwExceptionCode
0x18004e663  call    cs:__imp_RaiseException
0x18004e66a  nop     dword ptr [rax+rax+00h]
0x18004e66f  lea     r9, [rsp+98h+string]; string
0x18004e674  lea     r8, [rsp+98h+hstringHeader]; hstringHeader
0x18004e679  mov     edx, edi; length
0x18004e67b  mov     rcx, rbp; sourceString
0x18004e67e  call    cs:__imp_WindowsCreateStringReference
0x18004e685  nop     dword ptr [rax+rax+00h]
0x18004e68a  mov     rdx, [rsp+98h+string]; HSTRING
0x18004e68f  lea     rcx, [r15+140h]; this
0x18004e696  call    ?AppxDestagePackage@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEAUHSTRING__@@@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxDestagePackage(HSTRING__ *)
0x18004e69b  mov     edi, eax
0x18004e69d  xor     ebp, ebp
0x18004e69f  test    eax, eax
0x18004e6a1  jns     short loc_18004E6F0
0x18004e6a3  test    r14d, r14d
0x18004e6a6  jz      loc_18004E79C
0x18004e6ac  mov     dword ptr [rsp+98h+var_70], eax
0x18004e6b0  mov     [rsp+98h+var_78], 1; int
0x18004e6b8  lea     r9d, [rbp+4Fh]
0x18004e6bc  xor     r8d, r8d
0x18004e6bf  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e6c6  lea     rcx, aFailedToDestag_0; "Failed to destage packages."
0x18004e6cd  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004e6d2  test    eax, eax
0x18004e6d4  jns     short loc_18004E6F0
0x18004e6d6  mov     rcx, [rsp+98h]; this
0x18004e6de  mov     r9d, eax; char *
0x18004e6e1  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e6e8  lea     edx, [rbp+4Fh]; void *
0x18004e6eb  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e6f0  test    r12d, r12d
0x18004e6f3  jz      short loc_18004E774
0x18004e6f5  mov     rcx, [rsi+10h]
0x18004e6f9  add     rcx, 140h; this
0x18004e700  cmp     qword ptr [rbx+18h], 8
0x18004e705  jb      short loc_18004E70A
0x18004e707  mov     rbx, [rbx]
0x18004e70a  mov     r8, r13; int *
0x18004e70d  mov     rdx, rbx; unsigned __int16 *
0x18004e710  call    ?AppxRemovePackageForAllUsers@MsixAppxDeploymentClient@Library@Provisioning@MsixPackage@@QEAAJPEBGPEAH@Z; MsixPackage::Provisioning::Library::MsixAppxDeploymentClient::AppxRemovePackageForAllUsers(ushort const *,int *)
0x18004e715  mov     ebx, ebp
0x18004e717  cmp     eax, 80073CF1h
0x18004e71c  cmovnz  ebx, eax
0x18004e71f  test    ebx, ebx
0x18004e721  jns     short loc_18004E774
0x18004e723  test    r14d, r14d
0x18004e726  jz      loc_18004E7D4
0x18004e72c  mov     dword ptr [rsp+98h+var_70], ebx
0x18004e730  mov     [rsp+98h+var_78], 1; int
0x18004e738  mov     r9d, 62h ; 'b'
0x18004e73e  xor     r8d, r8d
0x18004e741  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e748  lea     rcx, aFailedToRemove_7; "Failed to remove package for all users."
0x18004e74f  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004e754  test    eax, eax
0x18004e756  jns     short loc_18004E774
0x18004e758  mov     rcx, [rsp+98h]; this
0x18004e760  mov     r9d, eax; char *
0x18004e763  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e76a  mov     edx, 62h ; 'b'; void *
0x18004e76f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004e774  xor     eax, eax
0x18004e776  mov     rcx, [rsp+98h+var_40]
0x18004e77b  xor     rcx, rsp; StackCookie
0x18004e77e  call    __security_check_cookie
0x18004e783  mov     rbx, [rsp+98h+arg_8]
0x18004e78b  add     rsp, 60h
0x18004e78f  pop     r15
0x18004e791  pop     r14
0x18004e793  pop     r13
0x18004e795  pop     r12
0x18004e797  pop     rdi
0x18004e798  pop     rsi
0x18004e799  pop     rbp
0x18004e79a  retn
0x18004e79c  mov     rcx, [rsp+98h]; this
0x18004e7a4  lea     rax, aFailedToDestag_0; "Failed to destage packages."
0x18004e7ab  mov     [rsp+98h+var_70], rax; char *
0x18004e7b0  lea     rax, aWs; "%ws"
0x18004e7b7  mov     qword ptr [rsp+98h+var_78], rax; int
0x18004e7bc  mov     r9d, edi; char *
0x18004e7bf  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e7c6  mov     edx, 4Fh ; 'O'; void *
0x18004e7cb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e7d0  mov     eax, edi
0x18004e7d2  jmp     short loc_18004E776
0x18004e7d4  lea     rax, aFailedToRemove_7; "Failed to remove package for all users."
0x18004e7db  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e7e2  mov     edx, 62h ; 'b'
0x18004e7e7  jmp     loc_18004E60D
```
