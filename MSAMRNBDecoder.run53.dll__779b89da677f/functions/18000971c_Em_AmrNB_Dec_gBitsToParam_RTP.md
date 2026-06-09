# Em_AmrNB_Dec_gBitsToParam_RTP

- ea: `0x18000971c`
- end: `0x180009a6b`
- name: `Em_AmrNB_Dec_gBitsToParam_RTP`
- size: `847`
- prototype: `__int64 __fastcall(int *, char *, int *, __int64, _WORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180003800`

## callees

- `0x180001400`
- `0x180001f66`
- `0x18000971c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gBitsToParam_RTP(int *a1, char *a2, int *a3, __int64 a4, _WORD *a5)
{
  unsigned int v6; // edx
  char v8; // bp
  int v9; // ecx
  int v10; // eax
  char *v11; // rsi
  __int64 v12; // rbp
  int v13; // r14d
  __int64 v14; // r11
  int v15; // r10d
  unsigned __int8 v16; // r9
  __int64 v17; // r8
  int v18; // eax
  unsigned __int8 v19; // r9
  __int64 i; // r10
  int v21; // r11d
  int v22; // r9d
  int v23; // edx
  __int64 v24; // r10
  int v25; // r8d
  int v26; // eax
  unsigned __int8 v28; // cl
  unsigned __int8 *v29; // rsi
  __int16 v30; // r8
  unsigned __int8 v31; // dl
  __int16 v32; // r8
  __int16 v33; // cx
  __int16 v34; // r8
  unsigned __int8 v35; // al
  __int16 v36; // cx
  __int16 v37; // r8
  unsigned int v38; // edx
  int v39; // edx
  _DWORD v40[10]; // [rsp+20h] [rbp-68h] BYREF

  v6 = 0;
  v8 = *a2;
  v9 = *a2 & 0x7C;
  if ( (unsigned __int8)((unsigned __int8)(*a2 & 0x7C) >> 3) <= 8u && ((v9 - 120) & 0xFFFFFFFB) != 0 )
  {
    if ( ((v9 - 64) & 0xFFFFFFFB) == 0 )
    {
      v10 = 5;
      goto LABEL_6;
    }
    v6 = (unsigned __int8)(*a2 & 0x7C) >> 3;
    if ( (*a2 & 4) == 0 )
    {
      v10 = 3;
LABEL_6:
      *a1 = v10;
      goto LABEL_10;
    }
    *a1 = 0;
    v10 = 0;
  }
  else
  {
    v10 = 7;
    *a1 = 7;
  }
LABEL_10:
  if ( v10 != 7 )
  {
    *(_DWORD *)(a4 + 48) = v6;
    *(_DWORD *)(a4 + 52) = v6;
    v11 = a2 + 1;
    if ( (unsigned int)(*a1 - 4) <= 2 )
    {
      if ( *a3 >= 6 )
      {
        *a3 = 6;
        v28 = *v11;
        v29 = (unsigned __int8 *)(v11 + 1);
        v30 = 8 * (v28 & 0x1F);
        a5[1] = v30;
        *a5 = v28 >> 5;
        v31 = *v29++;
        a5[1] = v30 | (v31 >> 5);
        v32 = 16 * (v31 & 0x1F);
        a5[2] = v32;
        v33 = v32 | (*v29 >> 4);
        v34 = *v29 & 0xF;
        a5[2] = v33;
        v34 *= 32;
        a5[3] = v34;
        v35 = v29[1];
        v36 = v34 | (v35 >> 3);
        v37 = 8 * (v35 & 7);
        a5[3] = v36;
        a5[4] = v37;
        v38 = v29[2];
        a5[4] = v37 | (v29[2] >> 5);
        if ( (v8 & 4) != 0 )
        {
          if ( (v38 & 0x10) == 0 )
            *a1 = 4;
        }
        else
        {
          *a1 = 6;
        }
        v39 = (v38 >> 1) & 2 | (4 * ((v38 >> 1) & 1)) | (v38 >> 3) & 1;
        *(_DWORD *)(a4 + 48) = v39;
        *(_DWORD *)(a4 + 52) = v39;
        return 0;
      }
    }
    else
    {
      v12 = v6;
      v13 = (unsigned __int8)Em_AmrNB_Dec_NoBytes_RTP[v6];
      if ( *a3 >= v13 + 2 )
      {
        *a3 = v13 + 2;
        memset_0(v40, 0, (4LL * (unsigned __int8)Em_AmrNB_Dec_NoWords[v6] + 4) & 0xFFFFFFFFFFFFFFFCuLL);
        v14 = (__int64)*(&Em_AmrNB_Dec_ReOrder + v12);
        v15 = 0;
        if ( v13 )
        {
          do
          {
            v16 = *v11;
            v17 = 7;
            ++v11;
            do
            {
              if ( (v16 & 1) != 0 )
                v40[(unsigned __int64)*(unsigned __int8 *)(v14 + v17) >> 5] |= 1 << (31 - (*(_BYTE *)(v14 + v17) & 0x1F));
              v16 >>= 1;
              --v17;
            }
            while ( v17 != -1 );
            v14 += 8;
            ++v15;
          }
          while ( v15 < v13 );
        }
        v18 = (unsigned __int8)Em_AmrNB_Dec_NoLastBits_RTP[v12];
        v19 = (unsigned __int8)*v11 >> (8 - v18);
        for ( i = (unsigned int)(v18 - 1); (int)i >= 0; i = (unsigned int)(i - 1) )
        {
          if ( (v19 & 1) != 0 )
            v40[(unsigned __int64)*(unsigned __int8 *)(i + v14) >> 5] |= 1 << (31 - (*(_BYTE *)(i + v14) & 0x1F));
          v19 >>= 1;
        }
        v21 = (unsigned __int8)Em_AmrNB_Dec_NoOfParam[v12];
        if ( Em_AmrNB_Dec_NoOfParam[v12] )
        {
          v22 = 0;
          v23 = 32;
          v24 = 0;
          do
          {
            if ( v22 >= 8 )
              break;
            v25 = *((unsigned __int8 *)*(&Em_AmrNB_Dec_NoOfBits + v12) + v24);
            if ( v25 <= v23 )
            {
              v23 -= v25;
              v26 = v40[v22] >> (32 - v25);
            }
            else
            {
              if ( v23 )
              {
                v25 -= v23;
                LOWORD(v26) = ((unsigned __int16)(v40[v22] >> (32 - v23)) << v25) | (v40[v22 + 1] >> (32 - v25));
              }
              else
              {
                v26 = v40[v22 + 1] >> (32 - v25);
              }
              v23 = 32 - v25;
              ++v22;
            }
            a5[v24] = v26;
            v24 = (unsigned int)(v24 + 1);
            v40[v22] <<= v25;
          }
          while ( (int)v24 < v21 );
        }
        return 0;
      }
    }
    *a3 = 1;
    return 4294966295LL;
  }
  *a3 = 1;
  *(_DWORD *)(a4 + 48) = *(_DWORD *)(a4 + 52);
  return 0;
}

```

