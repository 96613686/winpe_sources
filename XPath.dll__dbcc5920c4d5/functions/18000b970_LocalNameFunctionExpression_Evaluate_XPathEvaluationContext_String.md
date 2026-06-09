# LocalNameFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000b970`
- end: `0x18000ba0e`
- name: `?Evaluate@LocalNameFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `158`
- prototype: `int(LocalNameFunctionExpression *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x1800052bc`
- `0x18000b970`
- `0x18000e504`
- `0x180010ee0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall LocalNameFunctionExpression::Evaluate(
        LocalNameFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  bool v3; // zf
  XPathNavigatorInternal *ContextNode; // rax
  __int64 result; // rax
  unsigned __int16 *v7; // rdx
  unsigned __int64 v8; // kr00_8
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // ecx
  unsigned __int16 *v12; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 9) == 0;
  v12 = 0;
  if ( v3 )
  {
    ContextNode = XPathEvaluationContext::QueryContextNode(a2);
LABEL_3:
    result = XPathNavigatorInternal::GetLocalNameAtomized(ContextNode, (const unsigned __int16 **)&v12);
    if ( (int)result < 0 )
      return result;
    v7 = v12;
    goto LABEL_9;
  }
  v8 = **((_QWORD **)this + 3);
  v9 = (v8 - 8) & ((unsigned __int128)-(__int128)v8 >> 64);
  result = (*(__int64 (__fastcall **)(__int64, struct XPathEvaluationContext *))(*(_QWORD *)v9 + 104LL))(v9, a2);
  if ( (int)result < 0 )
    return result;
  if ( !(_DWORD)result )
  {
    ContextNode = (XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 72LL))((v8 - 8) & ((unsigned __int128)-(__int128)v8 >> 64));
    goto LABEL_3;
  }
  v7 = (unsigned __int16 *)&qword_180016F98;
  v12 = (unsigned __int16 *)&qword_180016F98;
LABEL_9:
  v10 = String::Initialize(a3, v7);
  v11 = 0;
  if ( v10 < 0 )
    return (unsigned int)v10;
  return v11;
}

```

## disassembly

```asm
0x18000b970  mov     [rsp+arg_8], rbx
0x18000b975  push    rdi
0x18000b976  sub     rsp, 20h
0x18000b97a  cmp     dword ptr [rcx+24h], 0
0x18000b97e  mov     rdi, r8
0x18000b981  mov     [rsp+28h+arg_0], 0
0x18000b98a  jnz     short loc_18000B9AC
0x18000b98c  mov     rcx, rdx; this
0x18000b98f  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000b994  lea     rdx, [rsp+28h+arg_0]; unsigned __int16 **
0x18000b999  mov     rcx, rax; this
0x18000b99c  call    ?GetLocalNameAtomized@XPathNavigatorInternal@@QEAAJPEAPEBG@Z; XPathNavigatorInternal::GetLocalNameAtomized(ushort const * *)
0x18000b9a1  test    eax, eax
0x18000b9a3  js      short loc_18000BA03
0x18000b9a5  mov     rdx, [rsp+28h+arg_0]
0x18000b9aa  jmp     short loc_18000B9F2
0x18000b9ac  mov     rax, [rcx+18h]
0x18000b9b0  mov     rcx, [rax]
0x18000b9b3  lea     rax, [rcx-8]
0x18000b9b7  neg     rcx
0x18000b9ba  sbb     rbx, rbx
0x18000b9bd  and     rbx, rax
0x18000b9c0  mov     rcx, rbx
0x18000b9c3  mov     rax, [rbx]
0x18000b9c6  mov     rax, [rax+68h]
0x18000b9ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9cf  test    eax, eax
0x18000b9d1  js      short loc_18000BA03
0x18000b9d3  jnz     short loc_18000B9E6
0x18000b9d5  mov     rax, [rbx]
0x18000b9d8  mov     rcx, rbx
0x18000b9db  mov     rax, [rax+48h]
0x18000b9df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e4  jmp     short loc_18000B994
0x18000b9e6  lea     rdx, qword_180016F98; unsigned __int16 *
0x18000b9ed  mov     [rsp+28h+arg_0], rdx
0x18000b9f2  mov     rcx, rdi; this
0x18000b9f5  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000b9fa  xor     ecx, ecx
0x18000b9fc  test    eax, eax
0x18000b9fe  cmovs   ecx, eax
0x18000ba01  mov     eax, ecx
0x18000ba03  mov     rbx, [rsp+28h+arg_8]
0x18000ba08  add     rsp, 20h
0x18000ba0c  pop     rdi
0x18000ba0d  retn
```
