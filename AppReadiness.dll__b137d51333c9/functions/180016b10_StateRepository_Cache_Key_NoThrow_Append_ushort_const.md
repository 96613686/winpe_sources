# StateRepository::Cache::Key_NoThrow::Append(ushort const *)

- ea: `0x180016b10`
- end: `0x180016d6c`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `604`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180016814`
- `0x18002ff94`
- `0x1800302f4`

## callees

- `0x180016b10`
- `0x180030914`
- `0x180075b58`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180016cc6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x180016cc6`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016d16`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180016d16`

## string_xrefs

- `0x180016c36`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180016ca4`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180016cd9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180016cf5`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        const unsigned __int16 *a2,
        __int64 a3,
        __int64 a4)
{
  const unsigned __int16 *v4; // rbx
  unsigned __int64 v6; // rsi
  const unsigned __int16 *v7; // rax
  __int64 v8; // r14
  __int64 v9; // rdx
  unsigned __int64 v10; // rdi
  __int64 v11; // r8
  __int64 v12; // rcx
  unsigned __int64 v13; // rdx
  _WORD *v14; // rax
  unsigned int v15; // ebp
  unsigned __int64 v16; // rax
  _WORD *v17; // rdx
  unsigned __int64 i; // rdi
  _WORD *v19; // rcx
  __int64 v21; // rcx
  void *v22; // rax
  void *v23; // rbp
  unsigned __int64 v24; // rdx
  _WORD *j; // rcx
  int v26; // [rsp+20h] [rbp-38h]
  int v27; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v4 = a2;
  if ( !a2 )
    return 0;
  v6 = 0;
  v7 = a2;
  v8 = 0;
  while ( 1 )
  {
    v9 = *v7;
    if ( !(_WORD)v9 )
      break;
    if ( ++v6 >= 0x7FFFFFFF )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x80070057LL,
        v26);
      return 2147942487LL;
    }
    if ( (_WORD)v9 == 94 )
      ++v8;
    ++v7;
  }
  v10 = v6 + v8 + *((_QWORD *)this + 65) + 1LL;
  if ( v10 <= *((_QWORD *)this + 66) )
  {
    v10 = *((_QWORD *)this + 66);
    goto LABEL_10;
  }
  v22 = (void *)SRCache_AllocStringBuffer((unsigned int)v10, v9, a3, a4);
  v23 = v22;
  if ( v22 )
  {
    memcpy_0(v22, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
    v21 = *(_QWORD *)this;
    *(_QWORD *)this = v23;
    if ( v21 )
      SRCache_Free();
    *((_QWORD *)this + 67) = *(_QWORD *)this;
    *((_QWORD *)this + 66) = v10;
LABEL_10:
    v11 = *((_QWORD *)this + 67);
    if ( !v8 )
    {
      v12 = 2147483646;
      if ( v10 - 1 > 0x7FFFFFFE )
      {
        v15 = -2147024809;
      }
      else
      {
        v13 = v10;
        v14 = (_WORD *)*((_QWORD *)this + 67);
        do
        {
          if ( !*v14 )
            break;
          ++v14;
          --v13;
        }
        while ( v13 );
        v15 = -2147024809;
        if ( v13 )
        {
          v16 = v10 - v13;
          v17 = (_WORD *)(v11 + 2 * (v10 - v13));
          for ( i = v10 - v16; i; --i )
          {
            if ( !v12 )
              break;
            if ( !*v4 )
              break;
            *v17++ = *v4++;
            --v12;
          }
          v19 = v17 - 1;
          v15 = -2147024774;
          if ( i )
          {
            v19 = v17;
            v15 = 0;
          }
          *v19 = 0;
          if ( i )
          {
LABEL_23:
            *((_QWORD *)this + 65) += v6;
            return 0;
          }
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)v15,
        v26);
      return v15;
    }
    v24 = 0;
    for ( j = (_WORD *)(v11 + 2LL * *((_QWORD *)this + 65)); v24 < v6; ++j )
    {
      if ( *v4 == 94 )
        *j++ = 94;
      ++v24;
      *j = *v4++;
    }
    *j = 0;
    goto LABEL_23;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x193,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v26);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x136,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v27);
  return 2147942414LL;
}

