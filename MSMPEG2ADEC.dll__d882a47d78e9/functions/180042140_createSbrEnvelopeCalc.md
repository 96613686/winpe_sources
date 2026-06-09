# createSbrEnvelopeCalc

- ea: `0x180042140`
- end: `0x18004241c`
- name: `createSbrEnvelopeCalc`
- size: `732`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x180039380`

## callees

- `0x1800017b0`
- `0x18003dc20`
- `0x180042140`

## pseudocode

```c
__int64 __fastcall createSbrEnvelopeCalc(__int64 a1, __int64 a2, __int64 a3, int a4)
{
  unsigned int v5; // edi
  __int64 v7; // r8
  __int64 v8; // rbx
  int v9; // r8d
  int v10; // edx
  unsigned __int8 v11; // r11
  __int64 v12; // r9
  __int64 v13; // r10
  __int64 v14; // rax
  _BYTE *v15; // r10
  _BYTE *v16; // r9
  unsigned int v17; // edx
  unsigned __int8 v18; // r8
  __int64 v19; // rcx
  unsigned __int8 i; // r8
  __int64 v21; // rcx
  unsigned __int8 *v22; // rsi
  unsigned __int8 v23; // r14
  unsigned __int8 v24; // r15
  int v25; // r9d
  int v26; // eax
  unsigned __int8 *v27; // r8
  float v28; // xmm0_4
  __int64 v29; // rcx
  float v30; // xmm1_4
  __int64 v31; // rax
  int v32; // r10d
  int v33; // r8d
  int v34; // r11d
  __int64 v35; // rcx
  int v36; // eax
  int j; // r9d
  __int64 v38; // rdx
  _DWORD v40[24]; // [rsp+20h] [rbp-A8h]

  v5 = -1;
  *(_QWORD *)(a1 + 28) = 0;
  *(_DWORD *)(a1 + 36) = 0;
  *(_BYTE *)(a1 + 40) = 0;
  v7 = 192LL * a4;
  *(_DWORD *)(a1 + 24) = -1;
  *(_QWORD *)a1 = v7 + a3 + 30720;
  *(_QWORD *)(a1 + 16) = 1;
  *(_QWORD *)(a1 + 8) = v7 + a3 + 32256;
  if ( !a4 )
  {
    v8 = *(_QWORD *)(a2 + 32);
    if ( !(unsigned int)sbrdecUpdateFreqScale((unsigned __int8 *)(v8 + 144), (unsigned __int8 *)(v8 + 3), a2) )
    {
      v9 = *(unsigned __int8 *)(v8 + 3);
      v10 = *(unsigned __int8 *)(a2 + 19);
      if ( (unsigned __int8)v10 <= (unsigned __int8)v9 )
      {
        v11 = v9 - v10;
        if ( v9 - v10 < 49 )
        {
          v12 = *(_QWORD *)(v8 + 32);
          v13 = *(unsigned __int8 *)(a2 + 19);
          do
          {
            v14 = (unsigned __int8)v10;
            LOBYTE(v10) = v10 + 1;
            *(_BYTE *)((unsigned int)v14 - v13 + v12) = *(_BYTE *)(v14 + v8 + 144);
          }
          while ( (unsigned __int8)v10 <= (unsigned __int8)v9 );
        }
        v15 = *(_BYTE **)(v8 + 32);
        v16 = *(_BYTE **)(v8 + 24);
        if ( (v11 & 1) != 0 )
        {
          *v16 = *v15;
          v17 = ((unsigned int)v11 + 1) >> 1;
          if ( 2 * (unsigned int)(unsigned __int8)v17 <= 0x30 )
          {
            for ( i = 1; i <= (unsigned __int8)v17; v16[v21] = v15[2 * v21 - 1] )
              v21 = i++;
          }
        }
        else
        {
          LOBYTE(v17) = v11 >> 1;
          if ( 2 * (unsigned int)(v11 >> 1) <= 0x30 )
          {
            v18 = 0;
            do
            {
              v19 = v18++;
              v16[v19] = v15[2 * v19];
            }
            while ( v18 <= (unsigned __int8)v17 );
          }
        }
        *(_BYTE *)v8 = v17;
        *(_BYTE *)(v8 + 1) = v11;
        if ( (unsigned __int8)(v17 - 1) <= 0x17u )
        {
          v22 = *(unsigned __int8 **)(v8 + 24);
          v23 = *v22;
          if ( *v22 <= 0x20u )
          {
            v24 = v22[(unsigned __int8)v17];
            if ( v23 < v24 )
            {
              v25 = *(unsigned __int8 *)(a2 + 22);
              if ( !(_BYTE)v25 )
              {
                LOBYTE(v26) = 1;
                *(_BYTE *)(v8 + 2) = 1;
                *(_BYTE *)(v8 + 20) = 1;
LABEL_28:
                v32 = (unsigned __int8)v17;
                v33 = 0;
                v34 = (unsigned __int8)v26;
                v40[0] = 0;
                if ( (_BYTE)v17 )
                {
                  while ( 1 )
                  {
                    v35 = v33++;
                    if ( (unsigned __int64)v33 >= 0x18 )
                      break;
                    v36 = v32 / v34--;
                    v32 -= v36;
                    v40[v33] = v40[v35] + v36;
                    if ( v32 <= 0 )
                      goto LABEL_33;
                  }
                  v33 = v35;
                }
LABEL_33:
                for ( j = 0; j <= v33; *(_BYTE *)(v38 + v8 + 138) = v22[v40[v38]] )
                  v38 = j++;
                *(_BYTE *)(v8 + 4) = v23;
                v5 = 0;
                *(_BYTE *)(v8 + 5) = v24;
                return v5;
              }
              v27 = *(unsigned __int8 **)(v8 + 32);
              v28 = 0.0;
              v29 = v27[v11];
              if ( (unsigned __int8)v29 >= 0x41u )
                v30 = 0.0;
              else
                v30 = *(float *)&dword_1800A39A0[v29];
              v31 = *v27;
              if ( (unsigned __int8)v31 < 0x41u )
                v28 = *(float *)&dword_1800A39A0[v31];
              v26 = (int)(float)((float)((float)(v30 - v28) * (float)v25) + 0.5);
              if ( !v26 )
                LOBYTE(v26) = 1;
              *(_BYTE *)(v8 + 2) = v26;
              *(_BYTE *)(v8 + 20) = v26;
              if ( (unsigned __int8)v26 <= 5u )
                goto LABEL_28;
            }
          }
        }
      }
    }
    return v5;
  }
  return 0;
}

