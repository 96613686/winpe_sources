# MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)

- ea: `0x18003b3f8`
- end: `0x18003b708`
- name: `??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ`
- size: `784`
- prototype: `void __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180032f28`
- `0x1800335d8`
- `0x1800350d0`
- `0x18003925c`
- `0x1800684c4`
- `0x180068578`
- `0x1800688a8`

## callees

- `0x18001c5b8`
- `0x180031ed8`
- `0x18003248c`
- `0x1800328e4`
- `0x18003b3f8`
- `0x18003c414`
- `0x180040400`
- `0x1800612f0`
- `0x18006a010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003b5f7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b692`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b6c4`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b5f7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b692`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003b6c4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b5e0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b4d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003b5e0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b558`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003b558`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x18003b4a3`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x18003b4a3`

## string_xrefs

- `0x18003b42c`: `An attempt to rollback ownership on the root folder %ws and its children`
- `0x18003b40b`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003b564`: `(0x%x) Failed to remove temporary path %s.`
- `0x18003b472`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003b5ab`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003b46b`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext`
- `0x18003b5a4`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
void __fastcall MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(
        PRTL_AVL_TABLE Table)
{
  int v2; // eax
  void *v3; // rbx
  int v4; // eax
  int v5; // eax
  struct ApplicabilityContext *v6; // rdx
  int v7; // eax
  PVOID **p_TableContext; // rbx
  const WCHAR *v9; // rcx
  DWORD LastError; // eax
  int v11; // eax
  void *v12; // rbx
  int v13; // eax
  struct _RTL_BALANCED_LINKS *RightChild; // rcx
  struct _RTL_BALANCED_LINKS *LeftChild; // rcx
  struct _RTL_BALANCED_LINKS *Parent; // rcx
  PVOID TableContext; // rcx
  int v18; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]
  LPVOID pv; // [rsp+40h] [rbp+8h] BYREF

  if ( Table[1].BalancedRoot.RightChild )
  {
    pv = 0;
    v2 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
           (char *)&pv,
           L"An attempt to rollback ownership on the root folder %ws and its children",
           *(_QWORD *)&Table[5].WhichOrderedElement);
    if ( v2 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x24,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)v2,
        v18);
    v18 = 2;
    v3 = pv;
    v4 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
           pv,
           L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
           L"MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext",
           44);
    if ( v4 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2C,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)v4,
        2);
    v5 = RollbackTakeOwnershipSession(Table[1].BalancedRoot.RightChild);
    if ( v5 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x2F,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)v5,
        v18);
    Table[1].BalancedRoot.RightChild = 0;
    if ( v3 )
      CoTaskMemFree(v3);
  }
  v6 = *(struct ApplicabilityContext **)&Table[7].BalancedRoot.Balance;
  if ( v6 )
  {
    v7 = MsixPackage::Provisioning::Library::MsixApplicabilityEngine::FreeApplicabilityContext(
           (MsixPackage::Provisioning::Library::MsixApplicabilityEngine *)&Table[1].BalancedRoot.Balance,
           v6);
    if ( v7 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x35,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
        (const char *)(unsigned int)v7,
        v18);
    *(_QWORD *)&Table[7].BalancedRoot.Balance = 0;
  }
  if ( Table[6].BalancedRoot.LeftChild )
  {
    p_TableContext = (PVOID **)&Table[5].TableContext;
    v9 = (const WCHAR *)(Table[6].BalancedRoot.RightChild < (struct _RTL_BALANCED_LINKS *)8
                       ? &Table[5].TableContext
                       : *p_TableContext);
    if ( !(unsigned int)DeletePathEx(v9) )
    {
      pv = 0;
      if ( Table[6].BalancedRoot.RightChild >= (struct _RTL_BALANCED_LINKS *)8 )
        p_TableContext = (PVOID **)*p_TableContext;
      LastError = GetLastError();
      v11 = wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
              (char *)&pv,
              L"(0x%x) Failed to remove temporary path %s.",
              LastError,
              p_TableContext);
      if ( v11 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x43,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v11,
          v18);
      v12 = pv;
      v13 = MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(
              pv,
              L"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
              L"MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext",
              75);
      if ( v13 < 0 )
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x4B,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningcontext.cpp",
          (const char *)(unsigned int)v13,
          1);
      if ( v12 )
        CoTaskMemFree(v12);
    }
  }
  if ( *(_QWORD *)&Table[7].DeleteCount >= 8u )
    operator delete(*(void **)&Table[7].WhichOrderedElement);
  *(_QWORD *)&Table[7].DeleteCount = 7;
  Table[7].RestartKey = 0;
  LOWORD(Table[7].WhichOrderedElement) = 0;
  RightChild = Table[7].BalancedRoot.RightChild;
  if ( RightChild )
    ((void (__fastcall *)(struct _RTL_BALANCED_LINKS *))RightChild->Parent->RightChild)(RightChild);
  LeftChild = Table[7].BalancedRoot.LeftChild;
  if ( LeftChild )
    ((void (__fastcall *)(struct _RTL_BALANCED_LINKS *))LeftChild->Parent->RightChild)(LeftChild);
  Parent = Table[7].BalancedRoot.Parent;
  if ( Parent )
    ((void (__fastcall *)(struct _RTL_BALANCED_LINKS *))Parent->Parent->RightChild)(Parent);
  TableContext = Table[6].TableContext;
  if ( TableContext )
    (*(void (__fastcall **)(PVOID))(*(_QWORD *)TableContext + 16LL))(TableContext);
  if ( (char *)Table[6].FreeRoutine >= (char *)8 )
    operator delete(*(void **)&Table[6].DeleteCount);
  Table[6].FreeRoutine = (PRTL_AVL_FREE_ROUTINE)7;
  Table[6].AllocateRoutine = 0;
  LOWORD(Table[6].DeleteCount) = 0;
  if ( Table[6].BalancedRoot.RightChild >= (struct _RTL_BALANCED_LINKS *)8 )
    operator delete(Table[5].TableContext);
  Table[6].BalancedRoot.RightChild = (struct _RTL_BALANCED_LINKS *)7;
  Table[6].BalancedRoot.LeftChild = 0;
  LOWORD(Table[5].TableContext) = 0;
  MsixPackage::Provisioning::Library::MsixProvisioningModules::~MsixProvisioningModules((MsixPackage::Provisioning::Library::MsixProvisioningModules *)&Table[1].BalancedRoot.Balance);
  Common::GenericMap<unsigned char *,MsixPackage::Provisioning::Library::HardlinkTarget *>::~GenericMap<unsigned char *,MsixPackage::Provisioning::Library::HardlinkTarget *>(Table);
}

