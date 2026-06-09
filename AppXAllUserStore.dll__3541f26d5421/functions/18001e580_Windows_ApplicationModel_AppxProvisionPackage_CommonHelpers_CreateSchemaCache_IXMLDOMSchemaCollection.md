# Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateSchemaCache(IXMLDOMSchemaCollection * *)

- ea: `0x18001e580`
- end: `0x18001e72e`
- name: `?CreateSchemaCache@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEAPEAUIXMLDOMSchemaCollection@@@Z`
- size: `430`
- prototype: `__int64 __fastcall(LPVOID *)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001d92c`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001df14`
- `0x18001e580`
- `0x18001e734`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e5fd`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001e5fd`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e63a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001e63a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e64a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e6d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e6f8`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e64a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e6d5`
- `OLEAUT32!__imp_SysFreeString` at `0x18001e6f8`
- `OLEAUT32!__imp_VariantClear` at `0x18001e654`
- `OLEAUT32!__imp_VariantClear` at `0x18001e702`
- `OLEAUT32!__imp_VariantClear` at `0x18001e654`
- `OLEAUT32!__imp_VariantClear` at `0x18001e702`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001e6aa`
- `OLEAUT32!__imp_GetErrorInfo` at `0x18001e6aa`

## string_xrefs

- `0x18001e633`: `http://schemas.microsoft.com/appx/2013/appxprovisionpackage`
- `0x18001e5b6`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001e60d`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateSchemaCache(LPVOID *a1)
{
  const unsigned __int16 *v2; // rcx
  int XmlDomOnString; // eax
  unsigned int v4; // ebx
  HRESULT v5; // eax
  BSTR v6; // rax
  OLECHAR *v7; // rbx
  BSTR v8; // rdx
  __int64 v9; // rax
  int v10; // edi
  BSTR bstrString; // [rsp+30h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v14; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  LPVOID ppv; // [rsp+98h] [rbp+28h] BYREF
  struct IDispatch *v17; // [rsp+A0h] [rbp+30h] BYREF
  IErrorInfo *pperrinfo; // [rsp+A8h] [rbp+38h] BYREF

  v17 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v17);
  XmlDomOnString = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDomOnString(
                     v2,
                     (struct IXMLDOMDocument2 **)&v17);
  v4 = XmlDomOnString;
  if ( XmlDomOnString >= 0 )
  {
    ppv = 0;
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&ppv);
    v5 = CoCreateInstance(
           &GUID_88d96a07_f192_11d4_a65f_0040963251e5,
           0,
           1u,
           &GUID_373984c8_b845_449b_91e7_45ac83036ade,
           &ppv);
    v4 = v5;
    if ( v5 >= 0 )
    {
      Common::AutoVariant::AutoVariant((Common::AutoVariant *)&pvarg, v17);
      v6 = SysAllocString(L"http://schemas.microsoft.com/appx/2013/appxprovisionpackage");
      v7 = v6;
      if ( v6 )
      {
        v8 = v6;
        v9 = *(_QWORD *)ppv;
        v14 = pvarg;
        v10 = (*(__int64 (__fastcall **)(LPVOID, BSTR, VARIANTARG *))(v9 + 56))(ppv, v8, &v14);
        if ( v10 >= 0 )
        {
          *a1 = ppv;
          ppv = 0;
        }
        else
        {
          pperrinfo = 0;
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&pperrinfo);
          GetErrorInfo(0, &pperrinfo);
          if ( pperrinfo )
          {
            bstrString = 0;
            ((void (__fastcall *)(IErrorInfo *, BSTR *))pperrinfo->lpVtbl->GetDescription)(pperrinfo, &bstrString);
            SysFreeString(bstrString);
          }
          Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&pperrinfo);
        }
        SysFreeString(v7);
        VariantClear(&pvarg);
        v4 = v10;
      }
      else
      {
        SysFreeString(0);
        VariantClear(&pvarg);
        v4 = -2147024882;
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x66,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
        (const char *)(unsigned int)v5);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&ppv);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x5F,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
      (const char *)(unsigned int)XmlDomOnString);
  }
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v17);
  return v4;
}

```

## disassembly

