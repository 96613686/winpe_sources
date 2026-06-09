# Common::StringBuffer::SetValue(ushort const *,ulong)

- ea: `0x14000e54c`
- end: `0x14000e616`
- name: `?SetValue@StringBuffer@Common@@QEAAJPEBGK@Z`
- size: `202`
- prototype: `__int64 __fastcall(Common::StringBuffer *__hidden this, const unsigned __int16 *Src, unsigned int)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x14000e61c`

## callees

- `0x140003f74`
- `0x14000b854`
- `0x14000e3ec`
- `0x14000e4d0`
- `0x14000e54c`

## string_xrefs

- `0x14000e56c`: `onecore\base\appmodel\common\widestring.cpp`
- `0x14000e5d1`: `onecore\base\appmodel\common\widestring.cpp`

## pseudocode

```c
__int64 __fastcall Common::StringBuffer::SetValue(
        Common::StringBuffer *this,
        const unsigned __int16 *Src,
        unsigned int a3)
{
  unsigned int v7; // edx
  unsigned int i; // edx
  int v9; // edi
  __int64 v10; // rdx
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( a3 > 0x7FFFFFFF )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x22F,
      (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
      (const char *)0x80070216LL);
    return 2147942934LL;
  }
  v7 = *((_DWORD *)this + 4) != 0 ? *((_DWORD *)this + 4) - 1 : 0;
  if ( a3 > v7 || v7 > 0x20 )
  {
    if ( a3 <= 0x20 )
    {
      for ( i = 8; i < a3; i *= 2 )
        ;
    }
    else
    {
      i = a3;
    }
    v9 = Common::StringBuffer::SetCapacity((void **)this, i);
    if ( v9 < 0 )
    {
      v10 = 562;
LABEL_11:
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)v10,
        (int)"onecore\\base\\appmodel\\common\\widestring.cpp",
        (const char *)(unsigned int)v9);
      return (unsigned int)v9;
    }
  }
  v9 = Common::StringBuffer::SetLength(this, a3);
  if ( v9 < 0 )
  {
    v10 = 565;
    goto LABEL_11;
  }
  memcpy_0(*((void **)this + 1), Src, 2 * a3);
  return 0;
}

```

## disassembly

```asm
0x14000e54c  push    rbx
0x14000e54e  push    rbp
0x14000e54f  push    rsi
0x14000e550  push    rdi
0x14000e551  sub     rsp, 28h
0x14000e555  mov     ebx, r8d
0x14000e558  mov     rbp, rdx
0x14000e55b  mov     rsi, rcx
0x14000e55e  cmp     r8d, 7FFFFFFFh
0x14000e565  jbe     short loc_14000E58C
0x14000e567  mov     rcx, [rsp+48h]; this
0x14000e56c  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e573  mov     ebx, 80070216h
0x14000e578  mov     edx, 22Fh; void *
0x14000e57d  mov     r9d, ebx; char *
0x14000e580  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e585  mov     eax, ebx
0x14000e587  jmp     loc_14000E60D
0x14000e58c  mov     eax, [rcx+10h]
0x14000e58f  lea     ecx, [rax-1]
0x14000e592  neg     eax
0x14000e594  sbb     edx, edx
0x14000e596  and     edx, ecx
0x14000e598  cmp     ebx, edx
0x14000e59a  ja      short loc_14000E5A1
0x14000e59c  cmp     edx, 20h ; ' '
0x14000e59f  jbe     short loc_14000E5E4
0x14000e5a1  cmp     ebx, 20h ; ' '
0x14000e5a4  jbe     short loc_14000E5AA
0x14000e5a6  mov     edx, ebx
0x14000e5a8  jmp     short loc_14000E5B9
0x14000e5aa  mov     edx, 8
0x14000e5af  cmp     ebx, edx
0x14000e5b1  jbe     short loc_14000E5B9
0x14000e5b3  add     edx, edx; unsigned int
0x14000e5b5  cmp     edx, ebx
0x14000e5b7  jb      short loc_14000E5B3
0x14000e5b9  mov     rcx, rsi; this
0x14000e5bc  call    ?SetCapacity@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetCapacity(ulong)
0x14000e5c1  mov     edi, eax
0x14000e5c3  test    eax, eax
0x14000e5c5  jns     short loc_14000E5E4
0x14000e5c7  mov     edx, 232h; void *
0x14000e5cc  mov     rcx, [rsp+48h]; this
0x14000e5d1  lea     r8, aOnecoreBaseApp_0; "onecore\\base\\appmodel\\common\\widest"...
0x14000e5d8  mov     r9d, edi; char *
0x14000e5db  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x14000e5e0  mov     eax, edi
0x14000e5e2  jmp     short loc_14000E60D
0x14000e5e4  mov     edx, ebx; unsigned int
0x14000e5e6  mov     rcx, rsi; this
0x14000e5e9  call    ?SetLength@StringBuffer@Common@@QEAAJK@Z; Common::StringBuffer::SetLength(ulong)
0x14000e5ee  mov     edi, eax
0x14000e5f0  test    eax, eax
0x14000e5f2  jns     short loc_14000E5FB
0x14000e5f4  mov     edx, 235h
0x14000e5f9  jmp     short loc_14000E5CC
0x14000e5fb  mov     rcx, [rsi+8]; void *
0x14000e5ff  lea     r8d, [rbx+rbx]; Size
0x14000e603  mov     rdx, rbp; Src
0x14000e606  call    memcpy_0
0x14000e60b  xor     eax, eax
0x14000e60d  add     rsp, 28h
0x14000e611  pop     rdi
0x14000e612  pop     rsi
0x14000e613  pop     rbp
0x14000e614  pop     rbx
0x14000e615  retn
```