```

## disassembly

```asm
0x180042140  mov     r11, rsp
0x180042143  push    rbp
0x180042144  push    rdi
0x180042145  push    r12
0x180042147  push    r13
0x180042149  sub     rsp, 0A8h
0x180042150  mov     rax, cs:__security_cookie
0x180042157  xor     rax, rsp
0x18004215a  mov     [rsp+0C8h+var_48], rax
0x180042162  mov     r10, r8
0x180042165  movsxd  rax, r9d
0x180042168  xor     r12d, r12d
0x18004216b  mov     edi, 0FFFFFFFFh
0x180042170  mov     [rcx+1Ch], r12
0x180042174  mov     rbp, rdx
0x180042177  mov     [rcx+24h], r12d
0x18004217b  mov     r13d, 1
0x180042181  lea     r8, [rax+rax*2]
0x180042185  mov     [rcx+28h], r12b
0x180042189  shl     r8, 6
0x18004218d  lea     rax, [r10+7800h]
0x180042194  add     rax, r8
0x180042197  mov     [rcx+18h], edi
0x18004219a  mov     [rcx], rax
0x18004219d  lea     rax, [r10+7E00h]
0x1800421a4  add     rax, r8
0x1800421a7  mov     qword ptr [rcx+10h], 1
0x1800421af  mov     [rcx+8], rax
0x1800421b3  test    r9d, r9d
0x1800421b6  jnz     loc_1800423FA
0x1800421bc  mov     [r11+18h], rbx
0x1800421c0  mov     r8, rdx
0x1800421c3  mov     rbx, [rdx+20h]
0x1800421c7  mov     [r11-28h], rsi
0x1800421cb  mov     [r11-30h], r14
0x1800421cf  mov     [r11-38h], r15
0x1800421d3  lea     rcx, [rbx+90h]
0x1800421da  lea     rdx, [rbx+3]
0x1800421de  call    sbrdecUpdateFreqScale
0x1800421e3  test    eax, eax
0x1800421e5  jnz     loc_1800423D6
0x1800421eb  movzx   r8d, byte ptr [rbx+3]
0x1800421f0  movzx   edx, byte ptr [rbp+13h]
0x1800421f4  cmp     dl, r8b
0x1800421f7  ja      loc_1800423D6
0x1800421fd  movzx   r11d, r8b
0x180042201  mov     eax, r8d
0x180042204  sub     r11b, dl
0x180042207  sub     eax, edx
0x180042209  cmp     eax, 31h ; '1'
0x18004220c  jge     short loc_180042230
0x18004220e  mov     r9, [rbx+20h]
0x180042212  mov     r10d, edx
0x180042215  movzx   eax, dl
0x180042218  inc     dl
0x18004221a  mov     ecx, eax
0x18004221c  sub     rcx, r10
0x18004221f  movzx   eax, byte ptr [rax+rbx+90h]
0x180042227  mov     [rcx+r9], al
0x18004222b  cmp     dl, r8b
0x18004222e  jbe     short loc_180042215
0x180042230  mov     r10, [rbx+20h]
0x180042234  mov     r9, [rbx+18h]
0x180042238  test    r13b, r11b
0x18004223b  jnz     short loc_180042267
0x18004223d  movzx   edx, r11b
0x180042241  shr     dl, 1
0x180042243  movzx   eax, dl
0x180042246  add     eax, eax
0x180042248  cmp     eax, 30h ; '0'
0x18004224b  ja      short loc_1800422A6
0x18004224d  xor     r8b, r8b
0x180042250  movzx   ecx, r8b
0x180042254  inc     r8b
0x180042257  movzx   eax, byte ptr [r10+rcx*2]
0x18004225c  mov     [rcx+r9], al
0x180042260  cmp     r8b, dl
0x180042263  jbe     short loc_180042250
0x180042265  jmp     short loc_1800422A6
0x180042267  movzx   eax, byte ptr [r10]
0x18004226b  mov     [r9], al
0x18004226e  movzx   edx, r11b
0x180042272  inc     edx
0x180042274  shr     edx, 1
0x180042276  movzx   eax, dl
0x180042279  add     eax, eax
0x18004227b  cmp     eax, 30h ; '0'
0x18004227e  ja      short loc_1800422A6
0x180042280  movzx   r8d, r13b
0x180042284  cmp     dl, r13b
0x180042287  jb      short loc_1800422A6
0x180042289  nop     dword ptr [rax+00000000h]
0x180042290  movzx   ecx, r8b
0x180042294  inc     r8b
0x180042297  movzx   eax, byte ptr [r10+rcx*2-1]
0x18004229d  mov     [rcx+r9], al
0x1800422a1  cmp     r8b, dl
0x1800422a4  jbe     short loc_180042290
0x1800422a6  lea     eax, [rdx-1]
0x1800422a9  mov     [rbx], dl
0x1800422ab  mov     [rbx+1], r11b
0x1800422af  cmp     al, 17h
0x1800422b1  ja      loc_1800423D6
0x1800422b7  mov     rsi, [rbx+18h]
0x1800422bb  movzx   r14d, byte ptr [rsi]
0x1800422bf  cmp     r14b, 20h ; ' '
0x1800422c3  ja      loc_1800423D6
0x1800422c9  movzx   eax, dl
0x1800422cc  movzx   r15d, byte ptr [rax+rsi]
0x1800422d1  cmp     r14b, r15b
0x1800422d4  jnb     loc_1800423D6
0x1800422da  movzx   r9d, byte ptr [rbp+16h]
0x1800422df  test    r9b, r9b
0x1800422e2  jnz     short loc_1800422F0
0x1800422e4  movzx   eax, r13b
0x1800422e8  mov     [rbx+2], al
0x1800422eb  mov     [rbx+14h], al
0x1800422ee  jmp     short loc_180042355
0x1800422f0  mov     r8, [rbx+20h]
0x1800422f4  lea     r10, dword_1800A39A0
0x1800422fb  movzx   eax, r11b
0x1800422ff  xorps   xmm0, xmm0
0x180042302  movzx   ecx, byte ptr [rax+r8]
0x180042307  cmp     cl, 41h ; 'A'
0x18004230a  jnb     short loc_180042314
0x18004230c  movss   xmm1, dword ptr [r10+rcx*4]
0x180042312  jmp     short loc_180042317
0x180042314  xorps   xmm1, xmm1
0x180042317  movzx   eax, byte ptr [r8]
0x18004231b  cmp     al, 41h ; 'A'
0x18004231d  jnb     short loc_180042325
0x18004231f  movss   xmm0, dword ptr [r10+rax*4]
0x180042325  subss   xmm1, xmm0
0x180042329  movd    xmm0, r9d
0x18004232e  cvtdq2ps xmm0, xmm0
0x180042331  mulss   xmm1, xmm0
0x180042335  addss   xmm1, cs:__real@3f000000
0x18004233d  cvttss2si eax, xmm1
0x180042341  test    eax, eax
0x180042343  cmovz   eax, r13d
0x180042347  mov     [rbx+2], al
0x18004234a  mov     [rbx+14h], al
0x18004234d  cmp     al, 5
0x18004234f  ja      loc_1800423D6
0x180042355  movzx   r10d, dl
0x180042359  mov     r8d, r12d
0x18004235c  movzx   r11d, al
0x180042360  mov     [rsp+0C8h+var_A8], r12d
0x180042365  test    dl, dl
0x180042367  jz      short loc_18004239F
0x180042369  nop     dword ptr [rax+00000000h]
0x180042370  movsxd  rcx, r8d
0x180042373  inc     r8d
0x180042376  movsxd  r9, r8d
0x180042379  cmp     r9, 18h
0x18004237d  jnb     short loc_18004239C
0x18004237f  mov     eax, r10d
0x180042382  cdq
0x180042383  idiv    r11d
0x180042386  dec     r11d
0x180042389  sub     r10d, eax
0x18004238c  add     eax, [rsp+rcx*4+0C8h+var_A8]
0x180042390  mov     [rsp+r9*4+0C8h+var_A8], eax
0x180042395  test    r10d, r10d
0x180042398  jg      short loc_180042370
0x18004239a  jmp     short loc_18004239F
0x18004239c  mov     r8d, ecx
0x18004239f  mov     r9d, r12d
0x1800423a2  test    r8d, r8d
0x1800423a5  js      short loc_1800423CB
0x1800423a7  nop     word ptr [rax+rax+00000000h]
0x1800423b0  movsxd  rdx, r9d
0x1800423b3  inc     r9d
0x1800423b6  movsxd  rax, [rsp+rdx*4+0C8h+var_A8]
0x1800423bb  movzx   ecx, byte ptr [rax+rsi]
0x1800423bf  mov     [rdx+rbx+8Ah], cl
0x1800423c6  cmp     r9d, r8d
0x1800423c9  jle     short loc_1800423B0
0x1800423cb  mov     [rbx+4], r14b
0x1800423cf  mov     edi, r12d
0x1800423d2  mov     [rbx+5], r15b
0x1800423d6  mov     r15, [rsp+0C8h+var_38]
0x1800423de  mov     eax, edi
0x1800423e0  mov     r14, [rsp+0C8h+var_30]
0x1800423e8  mov     rsi, [rsp+0C8h+var_28]
0x1800423f0  mov     rbx, [rsp+0C8h+arg_10]
0x1800423f8  jmp     short loc_1800423FD
0x1800423fa  mov     eax, r12d
0x1800423fd  mov     rcx, [rsp+0C8h+var_48]
0x180042405  xor     rcx, rsp; StackCookie
0x180042408  call    __security_check_cookie
0x18004240d  add     rsp, 0A8h
0x180042414  pop     r13
0x180042416  pop     r12
0x180042418  pop     rdi
0x180042419  pop     rbp
0x18004241a  retn
```
