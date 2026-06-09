# Em_AmrNB_Dec_gPostFilt

- ea: `0x180004dd0`
- end: `0x1800051d8`
- name: `Em_AmrNB_Dec_gPostFilt`
- size: `1032`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180003800`

## callees

- `0x180001400`
- `0x1800019b0`
- `0x180004d84`
- `0x180004dd0`
- `0x18000671c`
- `0x180006764`
- `0x1800067ac`
- `0x18000688c`
- `0x18000694c`
- `0x180006eb4`
- `0x180007b6c`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gPostFilt(__int64 a1, __int64 a2, __int64 a3, int a4, __int64 a5)
{
  int v5; // eax
  __int64 v6; // rbx
  int v7; // r12d
  __int64 v8; // rdx
  unsigned __int16 v9; // r11
  __int64 v10; // rcx
  int v11; // r15d
  __int64 v12; // r13
  __int64 v13; // rbx
  int v14; // eax
  unsigned int v15; // r14d
  int v16; // eax
  unsigned int v17; // esi
  int v18; // r11d
  unsigned __int16 v19; // di
  __int64 v20; // r10
  unsigned int v21; // eax
  int v22; // r11d
  int v23; // eax
  int v24; // edx
  int v25; // eax
  int v26; // edx
  __int64 v27; // rcx
  __int16 v28; // r14
  char *v29; // rdi
  int i; // ecx
  unsigned __int64 v31; // rdx
  int j; // ebx
  __int64 v33; // rsi
  int v34; // ecx
  __int64 v35; // rcx
  int k; // edi
  unsigned int v37; // eax
  int v38; // eax
  int v39; // edx
  int v40; // edx
  int v41; // r9d
  __int64 v42; // rax
  __int64 v43; // rdi
  int v44; // r9d
  int v45; // edi
  int v46; // edx
  int v47; // ecx
  unsigned __int16 v48; // ax
  unsigned __int16 v49; // r10
  __int64 v50; // rdi
  int v51; // edx
  __int64 v52; // r9
  int v53; // eax
  int v54; // r11d
  int v56; // [rsp+20h] [rbp-E0h]
  int v57; // [rsp+30h] [rbp-D0h]
  __int64 v61; // [rsp+48h] [rbp-B8h]
  __int64 v62; // [rsp+58h] [rbp-A8h]
  _WORD v63[56]; // [rsp+60h] [rbp-A0h]
  _WORD v64[40]; // [rsp+D0h] [rbp-30h] BYREF
  _WORD v65[12]; // [rsp+120h] [rbp+20h] BYREF
  _WORD v66[23]; // [rsp+138h] [rbp+38h] BYREF
  char v67; // [rsp+166h] [rbp+66h] BYREF

  v5 = a4;
  v6 = a2;
  LOWORD(v7) = 0;
  v62 = a3;
  v57 = 0;
  do
  {
    if ( (unsigned int)(v5 - 6) <= 1 )
      v8 = 22938;
    else
      v8 = 18022;
    Em_AmrNB_Dec_WeightLpc(a3 + 22LL * (unsigned __int16)v7, v8, v65);
    Em_AmrNB_Dec_WeightLpc(v10, v9, v66);
    v11 = 0;
    v61 = 40 * (unsigned int)(unsigned __int16)v7;
    v12 = v6 + 2 * v61;
    v13 = 0;
    do
    {
      v14 = v65[0] * *(__int16 *)(v12 + 2 * v13);
      v15 = 2 * v14;
      if ( v14 == 0x40000000 )
        v15 = 0x7FFFFFFF;
      v16 = v65[0] * *(__int16 *)(v12 + 2 * v13 + 2);
      v17 = 2 * v16;
      if ( v16 == 0x40000000 )
        v17 = 0x7FFFFFFF;
      v18 = 1;
      do
      {
        v19 = v65[v18];
        v15 = Em_AmrNB_Dec_L_mac(
                v15,
                v19,
                *(unsigned __int16 *)(v12 + 2 * ((unsigned int)v11 - (unsigned __int64)(unsigned int)v18)));
        v21 = Em_AmrNB_Dec_L_mac(v17, v19, *(unsigned __int16 *)(v12 + 2 * v20 + 2));
        v18 = v22 + 1;
        v17 = v21;
      }
      while ( v18 <= 10 );
      v23 = Em_AmrNB_Dec_L_shl(v15, 3);
      v24 = v23 + 0x8000;
      if ( v23 >= 0 && (v23 ^ v24) < 0 )
        HIWORD(v24) = 0x7FFF;
      v64[v13] = HIWORD(v24);
      v25 = Em_AmrNB_Dec_L_shl(v17, 3);
      v26 = v25 + 0x8000;
      if ( v25 >= 0 && (v25 ^ v26) < 0 )
        HIWORD(v26) = 0x7FFF;
      v11 += 2;
      v64[v13 + 1] = HIWORD(v26);
      v13 += 2;
    }
    while ( v11 < 40 );
    v27 = 0;
    v28 = v64[39];
    do
    {
      v66[v27 + 12] = v65[v27];
      ++v27;
    }
    while ( v27 != 11 );
    v29 = &v67;
    while ( v27 )
    {
      *(_WORD *)v29 = 0;
      v29 += 2;
      --v27;
    }
    for ( i = 0; i < 10; ++i )
    {
      v31 = (unsigned int)i;
      if ( v31 >= 50 )
        _report_rangecheckfailure();
      v63[v31] = 0;
    }
    for ( j = 0; j < 22; ++j )
    {
      v33 = (unsigned int)j;
      v34 = v66[0] * (__int16)v66[j + 12];
      if ( v34 == 0x40000000 )
        v35 = 0x7FFFFFFF;
      else
        v35 = (unsigned int)(2 * v34);
      for ( k = 1; k <= 10; ++k )
      {
        v37 = Em_AmrNB_Dec_L_msu(
                v35,
                (unsigned __int16)v66[k],
                (unsigned __int16)v63[(unsigned int)j - (unsigned __int64)(unsigned int)k + 10]);
        v35 = v37;
      }
      v38 = Em_AmrNB_Dec_L_shl(v37, 3);
      v39 = v38 + 0x8000;
      if ( v38 >= 0 && (v38 ^ v39) < 0 )
        v39 = 0x7FFFFFFF;
      v40 = v39 >> 16;
      v66[v33 + 12] = v40;
      v63[v33 + 10] = v40;
    }
    HIWORD(v7) = HIWORD(v57);
    v41 = 0;
    v42 = 0;
    do
    {
      v43 = v42 + 1;
      v41 = Em_AmrNB_Dec_L_mac((unsigned int)v41, (unsigned __int16)v66[v42 + 12], (unsigned __int16)v66[v42 + 13]);
      v42 = v43;
    }
    while ( v43 != 21 );
    v44 = v41 >> 16;
    if ( (__int16)v44 > 0 )
    {
      v45 = 0;
      v46 = 0;
      while ( 1 )
      {
        v47 = (__int16)v66[v46 + 12];
        v45 += 2 * v47 * v47;
        if ( v45 < 0 )
          break;
        if ( ++v46 >= 22 )
          goto LABEL_45;
      }
      HIWORD(v45) = 0x7FFF;
LABEL_45:
      if ( HIWORD(v45) )
      {
        v48 = Em_AmrNB_Dec_mult((unsigned __int16)v44);
        v49 = Em_AmrNB_Dec_div_s(v48);
        v50 = 39;
        do
        {
          v51 = (__int16)v64[v50] - (__int16)Em_AmrNB_Dec_mult(v49);
          if ( v51 <= 0x7FFF )
          {
            if ( v51 < -32768 )
              LOWORD(v51) = 0x8000;
          }
          else
          {
            LOWORD(v51) = 0x7FFF;
          }
          v64[v50] = v51;
          v50 = v52;
        }
        while ( v52 );
        v53 = v64[0] - (__int16)Em_AmrNB_Dec_mult(v49);
        if ( v53 <= 0x7FFF )
        {
          if ( v53 < v54 )
            LOWORD(v53) = v54;
        }
        else
        {
          LOWORD(v53) = 0x7FFF;
        }
        v64[0] = v53;
      }
    }
    Em_AmrNB_Dec_gIIRFilter((unsigned int)v66, (unsigned int)v64, a1 + 40, v44, v56, a5 + 2 * v61);
    Em_AmrNB_Dec_gAgc(a1, a2 + 2 * v61, a5 + 2 * v61, 4294967256LL);
    v5 = a4;
    LOWORD(v7) = v57 + 1;
    a3 = v62;
    v6 = a2;
    *(_WORD *)(a1 + 464) = v28;
    v57 = v7;
  }
  while ( (__int16)v7 < 4 );
  return 0;
}

```