```

## disassembly

```asm
0x18003b3f8  mov     rax, rsp
0x18003b3fb  mov     [rax+10h], rbx
0x18003b3ff  mov     [rax+18h], rbp
0x18003b403  push    rdi
0x18003b404  sub     rsp, 30h
0x18003b408  mov     rdi, rcx
0x18003b40b  lea     rbp, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003b412  cmp     qword ptr [rcx+78h], 0
0x18003b417  jz      loc_18003B4D8
0x18003b41d  mov     qword ptr [rax+8], 0
0x18003b425  mov     r8, [rcx+230h]
0x18003b42c  lea     rdx, aAnAttemptToRol_0; "An attempt to rollback ownership on the"...
0x18003b433  lea     rcx, [rax+8]
0x18003b437  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003b43c  mov     rcx, [rsp+38h]; this
0x18003b441  test    eax, eax
0x18003b443  jns     short loc_18003B455
0x18003b445  mov     r9d, eax; char *
0x18003b448  mov     r8, rbp; unsigned int
0x18003b44b  mov     edx, 24h ; '$'; void *
0x18003b450  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b455  mov     [rsp+38h+var_10], 0
0x18003b45d  mov     [rsp+38h+var_18], 2; int
0x18003b465  mov     r9d, 2Ch ; ','
0x18003b46b  lea     r8, aMsixpackagePro_19; "MsixPackage::Provisioning::Library::Msi"...
0x18003b472  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003b479  mov     rbx, [rsp+38h+pv]
0x18003b47e  mov     rcx, rbx
0x18003b481  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003b486  mov     rcx, [rsp+38h]; this
0x18003b48b  test    eax, eax
0x18003b48d  jns     short loc_18003B49F
0x18003b48f  mov     r9d, eax; char *
0x18003b492  mov     r8, rbp; unsigned int
0x18003b495  mov     edx, 2Ch ; ','; void *
0x18003b49a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b49f  mov     rcx, [rdi+78h]
0x18003b4a3  call    cs:__imp_RollbackTakeOwnershipSession
0x18003b4a9  mov     rcx, [rsp+38h]; this
0x18003b4ae  test    eax, eax
0x18003b4b0  jns     short loc_18003B4C2
0x18003b4b2  mov     r9d, eax; char *
0x18003b4b5  mov     r8, rbp; unsigned int
0x18003b4b8  mov     edx, 2Fh ; '/'; void *
0x18003b4bd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b4c2  mov     qword ptr [rdi+78h], 0
0x18003b4ca  test    rbx, rbx
0x18003b4cd  jz      short loc_18003B4D8
0x18003b4cf  mov     rcx, rbx; pv
0x18003b4d2  call    cs:__imp_CoTaskMemFree
0x18003b4d8  mov     rdx, [rdi+2F0h]; struct ApplicabilityContext *
0x18003b4df  test    rdx, rdx
0x18003b4e2  jz      short loc_18003B514
0x18003b4e4  lea     rcx, [rdi+80h]; this
0x18003b4eb  call    ?FreeApplicabilityContext@MsixApplicabilityEngine@Library@Provisioning@MsixPackage@@QEAAJPEAVApplicabilityContext@@@Z; MsixPackage::Provisioning::Library::MsixApplicabilityEngine::FreeApplicabilityContext(ApplicabilityContext *)
0x18003b4f0  mov     rcx, [rsp+38h]; this
0x18003b4f5  test    eax, eax
0x18003b4f7  jns     short loc_18003B509
0x18003b4f9  mov     r9d, eax; char *
0x18003b4fc  mov     r8, rbp; unsigned int
0x18003b4ff  mov     edx, 35h ; '5'; void *
0x18003b504  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b509  mov     qword ptr [rdi+2F0h], 0
0x18003b514  cmp     qword ptr [rdi+278h], 0
0x18003b51c  jz      loc_18003B5E6
0x18003b522  lea     rbx, [rdi+268h]
0x18003b529  cmp     qword ptr [rbx+18h], 8
0x18003b52e  jb      short loc_18003B535
0x18003b530  mov     rcx, [rbx]
0x18003b533  jmp     short loc_18003B538
0x18003b535  mov     rcx, rbx; lpFileName
0x18003b538  call    DeletePathEx
0x18003b53d  test    eax, eax
0x18003b53f  jnz     loc_18003B5E6
0x18003b545  mov     [rsp+38h+pv], 0
0x18003b54e  cmp     qword ptr [rbx+18h], 8
0x18003b553  jb      short loc_18003B558
0x18003b555  mov     rbx, [rbx]
0x18003b558  call    cs:__imp_GetLastError
0x18003b55e  mov     r9, rbx
0x18003b561  mov     r8d, eax
0x18003b564  lea     rdx, a0xXFailedToRem; "(0x%x) Failed to remove temporary path "...
0x18003b56b  lea     rcx, [rsp+38h+pv]
0x18003b570  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003b575  mov     rcx, [rsp+38h]; this
0x18003b57a  test    eax, eax
0x18003b57c  jns     short loc_18003B58E
0x18003b57e  mov     r9d, eax; char *
0x18003b581  mov     r8, rbp; unsigned int
0x18003b584  mov     edx, 43h ; 'C'; void *
0x18003b589  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b58e  mov     [rsp+38h+var_10], 0
0x18003b596  mov     [rsp+38h+var_18], 1; int
0x18003b59e  mov     r9d, 4Bh ; 'K'
0x18003b5a4  lea     r8, aMsixpackagePro_19; "MsixPackage::Provisioning::Library::Msi"...
0x18003b5ab  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003b5b2  mov     rbx, [rsp+38h+pv]
0x18003b5b7  mov     rcx, rbx
0x18003b5ba  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003b5bf  mov     rcx, [rsp+38h]; this
0x18003b5c4  test    eax, eax
0x18003b5c6  jns     short loc_18003B5D8
0x18003b5c8  mov     r9d, eax; char *
0x18003b5cb  mov     r8, rbp; unsigned int
0x18003b5ce  mov     edx, 4Bh ; 'K'; void *
0x18003b5d3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003b5d8  test    rbx, rbx
0x18003b5db  jz      short loc_18003B5E6
0x18003b5dd  mov     rcx, rbx; pv
0x18003b5e0  call    cs:__imp_CoTaskMemFree
0x18003b5e6  cmp     qword ptr [rdi+318h], 8
0x18003b5ee  jb      short loc_18003B5FD
0x18003b5f0  mov     rcx, [rdi+300h]
0x18003b5f7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003b5fd  mov     ebx, 7
0x18003b602  mov     [rdi+318h], rbx
0x18003b609  mov     qword ptr [rdi+310h], 0
0x18003b614  xor     eax, eax
0x18003b616  mov     [rdi+300h], ax
0x18003b61d  mov     rcx, [rdi+2E8h]
0x18003b624  test    rcx, rcx
0x18003b627  jz      short loc_18003B636
0x18003b629  mov     rax, [rcx]
0x18003b62c  mov     rax, [rax+10h]
0x18003b630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b635  nop
0x18003b636  mov     rcx, [rdi+2E0h]
0x18003b63d  test    rcx, rcx
0x18003b640  jz      short loc_18003B64F
0x18003b642  mov     rax, [rcx]
0x18003b645  mov     rax, [rax+10h]
0x18003b649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b64e  nop
0x18003b64f  mov     rcx, [rdi+2D8h]
0x18003b656  test    rcx, rcx
0x18003b659  jz      short loc_18003B668
0x18003b65b  mov     rax, [rcx]
0x18003b65e  mov     rax, [rax+10h]
0x18003b662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b667  nop
0x18003b668  mov     rcx, [rdi+2D0h]
0x18003b66f  test    rcx, rcx
0x18003b672  jz      short loc_18003B681
0x18003b674  mov     rax, [rcx]
0x18003b677  mov     rax, [rax+10h]
0x18003b67b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b680  nop
0x18003b681  cmp     qword ptr [rdi+2C8h], 8
0x18003b689  jb      short loc_18003B698
0x18003b68b  mov     rcx, [rdi+2B0h]
0x18003b692  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003b698  mov     [rdi+2C8h], rbx
0x18003b69f  mov     qword ptr [rdi+2C0h], 0
0x18003b6aa  xor     eax, eax
0x18003b6ac  mov     [rdi+2B0h], ax
0x18003b6b3  cmp     qword ptr [rdi+280h], 8
0x18003b6bb  jb      short loc_18003B6CA
0x18003b6bd  mov     rcx, [rdi+268h]
0x18003b6c4  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003b6ca  mov     [rdi+280h], rbx
0x18003b6d1  mov     qword ptr [rdi+278h], 0
0x18003b6dc  xor     eax, eax
0x18003b6de  mov     [rdi+268h], ax
0x18003b6e5  lea     rcx, [rdi+80h]; this
0x18003b6ec  call    ??1MsixProvisioningModules@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningModules::~MsixProvisioningModules(void)
0x18003b6f1  mov     rcx, rdi; Table
0x18003b6f4  mov     rbx, [rsp+38h+arg_8]
0x18003b6f9  mov     rbp, [rsp+38h+arg_10]
0x18003b6fe  add     rsp, 30h
0x18003b702  pop     rdi
0x18003b703  jmp     ??1?$GenericMap@PEAEPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@QEAA@XZ; Common::GenericMap<uchar *,MsixPackage::Provisioning::Library::HardlinkTarget *>::~GenericMap<uchar *,MsixPackage::Provisioning::Library::HardlinkTarget *>(void)
```
