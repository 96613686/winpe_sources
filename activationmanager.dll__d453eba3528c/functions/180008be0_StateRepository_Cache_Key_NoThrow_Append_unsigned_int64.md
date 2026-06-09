# StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)

- ea: `0x180008be0`
- end: `0x180008eba`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z`
- size: `730`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64)`
- caller_count: `9`
- callee_count: `4`
- tags: ``

## callers

- `0x180006530`
- `0x180007120`
- `0x18002d6c0`
- `0x18002e3cc`
- `0x18002e73c`
- `0x180053ea0`
- `0x180056fe8`
- `0x1800844e4`
- `0x18008e0ec`

## callees

- `0x180008be0`
- `0x18000b5c0`
- `0x18005ae90`
- `0x18005d2b9`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180008c0f`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x180008c0f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180008e1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180008e1f`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008dd3`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180008dd3`

## string_xrefs

- `0x180008d5f`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008d94`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008df4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008e32`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180008e50`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(StateRepository::Cache::Key_NoThrow *this, __int64 a2)
{
  int *v3; // rax
  unsigned __int64 v4; // rbx
  __int64 v5; // rbp
  unsigned __int64 v6; // rdi
  _WORD *v7; // r8
  __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  _WORD *v10; // rax
  unsigned __int64 v11; // rax
  int v12; // esi
  int *v13; // rdx
  _WORD *v14; // r8
  unsigned __int64 v15; // rdi
  __int64 v17; // rcx
  void *v18; // rax
  void *v19; // rsi
  int *v20; // rdx
  _WORD *v21; // rcx
  unsigned __int64 i; // r8
  int v23[10]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (unsigned int)_o__ui64tow_s(a2, v23, 17, 16) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v23[0]);
    return 2147549183LL;
  }
  else
  {
    v3 = v23;
    v4 = 0;
    v5 = 0;
    while ( *(_WORD *)v3 )
    {
      if ( ++v4 >= 0x7FFFFFFF )
      {
        v12 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x80070057LL,
          v23[0]);
        return (unsigned int)v12;
      }
      if ( *(_WORD *)v3 == 94 )
        ++v5;
      v3 = (int *)((char *)v3 + 2);
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
      if ( !v5 )
      {
        v8 = 2147483646;
        if ( v6 - 1 > 0x7FFFFFFE )
        {
          v12 = -2147024809;
        }
        else
        {
          v9 = v6;
          v10 = v7;
          do
          {
            if ( !*v10 )
            {
              v11 = v6 - v9;
              v12 = 0;
              goto LABEL_15;
            }
            ++v10;
            --v9;
          }
          while ( v9 );
          v11 = 0;
          v12 = -2147024809;
LABEL_15:
          if ( v12 >= 0 )
          {
            v13 = v23;
            v12 = 0;
            v14 = &v7[v11];
            v15 = v6 - v11;
            if ( v15 )
            {
              while ( v8 && *(_WORD *)v13 )
              {
                *v14 = *(_WORD *)v13;
                v13 = (int *)((char *)v13 + 2);
                ++v14;
                --v8;
                if ( !--v15 )
                  goto LABEL_20;
              }
            }
            else
            {
LABEL_20:
              --v14;
              v12 = -2147024774;
            }
            *v14 = 0;
            if ( v12 >= 0 )
              goto LABEL_22;
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)(unsigned int)v12,
          v23[0]);
        return (unsigned int)v12;
      }
      v20 = v23;
      v21 = &v7[*((_QWORD *)this + 65)];
      for ( i = 0; i < v4; ++v21 )
      {
        if ( *(_WORD *)v20 == 94 )
          *v21++ = 94;
        ++i;
        *v21 = *(_WORD *)v20;
        v20 = (int *)((char *)v20 + 2);
      }
      *v21 = 0;
LABEL_22:
      *((_QWORD *)this + 65) += v4;
      return 0;
    }
    v12 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8007000ELL,
      v23[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8007000ELL,
      v23[0]);
    return (unsigned int)v12;
  }
}

```

## disassembly

