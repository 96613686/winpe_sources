# MsixPackage::Provisioning::Library::MsixProvisioningRequest::CheckForExistingMainPackageAndRemove(ushort const *)

- ea: `0x18004e678`
- end: `0x18004e85b`
- name: `?CheckForExistingMainPackageAndRemove@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z`
- size: `483`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixProvisioningRequest *this, const char *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x18004dae8`
- `0x18004e1fc`

## callees

- `0x18000cfe8`
- `0x180039e9c`
- `0x180042444`
- `0x180049a44`
- `0x18004e678`
- `0x18006a010`

## import_xrefs

- `AppXAllUserStore!DeletePackageInfo` at `0x18004e704`
- `AppXAllUserStore!DeletePackageInfo` at `0x18004e846`
- `AppXAllUserStore!DeletePackageInfo` at `0x18004e704`
- `AppXAllUserStore!DeletePackageInfo` at `0x18004e846`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x18004e6c3`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x18004e6c3`

## string_xrefs

- `0x18004e6d8`: `Failed to find an existing version for package %ws in registry store`
- `0x18004e6e7`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004e742`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004e7b3`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004e7f8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x18004e7a4`: `Failed to remove equal or lower package version %ws`
- `0x18004e72e`: `Failed while adding package %ws since a higher version of the package, %ws, already exists`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::CheckForExistingMainPackageAndRemove(
        MsixPackage::Provisioning::Library::MsixProvisioningRequest *this,
        const char *a2)
{
  int ExistingVersionInRegistryStore; // ebx
  int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v8; // [rsp+70h] [rbp+20h] BYREF
  const unsigned __int16 **v9; // [rsp+80h] [rbp+30h] BYREF
  struct MsixPackage::Provisioning::Library::MsixPackageAdapter *v10; // [rsp+88h] [rbp+38h] BYREF

  v9 = 0;
  v8 = 0;
  ExistingVersionInRegistryStore = FindExistingVersionInRegistryStore(
                                     *(_QWORD *)(*((_QWORD *)this + 2) + 584LL),
                                     a2,
                                     0,
                                     &v8);
  if ( ExistingVersionInRegistryStore < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x44E,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
      (const char *)(unsigned int)ExistingVersionInRegistryStore,
      (int)"Failed to find an existing version for package %ws in registry store",
      a2);
LABEL_3:
    if ( v9 )
      DeletePackageInfo(&v9);
    return (unsigned int)ExistingVersionInRegistryStore;
  }
  if ( v8 == 3 )
  {
    ExistingVersionInRegistryStore = -1051262696;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x456,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
      (const char *)0xC1570118LL,
      (int)"Failed while adding package %ws since a higher version of the package, %ws, already exists",
      a2,
      *v9);
    goto LABEL_3;
  }
  if ( ((v8 - 1) & 0xFFFFFFFC) == 0 && v8 != 3 )
  {
    v10 = 0;
    ExistingVersionInRegistryStore = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(
                                       *v9,
                                       *((struct MsixPackage::Provisioning::Library::MsixProvisioningContext **)this + 2),
                                       1,
                                       &v10);
    if ( ExistingVersionInRegistryStore < 0 )
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x462,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)ExistingVersionInRegistryStore,
        (int)"Failed to remove equal or lower package version %ws",
        (const char *)*v9);
      if ( v10 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_3;
    }
    v6 = MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage(v10, 0);
    ExistingVersionInRegistryStore = v6;
    if ( v6 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x464,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixprovisioningrequest.cpp",
        (const char *)(unsigned int)v6,
        (int)&v9);
      if ( v10 )
        (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
      goto LABEL_3;
    }
    if ( v10 )
      (*(void (__fastcall **)(struct MsixPackage::Provisioning::Library::MsixPackageAdapter *))(*(_QWORD *)v10 + 16LL))(v10);
  }
  if ( v9 )
    DeletePackageInfo(&v9);
  return 0;
}

