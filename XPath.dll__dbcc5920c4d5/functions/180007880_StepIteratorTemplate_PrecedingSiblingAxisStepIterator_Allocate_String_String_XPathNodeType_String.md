# StepIteratorTemplate<PrecedingSiblingAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007880`
- end: `0x1800078fc`
- name: `?Allocate@?$StepIteratorTemplate@VPrecedingSiblingAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000c8d0`

## callees

- `0x180001078`
- `0x180006440`
- `0x180007880`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<PrecedingSiblingAxisStepIterator>::Allocate(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  StepIteratorBase *v8; // rax
  StepIteratorBase *v9; // rbx

  v8 = (StepIteratorBase *)operator new(0x68u);
  v9 = v8;
  if ( !v8 )
    return 0;
  memset_0(v8, 0, 0x68u);
  StepIteratorBase::StepIteratorBase(v9);
  *(_QWORD *)v9 = &PrecedingSiblingAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007880  push    rbx
0x180007882  push    rbp
0x180007883  push    rsi
0x180007884  push    rdi
0x180007885  push    r14
0x180007887  sub     rsp, 30h
0x18000788b  mov     r14, rcx
0x18000788e  mov     rdi, r9
0x180007891  mov     ecx, 68h ; 'h'; Size
0x180007896  mov     esi, r8d
0x180007899  mov     rbp, rdx
0x18000789c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800078a1  mov     rbx, rax
0x1800078a4  test    rax, rax
0x1800078a7  jz      short loc_1800078EC
0x1800078a9  xor     edx, edx; Val
0x1800078ab  mov     rcx, rax; void *
0x1800078ae  lea     r8d, [rdx+68h]; Size
0x1800078b2  call    memset_0
0x1800078b7  mov     rcx, rbx; this
0x1800078ba  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x1800078bf  lea     rax, ??_7PrecedingSiblingAxisStepIterator@@6BIXPathNodeIterator@@@; const PrecedingSiblingAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x1800078c6  mov     [rsp+58h+var_38], rdi
0x1800078cb  mov     [rbx], rax
0x1800078ce  mov     r9d, esi
0x1800078d1  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x1800078d8  mov     r8, rbp
0x1800078db  mov     rdx, r14
0x1800078de  mov     [rbx+8], rax
0x1800078e2  mov     rcx, rbx
0x1800078e5  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x1800078ea  jmp     short loc_1800078EE
0x1800078ec  xor     ebx, ebx
0x1800078ee  mov     rax, rbx
0x1800078f1  add     rsp, 30h
0x1800078f5  pop     r14
0x1800078f7  pop     rdi
0x1800078f8  pop     rsi
0x1800078f9  pop     rbp
0x1800078fa  pop     rbx
0x1800078fb  retn
```
