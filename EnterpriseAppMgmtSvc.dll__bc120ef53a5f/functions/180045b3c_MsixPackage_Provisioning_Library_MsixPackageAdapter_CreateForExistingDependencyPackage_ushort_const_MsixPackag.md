# MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)

- ea: `0x180045b3c`
- end: `0x180045ed0`
- name: `?CreateForExistingDependencyPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z`
- size: `916`
- prototype: `__int64 __fastcall(char *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, bool *, struct MsixPackage::Provisioning::Library::MsixPackageAdapter **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x18004cbe4`
- `0x18005207c`
- `0x1800524d0`

## callees

- `0x18001d160`
- `0x18003d4ec`
- `0x180044670`
- `0x180045b3c`
- `0x180045ed8`
- `0x180070010`

## import_xrefs

- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045c51`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045d19`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045db8`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045e7d`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045c51`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045d19`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045db8`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180045e7d`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045c77`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045d3f`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045dde`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045ea3`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045c77`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045d3f`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045dde`
- `AppXAllUserStore!DeletePackageInfo` at `0x180045ea3`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x180045c07`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x180045c07`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180045cc0`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180045cc0`

## string_xrefs

- `0x180045b8f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045c32`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045cfa`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045d82`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180045d73`: `Failed to create package adapter.`
- `0x180045c23`: `Failed to find existing version in registry for framework '%ws'.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(
        char *a1,
        struct MsixPackage::Provisioning::Library::MsixProvisioningContext *a2,
        bool *a3,
        struct MsixPackage::Provisioning::Library::MsixPackageAdapter **a4)
{
  bool *v5; // r15
  int v8; // ebx
  __int64 result; // rax
  int ExistingVersionInRegistryStore; // eax
  __int64 v11; // r8
  const char *v12; // r9
  unsigned int v13; // esi
  int v14; // ebx
  int v15; // ebx
  __int64 v16; // rbx
  char *v17; // rdx
  __int64 v18; // rdi
  __int64 v19; // r8
  char *v20; // rdx
  char *v21; // [rsp+28h] [rbp-50h]
  _QWORD v22[3]; // [rsp+30h] [rbp-48h] BYREF
  char v23; // [rsp+48h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+0h]
  int v25; // [rsp+88h] [rbp+10h] BYREF
  const char **v26; // [rsp+90h] [rbp+18h] BYREF
  __int64 v27; // [rsp+98h] [rbp+20h] BYREF

  v5 = a3;
  *a4 = 0;
  *a3 = 0;
  if ( *((_DWORD *)a2 + 150) )
  {
    v8 = MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackageOnline(
           (const unsigned __int16 *)a1,
           a2,
           a3,
           a4);
    if ( v8 >= 0 )
      return 0;
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xB1,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v8,
      (int)"Failed to find existing version online for framework '%ws'.",
      a1);
    return (unsigned int)v8;
  }
  v26 = 0;
  v27 = 0;
  v22[1] = &v27;
  v22[2] = &v26;
  v23 = 1;
  v25 = 0;
  LOBYTE(a3) = 1;
  ExistingVersionInRegistryStore = FindExistingVersionInRegistryStore(*((_QWORD *)a2 + 73), a1, a3, &v25);
  v13 = ExistingVersionInRegistryStore;
  if ( ExistingVersionInRegistryStore < 0 )
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0xD2,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)ExistingVersionInRegistryStore,
      (int)"Failed to find existing version in registry for framework '%ws'.",
      a1);
    if ( v27 )
    {
      RollbackTakeOwnershipSession(v27);
      v27 = 0;
    }
    if ( v26 )
      DeletePackageInfo(&v26);
    return v13;
  }
  try
  {
    if ( (unsigned int)(v25 - 2) <= 1 )
    {
      v22[0] = 0;
      v15 = MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(
              a2,
              v22);
      if ( v15 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xDB,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v15,
          (int)"Failed to create package adapter.",
          v21);
        if ( v22[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v22[0] + 16LL))(v22[0]);
        if ( v27 )
        {
          ((void (*)(void))RollbackTakeOwnershipSession)();
          v27 = 0;
        }
        if ( v26 )
          DeletePackageInfo(&v26);
        return (unsigned int)v15;
      }
      v16 = v22[0];
      *(_DWORD *)(v22[0] + 24LL) = 3;
      *(_QWORD *)(v16 + 28) = 1;
      *(_DWORD *)(v16 + 36) = 3;
      v17 = (char *)*v26;
      v18 = -1;
      if ( *(_WORD *)*v26 )
      {
        v19 = -1;
        do
          ++v19;
        while ( *(_WORD *)&v17[2 * v19] );
      }
      std::wstring::assign((void *)(v16 + 48), v17);
      v20 = (char *)v26[1];
      if ( *(_WORD *)v20 )
      {
        do
          ++v18;
        while ( *(_WORD *)&v20[2 * v18] );
      }
      std::wstring::assign((void *)(v16 + 144), v20);
      *v5 = 1;
      *a4 = (struct MsixPackage::Provisioning::Library::MsixPackageAdapter *)v16;
    }
    else if ( v25 == 1 || v25 == 4 )
    {
      LOBYTE(v11) = 1;
      v14 = RemoveStagedPackageFromRegistryStore(*((_QWORD *)a2 + 73), *v26, v11);
      if ( v14 < 0 )
      {
        wil::details::in1diag3::Return_HrMsg(
          retaddr,
          (void *)0xF2,
          (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
          (const char *)(unsigned int)v14,
          (int)"Failed to deregister staged package'%ws'",
          *v26);
        if ( v27 )
        {
          RollbackTakeOwnershipSession(v27);
          v27 = 0;
        }
        if ( v26 )
          DeletePackageInfo(&v26);
        return (unsigned int)v14;
      }
    }
    if ( v27 )
    {
      RollbackTakeOwnershipSession(v27);
      v27 = 0;
    }
    if ( v26 )
      DeletePackageInfo(&v26);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xF7,
                           (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180045b3c  mov     [rsp+arg_0], rbx
0x180045b41  push    rsi
0x180045b42  push    rdi
0x180045b43  push    r12
0x180045b45  push    r14
0x180045b47  push    r15
0x180045b49  sub     rsp, 50h
0x180045b4d  mov     r14, r9
0x180045b50  mov     r15, r8
0x180045b53  mov     rbx, rdx
0x180045b56  mov     rdi, rcx
0x180045b59  xor     r12d, r12d
0x180045b5c  mov     [r9], r12
0x180045b5f  mov     [r8], r12b
0x180045b62  cmp     [rdx+258h], r12d
0x180045b69  jz      short loc_180045BAE
0x180045b6b  call    ?CreateForExistingDependencyPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackageOnline(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180045b70  mov     ebx, eax
0x180045b72  test    eax, eax
0x180045b74  jns     short loc_180045BA7
0x180045b76  mov     rcx, [rsp+78h]; this
0x180045b7b  mov     [rsp+78h+var_50], rdi; char *
0x180045b80  lea     rax, aFailedToFindEx_0; "Failed to find existing version online "...
0x180045b87  mov     qword ptr [rsp+78h+var_58], rax; int
0x180045b8c  mov     r9d, ebx; char *
0x180045b8f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045b96  mov     edx, 0B1h; void *
0x180045b9b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045ba0  mov     eax, ebx
0x180045ba2  jmp     loc_180045EBA
0x180045ba7  xor     eax, eax
0x180045ba9  jmp     loc_180045EBA
0x180045bae  mov     [rsp+78h+arg_10], r12
0x180045bb6  mov     [rsp+78h+arg_18], r12
0x180045bbe  lea     rax, [rsp+78h+arg_18]
0x180045bc6  mov     [rsp+78h+var_40], rax
0x180045bcb  lea     rax, [rsp+78h+arg_10]
0x180045bd3  mov     [rsp+78h+var_38], rax
0x180045bd8  mov     [rsp+78h+var_30], 1
0x180045bdd  mov     [rsp+78h+arg_8], r12d
0x180045be5  lea     rax, [rsp+78h+arg_10]
0x180045bed  mov     qword ptr [rsp+78h+var_58], rax
0x180045bf2  lea     r9, [rsp+78h+arg_8]
0x180045bfa  mov     r8b, 1
0x180045bfd  mov     rdx, rdi
0x180045c00  mov     rcx, [rbx+248h]
0x180045c07  call    cs:__imp_FindExistingVersionInRegistryStore
0x180045c0e  nop     dword ptr [rax+rax+00h]
0x180045c13  mov     esi, eax
0x180045c15  test    eax, eax
0x180045c17  jns     short loc_180045C8A
0x180045c19  mov     rcx, [rsp+78h]; this
0x180045c1e  mov     [rsp+78h+var_50], rdi; char *
0x180045c23  lea     rax, aFailedToFindEx_1; "Failed to find existing version in regi"...
0x180045c2a  mov     qword ptr [rsp+78h+var_58], rax; int
0x180045c2f  mov     r9d, esi; char *
0x180045c32  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045c39  mov     edx, 0D2h; void *
0x180045c3e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045c43  nop
0x180045c44  mov     rcx, [rsp+78h+arg_18]
0x180045c4c  test    rcx, rcx
0x180045c4f  jz      short loc_180045C65
0x180045c51  call    cs:__imp_RollbackTakeOwnershipSession
0x180045c58  nop     dword ptr [rax+rax+00h]
0x180045c5d  mov     [rsp+78h+arg_18], r12
0x180045c65  cmp     [rsp+78h+arg_10], r12
0x180045c6d  jz      short loc_180045C83
0x180045c6f  lea     rcx, [rsp+78h+arg_10]
0x180045c77  call    cs:__imp_DeletePackageInfo
0x180045c7e  nop     dword ptr [rax+rax+00h]
0x180045c83  mov     eax, esi
0x180045c85  jmp     loc_180045EBA
0x180045c8a  mov     ecx, [rsp+78h+arg_8]
0x180045c91  lea     eax, [rcx-2]
0x180045c94  cmp     eax, 1
0x180045c97  jbe     loc_180045D52
0x180045c9d  cmp     ecx, 1
0x180045ca0  jz      short loc_180045CAB
0x180045ca2  cmp     ecx, 4
0x180045ca5  jnz     loc_180045E70
0x180045cab  mov     r8b, 1
0x180045cae  mov     rdx, [rsp+78h+arg_10]
0x180045cb6  mov     rdx, [rdx]
0x180045cb9  mov     rcx, [rbx+248h]
0x180045cc0  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x180045cc7  nop     dword ptr [rax+rax+00h]
0x180045ccc  mov     ebx, eax
0x180045cce  test    eax, eax
0x180045cd0  jns     loc_180045E70
0x180045cd6  mov     rcx, [rsp+78h]; this
0x180045cdb  mov     rdx, [rsp+78h+arg_10]
0x180045ce3  mov     r8, [rdx]
0x180045ce6  mov     [rsp+78h+var_50], r8; char *
0x180045ceb  lea     rax, aFailedToDeregi_1; "Failed to deregister staged package'%ws"...
0x180045cf2  mov     qword ptr [rsp+78h+var_58], rax; int
0x180045cf7  mov     r9d, ebx; char *
0x180045cfa  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045d01  mov     edx, 0F2h; void *
0x180045d06  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045d0b  nop
0x180045d0c  mov     rcx, [rsp+78h+arg_18]
0x180045d14  test    rcx, rcx
0x180045d17  jz      short loc_180045D2D
0x180045d19  call    cs:__imp_RollbackTakeOwnershipSession
0x180045d20  nop     dword ptr [rax+rax+00h]
0x180045d25  mov     [rsp+78h+arg_18], r12
0x180045d2d  cmp     [rsp+78h+arg_10], r12
0x180045d35  jz      short loc_180045D4B
0x180045d37  lea     rcx, [rsp+78h+arg_10]
0x180045d3f  call    cs:__imp_DeletePackageInfo
0x180045d46  nop     dword ptr [rax+rax+00h]
0x180045d4b  mov     eax, ebx
0x180045d4d  jmp     loc_180045EBA
0x180045d52  mov     [rsp+78h+var_48], r12
0x180045d57  lea     rdx, [rsp+78h+var_48]
0x180045d5c  mov     rcx, rbx
0x180045d5f  call    ??$Make@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixPackageAdapter@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180045d64  mov     ebx, eax
0x180045d66  test    eax, eax
0x180045d68  jns     loc_180045DF1
0x180045d6e  mov     rcx, [rsp+78h]; this
0x180045d73  lea     rax, aFailedToCreate_22; "Failed to create package adapter."
0x180045d7a  mov     qword ptr [rsp+78h+var_58], rax; int
0x180045d7f  mov     r9d, ebx; char *
0x180045d82  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180045d89  mov     edx, 0DBh; void *
0x180045d8e  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180045d93  nop
0x180045d94  mov     rcx, [rsp+78h+var_48]
0x180045d99  test    rcx, rcx
0x180045d9c  jz      short loc_180045DAB
0x180045d9e  mov     rax, [rcx]
0x180045da1  mov     rax, [rax+10h]
0x180045da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045daa  nop
0x180045dab  mov     rcx, [rsp+78h+arg_18]
0x180045db3  test    rcx, rcx
0x180045db6  jz      short loc_180045DCC
0x180045db8  call    cs:__imp_RollbackTakeOwnershipSession
0x180045dbf  nop     dword ptr [rax+rax+00h]
0x180045dc4  mov     [rsp+78h+arg_18], r12
0x180045dcc  cmp     [rsp+78h+arg_10], r12
0x180045dd4  jz      short loc_180045DEA
0x180045dd6  lea     rcx, [rsp+78h+arg_10]
0x180045dde  call    cs:__imp_DeletePackageInfo
0x180045de5  nop     dword ptr [rax+rax+00h]
0x180045dea  mov     eax, ebx
0x180045dec  jmp     loc_180045EBA
0x180045df1  mov     eax, 3
0x180045df6  mov     rbx, [rsp+78h+var_48]
0x180045dfb  mov     [rbx+18h], eax
0x180045dfe  mov     qword ptr [rbx+1Ch], 1
0x180045e06  mov     [rbx+24h], eax
0x180045e09  lea     rcx, [rbx+30h]; void *
0x180045e0d  mov     rax, [rsp+78h+arg_10]
0x180045e15  mov     rdx, [rax]; Src
0x180045e18  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180045e1c  cmp     [rdx], r12w
0x180045e20  jnz     short loc_180045E27
0x180045e22  mov     r8, r12
0x180045e25  jmp     short loc_180045E34
0x180045e27  mov     r8, rdi
0x180045e2a  inc     r8
0x180045e2d  cmp     [rdx+r8*2], r12w
0x180045e32  jnz     short loc_180045E2A
0x180045e34  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180045e39  lea     rcx, [rbx+90h]; void *
0x180045e40  mov     rax, [rsp+78h+arg_10]
0x180045e48  mov     rdx, [rax+8]; Src
0x180045e4c  cmp     [rdx], r12w
0x180045e50  jnz     short loc_180045E57
0x180045e52  mov     rdi, r12
0x180045e55  jmp     short loc_180045E61
0x180045e57  inc     rdi
0x180045e5a  cmp     [rdx+rdi*2], r12w
0x180045e5f  jnz     short loc_180045E57
0x180045e61  mov     r8, rdi
0x180045e64  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180045e69  mov     byte ptr [r15], 1
0x180045e6d  mov     [r14], rbx
0x180045e70  mov     rcx, [rsp+78h+arg_18]
0x180045e78  test    rcx, rcx
0x180045e7b  jz      short loc_180045E91
0x180045e7d  call    cs:__imp_RollbackTakeOwnershipSession
0x180045e84  nop     dword ptr [rax+rax+00h]
0x180045e89  mov     [rsp+78h+arg_18], r12
0x180045e91  cmp     [rsp+78h+arg_10], r12
0x180045e99  jz      short loc_180045EAF
0x180045e9b  lea     rcx, [rsp+78h+arg_10]
0x180045ea3  call    cs:__imp_DeletePackageInfo
0x180045eaa  nop     dword ptr [rax+rax+00h]
0x180045eaf  xor     eax, eax
0x180045eb1  jmp     short loc_180045EBA
0x180045eb3  mov     eax, [rsp+78h+arg_8]
0x180045eba  mov     rbx, [rsp+78h+arg_0]
0x180045ec2  add     rsp, 50h
0x180045ec6  pop     r15
0x180045ec8  pop     r14
0x180045eca  pop     r12
0x180045ecc  pop     rdi
0x180045ecd  pop     rsi
0x180045ece  retn
```
