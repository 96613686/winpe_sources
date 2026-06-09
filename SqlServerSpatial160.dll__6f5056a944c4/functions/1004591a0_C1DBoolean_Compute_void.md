# C1DBoolean::Compute(void)

- ea: `0x1004591a0`
- end: `0x100459406`
- name: `?Compute@C1DBoolean@@UEAAXXZ`
- size: `614`
- prototype: `void __fastcall(C1DBoolean *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x1004190d0`

## callees

- `0x1004591a0`

## pseudocode

```c
void __fastcall C1DBoolean::Compute(C1DBoolean *this)
{
  char v1; // si
  char v2; // di
  __int64 v4; // r9
  __int64 v5; // r8
  __int64 v6; // rbx
  __int64 v7; // r11
  unsigned int v8; // ecx
  bool v9; // cf
  int v10; // ecx
  double v11; // xmm0_8
  double v12; // xmm1_8
  int v13; // ecx
  int v14; // ecx
  double v15; // xmm1_8
  int v16; // ecx
  int v17; // ecx
  bool v18; // zf
  double v19; // xmm0_8
  int v20; // ecx
  double v21; // xmm1_8
  int v22; // ecx
  double v23; // xmm0_8
  int v24; // ecx
  int v25; // ecx
  bool v26; // zf
  double v27; // xmm1_8

  v1 = 0;
  v2 = 0;
  *((_QWORD *)this + 6) = 0x7FEFFFFFFFFFFFFFLL;
  *((_QWORD *)this + 1) = 0;
  while ( !v1 || !v2 )
  {
    v4 = *((_QWORD *)this + 3);
    v5 = *((_QWORD *)this + 4);
    v6 = *((unsigned int *)this + 10);
    v7 = *((unsigned int *)this + 11);
    v8 = *(_DWORD *)(v5 + 20);
    if ( (unsigned int)v6 >= *(_DWORD *)(v4 + 20) )
    {
      v1 = 1;
      if ( (unsigned int)v7 >= v8 )
      {
        v2 = 1;
      }
      else
      {
        v22 = *((_DWORD *)this + 4);
        *(_QWORD *)&v23 = *(_QWORD *)(*(_QWORD *)(v5 + 24) + 8 * v7) & _xmm;
        if ( !v22 )
        {
          v26 = *((_BYTE *)this + 56) == 0;
          goto LABEL_51;
        }
        v24 = v22 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( v25 )
          {
            if ( v25 != 1 )
              goto LABEL_56;
            v26 = *((_BYTE *)this + 56) == 1;
LABEL_51:
            if ( !v26 )
              goto LABEL_56;
          }
        }
        else if ( !*((_BYTE *)this + 56) )
        {
          goto LABEL_56;
        }
        v27 = *((double *)this + 6);
        if ( v27 == 1.797693134862316e308 )
        {
          *((double *)this + 6) = v23;
          goto LABEL_56;
        }
        *((double *)this + 1) = v23 - v27 + *((double *)this + 1);
LABEL_55:
        *((_QWORD *)this + 6) = 0x7FEFFFFFFFFFFFFFLL;
LABEL_56:
        *((_DWORD *)this + 11) = v7 + 1;
        *((_BYTE *)this + 57) = *((_BYTE *)this + 57) == 0;
      }
    }
    else
    {
      v9 = (unsigned int)v7 < v8;
      v10 = *((_DWORD *)this + 4);
      *(_QWORD *)&v11 = *(_QWORD *)(*(_QWORD *)(v4 + 24) + 8 * v6) & _xmm;
      if ( v9 )
      {
        *(_QWORD *)&v12 = *(_QWORD *)(*(_QWORD *)(v5 + 24) + 8 * v7) & _xmm;
        if ( v12 > v11 )
          goto LABEL_7;
        if ( v11 <= v12 )
        {
          if ( v10 && (v20 = v10 - 1) != 0 )
          {
            if ( v20 == 2 && *((_BYTE *)this + 56) != *((_BYTE *)this + 57) )
            {
LABEL_35:
              v21 = *((double *)this + 6);
              if ( v21 == 1.797693134862316e308 )
              {
                *((double *)this + 6) = v11;
              }
              else
              {
                *((_QWORD *)this + 6) = 0x7FEFFFFFFFFFFFFFLL;
                *((double *)this + 1) = v11 - v21 + *((double *)this + 1);
              }
            }
          }
          else if ( *((_BYTE *)this + 56) == *((_BYTE *)this + 57) )
          {
            goto LABEL_35;
          }
          *((_DWORD *)this + 10) = v6 + 1;
          *((_BYTE *)this + 56) = *((_BYTE *)this + 56) == 0;
          goto LABEL_56;
        }
        if ( v10 )
        {
          v16 = v10 - 1;
          if ( v16 )
          {
            v17 = v16 - 1;
            if ( v17 )
            {
              if ( v17 != 1 )
                goto LABEL_56;
              v18 = *((_BYTE *)this + 56) == 1;
              goto LABEL_25;
            }
          }
          else if ( !*((_BYTE *)this + 56) )
          {
            goto LABEL_56;
          }
        }
        else
        {
          v18 = *((_BYTE *)this + 56) == 0;
LABEL_25:
          if ( !v18 )
            goto LABEL_56;
        }
        v19 = *((double *)this + 6);
        if ( v19 == 1.797693134862316e308 )
        {
          *((double *)this + 6) = v12;
          goto LABEL_56;
        }
        *((double *)this + 1) = v12 - v19 + *((double *)this + 1);
        goto LABEL_55;
      }
      v2 = 1;
LABEL_7:
      if ( !v10 )
        goto LABEL_11;
      v13 = v10 - 1;
      if ( !v13 )
      {
        if ( !*((_BYTE *)this + 57) )
          goto LABEL_41;
        goto LABEL_12;
      }
      v14 = v13 - 1;
      if ( v14 )
      {
        if ( v14 != 1 )
          goto LABEL_41;
LABEL_11:
        if ( *((_BYTE *)this + 57) )
          goto LABEL_41;
      }
LABEL_12:
      v15 = *((double *)this + 6);
      if ( v15 == 1.797693134862316e308 )
      {
        *((double *)this + 6) = v11;
      }
      else
      {
        *((_QWORD *)this + 6) = 0x7FEFFFFFFFFFFFFFLL;
        *((double *)this + 1) = v11 - v15 + *((double *)this + 1);
      }
LABEL_41:
      *((_DWORD *)this + 10) = v6 + 1;
      *((_BYTE *)this + 56) = *((_BYTE *)this + 56) == 0;
    }
  }
}

```

