# CustomExpressionWrapper::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000b010`
- end: `0x18000b074`
- name: `?Evaluate@CustomExpressionWrapper@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `100`
- prototype: `int(CustomExpressionWrapper *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000b010`
- `0x180010f08`
- `0x1800114fc`
- `0x180011514`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall CustomExpressionWrapper::Evaluate(
        CustomExpressionWrapper *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  __int64 v3; // rcx
  int v5; // ebx
  unsigned int CCH; // eax
  unsigned __int16 *Src; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_QWORD *)this + 2);
  Src = 0;
  v5 = (*(__int64 (__fastcall **)(__int64, struct XPathEvaluationContext *, unsigned __int16 **))(*(_QWORD *)v3 + 48LL))(
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
0x18000b010  mov     [rsp+arg_8], rbx
0x18000b015  push    rdi
0x18000b016  sub     rsp, 20h
0x18000b01a  mov     rcx, [rcx+10h]
0x18000b01e  mov     rdi, r8
0x18000b021  mov     [rsp+28h+Src], 0
0x18000b02a  lea     r8, [rsp+28h+Src]
0x18000b02f  mov     rax, [rcx]
0x18000b032  mov     rax, [rax+30h]
0x18000b036  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b03b  mov     ebx, eax
0x18000b03d  test    eax, eax
0x18000b03f  js      short loc_18000B05D
0x18000b041  lea     rcx, [rsp+28h+Src]; this
0x18000b046  call    ?QueryCCH@ScopedBSTR@@QEBAIXZ; ScopedBSTR::QueryCCH(void)
0x18000b04b  mov     rdx, [rsp+28h+Src]; Src
0x18000b050  mov     rcx, rdi; this
0x18000b053  mov     r8d, eax; unsigned __int64
0x18000b056  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000b05b  mov     ebx, eax
0x18000b05d  lea     rcx, [rsp+28h+Src]; this
0x18000b062  call    ?Reset@ScopedBSTR@@QEAAXXZ; ScopedBSTR::Reset(void)
0x18000b067  mov     eax, ebx
0x18000b069  mov     rbx, [rsp+28h+arg_8]
0x18000b06e  add     rsp, 20h
0x18000b072  pop     rdi
0x18000b073  retn
```
