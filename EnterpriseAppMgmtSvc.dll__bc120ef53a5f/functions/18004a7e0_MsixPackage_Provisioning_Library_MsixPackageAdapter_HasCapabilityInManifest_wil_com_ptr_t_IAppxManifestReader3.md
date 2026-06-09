# MsixPackage::Provisioning::Library::MsixPackageAdapter::HasCapabilityInManifest(wil::com_ptr_t<IAppxManifestReader3,wil::err_returncode_policy> const &,APPX_CAPABILITY_CLASS_TYPE,ushort const *,bool &)

- ea: `0x18004a7e0`
- end: `0x18004aa46`
- name: `?HasCapabilityInManifest@MsixPackageAdapter@Library@Provisioning@MsixPackage@@AEAAJAEBV?$com_ptr_t@UIAppxManifestReader3@@Uerr_returncode_policy@wil@@@wil@@W4APPX_CAPABILITY_CLASS_TYPE@@PEBGAEA_N@Z`
- size: `614`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18004aa4c`
- `0x18004abb0`
- `0x18004acec`

## callees

- `0x18003d4ec`
- `0x18004a7e0`
- `0x180070010`

## import_xrefs

- `msvcrt!_wcsicmp` at `0x18004a90a`
- `msvcrt!_wcsicmp` at `0x18004a90a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a9a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a9df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa1e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a941`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a9a7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004a9df`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18004aa1e`

## string_xrefs

- `0x18004a844`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a8ab`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a98c`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004aa03`: `onecore\admin\appmodel\utilities\provisionhelper\msixpackageadapter.cpp`
- `0x18004a97d`: `Failed to move the next capability in enumerator.`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall MsixPackage::Provisioning::Library::MsixPackageAdapter::HasCapabilityInManifest(
        __int64 a1,
        __int64 **a2,
        int a3,
        const wchar_t *a4,
        wchar_t *String1)
{
  wchar_t *v6; // rdi
  __int64 *v7; // rcx
  __int64 v8; // rax
  int v9; // ebx
  __int64 v11; // rax
  const char *v12; // [rsp+28h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  __int64 *v14; // [rsp+50h] [rbp+20h] BYREF
  int v15; // [rsp+60h] [rbp+30h] BYREF

  v15 = a3;
  v6 = String1;
  *(_BYTE *)String1 = 0;
  v14 = 0;
  v7 = *a2;
  v8 = **a2;
  v14 = 0;
  v9 = (*(__int64 (__fastcall **)(__int64 *, __int64, __int64 **))(v8 + 104))(v7, 4, &v14);
  if ( v9 >= 0 )
  {
    v15 = 0;
    v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v14 + 32))(v14, &v15);
    if ( v9 >= 0 )
    {
      while ( 1 )
      {
        if ( !v15 )
          goto LABEL_15;
        String1 = 0;
        v11 = *v14;
        String1 = 0;
        v9 = (*(__int64 (__fastcall **)(__int64 *, wchar_t **))(v11 + 24))(v14, &String1);
        if ( v9 < 0 )
          break;
        if ( !_wcsicmp(String1, a4) )
        {
          *(_BYTE *)v6 = 1;
          if ( String1 )
            CoTaskMemFree(String1);
LABEL_15:
          if ( v14 )
            (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
          return 0;
        }
        v9 = (*(__int64 (__fastcall **)(__int64 *, int *))(*v14 + 40))(v14, &v15);
        if ( v9 < 0 )
        {
          wil::details::in1diag3::Return_HrMsg(
            retaddr,
            (void *)0x55D,
            (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
            (const char *)(unsigned int)v9,
            (int)"Failed to move the next capability in enumerator.",
            v12);
          if ( String1 )
            CoTaskMemFree(String1);
          if ( v14 )
            (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
          return (unsigned int)v9;
        }
        if ( String1 )
          CoTaskMemFree(String1);
      }
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x555,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v9,
        (int)"Failed to get current capability from enumerator.",
        v12);
      if ( String1 )
        CoTaskMemFree(String1);
      if ( v14 )
        (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    }
    else
    {
      wil::details::in1diag3::Return_HrMsg(
        retaddr,
        (void *)0x550,
        (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
        (const char *)(unsigned int)v9,
        (int)"Failed in GetHasCurrent for capability enumerator.",
        v12);
      if ( v14 )
        (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
    }
  }
  else
  {
    wil::details::in1diag3::Return_HrMsg(
      retaddr,
      (void *)0x54D,
      (unsigned int)"onecore\\admin\\appmodel\\utilities\\provisionhelper\\msixpackageadapter.cpp",
      (const char *)(unsigned int)v9,
      (int)"Failed to get Windows capabilities list for package.",
      v12);
    if ( v14 )
      (*(void (__fastcall **)(__int64 *))(*v14 + 16))(v14);
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x18004a7e0  mov     [rsp-18h+arg_8], rbx
0x18004a7e5  mov     [rsp-18h+arg_10], r8d
0x18004a7ea  mov     [rsp-18h+arg_0], rcx
0x18004a7ef  push    rbp
0x18004a7f0  push    rsi
0x18004a7f1  push    rdi
0x18004a7f2  mov     rbp, rsp
0x18004a7f5  sub     rsp, 30h
0x18004a7f9  mov     rsi, r9
0x18004a7fc  mov     rdi, [rbp+String1]
0x18004a800  mov     byte ptr [rdi], 0
0x18004a803  mov     [rbp+arg_0], 0
0x18004a80b  mov     rcx, [rdx]
0x18004a80e  mov     rax, [rcx]
0x18004a811  mov     [rbp+arg_0], 0
0x18004a819  lea     r8, [rbp+arg_0]
0x18004a81d  mov     edx, 4
0x18004a822  mov     rax, [rax+68h]
0x18004a826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a82b  mov     ebx, eax
0x18004a82d  test    eax, eax
0x18004a82f  jns     short loc_18004A873
0x18004a831  mov     rcx, [rbp+18h]; this
0x18004a835  lea     rax, aFailedToGetWin; "Failed to get Windows capabilities list"...
0x18004a83c  mov     qword ptr [rsp+30h+var_10], rax; int
0x18004a841  mov     r9d, ebx; char *
0x18004a844  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a84b  mov     edx, 54Dh; void *
0x18004a850  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a855  nop
0x18004a856  mov     rcx, [rbp+arg_0]
0x18004a85a  test    rcx, rcx
0x18004a85d  jz      short loc_18004A86C
0x18004a85f  mov     rax, [rcx]
0x18004a862  mov     rax, [rax+10h]
0x18004a866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a86b  nop
0x18004a86c  mov     eax, ebx
0x18004a86e  jmp     loc_18004A96B
0x18004a873  mov     [rbp+arg_10], 0
0x18004a87a  mov     rcx, [rbp+arg_0]
0x18004a87e  mov     rax, [rcx]
0x18004a881  lea     rdx, [rbp+arg_10]
0x18004a885  mov     rax, [rax+20h]
0x18004a889  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a88e  mov     ebx, eax
0x18004a890  test    eax, eax
0x18004a892  jns     loc_18004A94D
0x18004a898  mov     rcx, [rbp+18h]; this
0x18004a89c  lea     rax, aFailedInGethas; "Failed in GetHasCurrent for capability "...
0x18004a8a3  mov     qword ptr [rsp+30h+var_10], rax; int
0x18004a8a8  mov     r9d, ebx; char *
0x18004a8ab  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a8b2  mov     edx, 550h; void *
0x18004a8b7  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a8bc  nop
0x18004a8bd  mov     rcx, [rbp+arg_0]
0x18004a8c1  test    rcx, rcx
0x18004a8c4  jz      short loc_18004A8D3
0x18004a8c6  mov     rax, [rcx]
0x18004a8c9  mov     rax, [rax+10h]
0x18004a8cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8d2  nop
0x18004a8d3  jmp     short loc_18004A86C
0x18004a8d5  mov     [rbp+String1], 0
0x18004a8dd  mov     rcx, [rbp+arg_0]
0x18004a8e1  mov     rax, [rcx]
0x18004a8e4  mov     [rbp+String1], 0
0x18004a8ec  lea     rdx, [rbp+String1]
0x18004a8f0  mov     rax, [rax+18h]
0x18004a8f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a8f9  mov     ebx, eax
0x18004a8fb  test    eax, eax
0x18004a8fd  js      loc_18004A9F0
0x18004a903  mov     rdx, rsi; String2
0x18004a906  mov     rcx, [rbp+String1]; String1
0x18004a90a  call    cs:__imp__wcsicmp
0x18004a911  nop     dword ptr [rax+rax+00h]
0x18004a916  test    eax, eax
0x18004a918  jz      loc_18004A9CF
0x18004a91e  mov     rcx, [rbp+arg_0]
0x18004a922  mov     rax, [rcx]
0x18004a925  lea     rdx, [rbp+arg_10]
0x18004a929  mov     rax, [rax+28h]
0x18004a92d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a932  mov     ebx, eax
0x18004a934  test    eax, eax
0x18004a936  js      short loc_18004A979
0x18004a938  mov     rcx, [rbp+String1]; pv
0x18004a93c  test    rcx, rcx
0x18004a93f  jz      short loc_18004A94D
0x18004a941  call    cs:__imp_CoTaskMemFree
0x18004a948  nop     dword ptr [rax+rax+00h]
0x18004a94d  cmp     [rbp+arg_10], 0
0x18004a951  jnz     short loc_18004A8D5
0x18004a953  mov     rcx, [rbp+arg_0]
0x18004a957  test    rcx, rcx
0x18004a95a  jz      short loc_18004A969
0x18004a95c  mov     rax, [rcx]
0x18004a95f  mov     rax, [rax+10h]
0x18004a963  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a968  nop
0x18004a969  xor     eax, eax
0x18004a96b  mov     rbx, [rsp+30h+arg_8]
0x18004a970  add     rsp, 30h
0x18004a974  pop     rdi
0x18004a975  pop     rsi
0x18004a976  pop     rbp
0x18004a977  retn
0x18004a979  mov     rcx, [rbp+18h]; this
0x18004a97d  lea     rax, aFailedToMoveTh; "Failed to move the next capability in e"...
0x18004a984  mov     qword ptr [rsp+30h+var_10], rax; int
0x18004a989  mov     r9d, ebx; char *
0x18004a98c  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004a993  mov     edx, 55Dh; void *
0x18004a998  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004a99d  nop
0x18004a99e  mov     rcx, [rbp+String1]; pv
0x18004a9a2  test    rcx, rcx
0x18004a9a5  jz      short loc_18004A9B4
0x18004a9a7  call    cs:__imp_CoTaskMemFree
0x18004a9ae  nop     dword ptr [rax+rax+00h]
0x18004a9b3  nop
0x18004a9b4  mov     rcx, [rbp+arg_0]
0x18004a9b8  test    rcx, rcx
0x18004a9bb  jz      short loc_18004A9CA
0x18004a9bd  mov     rax, [rcx]
0x18004a9c0  mov     rax, [rax+10h]
0x18004a9c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a9c9  nop
0x18004a9ca  jmp     loc_18004A86C
0x18004a9cf  mov     byte ptr [rdi], 1
0x18004a9d2  mov     rcx, [rbp+String1]; pv
0x18004a9d6  test    rcx, rcx
0x18004a9d9  jz      loc_18004A953
0x18004a9df  call    cs:__imp_CoTaskMemFree
0x18004a9e6  nop     dword ptr [rax+rax+00h]
0x18004a9eb  jmp     loc_18004A953
0x18004a9f0  mov     rcx, [rbp+18h]; this
0x18004a9f4  lea     rax, aFailedToGetCur; "Failed to get current capability from e"...
0x18004a9fb  mov     qword ptr [rsp+30h+var_10], rax; int
0x18004aa00  mov     r9d, ebx; char *
0x18004aa03  lea     r8, aOnecoreAdminAp_0; "onecore\\admin\\appmodel\\utilities\\pr"...
0x18004aa0a  mov     edx, 555h; void *
0x18004aa0f  call    ?Return_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::Return_HrMsg(void *,uint,char const *,long,char const *,...)
0x18004aa14  nop
0x18004aa15  mov     rcx, [rbp+String1]; pv
0x18004aa19  test    rcx, rcx
0x18004aa1c  jz      short loc_18004AA2B
0x18004aa1e  call    cs:__imp_CoTaskMemFree
0x18004aa25  nop     dword ptr [rax+rax+00h]
0x18004aa2a  nop
0x18004aa2b  mov     rcx, [rbp+arg_0]
0x18004aa2f  test    rcx, rcx
0x18004aa32  jz      short loc_18004AA41
0x18004aa34  mov     rax, [rcx]
0x18004aa37  mov     rax, [rax+10h]
0x18004aa3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa40  nop
0x18004aa41  jmp     loc_18004A86C
```
