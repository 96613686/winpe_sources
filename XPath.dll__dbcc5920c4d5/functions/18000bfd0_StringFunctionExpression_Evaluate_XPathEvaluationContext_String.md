# StringFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000bfd0`
- end: `0x18000c030`
- name: `?Evaluate@StringFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `96`
- prototype: `int(StringFunctionExpression *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000637c`
- `0x1800067c8`
- `0x18000bfd0`
- `0x18000cd00`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StringFunctionExpression::Evaluate(
        StringFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  unsigned int v5; // ebx
  _BYTE v7[8]; // [rsp+20h] [rbp-48h] BYREF
  _BYTE v8[64]; // [rsp+28h] [rbp-40h] BYREF

  if ( *((_DWORD *)this + 9) )
    return (*(__int64 (__fastcall **)(_QWORD))(***((_QWORD ***)this + 3) + 64LL))(**((_QWORD **)this + 3));
  SingletonIterator::SingletonIterator((SingletonIterator *)v7, 0);
  v5 = XPathNodeIteratorBase::Evaluate((XPathNodeIteratorBase *)v8, a2, a3);
  SingletonIterator::~SingletonIterator((SingletonIterator *)v7);
  return v5;
}

```

## disassembly

```asm
0x18000bfd0  mov     [rsp+arg_0], rbx
0x18000bfd5  push    rdi
0x18000bfd6  sub     rsp, 60h
0x18000bfda  cmp     dword ptr [rcx+24h], 0
0x18000bfde  mov     rbx, r8
0x18000bfe1  mov     rdi, rdx
0x18000bfe4  jnz     short loc_18000C012
0x18000bfe6  xor     edx, edx; bool
0x18000bfe8  lea     rcx, [rsp+68h+var_48]; this
0x18000bfed  call    ??0SingletonIterator@@QEAA@_N@Z; SingletonIterator::SingletonIterator(bool)
0x18000bff2  mov     r8, rbx; struct String *
0x18000bff5  lea     rcx, [rsp+68h+var_40]; this
0x18000bffa  mov     rdx, rdi; struct XPathEvaluationContext *
0x18000bffd  call    ?Evaluate@XPathNodeIteratorBase@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z; XPathNodeIteratorBase::Evaluate(XPathEvaluationContext *,String &)
0x18000c002  lea     rcx, [rsp+68h+var_48]; this
0x18000c007  mov     ebx, eax
0x18000c009  call    ??1SingletonIterator@@UEAA@XZ; SingletonIterator::~SingletonIterator(void)
0x18000c00e  mov     eax, ebx
0x18000c010  jmp     short loc_18000C025
0x18000c012  mov     rax, [rcx+18h]
0x18000c016  mov     rcx, [rax]
0x18000c019  mov     rax, [rcx]
0x18000c01c  mov     rax, [rax+40h]
0x18000c020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c025  mov     rbx, [rsp+68h+arg_0]
0x18000c02a  add     rsp, 60h
0x18000c02e  pop     rdi
0x18000c02f  retn
```
