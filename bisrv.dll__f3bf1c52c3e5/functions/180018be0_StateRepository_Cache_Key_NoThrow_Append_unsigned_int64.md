# StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)

- ea: `0x180018be0`
- end: `0x180018eb0`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z`
- size: `720`
- prototype: `int(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64)`
- caller_count: `11`
- callee_count: `4`
- tags: ``

## callers

- `0x180017a4c`
- `0x180017d50`
- `0x18001806c`
- `0x180018eb8`
- `0x180019430`
- `0x180019804`
- `0x18001abd0`
- `0x18001b5f8`
- `0x18001b988`
- `0x18001bc18`
- `0x18001bfcc`

## callees

- `0x180018be0`
- `0x18001a1f0`
- `0x180094662`
- `0x1800946a0`

## import_xrefs

- `msvcrt!_ui64tow_s` at `0x180018c0f`
- `msvcrt!_ui64tow_s` at `0x180018c0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180018e15`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180018e15`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018dc9`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180018dc9`

## string_xrefs

- `0x180018d36`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180018d8a`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180018dea`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180018e28`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180018e46`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        unsigned __int64 a2)
{
  wchar_t *v3; // rax
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  _WORD *v7; // r8
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  _WORD *v10; // rax
  unsigned int v11; // esi
  unsigned __int64 v12; // rax
  wchar_t *v13; // rdx
  _WORD *v14; // r8
  unsigned __int64 v15; // rdi
  __int64 v17; // rcx
  void *v18; // rax
  void *v19; // rsi
  wchar_t *v20; // rdx
  _WORD *v21; // rcx
  unsigned __int64 i; // r8
  int Buffer[10]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( _ui64tow_s(a2, (wchar_t *)Buffer, 0x11u, 16) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      Buffer[0]);
    return 2147549183LL;
  }
  else
  {
    v3 = (wchar_t *)Buffer;
    v4 = 0;
    v5 = 0;
    while ( *v3 )
    {
      if ( ++v4 >= 0x7FFFFFFF )
      {
        v11 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x80070057LL,
          Buffer[0]);
        return v11;
      }
      if ( *v3 == 94 )
        ++v5;
      ++v3;
    }
    v6 = v4 + v5 + *((_QWORD *)this + 65) + 1LL;
    if ( v6 <= *((_QWORD *)this + 66) )
    {
      v7 = (_WORD *)*((_QWORD *)this + 67);
      v6 = *((_QWORD *)this + 66);
      goto LABEL_10;
    }
    v18 = (void *)SRCache_AllocStringBuffer((unsigned int)v6);
    v19 = v18;
    if ( v18 )
    {
      memcpy_0(v18, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      v17 = *(_QWORD *)this;
      *(_QWORD *)this = v19;
      if ( v17 )
        SRCache_Free(v17);
      v7 = *(_WORD **)this;
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v6;
LABEL_10:
      if ( v5 )
      {
        v20 = (wchar_t *)Buffer;
        v21 = &v7[*((_QWORD *)this + 65)];
        for ( i = 0; i < v4; ++v21 )
        {
          if ( *v20 == 94 )
            *v21++ = 94;
          ++i;
          *v21 = *v20++;
        }
        *v21 = 0;
      }
      else
      {
        v8 = 2147483646;
        if ( v6 - 1 > 0x7FFFFFFE )
        {
          v11 = -2147024809;
LABEL_22:
          wil::details::in1diag3::Return_Hr(
            retaddr,
            (void *)0x139,
            (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
            (const char *)v11,
            Buffer[0]);
          return v11;
        }
        v9 = v6;
        v10 = v7;
        do
        {
          if ( !*v10 )
            break;
          ++v10;
          --v9;
        }
        while ( v9 );
        v11 = -2147024809;
        if ( !v9 )
          goto LABEL_22;
        v12 = v6 - v9;
        v13 = (wchar_t *)Buffer;
        v11 = 0;
        v14 = &v7[v12];
        v15 = v6 - v12;
        if ( v15 )
        {
          while ( v8 && *v13 )
          {
            *v14++ = *v13++;
            --v8;
            if ( !--v15 )
              goto LABEL_20;
          }
        }
        else
        {
LABEL_20:
          --v14;
          v11 = -2147024774;
        }
        *v14 = 0;
        if ( (v11 & 0x80000000) != 0 )
          goto LABEL_22;
      }
      *((_QWORD *)this + 65) += v4;
      return 0;
    }
    v11 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8007000ELL,
      Buffer[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8007000ELL,
      Buffer[0]);
    return v11;
  }
}

