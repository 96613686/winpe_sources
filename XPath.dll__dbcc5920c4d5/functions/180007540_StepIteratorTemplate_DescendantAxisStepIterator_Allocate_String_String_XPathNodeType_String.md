# StepIteratorTemplate<DescendantAxisStepIterator>::Allocate(String &,String &,XPathNodeType,String &)

- ea: `0x180007540`
- end: `0x1800075b5`
- name: `?Allocate@?$StepIteratorTemplate@VDescendantAxisStepIterator@@@@SAPEAVXPathNodeIteratorBase@@AEAVString@@0W4XPathNodeType@@0@Z`
- size: `117`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180001078`
- `0x180006440`
- `0x180007540`
- `0x180008b0c`

## pseudocode

```c
__int64 __fastcall StepIteratorTemplate<DescendantAxisStepIterator>::Allocate(
        __int64 a1,
        __int64 a2,
        int a3,
        __int64 a4)
{
  StepIteratorBase *v8; // rax
  __int64 v9; // rbx

  v8 = (StepIteratorBase *)operator new(0x70u);
  v9 = (__int64)v8;
  if ( !v8 )
    return 0;
  StepIteratorBase::StepIteratorBase(v8);
  *(_DWORD *)(v9 + 104) = 0;
  *(_QWORD *)v9 = &DescendantAxisStepIterator::`vftable'{for `IXPathNodeIterator'};
  *(_QWORD *)(v9 + 8) = &AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'};
  StepIteratorBase::Initialize(v9, a1, a2, a3, a4);
  return v9;
}

```

## disassembly

```asm
0x180007540  push    rbx
0x180007542  push    rbp
0x180007543  push    rsi
0x180007544  push    rdi
0x180007545  push    r14
0x180007547  sub     rsp, 30h
0x18000754b  mov     r14, rcx
0x18000754e  mov     rdi, r9
0x180007551  mov     ecx, 70h ; 'p'; Size
0x180007556  mov     esi, r8d
0x180007559  mov     rbp, rdx
0x18000755c  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180007561  mov     rbx, rax
0x180007564  test    rax, rax
0x180007567  jz      short loc_1800075A5
0x180007569  mov     rcx, rax; this
0x18000756c  call    ??0StepIteratorBase@@IEAA@XZ; StepIteratorBase::StepIteratorBase(void)
0x180007571  lea     rax, ??_7DescendantAxisStepIterator@@6BIXPathNodeIterator@@@; const DescendantAxisStepIterator::`vftable'{for `IXPathNodeIterator'}
0x180007578  mov     dword ptr [rbx+68h], 0
0x18000757f  mov     [rbx], rax
0x180007582  mov     r9d, esi
0x180007585  lea     rax, ??_7AncestorOrSelfAxisStepIterator@@6BXPathExpressionBase@@@; const AncestorOrSelfAxisStepIterator::`vftable'{for `XPathExpressionBase'}
0x18000758c  mov     [rsp+58h+var_38], rdi
0x180007591  mov     r8, rbp
0x180007594  mov     [rbx+8], rax
0x180007598  mov     rdx, r14
0x18000759b  mov     rcx, rbx
0x18000759e  call    ?Initialize@StepIteratorBase@@IEAAXAEAVString@@0W4XPathNodeType@@0@Z; StepIteratorBase::Initialize(String &,String &,XPathNodeType,String &)
0x1800075a3  jmp     short loc_1800075A7
0x1800075a5  xor     ebx, ebx
0x1800075a7  mov     rax, rbx
0x1800075aa  add     rsp, 30h
0x1800075ae  pop     r14
0x1800075b0  pop     rdi
0x1800075b1  pop     rsi
0x1800075b2  pop     rbp
0x1800075b3  pop     rbx
0x1800075b4  retn
```
