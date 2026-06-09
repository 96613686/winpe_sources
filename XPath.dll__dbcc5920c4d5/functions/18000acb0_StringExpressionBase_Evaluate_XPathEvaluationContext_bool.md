# StringExpressionBase::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x18000acb0`
- end: `0x18000ad07`
- name: `?Evaluate@StringExpressionBase@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `87`
- prototype: `__int64 __fastcall(StringExpressionBase *__hidden this, struct XPathEvaluationContext *, bool *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000acb0`
- `0x180010f98`
- `0x180010fac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StringExpressionBase::Evaluate(
        StringExpressionBase *this,
        struct XPathEvaluationContext *a2,
        bool *a3)
{
  __int64 v3; // rax
  int v5; // ebx
  __int64 v7; // [rsp+30h] [rbp+8h] BYREF

  v3 = *(_QWORD *)this;
  v7 = 0;
  v5 = (*(__int64 (__fastcall **)(StringExpressionBase *, struct XPathEvaluationContext *, __int64 *))(v3 + 64))(
         this,
         a2,
         &v7);
  if ( v5 >= 0 )
  {
    v5 = 0;
    *a3 = String::QueryCCH((String *)&v7) != 0;
  }
  String::Reset((String *)&v7);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000acb0  mov     [rsp+arg_8], rbx
0x18000acb5  push    rdi
0x18000acb6  sub     rsp, 20h
0x18000acba  mov     rax, [rcx]
0x18000acbd  mov     rdi, r8
0x18000acc0  lea     r8, [rsp+28h+arg_0]
0x18000acc5  mov     [rsp+28h+arg_0], 0
0x18000acce  mov     rax, [rax+40h]
0x18000acd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000acd7  mov     ebx, eax
0x18000acd9  test    eax, eax
0x18000acdb  js      short loc_18000ACF0
0x18000acdd  lea     rcx, [rsp+28h+arg_0]; this
0x18000ace2  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000ace7  test    eax, eax
0x18000ace9  setnz   al
0x18000acec  xor     ebx, ebx
0x18000acee  mov     [rdi], al
0x18000acf0  lea     rcx, [rsp+28h+arg_0]; this
0x18000acf5  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000acfa  mov     eax, ebx
0x18000acfc  mov     rbx, [rsp+28h+arg_8]
0x18000ad01  add     rsp, 20h
0x18000ad05  pop     rdi
0x18000ad06  retn
```
