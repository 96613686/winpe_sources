# CommonUtil::UtilGetFilenameFromPath<wchar_t>(wchar_t const *,wchar_t const * *,unsigned __int64 *)

- ea: `0x140004064`
- end: `0x140004291`
- name: `??$UtilGetFilenameFromPath@_W@CommonUtil@@YAJPEB_WPEAPEB_WPEA_K@Z`
- size: `557`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140004294`

## callees

- `0x140004064`

## pseudocode

```c
__int64 __fastcall CommonUtil::UtilGetFilenameFromPath<wchar_t>(_WORD *a1, _QWORD *a2, unsigned __int64 *a3)
{
  unsigned int v3; // r10d
  unsigned __int64 v7; // rdi
  char v8; // si
  __int64 v9; // r11
  __int16 v10; // ax
  unsigned __int16 v11; // cx
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rax
  bool v15; // zf
  unsigned __int64 v16; // rax

  v3 = 0;
  *a2 = 0;
  v7 = 0;
  if ( a3 )
    *a3 = 0;
  v8 = 0;
  v9 = 0;
  if ( (*a1 == 47 || *a1 == 92) && (a1[1] == 47 || a1[1] == 92) )
  {
    v10 = a1[2];
    if ( v10 == 46 )
    {
      if ( a1[3] == 47 || a1[3] == 92 )
      {
        v9 = 4;
        goto LABEL_31;
      }
      goto LABEL_29;
    }
    if ( v10 == 63 )
    {
      if ( a1[3] == 47 || a1[3] == 92 )
      {
        v11 = a1[4];
        v9 = 4;
        if ( ((v11 - 85) & 0xFFDF) != 0 || ((a1[5] - 78) & 0xFFDF) != 0 || ((a1[6] - 67) & 0xFFDF) != 0 )
        {
          if ( (v11 < 0x61u || v11 > 0x7Au) && (unsigned __int16)(v11 - 65) > 0x19u
            || a1[5] != 58
            || a1[6] != 47 && a1[6] != 92 )
          {
            return 2147942402LL;
          }
          goto LABEL_31;
        }
        if ( a1[7] != 47 && a1[7] != 92 )
          return 2147942402LL;
        v9 = 8;
        goto LABEL_30;
      }
LABEL_29:
      v9 = 2;
LABEL_30:
      v8 = 1;
      goto LABEL_31;
    }
    if ( v10 != 47 && v10 != 92 )
      goto LABEL_29;
  }
LABEL_31:
  v12 = v9;
  v13 = v9;
  if ( !a1[v9] )
    goto LABEL_43;
  while ( 1 )
  {
    if ( a1[v13] == 47 || a1[v13] == 92 )
    {
      do
      {
        do
        {
          v12 = v13 + 1;
          v14 = v13;
          v15 = a1[++v13] == 47;
        }
        while ( v15 );
      }
      while ( a1[v12] == 92 );
      goto LABEL_41;
    }
    if ( a1[v13] == 58 )
      break;
LABEL_42:
    if ( !a1[++v13] )
      goto LABEL_43;
  }
  if ( v13 - v9 == 1 )
  {
    do
    {
      do
      {
        v12 = v13 + 1;
        v14 = v13;
        v15 = a1[++v13] == 47;
      }
      while ( v15 );
    }
    while ( a1[v12] == 92 );
LABEL_41:
    v13 = v14;
    ++v7;
    goto LABEL_42;
  }
  if ( a1[v13 + 1] == 47 && a1[v13 + 2] == 47 )
    return 2147500033LL;
LABEL_43:
  v16 = v13 - v12;
  if ( v8 && v7 < 2 )
    return 2147942402LL;
  if ( v16 > 2 )
    goto LABEL_54;
  if ( v16 == 1 )
    goto LABEL_49;
  if ( v16 != 2 )
    return 2147942402LL;
  if ( a1[v12 + 1] == 46 )
  {
LABEL_49:
    if ( a1[v12] == 46 )
      return 2147942402LL;
  }
LABEL_54:
  *a2 = &a1[v12];
  if ( a3 )
    *a3 = v16;
  LOBYTE(v3) = a1[v13] != 0;
  return v3;
}

