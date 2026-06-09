# MsixPackage::Provisioning::Library::MsixProvisioningRequest::CheckForExistingMainPackageAndRemove(ushort const *)

- ea: `0x18005294c`
- end: `0x180052b42`
- name: `?CheckForExistingMainPackageAndRemove@MsixProvisioningRequest@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z`
- size: `502`
- prototype: `int(MsixPackage::Provisioning::Library::MsixProvisioningRequest *__hidden this, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, registry_config, installer_update`

## callers

- `0x180051db0`
- `0x1800524d0`

## callees

- `0x18000d3dc`
- `0x18003d4ec`
- `0x1800461ac`
- `0x18004db50`
- `0x18005294c`
- `0x180070010`

## import_xrefs

- `AppXAllUserStore!DeletePackageInfo` at `0x1800529de`
- `AppXAllUserStore!DeletePackageInfo` at `0x180052b26`
- `AppXAllUserStore!DeletePackageInfo` at `0x1800529de`
- `AppXAllUserStore!DeletePackageInfo` at `0x180052b26`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x180052997`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x180052997`

## string_xrefs

- `0x1800529b2`: `Failed to find an existing version for package %ws in registry store`
- `0x1800529c1`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180052a22`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180052a93`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180052ad8`: `onecore\admin\appmodel\utilities\provisionhelper\msixprovisioningrequest.cpp`
- `0x180052a84`: `Failed to remove equal or lower package version %ws`
- `0x180052a0e`: `Failed while adding package %ws since a higher version of the package, %ws, already exists`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MsixPackage::Provisioning::Library::MsixProvisioningRequest::CheckForExistingMainPackageAndRemove(
        MsixPackage::Provisioning::Library::MsixProvisioningRequest *this,
        const char *a2)
{
  int ExistingVersionInRegistryStore; // ebx
  int v6; // eax
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+18h]
  int v8; // [rsp+70h] [rbp+20h] BYREF
  char **v9; // [rsp+80h] [rbp+30h] BYREF
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
        *v9);
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
0x18005294c  mov     [rsp-18h+arg_8], rbx
0x180052951  push    rbp
0x180052952  push    rsi
0x180052953  push    rdi
0x180052954  mov     rbp, rsp
0x180052957  sub     rsp, 50h
0x18005295b  mov     rdi, rdx
0x18005295e  mov     rsi, rcx
0x180052961  mov     [rbp+arg_10], 0
0x180052969  mov     [rbp+arg_0], 0
0x180052970  lea     rax, [rbp+arg_10]
0x180052974  mov     [rbp+var_10], rax
0x180052978  mov     [rbp+var_8], 1
0x18005297c  mov     rcx, [rcx+10h]
0x180052980  lea     rax, [rbp+arg_10]
0x180052984  mov     qword ptr [rsp+50h+var_30], rax; int
0x180052989  lea     r9, [rbp+arg_0]
0x18005298d  xor     r8d, r8d
0x180052990  mov     rcx, [rcx+248h]
0x180052997  call    cs:__imp_FindExistingVersionInRegistryStore
0x18005299e  nop     dword ptr [rax+rax+00h]
0x1800529a3  mov     ebx, eax
0x1800529a5  test    eax, eax
0x1800529a7  jns     short loc_1800529F1
0x1800529a9  mov     rcx, [rbp+18h]; this
0x1800529ad  mov     [rsp+50h+var_28], rdi; char *
0x1800529b2  lea     rax, aFailedToFindAn; "Failed to find an existing version for "...
0x1800529b9  mov     qword ptr [rsp+50h+var_30], rax; int
0x1800529be  mov     r9d, ebx; char *
0x1800529c1  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x1800529c8  mov     edx, 44Eh; void *
0x1800529cd  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x1800529d2  nop
0x1800529d3  cmp     [rbp+arg_10], 0
0x1800529d8  jz      short loc_1800529EA
0x1800529da  lea     rcx, [rbp+arg_10]
0x1800529de  call    cs:__imp_DeletePackageInfo
0x1800529e5  nop     dword ptr [rax+rax+00h]
0x1800529ea  mov     eax, ebx
0x1800529ec  jmp     loc_180052B34
0x1800529f1  mov     ecx, [rbp+arg_0]
0x1800529f4  cmp     ecx, 3
0x1800529f7  jnz     short loc_180052A35
0x1800529f9  mov     rcx, [rbp+18h]; this
0x1800529fd  mov     rax, [rbp+arg_10]
0x180052a01  mov     rdx, [rax]
0x180052a04  mov     [rsp+50h+var_20], rdx
0x180052a09  mov     [rsp+50h+var_28], rdi; char *
0x180052a0e  lea     rax, aFailedWhileAdd_1; "Failed while adding package %ws since a"...
0x180052a15  mov     qword ptr [rsp+50h+var_30], rax; int
0x180052a1a  mov     ebx, 0C1570118h
0x180052a1f  mov     r9d, ebx; char *
0x180052a22  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180052a29  mov     edx, 456h; void *
0x180052a2e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052a33  jmp     short loc_1800529D3
0x180052a35  lea     eax, [rcx-1]
0x180052a38  test    eax, 0FFFFFFFCh
0x180052a3d  jnz     loc_180052B1B
0x180052a43  cmp     ecx, 3
0x180052a46  jz      loc_180052B1B
0x180052a4c  mov     [rbp+arg_18], 0
0x180052a54  lea     r9, [rbp+arg_18]; struct MsixPackage::Provisioning::Library::MsixPackageAdapter **
0x180052a58  mov     r8d, 1; int
0x180052a5e  mov     rdx, [rsi+10h]; struct MsixPackage::Provisioning::Library::MsixProvisioningContext *
0x180052a62  mov     rcx, [rbp+arg_10]
0x180052a66  mov     rcx, [rcx]; unsigned __int16 *
0x180052a69  call    ?CreateForRemove@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@HPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForRemove(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,int,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180052a6e  mov     ebx, eax
0x180052a70  test    eax, eax
0x180052a72  jns     short loc_180052AC0
0x180052a74  mov     rcx, [rbp+18h]; this
0x180052a78  mov     rdx, [rbp+arg_10]
0x180052a7c  mov     r8, [rdx]
0x180052a7f  mov     [rsp+50h+var_28], r8; char *
0x180052a84  lea     rax, aFailedToRemove_8; "Failed to remove equal or lower package"...
0x180052a8b  mov     qword ptr [rsp+50h+var_30], rax; int
0x180052a90  mov     r9d, ebx; char *
0x180052a93  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180052a9a  mov     edx, 462h; void *
0x180052a9f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180052aa4  nop
0x180052aa5  mov     rcx, [rbp+arg_18]
0x180052aa9  test    rcx, rcx
0x180052aac  jz      short loc_180052ABB
0x180052aae  mov     rax, [rcx]
0x180052ab1  mov     rax, [rax+10h]
0x180052ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052aba  nop
0x180052abb  jmp     loc_1800529D3
0x180052ac0  xor     edx, edx; int
0x180052ac2  mov     rcx, [rbp+arg_18]; this
0x180052ac6  call    ?RemovePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJH@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::RemovePackage(int)
0x180052acb  mov     ebx, eax
0x180052acd  test    eax, eax
0x180052acf  jns     short loc_180052B05
0x180052ad1  mov     rcx, [rbp+18h]; this
0x180052ad5  mov     r9d, eax; char *
0x180052ad8  lea     r8, aOnecoreAdminAp_11; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180052adf  mov     edx, 464h; void *
0x180052ae4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052ae9  nop
0x180052aea  mov     rcx, [rbp+arg_18]
0x180052aee  test    rcx, rcx
0x180052af1  jz      short loc_180052B00
0x180052af3  mov     rax, [rcx]
0x180052af6  mov     rax, [rax+10h]
0x180052afa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052aff  nop
0x180052b00  jmp     loc_1800529D3
0x180052b05  mov     rcx, [rbp+arg_18]
0x180052b09  test    rcx, rcx
0x180052b0c  jz      short loc_180052B1B
0x180052b0e  mov     rax, [rcx]
0x180052b11  mov     rax, [rax+10h]
0x180052b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052b1a  nop
0x180052b1b  cmp     [rbp+arg_10], 0
0x180052b20  jz      short loc_180052B32
0x180052b22  lea     rcx, [rbp+arg_10]
0x180052b26  call    cs:__imp_DeletePackageInfo
0x180052b2d  nop     dword ptr [rax+rax+00h]
0x180052b32  xor     eax, eax
0x180052b34  mov     rbx, [rsp+50h+arg_8]
0x180052b39  add     rsp, 50h
0x180052b3d  pop     rdi
0x180052b3e  pop     rsi
0x180052b3f  pop     rbp
0x180052b40  retn
```
