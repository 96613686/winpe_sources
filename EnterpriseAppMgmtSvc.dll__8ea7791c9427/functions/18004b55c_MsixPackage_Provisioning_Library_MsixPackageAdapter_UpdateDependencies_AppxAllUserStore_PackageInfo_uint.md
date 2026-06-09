# MsixPackage::Provisioning::Library::MsixPackageAdapter::UpdateDependencies(AppxAllUserStore::_PackageInfo * *,uint)

- ea: `0x18004b55c`
- end: `0x18004b705`
- name: `?UpdateDependencies@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEAPEAU_PackageInfo@AppxAllUserStore@@I@Z`
- size: `425`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, struct AppxAllUserStore::_PackageInfo **, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x180048b1c`

## callees

- `0x18000cfe8`
- `0x1800390e0`
- `0x180044ecc`
- `0x180048534`
- `0x18004b55c`

## import_xrefs

- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x18004b5f3`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x18004b5f3`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004b6b5`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004b6b5`
- `AppXAllUserStore!UpdateFrameworkPackageInRegistryStore` at `0x18004b5b8`
- `AppXAllUserStore!UpdateFrameworkPackageInRegistryStore` at `0x18004b5b8`

## string_xrefs

- `0x18004b63d`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b677`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b6da`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004b692`: `(hr:0x%x) Updating packages in the registry store to use framework %ws failed`
- `0x18004b62e`: `(hr:0x%x) Removing framework %ws from the registry store failed`

## pseudocode

