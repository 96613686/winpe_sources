# StringLengthFunctionExpression::Evaluate(XPathEvaluationContext *,double &)

- ea: `0x18000c040`
- end: `0x18000c0e0`
- name: `?Evaluate@StringLengthFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAN@Z`
- size: `160`
- prototype: `int(StringLengthFunctionExpression *__hidden this, struct XPathEvaluationContext *, double *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x1800052bc`
- `0x18000c040`
- `0x18000e594`
- `0x180010ee0`
- `0x180010f98`
- `0x180010fac`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall StringLengthFunctionExpression::Evaluate(
        StringLengthFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        double *a3)
{
  bool v3; // zf
  XPathNavigatorInternal *ContextNode; // rax
  int Value; // ebx
  int v7; // eax
  __int64 v9; // [rsp+30h] [rbp+8h] BYREF
  unsigned __int16 *v10; // [rsp+48h] [rbp+20h] BYREF

  v3 = *((_DWORD *)this + 9) == 0;
  v9 = 0;
  if ( v3 )
  {
    v10 = 0;
    ContextNode = XPathEvaluationContext::QueryContextNode(a2);
    Value = XPathNavigatorInternal::GetValue(ContextNode, (const unsigned __int16 **)&v10);
    if ( Value < 0 )
      goto LABEL_6;
    v7 = String::Initialize((String *)&v9, v10);
  }
  else
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, __int64 *))(***((_QWORD ***)this + 3) + 64LL))(
           **((_QWORD **)this + 3),
           a2,
           &v9);
  }
  Value = v7;
  if ( v7 >= 0 )
  {
    Value = 0;
    *a3 = (double)(int)String::QueryCCH((String *)&v9);
  }
LABEL_6:
  String::Reset((String *)&v9);
  return (unsigned int)Value;
}

```

## disassembly

```asm
0x18000c040  mov     [rsp+arg_8], rbx
0x18000c045  push    rdi
0x18000c046  sub     rsp, 20h
0x18000c04a  cmp     dword ptr [rcx+24h], 0
0x18000c04e  mov     rdi, r8
0x18000c051  mov     [rsp+28h+arg_0], 0
0x18000c05a  jnz     short loc_18000C0C6
0x18000c05c  mov     rcx, rdx; this
0x18000c05f  mov     [rsp+28h+arg_18], 0
0x18000c068  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000c06d  lea     rdx, [rsp+28h+arg_18]; unsigned __int16 **
0x18000c072  mov     rcx, rax; this
0x18000c075  call    ?GetValue@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetValue(ushort const * *)
0x18000c07a  lea     rcx, [rsp+28h+arg_0]; this
0x18000c07f  mov     ebx, eax
0x18000c081  test    eax, eax
0x18000c083  js      short loc_18000C0B4
0x18000c085  mov     rdx, [rsp+28h+arg_18]; unsigned __int16 *
0x18000c08a  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000c08f  mov     ebx, eax
0x18000c091  test    eax, eax
0x18000c093  js      short loc_18000C0AF
0x18000c095  lea     rcx, [rsp+28h+arg_0]; this
0x18000c09a  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000c09f  mov     ecx, eax
0x18000c0a1  xorps   xmm0, xmm0
0x18000c0a4  xor     ebx, ebx
0x18000c0a6  cvtsi2sd xmm0, rcx
0x18000c0ab  movsd   qword ptr [rdi], xmm0
0x18000c0af  lea     rcx, [rsp+28h+arg_0]; this
0x18000c0b4  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c0b9  mov     eax, ebx
0x18000c0bb  mov     rbx, [rsp+28h+arg_8]
0x18000c0c0  add     rsp, 20h
0x18000c0c4  pop     rdi
0x18000c0c5  retn
0x18000c0c6  mov     rax, [rcx+18h]
0x18000c0ca  lea     r8, [rsp+28h+arg_0]
0x18000c0cf  mov     rcx, [rax]
0x18000c0d2  mov     rax, [rcx]
0x18000c0d5  mov     rax, [rax+40h]
0x18000c0d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0de  jmp     short loc_18000C08F
```
