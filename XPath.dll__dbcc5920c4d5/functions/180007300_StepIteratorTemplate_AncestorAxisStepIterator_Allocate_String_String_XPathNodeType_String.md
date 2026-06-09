# StepIteratorTemplate<AncestorAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007300`
- end: `0x18000737c`
- name: `?Allocate@?$StepIteratorTemplate@VAncestorAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `124`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x180007300`
- `0x180008b0c`
- `0x18001180a`

## pseudocode

```c
StepIteratorBase *__fastcall StepIteratorTemplate<AncestorAxisStepIterator>::Allocate(
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
  *(_QWORD *)v9 = &AncestorAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *((_QWORD *)v9 + 1) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize((__int64)v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007300  push    rbx
0x180007302  push    rbp
0x180007303  push    rsi
0x180007304  push    rdi
0x180007305  push    r14
0x180007307  sub     rsp, 30h
0x18000730b  mov     r14, rcx
0x18000730e  mov     rdi, r9
0x180007311  mov     ecx, 68h ; 'h'; Size
0x180007316  mov     esi, r8d
0x180007319  mov     rbp, rdx
0x18000731c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007321  mov     rbx, rax
0x180007324  test    rax, rax
0x180007327  jz      short loc_18000736C
0x180007329  xor     edx, edx; Val
0x18000732b  mov     rcx, rax; void *
0x18000732e  lea     r8d, [rdx+68h]; Size
0x180007332  call    memset_0
0x180007337  mov     rcx, rbx; this
0x18000733a  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x18000733f  lea     rax, ??_7AncestorAxisStepIterator@@6BIXPathNodeIterator@@@; const AncestorAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x180007346  mov     [rsp+58h+var_38], rdi
0x18000734b  mov     [rbx], rax
0x18000734e  mov     r9d, esi
0x180007351  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x180007358  mov     r8, rbp
0x18000735b  mov     rdx, r14
0x18000735e  mov     [rbx+8], rax
0x180007362  mov     rcx, rbx
0x180007365  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x18000736a  jmp     short loc_18000736E
0x18000736c  xor     ebx, ebx
0x18000736e  mov     rax, rbx
0x180007371  add     rsp, 30h
0x180007375  pop     r14
0x180007377  pop     rdi
0x180007378  pop     rsi
0x180007379  pop     rbp
0x18000737a  pop     rbx
0x18000737b  retn
```
