# MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext(void)

- ea: `0x18003ead0`
- end: `0x18003ee0a`
- name: `??1MsixProvisioningContext@Library@Provisioning@MsixPackage@@QEAA@XZ`
- size: `826`
- prototype: `void __fastcall(PRTL_AVL_TABLE Table)`
- caller_count: `7`
- callee_count: `9`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x180035f40`
- `0x180036618`
- `0x1800383dc`
- `0x18003c81c`
- `0x18006dfe6`
- `0x18006e09a`
- `0x18006e3ca`

## callees

- `0x18001d65c`
- `0x180034d7c`
- `0x180035370`
- `0x180035864`
- `0x18003ead0`
- `0x18003fbb8`
- `0x180043fb4`
- `0x1800666b4`
- `0x180070010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18003ece7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ed88`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003edc0`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ece7`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003ed88`
- `msvcrt!??3@YAXPEAX@Z` at `0x18003edc0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ecca`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ebb0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003ecca`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003ec3c`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x18003eb7b`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x18003eb7b`

## string_xrefs

- `0x18003eb04`: `An attempt to rollback ownership on the root folder %ws and its children`
- `0x18003eb4a`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003ec95`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003eb43`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext`
- `0x18003ec8e`: `MsixPackage::Provisioning::Library::MsixProvisioningContext::~MsixProvisioningContext`
- `0x18003eae3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningcontext.cpp`
- `0x18003ec4e`: `(0x%x) Failed to remove temporary path %s.`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18003ead0  mov     rax, rsp
0x18003ead3  mov     [rax+10h], rbx
0x18003ead7  mov     [rax+18h], rbp
0x18003eadb  push    rdi
0x18003eadc  sub     rsp, 30h
0x18003eae0  mov     rdi, rcx
0x18003eae3  lea     rbp, aOnecoreAdminAp_5; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003eaea  cmp     qword ptr [rcx+78h], 0
0x18003eaef  jz      loc_18003EBBC
0x18003eaf5  mov     qword ptr [rax+8], 0
0x18003eafd  mov     r8, [rcx+230h]
0x18003eb04  lea     rdx, aAnAttemptToRol_0; "An attempt to rollback ownership on the"...
0x18003eb0b  lea     rcx, [rax+8]
0x18003eb0f  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003eb14  mov     rcx, [rsp+38h]; this
0x18003eb19  test    eax, eax
0x18003eb1b  jns     short loc_18003EB2D
0x18003eb1d  mov     r9d, eax; char *
0x18003eb20  mov     r8, rbp; unsigned int
0x18003eb23  mov     edx, 24h ; '$'; void *
0x18003eb28  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003eb2d  mov     [rsp+38h+var_10], 0
0x18003eb35  mov     [rsp+38h+var_18], 2; int
0x18003eb3d  mov     r9d, 2Ch ; ','
0x18003eb43  lea     r8, aMsixpackagePro_19; "MsixPackage::Provisioning::Library::Msi"...
0x18003eb4a  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003eb51  mov     rbx, [rsp+38h+pv]
0x18003eb56  mov     rcx, rbx
0x18003eb59  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003eb5e  mov     rcx, [rsp+38h]; this
0x18003eb63  test    eax, eax
0x18003eb65  jns     short loc_18003EB77
0x18003eb67  mov     r9d, eax; char *
0x18003eb6a  mov     r8, rbp; unsigned int
0x18003eb6d  mov     edx, 2Ch ; ','; void *
0x18003eb72  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003eb77  mov     rcx, [rdi+78h]
0x18003eb7b  call    cs:__imp_RollbackTakeOwnershipSession
0x18003eb82  nop     dword ptr [rax+rax+00h]
0x18003eb87  mov     rcx, [rsp+38h]; this
0x18003eb8c  test    eax, eax
0x18003eb8e  jns     short loc_18003EBA0
0x18003eb90  mov     r9d, eax; char *
0x18003eb93  mov     r8, rbp; unsigned int
0x18003eb96  mov     edx, 2Fh ; '/'; void *
0x18003eb9b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003eba0  mov     qword ptr [rdi+78h], 0
0x18003eba8  test    rbx, rbx
0x18003ebab  jz      short loc_18003EBBC
0x18003ebad  mov     rcx, rbx; pv
0x18003ebb0  call    cs:__imp_CoTaskMemFree
0x18003ebb7  nop     dword ptr [rax+rax+00h]
0x18003ebbc  mov     rdx, [rdi+2F0h]; struct ApplicabilityContext *
0x18003ebc3  test    rdx, rdx
0x18003ebc6  jz      short loc_18003EBF8
0x18003ebc8  lea     rcx, [rdi+80h]; this
0x18003ebcf  call    ?FreeApplicabilityContext@MsixApplicabilityEngine@Library@Provisioning@MsixPackage@@QEAAJPEAVApplicabilityContext@@@Z; MsixPackage::Provisioning::Library::MsixApplicabilityEngine::FreeApplicabilityContext(ApplicabilityContext *)
0x18003ebd4  mov     rcx, [rsp+38h]; this
0x18003ebd9  test    eax, eax
0x18003ebdb  jns     short loc_18003EBED
0x18003ebdd  mov     r9d, eax; char *
0x18003ebe0  mov     r8, rbp; unsigned int
0x18003ebe3  mov     edx, 35h ; '5'; void *
0x18003ebe8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ebed  mov     qword ptr [rdi+2F0h], 0
0x18003ebf8  cmp     qword ptr [rdi+278h], 0
0x18003ec00  jz      loc_18003ECD6
0x18003ec06  lea     rbx, [rdi+268h]
0x18003ec0d  cmp     qword ptr [rbx+18h], 8
0x18003ec12  jb      short loc_18003EC19
0x18003ec14  mov     rcx, [rbx]
0x18003ec17  jmp     short loc_18003EC1C
0x18003ec19  mov     rcx, rbx; lpFileName
0x18003ec1c  call    DeletePathEx
0x18003ec21  test    eax, eax
0x18003ec23  jnz     loc_18003ECD6
0x18003ec29  mov     [rsp+38h+pv], 0
0x18003ec32  cmp     qword ptr [rbx+18h], 8
0x18003ec37  jb      short loc_18003EC3C
0x18003ec39  mov     rbx, [rbx]
0x18003ec3c  call    cs:__imp_GetLastError
0x18003ec43  nop     dword ptr [rax+rax+00h]
0x18003ec48  mov     r9, rbx
0x18003ec4b  mov     r8d, eax
0x18003ec4e  lea     rdx, a0xXFailedToRem; "(0x%x) Failed to remove temporary path "...
0x18003ec55  lea     rcx, [rsp+38h+pv]
0x18003ec5a  call    ??$str_printf_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YAJAEAV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBGZZ; wil::str_printf_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>> &,ushort const *,...)
0x18003ec5f  mov     rcx, [rsp+38h]; this
0x18003ec64  test    eax, eax
0x18003ec66  jns     short loc_18003EC78
0x18003ec68  mov     r9d, eax; char *
0x18003ec6b  mov     r8, rbp; unsigned int
0x18003ec6e  mov     edx, 43h ; 'C'; void *
0x18003ec73  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ec78  mov     [rsp+38h+var_10], 0
0x18003ec80  mov     [rsp+38h+var_18], 1; int
0x18003ec88  mov     r9d, 4Bh ; 'K'
0x18003ec8e  lea     r8, aMsixpackagePro_19; "MsixPackage::Provisioning::Library::Msi"...
0x18003ec95  lea     rdx, aOnecoreAdminAp_13; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18003ec9c  mov     rbx, [rsp+38h+pv]
0x18003eca1  mov     rcx, rbx
0x18003eca4  call    ?LogInformation@ProvisioningCommonUtils@Library@Provisioning@MsixPackage@@SAJPEBG00KW4InformationLogLevel@234@J@Z; MsixPackage::Provisioning::Library::ProvisioningCommonUtils::LogInformation(ushort const *,ushort const *,ushort const *,ulong,MsixPackage::Provisioning::Library::InformationLogLevel,long)
0x18003eca9  mov     rcx, [rsp+38h]; this
0x18003ecae  test    eax, eax
0x18003ecb0  jns     short loc_18003ECC2
0x18003ecb2  mov     r9d, eax; char *
0x18003ecb5  mov     r8, rbp; unsigned int
0x18003ecb8  mov     edx, 4Bh ; 'K'; void *
0x18003ecbd  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18003ecc2  test    rbx, rbx
0x18003ecc5  jz      short loc_18003ECD6
0x18003ecc7  mov     rcx, rbx; pv
0x18003ecca  call    cs:__imp_CoTaskMemFree
0x18003ecd1  nop     dword ptr [rax+rax+00h]
0x18003ecd6  cmp     qword ptr [rdi+318h], 8
0x18003ecde  jb      short loc_18003ECF3
0x18003ece0  mov     rcx, [rdi+300h]
0x18003ece7  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003ecee  nop     dword ptr [rax+rax+00h]
0x18003ecf3  mov     ebx, 7
0x18003ecf8  mov     [rdi+318h], rbx
0x18003ecff  mov     qword ptr [rdi+310h], 0
0x18003ed0a  xor     eax, eax
0x18003ed0c  mov     [rdi+300h], ax
0x18003ed13  mov     rcx, [rdi+2E8h]
0x18003ed1a  test    rcx, rcx
0x18003ed1d  jz      short loc_18003ED2C
0x18003ed1f  mov     rax, [rcx]
0x18003ed22  mov     rax, [rax+10h]
0x18003ed26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed2b  nop
0x18003ed2c  mov     rcx, [rdi+2E0h]
0x18003ed33  test    rcx, rcx
0x18003ed36  jz      short loc_18003ED45
0x18003ed38  mov     rax, [rcx]
0x18003ed3b  mov     rax, [rax+10h]
0x18003ed3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed44  nop
0x18003ed45  mov     rcx, [rdi+2D8h]
0x18003ed4c  test    rcx, rcx
0x18003ed4f  jz      short loc_18003ED5E
0x18003ed51  mov     rax, [rcx]
0x18003ed54  mov     rax, [rax+10h]
0x18003ed58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed5d  nop
0x18003ed5e  mov     rcx, [rdi+2D0h]
0x18003ed65  test    rcx, rcx
0x18003ed68  jz      short loc_18003ED77
0x18003ed6a  mov     rax, [rcx]
0x18003ed6d  mov     rax, [rax+10h]
0x18003ed71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ed76  nop
0x18003ed77  cmp     qword ptr [rdi+2C8h], 8
0x18003ed7f  jb      short loc_18003ED94
0x18003ed81  mov     rcx, [rdi+2B0h]
0x18003ed88  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003ed8f  nop     dword ptr [rax+rax+00h]
0x18003ed94  mov     [rdi+2C8h], rbx
0x18003ed9b  mov     qword ptr [rdi+2C0h], 0
0x18003eda6  xor     eax, eax
0x18003eda8  mov     [rdi+2B0h], ax
0x18003edaf  cmp     qword ptr [rdi+280h], 8
0x18003edb7  jb      short loc_18003EDCC
0x18003edb9  mov     rcx, [rdi+268h]
0x18003edc0  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18003edc7  nop     dword ptr [rax+rax+00h]
0x18003edcc  mov     [rdi+280h], rbx
0x18003edd3  mov     qword ptr [rdi+278h], 0
0x18003edde  xor     eax, eax
0x18003ede0  mov     [rdi+268h], ax
0x18003ede7  lea     rcx, [rdi+80h]; this
0x18003edee  call    ??1MsixProvisioningModules@Library@Provisioning@MsixPackage@@QEAA@XZ; MsixPackage::Provisioning::Library::MsixProvisioningModules::~MsixProvisioningModules(void)
0x18003edf3  mov     rcx, rdi; Table
0x18003edf6  mov     rbx, [rsp+38h+arg_8]
0x18003edfb  mov     rbp, [rsp+38h+arg_10]
0x18003ee00  add     rsp, 30h
0x18003ee04  pop     rdi
0x18003ee05  jmp     ??1?$GenericMap@PEAEPEAVHardlinkTarget@Library@Provisioning@MsixPackage@@@Common@@QEAA@XZ; Common::GenericMap<uchar *,MsixPackage::Provisioning::Library::HardlinkTarget *>::~GenericMap<uchar *,MsixPackage::Provisioning::Library::HardlinkTarget *>(void)
```
