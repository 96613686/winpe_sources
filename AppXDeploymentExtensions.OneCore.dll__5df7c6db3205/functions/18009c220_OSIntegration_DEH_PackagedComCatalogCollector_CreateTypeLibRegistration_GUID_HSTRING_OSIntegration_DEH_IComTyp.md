# OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration(_GUID,HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration * *)

- ea: `0x18009c220`
- end: `0x18009c4b7`
- name: `?CreateTypeLibRegistration@PackagedComCatalogCollector@DEH@OSIntegration@@UEAAJU_GUID@@PEAUHSTRING__@@PEAPEAUIComTypeLibRegistration@23@@Z`
- size: `663`
- prototype: `int(OSIntegration::DEH::PackagedComCatalogCollector *__hidden this, struct _GUID *__struct_ptr, HSTRING, struct OSIntegration::DEH::IComTypeLibRegistration **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18006a940`
- `0x18009aff4`
- `0x18009c220`
- `0x1800b3110`
- `0x1800f0260`
- `0x1801ade5c`
- `0x1801b0470`
- `0x180211010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18009c332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x18009c332`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c30c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c36e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c3ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c47f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c493`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c30c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c36e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c3ed`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c450`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c47f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18009c493`

## string_xrefs

- `0x18009c290`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18009c2df`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18009c359`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18009c3d8`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18009c43b`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x18009c289`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x18009c2d8`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x18009c352`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x18009c3d1`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x18009c434`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x18009c3c5`: `_typeLibs->Insert(typeLibKey.Get(), spRegistration.Get(), &replaced)`
- `0x18009c428`: `replaced`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration(
        OSIntegration::DEH::PackagedComCatalogCollector *this,
        struct _GUID *a2,
        HSTRING a3,
        struct OSIntegration::DEH::IComTypeLibRegistration **a4)
{
  int v8; // eax
  unsigned int v9; // ebx
  struct OSIntegration::DEH::IComTypeLibRegistration *v10; // rbx
  __int64 v11; // rax
  HRESULT v12; // eax
  int v13; // edi
  int v14; // eax
  char *v16; // [rsp+28h] [rbp-81h]
  int v17; // [rsp+30h] [rbp-79h] BYREF
  HSTRING newString; // [rsp+38h] [rbp-71h] BYREF
  HSTRING string; // [rsp+40h] [rbp-69h] BYREF
  HSTRING v20; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v21[32]; // [rsp+50h] [rbp-59h] BYREF
  OLECHAR sz[40]; // [rsp+70h] [rbp-39h] BYREF
  wil::details::in1diag5 *retaddr; // [rsp+108h] [rbp+5Fh]

