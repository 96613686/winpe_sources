# SubstringAfterFunctionExpression::Evaluate(XPathEvaluationContext *,String &)

- ea: `0x18000c0f0`
- end: `0x18000c1ce`
- name: `?Evaluate@SubstringAfterFunctionExpression@@UEAAJPEAVXPathEvaluationContext@@AEAVString@@@Z`
- size: `222`
- prototype: `int(SubstringAfterFunctionExpression *__hidden this, struct XPathEvaluationContext *, struct String *)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x18000c0f0`
- `0x180010ee0`
- `0x180010f98`
- `0x180010fac`
- `0x180012010`

## import_xrefs

- `msvcrt!wcsstr` at `0x18000c186`
- `msvcrt!wcsstr` at `0x18000c186`

## pseudocode

```c
__int64 __fastcall SubstringAfterFunctionExpression::Evaluate(
        SubstringAfterFunctionExpression *this,
        struct XPathEvaluationContext *a2,
        struct String *a3)
{
  _QWORD *v3; // rax
  int v7; // ebx
  wchar_t *v8; // rcx
  wchar_t *v9; // rdx
  wchar_t *v10; // rax
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
      if ( !String::QueryCCH((String *)&Str) )
        goto LABEL_10;
      v8 = (wchar_t *)&qword_180016F98;
      v9 = (wchar_t *)&qword_180016F98;
      if ( SubStr )
        v9 = SubStr;
      if ( Str )
        v8 = Str;
      v10 = wcsstr(v8, v9);
      if ( v10 )
      {
        v7 = String::Initialize(a3, v10 + 1);
      }
      else
      {
LABEL_10:
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
0x18000c0f0  mov     r11, rsp
0x18000c0f3  mov     [r11+10h], rbx
0x18000c0f7  push    rbp
0x18000c0f8  push    rsi
0x18000c0f9  push    rdi
0x18000c0fa  sub     rsp, 20h
0x18000c0fe  mov     rax, [rcx+18h]
0x18000c102  mov     rbp, rcx
0x18000c105  mov     qword ptr [r11+8], 0
0x18000c10d  mov     rdi, r8
0x18000c110  mov     qword ptr [r11+20h], 0
0x18000c118  lea     r8, [r11+8]
0x18000c11c  mov     rsi, rdx
0x18000c11f  mov     rcx, [rax]
0x18000c122  mov     rax, [rcx]
0x18000c125  mov     rax, [rax+40h]
0x18000c129  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c12e  mov     ebx, eax
0x18000c130  test    eax, eax
0x18000c132  js      short loc_18000C1AB
0x18000c134  mov     rax, [rbp+18h]
0x18000c138  lea     r8, [rsp+38h+SubStr]
0x18000c13d  mov     rdx, rsi
0x18000c140  mov     rcx, [rax+8]
0x18000c144  mov     rax, [rcx]
0x18000c147  mov     rax, [rax+40h]
0x18000c14b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c150  mov     ebx, eax
0x18000c152  test    eax, eax
0x18000c154  js      short loc_18000C1AB
0x18000c156  lea     rcx, [rsp+38h+Str]; this
0x18000c15b  call    ?QueryCCH@String@@QEBAKXZ; String::QueryCCH(void)
0x18000c160  test    eax, eax
0x18000c162  jz      short loc_18000C1A1
0x18000c164  mov     rax, [rsp+38h+SubStr]
0x18000c169  lea     rcx, qword_180016F98
0x18000c170  test    rax, rax
0x18000c173  mov     rdx, rcx
0x18000c176  cmovnz  rdx, rax; SubStr
0x18000c17a  mov     rax, [rsp+38h+Str]
0x18000c17f  test    rax, rax
0x18000c182  cmovnz  rcx, rax; Str
0x18000c186  call    cs:__imp_wcsstr
0x18000c18c  test    rax, rax
0x18000c18f  jz      short loc_18000C1A1
0x18000c191  lea     rdx, [rax+2]; unsigned __int16 *
0x18000c195  mov     rcx, rdi; this
0x18000c198  call    ?Initialize@String@@QEAAJPEBG@Z; String::Initialize(ushort const *)
0x18000c19d  mov     ebx, eax
0x18000c19f  jmp     short loc_18000C1AB
0x18000c1a1  mov     rcx, rdi; this
0x18000c1a4  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c1a9  xor     ebx, ebx
0x18000c1ab  lea     rcx, [rsp+38h+SubStr]; this
0x18000c1b0  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c1b5  lea     rcx, [rsp+38h+Str]; this
0x18000c1ba  call    ?Reset@String@@QEAAXXZ; String::Reset(void)
0x18000c1bf  mov     eax, ebx
0x18000c1c1  mov     rbx, [rsp+38h+arg_8]
0x18000c1c6  add     rsp, 20h
0x18000c1ca  pop     rdi
0x18000c1cb  pop     rsi
0x18000c1cc  pop     rbp
0x18000c1cd  retn
```
