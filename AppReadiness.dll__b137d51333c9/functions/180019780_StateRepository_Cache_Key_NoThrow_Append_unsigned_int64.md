# StateRepository::Cache::Key_NoThrow::Append(unsigned __int64)

- ea: `0x180019780`
- end: `0x180019a5e`
- name: `?Append@Key_NoThrow@Cache@StateRepository@@QEAAJ_K@Z`
- size: `734`
- prototype: `__int64 __fastcall(StateRepository::Cache::Key_NoThrow *__hidden this, unsigned __int64)`
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18002f5dc`
- `0x18002f820`
- `0x18002fb0c`
- `0x18002fd50`
- `0x18002ff94`
- `0x1800305a8`

## callees

- `0x180019780`
- `0x180030914`
- `0x18003e210`
- `0x180075b58`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800197af`
- `api-ms-win-crt-private-l1-1-0!_o__ui64tow_s` at `0x1800197af`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x1800199b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_AllocStringBuffer` at `0x1800199b4`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019a02`
- `ext-ms-onecore-appmodel-staterepository-cache-l1-1-0!SRCache_Free` at `0x180019a02`

## string_xrefs

- `0x18001990d`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180019966`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x180019994`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800199cb`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`
- `0x1800199e9`: `onecore\private\base\inc\appmodel\staterepository\cache\SRCache-Key.hpp`

## pseudocode

```c
__int64 __fastcall StateRepository::Cache::Key_NoThrow::Append(StateRepository::Cache::Key_NoThrow *this, __int64 a2)
{
  __int64 v3; // rdx
  __int64 v4; // r8
  __int64 v5; // r9
  int *v6; // rax
  unsigned __int64 v7; // rdi
  __int64 v8; // rbp
  unsigned __int64 v9; // rbx
  _WORD *v10; // r8
  __int64 v11; // rax
  unsigned __int64 v12; // rdx
  _WORD *v13; // rcx
  unsigned int v14; // esi
  unsigned __int64 v15; // rcx
  int *v16; // rdx
  _WORD *v17; // r8
  unsigned __int64 i; // rbx
  _WORD *v19; // rcx
  __int64 v21; // rcx
  void *v22; // rax
  void *v23; // rsi
  int *v24; // rdx
  _WORD *v25; // rcx
  unsigned __int64 j; // r8
  int v27[10]; // [rsp+20h] [rbp-48h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( (unsigned int)_o__ui64tow_s(a2, v27, 17) )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x166,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8000FFFFLL,
      v27[0]);
    return 2147549183LL;
  }
  else
  {
    v6 = v27;
    v7 = 0;
    v8 = 0;
    while ( *(_WORD *)v6 )
    {
      if ( ++v7 >= 0x7FFFFFFF )
      {
        v14 = -2147024809;
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x135,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)0x80070057LL,
          v27[0]);
        return v14;
      }
      if ( *(_WORD *)v6 == 94 )
        ++v8;
      v6 = (int *)((char *)v6 + 2);
    }
    v9 = v7 + v8 + *((_QWORD *)this + 65) + 1LL;
    if ( v9 <= *((_QWORD *)this + 66) )
    {
      v10 = (_WORD *)*((_QWORD *)this + 67);
      v9 = *((_QWORD *)this + 66);
      goto LABEL_10;
    }
    v22 = (void *)SRCache_AllocStringBuffer((unsigned int)v9, v3, v4, v5);
    v23 = v22;
    if ( v22 )
    {
      memcpy_0(v22, *((const void **)this + 67), 2LL * *((_QWORD *)this + 66));
      v21 = *(_QWORD *)this;
      *(_QWORD *)this = v23;
      if ( v21 )
        SRCache_Free();
      v10 = *(_WORD **)this;
      *((_QWORD *)this + 67) = *(_QWORD *)this;
      *((_QWORD *)this + 66) = v9;
LABEL_10:
      if ( !v8 )
      {
        v11 = 2147483646;
        if ( v9 - 1 > 0x7FFFFFFE )
        {
          v14 = -2147024809;
        }
        else
        {
          v12 = v9;
          v13 = v10;
          do
          {
            if ( !*v13 )
              break;
            ++v13;
            --v12;
          }
          while ( v12 );
          v14 = -2147024809;
          if ( v12 )
          {
            v15 = v9 - v12;
            v16 = v27;
            v17 = &v10[v15];
            for ( i = v9 - v15; i; --i )
            {
              if ( !v11 )
                break;
              if ( !*(_WORD *)v16 )
                break;
              *v17 = *(_WORD *)v16;
              v16 = (int *)((char *)v16 + 2);
              ++v17;
              --v11;
            }
            v19 = v17 - 1;
            v14 = -2147024774;
            if ( i )
            {
              v19 = v17;
              v14 = 0;
            }
            *v19 = 0;
            if ( i )
            {
LABEL_23:
              *((_QWORD *)this + 65) += v7;
              return 0;
            }
          }
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x139,
          (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
          (const char *)v14,
          v27[0]);
        return v14;
      }
      v24 = v27;
      v25 = &v10[*((_QWORD *)this + 65)];
      for ( j = 0; j < v7; ++v25 )
      {
        if ( *(_WORD *)v24 == 94 )
          *v25++ = 94;
        ++j;
        *v25 = *(_WORD *)v24;
        v24 = (int *)((char *)v24 + 2);
      }
      *v25 = 0;
      goto LABEL_23;
    }
    v14 = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x193,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8007000ELL,
      v27[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x136,
      (unsigned int)"onecore\\private\\base\\inc\\appmodel\\staterepository\\cache\\SRCache-Key.hpp",
      (const char *)0x8007000ELL,
      v27[0]);
    return v14;
  }
}

```