## disassembly

```asm
0x180004dd0  mov     [rsp-8+arg_18], rbx
0x180004dd5  push    rbp
0x180004dd6  push    rsi
0x180004dd7  push    rdi
0x180004dd8  push    r12
0x180004dda  push    r13
0x180004ddc  push    r14
0x180004dde  push    r15
0x180004de0  lea     rbp, [rsp-90h]
0x180004de8  sub     rsp, 190h
0x180004def  mov     rax, cs:__security_cookie
0x180004df6  xor     rax, rsp
0x180004df9  mov     [rbp+0C0h+var_40], rax
0x180004e00  xor     esi, esi
0x180004e02  mov     [rsp+1C0h+var_180], rcx
0x180004e07  mov     rcx, [rbp+0C0h+arg_20]
0x180004e0e  mov     eax, r9d
0x180004e11  mov     [rsp+1C0h+var_170], rcx
0x180004e16  mov     rbx, rdx
0x180004e19  mov     [rsp+1C0h+var_18C], eax
0x180004e1d  mov     r12d, esi
0x180004e20  lea     r15d, [rsi+1]
0x180004e24  mov     [rsp+1C0h+var_168], r8
0x180004e29  mov     [rsp+1C0h+var_188], rdx
0x180004e2e  mov     ecx, 599Ah
0x180004e33  mov     [rsp+1C0h+var_190], esi
0x180004e37  add     eax, 0FFFFFFFAh
0x180004e3a  cmp     eax, r15d
0x180004e3d  movzx   eax, r12w
0x180004e41  jbe     short loc_180004E4E
0x180004e43  movzx   r11d, cx
0x180004e47  mov     edx, 4666h
0x180004e4c  jmp     short loc_180004E57
0x180004e4e  mov     r11d, 6000h
0x180004e54  movzx   edx, cx
0x180004e57  movzx   edi, ax
0x180004e5a  imul    eax, edi, 0Bh
0x180004e5d  lea     rcx, [r8+rax*2]
0x180004e61  lea     r8, [rbp+0C0h+var_A0]
0x180004e65  call    Em_AmrNB_Dec_WeightLpc
0x180004e6a  movzx   edx, r11w
0x180004e6e  lea     r8, [rbp+0C0h+var_88]
0x180004e72  call    Em_AmrNB_Dec_WeightLpc
0x180004e77  lea     ecx, [rdi+rdi*4]
0x180004e7a  mov     r15d, esi
0x180004e7d  shl     ecx, 3
0x180004e80  mov     r12d, 7FFFFFFFh
0x180004e86  mov     eax, ecx
0x180004e88  mov     [rsp+1C0h+var_178], rax
0x180004e8d  lea     r13, [rbx+rcx*2]
0x180004e91  mov     rbx, rsi
0x180004e94  movsx   ecx, [rbp+0C0h+var_A0]
0x180004e98  movsx   eax, word ptr [r13+rbx*2+0]
0x180004e9e  imul    eax, ecx
0x180004ea1  lea     r14d, [rax+rax]
0x180004ea5  cmp     eax, 40000000h
0x180004eaa  jnz     short loc_180004EAF
0x180004eac  mov     r14d, r12d
0x180004eaf  movsx   eax, word ptr [r13+rbx*2+2]
0x180004eb5  imul    eax, ecx
0x180004eb8  lea     esi, [rax+rax]
0x180004ebb  cmp     eax, 40000000h
0x180004ec0  jnz     short loc_180004EC5
0x180004ec2  mov     esi, r12d
0x180004ec5  mov     r11d, 1
0x180004ecb  mov     eax, r11d
0x180004ece  mov     ecx, r14d
0x180004ed1  mov     r10d, r15d
0x180004ed4  sub     r10, rax
0x180004ed7  mov     eax, r11d
0x180004eda  movzx   edi, [rbp+rax*2+0C0h+var_A0]
0x180004edf  movzx   r8d, word ptr [r13+r10*2+0]
0x180004ee5  movzx   edx, di
0x180004ee8  call    Em_AmrNB_Dec_L_mac
0x180004eed  movzx   r8d, word ptr [r13+r10*2+2]
0x180004ef3  movzx   edx, di
0x180004ef6  mov     ecx, esi
0x180004ef8  mov     r14d, eax
0x180004efb  call    Em_AmrNB_Dec_L_mac
0x180004f00  inc     r11d
0x180004f03  mov     esi, eax
0x180004f05  cmp     r11d, 0Ah
0x180004f09  jle     short loc_180004ECB
0x180004f0b  mov     edi, 3
0x180004f10  mov     ecx, r14d
0x180004f13  mov     edx, edi
0x180004f15  call    Em_AmrNB_Dec_L_shl
0x180004f1a  lea     edx, [rax+8000h]
0x180004f20  test    eax, eax
0x180004f22  js      short loc_180004F2C
0x180004f24  mov     ecx, edx
0x180004f26  xor     ecx, eax
0x180004f28  cmovl   edx, r12d
0x180004f2c  sar     edx, 10h
0x180004f2f  mov     ecx, esi
0x180004f31  mov     [rbp+rbx*2+0C0h+var_F0], dx
0x180004f36  mov     edx, edi
0x180004f38  call    Em_AmrNB_Dec_L_shl
0x180004f3d  xor     esi, esi
0x180004f3f  lea     edx, [rax+8000h]
0x180004f45  test    eax, eax
0x180004f47  js      short loc_180004F51
0x180004f49  mov     ecx, edx
0x180004f4b  xor     ecx, eax
0x180004f4d  cmovl   edx, r12d
0x180004f51  sar     edx, 10h
0x180004f54  add     r15d, 2
0x180004f58  mov     [rbp+rbx*2+0C0h+var_EE], dx
0x180004f5d  add     rbx, 2
0x180004f61  cmp     r15d, 28h ; '('
0x180004f65  jl      loc_180004E94
0x180004f6b  mov     r13, [rsp+1C0h+var_180]
0x180004f70  mov     rcx, rsi
0x180004f73  movzx   r14d, [rbp+0C0h+var_A2]
0x180004f78  mov     r15d, 1
0x180004f7e  movzx   eax, [rbp+rcx*2+0C0h+var_A0]
0x180004f83  mov     [rbp+rcx*2+0C0h+var_70], ax
0x180004f88  add     rcx, r15
0x180004f8b  cmp     rcx, 0Bh
0x180004f8f  jnz     short loc_180004F7E
0x180004f91  movsxd  rax, esi
0x180004f94  lea     rdi, [rbp+0C0h+var_5A]
0x180004f98  movsx   rax, ax
0x180004f9c  rep stosw
0x180004f9f  mov     ecx, esi
0x180004fa1  mov     eax, ecx
0x180004fa3  lea     rdx, [rax+rax]
0x180004fa7  cmp     rdx, 64h ; 'd'
0x180004fab  jnb     loc_1800051D2
0x180004fb1  add     ecx, r15d
0x180004fb4  mov     [rsp+rdx+1C0h+var_160], si
0x180004fb9  cmp     ecx, 0Ah
0x180004fbc  jl      short loc_180004FA1
0x180004fbe  mov     ebx, esi
0x180004fc0  movsx   eax, [rbp+0C0h+var_88]
0x180004fc4  mov     esi, ebx
0x180004fc6  movsx   ecx, [rbp+rsi*2+0C0h+var_70]
0x180004fcb  imul    ecx, eax
0x180004fce  cmp     ecx, 40000000h
0x180004fd4  jz      short loc_180004FDA
0x180004fd6  add     ecx, ecx
0x180004fd8  jmp     short loc_180004FDD
0x180004fda  mov     ecx, r12d
0x180004fdd  mov     edi, r15d
0x180004fe0  mov     eax, edi
0x180004fe2  mov     r8, rsi
0x180004fe5  sub     r8, rax
0x180004fe8  mov     edx, edi
0x180004fea  movzx   r8d, [rsp+r8*2+1C0h+var_14C]
0x180004ff0  movzx   edx, [rbp+rdx*2+0C0h+var_88]
0x180004ff5  call    Em_AmrNB_Dec_L_msu
0x180004ffa  add     edi, r15d
0x180004ffd  mov     ecx, eax
0x180004fff  cmp     edi, 0Ah
0x180005002  jle     short loc_180004FE0
0x180005004  mov     edx, 3
0x180005009  call    Em_AmrNB_Dec_L_shl
0x18000500e  lea     edx, [rax+8000h]
0x180005014  test    eax, eax
0x180005016  js      short loc_180005020
0x180005018  mov     ecx, edx
0x18000501a  xor     ecx, eax
0x18000501c  cmovl   edx, r12d
0x180005020  sar     edx, 10h
0x180005023  add     ebx, r15d
0x180005026  mov     [rbp+rsi*2+0C0h+var_70], dx
0x18000502b  mov     [rsp+rsi*2+1C0h+var_14C], dx
0x180005030  cmp     ebx, 16h
0x180005033  jl      short loc_180004FC0
0x180005035  mov     r12d, [rsp+1C0h+var_190]
0x18000503a  xor     esi, esi
0x18000503c  mov     r9d, esi
0x18000503f  mov     eax, esi
0x180005041  movzx   edx, [rbp+rax*2+0C0h+var_70]
0x180005046  lea     rdi, [rax+1]
0x18000504a  movzx   r8d, [rbp+rdi*2+0C0h+var_70]
0x180005050  mov     ecx, r9d
0x180005053  call    Em_AmrNB_Dec_L_mac
0x180005058  mov     r9d, eax
0x18000505b  mov     rax, rdi
0x18000505e  cmp     rdi, 15h
0x180005062  jnz     short loc_180005041
0x180005064  sar     r9d, 10h
0x180005068  test    r9w, r9w
0x18000506c  jle     loc_180005139
0x180005072  mov     edi, esi
0x180005074  mov     edx, esi
0x180005076  mov     eax, edx
0x180005078  movsx   ecx, [rbp+rax*2+0C0h+var_70]
0x18000507d  imul    ecx, ecx
0x180005080  lea     edi, [rdi+rcx*2]
0x180005083  test    edi, edi
0x180005085  js      short loc_180005091
0x180005087  add     edx, r15d
0x18000508a  cmp     edx, 16h
0x18000508d  jl      short loc_180005076
0x18000508f  jmp     short loc_180005096
0x180005091  mov     edi, 7FFFFFFFh
0x180005096  shr     edi, 10h
0x180005099  test    di, di
0x18000509c  jz      loc_180005139
0x1800050a2  mov     edx, 6666h
0x1800050a7  movzx   ecx, r9w
0x1800050ab  call    Em_AmrNB_Dec_mult
0x1800050b0  movzx   ecx, ax
0x1800050b3  movzx   edx, di
0x1800050b6  call    Em_AmrNB_Dec_div_s
0x1800050bb  movzx   r10d, ax
0x1800050bf  mov     edi, 27h ; '''
0x1800050c4  mov     ebx, 7FFFh
0x1800050c9  lea     r9, [rdi-1]
0x1800050cd  movzx   ecx, r10w
0x1800050d1  movzx   edx, [rbp+r9*2+0C0h+var_F0]
0x1800050d7  call    Em_AmrNB_Dec_mult
0x1800050dc  movsx   edx, [rbp+rdi*2+0C0h+var_F0]
0x1800050e1  mov     r11d, 0FFFF8000h
0x1800050e7  movsx   ecx, ax
0x1800050ea  sub     edx, ecx
0x1800050ec  cmp     edx, ebx
0x1800050ee  jle     short loc_1800050F5
0x1800050f0  movzx   edx, bx
0x1800050f3  jmp     short loc_1800050FD
0x1800050f5  cmp     edx, r11d
0x1800050f8  jge     short loc_1800050FD
0x1800050fa  mov     edx, r11d
0x1800050fd  mov     [rbp+rdi*2+0C0h+var_F0], dx
0x180005102  mov     rdi, r9
0x180005105  test    r9, r9
0x180005108  jnz     short loc_1800050C9
0x18000510a  movzx   edx, word ptr [r13+1D0h]
0x180005112  movzx   ecx, r10w
0x180005116  call    Em_AmrNB_Dec_mult
0x18000511b  movsx   ecx, ax
0x18000511e  movsx   eax, [rbp+0C0h+var_F0]
0x180005122  sub     eax, ecx
0x180005124  cmp     eax, ebx
0x180005126  jle     short loc_18000512D
0x180005128  movzx   eax, bx
0x18000512b  jmp     short loc_180005135
0x18000512d  cmp     eax, r11d
0x180005130  jge     short loc_180005135
0x180005132  mov     eax, r11d
0x180005135  mov     [rbp+0C0h+var_F0], ax
0x180005139  mov     rax, [rsp+1C0h+var_170]
0x18000513e  lea     r8, [r13+28h]
0x180005142  mov     rbx, [rsp+1C0h+var_178]
0x180005147  lea     rdx, [rbp+0C0h+var_F0]
0x18000514b  lea     rcx, [rbp+0C0h+var_88]
0x18000514f  lea     rdi, [rax+rbx*2]
0x180005153  mov     [rsp+1C0h+var_198], rdi
0x180005158  call    Em_AmrNB_Dec_gIIRFilter
0x18000515d  mov     rax, [rsp+1C0h+var_188]
0x180005162  mov     r9d, 0FFFFFFD8h
0x180005168  mov     r8, rdi
0x18000516b  mov     rcx, r13
0x18000516e  lea     rdx, [rax+rbx*2]
0x180005172  call    Em_AmrNB_Dec_gAgc
0x180005177  mov     eax, [rsp+1C0h+var_18C]
0x18000517b  add     r12w, r15w
0x18000517f  mov     r8, [rsp+1C0h+var_168]
0x180005184  mov     ecx, 599Ah
0x180005189  mov     rbx, [rsp+1C0h+var_188]
0x18000518e  mov     [r13+1D0h], r14w
0x180005196  mov     [rsp+1C0h+var_190], r12d
0x18000519b  cmp     r12w, 4
0x1800051a0  jl      loc_180004E37
0x1800051a6  xor     eax, eax
0x1800051a8  mov     rcx, [rbp+0C0h+var_40]
0x1800051af  xor     rcx, rsp; StackCookie
0x1800051b2  call    __security_check_cookie
0x1800051b7  mov     rbx, [rsp+1C0h+arg_18]
0x1800051bf  add     rsp, 190h
0x1800051c6  pop     r15
0x1800051c8  pop     r14
0x1800051ca  pop     r13
0x1800051cc  pop     r12
0x1800051ce  pop     rdi
0x1800051cf  pop     rsi
0x1800051d0  pop     rbp
0x1800051d1  retn
0x1800051d2  call    __report_rangecheckfailure
```
