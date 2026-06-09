# StringExpressionWrapper::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000b0f0`
- end: `0x18000b154`
- name: `?Evaluate@StringExpressionWrapper@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `100`
- prototype: `int(StringExpressionWrapper *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000b0f0`
- `0x180010f08`
- `0x1800114fc`
- `0x180011514`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StringExpressionWrapper::Evaluate(
        StringExpressionWrapper *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  __int64 v3; // rcx
  int v5; // ebx
  unsigned int CCH; // eax
  unsigned __int16 *Src; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 2);
  Src = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, struct XPathEvaluationContext *, unsigned __int16 **))(*(_QWORD *)v3 + 24LL))(
         v3,
         a2,
         &Src);
  if ( v5 >= 0 )
  {
    CCH = ScopedBSTR::QueryCCH((ScopedBSTR *)&Src);
    v5 = String::Initialize(a3, Src, CCH);
  }
  ScopedBSTR::Reset((ScopedBSTR *)&Src);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000b0f0  mov     [rsp+arg_8], rbx
0x18000b0f5  push    rdi
0x18000b0f6  sub     rsp, 20h
0x18000b0fa  mov     rcx, [rcx+10h]
0x18000b0fe  mov     rdi, r8
0x18000b101  mov     [rsp+28h+Src], 0
0x18000b10a  lea     r8, [rsp+28h+Src]
0x18000b10f  mov     rax, [rcx]
0x18000b112  mov     rax, [rax+18h]
0x18000b116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b11b  mov     ebx, eax
0x18000b11d  test    eax, eax
0x18000b11f  js      short loc_18000B13D
0x18000b121  lea     rcx, [rsp+28h+Src]; this
0x18000b126  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x18000b12b  mov     rdx, [rsp+28h+Src]; Src
0x18000b130  mov     rcx, rdi; this
0x18000b133  mov     r8d, eax; unsigned __int64
0x18000b136  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000b13b  mov     ebx, eax
0x18000b13d  lea     rcx, [rsp+28h+Src]; this
0x18000b142  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b147  mov     eax, ebx
0x18000b149  mov     rbx, [rsp+28h+arg_8]
0x18000b14e  add     rsp, 20h
0x18000b152  pop     rdi
0x18000b153  retn
```
