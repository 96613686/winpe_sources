# Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDomFromFile(ushort const *,IXMLDOMDocument2 * *)

- ea: `0x18001c45c`
- end: `0x18001c61b`
- name: `?CreateXmlDomFromFile@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEBGPEAPEAUIXMLDOMDocument2@@@Z`
- size: `447`
- prototype: `__int64 __fastcall(OLECHAR *psz, struct IXMLDOMDocument2 **)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001db28`

## callees

- `0x180017f50`
- `0x18001c45c`
- `0x18001ca24`
- `0x18001d404`
- `0x18001d92c`
- `0x180048ae8`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001c4cd`
- `OLEAUT32!__imp_SysAllocString` at `0x18001c4cd`
- `OLEAUT32!__imp_VariantClear` at `0x18001c50a`
- `OLEAUT32!__imp_VariantClear` at `0x18001c578`
- `OLEAUT32!__imp_VariantClear` at `0x18001c5f4`
- `OLEAUT32!__imp_VariantClear` at `0x18001c50a`
- `OLEAUT32!__imp_VariantClear` at `0x18001c578`
- `OLEAUT32!__imp_VariantClear` at `0x18001c5f4`

## string_xrefs

- `0x18001c498`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001c554`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001c5ba`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDomFromFile(
        OLECHAR *psz,
        struct IXMLDOMDocument2 **a2)
{
  int v4; // eax
  unsigned int v5; // ebx
  VARTYPE vt; // ax
  struct IXMLDOMDocument2 *v7; // rbx
  struct IXMLDOMDocument2Vtbl *lpVtbl; // rax
  int v9; // eax
  int v10; // edi
  HRESULT (__stdcall *validate)(IXMLDOMDocument2 *, IXMLDOMParseError **); // rdi
  __int64 v12; // rdx
  struct IXMLDOMDocument2 *v14; // [rsp+20h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+28h] [rbp-38h] BYREF
  VARIANTARG v16; // [rsp+40h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+28h]
  __int16 v18; // [rsp+A0h] [rbp+40h] BYREF
  __int64 v19; // [rsp+A8h] [rbp+48h] BYREF

  v14 = 0;
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v14);
  v4 = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDom(&v14);
  v5 = v4;
  if ( v4 >= 0 )
  {
    pvarg.vt = 0;
    Common::AutoVariant::InternalClear((Common::AutoVariant *)&pvarg);
    pvarg.vt = 8;
    pvarg.llVal = (LONGLONG)SysAllocString(psz);
    v5 = -2147024882;
    if ( pvarg.llVal || !psz )
    {
      vt = pvarg.vt;
    }
    else
    {
      vt = 10;
      pvarg.lVal = -2147024882;
      pvarg.vt = 10;
    }
    if ( vt != 8 )
    {
      VariantClear(&pvarg);
      goto LABEL_21;
    }
    v7 = v14;
    v18 = 0;
    lpVtbl = v14->lpVtbl;
    v16 = pvarg;
    v9 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, VARIANTARG *, __int16 *))lpVtbl->load)(v14, &v16, &v18);
    v10 = v9;
    if ( v9 < 0 )
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0xEB,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
        (const char *)(unsigned int)v9);
LABEL_20:
      VariantClear(&pvarg);
      v5 = v10;
      goto LABEL_21;
    }
    if ( !v18 )
    {
      VariantClear(&pvarg);
      v5 = -2147418113;
      goto LABEL_21;
    }
    v19 = 0;
    validate = v7->lpVtbl->validate;
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
    v10 = ((__int64 (__fastcall *)(struct IXMLDOMDocument2 *, __int64 *))validate)(v7, &v19);
    if ( v10 >= 0 )
    {
      v10 = Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageNames(v7);
      if ( v10 >= 0 )
      {
        v14 = 0;
        *a2 = v7;
        goto LABEL_19;
      }
      v12 = 246;
    }
    else
    {
      v12 = 243;
    }
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v12,
      (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
      (const char *)(unsigned int)v10);
LABEL_19:
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
    goto LABEL_20;
  }
  wil::details::in1diag3::_Log_Hr(
    retaddr,
    (void *)0xE4,
    (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
    (const char *)(unsigned int)v4);
LABEL_21:
  Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v14);
  return v5;
}

```

## disassembly

