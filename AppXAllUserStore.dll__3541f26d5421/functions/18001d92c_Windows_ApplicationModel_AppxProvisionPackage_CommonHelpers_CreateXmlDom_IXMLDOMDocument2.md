# Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDom(IXMLDOMDocument2 * *)

- ea: `0x18001d92c`
- end: `0x18001db22`
- name: `?CreateXmlDom@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAPEAUIXMLDOMDocument2@@@Z`
- size: `502`
- prototype: `__int64 __fastcall(struct IXMLDOMDocument2 **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x18001c45c`
- `0x18001dbf4`
- `0x18001de70`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001d92c`
- `0x18001dcdc`
- `0x18001e580`
- `0x18001e734`
- `0x180048ae8`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001da39`
- `OLEAUT32!__imp_SysAllocString` at `0x18001da72`
- `OLEAUT32!__imp_SysAllocString` at `0x18001da39`
- `OLEAUT32!__imp_SysAllocString` at `0x18001da72`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dadd`
- `OLEAUT32!__imp_SysFreeString` at `0x18001dadd`
- `OLEAUT32!__imp_VariantClear` at `0x18001dae7`
- `OLEAUT32!__imp_VariantClear` at `0x18001daf3`
- `OLEAUT32!__imp_VariantClear` at `0x18001dae7`
- `OLEAUT32!__imp_VariantClear` at `0x18001daf3`

## string_xrefs

- `0x18001da2e`: `xmlns:m="http://schemas.microsoft.com/appx/2013/appxprovisionpackage"`
- `0x18001d968`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001d9a5`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001da01`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001dab9`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDom(
        struct IXMLDOMDocument2 **a1)
{
  int v2; // eax
  unsigned int v3; // ebx
  int SchemaCache; // eax
  struct IXMLDOMDocument2 *v5; // rsi
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  int v7; // eax
  int v8; // edi
  VARTYPE vt; // ax
  BSTR v10; // rax
  OLECHAR *v11; // rbx
  OLECHAR *v12; // rcx
  BSTR v13; // rdx
  HRESULT (__stdcall *setProperty)(IXMLDOMDocument2 *, BSTR, VARIANT); // rax
  int v15; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-50h] BYREF
  VARIANTARG v18; // [rsp+38h] [rbp-38h] BYREF
  VARIANTARG v19; // [rsp+50h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+18h]
  struct IXMLDOMDocument2 *v21; // [rsp+98h] [rbp+28h] BYREF
  struct IDispatch *v22; // [rsp+A0h] [rbp+30h] BYREF

  v21 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v21);
  v2 = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::InitializeXmlDom(&v21);
  v3 = v2;
  if ( v2 >= 0 )
  {
    v22 = 0;
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v22);
    SchemaCache = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateSchemaCache((LPVOID *)&v22);
    v3 = SchemaCache;
    if ( SchemaCache >= 0 )
    {
      Common::AutoVariant::AutoVariant((Common::AutoVariant *)&v18, v22);
      v5 = v21;
      lpVtbl = v21->lpVtbl;
      v19 = v18;
      v7 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *))lpVtbl->putref_schemas)(v21, &v19);
      v3 = v7;
      if ( v7 >= 0 )
      {
        pvarg.vt = 0;
        Common::AutoVariant::InternalClear((Common::AutoVariant *)&pvarg);
        pvarg.vt = 8;
        pvarg.llVal = (LONGLONG)SysAllocString(L"xmlns:m=\"http://schemas.microsoft.com/appx/2013/appxprovisionpackage\"");
        v8 = -2147024882;
        if ( pvarg.llVal )
        {
          vt = pvarg.vt;
        }
        else
        {
          vt = 10;
          pvarg.lVal = -2147024882;
          pvarg.vt = 10;
        }
        if ( vt == 8 )
        {
          v10 = SysAllocString(L"SelectionNamespaces");
          v11 = v10;
          if ( v10 )
          {
            v13 = v10;
            setProperty = v5->lpVtbl->setProperty;
            v19 = pvarg;
            v15 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, BSTR, VARIANTARG *))setProperty)(v5, v13, &v19);
            v8 = v15;
            if ( v15 >= 0 )
            {
              v21 = 0;
              *a1 = v5;
            }
            else
            {
              wil::details::in1diag3::_Log_Hr(
                retaddr,
                (void *)0xD2,
                (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
                (const char *)(unsigned int)v15);
            }
            v12 = v11;
          }
          else
          {
            v12 = 0;
          }
          SysFreeString(v12);
        }
        VariantClear(&pvarg);
        v3 = v8;
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0xCB,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
          (const char *)(unsigned int)v7);
      }
      VariantClear(&v18);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xC7,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
        (const char *)(unsigned int)SchemaCache);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v22);
  }
  else
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0xC3,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
      (const char *)(unsigned int)v2);
  }
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v21);
  return v3;
}

