# MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath(ushort const *)

- ea: `0x180048fe8`
- end: `0x180049226`
- name: `?DestagePath@MsixPackageAdapter@Library@Provisioning@MsixPackage@@CAJPEBG@Z`
- size: `574`
- prototype: `__int64 __fastcall(const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180048dec`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x18003d4b0`
- `0x18003d4ec`
- `0x180043fb4`
- `0x18004501c`
- `0x180048fe8`
- `0x180063c48`
- `0x1800666b4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800490fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800491f8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800490fb`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049155`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800491f8`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x1800490b7`
- `AppXAllUserStore!TakeOwnershipOnFolder` at `0x1800490b7`

## string_xrefs

- `0x18004904a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049191`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180049082`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x1800491c7`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004907b`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath`
- `0x1800491c0`: `MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePath`
- `0x180049036`: ` An attempt to obtain ownership on the root folder %ws and its children`
- `0x18004917d`: `The folder %s does not exist, must have already been de - staged`
- `0x180049137`: `Failed deleting path '%ws'`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
  int v10; // [rsp+20h] [rbp-30h]
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
           &pv,
           L" An attempt to obtain ownership on the root folder %ws and its children",
           lpFileName);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x427,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v2,
        v10);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v4,
        2);
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
                       0,
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
           &pv,
           L"The folder %s does not exist, must have already been de - staged",
           lpFileName);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x442,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v8,
        v10);
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
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v9,
        1);
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
0x180048fe8  mov     [rsp-18h+arg_18], rbx
0x180048fed  mov     [rsp-18h+lpFileName], rcx
0x180048ff2  push    rbp
0x180048ff3  push    rsi
0x180048ff4  push    rdi
0x180048ff5  mov     rbp, rsp
0x180048ff8  sub     rsp, 50h
0x180048ffc  mov     [rbp+arg_10], 0
0x180049004  lea     rax, [rbp+arg_10]
0x180049008  mov     [rbp+var_20], rax
0x18004900c  lea     rax, [rbp+lpFileName]
0x180049010  mov     [rbp+var_18], rax
0x180049014  mov     esi, 1
0x180049019  mov     byte ptr [rbp+var_10], sil
0x18004901d  call    DirectoryExists
0x180049022  mov     [rbp+pv], 0
0x18004902a  test    eax, eax
0x18004902c  jz      loc_180049179
0x180049032  mov     r8, [rbp+lpFileName]
0x180049036  lea     rdx, aAnAttemptToObt_1; " An attempt to obtain ownership on the "...
0x18004903d  lea     rcx, [rbp+pv]
0x180049041  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x180049046  mov     rcx, [rbp+18h]; this
0x18004904a  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049051  test    eax, eax
0x180049053  jns     short loc_180049065
0x180049055  mov     r9d, eax; char *
0x180049058  mov     r8, rdi; unsigned int
0x18004905b  mov     edx, 427h; void *
0x180049060  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x180049065  mov     dword ptr [rsp+50h+var_28], 0
0x18004906d  mov     dword ptr [rsp+50h+var_30], 2; int
0x180049075  mov     r9d, 42Fh
0x18004907b  lea     r8, aMsixpackagePro; "MsixPackage::Provisioning::Library::Msi"...
0x180049082  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049089  mov     rbx, [rbp+pv]
0x18004908d  mov     rcx, rbx
0x180049090  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x180049095  mov     rcx, [rbp+18h]; this
0x180049099  test    eax, eax
0x18004909b  jns     short loc_1800490AD
0x18004909d  mov     r9d, eax; char *
0x1800490a0  mov     r8, rdi; unsigned int
0x1800490a3  mov     edx, 42Fh; void *
0x1800490a8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800490ad  lea     r8, [rbp+arg_10]
0x1800490b1  mov     edx, esi
0x1800490b3  mov     rcx, [rbp+lpFileName]
0x1800490b7  call    cs:__imp_TakeOwnershipOnFolder
0x1800490be  nop     dword ptr [rax+rax+00h]
0x1800490c3  mov     esi, eax
0x1800490c5  test    eax, eax
0x1800490c7  jns     short loc_18004911D
0x1800490c9  mov     rcx, [rbp+18h]; this
0x1800490cd  mov     rdx, [rbp+lpFileName]
0x1800490d1  mov     [rsp+50h+var_28], rdx; char *
0x1800490d6  lea     rax, aFailedWhileTry_5; "Failed while trying to take ownership o"...
0x1800490dd  mov     [rsp+50h+var_30], rax; int
0x1800490e2  mov     r9d, esi; char *
0x1800490e5  mov     r8, rdi; unsigned int
0x1800490e8  mov     edx, 436h; void *
0x1800490ed  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800490f2  nop
0x1800490f3  test    rbx, rbx
0x1800490f6  jz      short loc_180049108
0x1800490f8  mov     rcx, rbx; pv
0x1800490fb  call    cs:__imp_CoTaskMemFree
0x180049102  nop     dword ptr [rax+rax+00h]
0x180049107  nop
0x180049108  mov     byte ptr [rbp+var_10], 0
0x18004910c  lea     rcx, [rbp+var_20]
0x180049110  call    _lambda_55d86e0c6a6c6761a9b9a2e277d6803f___operator__
0x180049115  nop
0x180049116  mov     eax, esi
0x180049118  jmp     loc_180049215
0x18004911d  mov     rcx, [rbp+lpFileName]; lpFileName
0x180049121  call    DeletePathEx
0x180049126  test    eax, eax
0x180049128  jnz     short loc_180049177
0x18004912a  mov     rax, [rbp+lpFileName]
0x18004912e  mov     rcx, [rbp+18h]; this
0x180049132  mov     [rsp+50h+var_30], rax; char *
0x180049137  lea     r9, aFailedDeleting; "Failed deleting path '%ws'"
0x18004913e  mov     r8, rdi; unsigned int
0x180049141  mov     edx, 439h; void *
0x180049146  call    ?Return_GetLastErrorMsg@in1diag3@details@wil@@YAJPEAXIPEBD1ZZ; wil::details::in1diag3::Return_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x18004914b  mov     edi, eax
0x18004914d  test    rbx, rbx
0x180049150  jz      short loc_180049162
0x180049152  mov     rcx, rbx; pv
0x180049155  call    cs:__imp_CoTaskMemFree
0x18004915c  nop     dword ptr [rax+rax+00h]
0x180049161  nop
0x180049162  mov     byte ptr [rbp+var_10], 0
0x180049166  lea     rcx, [rbp+var_20]
0x18004916a  call    _lambda_55d86e0c6a6c6761a9b9a2e277d6803f___operator__
0x18004916f  nop
0x180049170  mov     eax, edi
0x180049172  jmp     loc_180049215
0x180049177  jmp     short loc_1800491F0
0x180049179  mov     r8, [rbp+lpFileName]
0x18004917d  lea     rdx, aTheFolderSDoes; "The folder %s does not exist, must have"...
0x180049184  lea     rcx, [rbp+pv]
0x180049188  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18004918d  mov     rcx, [rbp+18h]; this
0x180049191  lea     rdi, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180049198  test    eax, eax
0x18004919a  jns     short loc_1800491AC
0x18004919c  mov     r9d, eax; char *
0x18004919f  mov     r8, rdi; unsigned int
0x1800491a2  mov     edx, 442h; void *
0x1800491a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800491ac  mov     dword ptr [rsp+50h+var_28], 0
0x1800491b4  mov     dword ptr [rsp+50h+var_30], esi; int
0x1800491b8  mov     esi, 44Ah
0x1800491bd  mov     r9d, esi
0x1800491c0  lea     r8, aMsixpackagePro; "MsixPackage::Provisioning::Library::Msi"...
0x1800491c7  lea     rdx, aOnecoreAdminAp_4; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800491ce  mov     rbx, [rbp+pv]
0x1800491d2  mov     rcx, rbx
0x1800491d5  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x1800491da  mov     rcx, [rbp+18h]; this
0x1800491de  test    eax, eax
0x1800491e0  jns     short loc_1800491F0
0x1800491e2  mov     r9d, eax; char *
0x1800491e5  mov     r8, rdi; unsigned int
0x1800491e8  mov     edx, esi; void *
0x1800491ea  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x1800491ef  nop
0x1800491f0  test    rbx, rbx
0x1800491f3  jz      short loc_180049205
0x1800491f5  mov     rcx, rbx; pv
0x1800491f8  call    cs:__imp_CoTaskMemFree
0x1800491ff  nop     dword ptr [rax+rax+00h]
0x180049204  nop
0x180049205  mov     byte ptr [rbp+var_10], 0
0x180049209  lea     rcx, [rbp+var_20]
0x18004920d  call    _lambda_55d86e0c6a6c6761a9b9a2e277d6803f___operator__
0x180049212  nop
0x180049213  xor     eax, eax
0x180049215  mov     rbx, [rsp+50h+arg_18]
0x18004921d  add     rsp, 50h
0x180049221  pop     rdi
0x180049222  pop     rsi
0x180049223  pop     rbp
0x180049224  retn
```