```asm
0x18001e580  mov     [rsp-18h+arg_0], rbx
0x18001e585  push    rbp
0x18001e586  push    rsi
0x18001e587  push    rdi
0x18001e588  mov     rbp, rsp
0x18001e58b  sub     rsp, 70h
0x18001e58f  mov     rsi, rcx
0x18001e592  mov     [rbp+arg_10], 0
0x18001e59a  lea     rcx, [rbp+arg_10]
0x18001e59e  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001e5a3  lea     rdx, [rbp+arg_10]; struct IXMLDOMDocument2 **
0x18001e5a7  call    ?CreateXmlDomOnString@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEBGPEAPEAUIXMLDOMDocument2@@@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDomOnString(ushort const *,IXMLDOMDocument2 * *)
0x18001e5ac  mov     ebx, eax
0x18001e5ae  test    eax, eax
0x18001e5b0  jns     short loc_18001E5CF
0x18001e5b2  mov     rcx, [rbp+18h]; this
0x18001e5b6  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001e5bd  mov     r9d, eax; char *
0x18001e5c0  mov     edx, 5Fh ; '_'; void *
0x18001e5c5  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e5ca  jmp     loc_18001E713
0x18001e5cf  lea     rcx, [rbp+arg_8]
0x18001e5d3  mov     [rbp+arg_8], 0
0x18001e5db  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001e5e0  xor     edx, edx; pUnkOuter
0x18001e5e2  lea     rax, [rbp+arg_8]
0x18001e5e6  lea     r9, _GUID_373984c8_b845_449b_91e7_45ac83036ade; riid
0x18001e5ed  mov     [rsp+70h+ppv], rax; int
0x18001e5f2  lea     rcx, _GUID_88d96a07_f192_11d4_a65f_0040963251e5; rclsid
0x18001e5f9  lea     r8d, [rdx+1]; dwClsContext
0x18001e5fd  call    cs:__imp_CoCreateInstance
0x18001e603  mov     ebx, eax
0x18001e605  test    eax, eax
0x18001e607  jns     short loc_18001E626
0x18001e609  mov     rcx, [rbp+18h]; this
0x18001e60d  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001e614  mov     r9d, eax; char *
0x18001e617  mov     edx, 66h ; 'f'; void *
0x18001e61c  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001e621  jmp     loc_18001E70A
0x18001e626  mov     rdx, [rbp+arg_10]; struct IDispatch *
0x18001e62a  lea     rcx, [rbp+pvarg]; this
0x18001e62e  call    ??0AutoVariant@Common@@QEAA@PEAUIDispatch@@@Z; Common::AutoVariant::AutoVariant(IDispatch *)
0x18001e633  lea     rcx, aHttpSchemasMic; "http://schemas.microsoft.com/appx/2013/"...
0x18001e63a  call    cs:__imp_SysAllocString
0x18001e640  mov     rbx, rax
0x18001e643  test    rax, rax
0x18001e646  jnz     short loc_18001E664
0x18001e648  xor     ecx, ecx; bstrString
0x18001e64a  call    cs:__imp_SysFreeString
0x18001e650  lea     rcx, [rbp+pvarg]; pvarg
0x18001e654  call    cs:__imp_VariantClear
0x18001e65a  mov     ebx, 8007000Eh
0x18001e65f  jmp     loc_18001E70A
0x18001e664  mov     rcx, [rbp+arg_8]
0x18001e668  lea     r8, [rbp+var_20]
0x18001e66c  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001e670  mov     rdx, rbx
0x18001e673  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001e678  mov     rax, [rcx]
0x18001e67b  movaps  [rbp+var_20], xmm0
0x18001e67f  movsd   [rbp+var_10], xmm1
0x18001e684  mov     rax, [rax+38h]
0x18001e688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e68d  mov     edi, eax
0x18001e68f  test    eax, eax
0x18001e691  jns     short loc_18001E6E6
0x18001e693  lea     rcx, [rbp+pperrinfo]
0x18001e697  mov     [rbp+pperrinfo], 0
0x18001e69f  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001e6a4  lea     rdx, [rbp+pperrinfo]; pperrinfo
0x18001e6a8  xor     ecx, ecx; dwReserved
0x18001e6aa  call    cs:__imp_GetErrorInfo
0x18001e6b0  mov     rcx, [rbp+pperrinfo]
0x18001e6b4  test    rcx, rcx
0x18001e6b7  jz      short loc_18001E6DB
0x18001e6b9  mov     [rbp+bstrString], 0
0x18001e6c1  lea     rdx, [rbp+bstrString]
0x18001e6c5  mov     rax, [rcx]
0x18001e6c8  mov     rax, [rax+28h]
0x18001e6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d1  mov     rcx, [rbp+bstrString]; bstrString
0x18001e6d5  call    cs:__imp_SysFreeString
0x18001e6db  lea     rcx, [rbp+pperrinfo]
0x18001e6df  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001e6e4  jmp     short loc_18001E6F5
0x18001e6e6  mov     rax, [rbp+arg_8]
0x18001e6ea  mov     [rsi], rax
0x18001e6ed  mov     [rbp+arg_8], 0
0x18001e6f5  mov     rcx, rbx; bstrString
0x18001e6f8  call    cs:__imp_SysFreeString
0x18001e6fe  lea     rcx, [rbp+pvarg]; pvarg
0x18001e702  call    cs:__imp_VariantClear
0x18001e708  mov     ebx, edi
0x18001e70a  lea     rcx, [rbp+arg_8]
0x18001e70e  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001e713  lea     rcx, [rbp+arg_10]
0x18001e717  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001e71c  mov     eax, ebx
0x18001e71e  mov     rbx, [rsp+70h+arg_0]
0x18001e726  add     rsp, 70h
0x18001e72a  pop     rdi
0x18001e72b  pop     rsi
0x18001e72c  pop     rbp
0x18001e72d  retn
```
