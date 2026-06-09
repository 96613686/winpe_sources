# SubstringBeforeFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000c1e0`
- end: `0x18000c2d5`
- name: `?Evaluate@SubstringBeforeFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `245`
- prototype: `int(SubstringBeforeFunctionExpression *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18000c1e0`
- `0x180010f08`
- `0x180010fac`
- `0x180012010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000c26f`
- `msvcrt!wcsstr` at `0x18000c26f`

## pseudocode

```c
__int64 __fastcall SubstringBeforeFunctionExpression::Evaluate(
        SubstringBeforeFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  _QWORD *v3; // rax
  int v7; // ebx
  wchar_t *v8; // rbx
  wchar_t *v9; // rdx
  wchar_t *v10; // rcx
  wchar_t *v11; // r8
  wchar_t *v12; // rcx
  unsigned __int64 v13; // r8
  wchar_t *Str; // [rsp+40h] [rbp+8h] BYREF
  wchar_t *SubStr; // [rsp+58h] [rbp+20h] BYREF

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
      v10 = (wchar_t *)&qword_180016F98;
      if ( SubStr )
        v9 = SubStr;
      if ( Str )
        v10 = Str;
      v11 = wcsstr(v10, v9);
      if ( v11 )
      {
        v12 = (wchar_t *)&qword_180016F98;
        if ( Str )
          v12 = Str;
        v13 = v11 - v12;
        if ( Str )
          v8 = Str;
        v7 = String::Initialize(a3, v8, v13);
      }
      else
      {
        String::Reset(a3);
        v7 = 0;
      }
    }
  }
  String::Reset((String *)&SubStr);
  String::Reset((String *)&Str);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000c1e0  mov     r11, rsp
0x18000c1e3  mov     [r11+10h], rbx
0x18000c1e7  push    rbp
0x18000c1e8  push    rsi
0x18000c1e9  push    rdi
0x18000c1ea  sub     rsp, 20h
0x18000c1ee  mov     rax, [rcx+18h]
0x18000c1f2  mov     rbp, rcx
0x18000c1f5  mov     qword ptr [r11+8], 0
0x18000c1fd  mov     rdi, r8
0x18000c200  mov     qword ptr [r11+20h], 0
0x18000c208  lea     r8, [r11+8]
0x18000c20c  mov     rsi, rdx
0x18000c20f  mov     rcx, [rax]
0x18000c212  mov     rax, [rcx]
0x18000c215  mov     rax, [rax+40h]
0x18000c219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c21e  mov     ebx, eax
0x18000c220  test    eax, eax
0x18000c222  js      loc_18000C2B2
0x18000c228  mov     rax, [rbp+18h]
0x18000c22c  lea     r8, [rsp+38h+SubStr]
0x18000c231  mov     rdx, rsi
0x18000c234  mov     rcx, [rax+8]
0x18000c238  mov     rax, [rcx]
0x18000c23b  mov     rax, [rax+40h]
0x18000c23f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c244  mov     ebx, eax
0x18000c246  test    eax, eax
0x18000c248  js      short loc_18000C2B2
0x18000c24a  mov     rax, [rsp+38h+SubStr]
0x18000c24f  lea     rbx, qword_180016F98
0x18000c256  test    rax, rax
0x18000c259  mov     rdx, rbx
0x18000c25c  mov     rcx, rbx
0x18000c25f  cmovnz  rdx, rax; SubStr
0x18000c263  mov     rax, [rsp+38h+Str]
0x18000c268  test    rax, rax
0x18000c26b  cmovnz  rcx, rax; Str
0x18000c26f  call    cs:__imp_wcsstr
0x18000c275  mov     r8, rax
0x18000c278  test    rax, rax
0x18000c27b  jnz     short loc_18000C289
0x18000c27d  mov     rcx, rdi; this
0x18000c280  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c285  xor     ebx, ebx
0x18000c287  jmp     short loc_18000C2B2
0x18000c289  mov     rax, [rsp+38h+Str]
0x18000c28e  mov     rcx, rbx
0x18000c291  test    rax, rax
0x18000c294  cmovnz  rcx, rax
0x18000c298  sub     r8, rcx
0x18000c29b  mov     rcx, rdi; this
0x18000c29e  sar     r8, 1; unsigned __int64
0x18000c2a1  test    rax, rax
0x18000c2a4  cmovnz  rbx, rax
0x18000c2a8  mov     rdx, rbx; Src
0x18000c2ab  call    ?Initialize@String@@QEAAJPEBG_K@Z; String::Initialize(ushort const *,unsigned __int64)
0x18000c2b0  mov     ebx, eax
0x18000c2b2  lea     rcx, [rsp+38h+SubStr]; this
0x18000c2b7  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c2bc  lea     rcx, [rsp+38h+Str]; this
0x18000c2c1  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c2c6  mov     eax, ebx
0x18000c2c8  mov     rbx, [rsp+38h+arg_8]
0x18000c2cd  add     rsp, 20h
0x18000c2d1  pop     rdi
0x18000c2d2  pop     rsi
0x18000c2d3  pop     rbp
0x18000c2d4  retn
```