```asm
0x18001c45c  mov     [rsp-28h+arg_0], rbx
0x18001c461  push    rbp
0x18001c462  push    rsi
0x18001c463  push    rdi
0x18001c464  push    r14
0x18001c466  push    r15
0x18001c468  mov     rbp, rsp
0x18001c46b  sub     rsp, 60h
0x18001c46f  mov     rdi, rcx
0x18001c472  xor     r14d, r14d
0x18001c475  lea     rcx, [rbp+var_40]
0x18001c479  mov     [rbp+var_40], r14
0x18001c47d  mov     rsi, rdx
0x18001c480  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001c485  lea     rcx, [rbp+var_40]; struct IXMLDOMDocument2 **
0x18001c489  call    ?CreateXmlDom@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAPEAUIXMLDOMDocument2@@@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::CreateXmlDom(IXMLDOMDocument2 * *)
0x18001c48e  mov     ebx, eax
0x18001c490  test    eax, eax
0x18001c492  jns     short loc_18001C4B1
0x18001c494  mov     rcx, [rbp+28h]; this
0x18001c498  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001c49f  mov     r9d, eax; char *
0x18001c4a2  mov     edx, 0E4h; void *
0x18001c4a7  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c4ac  jmp     loc_18001C5FC
0x18001c4b1  lea     rcx, [rbp+pvarg]; this
0x18001c4b5  mov     word ptr [rbp+pvarg], r14w
0x18001c4ba  call    ?InternalClear@AutoVariant@Common@@IEAAJXZ; Common::AutoVariant::InternalClear(void)
0x18001c4bf  mov     r15d, 8
0x18001c4c5  mov     rcx, rdi; psz
0x18001c4c8  mov     word ptr [rbp+pvarg], r15w
0x18001c4cd  call    cs:__imp_SysAllocString
0x18001c4d3  mov     rcx, rax
0x18001c4d6  mov     dword ptr [rbp+pvarg+8], eax
0x18001c4d9  sar     rcx, 20h
0x18001c4dd  mov     ebx, 8007000Eh
0x18001c4e2  mov     dword ptr [rbp+pvarg+0Ch], ecx
0x18001c4e5  test    rax, rax
0x18001c4e8  jnz     short loc_18001C4FC
0x18001c4ea  test    rdi, rdi
0x18001c4ed  jz      short loc_18001C4FC
0x18001c4ef  lea     eax, [r15+2]
0x18001c4f3  mov     dword ptr [rbp+pvarg+8], ebx
0x18001c4f6  mov     word ptr [rbp+pvarg], ax
0x18001c4fa  jmp     short loc_18001C500
0x18001c4fc  movzx   eax, word ptr [rbp+pvarg]
0x18001c500  cmp     ax, r15w
0x18001c504  jz      short loc_18001C515
0x18001c506  lea     rcx, [rbp+pvarg]; pvarg
0x18001c50a  call    cs:__imp_VariantClear
0x18001c510  jmp     loc_18001C5FC
0x18001c515  mov     rbx, [rbp+var_40]
0x18001c519  lea     r8, [rbp+arg_10]
0x18001c51d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001c521  lea     rdx, [rbp+var_20]
0x18001c525  mov     [rbp+arg_10], r14w
0x18001c52a  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001c52f  mov     rcx, rbx
0x18001c532  mov     rax, [rbx]
0x18001c535  movaps  [rbp+var_20], xmm0
0x18001c539  movsd   [rbp+var_10], xmm1
0x18001c53e  mov     rax, [rax+1D0h]
0x18001c545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c54a  mov     edi, eax
0x18001c54c  test    eax, eax
0x18001c54e  jns     short loc_18001C56D
0x18001c550  mov     rcx, [rbp+28h]; this
0x18001c554  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001c55b  mov     r9d, eax; char *
0x18001c55e  mov     edx, 0EBh; void *
0x18001c563  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c568  jmp     loc_18001C5F0
0x18001c56d  cmp     [rbp+arg_10], r14w
0x18001c572  jnz     short loc_18001C585
0x18001c574  lea     rcx, [rbp+pvarg]; pvarg
0x18001c578  call    cs:__imp_VariantClear
0x18001c57e  mov     ebx, 8000FFFFh
0x18001c583  jmp     short loc_18001C5FC
0x18001c585  mov     [rbp+arg_18], r14
0x18001c589  lea     rcx, [rbp+arg_18]
0x18001c58d  mov     rax, [rbx]
0x18001c590  mov     rdi, [rax+278h]
0x18001c597  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001c59c  lea     rdx, [rbp+arg_18]
0x18001c5a0  mov     rcx, rbx
0x18001c5a3  mov     rax, rdi
0x18001c5a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001c5ab  mov     edi, eax
0x18001c5ad  test    eax, eax
0x18001c5af  jns     short loc_18001C5CB
0x18001c5b1  mov     edx, 0F3h; void *
0x18001c5b6  mov     rcx, [rbp+28h]; this
0x18001c5ba  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001c5c1  mov     r9d, edi; char *
0x18001c5c4  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001c5c9  jmp     short loc_18001C5E7
0x18001c5cb  mov     rcx, rbx; struct IXMLDOMDocument2 *
0x18001c5ce  call    ?ValidatePackageNames@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@CAJPEAUIXMLDOMDocument2@@@Z; Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::ValidatePackageNames(IXMLDOMDocument2 *)
0x18001c5d3  mov     edi, eax
0x18001c5d5  test    eax, eax
0x18001c5d7  jns     short loc_18001C5E0
0x18001c5d9  mov     edx, 0F6h
0x18001c5de  jmp     short loc_18001C5B6
0x18001c5e0  mov     [rbp+var_40], r14
0x18001c5e4  mov     [rsi], rbx
0x18001c5e7  lea     rcx, [rbp+arg_18]
0x18001c5eb  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001c5f0  lea     rcx, [rbp+pvarg]; pvarg
0x18001c5f4  call    cs:__imp_VariantClear
0x18001c5fa  mov     ebx, edi
0x18001c5fc  lea     rcx, [rbp+var_40]
0x18001c600  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001c605  mov     eax, ebx
0x18001c607  mov     rbx, [rsp+60h+arg_0]
0x18001c60f  add     rsp, 60h
0x18001c613  pop     r15
0x18001c615  pop     r14
0x18001c617  pop     rdi
0x18001c618  pop     rsi
0x18001c619  pop     rbp
0x18001c61a  retn
```
