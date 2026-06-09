# parse_command_line_wchar_t_

- ea: `0x140012304`
- end: `0x1400124a6`
- name: `parse_command_line_wchar_t_`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140012508`

## callees

- `0x140012304`

## pseudocode

```c
__int64 __fastcall parse_command_line_wchar_t_(__int16 *a1, __int16 **a2, __int16 *a3, _QWORD *a4, _QWORD *a5)
{
  bool v6; // r9
  __int16 *v7; // r10
  __int16 v8; // ax
  bool v9; // di
  __int64 result; // rax
  int v11; // r10d
  unsigned int v12; // eax
  __int16 v13; // ax

  *a5 = 0;
  *a4 = 1;
  if ( a2 )
    *a2++ = a3;
  v6 = 0;
  do
  {
    v7 = a1;
    if ( *a1 == 34 )
    {
      v8 = 34;
      v6 = !v6;
      ++a1;
    }
    else
    {
      ++*a5;
      if ( a3 )
        *a3++ = *a1;
      v8 = *a1++;
      if ( !v8 )
      {
        a1 = v7;
        goto LABEL_15;
      }
    }
  }
  while ( v6 || v8 != 32 && v8 != 9 );
  if ( a3 )
    *(a3 - 1) = 0;
LABEL_15:
  v9 = 0;
  while ( 1 )
  {
    result = (unsigned __int16)*a1;
    if ( !(_WORD)result )
      break;
    while ( (_WORD)result == 32 || (_WORD)result == 9 )
      result = (unsigned __int16)*++a1;
    if ( !(_WORD)result )
      break;
    if ( a2 )
      *a2++ = a3;
    ++*a4;
    while ( 1 )
    {
      v11 = 1;
      v12 = 0;
      while ( *a1 == 92 )
      {
        ++a1;
        ++v12;
      }
      if ( *a1 == 34 )
      {
        if ( (v12 & 1) == 0 )
        {
          if ( v9 && a1[1] == 34 )
          {
            ++a1;
          }
          else
          {
            v11 = 0;
            v9 = !v9;
          }
        }
        v12 >>= 1;
      }
      while ( v12 )
      {
        --v12;
        if ( a3 )
          *a3++ = 92;
        ++*a5;
      }
      v13 = *a1;
      if ( !*a1 || !v9 && (v13 == 32 || v13 == 9) )
        break;
      if ( v11 )
      {
        if ( a3 )
          *a3++ = v13;
        ++*a5;
      }
      ++a1;
    }
    if ( a3 )
      *a3++ = 0;
    ++*a5;
  }
  if ( a2 )
    *a2 = 0;
  ++*a4;
  return result;
}

