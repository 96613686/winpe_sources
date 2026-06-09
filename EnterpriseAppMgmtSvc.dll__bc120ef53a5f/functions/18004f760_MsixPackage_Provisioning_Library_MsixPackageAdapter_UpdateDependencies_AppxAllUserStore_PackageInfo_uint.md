# MsixPackage::Provisioning::Library::MsixPackageAdapter::UpdateDependencies(AppxAllUserStore::_PackageInfo * *,uint)

- ea: `0x18004f760`
- end: `0x18004f91c`
- name: `?UpdateDependencies@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJPEAPEAU_PackageInfo@AppxAllUserStore@@I@Z`
- size: `444`
- prototype: `__int64 __fastcall(MsixPackage::Provisioning::Library::MsixPackageAdapter *__hidden this, struct AppxAllUserStore::_PackageInfo **, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, installer_update`

## callers

- `0x18004cbe4`

## callees

- `0x18000d3dc`
- `0x18003c690`
- `0x180048dec`
- `0x18004c5e8`
- `0x18004f760`

## import_xrefs

- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x18004f7fd`
- `AppXAllUserStore!RemoveStagedPackageFromRegistryStore` at `0x18004f7fd`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004f8c5`
- `AppXAllUserStore!DeleteAllPackagesFromPackageArray` at `0x18004f8c5`
- `AppXAllUserStore!UpdateFrameworkPackageInRegistryStore` at `0x18004f7bc`
- `AppXAllUserStore!UpdateFrameworkPackageInRegistryStore` at `0x18004f7bc`

## string_xrefs

