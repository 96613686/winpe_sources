# ContainsFunctionExpression::Evaluate(XPathEvaluationContext *,bool &)

- ea: `0x18000b790`
- end: `0x18000b84e`
- name: `?Evaluate@ContainsFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEA_N@Z`
- size: `190`
- prototype: `__int64 __fastcall(ContainsFunctionExpression *__hidden this, struct XPathEvaluationContext *, bool *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18000b790`
- `0x180010fac`
- `0x180012010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000b819`
- `msvcrt!wcsstr` at `0x18000b819`

## pseudocode

```c
__int64 __fastcall ContainsFunctionExpression::Evaluate(
        ContainsFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        bool *a3)
{
  _QWORD *v3; // rax
  int v7; // ebx
  wchar_t *v8; // rcx
  wchar_t *v9; // rdx
  wchar_t *SubStr; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *Str; // [rsp+58h] [rbp+20h] BYREF

  v3 = (_QWORD *)*((_QWORD *)this + 3);
  Str = 0;
  SubStr = 0;
  v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, wchar_t **))(*(_QWORD *)*v3 + 64LL))(
         *v3,
         a2,
         &Str);
  if ( v7 >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, struct XPathEvaluationContext *, wchar_t **))(**(_QWORD **)(*((_QWORD *)this + 3) + 8LL)
                                                                                        + 64LL))(
           *(_QWORD *)(*((_QWORD *)this + 3) + 8LL),
           a2,
           &SubStr);
    if ( v7 >= 0 )
    {
      v8 = (wchar_t *)&qword_180016F98;
      v9 = (wchar_t *)&qword_180016F98;
      if ( SubStr )
        v9 = SubStr;
      if ( Str )
        v8 = Str;
      v7 = 0;
      *a3 = wcsstr(v8, v9) != 0;
    }
  }
  String::Reset((String *)&SubStr);
  String::Reset((String *)&Str);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000b790  mov     r11, rsp
0x18000b793  mov     [r11+10h], rbx
0x18000b797  push    rsi
0x18000b798  push    rdi
0x18000b799  push    r14
0x18000b79b  sub     rsp, 20h
0x18000b79f  mov     rax, [rcx+18h]
0x18000b7a3  mov     rsi, rcx
0x18000b7a6  mov     qword ptr [r11+20h], 0
0x18000b7ae  mov     r14, r8
0x18000b7b1  mov     qword ptr [r11+8], 0
0x18000b7b9  lea     r8, [r11+20h]
0x18000b7bd  mov     rdi, rdx
0x18000b7c0  mov     rcx, [rax]
0x18000b7c3  mov     rax, [rcx]
0x18000b7c6  mov     rax, [rax+40h]
0x18000b7ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7cf  mov     ebx, eax
0x18000b7d1  test    eax, eax
0x18000b7d3  js      short loc_18000B82A
0x18000b7d5  mov     rax, [rsi+18h]
0x18000b7d9  lea     r8, [rsp+38h+SubStr]
0x18000b7de  mov     rdx, rdi
0x18000b7e1  mov     rcx, [rax+8]
0x18000b7e5  mov     rax, [rcx]
0x18000b7e8  mov     rax, [rax+40h]
0x18000b7ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b7f1  mov     ebx, eax
0x18000b7f3  test    eax, eax
0x18000b7f5  js      short loc_18000B82A
0x18000b7f7  mov     rax, [rsp+38h+SubStr]
0x18000b7fc  lea     rcx, qword_180016F98
0x18000b803  test    rax, rax
0x18000b806  mov     rdx, rcx
0x18000b809  cmovnz  rdx, rax; SubStr
0x18000b80d  mov     rax, [rsp+38h+Str]
0x18000b812  test    rax, rax
0x18000b815  cmovnz  rcx, rax; Str
0x18000b819  call    cs:__imp_wcsstr
0x18000b81f  test    rax, rax
0x18000b822  setnz   al
0x18000b825  xor     ebx, ebx
0x18000b827  mov     [r14], al
0x18000b82a  lea     rcx, [rsp+38h+SubStr]; this
0x18000b82f  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b834  lea     rcx, [rsp+38h+Str]; this
0x18000b839  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000b83e  mov     eax, ebx
0x18000b840  mov     rbx, [rsp+38h+arg_8]
0x18000b845  add     rsp, 20h
0x18000b849  pop     r14
0x18000b84b  pop     rdi
0x18000b84c  pop     rsi
0x18000b84d  retn
```
