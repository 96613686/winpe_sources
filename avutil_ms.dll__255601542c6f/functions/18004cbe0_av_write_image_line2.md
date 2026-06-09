# av_write_image_line2

- ea: `0x18004cbe0`
- end: `0x18004ce73`
- name: `av_write_image_line2`
- size: `659`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180040da0`
- `0x18004cb90`

## callees

- `0x18004cbe0`
- `0x180078c32`

## pseudocode

```c
int __fastcall av_write_image_line2(
        int *a1,
        __int64 a2,
        __int64 a3,
        __int64 a4,
        int a5,
        int a6,
        int a7,
        int a8,
        int a9)
{
  int *v9; // rdi
  int v10; // r15d
  int *v12; // rsi
  __m128i v13; // xmm1
  int v14; // r11d
  unsigned __int64 v15; // rax
  unsigned __int64 v16; // r10
  int v17; // edx
  __int64 v18; // r8
  unsigned int *v19; // r14
  __m128i v20; // xmm1
  int v21; // ebp
  char v22; // r12
  unsigned int v23; // ebx
  int v24; // r15d
  unsigned int v25; // eax
  int v26; // edx
  __int64 v27; // r9
  int v28; // r8d
  int v29; // edx
  _BYTE *v30; // r9
  int v31; // r8d
  int v32; // eax
  char v33; // cl
  int v34; // r8d
  int v35; // r12d
  unsigned int *v36; // rbx
  _BYTE *v37; // rbx
  int v38; // edx
  int v39; // r14d
  int v40; // r15d
  __int64 v41; // r13
  int v42; // ebp
  __int16 v43; // ax
  __int16 v44; // bp
  __int16 v45; // ax
  unsigned int v46; // eax
  int v47; // ebp
  unsigned int v48; // eax
  unsigned int v49; // eax
  int v51; // [rsp+80h] [rbp+38h]

  v9 = a1;
  v10 = *(_DWORD *)(a4 + 16);
  v12 = a1;
  v13 = *(__m128i *)(a4 + 20LL * a7 + 24);
  v14 = *(_DWORD *)(a4 + 20LL * a7 + 40);
  v15 = *(_QWORD *)(a4 + 20LL * a7 + 24);
  v16 = HIDWORD(v15);
  if ( v14 )
  {
    v17 = a6 * *(_DWORD *)(a3 + 4LL * (int)v15);
    v18 = *(_QWORD *)(a2 + 8LL * (int)v15);
    if ( (v10 & 4) != 0 )
    {
      v19 = (unsigned int *)(v18 + v17);
      v20 = _mm_srli_si128(v13, 8);
      if ( SHIDWORD(v15) <= 8 )
      {
        LODWORD(v15) = _mm_cvtsi128_si32(v20);
        v26 = v15 + a5 * v16;
        v27 = v26;
        v28 = 8 - (v26 & 7);
        v29 = a8;
        v30 = (char *)v19 + (v27 >> 3);
        v31 = v28 - v14;
        while ( v29 )
        {
          --v29;
          if ( a9 == 4 )
          {
            v32 = *v9++;
          }
          else
          {
            LOWORD(v32) = *(_WORD *)v12;
            v12 = (int *)((char *)v12 + 2);
          }
          v33 = v31;
          v34 = v31 - v16;
          *v30 |= (_BYTE)v32 << v33;
          v15 = (__int64)v34 >> 3;
          v30 -= v15;
          v31 = v34 & 7;
        }
      }
      else
      {
        v21 = a8;
        v22 = _mm_cvtsi128_si32(v20);
        if ( a8 )
        {
          v23 = ~(unsigned int)(((1LL << v14) - 1) << v22);
          do
          {
            --v21;
            if ( a9 == 4 )
            {
              v24 = *v9++;
            }
            else
            {
              v24 = *(unsigned __int16 *)v12;
              v12 = (int *)((char *)v12 + 2);
            }
            v25 = byteswap_ulong(*v19);
            LODWORD(v15) = byteswap_ulong((v24 << v22) | v25 & v23);
            *v19++ = v15;
          }
          while ( v21 );
        }
      }
    }
    else
    {
      v35 = _mm_cvtsi128_si32(_mm_srli_si128(v13, 12));
      LODWORD(v15) = v35 + v14;
      v36 = (unsigned int *)(v17
                           + v18
                           + a5 * (int)v16
                           + _mm_cvtsi128_si32(_mm_srli_si128(*(__m128i *)(a4 + 20LL * a7 + 24), 8)));
      v51 = v35 + v14;
      if ( v35 + v14 > 8 )
      {
        v39 = a8;
        if ( a8 )
        {
          v40 = *(_DWORD *)(a4 + 16) & 1;
          v41 = (int)v16;
          do
          {
            --v39;
            if ( a9 == 4 )
            {
              v42 = *v9++;
            }
            else
            {
              v42 = *(unsigned __int16 *)v12;
              v12 = (int *)((char *)v12 + 2);
            }
            if ( (int)v15 > 16 )
            {
              v46 = *v36;
              v47 = v42 << v35;
              if ( v40 )
              {
                _mm_lfence();
                v48 = byteswap_ulong(v46);
                v49 = byteswap_ulong(v47 | v48);
              }
              else
              {
                v49 = v47 | v46;
              }
              *v36 = v49;
            }
            else
            {
              v43 = *(_WORD *)v36;
              v44 = (_WORD)v42 << v35;
              if ( v40 )
                v45 = __ROR2__(v44 | __ROR2__(v43, 8), 8);
              else
                v45 = v44 | v43;
              *(_WORD *)v36 = v45;
            }
            LODWORD(v15) = v51;
            v36 = (unsigned int *)((char *)v36 + v41);
          }
          while ( v39 );
        }
      }
      else
      {
        v37 = (char *)v36 + (v10 & 1);
        LODWORD(v15) = a8;
        if ( a8 )
        {
          do
          {
            LODWORD(v15) = v15 - 1;
            if ( a9 == 4 )
            {
              v38 = *v9++;
            }
            else
            {
              LOWORD(v38) = *(_WORD *)v12;
              v12 = (int *)((char *)v12 + 2);
            }
            *v37 |= (_BYTE)v38 << v35;
            v37 += (int)v16;
          }
          while ( (_DWORD)v15 );
        }
      }
    }
  }
  return v15;
}

