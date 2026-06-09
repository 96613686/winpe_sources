# StateRepository::Text::SetFromChars(wchar_t const *,unsigned __int64)

- ea: `0x180102954`
- end: `0x180102a75`
- name: `?SetFromChars@Text@StateRepository@@QEAAJPEB_W_K@Z`
- size: `289`
- prototype: `__int64 __fastcall(StateRepository::Text *__hidden this, const wchar_t *, unsigned __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1801025a4`

## callees

- `0x1800eabf4`
- `0x1800edb2c`
- `0x18010272c`
- `0x1801027d0`
- `0x180102954`

## string_xrefs

- `0x18010298a`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x1801029cc`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180102a60`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Text::SetFromChars(const void **this, const wchar_t *a2, unsigned __int64 a3)
{
  unsigned __int64 v3; // rbx
  const wchar_t *v4; // r14
  unsigned __int64 v7; // rdi
  int v8; // eax
  unsigned int v9; // ebp
  _WORD *v10; // rdx
  unsigned int v11; // ebx
  unsigned __int64 v12; // r8
  _WORD *v13; // rcx
  int v14; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v3 = a3;
  v4 = a2;
  if ( a2 )
  {
    if ( a3 > 0x1DCD6500 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)0x80070057LL,
        v14);
      return 2147942487LL;
    }
    v7 = a3 + 1;
    v8 = StateRepository::Text::EnsureCapacity(this, a3 + 1, 0);
    v9 = v8;
    if ( v8 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x86,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)(unsigned int)v8,
        v14);
      return v9;
    }
    v10 = *this;
    if ( v7 )
    {
      if ( v7 <= 0x7FFFFFFF )
      {
        v12 = v7;
        do
        {
          if ( !v3 )
            break;
          if ( !*v4 )
            break;
          *v10++ = *v4++;
          --v3;
          --v12;
        }
        while ( v12 );
        v13 = v10 - 1;
        v11 = v12 == 0 ? 0x8007007A : 0;
        if ( v12 )
          v13 = v10;
        *v13 = 0;
        if ( v12 )
        {
          this[1] = (const void *)v7;
          return 0;
        }
      }
      else
      {
        v11 = -2147024809;
        *v10 = 0;
      }
    }
    else
    {
      v11 = -2147024809;
    }
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x87,
      (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
      (const char *)v11,
      v14);
  }
  StateRepository::TextA::Reset((StateRepository::TextA *)this);
  return 0;
}

```

## disassembly

```asm
0x180102954  push    rbx
0x180102956  push    rbp
0x180102957  push    rsi
0x180102958  push    rdi
0x180102959  push    r14
0x18010295b  push    r15
0x18010295d  sub     rsp, 28h
0x180102961  xor     r15d, r15d
0x180102964  mov     rbx, r8
0x180102967  mov     r14, rdx
0x18010296a  mov     rsi, rcx
0x18010296d  test    rdx, rdx
0x180102970  jnz     short loc_18010297C
0x180102972  call    ?Reset@TextA@StateRepository@@QEAAXXZ; StateRepository::TextA::Reset(void)
0x180102977  jmp     loc_180102A46
0x18010297c  cmp     rbx, 1DCD6500h
0x180102983  jbe     short loc_1801029B2
0x180102985  mov     rcx, [rsp+58h]; this
0x18010298a  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x180102991  mov     ebx, 80070057h
0x180102996  mov     edx, 85h; void *
0x18010299b  mov     r9d, ebx; char *
0x18010299e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801029a3  mov     eax, ebx
0x1801029a5  add     rsp, 28h
0x1801029a9  pop     r15
0x1801029ab  pop     r14
0x1801029ad  pop     rdi
0x1801029ae  pop     rsi
0x1801029af  pop     rbp
0x1801029b0  pop     rbx
0x1801029b1  retn
0x1801029b2  lea     rdi, [r8+1]
0x1801029b6  xor     r8d, r8d; bool
0x1801029b9  mov     rdx, rdi; unsigned __int64
0x1801029bc  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x1801029c1  mov     ebp, eax
0x1801029c3  test    eax, eax
0x1801029c5  jns     short loc_1801029E4
0x1801029c7  mov     rcx, [rsp+58h]; this
0x1801029cc  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x1801029d3  mov     r9d, eax; char *
0x1801029d6  mov     edx, 86h; void *
0x1801029db  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801029e0  mov     eax, ebp
0x1801029e2  jmp     short loc_1801029A5
0x1801029e4  mov     rdx, [rsi]
0x1801029e7  test    rdi, rdi
0x1801029ea  jz      short loc_180102A4D
0x1801029ec  cmp     rdi, 7FFFFFFFh
0x1801029f3  jbe     short loc_1801029FC
0x1801029f5  mov     ebx, 80070057h
0x1801029fa  jmp     short loc_180102A57
0x1801029fc  mov     r8, rdi
0x1801029ff  test    rbx, rbx
0x180102a02  jz      short loc_180102A21
0x180102a04  movzx   eax, word ptr [r14]
0x180102a08  test    ax, ax
0x180102a0b  jz      short loc_180102A21
0x180102a0d  mov     [rdx], ax
0x180102a10  add     r14, 2
0x180102a14  add     rdx, 2
0x180102a18  dec     rbx
0x180102a1b  sub     r8, 1
0x180102a1f  jnz     short loc_1801029FF
0x180102a21  mov     rax, r8
0x180102a24  lea     rcx, [rdx-2]
0x180102a28  neg     rax
0x180102a2b  sbb     ebx, ebx
0x180102a2d  not     ebx
0x180102a2f  and     ebx, 8007007Ah
0x180102a35  test    r8, r8
0x180102a38  cmovnz  rcx, rdx
0x180102a3c  mov     [rcx], r15w
0x180102a40  jz      short loc_180102A5B
0x180102a42  mov     [rsi+8], rdi
0x180102a46  xor     eax, eax
0x180102a48  jmp     loc_1801029A5
0x180102a4d  mov     ebx, 80070057h
0x180102a52  test    rdi, rdi
0x180102a55  jz      short loc_180102A5B
0x180102a57  mov     [rdx], r15w
0x180102a5b  mov     rcx, [rsp+58h]; this
0x180102a60  lea     r8, aOnecoreBaseApp_20; "onecore\\base\\appmodel\\staterepositor"...
0x180102a67  mov     r9d, ebx; char *
0x180102a6a  mov     edx, 87h; void *
0x180102a6f  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