```c
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::UpdateDependencies(
        MsixPackage::Provisioning::Library::MsixPackageAdapter *this,
        struct AppxAllUserStore::_PackageInfo **a2,
        unsigned int a3)
{
  __int64 v3; // rdi
  unsigned int v4; // r15d
  struct AppxAllUserStore::_PackageInfo **v5; // r12
  MsixPackage::Provisioning::Library::MsixPackageAdapter *v6; // r14
  __int64 v7; // rcx
  struct AppxAllUserStore::_PackageInfo *v8; // rdx
  int updated; // eax
  __int64 v10; // r8
  int v11; // ebx
  __int64 v12; // rcx
  __int64 v13; // rsi
  unsigned __int16 *v14; // r14
  unsigned int v15; // r13d
  unsigned __int64 v16; // r9
  const char *v17; // rcx
  unsigned int v18; // eax
  void *v19; // rdx
  unsigned int v20; // r8d
  int v22; // [rsp+20h] [rbp-38h]
  char *v23; // [rsp+28h] [rbp-30h]
  _QWORD v24[3]; // [rsp+40h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+40h]
  unsigned int v29; // [rsp+B8h] [rbp+60h] BYREF

  v3 = 0;
  v4 = a3;
  v5 = a2;
  v6 = this;
  if ( !a3 )
    return 0;
  do
  {
    v7 = *((_QWORD *)v6 + 2);
    v8 = v5[v3];
    v24[0] = 0;
    v29 = 0;
    updated = UpdateFrameworkPackageInRegistryStore(*(_QWORD *)(v7 + 584), v8, v24, &v29);
    v11 = updated;
    if ( updated < 0 )
    {
      LODWORD(v23) = updated;
      wil::details::in1diag3::Log_HrMsg(
        retaddr,
        (void *)0x2E7,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)updated,
        (int)"(hr:0x%x) Updating packages in the registry store to use framework %ws failed",
        v23);
      v12 = v29;
    }
    else
    {
      v12 = v29;
      v13 = 0;
      if ( v29 )
      {
        do
        {
          LOBYTE(v10) = 1;
          v11 = RemoveStagedPackageFromRegistryStore(
                  *(_QWORD *)(*((_QWORD *)this + 2) + 584LL),
                  *(_QWORD *)(v24[0] + 24 * v13),
                  v10);
          v14 = *(unsigned __int16 **)(v24[0] + 24 * v13);
          if ( v11 < 0 )
          {
            v15 = 737;
            v17 = "(hr:0x%x) Removing framework %ws from the registry store failed";
            v16 = (unsigned int)v11;
          }
          else
          {
            v15 = 733;
            v16 = (unsigned int)MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(this, v14);
            v17 = "(hr:0x%x) Destaging framework %ws failed";
          }
          LODWORD(v23) = v11;
          wil::details::in1diag3::Log_HrMsg(
            retaddr,
            (void *)v15,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)v16,
            (int)v17,
            v23,
            v14);
          v12 = v29;
          v13 = (unsigned int)(v13 + 1);
        }
        while ( (unsigned int)v13 < v29 );
        v4 = a3;
        v6 = this;
        v5 = a2;
      }
    }
    if ( v24[0] )
    {
      v18 = DeleteAllPackagesFromPackageArray(v12);
      wil::details::in1diag3::Log_Hr(retaddr, v19, v20, (const char *)v18, v22);
    }
    v3 = (unsigned int)(v3 + 1);
  }
  while ( (unsigned int)v3 < v4 );
  if ( v11 >= 0 )
    return 0;
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x2F0,
    (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
    (const char *)(unsigned int)v11,
    v22);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18004b55c  mov     [rsp-40h+arg_10], r8d
0x18004b561  mov     [rsp-40h+arg_8], rdx
0x18004b566  mov     [rsp-40h+arg_0], rcx
0x18004b56b  push    rbp
0x18004b56c  push    rbx
0x18004b56d  push    rsi
0x18004b56e  push    rdi
0x18004b56f  push    r12
0x18004b571  push    r13
0x18004b573  push    r14
0x18004b575  push    r15
0x18004b577  mov     rbp, rsp
0x18004b57a  sub     rsp, 58h
0x18004b57e  xor     edi, edi
0x18004b580  mov     r15d, r8d
0x18004b583  mov     r12, rdx
0x18004b586  mov     r14, rcx
0x18004b589  test    r8d, r8d
0x18004b58c  jz      loc_18004B6F2
0x18004b592  mov     rcx, [r14+10h]
0x18004b596  lea     r9, [rbp+arg_18]
0x18004b59a  mov     rdx, [r12+rdi*8]
0x18004b59e  lea     r8, [rbp+var_18]
0x18004b5a2  mov     [rbp+var_18], 0
0x18004b5aa  mov     [rbp+arg_18], 0
0x18004b5b1  mov     rcx, [rcx+248h]
0x18004b5b8  call    cs:__imp_UpdateFrameworkPackageInRegistryStore
0x18004b5be  mov     ebx, eax
0x18004b5c0  test    eax, eax
0x18004b5c2  js      loc_18004B673
0x18004b5c8  mov     ecx, [rbp+arg_18]
0x18004b5cb  xor     esi, esi
0x18004b5cd  test    ecx, ecx
0x18004b5cf  jz      loc_18004B6AA
0x18004b5d5  mov     r15, [rbp+arg_0]
0x18004b5d9  mov     rcx, [r15+10h]
0x18004b5dd  lea     r14, [rsi+rsi*2]
0x18004b5e1  mov     rdx, [rbp+var_18]
0x18004b5e5  mov     r8b, 1
0x18004b5e8  mov     rcx, [rcx+248h]
0x18004b5ef  mov     rdx, [rdx+r14*8]
0x18004b5f3  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x18004b5f9  mov     r12, [rbp+40h]
0x18004b5fd  mov     ebx, eax
0x18004b5ff  test    eax, eax
0x18004b601  mov     rax, [rbp+var_18]
0x18004b605  mov     r14, [rax+r14*8]
0x18004b609  js      short loc_18004B628
0x18004b60b  mov     rdx, r14; unsigned __int16 *
0x18004b60e  mov     rcx, r15; this
0x18004b611  mov     r13d, 2DDh
0x18004b617  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x18004b61c  mov     r9d, eax
0x18004b61f  lea     rcx, aHr0xXDestaging; "(hr:0x%x) Destaging framework %ws faile"...
0x18004b626  jmp     short loc_18004B638
0x18004b628  mov     r13d, 2E1h
0x18004b62e  lea     rcx, aHr0xXRemovingF; "(hr:0x%x) Removing framework %ws from t"...
0x18004b635  mov     r9d, ebx; char *
0x18004b638  mov     [rsp+58h+var_28], r14
0x18004b63d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b644  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x18004b648  mov     edx, r13d; void *
0x18004b64b  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18004b650  mov     rcx, r12; this
0x18004b653  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b658  mov     ecx, [rbp+arg_18]
0x18004b65b  inc     esi
0x18004b65d  cmp     esi, ecx
0x18004b65f  jb      loc_18004B5D9
0x18004b665  mov     r15d, [rbp+arg_10]
0x18004b669  mov     r14, [rbp+arg_0]
0x18004b66d  mov     r12, [rbp+arg_8]
0x18004b671  jmp     short loc_18004B6AA
0x18004b673  mov     rax, [r12+rdi*8]
0x18004b677  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b67e  mov     rcx, [rbp+40h]; this
0x18004b682  mov     r9d, ebx; char *
0x18004b685  mov     edx, 2E7h; void *
0x18004b68a  mov     rax, [rax]
0x18004b68d  mov     [rsp+58h+var_28], rax
0x18004b692  lea     rax, aHr0xXUpdatingP; "(hr:0x%x) Updating packages in the regi"...
0x18004b699  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x18004b69d  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004b6a2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004b6a7  mov     ecx, [rbp+arg_18]
0x18004b6aa  cmp     [rbp+var_18], 0
0x18004b6af  jz      short loc_18004B6C7
0x18004b6b1  lea     rdx, [rbp+var_18]
0x18004b6b5  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x18004b6bb  mov     rcx, [rbp+40h]; this
0x18004b6bf  mov     r9d, eax; char *
0x18004b6c2  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004b6c7  inc     edi
0x18004b6c9  cmp     edi, r15d
0x18004b6cc  jb      loc_18004B592
0x18004b6d2  test    ebx, ebx
0x18004b6d4  jns     short loc_18004B6F2
0x18004b6d6  mov     rcx, [rbp+40h]; this
0x18004b6da  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004b6e1  mov     r9d, ebx; char *
0x18004b6e4  mov     edx, 2F0h; void *
0x18004b6e9  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004b6ee  mov     eax, ebx
0x18004b6f0  jmp     short loc_18004B6F4
0x18004b6f2  xor     eax, eax
0x18004b6f4  add     rsp, 58h
0x18004b6f8  pop     r15
0x18004b6fa  pop     r14
0x18004b6fc  pop     r13
0x18004b6fe  pop     r12
0x18004b700  pop     rdi
0x18004b701  pop     rsi
0x18004b702  pop     rbx
0x18004b703  pop     rbp
0x18004b704  retn
```