```

## disassembly

```asm
0x18004e678  mov     [rsp-18h+arg_8], rbx
0x18004e67d  push    rbp
0x18004e67e  push    rsi
0x18004e67f  push    rdi
0x18004e680  mov     rbp, rsp
0x18004e683  sub     rsp, 50h
0x18004e687  mov     rdi, rdx
0x18004e68a  mov     rsi, rcx
0x18004e68d  mov     [rbp+arg_10], 0
0x18004e695  mov     [rbp+arg_0], 0
0x18004e69c  lea     rax, [rbp+arg_10]
0x18004e6a0  mov     [rbp+var_10], rax
0x18004e6a4  mov     [rbp+var_8], 1
0x18004e6a8  mov     rcx, [rcx+10h]
0x18004e6ac  lea     rax, [rbp+arg_10]
0x18004e6b0  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004e6b5  lea     r9, [rbp+arg_0]
0x18004e6b9  xor     r8d, r8d
0x18004e6bc  mov     rcx, [rcx+248h]
0x18004e6c3  call    cs:__imp_FindExistingVersionInRegistryStore
0x18004e6c9  mov     ebx, eax
0x18004e6cb  test    eax, eax
0x18004e6cd  jns     short loc_18004E711
0x18004e6cf  mov     rcx, [rbp+18h]; this
0x18004e6d3  mov     [rsp+50h+var_28], rdi; char *
0x18004e6d8  lea     rax, aFailedToFindAn; "Failed to find an existing version for "...
0x18004e6df  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004e6e4  mov     r9d, ebx; char *
0x18004e6e7  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e6ee  mov     edx, 44Eh; void *
0x18004e6f3  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e6f8  nop
0x18004e6f9  cmp     [rbp+arg_10], 0
0x18004e6fe  jz      short loc_18004E70A
0x18004e700  lea     rcx, [rbp+arg_10]
0x18004e704  call    cs:__imp_DeletePackageInfo
0x18004e70a  mov     eax, ebx
0x18004e70c  jmp     loc_18004E84E
0x18004e711  mov     ecx, [rbp+arg_0]
0x18004e714  cmp     ecx, 3
0x18004e717  jnz     short loc_18004E755
0x18004e719  mov     rcx, [rbp+18h]; this
0x18004e71d  mov     rax, [rbp+arg_10]
0x18004e721  mov     rdx, [rax]
0x18004e724  mov     [rsp+50h+var_20], rdx
0x18004e729  mov     [rsp+50h+var_28], rdi; char *
0x18004e72e  lea     rax, aFailedWhileAdd_1; "Failed while adding package %ws since a"...
0x18004e735  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004e73a  mov     ebx, 0C1570118h
0x18004e73f  mov     r9d, ebx; char *
0x18004e742  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e749  mov     edx, 456h; void *
0x18004e74e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e753  jmp     short loc_18004E6F9
0x18004e755  lea     eax, [rcx-1]
0x18004e758  test    eax, 0FFFFFFFCh
0x18004e75d  jnz     loc_18004E83B
0x18004e763  cmp     ecx, 3
0x18004e766  jz      loc_18004E83B
0x18004e76c  mov     [rbp+arg_18], 0
0x18004e774  lea     r9, [rbp+arg_18]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x18004e778  mov     r8d, 1; int
0x18004e77e  mov     rdx, [rsi+10h]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x18004e782  mov     rcx, [rbp+arg_10]
0x18004e786  mov     rcx, [rcx]; unsigned __int16 *
0x18004e789  call    ?CreateForRemove@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@HPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x18004e78e  mov     ebx, eax
0x18004e790  test    eax, eax
0x18004e792  jns     short loc_18004E7E0
0x18004e794  mov     rcx, [rbp+18h]; this
0x18004e798  mov     rdx, [rbp+arg_10]
0x18004e79c  mov     r8, [rdx]
0x18004e79f  mov     [rsp+50h+var_28], r8; char *
0x18004e7a4  lea     rax, aFailedToRemove_8; "Failed to remove equal or lower package"...
0x18004e7ab  mov     qword ptr [rsp+50h+var_30], rax; int
0x18004e7b0  mov     r9d, ebx; char *
0x18004e7b3  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e7ba  mov     edx, 462h; void *
0x18004e7bf  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004e7c4  nop
0x18004e7c5  mov     rcx, [rbp+arg_18]
0x18004e7c9  test    rcx, rcx
0x18004e7cc  jz      short loc_18004E7DB
0x18004e7ce  mov     rax, [rcx]
0x18004e7d1  mov     rax, [rax+10h]
0x18004e7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e7da  nop
0x18004e7db  jmp     loc_18004E6F9
0x18004e7e0  xor     edx, edx; int
0x18004e7e2  mov     rcx, [rbp+arg_18]; this
0x18004e7e6  call    ?RemovePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage(int)
0x18004e7eb  mov     ebx, eax
0x18004e7ed  test    eax, eax
0x18004e7ef  jns     short loc_18004E825
0x18004e7f1  mov     rcx, [rbp+18h]; this
0x18004e7f5  mov     r9d, eax; char *
0x18004e7f8  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004e7ff  mov     edx, 464h; void *
0x18004e804  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004e809  nop
0x18004e80a  mov     rcx, [rbp+arg_18]
0x18004e80e  test    rcx, rcx
0x18004e811  jz      short loc_18004E820
0x18004e813  mov     rax, [rcx]
0x18004e816  mov     rax, [rax+10h]
0x18004e81a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e81f  nop
0x18004e820  jmp     loc_18004E6F9
0x18004e825  mov     rcx, [rbp+arg_18]
0x18004e829  test    rcx, rcx
0x18004e82c  jz      short loc_18004E83B
0x18004e82e  mov     rax, [rcx]
0x18004e831  mov     rax, [rax+10h]
0x18004e835  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004e83a  nop
0x18004e83b  cmp     [rbp+arg_10], 0
0x18004e840  jz      short loc_18004E84C
0x18004e842  lea     rcx, [rbp+arg_10]
0x18004e846  call    cs:__imp_DeletePackageInfo
0x18004e84c  xor     eax, eax
0x18004e84e  mov     rbx, [rsp+50h+arg_8]
0x18004e853  add     rsp, 50h
0x18004e857  pop     rdi
0x18004e858  pop     rsi
0x18004e859  pop     rbp
0x18004e85a  retn
```
