# NamespaceUriFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000bb50`
- end: `0x18000bbf5`
- name: `?Evaluate@NamespaceUriFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `165`
- prototype: `int(NamespaceUriFunctionExpression *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `4`
- tags: `broker_com_uri`

## callees

- `0x1800052bc`
- `0x18000bb50`
- `0x180010ee0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall NamespaceUriFunctionExpression::Evaluate(
        NamespaceUriFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  bool v3; // zf
  struct XPathNavigatorInternal *ContextNode; // rax
  __int64 result; // rax
  const unsigned __int16 *v7; // rdx
  unsigned __int64 v8; // kr00_8
  __int64 v9; // rbx
  int v10; // eax
  unsigned int v11; // ecx
  const unsigned __int16 *v12; // [rsp+30h] [rbp+8h] BYREF

  v3 = *((_DWORD *)this + 9) == 0;
  v12 = 0;
  if ( v3 )
  {
    ContextNode = XPathEvaluationContext::QueryContextNode(a2);
LABEL_3:
    result = (*(__int64 (__fastcall **)(_QWORD, const unsigned __int16 **))(**(_QWORD **)ContextNode + 48LL))(
               *(_QWORD *)ContextNode,
               &v12);
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
    ContextNode = (struct XPathNavigatorInternal *)(*(__int64 (__fastcall **)(_QWORD))(*(_QWORD *)v9 + 72LL))((v8 - 8) & ((unsigned __int128)-(__int128)v8 >> 64));
    goto LABEL_3;
  }
  v7 = &qword_180016F98;
  v12 = &qword_180016F98;
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
0x18000bb50  mov     [rsp+arg_8], rbx
0x18000bb55  push    rdi
0x18000bb56  sub     rsp, 20h
0x18000bb5a  cmp     dword ptr [rcx+24h], 0
0x18000bb5e  mov     rdi, r8
0x18000bb61  mov     [rsp+28h+arg_0], 0
0x18000bb6a  jnz     short loc_18000BB93
0x18000bb6c  mov     rcx, rdx; this
0x18000bb6f  call    ?QueryContextNode@XPathEvaluationContext@@QEAAAEAVXPathNavigatorInternal@@XZ; XPathEvaluationContext::QueryContextNode(void)
0x18000bb74  mov     rcx, [rax]
0x18000bb77  lea     rdx, [rsp+28h+arg_0]
0x18000bb7c  mov     rax, [rcx]
0x18000bb7f  mov     rax, [rax+30h]
0x18000bb83  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bb88  test    eax, eax
0x18000bb8a  js      short loc_18000BBEA
0x18000bb8c  mov     rdx, [rsp+28h+arg_0]
0x18000bb91  jmp     short loc_18000BBD9
0x18000bb93  mov     rax, [rcx+18h]
0x18000bb97  mov     rcx, [rax]
0x18000bb9a  lea     rax, [rcx-8]
0x18000bb9e  neg     rcx
0x18000bba1  sbb     rbx, rbx
0x18000bba4  and     rbx, rax
0x18000bba7  mov     rcx, rbx
0x18000bbaa  mov     rax, [rbx]
0x18000bbad  mov     rax, [rax+68h]
0x18000bbb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbb6  test    eax, eax
0x18000bbb8  js      short loc_18000BBEA
0x18000bbba  jnz     short loc_18000BBCD
0x18000bbbc  mov     rax, [rbx]
0x18000bbbf  mov     rcx, rbx
0x18000bbc2  mov     rax, [rax+48h]
0x18000bbc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000bbcb  jmp     short loc_18000BB74
0x18000bbcd  lea     rdx, qword_180016F98; unsigned __int16 *
0x18000bbd4  mov     [rsp+28h+arg_0], rdx
0x18000bbd9  mov     rcx, rdi; this
0x18000bbdc  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000bbe1  xor     ecx, ecx
0x18000bbe3  test    eax, eax
0x18000bbe5  cmovs   ecx, eax
0x18000bbe8  mov     eax, ecx
0x18000bbea  mov     rbx, [rsp+28h+arg_8]
0x18000bbef  add     rsp, 20h
0x18000bbf3  pop     rdi
0x18000bbf4  retn
```
