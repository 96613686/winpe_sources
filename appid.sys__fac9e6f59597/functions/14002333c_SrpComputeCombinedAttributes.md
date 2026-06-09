# SrpComputeCombinedAttributes

- ea: `0x14002333c`
- end: `0x140023515`
- name: `SrpComputeCombinedAttributes`
- size: `473`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x140023c04`

## callees

- `0x1400032bc`
- `0x14002333c`

## pseudocode

```c
void __fastcall SrpComputeCombinedAttributes(__int64 a1)
{
  __int64 v1; // r8
  __int64 v2; // r9
  int v3; // ebx
  __int64 v4; // r11
  __int64 v5; // rsi
  __int64 v6; // rax
  __int64 v7; // rax
  unsigned int *v8; // rdx
  __int64 v9; // r11
  char *v10; // rdi
  unsigned int v11; // r13d
  unsigned int v12; // r12d
  __int64 i; // r10
  __int64 v14; // rcx
  unsigned int j; // r14d
  __int64 v16; // r15
  unsigned __int64 v17; // rcx
  __int64 v18; // rbp
  __int64 v19; // rdx
  int v20; // [rsp+68h] [rbp+10h]
  __int64 v21; // [rsp+70h] [rbp+18h]

  v1 = 0;
  v2 = a1;
  v3 = 0;
  v21 = 0;
  v20 = 0;
  v4 = 0;
  do
  {
    v5 = 3 * v4;
    if ( dword_1400196E4 )
    {
      if ( *(int *)(v2 + 48 * v4 + 32) >= 0 )
      {
        v6 = *(_QWORD *)(v2 + 48 * v4 + 40);
        if ( *(_DWORD *)(v6 + 12) )
        {
          *(_DWORD *)(v2 + 24 * v4 + 256) = *(_DWORD *)(v6 + 28);
          v7 = *(_QWORD *)(v2 + 48 * v4 + 40);
LABEL_8:
          *(_BYTE *)(v2 + 24 * v4 + 261) = *(_BYTE *)(v7 + 24) & 1;
          goto LABEL_9;
        }
      }
      if ( v3 == 2 )
      {
        v7 = *(_QWORD *)(v2 + 40);
        goto LABEL_8;
      }
    }
LABEL_9:
    if ( *(int *)(v2 + 208) >= 0 )
    {
      v8 = *(unsigned int **)(v2 + 216);
      if ( v8 )
      {
        if ( v8[3] )
        {
          v9 = v2 + 24 * v4;
          v10 = (char *)v8 + v8[2];
          v11 = 0;
          do
          {
            v12 = 0;
            for ( i = (__int64)&v8[7 * *((unsigned int *)v10 + 7)] + v8[4]; v12 < *((_DWORD *)v10 + 8); i += 28 )
            {
              v14 = *(_QWORD *)i - *(_QWORD *)(v2 + 8 * v5 + 240);
              if ( *(_QWORD *)i == *(_QWORD *)(v2 + 8 * v5 + 240) )
                v14 = *(_QWORD *)(i + 8) - *(_QWORD *)(v2 + 8 * v5 + 248);
              if ( !v14 )
              {
                LOBYTE(v1) = v3 == 2;
                AiSetAttributes(v9 + 256, *(unsigned int *)(i + 16), v1);
                v1 = 0;
                *(_BYTE *)(v2 + 8 * v5 + 260) = 1;
                for ( j = 0; j < *(_DWORD *)(i + 24); ++j )
                {
                  v16 = *(_QWORD *)(v2 + 224);
                  v17 = j + (unsigned __int64)*(unsigned int *)(i + 20);
                  v18 = 6 * v17;
                  if ( *(int *)(v16 + 48 * v17 + 32) >= 0 )
                  {
                    v19 = *(_QWORD *)(v16 + 48 * v17 + 40);
                    if ( *(_DWORD *)(v19 + 12) )
                    {
                      LOBYTE(v1) = v3 == 2;
                      AiSetAttributes(v9 + 256, *(unsigned int *)(v19 + 28), v1);
                      *(_BYTE *)(v2 + 8 * v5 + 261) |= *(_BYTE *)(*(_QWORD *)(v16 + 8 * v18 + 40) + 24LL) & 1;
                      v1 = 0;
                    }
                  }
                }
              }
              ++v12;
            }
            v8 = *(unsigned int **)(v2 + 216);
            ++v11;
            v10 += 36;
          }
          while ( v11 < v8[3] );
          v4 = v21;
          v3 = v20;
        }
      }
    }
    ++v3;
    ++v4;
    v20 = v3;
    v21 = v4;
  }
  while ( v3 < 4 );
}

