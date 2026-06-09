# StepIteratorTemplate<NamespaceAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007760`
- end: `0x1800077dc`
- name: `?Allocate@?$StepIteratorTemplate@VNamespaceAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x180007760`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<NamespaceAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &NamespaceAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007760  push    rbx
0x180007762  push    rbp
0x180007763  push    rsi
0x180007764  push    rdi
0x180007765  push    r14
0x180007767  sub     rsp, 30h
0x18000776b  mov     r14, rcx
0x18000776e  mov     rdi, r9
0x180007771  mov     ecx, 68h ; 'h'; Size
0x180007776  mov     esi, r8d
0x180007779  mov     rbp, rdx
0x18000777c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007781  mov     rbx, rax
0x180007784  test    rax, rax
0x180007787  jz      short loc_1800077CC
0x180007789  xor     edx, edx; Val
0x18000778b  mov     rcx, rax; void *
0x18000778e  lea     r8d, [rdx+68h]; Size
0x180007792  call    memset_0
0x180007797  mov     rcx, rbx; this
0x18000779a  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x18000779f  lea     rax, ??_7NamespaceAxisStepIterator@@6BIXPathNodeIterator@@@; const NamespaceAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x1800077a6  mov     [rsp+58h+var_38], rdi
0x1800077ab  mov     [rbx], rax
0x1800077ae  mov     r9d, esi
0x1800077b1  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x1800077b8  mov     r8, rbp
0x1800077bb  mov     rdx, r14
0x1800077be  mov     [rbx+8], rax
0x1800077c2  mov     rcx, rbx
0x1800077c5  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x1800077ca  jmp     short loc_1800077CE
0x1800077cc  xor     ebx, ebx
0x1800077ce  mov     rax, rbx
0x1800077d1  add     rsp, 30h
0x1800077d5  pop     r14
0x1800077d7  pop     rdi
0x1800077d8  pop     rsi
0x1800077d9  pop     rbp
0x1800077da  pop     rbx
0x1800077db  retn
```