## disassembly

```asm
0x18000971c  push    rbx
0x18000971e  push    rbp
0x18000971f  push    rsi
0x180009720  push    rdi
0x180009721  push    r12
0x180009723  push    r14
0x180009725  push    r15
0x180009727  sub     rsp, 50h
0x18000972b  mov     rax, cs:__security_cookie
0x180009732  xor     rax, rsp
0x180009735  mov     [rsp+88h+var_40], rax
0x18000973a  mov     r15, [rsp+88h+arg_20]
0x180009742  mov     rsi, rdx
0x180009745  xor     edx, edx
0x180009747  mov     r10, rcx
0x18000974a  movzx   ebp, byte ptr [rsi]
0x18000974d  mov     ecx, ebp
0x18000974f  lea     r14d, [rdx+4]
0x180009753  and     ecx, 7Ch
0x180009756  lea     edi, [rdx+7]
0x180009759  mov     r11d, ecx
0x18000975c  shr     r11d, 3
0x180009760  cmp     r11b, 8
0x180009764  ja      short loc_18000979B
0x180009766  lea     eax, [rcx-78h]
0x180009769  mov     ebx, 0FFFFFFFBh
0x18000976e  test    ebx, eax
0x180009770  jz      short loc_18000979B
0x180009772  lea     eax, [rcx-40h]
0x180009775  test    ebx, eax
0x180009777  jz      short loc_180009794
0x180009779  mov     edx, r11d
0x18000977c  test    r14b, cl
0x18000977f  jnz     short loc_180009789
0x180009781  lea     eax, [rdi-4]
0x180009784  mov     [r10], eax
0x180009787  jmp     short loc_1800097A0
0x180009789  mov     dword ptr [r10], 0
0x180009790  xor     eax, eax
0x180009792  jmp     short loc_1800097A0
0x180009794  mov     eax, 5
0x180009799  jmp     short loc_180009784
0x18000979b  mov     eax, edi
0x18000979d  mov     [r10], edi
0x1800097a0  cmp     eax, edi
0x1800097a2  jz      loc_180009A3E
0x1800097a8  mov     [r9+30h], edx
0x1800097ac  mov     ebx, 1
0x1800097b1  mov     [r9+34h], edx
0x1800097b5  add     rsi, rbx
0x1800097b8  mov     eax, [r10]
0x1800097bb  sub     eax, r14d
0x1800097be  cmp     eax, 2
0x1800097c1  jbe     loc_180009948
0x1800097c7  mov     ebp, edx
0x1800097c9  lea     r12, cs:180000000h
0x1800097d0  movzx   r14d, ds:rva Em_AmrNB_Dec_NoBytes_RTP[r12+rbp]
0x1800097d9  lea     eax, [r14+2]
0x1800097dd  cmp     [r8], eax
0x1800097e0  jl      loc_180009953
0x1800097e6  mov     [r8], eax
0x1800097e9  lea     rcx, [rsp+88h+var_68]; void *
0x1800097ee  movzx   eax, ds:rva Em_AmrNB_Dec_NoWords[r12+rbp]
0x1800097f7  xor     edx, edx; Val
0x1800097f9  lea     r8, ds:4[rax*4]
0x180009801  and     r8, 0FFFFFFFFFFFFFFFCh; Size
0x180009805  call    memset_0
0x18000980a  mov     r11, ds:rva Em_AmrNB_Dec_ReOrder[r12+rbp*8]
0x180009812  xor     r10d, r10d
0x180009815  test    r14d, r14d
0x180009818  jz      short loc_18000985D
0x18000981a  mov     r9b, [rsi]
0x18000981d  mov     r8, rdi
0x180009820  add     rsi, rbx
0x180009823  test    bl, r9b
0x180009826  jbe     short loc_180009845
0x180009828  movzx   eax, byte ptr [r11+r8]
0x18000982d  mov     ecx, 1Fh
0x180009832  mov     edx, eax
0x180009834  and     eax, 1Fh
0x180009837  sub     ecx, eax
0x180009839  shr     rdx, 5
0x18000983d  mov     eax, ebx
0x18000983f  shl     eax, cl
0x180009841  or      [rsp+rdx*4+88h+var_68], eax
0x180009845  shr     r9b, 1
0x180009848  sub     r8, rbx
0x18000984b  cmp     r8, 0FFFFFFFFFFFFFFFFh
0x18000984f  jnz     short loc_180009823
0x180009851  add     r11, 8
0x180009855  add     r10d, ebx
0x180009858  cmp     r10d, r14d
0x18000985b  jl      short loc_18000981A
0x18000985d  movzx   eax, ds:rva Em_AmrNB_Dec_NoLastBits_RTP[r12+rbp]
0x180009866  mov     ecx, 8
0x18000986b  mov     r9b, [rsi]
0x18000986e  sub     ecx, eax
0x180009870  shr     r9b, cl
0x180009873  lea     r10d, [rax-1]
0x180009877  test    r10d, r10d
0x18000987a  js      short loc_1800098A8
0x18000987c  test    bl, r9b
0x18000987f  jbe     short loc_1800098A0
0x180009881  movzx   edx, byte ptr [r10+r11]
0x180009886  mov     ecx, 1Fh
0x18000988b  mov     r8d, edx
0x18000988e  mov     eax, ebx
0x180009890  and     edx, 1Fh
0x180009893  shr     r8, 5
0x180009897  sub     ecx, edx
0x180009899  shl     eax, cl
0x18000989b  or      [rsp+r8*4+88h+var_68], eax
0x1800098a0  shr     r9b, 1
0x1800098a3  sub     r10d, ebx
0x1800098a6  jns     short loc_18000987C
0x1800098a8  movzx   r11d, ds:rva Em_AmrNB_Dec_NoOfParam[r12+rbp]
0x1800098b1  test    r11d, r11d
0x1800098b4  jz      loc_180009A4D
0x1800098ba  mov     esi, 20h ; ' '
0x1800098bf  xor     r9d, r9d
0x1800098c2  mov     edx, esi
0x1800098c4  xor     r10d, r10d
0x1800098c7  cmp     r9d, 8
0x1800098cb  jge     loc_180009A4D
0x1800098d1  mov     rax, ds:rva Em_AmrNB_Dec_NoOfBits[r12+rbp*8]
0x1800098d9  mov     ecx, esi
0x1800098db  movzx   r8d, byte ptr [r10+rax]
0x1800098e0  movsxd  rax, r9d
0x1800098e3  cmp     r8d, edx
0x1800098e6  jle     short loc_180009920
0x1800098e8  test    edx, edx
0x1800098ea  jnz     short loc_1800098F7
0x1800098ec  mov     eax, [rsp+rax*4+88h+var_64]
0x1800098f0  sub     ecx, r8d
0x1800098f3  shr     eax, cl
0x1800098f5  jmp     short loc_180009916
0x1800098f7  sub     ecx, edx
0x1800098f9  sub     r8d, edx
0x1800098fc  mov     edx, [rsp+rax*4+88h+var_68]
0x180009900  mov     eax, [rsp+rax*4+88h+var_64]
0x180009904  shr     edx, cl
0x180009906  mov     ecx, r8d
0x180009909  shl     dx, cl
0x18000990c  mov     ecx, esi
0x18000990e  sub     ecx, r8d
0x180009911  shr     eax, cl
0x180009913  or      ax, dx
0x180009916  mov     edx, esi
0x180009918  sub     edx, r8d
0x18000991b  add     r9d, ebx
0x18000991e  jmp     short loc_18000992C
0x180009920  mov     eax, [rsp+rax*4+88h+var_68]
0x180009924  sub     edx, r8d
0x180009927  sub     ecx, r8d
0x18000992a  shr     eax, cl
0x18000992c  mov     [r15+r10*2], ax
0x180009931  mov     ecx, r8d
0x180009934  movsxd  rax, r9d
0x180009937  add     r10d, ebx
0x18000993a  shl     [rsp+rax*4+88h+var_68], cl
0x18000993e  cmp     r10d, r11d
0x180009941  jl      short loc_1800098C7
0x180009943  jmp     loc_180009A4D
0x180009948  mov     r11d, 6
0x18000994e  cmp     [r8], r11d
0x180009951  jge     short loc_180009960
0x180009953  mov     [r8], ebx
0x180009956  mov     eax, 0FFFFFC17h
0x18000995b  jmp     loc_180009A4F
0x180009960  mov     [r8], r11d
0x180009963  mov     cl, [rsi]
0x180009965  add     rsi, rbx
0x180009968  mov     al, cl
0x18000996a  and     cl, 1Fh
0x18000996d  movzx   r8d, cl
0x180009971  shr     al, 5
0x180009974  shl     r8w, 3
0x180009979  mov     [r15+2], r8w
0x18000997e  movzx   eax, al
0x180009981  mov     [r15], ax
0x180009985  mov     dl, [rsi]
0x180009987  add     rsi, rbx
0x18000998a  mov     al, dl
0x18000998c  and     dl, 1Fh
0x18000998f  shr     al, 5
0x180009992  movzx   ecx, al
0x180009995  or      cx, r8w
0x180009999  movzx   r8d, dl
0x18000999d  mov     [r15+2], cx
0x1800099a2  shl     r8w, 4
0x1800099a7  mov     [r15+4], r8w
0x1800099ac  mov     dl, [rsi]
0x1800099ae  mov     al, dl
0x1800099b0  and     dl, 0Fh
0x1800099b3  shr     al, 4
0x1800099b6  movzx   ecx, al
0x1800099b9  or      cx, r8w
0x1800099bd  movzx   r8d, dl
0x1800099c1  mov     [r15+4], cx
0x1800099c6  shl     r8w, 5
0x1800099cb  mov     [r15+6], r8w
0x1800099d0  mov     dl, [rsi+rbx]
0x1800099d3  mov     al, dl
0x1800099d5  and     dl, dil
0x1800099d8  shr     al, 3
0x1800099db  movzx   ecx, al
0x1800099de  or      cx, r8w
0x1800099e2  movzx   r8d, dl
0x1800099e6  shl     r8w, 3
0x1800099eb  mov     [r15+6], cx
0x1800099f0  mov     [r15+8], r8w
0x1800099f5  movzx   edx, byte ptr [rsi+rbx+1]
0x1800099fa  mov     al, dl
0x1800099fc  shr     al, 5
0x1800099ff  movzx   ecx, al
0x180009a02  or      cx, r8w
0x180009a06  mov     [r15+8], cx
0x180009a0b  test    r14b, bpl
0x180009a0e  jz      short loc_180009A1A
0x180009a10  test    dl, 10h
0x180009a13  jnz     short loc_180009A1D
0x180009a15  mov     [r10], r14d
0x180009a18  jmp     short loc_180009A1D
0x180009a1a  mov     [r10], r11d
0x180009a1d  mov     ecx, edx
0x180009a1f  shr     edx, 3
0x180009a22  shr     ecx, 1
0x180009a24  and     edx, ebx
0x180009a26  mov     eax, ecx
0x180009a28  and     ecx, 2
0x180009a2b  and     eax, ebx
0x180009a2d  shl     eax, 2
0x180009a30  or      edx, eax
0x180009a32  or      edx, ecx
0x180009a34  mov     [r9+30h], edx
0x180009a38  mov     [r9+34h], edx
0x180009a3c  jmp     short loc_180009A4D
0x180009a3e  mov     dword ptr [r8], 1
0x180009a45  mov     eax, [r9+34h]
0x180009a49  mov     [r9+30h], eax
0x180009a4d  xor     eax, eax
0x180009a4f  mov     rcx, [rsp+88h+var_40]
0x180009a54  xor     rcx, rsp; StackCookie
0x180009a57  call    __security_check_cookie
0x180009a5c  add     rsp, 50h
0x180009a60  pop     r15
0x180009a62  pop     r14
0x180009a64  pop     r12
0x180009a66  pop     rdi
0x180009a67  pop     rsi
0x180009a68  pop     rbp
0x180009a69  pop     rbx
0x180009a6a  retn
```
