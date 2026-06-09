# MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath(ushort const *)

- ea: `0x1800450bc`
- end: `0x1800452e1`
- name: `?DestagePath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@CAJPEBG@Z`
- size: `549`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180044ecc`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x180039e60`
- `0x180039e9c`
- `0x180040400`
- `0x180041390`
- `0x1800450bc`
- `0x18005ed60`
- `0x1800612f0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800451c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004521d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800452ba`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800451c9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004521d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800452ba`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18004518b`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x18004518b`

## string_xrefs

- `0x180045156`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045289`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004511e`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045253`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800451ff`: `Failed deleting path '%ws'`
- `0x18004514f`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath`
- `0x180045282`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath`
- `0x18004510a`: ` An attempt to obtain ownership on the root folder %ws and its children`
- `0x18004523f`: `The folder %s does not exist, must have already been de - staged`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath(const unsigned __int16 *a1)
{
  int v1; // eax
  int v2; // eax
  void *v3; // rbx
  int v4; // eax
  int v5; // esi
  unsigned int LastErrorMsg; // edi
  int v8; // eax
  int v9; // eax
  int v10; // [rsp+28h] [rbp-28h]
  __int64 *v11; // [rsp+30h] [rbp-20h] BYREF
  LPCWSTR *p_lpFileName; // [rsp+38h] [rbp-18h]
  __int64 v13; // [rsp+40h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  LPCWSTR lpFileName; // [rsp+70h] [rbp+20h] BYREF
  LPVOID pv; // [rsp+78h] [rbp+28h] BYREF
  __int64 v17; // [rsp+80h] [rbp+30h] BYREF

  lpFileName = a1;
  v17 = 0;
  v11 = &v17;
  p_lpFileName = &lpFileName;
  LOBYTE(v13) = 1;
  v1 = DirectoryExists(a1);
  pv = 0;
  if ( v1 )
  {
    v2 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           (char *)&pv,
           L" An attempt to obtain ownership on the root folder %ws and its children",
           lpFileName);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x427,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v2);
    v10 = 0;
    v3 = pv;
    v4 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
           pv,
           L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
           L"MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath",
           1071);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x42F,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v4);
    v5 = TakeOwnershipOnFolder(lpFileName, 1, &v17);
    if ( v5 < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x436,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v5,
        (int)"Failed while trying to take ownership of package root '%ws'",
        (const char *)lpFileName,
        v11,
        p_lpFileName,
        v13);
      if ( v3 )
        CoTaskMemFree(v3);
      LOBYTE(v13) = 0;
      lambda_55d86e0c6a6c6761a9b9a2e277d6803f_::operator()(&v11);
      return (unsigned int)v5;
    }
    if ( !(unsigned int)DeletePathEx(lpFileName) )
    {
      LastErrorMsg = wil::details::in1diag3::Return_GetLastErrorMsg(
                       retaddr,
                       (void *)0x439,
                       (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                       "Failed deleting path '%ws'",
                       (const char *)lpFileName,
                       v10,
                       v11,
                       p_lpFileName,
                       v13);
      if ( v3 )
        CoTaskMemFree(v3);
      LOBYTE(v13) = 0;
      lambda_55d86e0c6a6c6761a9b9a2e277d6803f_::operator()(&v11);
      return LastErrorMsg;
    }
  }
  else
  {
    v8 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           (char *)&pv,
           L"The folder %s does not exist, must have already been de - staged",
           lpFileName);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x442,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v8);
    v3 = pv;
    v9 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
           pv,
           L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
           L"MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath",
           1098);
    if ( v9 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x44A,
        (int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v9);
  }
  if ( v3 )
    CoTaskMemFree(v3);
  LOBYTE(v13) = 0;
  lambda_55d86e0c6a6c6761a9b9a2e277d6803f_::operator()(&v11);
  return 0;
}

```

## disassembly

