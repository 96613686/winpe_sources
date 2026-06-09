# Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *)

- ea: `0x18001d670`
- end: `0x18001d808`
- name: `?CreateChildElement@AppxProvisionWriterImpl@AppxProvisionPackage@ApplicationModel@Windows@@AEAAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@@Z`
- size: `408`
- prototype: `__int64 __fastcall(Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *this, struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMElement **)`
- caller_count: `2`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001ca50`
- `0x18001cfb8`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001d670`
- `0x18001e284`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d691`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d691`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d6a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d7ee`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d6a1`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d7ee`
- `OLEAUT32!__imp_VariantClear` at `0x18001d7e5`
- `OLEAUT32!__imp_VariantClear` at `0x18001d7e5`

## string_xrefs

- `0x18001d71b`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001d76c`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`
- `0x18001d7a1`: `onecore\base\appmodel\appxprovisionpackage\src\appxprovisionwriter.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl::CreateChildElement(
        Windows::ApplicationModel::AppxProvisionPackage::AppxProvisionWriterImpl *this,
        struct IXMLDOMNode *a2,
        const unsigned __int16 *a3,
        struct IXMLDOMElement **a4)
{
  OLECHAR *v7; // rbx
  __int64 v9; // rsi
  __int64 (__fastcall *v10)(__int64, VARIANTARG *, OLECHAR *, __int64, int *); // rdi
  __int64 v11; // r9
  int v12; // eax
  unsigned int v13; // edi
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *appendChild)(IXMLDOMNode *, IXMLDOMNode *, IXMLDOMNode **); // rdi
  int v16; // eax
  int v17; // eax
  int v18[2]; // [rsp+30h] [rbp-50h] BYREF
  __int64 (__fastcall ***v19)(_QWORD, GUID *, __int64); // [rsp+38h] [rbp-48h] BYREF
  struct IXMLDOMElement *v20; // [rsp+40h] [rbp-40h] BYREF
  VARIANTARG pvarg; // [rsp+48h] [rbp-38h] BYREF
  VARIANTARG v22; // [rsp+60h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+38h]

  v7 = SysAllocString(a3);
  if ( v7 )
  {
    v9 = *((_QWORD *)this + 4);
    pvarg.lVal = 1;
    pvarg.vt = 3;
    *(_QWORD *)v18 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, VARIANTARG *, OLECHAR *, __int64, int *))(*(_QWORD *)v9 + 448LL);
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v18);
    v11 = *((_QWORD *)this + 3);
    v22 = pvarg;
    v12 = v10(v9, &v22, v7, v11, v18);
    v13 = v12;
    if ( v12 >= 0 )
    {
      lpVtbl = a2->lpVtbl;
      v19 = 0;
      appendChild = lpVtbl->appendChild;
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
      v16 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, _QWORD, _QWORD))appendChild)(a2, *(_QWORD *)v18, &v19);
      v13 = v16;
      if ( v16 >= 0 )
      {
        v20 = 0;
        v17 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v19, (__int64)&v20);
        v13 = v17;
        if ( v17 >= 0 )
        {
          *a4 = v20;
          v20 = 0;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x152,
            (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
            (const char *)(unsigned int)v17);
        }
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v20);
      }
      else
      {
        wil::details::in1diag3::_Log_Hr(
          retaddr,
          (void *)0x14F,
          (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
          (const char *)(unsigned int)v16);
      }
      Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v19);
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x14B,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\appxprovisionwriter.cpp",
        (const char *)(unsigned int)v12);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(v18);
    VariantClear(&pvarg);
    SysFreeString(v7);
    return v13;
  }
  else
  {
    SysFreeString(0);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x18001d670  push    rbp
0x18001d672  push    rbx
0x18001d673  push    rsi
0x18001d674  push    rdi
0x18001d675  push    r13
0x18001d677  push    r14
0x18001d679  push    r15
0x18001d67b  mov     rbp, rsp
0x18001d67e  sub     rsp, 80h
0x18001d685  mov     r13, rcx
0x18001d688  mov     r15, r9
0x18001d68b  mov     rcx, r8; psz
0x18001d68e  mov     r14, rdx
0x18001d691  call    cs:__imp_SysAllocString
0x18001d697  mov     rbx, rax
0x18001d69a  test    rax, rax
0x18001d69d  jnz     short loc_18001D6B1
0x18001d69f  xor     ecx, ecx; bstrString
0x18001d6a1  call    cs:__imp_SysFreeString
0x18001d6a7  mov     eax, 8007000Eh
0x18001d6ac  jmp     loc_18001D7F6
0x18001d6b1  mov     rsi, [r13+20h]
0x18001d6b5  lea     rcx, [rbp+var_50]
0x18001d6b9  mov     eax, 3
0x18001d6be  mov     dword ptr [rbp+pvarg+8], 1
0x18001d6c5  mov     word ptr [rbp+pvarg], ax
0x18001d6c9  mov     qword ptr [rbp+var_50], 0
0x18001d6d1  mov     rax, [rsi]
0x18001d6d4  mov     rdi, [rax+1C0h]
0x18001d6db  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d6e0  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18001d6e4  lea     rax, [rbp+var_50]
0x18001d6e8  mov     r9, [r13+18h]
0x18001d6ec  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18001d6f1  lea     rdx, [rbp+var_20]
0x18001d6f5  mov     qword ptr [rsp+80h+var_60], rax; int
0x18001d6fa  mov     r8, rbx
0x18001d6fd  mov     rax, rdi
0x18001d700  movaps  [rbp+var_20], xmm0
0x18001d704  mov     rcx, rsi
0x18001d707  movsd   [rbp+var_10], xmm1
0x18001d70c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d711  mov     edi, eax
0x18001d713  test    eax, eax
0x18001d715  jns     short loc_18001D734
0x18001d717  mov     rcx, [rbp+38h]; this
0x18001d71b  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d722  mov     r9d, eax; char *
0x18001d725  mov     edx, 14Bh; void *
0x18001d72a  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d72f  jmp     loc_18001D7D8
0x18001d734  mov     rax, [r14]
0x18001d737  lea     rcx, [rbp+var_48]
0x18001d73b  mov     [rbp+var_48], 0
0x18001d743  mov     rdi, [rax+0A8h]
0x18001d74a  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d74f  mov     rdx, qword ptr [rbp+var_50]
0x18001d753  lea     r8, [rbp+var_48]
0x18001d757  mov     rcx, r14
0x18001d75a  mov     rax, rdi
0x18001d75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d762  mov     edi, eax
0x18001d764  test    eax, eax
0x18001d766  jns     short loc_18001D782
0x18001d768  mov     rcx, [rbp+38h]; this
0x18001d76c  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d773  mov     r9d, eax; char *
0x18001d776  mov     edx, 14Fh; void *
0x18001d77b  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d780  jmp     short loc_18001D7CF
0x18001d782  lea     rdx, [rbp+var_40]
0x18001d786  mov     [rbp+var_40], 0
0x18001d78e  lea     rcx, [rbp+var_48]
0x18001d792  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x18001d797  mov     edi, eax
0x18001d799  test    eax, eax
0x18001d79b  jns     short loc_18001D7B7
0x18001d79d  mov     rcx, [rbp+38h]; this
0x18001d7a1  lea     r8, aOnecoreBaseApp_16; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d7a8  mov     r9d, eax; char *
0x18001d7ab  mov     edx, 152h; void *
0x18001d7b0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d7b5  jmp     short loc_18001D7C6
0x18001d7b7  mov     rax, [rbp+var_40]
0x18001d7bb  mov     [r15], rax
0x18001d7be  mov     [rbp+var_40], 0
0x18001d7c6  lea     rcx, [rbp+var_40]
0x18001d7ca  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d7cf  lea     rcx, [rbp+var_48]
0x18001d7d3  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d7d8  lea     rcx, [rbp+var_50]
0x18001d7dc  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d7e1  lea     rcx, [rbp+pvarg]; pvarg
0x18001d7e5  call    cs:__imp_VariantClear
0x18001d7eb  mov     rcx, rbx; bstrString
0x18001d7ee  call    cs:__imp_SysFreeString
0x18001d7f4  mov     eax, edi
0x18001d7f6  add     rsp, 80h
0x18001d7fd  pop     r15
0x18001d7ff  pop     r14
0x18001d801  pop     r13
0x18001d803  pop     rdi
0x18001d804  pop     rsi
0x18001d805  pop     rbx
0x18001d806  pop     rbp
0x18001d807  retn
```
