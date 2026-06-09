# MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackage(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)

- ea: `0x180041e2c`
- end: `0x180042180`
- name: `?CreateForExistingDependencyPackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z`
- size: `852`
- prototype: `__int64 __fastcall(char *, struct MsixPackage::Provisioning::Library::MsixProvisioningContext *, bool *, struct MsixPackage::Provisioning::Library::MsixPackageAdapter **)`
- caller_count: `3`
- callee_count: `6`
- tags: `registry_config, installer_update`

## callers

- `0x180048b1c`
- `0x18004ddb4`
- `0x18004e1fc`

## callees

- `0x18001bf0c`
- `0x180039e9c`
- `0x180040a48`
- `0x180041e2c`
- `0x180042188`
- `0x18006a010`

## import_xrefs

- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180041f3b`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180041ff1`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180042080`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180042139`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180041f3b`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180041ff1`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180042080`
- `AppXAllUserStore!RollbackTakeOwnershipSession` at `0x180042139`
- `AppXAllUserStore!DeletePackageInfo` at `0x180041f5b`
- `AppXAllUserStore!DeletePackageInfo` at `0x180042011`
- `AppXAllUserStore!DeletePackageInfo` at `0x1800420a0`
- `AppXAllUserStore!DeletePackageInfo` at `0x180042159`
- `AppXAllUserStore!DeletePackageInfo` at `0x180041f5b`
- `AppXAllUserStore!DeletePackageInfo` at `0x180042011`
- `AppXAllUserStore!DeletePackageInfo` at `0x1800420a0`
- `AppXAllUserStore!DeletePackageInfo` at `0x180042159`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x180041ef7`
- `AppXAllUserStore!FindExistingVersionInRegistryStore` at `0x180041ef7`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180041f9e`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x180041f9e`

## string_xrefs