```

## disassembly

```asm
0x14002333c  mov     [rsp+arg_18], rbx
0x140023341  push    rbp
0x140023342  push    rsi
0x140023343  push    rdi
0x140023344  push    r12
0x140023346  push    r13
0x140023348  push    r14
0x14002334a  push    r15
0x14002334c  sub     rsp, 20h
0x140023350  xor     r8d, r8d
0x140023353  mov     r9, rcx
0x140023356  mov     ebx, r8d
0x140023359  mov     [rsp+58h+arg_10], r8
0x14002335e  mov     [rsp+58h+arg_8], ebx
0x140023362  mov     r11d, r8d
0x140023365  cmp     ebx, 2
0x140023368  lea     rsi, [r11+r11*2]
0x14002336c  setz    [rsp+58h+arg_0]
0x140023371  cmp     cs:dword_1400196E4, r8d
0x140023378  jz      short loc_1400233BC
0x14002337a  lea     rcx, [r11+r11*2]
0x14002337e  add     rcx, rcx
0x140023381  cmp     [r9+rcx*8+20h], r8d
0x140023386  jl      short loc_1400233A5
0x140023388  mov     rax, [r9+rcx*8+28h]
0x14002338d  cmp     [rax+0Ch], r8d
0x140023391  jz      short loc_1400233A5
0x140023393  mov     eax, [rax+1Ch]
0x140023396  mov     [r9+rsi*8+100h], eax
0x14002339e  mov     rax, [r9+rcx*8+28h]
0x1400233a3  jmp     short loc_1400233AE
0x1400233a5  cmp     ebx, 2
0x1400233a8  jnz     short loc_1400233BC
0x1400233aa  mov     rax, [r9+28h]
0x1400233ae  mov     cl, [rax+18h]
0x1400233b1  and     cl, 1
0x1400233b4  mov     [r9+rsi*8+105h], cl
0x1400233bc  cmp     [r9+0D0h], r8d
0x1400233c3  jl      loc_1400234E8
0x1400233c9  mov     rdx, [r9+0D8h]
0x1400233d0  test    rdx, rdx
0x1400233d3  jz      loc_1400234E8
0x1400233d9  cmp     [rdx+0Ch], r8d
0x1400233dd  jbe     loc_1400234E8
0x1400233e3  mov     edi, [rdx+8]
0x1400233e6  lea     r11, [r9+rsi*8]
0x1400233ea  mov     bl, [rsp+58h+arg_0]
0x1400233ee  add     rdi, rdx
0x1400233f1  mov     r13d, r8d
0x1400233f4  mov     eax, [rdi+1Ch]
0x1400233f7  mov     r12d, r8d
0x1400233fa  mov     r10d, [rdx+10h]
0x1400233fe  imul    rax, 1Ch
0x140023402  add     rax, rdx
0x140023405  add     r10, rax
0x140023408  cmp     [rdi+20h], r8d
0x14002340c  jbe     loc_1400234C7
0x140023412  mov     rcx, [r10]
0x140023415  sub     rcx, [r9+rsi*8+0F0h]
0x14002341d  jnz     short loc_14002342B
0x14002341f  mov     rcx, [r10+8]
0x140023423  sub     rcx, [r9+rsi*8+0F8h]
0x14002342b  test    rcx, rcx
0x14002342e  jnz     loc_1400234B6
0x140023434  mov     edx, [r10+10h]
0x140023438  lea     rcx, [r11+100h]
0x14002343f  mov     r8b, bl
0x140023442  call    AiSetAttributes
0x140023447  xor     r8d, r8d
0x14002344a  mov     byte ptr [r9+rsi*8+104h], 1
0x140023453  mov     r14d, r8d
0x140023456  cmp     [r10+18h], r8d
0x14002345a  jbe     short loc_1400234B6
0x14002345c  mov     ecx, [r10+14h]
0x140023460  mov     r15, [r9+0E0h]
0x140023467  mov     eax, r14d
0x14002346a  add     rcx, rax
0x14002346d  lea     rbp, [rcx+rcx*2]
0x140023471  add     rbp, rbp
0x140023474  cmp     [r15+rbp*8+20h], r8d
0x140023479  jl      short loc_1400234AD
0x14002347b  mov     rdx, [r15+rbp*8+28h]
0x140023480  cmp     [rdx+0Ch], r8d
0x140023484  jz      short loc_1400234AD
0x140023486  mov     edx, [rdx+1Ch]
0x140023489  lea     rcx, [r11+100h]
0x140023490  mov     r8b, bl
0x140023493  call    AiSetAttributes
0x140023498  mov     rcx, [r15+rbp*8+28h]
0x14002349d  mov     al, [rcx+18h]
0x1400234a0  and     al, 1
0x1400234a2  or      [r9+rsi*8+105h], al
0x1400234aa  xor     r8d, r8d
0x1400234ad  inc     r14d
0x1400234b0  cmp     r14d, [r10+18h]
0x1400234b4  jb      short loc_14002345C
0x1400234b6  inc     r12d
0x1400234b9  add     r10, 1Ch
0x1400234bd  cmp     r12d, [rdi+20h]
0x1400234c1  jb      loc_140023412
0x1400234c7  mov     rdx, [r9+0D8h]
0x1400234ce  inc     r13d
0x1400234d1  add     rdi, 24h ; '$'
0x1400234d5  cmp     r13d, [rdx+0Ch]
0x1400234d9  jb      loc_1400233F4
0x1400234df  mov     r11, [rsp+58h+arg_10]
0x1400234e4  mov     ebx, [rsp+58h+arg_8]
0x1400234e8  inc     ebx
0x1400234ea  inc     r11
0x1400234ed  mov     [rsp+58h+arg_8], ebx
0x1400234f1  mov     [rsp+58h+arg_10], r11
0x1400234f6  cmp     ebx, 4
0x1400234f9  jl      loc_140023365
0x1400234ff  mov     rbx, [rsp+58h+arg_18]
0x140023504  add     rsp, 20h
0x140023508  pop     r15
0x14002350a  pop     r14
0x14002350c  pop     r13
0x14002350e  pop     r12
0x140023510  pop     rdi
0x140023511  pop     rsi
0x140023512  pop     rbp
0x140023513  retn
```
