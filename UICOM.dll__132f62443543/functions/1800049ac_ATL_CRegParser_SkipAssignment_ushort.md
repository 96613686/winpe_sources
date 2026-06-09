# ATL::CRegParser::SkipAssignment(ushort *)

- ea: `0x1800049ac`
- end: `0x180004a58`
- name: `?SkipAssignment@CRegParser@ATL@@IEAAJPEAG@Z`
- size: `172`
- prototype: `__int64 __fastcall(ATL::CRegParser *__hidden this, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x1800041fc`

## callees

- `0x1800038f4`
- `0x1800049ac`
- `0x180005f60`
- `0x180005ff0`

## import_xrefs

- `USER32!CharNextW` at `0x180004a03`
- `USER32!CharNextW` at `0x180004a03`

## pseudocode

```c
__int64 __fastcall ATL::CRegParser::SkipAssignment(LPCWSTR *this, unsigned __int16 *a2)
{
  __int64 result; // rax
  int Token; // eax
  unsigned int v6; // ecx
  unsigned __int16 v7[4096]; // [rsp+20h] [rbp-2018h] BYREF

  if ( *a2 != 61 )
    return 0;
  result = ATL::CRegParser::NextToken(this, a2);
  if ( (int)result >= 0 )
  {
    while ( **this == 9 || **this == 10 || **this == 13 || **this == 32 )
      *this = CharNextW(*this);
    result = ATL::CRegParser::NextToken(this, v7);
    if ( (int)result >= 0 )
    {
      Token = ATL::CRegParser::NextToken(this, a2);
      v6 = 0;
      if ( Token < 0 )
        return (unsigned int)Token;
      return v6;
    }
  }
  return result;
}

```

## disassembly

```asm
0x1800049ac  mov     [rsp+arg_10], rbx
0x1800049b1  push    rdi
0x1800049b2  mov     eax, 2030h
0x1800049b7  call    _alloca_probe
0x1800049bc  sub     rsp, rax
0x1800049bf  mov     rax, cs:__security_cookie
0x1800049c6  xor     rax, rsp
0x1800049c9  mov     [rsp+2038h+var_18], rax
0x1800049d1  cmp     word ptr [rdx], 3Dh ; '='
0x1800049d5  mov     rdi, rdx
0x1800049d8  mov     rbx, rcx
0x1800049db  jnz     short loc_180004A35
0x1800049dd  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x1800049e2  test    eax, eax
0x1800049e4  js      short loc_180004A37
0x1800049e6  mov     rdx, [rbx]
0x1800049e9  movzx   ecx, word ptr [rdx]
0x1800049ec  sub     ecx, 9
0x1800049ef  jz      short loc_180004A00
0x1800049f1  sub     ecx, 1
0x1800049f4  jz      short loc_180004A00
0x1800049f6  sub     ecx, 3
0x1800049f9  jz      short loc_180004A00
0x1800049fb  cmp     ecx, 13h
0x1800049fe  jnz     short loc_180004A0E
0x180004a00  mov     rcx, rdx; lpsz
0x180004a03  call    cs:__imp_CharNextW
0x180004a09  mov     [rbx], rax
0x180004a0c  jmp     short loc_1800049E6
0x180004a0e  lea     rdx, [rsp+2038h+var_2018]; unsigned __int16 *
0x180004a13  mov     rcx, rbx; this
0x180004a16  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a1b  test    eax, eax
0x180004a1d  js      short loc_180004A37
0x180004a1f  mov     rdx, rdi; unsigned __int16 *
0x180004a22  mov     rcx, rbx; this
0x180004a25  call    ?NextToken@CRegParser@ATL@@IEAAJPEAG@Z; ATL::CRegParser::NextToken(ushort *)
0x180004a2a  xor     ecx, ecx
0x180004a2c  test    eax, eax
0x180004a2e  cmovs   ecx, eax
0x180004a31  mov     eax, ecx
0x180004a33  jmp     short loc_180004A37
0x180004a35  xor     eax, eax
0x180004a37  mov     rcx, [rsp+2038h+var_18]
0x180004a3f  xor     rcx, rsp; StackCookie
0x180004a42  call    __security_check_cookie
0x180004a47  mov     rbx, [rsp+2038h+arg_10]
0x180004a4f  add     rsp, 2030h
0x180004a56  pop     rdi
0x180004a57  retn
```
