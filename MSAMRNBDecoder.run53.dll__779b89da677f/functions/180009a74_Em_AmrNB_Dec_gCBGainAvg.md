# Em_AmrNB_Dec_gCBGainAvg

- ea: `0x180009a74`
- end: `0x180009e98`
- name: `Em_AmrNB_Dec_gCBGainAvg`
- size: `1060`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180003800`

## callees

- `0x180006764`
- `0x1800067ac`
- `0x18000688c`
- `0x180009a74`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gCBGainAvg(_WORD *a1, _WORD *a2, __int64 a3, __int64 a4)
{
  int v4; // r10d
  __int64 v6; // rcx
  __int16 v7; // r14
  __int16 v8; // r12
  __int64 i; // r15
  __int16 v10; // dx
  __int16 v11; // ax
  __int16 v12; // r8
  __int16 v13; // ax
  __int16 v14; // cx
  __int16 v15; // bp
  unsigned __int16 v16; // r8
  __int16 v17; // di
  __int16 v18; // cx
  __int16 v19; // ax
  __int16 v20; // cx
  __int16 v21; // ax
  int v22; // ecx
  int v23; // eax
  __int64 v24; // r9
  int v25; // esi
  __int16 v26; // r8
  __int16 v27; // r11
  __int16 v28; // dx
  __int16 v29; // ax
  __int16 v30; // dx
  __int64 v31; // r9
  int v32; // r8d
  int v33; // eax
  int v34; // edx
  int v35; // r8d
  int v36; // eax
  int v37; // r8d
  int v38; // ecx
  __int64 v39; // r8
  int v40; // ecx
  int v41; // eax
  unsigned int v42; // r9d
  unsigned int v43; // eax
  int v44; // eax
  int v45; // esi
  int v46; // eax
  __int64 result; // rax
  __int16 v48; // [rsp+20h] [rbp-58h]

  v4 = 0;
  v6 = 0;
  do
  {
    ++v4;
    a1[v6 + 544] = a1[v6 + 545];
    ++v6;
  }
  while ( v4 < 6 );
  v7 = 0x7FFF;
  a1[v4 + 544] = a2[652];
  v8 = 0;
  v48 = a2[652];
  for ( i = 0; i != 10; ++i )
  {
    v10 = *(_WORD *)(a4 + 2 * i);
    v11 = v10 - *(_WORD *)(a3 + 2 * i);
    if ( v11 == (__int16)0x8000 )
    {
      v12 = 0x7FFF;
LABEL_9:
      v13 = 0;
      goto LABEL_17;
    }
    v12 = *(_WORD *)(a3 + 2 * i) - v10;
    if ( v11 > 0 )
      v12 = v10 - *(_WORD *)(a3 + 2 * i);
    if ( !v12 )
      goto LABEL_9;
    if ( v12 == -1 )
    {
      v13 = 15;
    }
    else
    {
      v14 = v12;
      if ( v12 < 0 )
        v14 = ~v12;
      v13 = 0;
      while ( v14 < 0x4000 )
      {
        v14 *= 2;
        ++v13;
      }
    }
LABEL_17:
    v15 = v13 - 1;
    v16 = v12 << (v13 - 1);
    if ( v10 )
    {
      if ( v10 == -1 )
      {
        v17 = 15;
      }
      else
      {
        v18 = *(_WORD *)(a4 + 2 * i);
        if ( v10 < 0 )
          v18 = ~v10;
        v17 = 0;
        while ( v18 < 0x4000 )
        {
          v18 *= 2;
          ++v17;
        }
      }
    }
    else
    {
      v17 = 0;
    }
    v19 = Em_AmrNB_Dec_div_s(v16);
    v20 = v15 - v17 + 2;
    if ( v20 < 0 )
      v21 = v19 << -(char)v20;
    else
      v21 = v19 >> v20;
    v22 = v21 + v8;
    if ( v22 <= 0x7FFF )
    {
      if ( v22 < -32768 )
        LOWORD(v22) = 0x8000;
    }
    else
    {
      LOWORD(v22) = 0x7FFF;
    }
    v8 = v22;
  }
  if ( (__int16)v22 <= 5325 )
  {
    a1[234] = 0;
  }
  else
  {
    v23 = (__int16)a1[234] + 1;
    if ( v23 <= 0x7FFF )
    {
      if ( v23 < -32768 )
        LOWORD(v23) = 0x8000;
    }
    else
    {
      LOWORD(v23) = 0x7FFF;
    }
    a1[234] = v23;
    if ( (__int16)v23 > 10 )
      a1[235] = 0;
  }
  v24 = 3;
  LOWORD(v25) = v48;
  v26 = a2[653];
  if ( v26 <= 3 || v26 == 6 )
  {
    v27 = 0x2000;
    if ( v26 < 3 && a1[531] && (__int16)a1[532] > 1 && (a2[672] || a1[527] || a2[673] && a1[528]) )
      v28 = 4506;
    else
      v28 = 3277;
    v29 = v22 - v28;
    v30 = 0;
    if ( v29 >= 0 )
      v30 = v29;
    if ( v30 <= 2048 )
      v27 = 4 * v30;
    if ( (__int16)a1[235] < 40 || (__int16)v22 > 5325 )
      v27 = 0x2000;
    if ( v26 < 3 && a1[531] && (a2[672] || a1[527]) )
    {
      v31 = 1;
      v32 = 9362 * (__int16)a1[544];
      do
      {
        v33 = (__int16)a1[v31 + 544];
        v34 = 9362 * v33 + v32;
        if ( (v32 ^ (9362 * v33)) >= 0 && (v32 ^ v34) < 0 )
        {
          v34 = 0x7FFFFFFF;
          if ( v32 < 0 )
            v34 = 0x80000000;
        }
        ++v31;
        v32 = v34;
      }
      while ( v31 != 7 );
    }
    else
    {
      v35 = 13108 * (__int16)a1[546];
      do
      {
        v36 = (__int16)a1[v24 + 544];
        v34 = 13108 * v36 + v35;
        if ( (v35 ^ (13108 * v36)) >= 0 && (v35 ^ v34) < 0 )
        {
          v34 = 0x7FFFFFFF;
          if ( v35 < 0 )
            v34 = 0x80000000;
        }
        ++v24;
        v35 = v34;
      }
      while ( v24 != 7 );
    }
    v37 = v34 + 0x8000;
    if ( v34 >= 0 && (v34 ^ v37) < 0 )
      v37 = 0x7FFFFFFF;
    v38 = v48 * v27;
    v39 = (unsigned int)(v37 >> 16);
    if ( v38 == 0x40000000 )
      v40 = 0x7FFFFFFF;
    else
      v40 = 2 * v38;
    v41 = (__int16)v39 << 14;
    v42 = v41 + v40;
    if ( (v40 ^ v41) >= 0 && ((v40 ^ v42) & 0x80000000) != 0 )
    {
      v42 = 0x7FFFFFFF;
      if ( v40 < 0 )
        v42 = 0x80000000;
    }
    v43 = Em_AmrNB_Dec_L_msu(v42, (unsigned __int16)v27, v39);
    v44 = Em_AmrNB_Dec_L_shl(v43, 2);
    v45 = v44 + 0x8000;
    if ( v44 >= 0 && (v44 ^ v45) < 0 )
      v45 = 0x7FFFFFFF;
    v25 = v45 >> 16;
  }
  v46 = (__int16)a1[235] + 1;
  if ( v46 <= 0x7FFF )
  {
    v7 = 0x8000;
    if ( v46 >= -32768 )
      v7 = a1[235] + 1;
  }
  a1[235] = v7;
  result = 0;
  a2[652] = v25;
  return result;
}

```