```

## disassembly

```asm
0x140004064  mov     [rsp+arg_18], rbx
0x140004069  push    rsi
0x14000406a  push    rdi
0x14000406b  push    r14
0x14000406d  sub     rsp, 10h
0x140004071  xor     r10d, r10d
0x140004074  mov     rbx, r8
0x140004077  mov     [rdx], r10
0x14000407a  mov     r14, rdx
0x14000407d  mov     r9, rcx
0x140004080  mov     edi, r10d
0x140004083  test    r8, r8
0x140004086  jz      short loc_14000408B
0x140004088  mov     [r8], r10
0x14000408b  cmp     word ptr [rcx], 2Fh ; '/'
0x14000408f  mov     sil, r10b
0x140004092  mov     r11, r10
0x140004095  jz      short loc_1400040A1
0x140004097  cmp     word ptr [rcx], 5Ch ; '\'
0x14000409b  jnz     loc_140004196
0x1400040a1  cmp     word ptr [rcx+2], 2Fh ; '/'
0x1400040a6  jz      short loc_1400040B3
0x1400040a8  cmp     word ptr [rcx+2], 5Ch ; '\'
0x1400040ad  jnz     loc_140004196
0x1400040b3  movzx   eax, word ptr [rcx+4]
0x1400040b7  cmp     ax, 2Eh ; '.'
0x1400040bb  jnz     short loc_1400040DA
0x1400040bd  cmp     word ptr [rcx+6], 2Fh ; '/'
0x1400040c2  jz      short loc_1400040CF
0x1400040c4  cmp     word ptr [rcx+6], 5Ch ; '\'
0x1400040c9  jnz     loc_14000418D
0x1400040cf  mov     r11d, 4
0x1400040d5  jmp     loc_140004196
0x1400040da  cmp     ax, 3Fh ; '?'
0x1400040de  jnz     loc_140004181
0x1400040e4  cmp     word ptr [rcx+6], 2Fh ; '/'
0x1400040e9  jz      short loc_1400040F6
0x1400040eb  cmp     word ptr [rcx+6], 5Ch ; '\'
0x1400040f0  jnz     loc_14000418D
0x1400040f6  movzx   ecx, word ptr [rcx+8]
0x1400040fa  mov     edx, 0FFDFh
0x1400040ff  mov     r11d, 4
0x140004105  lea     eax, [rcx-55h]
0x140004108  test    dx, ax
0x14000410b  jnz     short loc_140004145
0x14000410d  movzx   eax, word ptr [r9+0Ah]
0x140004112  sub     ax, 4Eh ; 'N'
0x140004116  test    dx, ax
0x140004119  jnz     short loc_140004145
0x14000411b  movzx   eax, word ptr [r9+0Ch]
0x140004120  sub     ax, 43h ; 'C'
0x140004124  test    dx, ax
0x140004127  jnz     short loc_140004145
0x140004129  cmp     word ptr [r9+0Eh], 2Fh ; '/'
0x14000412f  jz      short loc_14000413D
0x140004131  cmp     word ptr [r9+0Eh], 5Ch ; '\'
0x140004137  jnz     loc_140004248
0x14000413d  mov     r11d, 8
0x140004143  jmp     short loc_140004193
0x140004145  cmp     cx, 61h ; 'a'
0x140004149  jb      short loc_140004151
0x14000414b  cmp     cx, 7Ah ; 'z'
0x14000414f  jbe     short loc_14000415F
0x140004151  sub     cx, 41h ; 'A'
0x140004155  cmp     cx, 19h
0x140004159  ja      loc_140004248
0x14000415f  cmp     word ptr [r9+0Ah], 3Ah ; ':'
0x140004165  jnz     loc_140004248
0x14000416b  cmp     word ptr [r9+0Ch], 2Fh ; '/'
0x140004171  jz      short loc_140004196
0x140004173  cmp     word ptr [r9+0Ch], 5Ch ; '\'
0x140004179  jnz     loc_140004248
0x14000417f  jmp     short loc_140004196
0x140004181  cmp     ax, 2Fh ; '/'
0x140004185  jz      short loc_140004196
0x140004187  cmp     ax, 5Ch ; '\'
0x14000418b  jz      short loc_140004196
0x14000418d  mov     r11d, 2
0x140004193  mov     sil, 1
0x140004196  mov     r8, r11
0x140004199  mov     rdx, r11
0x14000419c  cmp     [r9+r11*2], r10w
0x1400041a1  jz      short loc_140004211
0x1400041a3  cmp     word ptr [r9+rdx*2], 2Fh ; '/'
0x1400041a9  jz      short loc_1400041E7
0x1400041ab  cmp     word ptr [r9+rdx*2], 5Ch ; '\'
0x1400041b1  jz      short loc_1400041E7
0x1400041b3  cmp     word ptr [r9+rdx*2], 3Ah ; ':'
0x1400041b9  jnz     short loc_140004207
0x1400041bb  mov     rax, rdx
0x1400041be  sub     rax, r11
0x1400041c1  cmp     rax, 1
0x1400041c5  jnz     loc_14000424F
0x1400041cb  lea     r8, [rdx+1]
0x1400041cf  mov     rax, rdx
0x1400041d2  cmp     word ptr [r9+r8*2], 2Fh ; '/'
0x1400041d8  mov     rdx, r8
0x1400041db  jz      short loc_1400041CB
0x1400041dd  cmp     word ptr [r9+r8*2], 5Ch ; '\'
0x1400041e3  jz      short loc_1400041CB
0x1400041e5  jmp     short loc_140004201
0x1400041e7  lea     r8, [rdx+1]
0x1400041eb  mov     rax, rdx
0x1400041ee  cmp     word ptr [r9+r8*2], 2Fh ; '/'
0x1400041f4  mov     rdx, r8
0x1400041f7  jz      short loc_1400041E7
0x1400041f9  cmp     word ptr [r9+r8*2], 5Ch ; '\'
0x1400041ff  jz      short loc_1400041E7
0x140004201  mov     rdx, rax
0x140004204  inc     rdi
0x140004207  inc     rdx
0x14000420a  cmp     [r9+rdx*2], r10w
0x14000420f  jnz     short loc_1400041A3
0x140004211  mov     rax, rdx
0x140004214  sub     rax, r8
0x140004217  test    sil, sil
0x14000421a  jz      short loc_140004222
0x14000421c  cmp     rdi, 2
0x140004220  jb      short loc_140004248
0x140004222  cmp     rax, 2
0x140004226  ja      short loc_140004268
0x140004228  mov     rcx, rax
0x14000422b  sub     rcx, 1
0x14000422f  jz      short loc_140004240
0x140004231  cmp     rcx, 1
0x140004235  jnz     short loc_140004248
0x140004237  cmp     word ptr [r9+r8*2+2], 2Eh ; '.'
0x14000423e  jnz     short loc_140004268
0x140004240  cmp     word ptr [r9+r8*2], 2Eh ; '.'
0x140004246  jnz     short loc_140004268
0x140004248  mov     eax, 80070002h
0x14000424d  jmp     short loc_140004283
0x14000424f  cmp     word ptr [r9+rdx*2+2], 2Fh ; '/'
0x140004256  jnz     short loc_140004211
0x140004258  cmp     word ptr [r9+rdx*2+4], 2Fh ; '/'
0x14000425f  jnz     short loc_140004211
0x140004261  mov     eax, 80004001h
0x140004266  jmp     short loc_140004283
0x140004268  lea     rcx, [r9+r8*2]
0x14000426c  mov     [r14], rcx
0x14000426f  test    rbx, rbx
0x140004272  jz      short loc_140004277
0x140004274  mov     [rbx], rax
0x140004277  cmp     [r9+rdx*2], r10w
0x14000427c  setnz   r10b
0x140004280  mov     eax, r10d
0x140004283  mov     rbx, [rsp+28h+arg_18]
0x140004288  add     rsp, 10h
0x14000428c  pop     r14
0x14000428e  pop     rdi
0x14000428f  pop     rsi
0x140004290  retn
```
