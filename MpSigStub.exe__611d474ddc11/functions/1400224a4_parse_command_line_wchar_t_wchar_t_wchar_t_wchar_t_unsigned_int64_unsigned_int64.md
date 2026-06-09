# parse_command_line<wchar_t>(wchar_t *,wchar_t * *,wchar_t *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x1400224a4`
- end: `0x140022646`
- name: `??$parse_command_line@_W@@YAXPEA_WPEAPEA_W0PEA_K2@Z`
- size: `418`
- prototype: `__int64 __fastcall(__int16 *, __int16 **, __int16 *, _QWORD *, _QWORD *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1400226a8`

## callees

- `0x1400224a4`

## pseudocode

```c
__int64 __fastcall parse_command_line<wchar_t>(__int16 *a1, __int16 **a2, __int16 *a3, _QWORD *a4, _QWORD *a5)
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
0x1400224a4  mov     rax, rsp
0x1400224a7  mov     [rax+8], rbx
0x1400224ab  mov     [rax+10h], rsi
0x1400224af  mov     [rax+18h], rdi
0x1400224b3  mov     [rax+20h], r14
0x1400224b7  push    r15
0x1400224b9  mov     r11, [rsp+8+arg_20]
0x1400224be  xor     esi, esi
0x1400224c0  mov     rbx, r9
0x1400224c3  mov     [r11], rsi
0x1400224c6  mov     qword ptr [r9], 1
0x1400224cd  test    rdx, rdx
0x1400224d0  jz      short loc_1400224D9
0x1400224d2  mov     [rdx], r8
0x1400224d5  add     rdx, 8
0x1400224d9  mov     r9b, sil
0x1400224dc  mov     r15d, 22h ; '"'
0x1400224e2  mov     r10, rcx
0x1400224e5  cmp     [rcx], r15w
0x1400224e9  jnz     short loc_1400224FC
0x1400224eb  test    r9b, r9b
0x1400224ee  movzx   eax, r15w
0x1400224f2  setz    r9b
0x1400224f6  add     rcx, 2
0x1400224fa  jmp     short loc_14002251B
0x1400224fc  inc     qword ptr [r11]
0x1400224ff  test    r8, r8
0x140022502  jz      short loc_14002250F
0x140022504  movzx   eax, word ptr [rcx]
0x140022507  mov     [r8], ax
0x14002250b  add     r8, 2
0x14002250f  movzx   eax, word ptr [rcx]
0x140022512  add     rcx, 2
0x140022516  test    ax, ax
0x140022519  jz      short loc_140022538
0x14002251b  test    r9b, r9b
0x14002251e  jnz     short loc_1400224E2
0x140022520  cmp     ax, 20h ; ' '
0x140022524  jz      short loc_14002252C
0x140022526  cmp     ax, 9
0x14002252a  jnz     short loc_1400224E2
0x14002252c  test    r8, r8
0x14002252f  jz      short loc_14002253B
0x140022531  mov     [r8-2], si
0x140022536  jmp     short loc_14002253B
0x140022538  mov     rcx, r10
0x14002253b  mov     dil, sil
0x14002253e  mov     r14d, 5Ch ; '\'
0x140022544  movzx   eax, word ptr [rcx]
0x140022547  test    ax, ax
0x14002254a  jz      loc_140022624
0x140022550  cmp     ax, 20h ; ' '
0x140022554  jz      short loc_14002255C
0x140022556  cmp     ax, 9
0x14002255a  jnz     short loc_140022565
0x14002255c  add     rcx, 2
0x140022560  movzx   eax, word ptr [rcx]
0x140022563  jmp     short loc_140022550
0x140022565  test    ax, ax
0x140022568  jz      loc_140022624
0x14002256e  test    rdx, rdx
0x140022571  jz      short loc_14002257A
0x140022573  mov     [rdx], r8
0x140022576  add     rdx, 8
0x14002257a  inc     qword ptr [rbx]
0x14002257d  mov     r10d, 1
0x140022583  mov     eax, esi
0x140022585  jmp     short loc_14002258D
0x140022587  add     rcx, 2
0x14002258b  inc     eax
0x14002258d  movzx   r9d, word ptr [rcx]
0x140022591  cmp     r9w, r14w
0x140022595  jz      short loc_140022587
0x140022597  cmp     r9w, r15w
0x14002259b  jnz     short loc_1400225D4
0x14002259d  test    r10b, al
0x1400225a0  jnz     short loc_1400225BE
0x1400225a2  test    dil, dil
0x1400225a5  jz      short loc_1400225B4
0x1400225a7  cmp     [rcx+2], r15w
0x1400225ac  jnz     short loc_1400225B4
0x1400225ae  add     rcx, 2
0x1400225b2  jmp     short loc_1400225BE
0x1400225b4  test    dil, dil
0x1400225b7  mov     r10d, esi
0x1400225ba  setz    dil
0x1400225be  shr     eax, 1
0x1400225c0  jmp     short loc_1400225D4
0x1400225c2  dec     eax
0x1400225c4  test    r8, r8
0x1400225c7  jz      short loc_1400225D1
0x1400225c9  mov     [r8], r14w
0x1400225cd  add     r8, 2
0x1400225d1  inc     qword ptr [r11]
0x1400225d4  test    eax, eax
0x1400225d6  jnz     short loc_1400225C2
0x1400225d8  movzx   eax, word ptr [rcx]
0x1400225db  test    ax, ax
0x1400225de  jz      short loc_14002260F
0x1400225e0  test    dil, dil
0x1400225e3  jnz     short loc_1400225F1
0x1400225e5  cmp     ax, 20h ; ' '
0x1400225e9  jz      short loc_14002260F
0x1400225eb  cmp     ax, 9
0x1400225ef  jz      short loc_14002260F
0x1400225f1  test    r10d, r10d
0x1400225f4  jz      short loc_140022606
0x1400225f6  test    r8, r8
0x1400225f9  jz      short loc_140022603
0x1400225fb  mov     [r8], ax
0x1400225ff  add     r8, 2
0x140022603  inc     qword ptr [r11]
0x140022606  add     rcx, 2
0x14002260a  jmp     loc_14002257D
0x14002260f  test    r8, r8
0x140022612  jz      short loc_14002261C
0x140022614  mov     [r8], si
0x140022618  add     r8, 2
0x14002261c  inc     qword ptr [r11]
0x14002261f  jmp     loc_140022544
0x140022624  test    rdx, rdx
0x140022627  jz      short loc_14002262C
0x140022629  mov     [rdx], rsi
0x14002262c  inc     qword ptr [rbx]
0x14002262f  mov     rbx, [rsp+8+arg_0]
0x140022634  mov     rsi, [rsp+8+arg_8]
0x140022639  mov     rdi, [rsp+8+arg_10]
0x14002263e  mov     r14, [rsp+8+arg_18]
0x140022643  pop     r15
0x140022645  retn
```
