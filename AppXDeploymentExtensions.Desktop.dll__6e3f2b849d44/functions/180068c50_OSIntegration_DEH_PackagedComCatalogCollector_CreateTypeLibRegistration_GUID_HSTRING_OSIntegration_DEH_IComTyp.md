# OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration(_GUID,HSTRING__ *,OSIntegration::DEH::IComTypeLibRegistration * *)

- ea: `0x180068c50`
- end: `0x180068f12`
- name: `?CreateTypeLibRegistration@PackagedComCatalogCollector@DEH@OSIntegration@@UEAAJU_GUID@@PEAUHSTRING__@@PEAPEAUIComTypeLibRegistration@23@@Z`
- size: `706`
- prototype: `int(OSIntegration::DEH::PackagedComCatalogCollector *__hidden this, struct _GUID *__struct_ptr, HSTRING, struct OSIntegration::DEH::IComTypeLibRegistration **)`
- caller_count: `0`
- callee_count: `8`
- tags: `broker_com_uri`

## callees

- `0x18004c6e0`
- `0x1800606d4`
- `0x180068c50`
- `0x18006a4c8`
- `0x1800aed10`
- `0x1801429c8`
- `0x1801455d4`
- `0x1801ac010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180068d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180068d68`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068d3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068daa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068ee7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068d3c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068daa`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e2f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068e98`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068ecd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180068ee7`

## string_xrefs

- `0x180068cc0`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180068d0f`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180068d95`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180068e1a`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180068e83`: `onecore\admin\appmodel\osim\src\deh\winrt\collector\packagedcomregistration.cpp`
- `0x180068cb9`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x180068d08`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x180068d8e`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x180068e13`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x180068e7c`: `OSIntegration::DEH::PackagedComCatalogCollector::CreateTypeLibRegistration`
- `0x180068e07`: `_typeLibs->Insert(typeLibKey.Get(), spRegistration.Get(), &replaced)`
- `0x180068e70`: `replaced`

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
0x180068c50  push    rbp
0x180068c52  push    rbx
0x180068c53  push    rsi
0x180068c54  push    rdi
0x180068c55  push    r14
0x180068c57  push    r15
0x180068c59  lea     rbp, [rsp-2Fh]
0x180068c5e  sub     rsp, 0D8h
0x180068c65  mov     rax, cs:__security_cookie
0x180068c6c  xor     rax, rsp
0x180068c6f  mov     [rbp+57h+var_40], rax
0x180068c73  mov     rsi, r9
0x180068c76  mov     r14, r8
0x180068c79  mov     rdi, rdx
0x180068c7c  mov     r15, rcx
0x180068c7f  mov     [rbp+57h+var_B8], r8
0x180068c83  mov     qword ptr [r9], 0
0x180068c8a  mov     [rbp+57h+string], 0
0x180068c92  lea     rdx, [rbp+57h+var_B8]; HSTRING *
0x180068c96  lea     rcx, [rbp+57h+string]; newString
0x180068c9a  call    ?Set@HString@Wrappers@WRL@Microsoft@@QEAAJAEBQEAUHSTRING__@@@Z; Microsoft::WRL::Wrappers::HString::Set(HSTRING__ * const &)
0x180068c9f  mov     ebx, eax
0x180068ca1  test    eax, eax
0x180068ca3  jns     short loc_180068CD6
0x180068ca5  mov     rcx, [rbp+5Fh]; this
0x180068ca9  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x180068cad  lea     rax, aVersionnumbers; "versionNumberString.Set(versionNumber)"
0x180068cb4  mov     [rsp+100h+var_E0], rax; char *
0x180068cb9  lea     r9, aOsintegrationD_77; "OSIntegration::DEH::PackagedComCatalogC"...
0x180068cc0  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180068cc7  mov     edx, 1438h; void *
0x180068ccc  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180068cd1  jmp     loc_180068EE3
0x180068cd6  lea     r8, [rbp+57h+string]
0x180068cda  mov     rdx, rdi
0x180068cdd  lea     rcx, [rbp+57h+var_B8]
0x180068ce1  call    ??$Make@VComTypeLibRegistration@DEH@OSIntegration@@AEAU_GUID@@AEAVOpaqueString@@@Details@WRL@Microsoft@@YA?AV?$ComPtr@VComTypeLibRegistration@DEH@OSIntegration@@@12@AEAU_GUID@@AEAVOpaqueString@@@Z; Microsoft::WRL::Details::Make<OSIntegration::DEH::ComTypeLibRegistration,_GUID &,OpaqueString &>(_GUID &,OpaqueString &)
0x180068ce6  mov     rbx, [rbp+57h+var_B8]
0x180068cea  test    rbx, rbx
0x180068ced  jnz     short loc_180068D26
0x180068cef  mov     rcx, [rbp+5Fh]; this
0x180068cf3  mov     ebx, 8007000Eh
0x180068cf8  mov     dword ptr [rsp+100h+var_D8], ebx; char *
0x180068cfc  lea     rax, aSpregistration_3; "spRegistration"
0x180068d03  mov     [rsp+100h+var_E0], rax; char *
0x180068d08  lea     r9, aOsintegrationD_77; "OSIntegration::DEH::PackagedComCatalogC"...
0x180068d0f  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180068d16  mov     edx, 143Dh; void *
0x180068d1b  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180068d20  nop
0x180068d21  jmp     loc_180068EE3
0x180068d26  mov     rdx, rdi; rguid
0x180068d29  lea     rcx, [rbp+57h+sz]; lpsz
0x180068d2d  call    ??0GuidString@@QEAA@AEBU_GUID@@@Z; GuidString::GuidString(_GUID const &)
0x180068d32  mov     [rbp+57h+newString], 0
0x180068d3a  xor     ecx, ecx; string
0x180068d3c  call    cs:__imp_WindowsDeleteString
0x180068d43  nop     dword ptr [rax+rax+00h]
0x180068d48  mov     [rbp+57h+newString], 0
0x180068d50  lea     rdx, [rbp+57h+sz]
0x180068d54  lea     rcx, [rbp+57h+var_B0]
0x180068d58  call    ??$?0VGuidString@@@HStringReference@Wrappers@WRL@Microsoft@@QEAA@AEBVGuidString@@UDummy@Details@23@@Z; Microsoft::WRL::Wrappers::HStringReference::HStringReference(GuidString const &,Microsoft::WRL::Details::Dummy)
0x180068d5d  lea     r8, [rbp+57h+newString]; newString
0x180068d61  mov     rdx, r14; string2
0x180068d64  mov     rcx, [rax+18h]; string1
0x180068d68  call    cs:__imp_WindowsConcatString
0x180068d6f  nop     dword ptr [rax+rax+00h]
0x180068d74  mov     edi, eax
0x180068d76  test    eax, eax
0x180068d78  jns     short loc_180068DDA
0x180068d7a  mov     rcx, [rbp+5Fh]; this
0x180068d7e  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x180068d82  lea     rax, aWindowsconcats; "WindowsConcatString( Wrappers::HStringR"...
0x180068d89  mov     [rsp+100h+var_E0], rax; char *
0x180068d8e  lea     r9, aOsintegrationD_77; "OSIntegration::DEH::PackagedComCatalogC"...
0x180068d95  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180068d9c  mov     edx, 1445h; void *
0x180068da1  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180068da6  mov     rcx, [rbp+57h+newString]; string
0x180068daa  call    cs:__imp_WindowsDeleteString
0x180068db1  nop     dword ptr [rax+rax+00h]
0x180068db6  mov     [rbp+57h+newString], 0
0x180068dbe  test    rbx, rbx
0x180068dc1  jz      short loc_180068DD3
0x180068dc3  mov     rax, [rbx]
0x180068dc6  mov     rcx, rbx
0x180068dc9  mov     rax, [rax+10h]
0x180068dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068dd2  nop
0x180068dd3  mov     ebx, edi
0x180068dd5  jmp     loc_180068EE3
0x180068dda  mov     byte ptr [rbp+57h+var_D0], 0
0x180068dde  mov     rcx, [r15+58h]
0x180068de2  mov     rax, [rcx]
0x180068de5  lea     r9, [rbp+57h+var_D0]
0x180068de9  mov     r8, rbx
0x180068dec  mov     rdx, [rbp+57h+newString]
0x180068df0  mov     rax, [rax+50h]
0x180068df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068df9  mov     edi, eax
0x180068dfb  test    eax, eax
0x180068dfd  jns     short loc_180068E5D
0x180068dff  mov     rcx, [rbp+5Fh]; this
0x180068e03  mov     dword ptr [rsp+100h+var_D8], eax; char *
0x180068e07  lea     rax, aTypelibsInsert; "_typeLibs->Insert(typeLibKey.Get(), spR"...
0x180068e0e  mov     [rsp+100h+var_E0], rax; char *
0x180068e13  lea     r9, aOsintegrationD_77; "OSIntegration::DEH::PackagedComCatalogC"...
0x180068e1a  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180068e21  mov     edx, 1448h; void *
0x180068e26  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180068e2b  mov     rcx, [rbp+57h+newString]; string
0x180068e2f  call    cs:__imp_WindowsDeleteString
0x180068e36  nop     dword ptr [rax+rax+00h]
0x180068e3b  mov     [rbp+57h+newString], 0
0x180068e43  test    rbx, rbx
0x180068e46  jz      short loc_180068E58
0x180068e48  mov     rax, [rbx]
0x180068e4b  mov     rcx, rbx
0x180068e4e  mov     rax, [rax+10h]
0x180068e52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068e57  nop
0x180068e58  jmp     loc_180068DD3
0x180068e5d  cmp     byte ptr [rbp+57h+var_D0], 0
0x180068e61  jz      short loc_180068EC6
0x180068e63  mov     rcx, [rbp+5Fh]; this
0x180068e67  mov     edi, 8000000Dh
0x180068e6c  mov     dword ptr [rsp+100h+var_D8], edi; char *
0x180068e70  lea     rax, aReplaced; "replaced"
0x180068e77  mov     [rsp+100h+var_E0], rax; char *
0x180068e7c  lea     r9, aOsintegrationD_77; "OSIntegration::DEH::PackagedComCatalogC"...
0x180068e83  lea     r8, aOnecoreAdminAp_92; "onecore\\admin\\appmodel\\osim\\src\\de"...
0x180068e8a  mov     edx, 1449h; void *
0x180068e8f  call    ?Return_Hr@in1diag5@details@wil@@YAXPEAXIPEBD11J@Z; wil::details::in1diag5::Return_Hr(void *,uint,char const *,char const *,char const *,long)
0x180068e94  mov     rcx, [rbp+57h+newString]; string
0x180068e98  call    cs:__imp_WindowsDeleteString
0x180068e9f  nop     dword ptr [rax+rax+00h]
0x180068ea4  mov     [rbp+57h+newString], 0
0x180068eac  test    rbx, rbx
0x180068eaf  jz      short loc_180068EC1
0x180068eb1  mov     rax, [rbx]
0x180068eb4  mov     rcx, rbx
0x180068eb7  mov     rax, [rax+10h]
0x180068ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068ec0  nop
0x180068ec1  jmp     loc_180068DD3
0x180068ec6  mov     [rsi], rbx
0x180068ec9  mov     rcx, [rbp+57h+newString]; string
0x180068ecd  call    cs:__imp_WindowsDeleteString
0x180068ed4  nop     dword ptr [rax+rax+00h]
0x180068ed9  mov     [rbp+57h+newString], 0
0x180068ee1  xor     ebx, ebx
0x180068ee3  mov     rcx, [rbp+57h+string]; string
0x180068ee7  call    cs:__imp_WindowsDeleteString
0x180068eee  nop     dword ptr [rax+rax+00h]
0x180068ef3  mov     eax, ebx
0x180068ef5  mov     rcx, [rbp+57h+var_40]
0x180068ef9  xor     rcx, rsp; StackCookie
0x180068efc  call    __security_check_cookie
0x180068f01  add     rsp, 0D8h
0x180068f08  pop     r15
0x180068f0a  pop     r14
0x180068f0c  pop     rdi
0x180068f0d  pop     rsi
0x180068f0e  pop     rbx
0x180068f0f  pop     rbp
0x180068f10  retn
```
