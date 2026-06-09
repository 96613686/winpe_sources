# XPathException::~XPathException(void)

- ea: `0x1800110b8`
- end: `0x1800110f9`
- name: `??1XPathException@@UEAA@XZ`
- size: `65`
- prototype: `void __fastcall(XPathException *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x180011100`

## callees

- `0x1800020b4`
- `0x180002398`
- `0x180010fac`

## pseudocode

```c
void __fastcall XPathException::~XPathException(XPathException *this)
{
  *(_QWORD *)this = &XPathException::`vftable';
  String::Reset((XPathException *)((char *)this + 48));
  String::Reset((XPathException *)((char *)this + 40));
  String::Reset((XPathException *)((char *)this + 32));
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 2);
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800110b8  push    rbx
0x1800110ba  sub     rsp, 20h
0x1800110be  lea     rax, ??_7XPathException@@6B@; const XPathException::`vftable'
0x1800110c5  mov     rbx, rcx
0x1800110c8  mov     [rcx], rax
0x1800110cb  add     rcx, 30h ; '0'; this
0x1800110cf  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x1800110d4  lea     rcx, [rbx+28h]; this
0x1800110d8  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x1800110dd  lea     rcx, [rbx+20h]; this
0x1800110e1  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x1800110e6  lea     rcx, [rbx+10h]
0x1800110ea  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800110ef  add     rsp, 20h
0x1800110f3  pop     rbx
0x1800110f4  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
