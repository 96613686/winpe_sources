# Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::AddPackageToList(ProvisionPackageList,IAppxProvisionPackage *)

- ea: `0x18001ca50`
- end: `0x18001cdf9`
- name: `?AddPackageToList@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@UEAAJW4ProvisionPackageList@@PEAUIAppxProvisionPackage@@@Z`
- size: `937`
- prototype: `__int64 __fastcall(struct IXMLDOMNode **, int, __int64 *)`
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001ca50`
- `0x18001ce00`
- `0x18001d670`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cde4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd05`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cd1d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001cde4`

## string_xrefs

- `0x18001cab6`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001cb20`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001cb6f`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001cbb7`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001ccf2`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001cd80`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001cdc3`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::AddPackageToList(
        struct IXMLDOMNode **a1,
        int a2,
        __int64 *a3)
{
  int v6; // edx
  __int64 v7; // rax
  int v8; // edi
  __int64 v9; // rdx
  void *v10; // rcx
  __int64 v11; // rax
  int v12; // eax
  int v13; // ebx
  void *v14; // rcx
  int ChildElement; // eax
  struct IXMLDOMElement *v16; // rbx
  __int64 v17; // rdx
  char v18; // al
  __int64 v19; // rax
  __int64 v20; // rdx
  int v21; // eax
  int Attribute; // eax
  struct IXMLDOMElement *v23[2]; // [rsp+20h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+18h]
  LPVOID pv; // [rsp+60h] [rbp+30h] BYREF
  struct IXMLDOMElement *v26; // [rsp+68h] [rbp+38h] BYREF

  if ( !a3 )
    return 2147500035LL;
  v6 = a2 - 1;
  if ( !v6 )
  {
    v19 = *a3;
    pv = 0;
    v13 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v19 + 32))(a3, &pv);
    if ( v13 >= 0 )
    {
      if ( !pv )
        goto LABEL_45;
      v13 = ((__int64 (__fastcall *)(struct IXMLDOMNode **, __int64))(*a1)[4].lpVtbl)(a1, 1);
      if ( v13 >= 0 )
      {
        v26 = 0;
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v26);
        v21 = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(
                (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                a1[6],
                L"Package",
                &v26);
        v13 = v21;
        if ( v21 >= 0 )
        {
          Attribute = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
                        (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                        v26,
                        L"FamilyName",
                        (const unsigned __int16 *)pv);
          v8 = Attribute;
          if ( Attribute < 0 )
            wil::details::in1diag3::_Log_Hr(
              retaddr,
              (void *)0x86,
              (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
              (const char *)(unsigned int)Attribute);
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v26);
          v10 = pv;
          goto LABEL_53;
        }
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x85,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
          (const char *)(unsigned int)v21);
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v26);
        goto LABEL_42;
      }
      v20 = 129;
    }
    else
    {
      v20 = 125;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v20,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
      (const char *)(unsigned int)v13);
LABEL_42:
    v14 = pv;
    goto LABEL_43;
  }
  if ( v6 != 1 )
    return 2147549183LL;
  v7 = *a3;
  v26 = 0;
  v8 = (*(__int64 (__fastcall **)(__int64 *, struct IXMLDOMElement **))(v7 + 24))(a3, &v26);
  if ( v8 >= 0 )
  {
    if ( v26 )
    {
      v8 = ((__int64 (__fastcall *)(struct IXMLDOMNode **, __int64))(*a1)[4].lpVtbl)(a1, 2);
      if ( v8 < 0 )
      {
        v9 = 145;
        goto LABEL_8;
      }
      v11 = *a3;
      LODWORD(pv) = 0;
      v12 = (*(__int64 (__fastcall **)(__int64 *, LPVOID *))(v11 + 40))(a3, &pv);
      v13 = v12;
      if ( v12 < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x95,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
          (const char *)(unsigned int)v12);
LABEL_15:
        v14 = v26;
LABEL_43:
        CoTaskMemFree(v14);
        return (unsigned int)v13;
      }
      v23[0] = 0;
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v23);
      ChildElement = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(
                       (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                       a1[7],
                       L"Package",
                       v23);
      v13 = ChildElement;
      if ( ChildElement < 0 )
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x99,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
          (const char *)(unsigned int)ChildElement);
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v23);
        goto LABEL_15;
      }
      v16 = v23[0];
      v8 = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
             (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
             v23[0],
             L"FullName",
             (const unsigned __int16 *)v26);
      if ( v8 >= 0 )
      {
        v18 = (char)pv;
        if ( ((unsigned __int8)pv & 0x10) != 0 )
        {
          v8 = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
                 (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                 v16,
                 L"ProvisionSourceIsBundle",
                 L"true");
          if ( v8 < 0 )
          {
            v17 = 159;
            goto LABEL_20;
          }
          v18 = (char)pv;
        }
        if ( (v18 & 0x20) != 0 )
        {
          v8 = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
                 (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                 v16,
                 L"IsLOBApp",
                 L"true");
          if ( v8 < 0 )
          {
            v17 = 165;
            goto LABEL_20;
          }
          v18 = (char)pv;
        }
        if ( (v18 & 2) != 0 )
        {
          v8 = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
                 (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                 v16,
                 L"PackageType",
                 L"bundle");
          if ( v8 >= 0 )
            goto LABEL_21;
          v17 = 171;
        }
        else if ( (v18 & 8) != 0 )
        {
          v8 = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
                 (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                 v16,
                 L"PackageType",
                 L"framework");
          if ( v8 >= 0 )
            goto LABEL_21;
          v17 = 175;
        }
        else
        {
          if ( (v18 & 4) == 0 )
            goto LABEL_21;
          v8 = Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(
                 (Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *)a1,
                 v16,
                 L"PackageType",
                 L"resource");
          if ( v8 >= 0 )
            goto LABEL_21;
          v17 = 179;
        }
      }
      else
      {
        v17 = 154;
      }
LABEL_20:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v17,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
        (const char *)(unsigned int)v8);
LABEL_21:
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v23);
      goto LABEL_9;
    }
LABEL_45:
    CoTaskMemFree(0);
    return 2147942487LL;
  }
  v9 = 141;
LABEL_8:
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)v9,
    (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
    (const char *)(unsigned int)v8);
LABEL_9:
  v10 = v26;
LABEL_53:
  CoTaskMemFree(v10);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18001ca50  mov     [rsp-18h+arg_0], rbx
0x18001ca55  push    rbp
0x18001ca56  push    rsi
0x18001ca57  push    rdi
0x18001ca58  mov     rbp, rsp
0x18001ca5b  sub     rsp, 30h
0x18001ca5f  mov     rbx, r8
0x18001ca62  mov     rsi, rcx
0x18001ca65  test    r8, r8
0x18001ca68  jnz     short loc_18001CA74
0x18001ca6a  mov     eax, 80004003h
0x18001ca6f  jmp     loc_18001CDEC
0x18001ca74  sub     edx, 1
0x18001ca77  jz      loc_18001CCC8
0x18001ca7d  cmp     edx, 1
0x18001ca80  jz      short loc_18001CA8C
0x18001ca82  mov     eax, 8000FFFFh
0x18001ca87  jmp     loc_18001CDEC
0x18001ca8c  mov     rax, [r8]
0x18001ca8f  lea     rdx, [rbp+arg_18]
0x18001ca93  mov     rcx, rbx
0x18001ca96  mov     [rbp+arg_18], 0
0x18001ca9e  mov     rax, [rax+18h]
0x18001caa2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caa7  mov     edi, eax
0x18001caa9  test    eax, eax
0x18001caab  jns     short loc_18001CACE
0x18001caad  mov     edx, 8Dh; void *
0x18001cab2  mov     rcx, [rbp+18h]; this
0x18001cab6  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cabd  mov     r9d, edi; char *
0x18001cac0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cac5  mov     rcx, [rbp+arg_18]
0x18001cac9  jmp     loc_18001CDE4
0x18001cace  mov     r8, [rbp+arg_18]
0x18001cad2  test    r8, r8
0x18001cad5  jz      loc_18001CD1B
0x18001cadb  mov     rax, [rsi]
0x18001cade  mov     edx, 2
0x18001cae3  mov     rcx, rsi
0x18001cae6  mov     rax, [rax+20h]
0x18001caea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001caef  mov     edi, eax
0x18001caf1  test    eax, eax
0x18001caf3  jns     short loc_18001CAFC
0x18001caf5  mov     edx, 91h
0x18001cafa  jmp     short loc_18001CAB2
0x18001cafc  mov     rax, [rbx]
0x18001caff  lea     rdx, [rbp+pv]
0x18001cb03  mov     rcx, rbx
0x18001cb06  mov     dword ptr [rbp+pv], 0
0x18001cb0d  mov     rax, [rax+28h]
0x18001cb11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cb16  mov     ebx, eax
0x18001cb18  test    eax, eax
0x18001cb1a  jns     short loc_18001CB3D
0x18001cb1c  mov     rcx, [rbp+18h]; this
0x18001cb20  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cb27  mov     r9d, eax; char *
0x18001cb2a  mov     edx, 95h; void *
0x18001cb2f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cb34  mov     rcx, [rbp+arg_18]
0x18001cb38  jmp     loc_18001CD05
0x18001cb3d  lea     rcx, [rbp+var_10]
0x18001cb41  mov     [rbp+var_10], 0
0x18001cb49  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cb4e  mov     rdx, [rsi+38h]; struct IXMLDOMNode *
0x18001cb52  lea     r9, [rbp+var_10]; struct IXMLDOMElement **
0x18001cb56  lea     r8, aPackage; "Package"
0x18001cb5d  mov     rcx, rsi; this
0x18001cb60  call    ?CreateChildElement@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001cb65  mov     ebx, eax
0x18001cb67  test    eax, eax
0x18001cb69  jns     short loc_18001CB8E
0x18001cb6b  mov     rcx, [rbp+18h]; this
0x18001cb6f  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cb76  mov     r9d, eax; char *
0x18001cb79  mov     edx, 99h; void *
0x18001cb7e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cb83  lea     rcx, [rbp+var_10]
0x18001cb87  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cb8c  jmp     short loc_18001CB34
0x18001cb8e  mov     rbx, [rbp+var_10]
0x18001cb92  lea     r8, aFullname; "FullName"
0x18001cb99  mov     r9, [rbp+arg_18]; unsigned __int16 *
0x18001cb9d  mov     rdx, rbx; struct IXMLDOMElement *
0x18001cba0  mov     rcx, rsi; this
0x18001cba3  call    ?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001cba8  mov     edi, eax
0x18001cbaa  test    eax, eax
0x18001cbac  jns     short loc_18001CBD4
0x18001cbae  mov     edx, 9Ah; void *
0x18001cbb3  mov     rcx, [rbp+18h]; this
0x18001cbb7  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cbbe  mov     r9d, edi; char *
0x18001cbc1  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cbc6  lea     rcx, [rbp+var_10]
0x18001cbca  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cbcf  jmp     loc_18001CAC5
0x18001cbd4  mov     eax, dword ptr [rbp+pv]
0x18001cbd7  test    al, 10h
0x18001cbd9  jz      short loc_18001CC04
0x18001cbdb  lea     r9, aTrue; "true"
0x18001cbe2  mov     rdx, rbx; struct IXMLDOMElement *
0x18001cbe5  lea     r8, aProvisionsourc; "ProvisionSourceIsBundle"
0x18001cbec  mov     rcx, rsi; this
0x18001cbef  call    ?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001cbf4  mov     edi, eax
0x18001cbf6  test    eax, eax
0x18001cbf8  jns     short loc_18001CC01
0x18001cbfa  mov     edx, 9Fh
0x18001cbff  jmp     short loc_18001CBB3
0x18001cc01  mov     eax, dword ptr [rbp+pv]
0x18001cc04  test    al, 20h
0x18001cc06  jz      short loc_18001CC31
0x18001cc08  lea     r9, aTrue; "true"
0x18001cc0f  mov     rdx, rbx; struct IXMLDOMElement *
0x18001cc12  lea     r8, aIslobapp; "IsLOBApp"
0x18001cc19  mov     rcx, rsi; this
0x18001cc1c  call    ?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001cc21  mov     edi, eax
0x18001cc23  test    eax, eax
0x18001cc25  jns     short loc_18001CC2E
0x18001cc27  mov     edx, 0A5h
0x18001cc2c  jmp     short loc_18001CBB3
0x18001cc2e  mov     eax, dword ptr [rbp+pv]
0x18001cc31  test    al, 2
0x18001cc33  jz      short loc_18001CC62
0x18001cc35  lea     r9, aBundle; "bundle"
0x18001cc3c  mov     rdx, rbx; struct IXMLDOMElement *
0x18001cc3f  lea     r8, aPackagetype_0; "PackageType"
0x18001cc46  mov     rcx, rsi; this
0x18001cc49  call    ?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001cc4e  mov     edi, eax
0x18001cc50  test    eax, eax
0x18001cc52  jns     loc_18001CBC6
0x18001cc58  mov     edx, 0ABh
0x18001cc5d  jmp     loc_18001CBB3
0x18001cc62  test    al, 8
0x18001cc64  jz      short loc_18001CC93
0x18001cc66  lea     r9, aFramework_0; "framework"
0x18001cc6d  mov     rdx, rbx; struct IXMLDOMElement *
0x18001cc70  lea     r8, aPackagetype_0; "PackageType"
0x18001cc77  mov     rcx, rsi; this
0x18001cc7a  call    ?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001cc7f  mov     edi, eax
0x18001cc81  test    eax, eax
0x18001cc83  jns     loc_18001CBC6
0x18001cc89  mov     edx, 0AFh
0x18001cc8e  jmp     loc_18001CBB3
0x18001cc93  test    al, 4
0x18001cc95  jz      loc_18001CBC6
0x18001cc9b  lea     r9, aResource; "resource"
0x18001cca2  mov     rdx, rbx; struct IXMLDOMElement *
0x18001cca5  lea     r8, aPackagetype_0; "PackageType"
0x18001ccac  mov     rcx, rsi; this
0x18001ccaf  call    ?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001ccb4  mov     edi, eax
0x18001ccb6  test    eax, eax
0x18001ccb8  jns     loc_18001CBC6
0x18001ccbe  mov     edx, 0B3h
0x18001ccc3  jmp     loc_18001CBB3
0x18001ccc8  mov     rax, [r8]
0x18001cccb  lea     rdx, [rbp+pv]
0x18001cccf  mov     rcx, rbx
0x18001ccd2  mov     [rbp+pv], 0
0x18001ccda  mov     rax, [rax+20h]
0x18001ccde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cce3  mov     ebx, eax
0x18001cce5  test    eax, eax
0x18001cce7  jns     short loc_18001CD12
0x18001cce9  mov     edx, 7Dh ; '}'; void *
0x18001ccee  mov     rcx, [rbp+18h]; this
0x18001ccf2  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001ccf9  mov     r9d, ebx; char *
0x18001ccfc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cd01  mov     rcx, [rbp+pv]; pv
0x18001cd05  call    cs:__imp_CoTaskMemFree
0x18001cd0b  mov     eax, ebx
0x18001cd0d  jmp     loc_18001CDEC
0x18001cd12  mov     r8, [rbp+pv]
0x18001cd16  test    r8, r8
0x18001cd19  jnz     short loc_18001CD2D
0x18001cd1b  xor     ecx, ecx; pv
0x18001cd1d  call    cs:__imp_CoTaskMemFree
0x18001cd23  mov     eax, 80070057h
0x18001cd28  jmp     loc_18001CDEC
0x18001cd2d  mov     rax, [rsi]
0x18001cd30  mov     edx, 1
0x18001cd35  mov     rcx, rsi
0x18001cd38  mov     rax, [rax+20h]
0x18001cd3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001cd41  mov     ebx, eax
0x18001cd43  test    eax, eax
0x18001cd45  jns     short loc_18001CD4E
0x18001cd47  mov     edx, 81h
0x18001cd4c  jmp     short loc_18001CCEE
0x18001cd4e  lea     rcx, [rbp+arg_18]
0x18001cd52  mov     [rbp+arg_18], 0
0x18001cd5a  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cd5f  mov     rdx, [rsi+30h]; struct IXMLDOMNode *
0x18001cd63  lea     r9, [rbp+arg_18]; struct IXMLDOMElement **
0x18001cd67  lea     r8, aPackage; "Package"
0x18001cd6e  mov     rcx, rsi; this
0x18001cd71  call    ?CreateChildElement@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *)
0x18001cd76  mov     ebx, eax
0x18001cd78  test    eax, eax
0x18001cd7a  jns     short loc_18001CDA2
0x18001cd7c  mov     rcx, [rbp+18h]; this
0x18001cd80  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cd87  mov     r9d, eax; char *
0x18001cd8a  mov     edx, 85h; void *
0x18001cd8f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cd94  lea     rcx, [rbp+arg_18]
0x18001cd98  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cd9d  jmp     loc_18001CD01
0x18001cda2  mov     r9, [rbp+pv]; unsigned __int16 *
0x18001cda6  lea     r8, aFamilyname_0; "FamilyName"
0x18001cdad  mov     rdx, [rbp+arg_18]; struct IXMLDOMElement *
0x18001cdb1  mov     rcx, rsi; this
0x18001cdb4  call    ?CreateAttribute@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMElement@@PEBG1@Z; Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateAttribute(IXMLDOMElement *,ushort const *,ushort const *)
0x18001cdb9  mov     edi, eax
0x18001cdbb  test    eax, eax
0x18001cdbd  jns     short loc_18001CDD7
0x18001cdbf  mov     rcx, [rbp+18h]; this
0x18001cdc3  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001cdca  mov     r9d, eax; char *
0x18001cdcd  mov     edx, 86h; void *
0x18001cdd2  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001cdd7  lea     rcx, [rbp+arg_18]
0x18001cddb  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001cde0  mov     rcx, [rbp+pv]; pv
0x18001cde4  call    cs:__imp_CoTaskMemFree
0x18001cdea  mov     eax, edi
0x18001cdec  mov     rbx, [rsp+30h+arg_0]
0x18001cdf1  add     rsp, 30h
0x18001cdf5  pop     rdi
0x18001cdf6  pop     rsi
0x18001cdf7  pop     rbp
0x18001cdf8  retn
```
