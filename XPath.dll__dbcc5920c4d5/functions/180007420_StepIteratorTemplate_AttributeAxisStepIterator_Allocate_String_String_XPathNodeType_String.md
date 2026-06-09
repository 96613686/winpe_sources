# StepIteratorTemplate<AttributeAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007420`
- end: `0x18000749c`
- name: `?Allocate@?$StepIteratorTemplate@VAttributeAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x180007420`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<AttributeAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &AttributeAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007420  push    rbx
0x180007422  push    rbp
0x180007423  push    rsi
0x180007424  push    rdi
0x180007425  push    r14
0x180007427  sub     rsp, 30h
0x18000742b  mov     r14, rcx
0x18000742e  mov     rdi, r9
0x180007431  mov     ecx, 68h ; 'h'; Size
0x180007436  mov     esi, r8d
0x180007439  mov     rbp, rdx
0x18000743c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007441  mov     rbx, rax
0x180007444  test    rax, rax
0x180007447  jz      short loc_18000748C
0x180007449  xor     edx, edx; Val
0x18000744b  mov     rcx, rax; void *
0x18000744e  lea     r8d, [rdx+68h]; Size
0x180007452  call    memset_0
0x180007457  mov     rcx, rbx; this
0x18000745a  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x18000745f  lea     rax, ??_7AttributeAxisStepIterator@@6BIXPathNodeIterator@@@; const AttributeAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x180007466  mov     [rsp+58h+var_38], rdi
0x18000746b  mov     [rbx], rax
0x18000746e  mov     r9d, esi
0x180007471  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x180007478  mov     r8, rbp
0x18000747b  mov     rdx, r14
0x18000747e  mov     [rbx+8], rax
0x180007482  mov     rcx, rbx
0x180007485  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x18000748a  jmp     short loc_18000748E
0x18000748c  xor     ebx, ebx
0x18000748e  mov     rax, rbx
0x180007491  add     rsp, 30h
0x180007495  pop     r14
0x180007497  pop     rdi
0x180007498  pop     rsi
0x180007499  pop     rbp
0x18000749a  pop     rbx
0x18000749b  retn
```
