# parse_command_line<wchar_t>(wchar_t *,wchar_t * *,wchar_t *,unsigned __int64 *,unsigned __int64 *)

- ea: `0x140004744`
- end: `0x1400048e6`
- name: `??$parse_command_line@_W@@YAXPEA_WPEAPEA_W0PEA_K2@Z`
- size: `418`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004948`

## callees

- `0x140004744`

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
0x140004744  mov     rax, rsp
0x140004747  mov     [rax+8], rbx
0x14000474b  mov     [rax+10h], rsi
0x14000474f  mov     [rax+18h], rdi
0x140004753  mov     [rax+20h], r14
0x140004757  push    r15
0x140004759  mov     r11, [rsp+8+arg_20]
0x14000475e  xor     esi, esi
0x140004760  mov     rbx, r9
0x140004763  mov     [r11], rsi
0x140004766  mov     qword ptr [r9], 1
0x14000476d  test    rdx, rdx
0x140004770  jz      short loc_140004779
0x140004772  mov     [rdx], r8
0x140004775  add     rdx, 8
0x140004779  mov     r9b, sil
0x14000477c  mov     r15d, 22h ; '"'
0x140004782  mov     r10, rcx
0x140004785  cmp     [rcx], r15w
0x140004789  jnz     short loc_14000479C
0x14000478b  test    r9b, r9b
0x14000478e  movzx   eax, r15w
0x140004792  setz    r9b
0x140004796  add     rcx, 2
0x14000479a  jmp     short loc_1400047BB
0x14000479c  inc     qword ptr [r11]
0x14000479f  test    r8, r8
0x1400047a2  jz      short loc_1400047AF
0x1400047a4  movzx   eax, word ptr [rcx]
0x1400047a7  mov     [r8], ax
0x1400047ab  add     r8, 2
0x1400047af  movzx   eax, word ptr [rcx]
0x1400047b2  add     rcx, 2
0x1400047b6  test    ax, ax
0x1400047b9  jz      short loc_1400047D8
0x1400047bb  test    r9b, r9b
0x1400047be  jnz     short loc_140004782
0x1400047c0  cmp     ax, 20h ; ' '
0x1400047c4  jz      short loc_1400047CC
0x1400047c6  cmp     ax, 9
0x1400047ca  jnz     short loc_140004782
0x1400047cc  test    r8, r8
0x1400047cf  jz      short loc_1400047DB
0x1400047d1  mov     [r8-2], si
0x1400047d6  jmp     short loc_1400047DB
0x1400047d8  mov     rcx, r10
0x1400047db  mov     dil, sil
0x1400047de  mov     r14d, 5Ch ; '\'
0x1400047e4  movzx   eax, word ptr [rcx]
0x1400047e7  test    ax, ax
0x1400047ea  jz      loc_1400048C4
0x1400047f0  cmp     ax, 20h ; ' '
0x1400047f4  jz      short loc_1400047FC
0x1400047f6  cmp     ax, 9
0x1400047fa  jnz     short loc_140004805
0x1400047fc  add     rcx, 2
0x140004800  movzx   eax, word ptr [rcx]
0x140004803  jmp     short loc_1400047F0
0x140004805  test    ax, ax
0x140004808  jz      loc_1400048C4
0x14000480e  test    rdx, rdx
0x140004811  jz      short loc_14000481A
0x140004813  mov     [rdx], r8
0x140004816  add     rdx, 8
0x14000481a  inc     qword ptr [rbx]
0x14000481d  mov     r10d, 1
0x140004823  mov     eax, esi
0x140004825  jmp     short loc_14000482D
0x140004827  add     rcx, 2
0x14000482b  inc     eax
0x14000482d  movzx   r9d, word ptr [rcx]
0x140004831  cmp     r9w, r14w
0x140004835  jz      short loc_140004827
0x140004837  cmp     r9w, r15w
0x14000483b  jnz     short loc_140004874
0x14000483d  test    r10b, al
0x140004840  jnz     short loc_14000485E
0x140004842  test    dil, dil
0x140004845  jz      short loc_140004854
0x140004847  cmp     [rcx+2], r15w
0x14000484c  jnz     short loc_140004854
0x14000484e  add     rcx, 2
0x140004852  jmp     short loc_14000485E
0x140004854  test    dil, dil
0x140004857  mov     r10d, esi
0x14000485a  setz    dil
0x14000485e  shr     eax, 1
0x140004860  jmp     short loc_140004874
0x140004862  dec     eax
0x140004864  test    r8, r8
0x140004867  jz      short loc_140004871
0x140004869  mov     [r8], r14w
0x14000486d  add     r8, 2
0x140004871  inc     qword ptr [r11]
0x140004874  test    eax, eax
0x140004876  jnz     short loc_140004862
0x140004878  movzx   eax, word ptr [rcx]
0x14000487b  test    ax, ax
0x14000487e  jz      short loc_1400048AF
0x140004880  test    dil, dil
0x140004883  jnz     short loc_140004891
0x140004885  cmp     ax, 20h ; ' '
0x140004889  jz      short loc_1400048AF
0x14000488b  cmp     ax, 9
0x14000488f  jz      short loc_1400048AF
0x140004891  test    r10d, r10d
0x140004894  jz      short loc_1400048A6
0x140004896  test    r8, r8
0x140004899  jz      short loc_1400048A3
0x14000489b  mov     [r8], ax
0x14000489f  add     r8, 2
0x1400048a3  inc     qword ptr [r11]
0x1400048a6  add     rcx, 2
0x1400048aa  jmp     loc_14000481D
0x1400048af  test    r8, r8
0x1400048b2  jz      short loc_1400048BC
0x1400048b4  mov     [r8], si
0x1400048b8  add     r8, 2
0x1400048bc  inc     qword ptr [r11]
0x1400048bf  jmp     loc_1400047E4
0x1400048c4  test    rdx, rdx
0x1400048c7  jz      short loc_1400048CC
0x1400048c9  mov     [rdx], rsi
0x1400048cc  inc     qword ptr [rbx]
0x1400048cf  mov     rbx, [rsp+8+arg_0]
0x1400048d4  mov     rsi, [rsp+8+arg_8]
0x1400048d9  mov     rdi, [rsp+8+arg_10]
0x1400048de  mov     r14, [rsp+8+arg_18]
0x1400048e3  pop     r15
0x1400048e5  retn
```
