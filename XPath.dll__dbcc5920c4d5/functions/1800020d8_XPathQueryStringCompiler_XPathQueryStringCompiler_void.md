# XPathQueryStringCompiler::~XPathQueryStringCompiler(void)

- ea: `0x1800020d8`
- end: `0x180002107`
- name: `??1XPathQueryStringCompiler@@UEAA@XZ`
- size: `47`
- prototype: `void __fastcall(XPathQueryStringCompiler *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180002150`

## callees

- `0x1800020b4`
- `0x180002398`
- `0x180010fac`

## pseudocode

```c
void __fastcall XPathQueryStringCompiler::~XPathQueryStringCompiler(XPathQueryStringCompiler *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 7);
  String::Reset((XPathQueryStringCompiler *)((char *)this + 16));
  *(_QWORD *)this = &SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800020d8  push    rbx
0x1800020da  sub     rsp, 20h
0x1800020de  mov     rbx, rcx
0x1800020e1  add     rcx, 38h ; '8'
0x1800020e5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800020ea  lea     rcx, [rbx+10h]; this
0x1800020ee  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x1800020f3  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathQueryStringCompiler@@@@6B@; const SimpleIUnknownImpl<IXPathQueryStringCompiler>::`vftable'
0x1800020fa  mov     [rbx], rax
0x1800020fd  add     rsp, 20h
0x180002101  pop     rbx
0x180002102  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