- `0x18004f84d`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f887`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f8f0`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004f83e`: `(hr:0x%x) Removing framework %ws from the registry store failed`
- `0x18004f8a2`: `(hr:0x%x) Updating packages in the registry store to use framework %ws failed`

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
  const unsigned __int16 *v14; // r14
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
          v14 = *(const unsigned __int16 **)(v24[0] + 24 * v13);
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
0x18004f760  mov     [rsp-40h+arg_10], r8d
0x18004f765  mov     [rsp-40h+arg_8], rdx
0x18004f76a  mov     [rsp-40h+arg_0], rcx
0x18004f76f  push    rbp
0x18004f770  push    rbx
0x18004f771  push    rsi
0x18004f772  push    rdi
0x18004f773  push    r12
0x18004f775  push    r13
0x18004f777  push    r14
0x18004f779  push    r15
0x18004f77b  mov     rbp, rsp
0x18004f77e  sub     rsp, 58h
0x18004f782  xor     edi, edi
0x18004f784  mov     r15d, r8d
0x18004f787  mov     r12, rdx
0x18004f78a  mov     r14, rcx
0x18004f78d  test    r8d, r8d
0x18004f790  jz      loc_18004F908
0x18004f796  mov     rcx, [r14+10h]
0x18004f79a  lea     r9, [rbp+arg_18]
0x18004f79e  mov     rdx, [r12+rdi*8]
0x18004f7a2  lea     r8, [rbp+var_18]
0x18004f7a6  mov     [rbp+var_18], 0
0x18004f7ae  mov     [rbp+arg_18], 0
0x18004f7b5  mov     rcx, [rcx+248h]
0x18004f7bc  call    cs:__imp_UpdateFrameworkPackageInRegistryStore
0x18004f7c3  nop     dword ptr [rax+rax+00h]
0x18004f7c8  mov     ebx, eax
0x18004f7ca  test    eax, eax
0x18004f7cc  js      loc_18004F883
0x18004f7d2  mov     ecx, [rbp+arg_18]
0x18004f7d5  xor     esi, esi
0x18004f7d7  test    ecx, ecx
0x18004f7d9  jz      loc_18004F8BA
0x18004f7df  mov     r15, [rbp+arg_0]
0x18004f7e3  mov     rcx, [r15+10h]
0x18004f7e7  lea     r14, [rsi+rsi*2]
0x18004f7eb  mov     rdx, [rbp+var_18]
0x18004f7ef  mov     r8b, 1
0x18004f7f2  mov     rcx, [rcx+248h]
0x18004f7f9  mov     rdx, [rdx+r14*8]
0x18004f7fd  call    cs:__imp_RemoveStagedPackageFromRegistryStore
0x18004f804  nop     dword ptr [rax+rax+00h]
0x18004f809  mov     r12, [rbp+40h]
0x18004f80d  mov     ebx, eax
0x18004f80f  test    eax, eax
0x18004f811  mov     rax, [rbp+var_18]
0x18004f815  mov     r14, [rax+r14*8]
0x18004f819  js      short loc_18004F838
0x18004f81b  mov     rdx, r14; unsigned __int16 *
0x18004f81e  mov     rcx, r15; this
0x18004f821  mov     r13d, 2DDh
0x18004f827  call    ?DestagePackage@MsixPackageAdapter@Library@Provisioning@MsixPackage@@QEAAJPEBG@Z; MsixPackage::Provisioning::Library::MsixPackageAdapter::DestagePackage(ushort const *)
0x18004f82c  mov     r9d, eax
0x18004f82f  lea     rcx, aHr0xXDestaging; "(hr:0x%x) Destaging framework %ws faile"...
0x18004f836  jmp     short loc_18004F848
0x18004f838  mov     r13d, 2E1h
0x18004f83e  lea     rcx, aHr0xXRemovingF; "(hr:0x%x) Removing framework %ws from t"...
0x18004f845  mov     r9d, ebx; char *
0x18004f848  mov     [rsp+58h+var_28], r14
0x18004f84d  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f854  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x18004f858  mov     edx, r13d; void *
0x18004f85b  mov     qword ptr [rsp+58h+var_38], rcx; int
0x18004f860  mov     rcx, r12; this
0x18004f863  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f868  mov     ecx, [rbp+arg_18]
0x18004f86b  inc     esi
0x18004f86d  cmp     esi, ecx
0x18004f86f  jb      loc_18004F7E3
0x18004f875  mov     r15d, [rbp+arg_10]
0x18004f879  mov     r14, [rbp+arg_0]
0x18004f87d  mov     r12, [rbp+arg_8]
0x18004f881  jmp     short loc_18004F8BA
0x18004f883  mov     rax, [r12+rdi*8]
0x18004f887  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f88e  mov     rcx, [rbp+40h]; this
0x18004f892  mov     r9d, ebx; char *
0x18004f895  mov     edx, 2E7h; void *
0x18004f89a  mov     rax, [rax]
0x18004f89d  mov     [rsp+58h+var_28], rax
0x18004f8a2  lea     rax, aHr0xXUpdatingP; "(hr:0x%x) Updating packages in the regi"...
0x18004f8a9  mov     dword ptr [rsp+58h+var_30], ebx; char *
0x18004f8ad  mov     qword ptr [rsp+58h+var_38], rax; int
0x18004f8b2  call    ?Log_HrMsg@in1diag3@details@wil@@YAJPEAXIPEBDJ1ZZ; wil::details::in1diag3::Log_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004f8b7  mov     ecx, [rbp+arg_18]
0x18004f8ba  cmp     [rbp+var_18], 0
0x18004f8bf  jz      short loc_18004F8DD
0x18004f8c1  lea     rdx, [rbp+var_18]
0x18004f8c5  call    cs:__imp_DeleteAllPackagesFromPackageArray
0x18004f8cc  nop     dword ptr [rax+rax+00h]
0x18004f8d1  mov     rcx, [rbp+40h]; this
0x18004f8d5  mov     r9d, eax; char *
0x18004f8d8  call    ?Log_Hr@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_Hr(void *,uint,char const *,long)
0x18004f8dd  inc     edi
0x18004f8df  cmp     edi, r15d
0x18004f8e2  jb      loc_18004F796
0x18004f8e8  test    ebx, ebx
0x18004f8ea  jns     short loc_18004F908
0x18004f8ec  mov     rcx, [rbp+40h]; this
0x18004f8f0  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004f8f7  mov     r9d, ebx; char *
0x18004f8fa  mov     edx, 2F0h; void *
0x18004f8ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18004f904  mov     eax, ebx
0x18004f906  jmp     short loc_18004F90A
0x18004f908  xor     eax, eax
0x18004f90a  add     rsp, 58h
0x18004f90e  pop     r15
0x18004f910  pop     r14
0x18004f912  pop     r13
0x18004f914  pop     r12
0x18004f916  pop     rdi
0x18004f917  pop     rsi
0x18004f918  pop     rbx
0x18004f919  pop     rbp
0x18004f91a  retn
```
