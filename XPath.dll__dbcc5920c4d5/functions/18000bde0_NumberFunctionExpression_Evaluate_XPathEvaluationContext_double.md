# NumberFunctionExpression::Evaluate(XPathEvaluationContext *,double &)

- ea: `0x18000bde0`
- end: `0x18000be40`
- name: `?Evaluate@NumberFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAN@Z`
- size: `96`
- prototype: `__int64 __fastcall(NumberFunctionExpression *__hidden this, struct XPathEvaluationContext *, double *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000637c`
- `0x1800067c8`
- `0x18000a5e4`
- `0x18000bde0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall NumberFunctionExpression::Evaluate(
        NumberFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        double *a3)
{
  unsigned int v5; // ebx
  _BYTE v7[8]; // [rsp+20h] [rbp-48h] BYREF
  __int64 v8[8]; // [rsp+28h] [rbp-40h] BYREF

  if ( *((_DWORD *)this + 9) )
    return (*(__int64 (__fastcall **)(_QWORD))(***((_QWORD ***)this + 3) + 72LL))(**((_QWORD **)this + 3));
  SingletonIterator::SingletonIterator((SingletonIterator *)v7, 0);
  v5 = XPathExpressionBase::EvaluateAsTypeAndConvertToResult<String,double>(v8, (__int64)a2, a3);
  SingletonIterator::~SingletonIterator((SingletonIterator *)v7);
  return v5;
}

```

## disassembly

```asm
0x18000bde0  mov     [rsp+arg_0], rbx
0x18000bde5  push    rdi
0x18000bde6  sub     rsp, 60h
0x18000bdea  cmp     dword ptr [rcx+24h], 0
0x18000bdee  mov     rbx, r8
0x18000bdf1  mov     rdi, rdx
0x18000bdf4  jnz     short loc_18000BE22
0x18000bdf6  xor     edx, edx; bool
0x18000bdf8  lea     rcx, [rsp+68h+var_48]; this
0x18000bdfd  call    ??0SingletonIterator@@QEAA@_N@Z; SingletonIterator::SingletonIterator(bool)
0x18000be02  mov     r8, rbx
0x18000be05  lea     rcx, [rsp+68h+var_40]
0x18000be0a  mov     rdx, rdi
0x18000be0d  call    ??$EvaluateAsTypeAndConvertToResult@VString@@N@XPathExpressionBase@@IEAAJPEAVXPathEvaluationContext@@AEAN@Z; XPathExpressionBase::EvaluateAsTypeAndConvertToResult<String,double>(XPathEvaluationContext *,double &)
0x18000be12  lea     rcx, [rsp+68h+var_48]; this
0x18000be17  mov     ebx, eax
0x18000be19  call    ??1SingletonIterator@@UEAA@XZ; SingletonIterator::~SingletonIterator(void)
0x18000be1e  mov     eax, ebx
0x18000be20  jmp     short loc_18000BE35
0x18000be22  mov     rax, [rcx+18h]
0x18000be26  mov     rcx, [rax]
0x18000be29  mov     rax, [rcx]
0x18000be2c  mov     rax, [rax+48h]
0x18000be30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000be35  mov     rbx, [rsp+68h+arg_0]
0x18000be3a  add     rsp, 60h
0x18000be3e  pop     rdi
0x18000be3f  retn
```