```

## disassembly

```asm
0x140012304  mov     rax, rsp
0x140012307  mov     [rax+8], rbx
0x14001230b  mov     [rax+10h], rsi
0x14001230f  mov     [rax+18h], rdi
0x140012313  mov     [rax+20h], r14
0x140012317  push    r15
0x140012319  mov     r11, [rsp+8+arg_20]
0x14001231e  xor     esi, esi
0x140012320  mov     rbx, r9
0x140012323  mov     [r11], rsi
0x140012326  mov     qword ptr [r9], 1
0x14001232d  test    rdx, rdx
0x140012330  jz      short loc_140012339
0x140012332  mov     [rdx], r8
0x140012335  add     rdx, 8
0x140012339  mov     r9b, sil
0x14001233c  mov     r15d, 22h ; '"'
0x140012342  mov     r10, rcx
0x140012345  cmp     [rcx], r15w
0x140012349  jnz     short loc_14001235C
0x14001234b  test    r9b, r9b
0x14001234e  movzx   eax, r15w
0x140012352  setz    r9b
0x140012356  add     rcx, 2
0x14001235a  jmp     short loc_14001237B
0x14001235c  inc     qword ptr [r11]
0x14001235f  test    r8, r8
0x140012362  jz      short loc_14001236F
0x140012364  movzx   eax, word ptr [rcx]
0x140012367  mov     [r8], ax
0x14001236b  add     r8, 2
0x14001236f  movzx   eax, word ptr [rcx]
0x140012372  add     rcx, 2
0x140012376  test    ax, ax
0x140012379  jz      short loc_140012398
0x14001237b  test    r9b, r9b
0x14001237e  jnz     short loc_140012342
0x140012380  cmp     ax, 20h ; ' '
0x140012384  jz      short loc_14001238C
0x140012386  cmp     ax, 9
0x14001238a  jnz     short loc_140012342
0x14001238c  test    r8, r8
0x14001238f  jz      short loc_14001239B
0x140012391  mov     [r8-2], si
0x140012396  jmp     short loc_14001239B
0x140012398  mov     rcx, r10
0x14001239b  mov     dil, sil
0x14001239e  mov     r14d, 5Ch ; '\'
0x1400123a4  movzx   eax, word ptr [rcx]
0x1400123a7  test    ax, ax
0x1400123aa  jz      loc_140012484
0x1400123b0  cmp     ax, 20h ; ' '
0x1400123b4  jz      short loc_1400123BC
0x1400123b6  cmp     ax, 9
0x1400123ba  jnz     short loc_1400123C5
0x1400123bc  add     rcx, 2
0x1400123c0  movzx   eax, word ptr [rcx]
0x1400123c3  jmp     short loc_1400123B0
0x1400123c5  test    ax, ax
0x1400123c8  jz      loc_140012484
0x1400123ce  test    rdx, rdx
0x1400123d1  jz      short loc_1400123DA
0x1400123d3  mov     [rdx], r8
0x1400123d6  add     rdx, 8
0x1400123da  inc     qword ptr [rbx]
0x1400123dd  mov     r10d, 1
0x1400123e3  mov     eax, esi
0x1400123e5  jmp     short loc_1400123ED
0x1400123e7  add     rcx, 2
0x1400123eb  inc     eax
0x1400123ed  movzx   r9d, word ptr [rcx]
0x1400123f1  cmp     r9w, r14w
0x1400123f5  jz      short loc_1400123E7
0x1400123f7  cmp     r9w, r15w
0x1400123fb  jnz     short loc_140012434
0x1400123fd  test    r10b, al
0x140012400  jnz     short loc_14001241E
0x140012402  test    dil, dil
0x140012405  jz      short loc_140012414
0x140012407  cmp     [rcx+2], r15w
0x14001240c  jnz     short loc_140012414
0x14001240e  add     rcx, 2
0x140012412  jmp     short loc_14001241E
0x140012414  test    dil, dil
0x140012417  mov     r10d, esi
0x14001241a  setz    dil
0x14001241e  shr     eax, 1
0x140012420  jmp     short loc_140012434
0x140012422  dec     eax
0x140012424  test    r8, r8
0x140012427  jz      short loc_140012431
0x140012429  mov     [r8], r14w
0x14001242d  add     r8, 2
0x140012431  inc     qword ptr [r11]
0x140012434  test    eax, eax
0x140012436  jnz     short loc_140012422
0x140012438  movzx   eax, word ptr [rcx]
0x14001243b  test    ax, ax
0x14001243e  jz      short loc_14001246F
0x140012440  test    dil, dil
0x140012443  jnz     short loc_140012451
0x140012445  cmp     ax, 20h ; ' '
0x140012449  jz      short loc_14001246F
0x14001244b  cmp     ax, 9
0x14001244f  jz      short loc_14001246F
0x140012451  test    r10d, r10d
0x140012454  jz      short loc_140012466
0x140012456  test    r8, r8
0x140012459  jz      short loc_140012463
0x14001245b  mov     [r8], ax
0x14001245f  add     r8, 2
0x140012463  inc     qword ptr [r11]
0x140012466  add     rcx, 2
0x14001246a  jmp     loc_1400123DD
0x14001246f  test    r8, r8
0x140012472  jz      short loc_14001247C
0x140012474  mov     [r8], si
0x140012478  add     r8, 2
0x14001247c  inc     qword ptr [r11]
0x14001247f  jmp     loc_1400123A4
0x140012484  test    rdx, rdx
0x140012487  jz      short loc_14001248C
0x140012489  mov     [rdx], rsi
0x14001248c  inc     qword ptr [rbx]
0x14001248f  mov     rbx, [rsp+8+arg_0]
0x140012494  mov     rsi, [rsp+8+arg_8]
0x140012499  mov     rdi, [rsp+8+arg_10]
0x14001249e  mov     r14, [rsp+8+arg_18]
0x1400124a3  pop     r15
0x1400124a5  retn
```
