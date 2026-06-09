# StateRepository::Text::SetFromChars(ushort const *,unsigned __int64)

- ea: `0x1800149f4`
- end: `0x180014ab4`
- name: `?SetFromChars@Text@StateRepository@@QEAAJPEBG_K@Z`
- size: `192`
- prototype: `int(StateRepository::Text *__hidden this, const unsigned __int16 *, unsigned __int64)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180014728`

## callees

- `0x18000a3c0`
- `0x180014814`
- `0x1800148b8`
- `0x1800149f4`
- `0x180014b3c`
- `0x180014ca0`

## string_xrefs

- `0x180014a25`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180014a5c`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`
- `0x180014a8e`: `onecore\base\appmodel\staterepository\dataaccesslayer\text.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Text::SetFromChars(
        StateRepository::Text *this,
        const unsigned __int16 *a2,
        unsigned __int64 a3)
{
  unsigned __int64 v7; // rbp
  int v8; // eax
  unsigned int v9; // esi
  int v10; // eax
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a2 )
  {
    if ( a3 > 0x1DCD6500 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x85,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)0x80070057LL,
        v11);
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
        v11);
      return v9;
    }
    v10 = StringCchCopyNW(*(unsigned __int16 **)this, v7, a2, a3);
    if ( v10 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0x87,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\dataaccesslayer\\text.cpp",
        (const char *)(unsigned int)v10,
        v11);
    *((_QWORD *)this + 1) = v7;
  }
  else
  {
    StateRepository::Text::Reset(this);
  }
  return 0;
}

```

## disassembly

```asm
0x1800149f4  push    rbx
0x1800149f6  push    rbp
0x1800149f7  push    rsi
0x1800149f8  push    rdi
0x1800149f9  push    r14; int
0x1800149fb  sub     rsp, 20h
0x1800149ff  mov     rdi, r8
0x180014a02  mov     r14, rdx
0x180014a05  mov     rbx, rcx
0x180014a08  test    rdx, rdx
0x180014a0b  jnz     short loc_180014A17
0x180014a0d  call    ?Reset@Text@StateRepository@@QEAAXXZ; StateRepository::Text::Reset(void)
0x180014a12  jmp     loc_180014AA7
0x180014a17  cmp     rdi, 1DCD6500h
0x180014a1e  jbe     short loc_180014A42
0x180014a20  mov     rcx, [rsp+48h]; this
0x180014a25  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x180014a2c  mov     ebx, 80070057h
0x180014a31  mov     edx, 85h; void *
0x180014a36  mov     r9d, ebx; char *
0x180014a39  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a3e  mov     eax, ebx
0x180014a40  jmp     short loc_180014AA9
0x180014a42  lea     rbp, [r8+1]
0x180014a46  xor     r8d, r8d; bool
0x180014a49  mov     rdx, rbp; unsigned __int64
0x180014a4c  call    ?EnsureCapacity@Text@StateRepository@@QEAAJ_K_N@Z; StateRepository::Text::EnsureCapacity(unsigned __int64,bool)
0x180014a51  mov     esi, eax
0x180014a53  test    eax, eax
0x180014a55  jns     short loc_180014A74
0x180014a57  mov     rcx, [rsp+48h]; this
0x180014a5c  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x180014a63  mov     r9d, eax; char *
0x180014a66  mov     edx, 86h; void *
0x180014a6b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180014a70  mov     eax, esi
0x180014a72  jmp     short loc_180014AA9
0x180014a74  mov     rcx, [rbx]; unsigned __int16 *
0x180014a77  mov     r9, rdi; unsigned __int64
0x180014a7a  mov     r8, r14; unsigned __int16 *
0x180014a7d  mov     rdx, rbp; unsigned __int64
0x180014a80  call    ?StringCchCopyNW@@YAJPEAG_KPEBG1@Z; StringCchCopyNW(ushort *,unsigned __int64,ushort const *,unsigned __int64)
0x180014a85  test    eax, eax
0x180014a87  jns     short loc_180014AA3
0x180014a89  mov     rcx, [rsp+48h]; this
0x180014a8e  lea     r8, aOnecoreBaseApp_48; "onecore\\base\\appmodel\\staterepositor"...
0x180014a95  mov     r9d, eax; char *
0x180014a98  mov     edx, 87h; void *
0x180014a9d  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180014aa3  mov     [rbx+8], rbp
0x180014aa7  xor     eax, eax
0x180014aa9  add     rsp, 20h
0x180014aad  pop     r14
0x180014aaf  pop     rdi
0x180014ab0  pop     rsi
0x180014ab1  pop     rbp
0x180014ab2  pop     rbx
0x180014ab3  retn
```
