# Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(IXMLDOMNode *,ushort const *,IXMLDOMElement * *,bool *)

- ea: `0x18001d810`
- end: `0x18001d923`
- name: `?GetElement@CommonHelpers@AppxProvisionPackage@ApplicationModel@Windows@@SAJPEAUIXMLDOMNode@@PEBGPEAPEAUIXMLDOMElement@@PEA_N@Z`
- size: `275`
- prototype: `static int(struct IXMLDOMNode *, const unsigned __int16 *, struct IXMLDOMElement **, bool *)`
- caller_count: `3`
- callee_count: `5`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18001bbfc`
- `0x18001c630`
- `0x18001cfb8`

## callees

- `0x180017f50`
- `0x18001ca24`
- `0x18001d810`
- `0x18001e284`
- `0x18004d010`

## import_xrefs

- `OLEAUT32!__imp_SysAllocString` at `0x18001d83a`
- `OLEAUT32!__imp_SysAllocString` at `0x18001d83a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d84a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d90a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d84a`
- `OLEAUT32!__imp_SysFreeString` at `0x18001d90a`

## string_xrefs

- `0x18001d891`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`
- `0x18001d8cd`: `onecore\base\appmodel\appxprovisionpackage\src\commonhelpers.cpp`

## pseudocode

```c
__int64 __fastcall Windows::ApplicationModel::AppxProvisionPackage::CommonHelpers::GetElement(
        struct IXMLDOMNode *a1,
        const unsigned __int16 *a2,
        struct IXMLDOMElement **a3,
        bool *a4)
{
  OLECHAR *v7; // rbx
  struct IXMLDOMNodeVtbl *lpVtbl; // rax
  HRESULT (__stdcall *selectSingleNode)(IXMLDOMNode *, BSTR, IXMLDOMNode **); // rdi
  int v11; // eax
  unsigned int v12; // edi
  int v13; // eax
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+28h]
  __int64 (__fastcall ***v15)(_QWORD, GUID *, __int64); // [rsp+60h] [rbp+40h] BYREF
  struct IXMLDOMElement *v16; // [rsp+68h] [rbp+48h] BYREF

  *a4 = 0;
  *a3 = 0;
  v7 = SysAllocString(a2);
  if ( v7 )
  {
    lpVtbl = a1->lpVtbl;
    v15 = 0;
    selectSingleNode = lpVtbl->selectSingleNode;
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v15);
    v11 = ((__int64 (__fastcall *)(struct IXMLDOMNode *, OLECHAR *, _QWORD))selectSingleNode)(a1, v7, &v15);
    v12 = v11;
    if ( v11 >= 0 )
    {
      if ( v15 )
      {
        v16 = 0;
        v13 = Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(&v15, (__int64)&v16);
        v12 = v13;
        if ( v13 >= 0 )
        {
          *a3 = v16;
          v16 = 0;
          *a4 = 1;
        }
        else
        {
          wil::details::in1diag3::_Log_Hr(
            retaddr,
            (void *)0x12D,
            (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
            (const char *)(unsigned int)v13);
        }
        Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v16);
      }
    }
    else
    {
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x128,
        (int)"onecore\\base\\appmodel\\appxprovisionpackage\\src\\commonhelpers.cpp",
        (const char *)(unsigned int)v11);
    }
    Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(&v15);
    SysFreeString(v7);
    return v12;
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
0x18001d810  mov     [rsp-28h+arg_0], rbx
0x18001d815  push    rbp
0x18001d816  push    rsi
0x18001d817  push    rdi
0x18001d818  push    r14
0x18001d81a  push    r15; int
0x18001d81c  mov     rbp, rsp
0x18001d81f  sub     rsp, 20h
0x18001d823  mov     r15, rcx
0x18001d826  mov     byte ptr [r9], 0
0x18001d82a  mov     rcx, rdx; psz
0x18001d82d  mov     qword ptr [r8], 0
0x18001d834  mov     rsi, r9
0x18001d837  mov     r14, r8
0x18001d83a  call    cs:__imp_SysAllocString
0x18001d840  mov     rbx, rax
0x18001d843  test    rax, rax
0x18001d846  jnz     short loc_18001D85A
0x18001d848  xor     ecx, ecx; bstrString
0x18001d84a  call    cs:__imp_SysFreeString
0x18001d850  mov     eax, 8007000Eh
0x18001d855  jmp     loc_18001D912
0x18001d85a  mov     rax, [r15]
0x18001d85d  lea     rcx, [rbp+arg_10]
0x18001d861  mov     [rbp+arg_10], 0
0x18001d869  mov     rdi, [rax+128h]
0x18001d870  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d875  lea     r8, [rbp+arg_10]
0x18001d879  mov     rdx, rbx
0x18001d87c  mov     rcx, r15
0x18001d87f  mov     rax, rdi
0x18001d882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001d887  mov     edi, eax
0x18001d889  test    eax, eax
0x18001d88b  jns     short loc_18001D8A7
0x18001d88d  mov     rcx, [rbp+28h]; this
0x18001d891  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d898  mov     r9d, eax; char *
0x18001d89b  mov     edx, 128h; void *
0x18001d8a0  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d8a5  jmp     short loc_18001D8FE
0x18001d8a7  cmp     [rbp+arg_10], 0
0x18001d8ac  jz      short loc_18001D8FE
0x18001d8ae  lea     rdx, [rbp+arg_18]
0x18001d8b2  mov     [rbp+arg_18], 0
0x18001d8ba  lea     rcx, [rbp+arg_10]
0x18001d8be  call    ??$As@UIXMLDOMElement@@@?$ComPtr@UIXMLDOMNode@@@WRL@Microsoft@@QEBAJV?$ComPtrRef@V?$ComPtr@UIXMLDOMElement@@@WRL@Microsoft@@@Details@12@@Z; Microsoft::WRL::ComPtr<IXMLDOMNode>::As<IXMLDOMElement>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<IXMLDOMElement>>)
0x18001d8c3  mov     edi, eax
0x18001d8c5  test    eax, eax
0x18001d8c7  jns     short loc_18001D8E3
0x18001d8c9  mov     rcx, [rbp+28h]; this
0x18001d8cd  lea     r8, aOnecoreBaseApp; "onecore\\base\\appmodel\\appxprovisionp"...
0x18001d8d4  mov     r9d, eax; char *
0x18001d8d7  mov     edx, 12Dh; void *
0x18001d8dc  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18001d8e1  jmp     short loc_18001D8F5
0x18001d8e3  mov     rax, [rbp+arg_18]
0x18001d8e7  mov     [r14], rax
0x18001d8ea  mov     [rbp+arg_18], 0
0x18001d8f2  mov     byte ptr [rsi], 1
0x18001d8f5  lea     rcx, [rbp+arg_18]
0x18001d8f9  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d8fe  lea     rcx, [rbp+arg_10]
0x18001d902  call    ?InternalRelease@?$ComPtr@UIXMLDOMSchemaCollection@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IXMLDOMSchemaCollection>::InternalRelease(void)
0x18001d907  mov     rcx, rbx; bstrString
0x18001d90a  call    cs:__imp_SysFreeString
0x18001d910  mov     eax, edi
0x18001d912  mov     rbx, [rsp+20h+arg_0]
0x18001d917  add     rsp, 20h
0x18001d91b  pop     r15
0x18001d91d  pop     r14
0x18001d91f  pop     rdi
0x18001d920  pop     rsi
0x18001d921  pop     rbp
0x18001d922  retn
```