## disassembly

```asm
0x1004591a0  mov     [rsp+arg_8], rbp
0x1004591a5  mov     [rsp+arg_10], rsi
0x1004591aa  push    rdi
0x1004591ab  movsd   xmm3, qword ptr cs:__xmm@7fffffffffffffff7fffffffffffffff
0x1004591b3  xor     sil, sil
0x1004591b6  movsd   xmm2, cs:__real@7fefffffffffffff
0x1004591be  mov     rbp, 7FEFFFFFFFFFFFFFh
0x1004591c8  xor     dil, dil
0x1004591cb  mov     [rcx+30h], rbp
0x1004591cf  mov     rdx, rcx
0x1004591d2  mov     qword ptr [rcx+8], 0
0x1004591da  mov     [rsp+8+arg_0], rbx
0x1004591df  nop
0x1004591e0  test    sil, sil
0x1004591e3  jz      short loc_1004591EE
0x1004591e5  test    dil, dil
0x1004591e8  jnz     loc_1004593F5
0x1004591ee  mov     r9, [rdx+18h]
0x1004591f2  mov     r8, [rdx+20h]
0x1004591f6  mov     ebx, [rdx+28h]
0x1004591f9  mov     r11d, [rdx+2Ch]
0x1004591fd  mov     ecx, [r8+14h]
0x100459201  cmp     ebx, [r9+14h]
0x100459205  jnb     loc_100459371
0x10045920b  mov     r10, [r9+18h]
0x10045920f  cmp     r11d, ecx
0x100459212  mov     ecx, [rdx+10h]
0x100459215  movsd   xmm0, qword ptr [r10+rbx*8]
0x10045921b  andps   xmm0, xmm3
0x10045921e  jnb     loc_100459342
0x100459224  mov     rax, [r8+18h]
0x100459228  movsd   xmm1, qword ptr [rax+r11*8]
0x10045922e  andps   xmm1, xmm3
0x100459231  comisd  xmm1, xmm0
0x100459235  jbe     short loc_100459283
0x100459237  test    ecx, ecx
0x100459239  jz      short loc_10045924E
0x10045923b  sub     ecx, 1
0x10045923e  jz      short loc_100459277
0x100459240  sub     ecx, 1
0x100459243  jz      short loc_100459258
0x100459245  cmp     ecx, 1
0x100459248  jnz     loc_10045935C
0x10045924e  cmp     byte ptr [rdx+39h], 0
0x100459252  jnz     loc_10045935C
0x100459258  movsd   xmm1, qword ptr [rdx+30h]
0x10045925d  ucomisd xmm1, xmm2
0x100459261  jp      loc_10045934A
0x100459267  jnz     loc_10045934A
0x10045926d  movsd   qword ptr [rdx+30h], xmm0
0x100459272  jmp     loc_10045935C
0x100459277  cmp     byte ptr [rdx+39h], 0
0x10045927b  jz      loc_10045935C
0x100459281  jmp     short loc_100459258
0x100459283  comisd  xmm0, xmm1
0x100459287  jbe     short loc_1004592E5
0x100459289  test    ecx, ecx
0x10045928b  jz      short loc_1004592B1
0x10045928d  sub     ecx, 1
0x100459290  jz      short loc_1004592A5
0x100459292  sub     ecx, 1
0x100459295  jz      short loc_1004592BB
0x100459297  cmp     ecx, 1
0x10045929a  jnz     loc_1004593D6
0x1004592a0  cmp     [rdx+38h], cl
0x1004592a3  jmp     short loc_1004592B5
0x1004592a5  cmp     byte ptr [rdx+38h], 0
0x1004592a9  jz      loc_1004593D6
0x1004592af  jmp     short loc_1004592BB
0x1004592b1  cmp     byte ptr [rdx+38h], 0
0x1004592b5  jnz     loc_1004593D6
0x1004592bb  movsd   xmm0, qword ptr [rdx+30h]
0x1004592c0  ucomisd xmm0, xmm2
0x1004592c4  jp      short loc_1004592D2
0x1004592c6  jnz     short loc_1004592D2
0x1004592c8  movsd   qword ptr [rdx+30h], xmm1
0x1004592cd  jmp     loc_1004593D6
0x1004592d2  subsd   xmm1, xmm0
0x1004592d6  addsd   xmm1, qword ptr [rdx+8]
0x1004592db  movsd   qword ptr [rdx+8], xmm1
0x1004592e0  jmp     loc_1004593D2
0x1004592e5  test    ecx, ecx
0x1004592e7  jz      short loc_1004592FE
0x1004592e9  sub     ecx, 1
0x1004592ec  jz      short loc_1004592FE
0x1004592ee  cmp     ecx, 2
0x1004592f1  jnz     short loc_10045932D
0x1004592f3  movzx   eax, byte ptr [rdx+39h]
0x1004592f7  cmp     [rdx+38h], al
0x1004592fa  jz      short loc_10045932D
0x1004592fc  jmp     short loc_100459307
0x1004592fe  movzx   eax, byte ptr [rdx+39h]
0x100459302  cmp     [rdx+38h], al
0x100459305  jnz     short loc_10045932D
0x100459307  movsd   xmm1, qword ptr [rdx+30h]
0x10045930c  ucomisd xmm1, xmm2
0x100459310  jp      short loc_10045931B
0x100459312  jnz     short loc_10045931B
0x100459314  movsd   qword ptr [rdx+30h], xmm0
0x100459319  jmp     short loc_10045932D
0x10045931b  subsd   xmm0, xmm1
0x10045931f  mov     [rdx+30h], rbp
0x100459323  addsd   xmm0, qword ptr [rdx+8]
0x100459328  movsd   qword ptr [rdx+8], xmm0
0x10045932d  lea     eax, [rbx+1]
0x100459330  mov     [rdx+28h], eax
0x100459333  cmp     byte ptr [rdx+38h], 0
0x100459337  setz    al
0x10045933a  mov     [rdx+38h], al
0x10045933d  jmp     loc_1004593D6
0x100459342  mov     dil, 1
0x100459345  jmp     loc_100459237
0x10045934a  subsd   xmm0, xmm1
0x10045934e  mov     [rdx+30h], rbp
0x100459352  addsd   xmm0, qword ptr [rdx+8]
0x100459357  movsd   qword ptr [rdx+8], xmm0
0x10045935c  lea     eax, [rbx+1]
0x10045935f  mov     [rdx+28h], eax
0x100459362  cmp     byte ptr [rdx+38h], 0
0x100459366  setz    al
0x100459369  mov     [rdx+38h], al
0x10045936c  jmp     loc_1004591E0
0x100459371  mov     sil, 1
0x100459374  cmp     r11d, ecx
0x100459377  jnb     short loc_1004593EC
0x100459379  mov     rax, [r8+18h]
0x10045937d  mov     ecx, [rdx+10h]
0x100459380  movsd   xmm0, qword ptr [rax+r11*8]
0x100459386  andps   xmm0, xmm3
0x100459389  test    ecx, ecx
0x10045938b  jz      short loc_1004593AA
0x10045938d  sub     ecx, 1
0x100459390  jz      short loc_1004593A2
0x100459392  sub     ecx, 1
0x100459395  jz      short loc_1004593B0
0x100459397  cmp     ecx, 1
0x10045939a  jnz     short loc_1004593D6
0x10045939c  cmp     [rdx+38h], sil
0x1004593a0  jmp     short loc_1004593AE
0x1004593a2  cmp     byte ptr [rdx+38h], 0
0x1004593a6  jz      short loc_1004593D6
0x1004593a8  jmp     short loc_1004593B0
0x1004593aa  cmp     byte ptr [rdx+38h], 0
0x1004593ae  jnz     short loc_1004593D6
0x1004593b0  movsd   xmm1, qword ptr [rdx+30h]
0x1004593b5  ucomisd xmm1, xmm2
0x1004593b9  jp      short loc_1004593C4
0x1004593bb  jnz     short loc_1004593C4
0x1004593bd  movsd   qword ptr [rdx+30h], xmm0
0x1004593c2  jmp     short loc_1004593D6
0x1004593c4  subsd   xmm0, xmm1
0x1004593c8  addsd   xmm0, qword ptr [rdx+8]
0x1004593cd  movsd   qword ptr [rdx+8], xmm0
0x1004593d2  mov     [rdx+30h], rbp
0x1004593d6  lea     eax, [r11+1]
0x1004593da  mov     [rdx+2Ch], eax
0x1004593dd  cmp     byte ptr [rdx+39h], 0
0x1004593e1  setz    al
0x1004593e4  mov     [rdx+39h], al
0x1004593e7  jmp     loc_1004591E0
0x1004593ec  movzx   edi, sil
0x1004593f0  jmp     loc_1004591E0
0x1004593f5  mov     rbx, [rsp+8+arg_0]
0x1004593fa  mov     rbp, [rsp+8+arg_8]
0x1004593ff  mov     rsi, [rsp+8+arg_10]
0x100459404  pop     rdi
0x100459405  retn
```