- `0x180041e7f`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180041f1c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180041fd2`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004204a`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x180041f0d`: `Failed to find existing version in registry for framework '%ws'.`
- `0x18004203b`: `Failed to create package adapter.`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  unsigned __int64 v18; // rdi
  unsigned __int64 v19; // r8
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
              (__int64)a2,
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
          RollbackTakeOwnershipSession(v27);
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
      else
      {
        v19 = 0;
      }
      std::wstring::assign((_QWORD *)(v16 + 48), v17, v19);
      v20 = (char *)v26[1];
      if ( *(_WORD *)v20 )
      {
        do
          ++v18;
        while ( *(_WORD *)&v20[2 * v18] );
      }
      else
      {
        v18 = 0;
      }
      std::wstring::assign((_QWORD *)(v16 + 144), v20, v18);
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
0x180041e2c  mov     [rsp+arg_0], rbx
0x180041e31  push    rsi
0x180041e32  push    rdi
0x180041e33  push    r12
0x180041e35  push    r14
0x180041e37  push    r15
0x180041e39  sub     rsp, 50h
0x180041e3d  mov     r14, r9
0x180041e40  mov     r15, r8
0x180041e43  mov     rbx, rdx
0x180041e46  mov     rdi, rcx
0x180041e49  xor     r12d, r12d
0x180041e4c  mov     [r9], r12
0x180041e4f  mov     [r8], r12b
0x180041e52  cmp     [rdx+258h], r12d
0x180041e59  jz      short loc_180041E9E
0x180041e5b  call    ?CreateForExistingDependencyPackageOnline@MsixPackageAdapter@Library@Provisioning@MsixPackage@@SAJPEBGPEAVMsixProvisioningContext@234@AEA_NPEAPEAV1234@@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::CreateForExistingDependencyPackageOnline(ushort const *,MsixPackage::Provisioning::Library::MsixProvisioningContext *,bool &,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180041e60  mov     ebx, eax
0x180041e62  test    eax, eax
0x180041e64  jns     short loc_180041E97
0x180041e66  mov     rcx, [rsp+78h]; this
0x180041e6b  mov     [rsp+78h+var_50], rdi; char *
0x180041e70  lea     rax, aFailedToFindEx_0; "Failed to find existing version online "...
0x180041e77  mov     qword ptr [rsp+78h+var_58], rax; int
0x180041e7c  mov     r9d, ebx; char *
0x180041e7f  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041e86  mov     edx, 0B1h; void *
0x180041e8b  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041e90  mov     eax, ebx
0x180041e92  jmp     loc_18004216A
0x180041e97  xor     eax, eax
0x180041e99  jmp     loc_18004216A
0x180041e9e  mov     [rsp+78h+arg_10], r12
0x180041ea6  mov     [rsp+78h+arg_18], r12
0x180041eae  lea     rax, [rsp+78h+arg_18]
0x180041eb6  mov     [rsp+78h+var_40], rax
0x180041ebb  lea     rax, [rsp+78h+arg_10]
0x180041ec3  mov     [rsp+78h+var_38], rax
0x180041ec8  mov     [rsp+78h+var_30], 1
0x180041ecd  mov     [rsp+78h+arg_8], r12d
0x180041ed5  lea     rax, [rsp+78h+arg_10]
0x180041edd  mov     qword ptr [rsp+78h+var_58], rax
0x180041ee2  lea     r9, [rsp+78h+arg_8]
0x180041eea  mov     r8b, 1
0x180041eed  mov     rdx, rdi
0x180041ef0  mov     rcx, [rbx+248h]
0x180041ef7  call    cs:__imp_FindExistingVersionInRegistryStore
0x180041efd  mov     esi, eax
0x180041eff  test    eax, eax
0x180041f01  jns     short loc_180041F68
0x180041f03  mov     rcx, [rsp+78h]; this
0x180041f08  mov     [rsp+78h+var_50], rdi; char *
0x180041f0d  lea     rax, aFailedToFindEx_1; "Failed to find existing version in regi"...
0x180041f14  mov     qword ptr [rsp+78h+var_58], rax; int
0x180041f19  mov     r9d, esi; char *
0x180041f1c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041f23  mov     edx, 0D2h; void *
0x180041f28  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041f2d  nop
0x180041f2e  mov     rcx, [rsp+78h+arg_18]
0x180041f36  test    rcx, rcx
0x180041f39  jz      short loc_180041F49
0x180041f3b  call    cs:__imp_RollbackTakeOwnershipSession
0x180041f41  mov     [rsp+78h+arg_18], r12
0x180041f49  cmp     [rsp+78h+arg_10], r12
0x180041f51  jz      short loc_180041F61
0x180041f53  lea     rcx, [rsp+78h+arg_10]
0x180041f5b  call    cs:__imp_DeletePackageInfo
0x180041f61  mov     eax, esi
0x180041f63  jmp     loc_18004216A
0x180041f68  mov     ecx, [rsp+78h+arg_8]
0x180041f6f  lea     eax, [rcx-2]
0x180041f72  cmp     eax, 1
0x180041f75  jbe     loc_18004201E
0x180041f7b  cmp     ecx, 1
0x180041f7e  jz      short loc_180041F89
0x180041f80  cmp     ecx, 4
0x180041f83  jnz     loc_18004212C
0x180041f89  mov     r8b, 1
0x180041f8c  mov     rdx, [rsp+78h+arg_10]
0x180041f94  mov     rdx, [rdx]
0x180041f97  mov     rcx, [rbx+248h]
0x180041f9e  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x180041fa4  mov     ebx, eax
0x180041fa6  test    eax, eax
0x180041fa8  jns     loc_18004212C
0x180041fae  mov     rcx, [rsp+78h]; this
0x180041fb3  mov     rdx, [rsp+78h+arg_10]
0x180041fbb  mov     r8, [rdx]
0x180041fbe  mov     [rsp+78h+var_50], r8; char *
0x180041fc3  lea     rax, aFailedToDeregi_1; "Failed to deregister staged package'%ws"...
0x180041fca  mov     qword ptr [rsp+78h+var_58], rax; int
0x180041fcf  mov     r9d, ebx; char *
0x180041fd2  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180041fd9  mov     edx, 0F2h; void *
0x180041fde  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x180041fe3  nop
0x180041fe4  mov     rcx, [rsp+78h+arg_18]
0x180041fec  test    rcx, rcx
0x180041fef  jz      short loc_180041FFF
0x180041ff1  call    cs:__imp_RollbackTakeOwnershipSession
0x180041ff7  mov     [rsp+78h+arg_18], r12
0x180041fff  cmp     [rsp+78h+arg_10], r12
0x180042007  jz      short loc_180042017
0x180042009  lea     rcx, [rsp+78h+arg_10]
0x180042011  call    cs:__imp_DeletePackageInfo
0x180042017  mov     eax, ebx
0x180042019  jmp     loc_18004216A
0x18004201e  mov     [rsp+78h+var_48], r12
0x180042023  lea     rdx, [rsp+78h+var_48]
0x180042028  mov     rcx, rbx
0x18004202b  call    ??$Make@VMsixPackageAdapter@Library@Provisioning@MsixPackage@@@MsixAdapterBase@Library@Provisioning@MsixPackage@@SAJPEAVMsixProvisioningContext@123@PEAPEAVMsixPackageAdapter@123@@Z; MsixPackage::Provisioning::Library::MsixAdapterBase::Make<MsixPackage::Provisioning::Library::MsixPackageAdapter>(MsixPackage::Provisioning::Library::MsixProvisioningContext *,MsixPackage::Provisioning::Library::MsixPackageAdapter * *)
0x180042030  mov     ebx, eax
0x180042032  test    eax, eax
0x180042034  jns     short loc_1800420AD
0x180042036  mov     rcx, [rsp+78h]; this
0x18004203b  lea     rax, aFailedToCreate_22; "Failed to create package adapter."
0x180042042  mov     qword ptr [rsp+78h+var_58], rax; int
0x180042047  mov     r9d, ebx; char *
0x18004204a  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x180042051  mov     edx, 0DBh; void *
0x180042056  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004205b  nop
0x18004205c  mov     rcx, [rsp+78h+var_48]
0x180042061  test    rcx, rcx
0x180042064  jz      short loc_180042073
0x180042066  mov     rax, [rcx]
0x180042069  mov     rax, [rax+10h]
0x18004206d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042072  nop
0x180042073  mov     rcx, [rsp+78h+arg_18]
0x18004207b  test    rcx, rcx
0x18004207e  jz      short loc_18004208E
0x180042080  call    cs:__imp_RollbackTakeOwnershipSession
0x180042086  mov     [rsp+78h+arg_18], r12
0x18004208e  cmp     [rsp+78h+arg_10], r12
0x180042096  jz      short loc_1800420A6
0x180042098  lea     rcx, [rsp+78h+arg_10]
0x1800420a0  call    cs:__imp_DeletePackageInfo
0x1800420a6  mov     eax, ebx
0x1800420a8  jmp     loc_18004216A
0x1800420ad  mov     eax, 3
0x1800420b2  mov     rbx, [rsp+78h+var_48]
0x1800420b7  mov     [rbx+18h], eax
0x1800420ba  mov     qword ptr [rbx+1Ch], 1
0x1800420c2  mov     [rbx+24h], eax
0x1800420c5  lea     rcx, [rbx+30h]; void *
0x1800420c9  mov     rax, [rsp+78h+arg_10]
0x1800420d1  mov     rdx, [rax]; Src
0x1800420d4  or      rdi, 0FFFFFFFFFFFFFFFFh
0x1800420d8  cmp     [rdx], r12w
0x1800420dc  jnz     short loc_1800420E3
0x1800420de  mov     r8, r12
0x1800420e1  jmp     short loc_1800420F0
0x1800420e3  mov     r8, rdi
0x1800420e6  inc     r8
0x1800420e9  cmp     [rdx+r8*2], r12w
0x1800420ee  jnz     short loc_1800420E6
0x1800420f0  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x1800420f5  lea     rcx, [rbx+90h]; void *
0x1800420fc  mov     rax, [rsp+78h+arg_10]
0x180042104  mov     rdx, [rax+8]; Src
0x180042108  cmp     [rdx], r12w
0x18004210c  jnz     short loc_180042113
0x18004210e  mov     rdi, r12
0x180042111  jmp     short loc_18004211D
0x180042113  inc     rdi
0x180042116  cmp     [rdx+rdi*2], r12w
0x18004211b  jnz     short loc_180042113
0x18004211d  mov     r8, rdi
0x180042120  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x180042125  mov     byte ptr [r15], 1
0x180042129  mov     [r14], rbx
0x18004212c  mov     rcx, [rsp+78h+arg_18]
0x180042134  test    rcx, rcx
0x180042137  jz      short loc_180042147
0x180042139  call    cs:__imp_RollbackTakeOwnershipSession
0x18004213f  mov     [rsp+78h+arg_18], r12
0x180042147  cmp     [rsp+78h+arg_10], r12
0x18004214f  jz      short loc_18004215F
0x180042151  lea     rcx, [rsp+78h+arg_10]
0x180042159  call    cs:__imp_DeletePackageInfo
0x18004215f  xor     eax, eax
0x180042161  jmp     short loc_18004216A
0x180042163  mov     eax, [rsp+78h+arg_8]
0x18004216a  mov     rbx, [rsp+78h+arg_0]
0x180042172  add     rsp, 50h
0x180042176  pop     r15
0x180042178  pop     r14
0x18004217a  pop     r12
0x18004217c  pop     rdi
0x18004217d  pop     rsi
0x18004217e  retn
```