```

## disassembly

```asm
0x180016b10  push    rbx
0x180016b12  push    rbp
0x180016b13  push    rsi
0x180016b14  push    rdi
0x180016b15  push    r14
0x180016b17  push    r15
0x180016b19  sub     rsp, 28h
0x180016b1d  mov     rbx, rdx
0x180016b20  mov     r15, rcx
0x180016b23  test    rdx, rdx
0x180016b26  jz      loc_180016C22
0x180016b2c  xor     esi, esi
0x180016b2e  mov     rax, rdx
0x180016b31  xor     r14d, r14d
0x180016b34  movzx   edx, word ptr [rax]
0x180016b37  test    dx, dx
0x180016b3a  jz      short loc_180016B5C
0x180016b3c  inc     rsi
0x180016b3f  cmp     rsi, 7FFFFFFFh
0x180016b46  jnb     loc_180016C9F
0x180016b4c  cmp     dx, 5Eh ; '^'
0x180016b50  jz      loc_180016C97
0x180016b56  add     rax, 2
0x180016b5a  jmp     short loc_180016B34
0x180016b5c  mov     rdi, [rcx+208h]
0x180016b63  mov     rax, [rcx+210h]
0x180016b6a  inc     rdi
0x180016b6d  add     rdi, r14
0x180016b70  add     rdi, rsi
0x180016b73  cmp     rdi, rax
0x180016b76  ja      loc_180016CC4
0x180016b7c  mov     rdi, rax
0x180016b7f  mov     r8, [r15+218h]
0x180016b86  test    r14, r14
0x180016b89  jnz     loc_180016D2B
0x180016b8f  lea     rax, [rdi-1]
0x180016b93  mov     ecx, 7FFFFFFEh
0x180016b98  cmp     rax, rcx
0x180016b9b  ja      loc_180016D21
0x180016ba1  mov     rdx, rdi
0x180016ba4  mov     rax, r8
0x180016ba7  cmp     word ptr [rax], 0
0x180016bab  jz      short loc_180016BB7
0x180016bad  add     rax, 2
0x180016bb1  sub     rdx, 1
0x180016bb5  jnz     short loc_180016BA7
0x180016bb7  xor     eax, eax
0x180016bb9  mov     ebp, 80070057h
0x180016bbe  test    rdx, rdx
0x180016bc1  cmovnz  ebp, eax
0x180016bc4  jz      short loc_180016C31
0x180016bc6  mov     rax, rdi
0x180016bc9  sub     rax, rdx
0x180016bcc  test    rdx, rdx
0x180016bcf  jz      short loc_180016C31
0x180016bd1  lea     rdx, [r8+rax*2]
0x180016bd5  sub     rdi, rax
0x180016bd8  jz      short loc_180016C01
0x180016bda  nop     word ptr [rax+rax+00h]
0x180016be0  test    rcx, rcx
0x180016be3  jz      short loc_180016C01
0x180016be5  movzx   eax, word ptr [rbx]
0x180016be8  test    ax, ax
0x180016beb  jz      short loc_180016C01
0x180016bed  mov     [rdx], ax
0x180016bf0  add     rbx, 2
0x180016bf4  add     rdx, 2
0x180016bf8  dec     rcx
0x180016bfb  sub     rdi, 1
0x180016bff  jnz     short loc_180016BE0
0x180016c01  xor     eax, eax
0x180016c03  lea     rcx, [rdx-2]
0x180016c07  test    rdi, rdi
0x180016c0a  mov     ebp, 8007007Ah
0x180016c0f  cmovnz  rcx, rdx
0x180016c13  cmovnz  ebp, eax
0x180016c16  mov     [rcx], ax
0x180016c19  jz      short loc_180016C31
0x180016c1b  add     [r15+208h], rsi
0x180016c22  xor     eax, eax
0x180016c24  add     rsp, 28h
0x180016c28  pop     r15
0x180016c2a  pop     r14
0x180016c2c  pop     rdi
0x180016c2d  pop     rsi
0x180016c2e  pop     rbp
0x180016c2f  pop     rbx
0x180016c30  retn
0x180016c31  mov     rcx, [rsp+58h]; this
0x180016c36  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016c3d  mov     r9d, ebp; char *
0x180016c40  mov     edx, 139h; void *
0x180016c45  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c4a  mov     eax, ebp
0x180016c4c  add     rsp, 28h
0x180016c50  pop     r15
0x180016c52  pop     r14
0x180016c54  pop     rdi
0x180016c55  pop     rsi
0x180016c56  pop     rbp
0x180016c57  pop     rbx
0x180016c58  retn
0x180016c59  mov     r8, [r15+210h]
0x180016c60  mov     rcx, rbp; void *
0x180016c63  mov     rdx, [r15+218h]; Src
0x180016c6a  add     r8, r8; Size
0x180016c6d  call    memcpy_0
0x180016c72  mov     rcx, [r15]
0x180016c75  mov     [r15], rbp
0x180016c78  test    rcx, rcx
0x180016c7b  jnz     loc_180016D16
0x180016c81  mov     rax, [r15]
0x180016c84  mov     [r15+218h], rax
0x180016c8b  mov     [r15+210h], rdi
0x180016c92  jmp     loc_180016B7F
0x180016c97  inc     r14
0x180016c9a  jmp     loc_180016B56
0x180016c9f  mov     rcx, [rsp+58h]; this
0x180016ca4  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016cab  mov     ebp, 80070057h
0x180016cb0  mov     edx, 135h; void *
0x180016cb5  mov     r9d, ebp; char *
0x180016cb8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cbd  mov     eax, ebp
0x180016cbf  jmp     loc_180016C24
0x180016cc4  mov     ecx, edi
0x180016cc6  call    cs:__imp_SRCache_AllocStringBuffer
0x180016ccc  mov     rbp, rax
0x180016ccf  test    rax, rax
0x180016cd2  jnz     short loc_180016C59
0x180016cd4  mov     rcx, [rsp+58h]; this
0x180016cd9  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016ce0  mov     r9d, 8007000Eh; char *
0x180016ce6  mov     edx, 193h; void *
0x180016ceb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016cf0  mov     rcx, [rsp+58h]; this
0x180016cf5  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180016cfc  mov     r9d, 8007000Eh; char *
0x180016d02  mov     edx, 136h; void *
0x180016d07  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016d0c  mov     eax, 8007000Eh
0x180016d11  jmp     loc_180016C24
0x180016d16  call    cs:__imp_SRCache_Free
0x180016d1c  jmp     loc_180016C81
0x180016d21  mov     ebp, 80070057h
0x180016d26  jmp     loc_180016C31
0x180016d2b  mov     rax, [r15+208h]
0x180016d32  xor     edx, edx
0x180016d34  lea     rcx, [r8+rax*2]
0x180016d38  test    rsi, rsi
0x180016d3b  jz      short loc_180016D62
0x180016d3d  cmp     word ptr [rbx], 5Eh ; '^'
0x180016d41  jnz     short loc_180016D4C
0x180016d43  mov     word ptr [rcx], 5Eh ; '^'
0x180016d48  add     rcx, 2
0x180016d4c  movzx   eax, word ptr [rbx]
0x180016d4f  inc     rdx
0x180016d52  mov     [rcx], ax
0x180016d55  add     rbx, 2
0x180016d59  add     rcx, 2
0x180016d5d  cmp     rdx, rsi
0x180016d60  jb      short loc_180016D3D
0x180016d62  xor     eax, eax
0x180016d64  mov     [rcx], ax
0x180016d67  jmp     loc_180016C1B
```