## disassembly

```asm
0x180019780  push    r14
0x180019782  sub     rsp, 60h
0x180019786  mov     rax, cs:__security_cookie
0x18001978d  xor     rax, rsp
0x180019790  mov     [rsp+68h+var_20], rax
0x180019795  mov     rax, rdx
0x180019798  mov     r14, rcx
0x18001979b  mov     rcx, rax
0x18001979e  lea     rdx, [rsp+68h+var_48]
0x1800197a3  mov     r9d, 10h
0x1800197a9  mov     r8d, 11h
0x1800197af  call    cs:__imp__o__ui64tow_s
0x1800197b5  test    eax, eax
0x1800197b7  jnz     loc_180019961
0x1800197bd  mov     [rsp+68h+arg_18], rbp
0x1800197c5  lea     rax, [rsp+68h+var_48]
0x1800197ca  mov     [rsp+68h+var_10], rsi
0x1800197cf  mov     [rsp+68h+var_18], rdi
0x1800197d4  xor     edi, edi
0x1800197d6  xor     ebp, ebp
0x1800197d8  movzx   ecx, word ptr [rax]
0x1800197db  test    cx, cx
0x1800197de  jz      short loc_180019800
0x1800197e0  inc     rdi
0x1800197e3  cmp     rdi, 7FFFFFFFh
0x1800197ea  jnb     loc_18001998F
0x1800197f0  cmp     cx, 5Eh ; '^'
0x1800197f4  jz      loc_180019987
0x1800197fa  add     rax, 2
0x1800197fe  jmp     short loc_1800197D8
0x180019800  mov     rax, [r14+210h]
0x180019807  mov     [rsp+68h+arg_10], rbx
0x18001980f  mov     rbx, [r14+208h]
0x180019816  inc     rbx
0x180019819  add     rbx, rbp
0x18001981c  add     rbx, rdi
0x18001981f  cmp     rbx, rax
0x180019822  ja      loc_1800199B2
0x180019828  mov     r8, [r14+218h]
0x18001982f  mov     rbx, rax
0x180019832  test    rbp, rbp
0x180019835  jnz     loc_180019A17
0x18001983b  lea     rcx, [rbx-1]
0x18001983f  mov     eax, 7FFFFFFEh
0x180019844  cmp     rcx, rax
0x180019847  ja      loc_180019A0D
0x18001984d  mov     rdx, rbx
0x180019850  mov     rcx, r8
0x180019853  cmp     word ptr [rcx], 0
0x180019857  jz      short loc_180019863
0x180019859  add     rcx, 2
0x18001985d  sub     rdx, 1
0x180019861  jnz     short loc_180019853
0x180019863  xor     ecx, ecx
0x180019865  mov     esi, 80070057h
0x18001986a  test    rdx, rdx
0x18001986d  cmovnz  esi, ecx
0x180019870  jz      loc_180019908
0x180019876  mov     rcx, rbx
0x180019879  sub     rcx, rdx
0x18001987c  test    rdx, rdx
0x18001987f  jz      loc_180019908
0x180019885  lea     rdx, [rsp+68h+var_48]
0x18001988a  lea     r8, [r8+rcx*2]
0x18001988e  sub     rbx, rcx
0x180019891  jz      short loc_1800198B5
0x180019893  test    rax, rax
0x180019896  jz      short loc_1800198B5
0x180019898  movzx   ecx, word ptr [rdx]
0x18001989b  test    cx, cx
0x18001989e  jz      short loc_1800198B5
0x1800198a0  mov     [r8], cx
0x1800198a4  add     rdx, 2
0x1800198a8  add     r8, 2
0x1800198ac  dec     rax
0x1800198af  sub     rbx, 1
0x1800198b3  jnz     short loc_180019893
0x1800198b5  xor     eax, eax
0x1800198b7  lea     rcx, [r8-2]
0x1800198bb  test    rbx, rbx
0x1800198be  mov     esi, 8007007Ah
0x1800198c3  cmovnz  rcx, r8
0x1800198c7  cmovnz  esi, eax
0x1800198ca  mov     [rcx], ax
0x1800198cd  jz      short loc_180019908
0x1800198cf  add     [r14+208h], rdi
0x1800198d6  xor     esi, esi
0x1800198d8  mov     rbx, [rsp+68h+arg_10]
0x1800198e0  mov     rdi, [rsp+68h+var_18]
0x1800198e5  mov     eax, esi
0x1800198e7  mov     rsi, [rsp+68h+var_10]
0x1800198ec  mov     rbp, [rsp+68h+arg_18]
0x1800198f4  mov     rcx, [rsp+68h+var_20]
0x1800198f9  xor     rcx, rsp; StackCookie
0x1800198fc  call    __security_check_cookie
0x180019901  add     rsp, 60h
0x180019905  pop     r14
0x180019907  retn
0x180019908  mov     rcx, [rsp+68h]; this
0x18001990d  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x180019914  mov     r9d, esi; char *
0x180019917  mov     edx, 139h; void *
0x18001991c  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180019921  jmp     short loc_1800198D8
0x180019923  mov     r8, [r14+210h]
0x18001992a  mov     rcx, rsi; void *
0x18001992d  mov     rdx, [r14+218h]; Src
0x180019934  add     r8, r8; Size
0x180019937  call    memcpy_0
0x18001993c  mov     rcx, [r14]
0x18001993f  mov     [r14], rsi
0x180019942  test    rcx, rcx
0x180019945  jnz     loc_180019A02
0x18001994b  mov     r8, [r14]
0x18001994e  mov     [r14+218h], r8
0x180019955  mov     [r14+210h], rbx
0x18001995c  jmp     loc_180019832
0x180019961  mov     rcx, [rsp+68h]; this
0x180019966  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001996d  mov     r9d, 8000FFFFh; char *
0x180019973  mov     edx, 166h; void *
0x180019978  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001997d  mov     eax, 8000FFFFh
0x180019982  jmp     loc_1800198F4
0x180019987  inc     rbp
0x18001998a  jmp     loc_1800197FA
0x18001998f  mov     rcx, [rsp+68h]; this
0x180019994  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x18001999b  mov     esi, 80070057h
0x1800199a0  mov     edx, 135h; void *
0x1800199a5  mov     r9d, esi; char *
0x1800199a8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199ad  jmp     loc_1800198E0
0x1800199b2  mov     ecx, ebx
0x1800199b4  call    cs:__imp_SRCache_AllocStringBuffer
0x1800199ba  mov     rsi, rax
0x1800199bd  test    rax, rax
0x1800199c0  jnz     loc_180019923
0x1800199c6  mov     rcx, [rsp+68h]; this
0x1800199cb  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800199d2  mov     esi, 8007000Eh
0x1800199d7  mov     edx, 193h; void *
0x1800199dc  mov     r9d, esi; char *
0x1800199df  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199e4  mov     rcx, [rsp+68h]; this
0x1800199e9  lea     r8, aOnecorePrivate; "onecore\\private\\base\\inc\\appmodel\\"...
0x1800199f0  mov     r9d, esi; char *
0x1800199f3  mov     edx, 136h; void *
0x1800199f8  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800199fd  jmp     loc_1800198D8
0x180019a02  call    cs:__imp_SRCache_Free
0x180019a08  jmp     loc_18001994B
0x180019a0d  mov     esi, 80070057h
0x180019a12  jmp     loc_180019908
0x180019a17  mov     rax, [r14+208h]
0x180019a1e  lea     rdx, [rsp+68h+var_48]
0x180019a23  lea     rcx, [r8+rax*2]
0x180019a27  xor     r8d, r8d
0x180019a2a  test    rdi, rdi
0x180019a2d  jz      short loc_180019A54
0x180019a2f  cmp     word ptr [rdx], 5Eh ; '^'
0x180019a33  jnz     short loc_180019A3E
0x180019a35  mov     word ptr [rcx], 5Eh ; '^'
0x180019a3a  add     rcx, 2
0x180019a3e  movzx   eax, word ptr [rdx]
0x180019a41  inc     r8
0x180019a44  mov     [rcx], ax
0x180019a47  add     rdx, 2
0x180019a4b  add     rcx, 2
0x180019a4f  cmp     r8, rdi
0x180019a52  jb      short loc_180019A2F
0x180019a54  xor     eax, eax
0x180019a56  mov     [rcx], ax
0x180019a59  jmp     loc_1800198CF
```
