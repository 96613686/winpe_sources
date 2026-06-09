# NameFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000ba20`
- end: `0x18000bb3b`
- name: `?Evaluate@NameFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `283`
- prototype: `int(NameFunctionExpression *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `6`
- tags: ``

## callees

- `0x1800052bc`
- `0x18000ba20`
- `0x18000e504`
- `0x18000e54c`
- `0x180010d6c`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall NameFunctionExpression::Evaluate(
        NameFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  unsigned __int16 *v3; // rbx
  XPathNavigatorInternal *ContextNode; // rax
  __int64 result; // rax
  XPathNavigatorInternal *v8; // rax
  unsigned __int16 *v9; // r8
  const unsigned __int16 *v10; // rcx
  const unsigned __int16 *v11; // rdx
  __int64 v12; // rdi
  XPathNavigatorInternal *v13; // rax
  const wchar_t *v14; // rax
  unsigned __int16 *v15[4]; // [rsp+20h] [rbp-20h] BYREF
  unsigned __int16 *v16; // [rsp+70h] [rbp+30h] BYREF
  unsigned __int16 *v17; // [rsp+88h] [rbp+48h] BYREF

  v3 = (unsigned __int16 *)&qword_180016F98;
  v16 = 0;
  v17 = 0;
  if ( !*((_DWORD *)this + 9) )
  {
    ContextNode = XPathEvaluationContext::QueryContextNode(a2);
    result = XPathNavigatorInternal::GetPrefixAtomized(ContextNode, (const unsigned __int16 **)&v16);
    if ( (int)result < 0 )
      return result;
    v8 = XPathEvaluationContext::QueryContextNode(a2);
LABEL_4:
    result = XPathNavigatorInternal::GetLocalNameAtomized(v8, (const unsigned __int16 **)&v17);
    if ( (int)result < 0 )
      return result;
    v10 = v16;
    v11 = v17;
    goto LABEL_11;
  }
  v12 = (**((_QWORD **)this + 3) - 8LL) & -(__int64)(**((_QWORD **)this + 3) != 0);
  result = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 104LL))(v12);
  if ( (int)result < 0 )
    return result;
  if ( !(_DWORD)result )
  {
    v13 = (XPathNavigatorInternal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 72LL))(v12);
    result = XPathNavigatorInternal::GetPrefixAtomized(v13, (const unsigned __int16 **)&v16);
    if ( (int)result < 0 )
      return result;
    v8 = (XPathNavigatorInternal *)(*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v12 + 72LL))(v12);
    goto LABEL_4;
  }
  v10 = &qword_180016F98;
  v16 = (unsigned __int16 *)&qword_180016F98;
  v11 = &qword_180016F98;
  v17 = (unsigned __int16 *)&qword_180016F98;
LABEL_11:
  if ( *v10 )
  {
    v14 = L":";
    if ( !*v11 )
      v14 = &qword_180016F98;
    v3 = (unsigned __int16 *)v14;
  }
  v15[0] = (unsigned __int16 *)v10;
  v15[2] = (unsigned __int16 *)v11;
  v15[1] = v3;
  return String::Initialize(a3, (const unsigned __int16 *const *const)v15, v9);
}

```

## disassembly

```asm
0x18000ba20  mov     [rsp-28h+arg_8], rbx
0x18000ba25  push    rbp
0x18000ba26  push    rsi
0x18000ba27  push    rdi
0x18000ba28  push    r14
0x18000ba2a  push    r15
0x18000ba2c  mov     rbp, rsp
0x18000ba2f  sub     rsp, 40h
0x18000ba33  xor     r15d, r15d
0x18000ba36  lea     rbx, qword_180016F98
0x18000ba3d  mov     r14, r8
0x18000ba40  mov     rsi, rdx
0x18000ba43  mov     [rbp+arg_0], r15
0x18000ba47  mov     [rbp+arg_18], r15
0x18000ba4b  cmp     [rcx+24h], r15d
0x18000ba4f  jnz     short loc_18000BA93
0x18000ba51  mov     rcx, rdx; this
0x18000ba54  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000ba59  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x18000ba5d  mov     rcx, rax; this
0x18000ba60  call    ?GetPrefixAtomized@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetPrefixAtomized(ushort const * *)
0x18000ba65  test    eax, eax
0x18000ba67  js      loc_18000BB2A
0x18000ba6d  mov     rcx, rsi; this
0x18000ba70  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000ba75  lea     rdx, [rbp+arg_18]; unsigned __int16 **
0x18000ba79  mov     rcx, rax; this
0x18000ba7c  call    ?GetLocalNameAtomized@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetLocalNameAtomized(ushort const * *)
0x18000ba81  test    eax, eax
0x18000ba83  js      loc_18000BB2A
0x18000ba89  mov     rcx, [rbp+arg_0]
0x18000ba8d  mov     rdx, [rbp+arg_18]
0x18000ba91  jmp     short loc_18000BAFA
0x18000ba93  mov     rax, [rcx+18h]
0x18000ba97  mov     rcx, [rax]
0x18000ba9a  lea     rax, [rcx-8]
0x18000ba9e  neg     rcx
0x18000baa1  sbb     rdi, rdi
0x18000baa4  and     rdi, rax
0x18000baa7  mov     rcx, rdi
0x18000baaa  mov     rax, [rdi]
0x18000baad  mov     rax, [rax+68h]
0x18000bab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bab6  test    eax, eax
0x18000bab8  js      short loc_18000BB2A
0x18000baba  jnz     short loc_18000BAEC
0x18000babc  mov     rax, [rdi]
0x18000babf  mov     rcx, rdi
0x18000bac2  mov     rax, [rax+48h]
0x18000bac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bacb  lea     rdx, [rbp+arg_0]; unsigned __int16 **
0x18000bacf  mov     rcx, rax; this
0x18000bad2  call    ?GetPrefixAtomized@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetPrefixAtomized(ushort const * *)
0x18000bad7  test    eax, eax
0x18000bad9  js      short loc_18000BB2A
0x18000badb  mov     rax, [rdi]
0x18000bade  mov     rcx, rdi
0x18000bae1  mov     rax, [rax+48h]
0x18000bae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000baea  jmp     short loc_18000BA75
0x18000baec  mov     rcx, rbx
0x18000baef  mov     [rbp+arg_0], rbx
0x18000baf3  mov     rdx, rbx
0x18000baf6  mov     [rbp+arg_18], rbx
0x18000bafa  cmp     [rcx], r15w
0x18000bafe  jz      short loc_18000BB12
0x18000bb00  cmp     [rdx], r15w
0x18000bb04  lea     rax, asc_180017240; ":"
0x18000bb0b  cmovz   rax, rbx
0x18000bb0f  mov     rbx, rax
0x18000bb12  mov     [rbp+var_20], rcx
0x18000bb16  mov     rcx, r14; this
0x18000bb19  mov     [rbp+var_10], rdx
0x18000bb1d  lea     rdx, [rbp+var_20]; unsigned __int16 **
0x18000bb21  mov     [rbp+var_18], rbx
0x18000bb25  call    ?Initialize@String@@AEAAJQEBQEBG_K@Z; String::Initialize(ushort const * const * const,unsigned __int64)
0x18000bb2a  mov     rbx, [rsp+40h+arg_8]
0x18000bb2f  add     rsp, 40h
0x18000bb33  pop     r15
0x18000bb35  pop     r14
0x18000bb37  pop     rdi
0x18000bb38  pop     rsi
0x18000bb39  pop     rbp
0x18000bb3a  retn
```