  v20 = a3;
  *a4 = 0;
  string = 0;
  v8 = Microsoft::WRL::Wrappers::HString::Set(&string, &v20);
  v9 = v8;
  if ( v8 >= 0 )
  {
    Microsoft::WRL::Details::Make<OSIntegration::DEH::ComTypeLibRegistration,_GUID &,OpaqueString &>(&v20, a2, &string);
    v10 = (struct OSIntegration::DEH::IComTypeLibRegistration *)v20;
    if ( v20 )
    {
      GuidString::GuidString(sz, a2);
      WindowsDeleteString(0);
      newString = 0;
      v11 = Microsoft::WRL::Wrappers::HStringReference::HStringReference(v21, sz);
      v12 = WindowsConcatString(*(HSTRING *)(v11 + 24), a3, &newString);
      v13 = v12;
      if ( v12 >= 0 )
      {
        LOBYTE(v17) = 0;
        v14 = (*(__int64 (__fastcall **)(_QWORD, HSTRING, struct OSIntegration::DEH::IComTypeLibRegistration *, int *))(**((_QWORD **)this + 11) + 80LL))(
                *((_QWORD *)this + 11),
                newString,
                v10,
                &v17);
        v13 = v14;
        if ( v14 >= 0 )
        {
          if ( !(_BYTE)v17 )
          {
            *a4 = v10;
            WindowsDeleteString(newString);
            newString = 0;
            v9 = 0;
            goto LABEL_18;
          }
          v13 = -2147483635;
          LODWORD(v16) = -2147483635;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x1449,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration",
            "replaced",
            v16,
            v17);
          WindowsDeleteString(newString);
          newString = 0;
          if ( v10 )
            (*(void (__fastcall **)(struct OSIntegration::DEH::IComTypeLibRegistration *))(*(_QWORD *)v10 + 16LL))(v10);
        }
        else
        {
          LODWORD(v16) = v14;
          wil::details::in1diag5::Return_Hr(
            retaddr,
            (void *)0x1448,
            (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
            "OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration",
            "_typeLibs->Insert(typeLibKey.Get(), spRegistration.Get(), &replaced)",
            v16,
            v17);
          WindowsDeleteString(newString);
          newString = 0;
          if ( v10 )
            (*(void (__fastcall **)(struct OSIntegration::DEH::IComTypeLibRegistration *))(*(_QWORD *)v10 + 16LL))(v10);
        }
      }
      else
      {
        LODWORD(v16) = v12;
        wil::details::in1diag5::Return_Hr(
          retaddr,
          (void *)0x1445,
          (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
          "OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration",
          "WindowsConcatString( Wrappers::HStringReference(typeLibIdString).Get(), versionNumber, typeLibKey.GetAddressOf())",
          v16,
          v17);
        WindowsDeleteString(newString);
        newString = 0;
        if ( v10 )
          (*(void (__fastcall **)(struct OSIntegration::DEH::IComTypeLibRegistration *))(*(_QWORD *)v10 + 16LL))(v10);
      }
      v9 = v13;
    }
    else
    {
      v9 = -2147024882;
      LODWORD(v16) = -2147024882;
      wil::details::in1diag5::Return_Hr(
        retaddr,
        (void *)0x143D,
        (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
        "OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration",
        "spRegistration",
        v16,
        v17);
    }
  }
  else
  {
    LODWORD(v16) = v8;
    wil::details::in1diag5::Return_Hr(
      retaddr,
      (void *)0x1438,
      (unsigned int)"onecore\\admin\\appmodel\\osim\\src\\deh\\winrt\\collector\\packagedcomregistration.cpp",
      "OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration",
      "versionNumberString.Set(versionNumber)",
      v16,
      v17);
  }
LABEL_18:
  WindowsDeleteString(string);
  return v9;
}

```

## disassembly

```asm
0x18009c220  push    rbp
0x18009c222  push    rbx
0x18009c223  push    rsi
0x18009c224  push    rdi
0x18009c225  push    r14
0x18009c227  push    r15
0x18009c229  lea     rbp, [rsp-2Fh]
0x18009c22e  sub     rsp, 0D8h
0x18009c235  mov     rax, cs:__security_cookie
0x18009c23c  xor     rax, rsp
0x18009c23f  mov     [rbp+57h+var_40], rax
0x18009c243  mov     rsi, r9
0x18009c246  mov     r14, r8
0x18009c249  mov     rdi, rdx
0x18009c24c  mov     r15, rcx
0x18009c24f  mov     [rbp+57h+var_B8], r8
0x18009c253  mov     qword ptr [r9], 0
0x18009c25a  mov     [rbp+57h+string], 0
0x18009c262  lea     rdx, [rbp+57h+var_B8]; HSTRING *
0x18009c266  lea     rcx, [rbp+57h+string]; newString
0x18009c26a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x18009c26f  mov     ebx, eax
0x18009c271  test    eax, eax
0x18009c273  jns     short loc_18009C2A6
0x18009c275  mov     rcx, [rbp+5Fh]; this
0x18009c279  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x18009c27d  lea     rax, aVersionnumbers; "versionNumberString.Set(versionNumber)"
0x18009c284  mov     [rsp+100h+var_E0], rax; char *
0x18009c289  lea     r9, aOsintegrationD_108; "OSIntegration::DEH::PackagedComCatalogC"...
0x18009c290  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009c297  mov     edx, 1438h; void *
0x18009c29c  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009c2a1  jmp     loc_18009C48F
0x18009c2a6  lea     r8, [rbp+57h+string]
0x18009c2aa  mov     rdx, rdi
0x18009c2ad  lea     rcx, [rbp+57h+var_B8]
0x18009c2b1  call    ??$Make@VComTypeLibRegistration@DEH@OSIntegration@@AEAU_GUID@@AEAVOpaqueString@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VComTypeLibRegistration@DEH@OSIntegration@@@12@AEAU_GUID@@AEAVOpaqueString@@@Z; Microsoft::WRL::Details::Make<OSIntegration::DEH::ComTypeLibRegistration,_GUID &,OpaqueString &>(_GUID &,OpaqueString &)
0x18009c2b6  mov     rbx, [rbp+57h+var_B8]
0x18009c2ba  test    rbx, rbx
0x18009c2bd  jnz     short loc_18009C2F6
0x18009c2bf  mov     rcx, [rbp+5Fh]; this
0x18009c2c3  mov     ebx, 8007000Eh
0x18009c2c8  mov     dword ptr [rsp+100h+var_D8], ebx; char *
0x18009c2cc  lea     rax, aSpregistration_3; "spRegistration"
0x18009c2d3  mov     [rsp+100h+var_E0], rax; char *
0x18009c2d8  lea     r9, aOsintegrationD_108; "OSIntegration::DEH::PackagedComCatalogC"...
0x18009c2df  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009c2e6  mov     edx, 143Dh; void *
0x18009c2eb  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009c2f0  nop
0x18009c2f1  jmp     loc_18009C48F
0x18009c2f6  mov     rdx, rdi; rguid
0x18009c2f9  lea     rcx, [rbp+57h+sz]; lpsz
0x18009c2fd  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x18009c302  mov     [rbp+57h+newString], 0
0x18009c30a  xor     ecx, ecx; string
0x18009c30c  call    cs:__imp_WindowsDeleteString
0x18009c312  mov     [rbp+57h+newString], 0
0x18009c31a  lea     rdx, [rbp+57h+sz]
0x18009c31e  lea     rcx, [rbp+57h+var_B0]
0x18009c322  call    ??$?0VGuidString@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBVGuidString@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(GuidString const &,Microsoft::WRL::Details::Dummy)
0x18009c327  lea     r8, [rbp+57h+newString]; newString
0x18009c32b  mov     rdx, r14; string2
0x18009c32e  mov     rcx, [rax+18h]; string1
0x18009c332  call    cs:__imp_WindowsConcatString
0x18009c338  mov     edi, eax
0x18009c33a  test    eax, eax
0x18009c33c  jns     short loc_18009C398
0x18009c33e  mov     rcx, [rbp+5Fh]; this
0x18009c342  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x18009c346  lea     rax, aWindowsconcats_1; "WindowsConcatString( Wrappers::HStringR"...
0x18009c34d  mov     [rsp+100h+var_E0], rax; char *
0x18009c352  lea     r9, aOsintegrationD_108; "OSIntegration::DEH::PackagedComCatalogC"...
0x18009c359  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009c360  mov     edx, 1445h; void *
0x18009c365  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009c36a  mov     rcx, [rbp+57h+newString]; string
0x18009c36e  call    cs:__imp_WindowsDeleteString
0x18009c374  mov     [rbp+57h+newString], 0
0x18009c37c  test    rbx, rbx
0x18009c37f  jz      short loc_18009C391
0x18009c381  mov     rax, [rbx]
0x18009c384  mov     rcx, rbx
0x18009c387  mov     rax, [rax+10h]
0x18009c38b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c390  nop
0x18009c391  mov     ebx, edi
0x18009c393  jmp     loc_18009C48F
0x18009c398  mov     byte ptr [rbp+57h+var_D0], 0
0x18009c39c  mov     rcx, [r15+58h]
0x18009c3a0  mov     rax, [rcx]
0x18009c3a3  lea     r9, [rbp+57h+var_D0]
0x18009c3a7  mov     r8, rbx
0x18009c3aa  mov     rdx, [rbp+57h+newString]
0x18009c3ae  mov     rax, [rax+50h]
0x18009c3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c3b7  mov     edi, eax
0x18009c3b9  test    eax, eax
0x18009c3bb  jns     short loc_18009C415
0x18009c3bd  mov     rcx, [rbp+5Fh]; this
0x18009c3c1  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x18009c3c5  lea     rax, aTypelibsInsert; "_typeLibs->Insert(typeLibKey.Get(), spR"...
0x18009c3cc  mov     [rsp+100h+var_E0], rax; char *
0x18009c3d1  lea     r9, aOsintegrationD_108; "OSIntegration::DEH::PackagedComCatalogC"...
0x18009c3d8  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009c3df  mov     edx, 1448h; void *
0x18009c3e4  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009c3e9  mov     rcx, [rbp+57h+newString]; string
0x18009c3ed  call    cs:__imp_WindowsDeleteString
0x18009c3f3  mov     [rbp+57h+newString], 0
0x18009c3fb  test    rbx, rbx
0x18009c3fe  jz      short loc_18009C410
0x18009c400  mov     rax, [rbx]
0x18009c403  mov     rcx, rbx
0x18009c406  mov     rax, [rax+10h]
0x18009c40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c40f  nop
0x18009c410  jmp     loc_18009C391
0x18009c415  cmp     byte ptr [rbp+57h+var_D0], 0
0x18009c419  jz      short loc_18009C478
0x18009c41b  mov     rcx, [rbp+5Fh]; this
0x18009c41f  mov     edi, 8000000Dh
0x18009c424  mov     dword ptr [rsp+100h+var_D8], edi; char *
0x18009c428  lea     rax, aReplaced; "replaced"
0x18009c42f  mov     [rsp+100h+var_E0], rax; char *
0x18009c434  lea     r9, aOsintegrationD_108; "OSIntegration::DEH::PackagedComCatalogC"...
0x18009c43b  lea     r8, aOnecoreAdminAp_96; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x18009c442  mov     edx, 1449h; void *
0x18009c447  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x18009c44c  mov     rcx, [rbp+57h+newString]; string
0x18009c450  call    cs:__imp_WindowsDeleteString
0x18009c456  mov     [rbp+57h+newString], 0
0x18009c45e  test    rbx, rbx
0x18009c461  jz      short loc_18009C473
0x18009c463  mov     rax, [rbx]
0x18009c466  mov     rcx, rbx
0x18009c469  mov     rax, [rax+10h]
0x18009c46d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009c472  nop
0x18009c473  jmp     loc_18009C391
0x18009c478  mov     [rsi], rbx
0x18009c47b  mov     rcx, [rbp+57h+newString]; string
0x18009c47f  call    cs:__imp_WindowsDeleteString
0x18009c485  mov     [rbp+57h+newString], 0
0x18009c48d  xor     ebx, ebx
0x18009c48f  mov     rcx, [rbp+57h+string]; string
0x18009c493  call    cs:__imp_WindowsDeleteString
0x18009c499  mov     eax, ebx
0x18009c49b  mov     rcx, [rbp+57h+var_40]
0x18009c49f  xor     rcx, rsp; StackCookie
0x18009c4a2  call    __security_check_cookie
0x18009c4a7  add     rsp, 0D8h
0x18009c4ae  pop     r15
0x18009c4b0  pop     r14
0x18009c4b2  pop     rdi
0x18009c4b3  pop     rsi
0x18009c4b4  pop     rbx
0x18009c4b5  pop     rbp
0x18009c4b6  retn
```