## disassembly

```asm
0x180009a74  mov     rax, rsp
0x180009a77  mov     [rax+20h], r9
0x180009a7b  mov     [rax+18h], r8
0x180009a7f  mov     [rax+10h], rdx
0x180009a83  mov     [rax+8], rcx
0x180009a87  push    rbx
0x180009a88  push    rbp
0x180009a89  push    rsi
0x180009a8a  push    rdi
0x180009a8b  push    r12
0x180009a8d  push    r13
0x180009a8f  push    r14
0x180009a91  push    r15
0x180009a93  sub     rsp, 38h
0x180009a97  xor     r10d, r10d
0x180009a9a  mov     rbx, rcx
0x180009a9d  xor     ecx, ecx
0x180009a9f  lea     r9d, [r10+1]
0x180009aa3  movzx   eax, word ptr [rbx+rcx*2+442h]
0x180009aab  add     r10d, r9d
0x180009aae  mov     [rbx+rcx*2+440h], ax
0x180009ab6  add     rcx, r9
0x180009ab9  cmp     r10d, 6
0x180009abd  jl      short loc_180009AA3
0x180009abf  movzx   eax, word ptr [rdx+518h]
0x180009ac6  mov     r8d, 0FFFF8000h
0x180009acc  mov     r13, [rsp+78h+arg_10]
0x180009ad4  mov     r14d, 7FFFh
0x180009ada  movsxd  rcx, r10d
0x180009add  mov     r10d, 4000h
0x180009ae3  mov     [rbx+rcx*2+440h], ax
0x180009aeb  xor     ebx, ebx
0x180009aed  movzx   esi, word ptr [rdx+518h]
0x180009af4  mov     r12d, ebx
0x180009af7  mov     dword ptr [rsp+78h+var_58], esi
0x180009afb  mov     r15d, ebx
0x180009afe  mov     rsi, [rsp+78h+arg_18]
0x180009b06  lea     r11d, [rbx+0Fh]
0x180009b0a  movzx   edx, word ptr [rsi+r15*2]
0x180009b0f  movzx   eax, dx
0x180009b12  sub     ax, [r13+r15*2+0]
0x180009b18  cmp     ax, r8w
0x180009b1c  jnz     short loc_180009B24
0x180009b1e  movzx   r8d, r14w
0x180009b22  jmp     short loc_180009B37
0x180009b24  movzx   r8d, ax
0x180009b28  neg     r8w
0x180009b2c  cmovs   r8w, ax
0x180009b31  test    r8w, r8w
0x180009b35  jnz     short loc_180009B3B
0x180009b37  mov     eax, ebx
0x180009b39  jmp     short loc_180009B66
0x180009b3b  cmp     r8w, 0FFFFh
0x180009b40  jnz     short loc_180009B48
0x180009b42  movzx   eax, r11w
0x180009b46  jmp     short loc_180009B66
0x180009b48  movzx   ecx, r8w
0x180009b4c  test    r8w, r8w
0x180009b50  jns     short loc_180009B55
0x180009b52  not     cx
0x180009b55  mov     eax, ebx
0x180009b57  jmp     short loc_180009B60
0x180009b59  add     cx, cx
0x180009b5c  add     ax, r9w
0x180009b60  cmp     cx, r10w
0x180009b64  jl      short loc_180009B59
0x180009b66  sub     ax, r9w
0x180009b6a  movzx   ebp, ax
0x180009b6d  mov     ecx, ebp
0x180009b6f  shl     r8w, cl
0x180009b73  test    dx, dx
0x180009b76  jnz     short loc_180009B7C
0x180009b78  mov     edi, ebx
0x180009b7a  jmp     short loc_180009BA4
0x180009b7c  cmp     dx, 0FFFFh
0x180009b80  jnz     short loc_180009B88
0x180009b82  movzx   edi, r11w
0x180009b86  jmp     short loc_180009BA4
0x180009b88  movzx   ecx, dx
0x180009b8b  test    dx, dx
0x180009b8e  jns     short loc_180009B93
0x180009b90  not     cx
0x180009b93  mov     edi, ebx
0x180009b95  jmp     short loc_180009B9E
0x180009b97  add     cx, cx
0x180009b9a  add     di, r9w
0x180009b9e  cmp     cx, r10w
0x180009ba2  jl      short loc_180009B97
0x180009ba4  mov     cl, dil
0x180009ba7  shl     dx, cl
0x180009baa  movzx   ecx, r8w
0x180009bae  call    Em_AmrNB_Dec_div_s
0x180009bb3  mov     ecx, 2
0x180009bb8  sub     bp, di
0x180009bbb  add     cx, bp
0x180009bbe  js      short loc_180009BC5
0x180009bc0  sar     ax, cl
0x180009bc3  jmp     short loc_180009BCA
0x180009bc5  neg     ecx
0x180009bc7  shl     ax, cl
0x180009bca  movsx   ecx, r12w
0x180009bce  mov     r8d, 0FFFF8000h
0x180009bd4  cwde
0x180009bd5  add     ecx, eax
0x180009bd7  cmp     ecx, r14d
0x180009bda  jle     short loc_180009BE2
0x180009bdc  movzx   ecx, r14w
0x180009be0  jmp     short loc_180009BEA
0x180009be2  cmp     ecx, r8d
0x180009be5  jge     short loc_180009BEA
0x180009be7  mov     ecx, r8d
0x180009bea  mov     ebp, 0Ah
0x180009bef  inc     r15
0x180009bf2  movzx   r12d, cx
0x180009bf6  mov     r10d, 4000h
0x180009bfc  lea     r9d, [rbp-9]
0x180009c00  lea     r11d, [rbp+5]
0x180009c04  cmp     r15, rbp
0x180009c07  jnz     loc_180009B0A
0x180009c0d  mov     rbx, [rsp+78h+arg_0]
0x180009c15  mov     edi, 14CDh
0x180009c1a  cmp     cx, di
0x180009c1d  jle     short loc_180009C52
0x180009c1f  movsx   eax, word ptr [rbx+1D4h]
0x180009c26  inc     eax
0x180009c28  cmp     eax, r14d
0x180009c2b  jle     short loc_180009C33
0x180009c2d  movzx   eax, r14w
0x180009c31  jmp     short loc_180009C3B
0x180009c33  cmp     eax, r8d
0x180009c36  jge     short loc_180009C3B
0x180009c38  mov     eax, r8d
0x180009c3b  mov     [rbx+1D4h], ax
0x180009c42  cmp     ax, bp
0x180009c45  jle     short loc_180009C5D
0x180009c47  xor     ebp, ebp
0x180009c49  mov     [rbx+1D6h], bp
0x180009c50  jmp     short loc_180009C5F
0x180009c52  xor     ebp, ebp
0x180009c54  mov     [rbx+1D4h], bp
0x180009c5b  jmp     short loc_180009C5F
0x180009c5d  xor     ebp, ebp
0x180009c5f  mov     r13, [rsp+78h+arg_8]
0x180009c67  mov     r9d, 3
0x180009c6d  mov     esi, dword ptr [rsp+78h+var_58]
0x180009c71  movzx   r8d, word ptr [r13+51Ah]
0x180009c79  cmp     r8w, r9w
0x180009c7d  jle     short loc_180009C8D
0x180009c7f  lea     eax, [r9+3]
0x180009c83  cmp     r8w, ax
0x180009c87  jnz     loc_180009E58
0x180009c8d  mov     r10d, 2000h
0x180009c93  mov     r15d, 1
0x180009c99  movzx   r11d, r10w
0x180009c9d  cmp     r8w, r9w
0x180009ca1  jge     short loc_180009CE3
0x180009ca3  cmp     [rbx+426h], bp
0x180009caa  jz      short loc_180009CE3
0x180009cac  cmp     [rbx+428h], r15w
0x180009cb4  jle     short loc_180009CE3
0x180009cb6  cmp     [r13+540h], bp
0x180009cbe  jnz     short loc_180009CDC
0x180009cc0  cmp     [rbx+41Eh], bp
0x180009cc7  jnz     short loc_180009CDC
0x180009cc9  cmp     [r13+542h], bp
0x180009cd1  jz      short loc_180009CE3
0x180009cd3  cmp     [rbx+420h], bp
0x180009cda  jz      short loc_180009CE3
0x180009cdc  mov     edx, 119Ah
0x180009ce1  jmp     short loc_180009CE8
0x180009ce3  mov     edx, 0CCDh
0x180009ce8  movzx   eax, cx
0x180009ceb  sub     ax, dx
0x180009cee  mov     edx, ebp
0x180009cf0  test    ax, ax
0x180009cf3  cmovns  dx, ax
0x180009cf7  mov     eax, 800h
0x180009cfc  cmp     ax, dx
0x180009cff  jl      short loc_180009D0A
0x180009d01  movzx   r11d, dx
0x180009d05  shl     r11w, 2
0x180009d0a  cmp     word ptr [rbx+1D6h], 28h ; '('
0x180009d12  jl      short loc_180009D19
0x180009d14  cmp     cx, di
0x180009d17  jle     short loc_180009D1C
0x180009d19  mov     r11d, r10d
0x180009d1c  cmp     r8w, r9w
0x180009d20  jge     short loc_180009D90
0x180009d22  cmp     [rbx+426h], bp
0x180009d29  jz      short loc_180009D90
0x180009d2b  cmp     [r13+540h], bp
0x180009d33  jnz     short loc_180009D3E
0x180009d35  cmp     [rbx+41Eh], bp
0x180009d3c  jz      short loc_180009D90
0x180009d3e  movsx   eax, word ptr [rbx+440h]
0x180009d45  mov     r9, r15
0x180009d48  imul    r8d, eax, 2492h
0x180009d4f  mov     edi, 7FFFFFFFh
0x180009d54  mov     r10d, 80000000h
0x180009d5a  movsx   eax, word ptr [rbx+r9*2+440h]
0x180009d63  imul    ecx, eax, 2492h
0x180009d69  lea     edx, [rcx+r8]
0x180009d6d  xor     ecx, r8d
0x180009d70  jl      short loc_180009D82
0x180009d72  mov     eax, edx
0x180009d74  xor     eax, r8d
0x180009d77  jge     short loc_180009D82
0x180009d79  test    r8d, r8d
0x180009d7c  mov     edx, edi
0x180009d7e  cmovs   edx, r10d
0x180009d82  add     r9, r15
0x180009d85  mov     r8d, edx
0x180009d88  cmp     r9, 7
0x180009d8c  jnz     short loc_180009D5A
0x180009d8e  jmp     short loc_180009DDD
0x180009d90  movsx   eax, word ptr [rbx+444h]
0x180009d97  mov     edi, 7FFFFFFFh
0x180009d9c  imul    r8d, eax, 3334h
0x180009da3  mov     r10d, 80000000h
0x180009da9  movsx   eax, word ptr [rbx+r9*2+440h]
0x180009db2  imul    ecx, eax, 3334h
0x180009db8  lea     edx, [rcx+r8]
0x180009dbc  xor     ecx, r8d
0x180009dbf  jl      short loc_180009DD1
0x180009dc1  mov     eax, edx
0x180009dc3  xor     eax, r8d
0x180009dc6  jge     short loc_180009DD1
0x180009dc8  test    r8d, r8d
0x180009dcb  mov     edx, edi
0x180009dcd  cmovs   edx, r10d
0x180009dd1  add     r9, r15
0x180009dd4  mov     r8d, edx
0x180009dd7  cmp     r9, 7
0x180009ddb  jnz     short loc_180009DA9
0x180009ddd  lea     r8d, [rdx+8000h]
0x180009de4  test    edx, edx
0x180009de6  js      short loc_180009DF1
0x180009de8  mov     eax, r8d
0x180009deb  xor     eax, edx
0x180009ded  cmovl   r8d, edi
0x180009df1  movsx   ecx, r11w
0x180009df5  movsx   eax, si
0x180009df8  imul    ecx, eax
0x180009dfb  sar     r8d, 10h
0x180009dff  cmp     ecx, 40000000h
0x180009e05  jz      short loc_180009E0B
0x180009e07  add     ecx, ecx
0x180009e09  jmp     short loc_180009E0D
0x180009e0b  mov     ecx, edi
0x180009e0d  movsx   eax, r8w
0x180009e11  shl     eax, 0Eh
0x180009e14  lea     r9d, [rax+rcx]
0x180009e18  xor     eax, ecx
0x180009e1a  jl      short loc_180009E2C
0x180009e1c  mov     eax, r9d
0x180009e1f  xor     eax, ecx
0x180009e21  jge     short loc_180009E2C
0x180009e23  test    ecx, ecx
0x180009e25  mov     r9d, edi
0x180009e28  cmovs   r9d, r10d
0x180009e2c  movzx   edx, r11w
0x180009e30  mov     ecx, r9d
0x180009e33  call    Em_AmrNB_Dec_L_msu
0x180009e38  mov     ecx, eax
0x180009e3a  mov     edx, 2
0x180009e3f  call    Em_AmrNB_Dec_L_shl
0x180009e44  lea     esi, [rax+8000h]
0x180009e4a  test    eax, eax
0x180009e4c  js      short loc_180009E55
0x180009e4e  mov     ecx, esi
0x180009e50  xor     ecx, eax
0x180009e52  cmovl   esi, edi
0x180009e55  sar     esi, 10h
0x180009e58  movsx   eax, word ptr [rbx+1D6h]
0x180009e5f  inc     eax
0x180009e61  cmp     eax, r14d
0x180009e64  jg      short loc_180009E75
0x180009e66  mov     r14d, 0FFFF8000h
0x180009e6c  cmp     eax, r14d
0x180009e6f  jl      short loc_180009E75
0x180009e71  movzx   r14d, ax
0x180009e75  mov     [rbx+1D6h], r14w
0x180009e7d  xor     eax, eax
0x180009e7f  mov     [r13+518h], si
0x180009e87  add     rsp, 38h
0x180009e8b  pop     r15
0x180009e8d  pop     r14
0x180009e8f  pop     r13
0x180009e91  pop     r12
0x180009e93  pop     rdi
0x180009e94  pop     rsi
0x180009e95  pop     rbp
0x180009e96  pop     rbx
0x180009e97  retn
```
