# Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageNames(IXMLDOMDocument2 *)

- ea: `0x18001d404`
- end: `0x18001d668`
- name: `?ValidatePackageNames@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEAUIXMLDOMDocument2@@@Z`
- size: `612`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001c45c`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001d404`
- `0x18001e374`
- `0x18001e3dc`
- `0x18001f9c0`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x18001d4cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d501`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d5e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d619`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d4cf`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d501`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d5e7`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d619`

## string_xrefs

- `0x18001d4ee`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001d520`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001d606`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001d62c`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageNames(
        struct IXMLDOMNode *a1)
{
  int v1; // edi
  struct IXMLDOMNodeList *v3; // rbx
  int i; // esi
  HRESULT (__stdcall *get_item)(IXMLDOMNodeList *, int, IXMLDOMNode **); // rdi
  int v6; // eax
  __int64 v7; // rdx
  struct IXMLDOMNodeList *v8; // rbx
  int j; // esi
  HRESULT (__stdcall *v10)(IXMLDOMNodeList *, int, IXMLDOMNode **); // rdi
  int v11; // eax
  __int64 v12; // rdx
  struct IXMLDOMNodeList *v14; // [rsp+30h] [rbp-10h] BYREF
  BSTR bstrString; // [rsp+38h] [rbp-8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  __int64 v17; // [rsp+78h] [rbp+38h] BYREF
  int v18; // [rsp+80h] [rbp+40h] BYREF
  struct IXMLDOMNodeList *v19; // [rsp+88h] [rbp+48h] BYREF

  v1 = 0;
  LOBYTE(v17) = 0;
  v18 = 0;
  v19 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
  Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetNodesList(
    a1,
    L"m:AppxProvisionList/m:Provisioned/m:Package/@FullName",
    &v19,
    &v18,
    (bool *)&v17);
  if ( (_BYTE)v17 )
  {
    v3 = v19;
    for ( i = 0; ; ++i )
    {
      if ( i >= v18 )
        goto LABEL_12;
      v14 = 0;
      get_item = v3->lpVtbl->get_item;
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v14);
      v6 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, struct IXMLDOMNodeList **))get_item)(
             v3,
             (unsigned int)i,
             &v14);
      v1 = v6;
      if ( v6 < 0 )
        break;
      bstrString = 0;
      v1 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, BSTR *))v14->lpVtbl[2].Release)(v14, &bstrString);
      if ( v1 < 0 )
      {
        v7 = 530;
        goto LABEL_9;
      }
      v1 = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageFullName(bstrString);
      if ( v1 < 0 )
      {
        v7 = 531;
LABEL_9:
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)v7,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
          (const char *)(unsigned int)v1);
        SysFreeString(bstrString);
        goto LABEL_24;
      }
      SysFreeString(bstrString);
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v14);
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x20F,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
      (const char *)(unsigned int)v6);
  }
  else
  {
LABEL_12:
    v14 = 0;
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v14);
    Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetNodesList(
      a1,
      L"m:AppxProvisionList/m:EndOfLife/m:Package/@FamilyName",
      &v14,
      &v18,
      (bool *)&v17);
    if ( (_BYTE)v17 )
    {
      v8 = v14;
      for ( j = 0; ; ++j )
      {
        if ( j >= v18 )
          goto LABEL_24;
        v17 = 0;
        v10 = v8->lpVtbl->get_item;
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v17);
        v11 = ((__int64 (__fastcall *)(struct IXMLDOMNodeList *, _QWORD, __int64 *))v10)(v8, (unsigned int)j, &v17);
        v1 = v11;
        if ( v11 < 0 )
          break;
        bstrString = 0;
        v1 = (*(__int64 (__fastcall **)(__int64, BSTR *))(*(_QWORD *)v17 + 208LL))(v17, &bstrString);
        if ( v1 < 0 )
        {
          v12 = 545;
LABEL_20:
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)v12,
            (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
            (const char *)(unsigned int)v1);
          SysFreeString(bstrString);
LABEL_23:
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v17);
          goto LABEL_24;
        }
        v1 = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageFamilyName(bstrString);
        if ( v1 < 0 )
        {
          v12 = 546;
          goto LABEL_20;
        }
        SysFreeString(bstrString);
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v17);
      }
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x21E,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
        (const char *)(unsigned int)v11);
      goto LABEL_23;
    }
  }
LABEL_24:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v14);
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x18001d404  push    rbp
0x18001d406  push    rbx
0x18001d407  push    rsi
0x18001d408  push    rdi
0x18001d409  push    r14
0x18001d40b  mov     rbp, rsp
0x18001d40e  sub     rsp, 40h
0x18001d412  xor     edi, edi
0x18001d414  mov     r14, rcx
0x18001d417  lea     rcx, [rbp+arg_18]
0x18001d41b  mov     byte ptr [rbp+arg_8], dil
0x18001d41f  mov     [rbp+arg_10], edi
0x18001d422  mov     [rbp+arg_18], rdi
0x18001d426  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d42b  lea     rax, [rbp+arg_8]
0x18001d42f  mov     rcx, r14; struct IXMLDOMNode *
0x18001d432  lea     r9, [rbp+arg_10]; int *
0x18001d436  mov     [rsp+40h+var_20], rax; int
0x18001d43b  lea     r8, [rbp+arg_18]; struct IXMLDOMNodeList **
0x18001d43f  lea     rdx, aMAppxprovision_1; "m:AppxProvisionList/m:Provisioned/m:Pac"...
0x18001d446  call    ?GetNodesList@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJPEA_N@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetNodesList(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *,bool *)
0x18001d44b  cmp     byte ptr [rbp+arg_8], dil
0x18001d44f  jz      loc_18001D536
0x18001d455  mov     rbx, [rbp+arg_18]
0x18001d459  xor     esi, esi
0x18001d45b  cmp     esi, [rbp+arg_10]
0x18001d45e  jge     loc_18001D536
0x18001d464  mov     [rbp+var_10], 0
0x18001d46c  lea     rcx, [rbp+var_10]
0x18001d470  mov     rax, [rbx]
0x18001d473  mov     rdi, [rax+38h]
0x18001d477  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d47c  lea     r8, [rbp+var_10]
0x18001d480  mov     edx, esi
0x18001d482  mov     rcx, rbx
0x18001d485  mov     rax, rdi
0x18001d488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d48d  mov     edi, eax
0x18001d48f  test    eax, eax
0x18001d491  js      loc_18001D51C
0x18001d497  mov     rcx, [rbp+var_10]
0x18001d49b  lea     rdx, [rbp+bstrString]
0x18001d49f  mov     [rbp+bstrString], 0
0x18001d4a7  mov     rax, [rcx]
0x18001d4aa  mov     rax, [rax+0D0h]
0x18001d4b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d4b6  mov     edi, eax
0x18001d4b8  test    eax, eax
0x18001d4ba  js      short loc_18001D515
0x18001d4bc  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x18001d4c0  call    ?ValidatePackageFullName@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEBG@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageFullName(ushort const *)
0x18001d4c5  mov     edi, eax
0x18001d4c7  test    eax, eax
0x18001d4c9  js      short loc_18001D4E5
0x18001d4cb  mov     rcx, [rbp+bstrString]; bstrString
0x18001d4cf  call    cs:__imp_SysFreeString
0x18001d4d5  lea     rcx, [rbp+var_10]
0x18001d4d9  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d4de  inc     esi
0x18001d4e0  jmp     loc_18001D45B
0x18001d4e5  mov     edx, 213h; void *
0x18001d4ea  mov     rcx, [rbp+28h]; this
0x18001d4ee  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d4f5  mov     r9d, edi; char *
0x18001d4f8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d4fd  mov     rcx, [rbp+bstrString]; bstrString
0x18001d501  call    cs:__imp_SysFreeString
0x18001d507  lea     rcx, [rbp+var_10]
0x18001d50b  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d510  jmp     loc_18001D652
0x18001d515  mov     edx, 212h
0x18001d51a  jmp     short loc_18001D4EA
0x18001d51c  mov     rcx, [rbp+28h]; this
0x18001d520  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d527  mov     r9d, edi; char *
0x18001d52a  mov     edx, 20Fh; void *
0x18001d52f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d534  jmp     short loc_18001D507
0x18001d536  lea     rcx, [rbp+var_10]
0x18001d53a  mov     [rbp+var_10], 0
0x18001d542  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d547  lea     rax, [rbp+arg_8]
0x18001d54b  mov     rcx, r14; struct IXMLDOMNode *
0x18001d54e  lea     r9, [rbp+arg_10]; int *
0x18001d552  mov     [rsp+40h+var_20], rax; int
0x18001d557  lea     r8, [rbp+var_10]; struct IXMLDOMNodeList **
0x18001d55b  lea     rdx, aMAppxprovision_0; "m:AppxProvisionList/m:EndOfLife/m:Packa"...
0x18001d562  call    ?GetNodesList@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMNodeList@@PEAJPEA_N@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetNodesList(IXMLDOMNode *,ushort const *,IXMLDOMNodeList * *,long *,bool *)
0x18001d567  cmp     byte ptr [rbp+arg_8], 0
0x18001d56b  jz      loc_18001D649
0x18001d571  mov     rbx, [rbp+var_10]
0x18001d575  xor     esi, esi
0x18001d577  cmp     esi, [rbp+arg_10]
0x18001d57a  jge     loc_18001D649
0x18001d580  mov     [rbp+arg_8], 0
0x18001d588  lea     rcx, [rbp+arg_8]
0x18001d58c  mov     rax, [rbx]
0x18001d58f  mov     rdi, [rax+38h]
0x18001d593  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d598  lea     r8, [rbp+arg_8]
0x18001d59c  mov     edx, esi
0x18001d59e  mov     rcx, rbx
0x18001d5a1  mov     rax, rdi
0x18001d5a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5a9  mov     edi, eax
0x18001d5ab  test    eax, eax
0x18001d5ad  js      short loc_18001D628
0x18001d5af  mov     rcx, [rbp+arg_8]
0x18001d5b3  lea     rdx, [rbp+bstrString]
0x18001d5b7  mov     [rbp+bstrString], 0
0x18001d5bf  mov     rax, [rcx]
0x18001d5c2  mov     rax, [rax+0D0h]
0x18001d5c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d5ce  mov     edi, eax
0x18001d5d0  test    eax, eax
0x18001d5d2  js      short loc_18001D621
0x18001d5d4  mov     rcx, [rbp+bstrString]; unsigned __int16 *
0x18001d5d8  call    ?ValidatePackageFamilyName@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEBG@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageFamilyName(ushort const *)
0x18001d5dd  mov     edi, eax
0x18001d5df  test    eax, eax
0x18001d5e1  js      short loc_18001D5FD
0x18001d5e3  mov     rcx, [rbp+bstrString]; bstrString
0x18001d5e7  call    cs:__imp_SysFreeString
0x18001d5ed  lea     rcx, [rbp+arg_8]
0x18001d5f1  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d5f6  inc     esi
0x18001d5f8  jmp     loc_18001D577
0x18001d5fd  mov     edx, 222h; void *
0x18001d602  mov     rcx, [rbp+28h]; this
0x18001d606  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d60d  mov     r9d, edi; char *
0x18001d610  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d615  mov     rcx, [rbp+bstrString]; bstrString
0x18001d619  call    cs:__imp_SysFreeString
0x18001d61f  jmp     short loc_18001D640
0x18001d621  mov     edx, 221h
0x18001d626  jmp     short loc_18001D602
0x18001d628  mov     rcx, [rbp+28h]; this
0x18001d62c  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d633  mov     r9d, edi; char *
0x18001d636  mov     edx, 21Eh; void *
0x18001d63b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d640  lea     rcx, [rbp+arg_8]
0x18001d644  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d649  lea     rcx, [rbp+var_10]
0x18001d64d  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d652  lea     rcx, [rbp+arg_18]
0x18001d656  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d65b  mov     eax, edi
0x18001d65d  add     rsp, 40h
0x18001d661  pop     r14
0x18001d663  pop     rdi
0x18001d664  pop     rsi
0x18001d665  pop     rbx
0x18001d666  pop     rbp
0x18001d667  retn
```