```

## disassembly

```asm
0x18001d92c  mov     [rsp-18h+arg_0], rbx
0x18001d931  mov     [rsp-18h+arg_18], rsi
0x18001d936  push    rbp
0x18001d937  push    rdi
0x18001d938  push    r14
0x18001d93a  mov     rbp, rsp
0x18001d93d  sub     rsp, 70h
0x18001d941  mov     r14, rcx
0x18001d944  mov     [rbp+arg_8], 0
0x18001d94c  lea     rcx, [rbp+arg_8]
0x18001d950  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d955  lea     rcx, [rbp+arg_8]; struct IXMLDOMDocument2 **
0x18001d959  call    ?InitializeXmlDom@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEAPEAUIXMLDOMDocument2@@@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::InitializeXmlDom(IXMLDOMDocument2 * *)
0x18001d95e  mov     ebx, eax
0x18001d960  test    eax, eax
0x18001d962  jns     short loc_18001D981
0x18001d964  mov     rcx, [rbp+18h]; this
0x18001d968  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d96f  mov     r9d, eax; char *
0x18001d972  mov     edx, 0C3h; void *
0x18001d977  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d97c  jmp     loc_18001DB02
0x18001d981  lea     rcx, [rbp+arg_10]
0x18001d985  mov     [rbp+arg_10], 0
0x18001d98d  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d992  lea     rcx, [rbp+arg_10]; struct IXMLDOMSchemaCollection **
0x18001d996  call    ?CreateSchemaCache@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEAPEAUIXMLDOMSchemaCollection@@@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateSchemaCache(IXMLDOMSchemaCollection * *)
0x18001d99b  mov     ebx, eax
0x18001d99d  test    eax, eax
0x18001d99f  jns     short loc_18001D9BE
0x18001d9a1  mov     rcx, [rbp+18h]; this
0x18001d9a5  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d9ac  mov     r9d, eax; char *
0x18001d9af  mov     edx, 0C7h; void *
0x18001d9b4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d9b9  jmp     loc_18001DAF9
0x18001d9be  mov     rdx, [rbp+arg_10]; struct IDispatch *
0x18001d9c2  lea     rcx, [rbp+var_38]; this
0x18001d9c6  call    ??0AutoVariant@Common@@QEAA@PEAUIDispatch@@@Z; Common::AutoVariant::AutoVariant(IDispatch *)
0x18001d9cb  mov     rsi, [rbp+arg_8]
0x18001d9cf  lea     rdx, [rbp+var_20]
0x18001d9d3  movups  xmm0, xmmword ptr [rbp+var_38]
0x18001d9d7  mov     rcx, rsi
0x18001d9da  movsd   xmm1, qword ptr [rbp+var_38+10h]
0x18001d9df  mov     rax, [rsi]
0x18001d9e2  movaps  [rbp+var_20], xmm0
0x18001d9e6  movsd   [rbp+var_10], xmm1
0x18001d9eb  mov     rax, [rax+270h]
0x18001d9f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d9f7  mov     ebx, eax
0x18001d9f9  test    eax, eax
0x18001d9fb  jns     short loc_18001DA1A
0x18001d9fd  mov     rcx, [rbp+18h]; this
0x18001da01  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001da08  mov     r9d, eax; char *
0x18001da0b  mov     edx, 0CBh; void *
0x18001da10  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001da15  jmp     loc_18001DAEF
0x18001da1a  xor     eax, eax
0x18001da1c  lea     rcx, [rbp+pvarg]; this
0x18001da20  mov     word ptr [rbp+pvarg], ax
0x18001da24  call    ?InternalClear@AutoVariant@Common@@IEAAJXZ; Common::AutoVariant::InternalClear(void)
0x18001da29  mov     ebx, 8
0x18001da2e  lea     rcx, aXmlnsMHttpSche; "xmlns:m=\"http://schemas.microsoft.com/"...
0x18001da35  mov     word ptr [rbp+pvarg], bx
0x18001da39  call    cs:__imp_SysAllocString
0x18001da3f  mov     rcx, rax
0x18001da42  mov     dword ptr [rbp+pvarg+8], eax
0x18001da45  sar     rcx, 20h
0x18001da49  mov     edi, 8007000Eh
0x18001da4e  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x18001da51  test    rax, rax
0x18001da54  jnz     short loc_18001DA62
0x18001da56  lea     eax, [rbx+2]
0x18001da59  mov     dword ptr [rbp+pvarg+8], edi
0x18001da5c  mov     word ptr [rbp+pvarg], ax
0x18001da60  jmp     short loc_18001DA66
0x18001da62  movzx   eax, word ptr [rbp+pvarg]
0x18001da66  cmp     ax, bx
0x18001da69  jnz     short loc_18001DAE3
0x18001da6b  lea     rcx, aSelectionnames; "SelectionNamespaces"
0x18001da72  call    cs:__imp_SysAllocString
0x18001da78  mov     rbx, rax
0x18001da7b  test    rax, rax
0x18001da7e  jnz     short loc_18001DA84
0x18001da80  xor     ecx, ecx
0x18001da82  jmp     short loc_18001DADD
0x18001da84  mov     rax, [rsi]
0x18001da87  lea     r8, [rbp+var_20]
0x18001da8b  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001da8f  mov     rdx, rbx
0x18001da92  mov     rcx, rsi
0x18001da95  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001da9a  mov     rax, [rax+280h]
0x18001daa1  movaps  [rbp+var_20], xmm0
0x18001daa5  movsd   [rbp+var_10], xmm1
0x18001daaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001daaf  mov     edi, eax
0x18001dab1  test    eax, eax
0x18001dab3  jns     short loc_18001DACF
0x18001dab5  mov     rcx, [rbp+18h]; this
0x18001dab9  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001dac0  mov     r9d, eax; char *
0x18001dac3  mov     edx, 0D2h; void *
0x18001dac8  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001dacd  jmp     short loc_18001DADA
0x18001dacf  mov     [rbp+arg_8], 0
0x18001dad7  mov     [r14], rsi
0x18001dada  mov     rcx, rbx; bstrString
0x18001dadd  call    cs:__imp_SysFreeString
0x18001dae3  lea     rcx, [rbp+pvarg]; pvarg
0x18001dae7  call    cs:__imp_VariantClear
0x18001daed  mov     ebx, edi
0x18001daef  lea     rcx, [rbp+var_38]; pvarg
0x18001daf3  call    cs:__imp_VariantClear
0x18001daf9  lea     rcx, [rbp+arg_10]
0x18001dafd  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001db02  lea     rcx, [rbp+arg_8]
0x18001db06  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001db0b  lea     r11, [rsp+70h+var_s0]
0x18001db10  mov     eax, ebx
0x18001db12  mov     rbx, [r11+20h]
0x18001db16  mov     rsi, [r11+38h]
0x18001db1a  mov     rsp, r11
0x18001db1d  pop     r14
0x18001db1f  pop     rdi
0x18001db20  pop     rbp
0x18001db21  retn
```
