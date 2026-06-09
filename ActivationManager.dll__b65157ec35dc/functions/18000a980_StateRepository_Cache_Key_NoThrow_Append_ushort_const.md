# StateRepository::Cache::Key_NoThrow::Append(ushort const *)

- ea: `0x18000a980`
- end: `0x18000abe4`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJPEBG@Z`
- size: `612`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `3`
- tags: ``

## callers

- `0x18002d9f8`
- `0x18002e73c`
- `0x180037dd0`
- `0x180056fe8`

## callees

- `0x18000a980`
- `0x18000b5c0`
- `0x18005d2b9`

## import_xrefs

- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000ab49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x18000ab49`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ab23`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x18000ab23`

## string_xrefs

- `0x18000aa95`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000aad7`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000ab5c`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x18000ab78`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(
        StateRepository::Cache::Key_NoThrow *this,
        const unsigned __int16 *a2)
{
  const unsigned __int16 *v2; // rsi
  unsigned __int64 v4; // rbx
  const unsigned __int16 *v5; // rax
  __int64 v6; // r14
  unsigned __int64 v7; // rdi
  __int64 v8; // r8
  __int64 v9; // rcx
  unsigned __int64 v10; // rdx
  _WORD *v11; // rax
  unsigned __int64 v12; // rax
  int v13; // ebp
  _WORD *v14; // rdx
  unsigned __int64 v15; // rdi
  __int64 v17; // rcx
  void *v18; // rax
  void *v19; // rbp
  unsigned __int64 v20; // rdx
  _WORD *i; // rcx
  int v22; // [rsp+20h] [rbp-38h]
  int v23; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  v2 = a2;
  if ( !a2 )
    return 0;
  v4 = 0;
  v5 = a2;
  v6 = 0;
  while ( *v5 )
  {
    if ( ++v4 >= 0x7FFFFFFF )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x135,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)0x80070057LL,
        v22);
      return 2147942487LL;
    }
    if ( *v5 == 94 )
      ++v6;
    ++v5;
  }
  v7 = v4 + v6 + *((_QWORD *)this + 65) + 1LL;
  if ( v7 <= *((_QWORD *)this + 66) )
  {
    v7 = *((_QWORD *)this + 66);
    goto LABEL_10;
  }
  v18 = (void *)SRCache_AllocStringBuffer((unsigned int)v7);
  v19 = v18;
  if ( v18 )
  {
    memcpy_0(v18, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
    v17 = *(_QWORD *)this;
    *(_QWORD *)this = v19;
    if ( v17 )
      SRCache_Free(v17);
    *((_QWORD *)this + 67) = *(_QWORD *)this;
    *((_QWORD *)this + 66) = v7;
LABEL_10:
    v8 = *((_QWORD *)this + 67);
    if ( !v6 )
    {
      v9 = 2147483646;
      if ( v7 - 1 > 0x7FFFFFFE )
      {
        v13 = -2147024809;
      }
      else
      {
        v10 = v7;
        v11 = (_WORD *)*((_QWORD *)this + 67);
        do
        {
          if ( !*v11 )
          {
            v12 = v7 - v10;
            v13 = 0;
            goto LABEL_15;
          }
          ++v11;
          --v10;
        }
        while ( v10 );
        v12 = 0;
        v13 = -2147024809;
LABEL_15:
        if ( v13 >= 0 )
        {
          v14 = (_WORD *)(v8 + 2 * v12);
          v13 = 0;
          v15 = v7 - v12;
          if ( v15 )
          {
            while ( v9 && *v2 )
            {
              *v14++ = *v2++;
              --v9;
              if ( !--v15 )
                goto LABEL_20;
            }
          }
          else
          {
LABEL_20:
            --v14;
            v13 = -2147024774;
          }
          *v14 = 0;
          if ( v13 >= 0 )
            goto LABEL_22;
        }
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x139,
        (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
        (const char *)(unsigned int)v13,
        v22);
      return (unsigned int)v13;
    }
    v20 = 0;
    for ( i = (_WORD *)(v8 + 2LL * *((_QWORD *)this + 65)); v20 < v4; ++i )
    {
      if ( *v2 == 94 )
        *i++ = 94;
      ++v20;
      *i = *v2++;
    }
    *i = 0;
LABEL_22:
    *((_QWORD *)this + 65) += v4;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x193,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v22);
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x136,
    (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
    (const char *)0x8007000ELL,
    v23);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000a980  push    rbx
0x18000a982  push    rbp
0x18000a983  push    rsi
0x18000a984  push    rdi
0x18000a985  push    r14
0x18000a987  push    r15
0x18000a989  sub     rsp, 28h
0x18000a98d  mov     rsi, rdx
0x18000a990  mov     r15, rcx
0x18000a993  test    rdx, rdx
0x18000a996  jz      loc_18000AA81
0x18000a99c  xor     ebx, ebx
0x18000a99e  mov     rax, rdx
0x18000a9a1  xor     r14d, r14d
0x18000a9a4  movzx   r8d, word ptr [rax]
0x18000a9a8  test    r8w, r8w
0x18000a9ac  jz      short loc_18000A9CF
0x18000a9ae  inc     rbx
0x18000a9b1  cmp     rbx, 7FFFFFFFh
0x18000a9b8  jnb     loc_18000AAD2
0x18000a9be  cmp     r8w, 5Eh ; '^'
0x18000a9c3  jz      loc_18000AB3F
0x18000a9c9  add     rax, 2
0x18000a9cd  jmp     short loc_18000A9A4
0x18000a9cf  mov     rdi, [rcx+208h]
0x18000a9d6  mov     rax, [rcx+210h]
0x18000a9dd  inc     rdi
0x18000a9e0  add     rdi, r14
0x18000a9e3  add     rdi, rbx
0x18000a9e6  cmp     rdi, rax
0x18000a9e9  ja      loc_18000AB47
0x18000a9ef  mov     rdi, rax
0x18000a9f2  mov     r8, [r15+218h]
0x18000a9f9  test    r14, r14
0x18000a9fc  jnz     loc_18000ABA3
0x18000aa02  lea     rax, [rdi-1]
0x18000aa06  mov     ecx, 7FFFFFFEh
0x18000aa0b  cmp     rax, rcx
0x18000aa0e  ja      loc_18000AB99
0x18000aa14  mov     rdx, rdi
0x18000aa17  mov     rax, r8
0x18000aa1a  cmp     word ptr [rax], 0
0x18000aa1e  jnz     loc_18000AAB8
0x18000aa24  mov     rax, rdi
0x18000aa27  sub     rax, rdx
0x18000aa2a  xor     ebp, ebp
0x18000aa2c  test    ebp, ebp
0x18000aa2e  js      short loc_18000AA90
0x18000aa30  lea     rdx, [r8+rax*2]
0x18000aa34  mov     ebp, 0
0x18000aa39  sub     rdi, rax
0x18000aa3c  jz      short loc_18000AA61
0x18000aa3e  xchg    ax, ax
0x18000aa40  test    rcx, rcx
0x18000aa43  jz      short loc_18000AA71
0x18000aa45  movzx   eax, word ptr [rsi]
0x18000aa48  test    ax, ax
0x18000aa4b  jz      short loc_18000AA6C
0x18000aa4d  mov     [rdx], ax
0x18000aa50  add     rsi, 2
0x18000aa54  add     rdx, 2
0x18000aa58  dec     rcx
0x18000aa5b  sub     rdi, 1
0x18000aa5f  jnz     short loc_18000AA40
0x18000aa61  sub     rdx, 2
0x18000aa65  mov     ebp, 8007007Ah
0x18000aa6a  jmp     short loc_18000AA71
0x18000aa6c  test    rdi, rdi
0x18000aa6f  jz      short loc_18000AA61
0x18000aa71  xor     eax, eax
0x18000aa73  mov     [rdx], ax
0x18000aa76  test    ebp, ebp
0x18000aa78  js      short loc_18000AA90
0x18000aa7a  add     [r15+208h], rbx
0x18000aa81  xor     eax, eax
0x18000aa83  add     rsp, 28h
0x18000aa87  pop     r15
0x18000aa89  pop     r14
0x18000aa8b  pop     rdi
0x18000aa8c  pop     rsi
0x18000aa8d  pop     rbp
0x18000aa8e  pop     rbx
0x18000aa8f  retn
0x18000aa90  mov     rcx, [rsp+58h]; this
0x18000aa95  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000aa9c  mov     r9d, ebp; char *
0x18000aa9f  mov     edx, 139h; void *
0x18000aaa4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaa9  mov     eax, ebp
0x18000aaab  add     rsp, 28h
0x18000aaaf  pop     r15
0x18000aab1  pop     r14
0x18000aab3  pop     rdi
0x18000aab4  pop     rsi
0x18000aab5  pop     rbp
0x18000aab6  pop     rbx
0x18000aab7  retn
0x18000aab8  add     rax, 2
0x18000aabc  sub     rdx, 1
0x18000aac0  jnz     loc_18000AA1A
0x18000aac6  xor     eax, eax
0x18000aac8  mov     ebp, 80070057h
0x18000aacd  jmp     loc_18000AA2C
0x18000aad2  mov     rcx, [rsp+58h]; this
0x18000aad7  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000aade  mov     ebp, 80070057h
0x18000aae3  mov     edx, 135h; void *
0x18000aae8  mov     r9d, ebp; char *
0x18000aaeb  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000aaf0  mov     eax, ebp
0x18000aaf2  add     rsp, 28h
0x18000aaf6  pop     r15
0x18000aaf8  pop     r14
0x18000aafa  pop     rdi
0x18000aafb  pop     rsi
0x18000aafc  pop     rbp
0x18000aafd  pop     rbx
0x18000aafe  retn
0x18000aaff  mov     r8, [r15+210h]
0x18000ab06  mov     rcx, rbp; void *
0x18000ab09  mov     rdx, [r15+218h]; Src
0x18000ab10  add     r8, r8; Size
0x18000ab13  call    memcpy_0
0x18000ab18  mov     rcx, [r15]
0x18000ab1b  mov     [r15], rbp
0x18000ab1e  test    rcx, rcx
0x18000ab21  jz      short loc_18000AB29
0x18000ab23  call    cs:__imp_SRCache_Free
0x18000ab29  mov     rax, [r15]
0x18000ab2c  mov     [r15+218h], rax
0x18000ab33  mov     [r15+210h], rdi
0x18000ab3a  jmp     loc_18000A9F2
0x18000ab3f  inc     r14
0x18000ab42  jmp     loc_18000A9C9
0x18000ab47  mov     ecx, edi
0x18000ab49  call    cs:__imp_SRCache_AllocStringBuffer
0x18000ab4f  mov     rbp, rax
0x18000ab52  test    rax, rax
0x18000ab55  jnz     short loc_18000AAFF
0x18000ab57  mov     rcx, [rsp+58h]; this
0x18000ab5c  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ab63  mov     r9d, 8007000Eh; char *
0x18000ab69  mov     edx, 193h; void *
0x18000ab6e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab73  mov     rcx, [rsp+58h]; this
0x18000ab78  lea     r8, aOnecorePrivate_0; "onecore\\private\\base\\inc\\appmodel\\"...
0x18000ab7f  mov     r9d, 8007000Eh; char *
0x18000ab85  mov     edx, 136h; void *
0x18000ab8a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000ab8f  mov     eax, 8007000Eh
0x18000ab94  jmp     loc_18000AA83
0x18000ab99  mov     ebp, 80070057h
0x18000ab9e  jmp     loc_18000AA90
0x18000aba3  mov     rax, [r15+208h]
0x18000abaa  xor     edx, edx
0x18000abac  lea     rcx, [r8+rax*2]
0x18000abb0  test    rbx, rbx
0x18000abb3  jz      short loc_18000ABDA
0x18000abb5  cmp     word ptr [rsi], 5Eh ; '^'
0x18000abb9  jnz     short loc_18000ABC4
0x18000abbb  mov     word ptr [rcx], 5Eh ; '^'
0x18000abc0  add     rcx, 2
0x18000abc4  movzx   eax, word ptr [rsi]
0x18000abc7  inc     rdx
0x18000abca  mov     [rcx], ax
0x18000abcd  add     rsi, 2
0x18000abd1  add     rcx, 2
0x18000abd5  cmp     rdx, rbx
0x18000abd8  jb      short loc_18000ABB5
0x18000abda  xor     eax, eax
0x18000abdc  mov     [rcx], ax
0x18000abdf  jmp     loc_18000AA7A
```
