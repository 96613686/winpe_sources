# XPathEvaluationContext::~XPathEvaluationContext(void)

- ea: `0x1800033e8`
- end: `0x180003417`
- name: `??1XPathEvaluationContext@@UEAA@XZ`
- size: `47`
- prototype: `void __fastcall(XPathEvaluationContext *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800035f0`

## callees

- `0x1800020b4`
- `0x180002398`

## pseudocode

```c
void __fastcall XPathEvaluationContext::~XPathEvaluationContext(XPathEvaluationContext *this)
{
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 4);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>((__int64 *)this + 2);
  *(_QWORD *)this = &SimpleIUnknownImpl<IXPathEvaluationContext>::`vftable';
  ModuleRefCounter::Release();
}

```

## disassembly

```asm
0x1800033e8  push    rbx
0x1800033ea  sub     rsp, 20h
0x1800033ee  mov     rbx, rcx
0x1800033f1  add     rcx, 20h ; ' '
0x1800033f5  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x1800033fa  lea     rcx, [rbx+10h]
0x1800033fe  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x180003403  lea     rax, ??_7?$SimpleIUnknownImpl@UIXPathEvaluationContext@@@@6B@; const SimpleIUnknownImpl<IXPathEvaluationContext>::`vftable'
0x18000340a  mov     [rbx], rax
0x18000340d  add     rsp, 20h
0x180003411  pop     rbx
0x180003412  jmp     ?Release@ModuleRefCounter@@SAXXZ; ModuleRefCounter::Release(void)
```