```asm
0x180008be0  push    r14
0x180008be2  sub     rsp, 60h
0x180008be6  mov     rax, cs:__security_cookie
0x180008bed  xor     rax, rsp
0x180008bf0  mov     [rsp+68h+var_20], rax
0x180008bf5  mov     rax, rdx
0x180008bf8  mov     r14, rcx
0x180008bfb  mov     rcx, rax
0x180008bfe  lea     rdx, [rsp+68h+var_48]
0x180008c03  mov     r9d, 10h
0x180008c09  mov     r8d, 11h
0x180008c0f  call    cs:__imp__o__ui64tow_s
0x180008c15  test    eax, eax
0x180008c17  jnz     loc_180008DEF
0x180008c1d  mov     [rsp+68h+arg_10], rbx
0x180008c25  lea     rax, [rsp+68h+var_48]
0x180008c2a  mov     [rsp+68h+arg_18], rbp
0x180008c32  xor     ebx, ebx
0x180008c34  xor     ebp, ebp
0x180008c36  mov     [rsp+68h+var_10], rsi
0x180008c3b  nop     dword ptr [rax+rax+00h]
0x180008c40  movzx   ecx, word ptr [rax]
0x180008c43  test    cx, cx
0x180008c46  jz      short loc_180008C68
0x180008c48  inc     rbx
0x180008c4b  cmp     rbx, 7FFFFFFFh
0x180008c52  jnb     loc_180008D8F
0x180008c58  cmp     cx, 5Eh ; '^'
0x180008c5c  jz      loc_180008E15
0x180008c62  add     rax, 2
0x180008c66  jmp     short loc_180008C40
0x180008c68  mov     rax, [r14+210h]
0x180008c6f  mov     [rsp+68h+var_18], rdi
0x180008c74  mov     rdi, [r14+208h]
0x180008c7b  inc     rdi
0x180008c7e  add     rdi, rbp
0x180008c81  add     rdi, rbx
0x180008c84  cmp     rdi, rax
0x180008c87  ja      loc_180008E1D
0x180008c8d  mov     r8, [r14+218h]
0x180008c94  mov     rdi, rax
0x180008c97  test    rbp, rbp
0x180008c9a  jnz     loc_180008E73
0x180008ca0  lea     rax, [rdi-1]
0x180008ca4  mov     ecx, 7FFFFFFEh
0x180008ca9  cmp     rax, rcx
0x180008cac  ja      loc_180008E69
0x180008cb2  mov     rdx, rdi
0x180008cb5  mov     rax, r8
0x180008cb8  cmp     word ptr [rax], 0
0x180008cbc  jnz     loc_180008D75
0x180008cc2  mov     rax, rdi
0x180008cc5  sub     rax, rdx
0x180008cc8  xor     esi, esi
0x180008cca  test    esi, esi
0x180008ccc  js      loc_180008D5A
0x180008cd2  lea     rdx, [rsp+68h+var_48]
0x180008cd7  mov     esi, 0
0x180008cdc  lea     r8, [r8+rax*2]
0x180008ce0  sub     rdi, rax
0x180008ce3  jz      short loc_180008D07
0x180008ce5  test    rcx, rcx
0x180008ce8  jz      short loc_180008D17
0x180008cea  movzx   eax, word ptr [rdx]
0x180008ced  test    ax, ax
0x180008cf0  jz      short loc_180008D12
0x180008cf2  mov     [r8], ax
0x180008cf6  add     rdx, 2
0x180008cfa  add     r8, 2
0x180008cfe  dec     rcx
0x180008d01  sub     rdi, 1
0x180008d05  jnz     short loc_180008CE5
0x180008d07  sub     r8, 2
0x180008d0b  mov     esi, 8007007Ah
0x180008d10  jmp     short loc_180008D17
0x180008d12  test    rdi, rdi
0x180008d15  jz      short loc_180008D07
0x180008d17  xor     eax, eax
0x180008d19  mov     [r8], ax
0x180008d1d  test    esi, esi
0x180008d1f  js      short loc_180008D5A
0x180008d21  add     [r14+208h], rbx
0x180008d28  xor     esi, esi
0x180008d2a  mov     rdi, [rsp+68h+var_18]
0x180008d2f  mov     rbp, [rsp+68h+arg_18]
0x180008d37  mov     eax, esi
0x180008d39  mov     rsi, [rsp+68h+var_10]
0x180008d3e  mov     rbx, [rsp+68h+arg_10]
0x180008d46  mov     rcx, [rsp+68h+var_20]
0x180008d4b  xor     rcx, rsp; StackCookie
0x180008d4e  call    __security_check_cookie
0x180008d53  add     rsp, 60h
0x180008d57  pop     r14
0x180008d59  retn
0x180008d5a  mov     rcx, [rsp+68h]; this
0x180008d5f  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008d66  mov     r9d, esi; char *
0x180008d69  mov     edx, 139h; void *
0x180008d6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008d73  jmp     short loc_180008D2A
0x180008d75  add     rax, 2
0x180008d79  sub     rdx, 1
0x180008d7d  jnz     loc_180008CB8
0x180008d83  xor     eax, eax
0x180008d85  mov     esi, 80070057h
0x180008d8a  jmp     loc_180008CCA
0x180008d8f  mov     rcx, [rsp+68h]; this
0x180008d94  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008d9b  mov     esi, 80070057h
0x180008da0  mov     edx, 135h; void *
0x180008da5  mov     r9d, esi; char *
0x180008da8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008dad  jmp     short loc_180008D2F
0x180008daf  mov     r8, [r14+210h]
0x180008db6  mov     rcx, rsi; void *
0x180008db9  mov     rdx, [r14+218h]; Src
0x180008dc0  add     r8, r8; Size
0x180008dc3  call    memcpy_0
0x180008dc8  mov     rcx, [r14]
0x180008dcb  mov     [r14], rsi
0x180008dce  test    rcx, rcx
0x180008dd1  jz      short loc_180008DD9
0x180008dd3  call    cs:__imp_SRCache_Free
0x180008dd9  mov     r8, [r14]
0x180008ddc  mov     [r14+218h], r8
0x180008de3  mov     [r14+210h], rdi
0x180008dea  jmp     loc_180008C97
0x180008def  mov     rcx, [rsp+68h]; this
0x180008df4  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008dfb  mov     r9d, 8000FFFFh; char *
0x180008e01  mov     edx, 166h; void *
0x180008e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e0b  mov     eax, 8000FFFFh
0x180008e10  jmp     loc_180008D46
0x180008e15  inc     rbp
0x180008e18  jmp     loc_180008C62
0x180008e1d  mov     ecx, edi
0x180008e1f  call    cs:__imp_SRCache_AllocStringBuffer
0x180008e25  mov     rsi, rax
0x180008e28  test    rax, rax
0x180008e2b  jnz     short loc_180008DAF
0x180008e2d  mov     rcx, [rsp+68h]; this
0x180008e32  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008e39  mov     esi, 8007000Eh
0x180008e3e  mov     edx, 193h; void *
0x180008e43  mov     r9d, esi; char *
0x180008e46  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e4b  mov     rcx, [rsp+68h]; this
0x180008e50  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x180008e57  mov     r9d, esi; char *
0x180008e5a  mov     edx, 136h; void *
0x180008e5f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180008e64  jmp     loc_180008D2A
0x180008e69  mov     esi, 80070057h
0x180008e6e  jmp     loc_180008D5A
0x180008e73  mov     rax, [r14+208h]
0x180008e7a  lea     rdx, [rsp+68h+var_48]
0x180008e7f  lea     rcx, [r8+rax*2]
0x180008e83  xor     r8d, r8d
0x180008e86  test    rbx, rbx
0x180008e89  jz      short loc_180008EB0
0x180008e8b  cmp     word ptr [rdx], 5Eh ; '^'
0x180008e8f  jnz     short loc_180008E9A
0x180008e91  mov     word ptr [rcx], 5Eh ; '^'
0x180008e96  add     rcx, 2
0x180008e9a  movzx   eax, word ptr [rdx]
0x180008e9d  inc     r8
0x180008ea0  mov     [rcx], ax
0x180008ea3  add     rdx, 2
0x180008ea7  add     rcx, 2
0x180008eab  cmp     r8, rbx
0x180008eae  jb      short loc_180008E8B
0x180008eb0  xor     eax, eax
0x180008eb2  mov     [rcx], ax
0x180008eb5  jmp     loc_180008D21
```