```asm
0x1800450bc  mov     [rsp-18h+arg_18], rbx
0x1800450c1  mov     [rsp-18h+lpFileName], rcx
0x1800450c6  push    rbp
0x1800450c7  push    rsi
0x1800450c8  push    rdi
0x1800450c9  mov     rbp, rsp
0x1800450cc  sub     rsp, 50h
0x1800450d0  mov     [rbp+arg_10], 0
0x1800450d8  lea     rax, [rbp+arg_10]
0x1800450dc  mov     [rbp+var_20], rax
0x1800450e0  lea     rax, [rbp+lpFileName]
0x1800450e4  mov     [rbp+var_18], rax
0x1800450e8  mov     esi, 1
0x1800450ed  mov     byte ptr [rbp+var_10], sil
0x1800450f1  call    DirectoryExists
0x1800450f6  mov     [rbp+pv], 0
0x1800450fe  test    eax, eax
0x180045100  jz      loc_18004523B
0x180045106  mov     r8, [rbp+lpFileName]
0x18004510a  lea     rdx, aAnAttemptToObt_1; " An attempt to obtain ownership on the "...
0x180045111  lea     rcx, [rbp+pv]
0x180045115  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004511a  mov     rcx, [rbp+18h]; this
0x18004511e  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045125  test    eax, eax
0x180045127  jns     short loc_180045139
0x180045129  mov     r9d, eax; char *
0x18004512c  mov     r8, rdi; unsigned int
0x18004512f  mov     edx, 427h; void *
0x180045134  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045139  mov     dword ptr [rsp+50h+var_28], 0
0x180045141  mov     dword ptr [rsp+50h+var_30], 2; int
0x180045149  mov     r9d, 42Fh
0x18004514f  lea     r8, aMsixpackagePro; "MsixPackage::Provisioning::Library::Msi"...
0x180045156  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004515d  mov     rbx, [rbp+pv]
0x180045161  mov     rcx, rbx
0x180045164  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180045169  mov     rcx, [rbp+18h]; this
0x18004516d  test    eax, eax
0x18004516f  jns     short loc_180045181
0x180045171  mov     r9d, eax; char *
0x180045174  mov     r8, rdi; unsigned int
0x180045177  mov     edx, 42Fh; void *
0x18004517c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180045181  lea     r8, [rbp+arg_10]
0x180045185  mov     edx, esi
0x180045187  mov     rcx, [rbp+lpFileName]
0x18004518b  call    cs:__imp_TakeOwnershipOnFolder
0x180045191  mov     esi, eax
0x180045193  test    eax, eax
0x180045195  jns     short loc_1800451E5
0x180045197  mov     rcx, [rbp+18h]; this
0x18004519b  mov     rdx, [rbp+lpFileName]
0x18004519f  mov     [rsp+50h+var_28], rdx; char *
0x1800451a4  lea     rax, aFailedWhileTry_5; "Failed while trying to take ownership o"...
0x1800451ab  mov     [rsp+50h+var_30], rax; int
0x1800451b0  mov     r9d, esi; char *
0x1800451b3  mov     r8, rdi; unsigned int
0x1800451b6  mov     edx, 436h; void *
0x1800451bb  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800451c0  nop
0x1800451c1  test    rbx, rbx
0x1800451c4  jz      short loc_1800451D0
0x1800451c6  mov     rcx, rbx; pv
0x1800451c9  call    cs:__imp_CoTaskMemFree
0x1800451cf  nop
0x1800451d0  mov     byte ptr [rbp+var_10], 0
0x1800451d4  lea     rcx, [rbp+var_20]
0x1800451d8  call    _lambda_55d86e0c6a6c6761a9b9a2e277d6803f___operator__
0x1800451dd  nop
0x1800451de  mov     eax, esi
0x1800451e0  jmp     loc_1800452D1
0x1800451e5  mov     rcx, [rbp+lpFileName]; lpFileName
0x1800451e9  call    DeletePathEx
0x1800451ee  test    eax, eax
0x1800451f0  jnz     short loc_180045239
0x1800451f2  mov     rax, [rbp+lpFileName]
0x1800451f6  mov     rcx, [rbp+18h]; this
0x1800451fa  mov     [rsp+50h+var_30], rax; char *
0x1800451ff  lea     r9, aFailedDeleting; "Failed deleting path '%ws'"
0x180045206  mov     r8, rdi; unsigned int
0x180045209  mov     edx, 439h; void *
0x18004520e  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x180045213  mov     edi, eax
0x180045215  test    rbx, rbx
0x180045218  jz      short loc_180045224
0x18004521a  mov     rcx, rbx; pv
0x18004521d  call    cs:__imp_CoTaskMemFree
0x180045223  nop
0x180045224  mov     byte ptr [rbp+var_10], 0
0x180045228  lea     rcx, [rbp+var_20]
0x18004522c  call    _lambda_55d86e0c6a6c6761a9b9a2e277d6803f___operator__
0x180045231  nop
0x180045232  mov     eax, edi
0x180045234  jmp     loc_1800452D1
0x180045239  jmp     short loc_1800452B2
0x18004523b  mov     r8, [rbp+lpFileName]
0x18004523f  lea     rdx, aTheFolderSDoes; "The folder %s does not exist, must have"...
0x180045246  lea     rcx, [rbp+pv]
0x18004524a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004524f  mov     rcx, [rbp+18h]; this
0x180045253  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004525a  test    eax, eax
0x18004525c  jns     short loc_18004526E
0x18004525e  mov     r9d, eax; char *
0x180045261  mov     r8, rdi; unsigned int
0x180045264  mov     edx, 442h; void *
0x180045269  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18004526e  mov     dword ptr [rsp+50h+var_28], 0
0x180045276  mov     dword ptr [rsp+50h+var_30], esi; int
0x18004527a  mov     esi, 44Ah
0x18004527f  mov     r9d, esi
0x180045282  lea     r8, aMsixpackagePro; "MsixPackage::Provisioning::Library::Msi"...
0x180045289  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045290  mov     rbx, [rbp+pv]
0x180045294  mov     rcx, rbx
0x180045297  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18004529c  mov     rcx, [rbp+18h]; this
0x1800452a0  test    eax, eax
0x1800452a2  jns     short loc_1800452B2
0x1800452a4  mov     r9d, eax; char *
0x1800452a7  mov     r8, rdi; unsigned int
0x1800452aa  mov     edx, esi; void *
0x1800452ac  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800452b1  nop
0x1800452b2  test    rbx, rbx
0x1800452b5  jz      short loc_1800452C1
0x1800452b7  mov     rcx, rbx; pv
0x1800452ba  call    cs:__imp_CoTaskMemFree
0x1800452c0  nop
0x1800452c1  mov     byte ptr [rbp+var_10], 0
0x1800452c5  lea     rcx, [rbp+var_20]
0x1800452c9  call    _lambda_55d86e0c6a6c6761a9b9a2e277d6803f___operator__
0x1800452ce  nop
0x1800452cf  xor     eax, eax
0x1800452d1  mov     rbx, [rsp+50h+arg_18]
0x1800452d9  add     rsp, 50h
0x1800452dd  pop     rdi
0x1800452de  pop     rsi
0x1800452df  pop     rbp
0x1800452e0  retn
```