```

## disassembly

```asm
0x180018be0  push    r14
0x180018be2  sub     rsp, 60h
0x180018be6  mov     rax, cs:__security_cookie
0x180018bed  xor     rax, rsp
0x180018bf0  mov     [rsp+68h+var_20], rax
0x180018bf5  mov     rax, rdx
0x180018bf8  mov     r14, rcx
0x180018bfb  mov     rcx, rax; Value
0x180018bfe  lea     rdx, [rsp+68h+Buffer]; Buffer
0x180018c03  mov     r9d, 10h; Radix
0x180018c09  mov     r8d, 11h; BufferCount
0x180018c0f  call    cs:__imp__ui64tow_s
0x180018c15  test    eax, eax
0x180018c17  jnz     loc_180018DE5
0x180018c1d  mov     [rsp+68h+arg_10], rbx
0x180018c25  lea     rax, [rsp+68h+Buffer]
0x180018c2a  mov     [rsp+68h+arg_18], rbp
0x180018c32  xor     ebx, ebx
0x180018c34  xor     ebp, ebp
0x180018c36  mov     [rsp+68h+var_10], rsi
0x180018c3b  nop     dword ptr [rax+rax+00h]
0x180018c40  movzx   ecx, word ptr [rax]
0x180018c43  test    cx, cx
0x180018c46  jz      short loc_180018C68
0x180018c48  inc     rbx
0x180018c4b  cmp     rbx, 7FFFFFFFh
0x180018c52  jnb     loc_180018D85
0x180018c58  cmp     cx, 5Eh ; '^'
0x180018c5c  jz      loc_180018E0B
0x180018c62  add     rax, 2
0x180018c66  jmp     short loc_180018C40
0x180018c68  mov     rax, [r14+210h]
0x180018c6f  mov     [rsp+68h+var_18], rdi
0x180018c74  mov     rdi, [r14+208h]
0x180018c7b  inc     rdi
0x180018c7e  add     rdi, rbp
0x180018c81  add     rdi, rbx
0x180018c84  cmp     rdi, rax
0x180018c87  ja      loc_180018E13
0x180018c8d  mov     r8, [r14+218h]
0x180018c94  mov     rdi, rax
0x180018c97  test    rbp, rbp
0x180018c9a  jnz     loc_180018E69
0x180018ca0  lea     rax, [rdi-1]
0x180018ca4  mov     ecx, 7FFFFFFEh
0x180018ca9  cmp     rax, rcx
0x180018cac  ja      loc_180018E5F
0x180018cb2  mov     rdx, rdi
0x180018cb5  mov     rax, r8
0x180018cb8  cmp     word ptr [rax], 0
0x180018cbc  jz      short loc_180018CC8
0x180018cbe  add     rax, 2
0x180018cc2  sub     rdx, 1
0x180018cc6  jnz     short loc_180018CB8
0x180018cc8  xor     eax, eax
0x180018cca  mov     esi, 80070057h
0x180018ccf  test    rdx, rdx
0x180018cd2  cmovnz  esi, eax
0x180018cd5  jz      short loc_180018D31
0x180018cd7  mov     rax, rdi
0x180018cda  sub     rax, rdx
0x180018cdd  test    rdx, rdx
0x180018ce0  jz      short loc_180018D31
0x180018ce2  lea     rdx, [rsp+68h+Buffer]
0x180018ce7  mov     esi, 0
0x180018cec  lea     r8, [r8+rax*2]
0x180018cf0  sub     rdi, rax
0x180018cf3  jz      short loc_180018D17
0x180018cf5  test    rcx, rcx
0x180018cf8  jz      short loc_180018D27
0x180018cfa  movzx   eax, word ptr [rdx]
0x180018cfd  test    ax, ax
0x180018d00  jz      short loc_180018D22
0x180018d02  mov     [r8], ax
0x180018d06  add     rdx, 2
0x180018d0a  add     r8, 2
0x180018d0e  dec     rcx
0x180018d11  sub     rdi, 1
0x180018d15  jnz     short loc_180018CF5
0x180018d17  sub     r8, 2
0x180018d1b  mov     esi, 8007007Ah
0x180018d20  jmp     short loc_180018D27
0x180018d22  test    rdi, rdi
0x180018d25  jz      short loc_180018D17
0x180018d27  xor     eax, eax
0x180018d29  mov     [r8], ax
0x180018d2d  test    esi, esi
0x180018d2f  jns     short loc_180018D7A
0x180018d31  mov     rcx, [rsp+68h]; this
0x180018d36  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018d3d  mov     r9d, esi; char *
0x180018d40  mov     edx, 139h; void *
0x180018d45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018d4a  mov     rdi, [rsp+68h+var_18]
0x180018d4f  mov     rbp, [rsp+68h+arg_18]
0x180018d57  mov     eax, esi
0x180018d59  mov     rsi, [rsp+68h+var_10]
0x180018d5e  mov     rbx, [rsp+68h+arg_10]
0x180018d66  mov     rcx, [rsp+68h+var_20]
0x180018d6b  xor     rcx, rsp; StackCookie
0x180018d6e  call    __security_check_cookie
0x180018d73  add     rsp, 60h
0x180018d77  pop     r14
0x180018d79  retn
0x180018d7a  add     [r14+208h], rbx
0x180018d81  xor     esi, esi
0x180018d83  jmp     short loc_180018D4A
0x180018d85  mov     rcx, [rsp+68h]; this
0x180018d8a  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018d91  mov     esi, 80070057h
0x180018d96  mov     edx, 135h; void *
0x180018d9b  mov     r9d, esi; char *
0x180018d9e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018da3  jmp     short loc_180018D4F
0x180018da5  mov     r8, [r14+210h]
0x180018dac  mov     rcx, rsi; void *
0x180018daf  mov     rdx, [r14+218h]; Src
0x180018db6  add     r8, r8; Size
0x180018db9  call    memcpy_0
0x180018dbe  mov     rcx, [r14]
0x180018dc1  mov     [r14], rsi
0x180018dc4  test    rcx, rcx
0x180018dc7  jz      short loc_180018DCF
0x180018dc9  call    cs:__imp_SRCache_Free
0x180018dcf  mov     r8, [r14]
0x180018dd2  mov     [r14+218h], r8
0x180018dd9  mov     [r14+210h], rdi
0x180018de0  jmp     loc_180018C97
0x180018de5  mov     rcx, [rsp+68h]; this
0x180018dea  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018df1  mov     r9d, 8000FFFFh; char *
0x180018df7  mov     edx, 166h; void *
0x180018dfc  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e01  mov     eax, 8000FFFFh
0x180018e06  jmp     loc_180018D66
0x180018e0b  inc     rbp
0x180018e0e  jmp     loc_180018C62
0x180018e13  mov     ecx, edi
0x180018e15  call    cs:__imp_SRCache_AllocStringBuffer
0x180018e1b  mov     rsi, rax
0x180018e1e  test    rax, rax
0x180018e21  jnz     short loc_180018DA5
0x180018e23  mov     rcx, [rsp+68h]; this
0x180018e28  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018e2f  mov     esi, 8007000Eh
0x180018e34  mov     edx, 193h; void *
0x180018e39  mov     r9d, esi; char *
0x180018e3c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e41  mov     rcx, [rsp+68h]; this
0x180018e46  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180018e4d  mov     r9d, esi; char *
0x180018e50  mov     edx, 136h; void *
0x180018e55  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180018e5a  jmp     loc_180018D4A
0x180018e5f  mov     esi, 80070057h
0x180018e64  jmp     loc_180018D31
0x180018e69  mov     rax, [r14+208h]
0x180018e70  lea     rdx, [rsp+68h+Buffer]
0x180018e75  lea     rcx, [r8+rax*2]
0x180018e79  xor     r8d, r8d
0x180018e7c  test    rbx, rbx
0x180018e7f  jz      short loc_180018EA6
0x180018e81  cmp     word ptr [rdx], 5Eh ; '^'
0x180018e85  jnz     short loc_180018E90
0x180018e87  mov     word ptr [rcx], 5Eh ; '^'
0x180018e8c  add     rcx, 2
0x180018e90  movzx   eax, word ptr [rdx]
0x180018e93  inc     r8
0x180018e96  mov     [rcx], ax
0x180018e99  add     rdx, 2
0x180018e9d  add     rcx, 2
0x180018ea1  cmp     r8, rbx
0x180018ea4  jb      short loc_180018E81
0x180018ea6  xor     eax, eax
0x180018ea8  mov     [rcx], ax
0x180018eab  jmp     loc_180018D7A
```