```

## disassembly

```asm
0x18004cbe0  mov     [rsp+arg_0], rbx
0x18004cbe5  mov     [rsp+arg_8], rbp
0x18004cbea  mov     [rsp+arg_10], rsi
0x18004cbef  push    rdi
0x18004cbf0  push    r12
0x18004cbf2  push    r13
0x18004cbf4  push    r14
0x18004cbf6  push    r15
0x18004cbf8  sub     rsp, 20h
0x18004cbfc  movsxd  rax, [rsp+48h+arg_30]
0x18004cc04  mov     rdi, rcx
0x18004cc07  mov     r15d, [r9+10h]
0x18004cc0b  mov     rbx, rdx
0x18004cc0e  mov     rsi, rdi
0x18004cc11  lea     rcx, [rax+rax*4]
0x18004cc15  movups  xmm1, xmmword ptr [r9+rcx*4+18h]
0x18004cc1b  mov     r11d, [r9+rcx*4+28h]
0x18004cc20  movq    rax, xmm1
0x18004cc25  mov     r10, rax
0x18004cc28  shr     r10, 20h
0x18004cc2c  test    r11d, r11d
0x18004cc2f  jz      loc_18004CE56
0x18004cc35  cdqe
0x18004cc37  mov     edx, [r8+rax*4]
0x18004cc3b  imul    edx, [rsp+48h+arg_28]
0x18004cc40  mov     r8, [rbx+rax*8]
0x18004cc44  test    r15b, 4
0x18004cc48  jz      loc_18004CD3D
0x18004cc4e  movsxd  r14, edx
0x18004cc51  add     r14, r8
0x18004cc54  psrldq  xmm1, 8
0x18004cc59  mov     r8d, 8
0x18004cc5f  cmp     r10d, r8d
0x18004cc62  jle     short loc_18004CCD6
0x18004cc64  mov     ebp, [rsp+48h+arg_38]
0x18004cc6b  lea     ebx, [r8-7]
0x18004cc6f  mov     ecx, r11d
0x18004cc72  movd    r12d, xmm1
0x18004cc77  shl     rbx, cl
0x18004cc7a  dec     rbx
0x18004cc7d  mov     ecx, r12d
0x18004cc80  shl     rbx, cl
0x18004cc83  test    ebp, ebp
0x18004cc85  jz      loc_18004CE56
0x18004cc8b  not     ebx
0x18004cc8d  dec     ebp
0x18004cc8f  cmp     [rsp+48h+arg_40], 4
0x18004cc97  jnz     short loc_18004CCA2
0x18004cc99  mov     r15d, [rdi]
0x18004cc9c  add     rdi, 4
0x18004cca0  jmp     short loc_18004CCAA
0x18004cca2  movzx   r15d, word ptr [rsi]
0x18004cca6  add     rsi, 2
0x18004ccaa  mov     ecx, [r14]; Number
0x18004ccad  call    _byteswap_ulong
0x18004ccb2  mov     ecx, r12d
0x18004ccb5  mov     edx, ebx
0x18004ccb7  shl     r15d, cl
0x18004ccba  and     edx, eax
0x18004ccbc  or      edx, r15d
0x18004ccbf  mov     ecx, edx; Number
0x18004ccc1  call    _byteswap_ulong
0x18004ccc6  mov     [r14], eax
0x18004ccc9  add     r14, 4
0x18004cccd  test    ebp, ebp
0x18004cccf  jnz     short loc_18004CC8D
0x18004ccd1  jmp     loc_18004CE56
0x18004ccd6  mov     edx, r10d
0x18004ccd9  movd    eax, xmm1
0x18004ccdd  imul    edx, [rsp+48h+arg_20]
0x18004cce2  add     edx, eax
0x18004cce4  movsxd  r9, edx
0x18004cce7  and     edx, 7
0x18004ccea  sar     r9, 3
0x18004ccee  sub     r8d, edx
0x18004ccf1  mov     edx, [rsp+48h+arg_38]
0x18004ccf8  add     r9, r14
0x18004ccfb  sub     r8d, r11d
0x18004ccfe  jmp     short loc_18004CD34
0x18004cd00  dec     edx
0x18004cd02  cmp     [rsp+48h+arg_40], 4
0x18004cd0a  jnz     short loc_18004CD14
0x18004cd0c  mov     eax, [rdi]
0x18004cd0e  add     rdi, 4
0x18004cd12  jmp     short loc_18004CD1B
0x18004cd14  movzx   eax, word ptr [rsi]
0x18004cd17  add     rsi, 2
0x18004cd1b  mov     ecx, r8d
0x18004cd1e  sub     r8d, r10d
0x18004cd21  shl     al, cl
0x18004cd23  or      [r9], al
0x18004cd26  movsxd  rax, r8d
0x18004cd29  sar     rax, 3
0x18004cd2d  sub     r9, rax
0x18004cd30  and     r8d, 7
0x18004cd34  test    edx, edx
0x18004cd36  jnz     short loc_18004CD00
0x18004cd38  jmp     loc_18004CE56
0x18004cd3d  movdqa  xmm0, xmm1
0x18004cd41  movsxd  rdx, edx
0x18004cd44  mov     eax, r10d
0x18004cd47  psrldq  xmm1, 0Ch
0x18004cd4c  imul    eax, [rsp+48h+arg_20]
0x18004cd51  psrldq  xmm0, 8
0x18004cd56  movd    r12d, xmm1
0x18004cd5b  movsxd  rcx, eax
0x18004cd5e  add     rcx, r8
0x18004cd61  movd    eax, xmm0
0x18004cd65  add     rcx, rdx
0x18004cd68  mov     r8d, 8
0x18004cd6e  movsxd  rbx, eax
0x18004cd71  lea     eax, [r12+r11]
0x18004cd75  add     rbx, rcx
0x18004cd78  mov     [rsp+48h+arg_30], eax
0x18004cd7f  cmp     eax, r8d
0x18004cd82  jg      short loc_18004CDCD
0x18004cd84  mov     eax, r15d
0x18004cd87  and     eax, 1
0x18004cd8a  add     rbx, rax
0x18004cd8d  mov     eax, [rsp+48h+arg_38]
0x18004cd94  test    eax, eax
0x18004cd96  jz      loc_18004CE56
0x18004cd9c  movsxd  r8, r10d
0x18004cd9f  dec     eax
0x18004cda1  cmp     [rsp+48h+arg_40], 4
0x18004cda9  jnz     short loc_18004CDB3
0x18004cdab  mov     edx, [rdi]
0x18004cdad  add     rdi, 4
0x18004cdb1  jmp     short loc_18004CDBA
0x18004cdb3  movzx   edx, word ptr [rsi]
0x18004cdb6  add     rsi, 2
0x18004cdba  mov     ecx, r12d
0x18004cdbd  shl     dl, cl
0x18004cdbf  or      [rbx], dl
0x18004cdc1  add     rbx, r8
0x18004cdc4  test    eax, eax
0x18004cdc6  jnz     short loc_18004CD9F
0x18004cdc8  jmp     loc_18004CE56
0x18004cdcd  mov     r14d, [rsp+48h+arg_38]
0x18004cdd5  test    r14d, r14d
0x18004cdd8  jz      short loc_18004CE56
0x18004cdda  and     r15d, 1
0x18004cdde  movsxd  r13, r10d
0x18004cde1  dec     r14d
0x18004cde4  cmp     [rsp+48h+arg_40], 4
0x18004cdec  jnz     short loc_18004CDF6
0x18004cdee  mov     ebp, [rdi]
0x18004cdf0  add     rdi, 4
0x18004cdf4  jmp     short loc_18004CDFD
0x18004cdf6  movzx   ebp, word ptr [rsi]
0x18004cdf9  add     rsi, 2
0x18004cdfd  mov     ecx, r12d
0x18004ce00  cmp     eax, 10h
0x18004ce03  jg      short loc_18004CE25
0x18004ce05  movzx   eax, word ptr [rbx]
0x18004ce08  shl     bp, cl
0x18004ce0b  test    r15d, r15d
0x18004ce0e  jz      short loc_18004CE1D
0x18004ce10  ror     ax, 8
0x18004ce14  or      ax, bp
0x18004ce17  ror     ax, 8
0x18004ce1b  jmp     short loc_18004CE20
0x18004ce1d  or      ax, bp
0x18004ce20  mov     [rbx], ax
0x18004ce23  jmp     short loc_18004CE47
0x18004ce25  mov     eax, [rbx]
0x18004ce27  shl     ebp, cl
0x18004ce29  test    r15d, r15d
0x18004ce2c  jz      short loc_18004CE43
0x18004ce2e  lfence
0x18004ce31  mov     ecx, eax; Number
0x18004ce33  call    _byteswap_ulong
0x18004ce38  or      eax, ebp
0x18004ce3a  mov     ecx, eax; Number
0x18004ce3c  call    _byteswap_ulong
0x18004ce41  jmp     short loc_18004CE45
0x18004ce43  or      eax, ebp
0x18004ce45  mov     [rbx], eax
0x18004ce47  mov     eax, [rsp+48h+arg_30]
0x18004ce4e  add     rbx, r13
0x18004ce51  test    r14d, r14d
0x18004ce54  jnz     short loc_18004CDE1
0x18004ce56  mov     rbx, [rsp+48h+arg_0]
0x18004ce5b  mov     rbp, [rsp+48h+arg_8]
0x18004ce60  mov     rsi, [rsp+48h+arg_10]
0x18004ce65  add     rsp, 20h
0x18004ce69  pop     r15
0x18004ce6b  pop     r14
0x18004ce6d  pop     r13
0x18004ce6f  pop     r12
0x18004ce71  pop     rdi
0x18004ce72  retn
```
