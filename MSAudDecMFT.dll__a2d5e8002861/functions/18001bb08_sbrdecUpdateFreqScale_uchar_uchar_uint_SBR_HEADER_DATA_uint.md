# sbrdecUpdateFreqScale(uchar *,uchar *,uint,SBR_HEADER_DATA *,uint)

- ea: `0x18001bb08`
- end: `0x18001be7b`
- name: `?sbrdecUpdateFreqScale@@YA?AW4SBR_ERROR@@PEAE0IPEAUSBR_HEADER_DATA@@I@Z`
- size: `883`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `installer_update`

## callers

- `0x18001b960`

## callees

- `0x18001bb08`
- `0x18001bf80`
- `0x180037e64`
- `0x180047f8c`
- `0x18004d320`
- `0x18004dd14`
- `0x180082078`
- `0x1800820ac`
- `0x180082204`
- `0x180082264`

## pseudocode

```c
__int64 __fastcall sbrdecUpdateFreqScale(__int64 a1, unsigned __int8 *a2, unsigned int a3, _BYTE *a4, unsigned int a5)
{
  unsigned int v5; // ebx
  __int64 v6; // r13
  unsigned __int8 StartBand; // al
  __int64 v9; // rdx
  __int64 v10; // r9
  unsigned int v11; // r14d
  unsigned __int8 StopBand; // al
  unsigned int v13; // r12d
  __int64 v15; // rcx
  unsigned int v16; // r15d
  char v17; // r13
  unsigned __int8 v18; // bl
  __int64 v19; // rcx
  __int64 v20; // rdx
  unsigned __int8 v21; // si
  __int64 v22; // r8
  __int64 v23; // r9
  __int64 v24; // rcx
  __int64 v25; // r8
  __int64 v26; // r8
  __int64 v27; // r9
  __int64 v28; // rdx
  __int64 v29; // r8
  __int64 v30; // r14
  __int64 v31; // rcx
  unsigned __int8 *v32; // rdx
  unsigned __int8 v33; // bl
  __int64 v34; // r9
  unsigned __int8 v35; // al
  __int64 v36; // rdx
  __int64 v37; // r8
  __int64 v38; // r9
  int v39; // ebx
  char v40; // al
  float v41; // xmm0_4
  float v42; // xmm0_4
  int v43; // edx
  unsigned __int8 v44; // si
  unsigned __int8 v45; // r12
  int v46; // ebx
  __int64 v47; // rcx
  int v48; // edx
  __int64 v49; // r8
  __int64 v50; // rax
  int i; // r8d
  unsigned __int8 *v54; // [rsp+30h] [rbp-79h]
  unsigned __int8 v56[29]; // [rsp+48h] [rbp-61h] BYREF
  unsigned __int8 v57[51]; // [rsp+65h] [rbp-44h] BYREF

  v5 = a3 >> 1;
  v54 = a2;
  v6 = a1;
  if ( (a5 & 0x80) == 0 )
    v5 = a3;
  LOBYTE(a2) = a4[16];
  StartBand = getStartBand(v5, a2, a5);
  v11 = StartBand;
  if ( StartBand == 0xFF )
    return 6;
  LOBYTE(v10) = StartBand;
  LOBYTE(v9) = a4[17];
  StopBand = getStopBand(v5, v9, a5, v10);
  v13 = StopBand;
  if ( StopBand == 0xFF )
    return 6;
  if ( !a4[18] )
  {
    v16 = v11;
    v39 = StopBand;
    v40 = a4[19];
    v41 = (float)(int)(v13 - v11);
    if ( v40 )
      v42 = (float)(v41 * 0.25) + 0.5;
    else
      v42 = v41 * 0.5;
    v43 = (v40 != 0) + 1;
    v44 = 2 * (int)v42;
    if ( !v44 )
      return 6;
    v45 = 0;
    v46 = v39 - v43 * v44 - v11;
    memset_0(v56, v43, v44);
    do
      ++v45;
    while ( v45 < v44 );
    v47 = 0;
    if ( v46 >= 0 )
      v47 = v45;
    if ( v46 <= 0 )
    {
      v48 = (unsigned int)v46 >> 31;
      v49 = (unsigned int)v46 >> 31;
      if ( !v46 )
      {
LABEL_30:
        LOBYTE(v49) = 2 * (int)v42;
        LOBYTE(v47) = v11;
        cumSum(v47, v56, v49, v6);
        v33 = 2 * (int)v42;
        *v54 = v44;
        goto LABEL_31;
      }
    }
    else
    {
      v48 = -1;
      LOBYTE(v47) = v44 - 1;
      v49 = 0xFFFFFFFFLL;
    }
    do
    {
      v50 = (unsigned __int8)v47;
      LOBYTE(v47) = v49 + v47;
      v56[v50] -= v49;
      v46 += v48;
    }
    while ( v46 );
    goto LABEL_30;
  }
  v15 = 2245 * v11;
  v16 = v11;
  if ( 1000 * (unsigned int)StopBand <= (unsigned int)v15 )
  {
    v35 = numberOfBands(v15, v11, StopBand, 0);
    v33 = v35;
    if ( !v35 )
      return 6;
    LOBYTE(v38) = v35;
    LOBYTE(v37) = v13;
    LOBYTE(v36) = v11;
    CalcBands(v56, v36, v37, v38);
    shellsort(v56, v33);
    if ( !v56[0] )
      return 6;
    v32 = v56;
    v34 = a1;
    v17 = v11;
    v21 = v33;
  }
  else
  {
    v17 = 2 * v11;
    v18 = numberOfBands(v15, v11, 2 * v11, 0);
    v21 = numberOfBands(v19, 2 * v11, v13, (unsigned __int8)a4[19]);
    if ( !v18 )
      return 6;
    if ( !v21 )
      return 6;
    LOBYTE(v23) = v18;
    LOBYTE(v22) = 2 * v11;
    LOBYTE(v20) = v11;
    CalcBands(v56, v20, v22, v23);
    shellsort(v56, v18);
    if ( !v56[0] )
      return 6;
    LOBYTE(v25) = v18;
    LOBYTE(v24) = v11;
    cumSum(v24, v56, v25, a1);
    LOBYTE(v26) = v13;
    LOBYTE(v27) = v21;
    LOBYTE(v28) = 2 * v11;
    CalcBands(v57, v28, v26, v27);
    shellsort(v57, v21);
    v30 = v18;
    LOBYTE(v31) = v56[v18 - 1];
    if ( (unsigned __int8)v31 > v57[0] )
    {
      LOBYTE(v29) = v21;
      if ( (unsigned int)modifyBands(v31, v57, v29) )
        return 6;
    }
    v32 = v57;
    v33 = v18 + v21;
    v34 = v30 + a1;
  }
  LOBYTE(v29) = v21;
  LOBYTE(v31) = v17;
  cumSum(v31, v32, v29, v34);
  *v54 = v33;
  if ( !v33 )
    return 6;
  v6 = a1;
LABEL_31:
  if ( (a5 & 0x80) != 0 )
  {
    for ( i = 1; i < v33; ++i )
    {
      if ( *(unsigned __int8 *)(i + v6) - *(unsigned __int8 *)(i + v6 - 1) > (int)(v16 - 2) )
        return 6;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18001bb08  mov     rax, rsp
0x18001bb0b  push    rbp
0x18001bb0c  push    rbx
0x18001bb0d  push    rsi
0x18001bb0e  push    rdi
0x18001bb0f  push    r12
0x18001bb11  push    r13
0x18001bb13  push    r14
0x18001bb15  push    r15
0x18001bb17  lea     rbp, [rax-57h]
0x18001bb1b  sub     rsp, 0B8h
0x18001bb22  movaps  xmmword ptr [rax-58h], xmm6
0x18001bb26  mov     rax, cs:__security_cookie
0x18001bb2d  xor     rax, rsp
0x18001bb30  mov     [rbp+4Fh+var_60], rax
0x18001bb34  mov     r15d, [rbp+4Fh+arg_20]
0x18001bb38  mov     ebx, r8d
0x18001bb3b  and     r15d, 80h
0x18001bb42  shr     ebx, 1
0x18001bb44  mov     [rbp+4Fh+var_C8], rdx
0x18001bb48  mov     r13, rcx
0x18001bb4b  mov     dl, [r9+10h]
0x18001bb4f  test    r15d, r15d
0x18001bb52  mov     [rsp+20h], rcx
0x18001bb57  mov     rsi, r9
0x18001bb5a  cmovz   ebx, r8d
0x18001bb5e  mov     [rbp+4Fh+var_BC], r15d
0x18001bb62  mov     r8d, [rbp+4Fh+arg_20]
0x18001bb66  mov     ecx, ebx
0x18001bb68  call    getStartBand
0x18001bb6d  movzx   r14d, al
0x18001bb71  cmp     r14b, 0FFh
0x18001bb75  jz      loc_18001BE4D
0x18001bb7b  mov     r8d, [rbp+4Fh+arg_20]
0x18001bb7f  mov     r9b, r14b
0x18001bb82  mov     dl, [rsi+11h]
0x18001bb85  mov     ecx, ebx
0x18001bb87  call    getStopBand
0x18001bb8c  movzx   r12d, al
0x18001bb90  cmp     r12b, 0FFh
0x18001bb94  jz      loc_18001BE4D
0x18001bb9a  mov     cl, [rsi+12h]
0x18001bb9d  test    cl, cl
0x18001bb9f  jz      loc_18001BD53
0x18001bba5  mov     edi, 1
0x18001bbaa  cmp     cl, dil
0x18001bbad  jnz     short loc_18001BBB9
0x18001bbaf  movss   xmm6, cs:__real@41400000
0x18001bbb7  jmp     short loc_18001BBD0
0x18001bbb9  cmp     cl, 2
0x18001bbbc  jnz     short loc_18001BBC8
0x18001bbbe  movss   xmm6, cs:__real@41200000
0x18001bbc6  jmp     short loc_18001BBD0
0x18001bbc8  movss   xmm6, cs:__real@41000000
0x18001bbd0  test    r15d, r15d
0x18001bbd3  jz      short loc_18001BBF5
0x18001bbd5  movd    xmm0, r14d
0x18001bbda  cvtdq2ps xmm0, xmm0
0x18001bbdd  comiss  xmm6, xmm0
0x18001bbe0  jbe     short loc_18001BBF5
0x18001bbe2  mov     al, r14b
0x18001bbe5  shr     al, 1
0x18001bbe7  movzx   eax, al
0x18001bbea  movd    xmm6, eax
0x18001bbee  cvtdq2ps xmm6, xmm6
0x18001bbf1  addss   xmm6, xmm6
0x18001bbf5  imul    ecx, r14d, 8C5h
0x18001bbfc  xor     r9d, r9d
0x18001bbff  imul    eax, r12d, 3E8h
0x18001bc06  mov     r15d, r14d
0x18001bc09  mov     edx, r14d
0x18001bc0c  movaps  xmm0, xmm6
0x18001bc0f  cmp     eax, ecx
0x18001bc11  jbe     loc_18001BCDE
0x18001bc17  lea     r13d, [r14+r14]
0x18001bc1b  mov     r8d, r13d
0x18001bc1e  call    numberOfBands
0x18001bc23  movzx   r9d, byte ptr [rsi+13h]
0x18001bc28  mov     r8d, r12d
0x18001bc2b  mov     ebx, eax
0x18001bc2d  mov     edx, r13d
0x18001bc30  movaps  xmm0, xmm6
0x18001bc33  mov     [rbp+4Fh+var_C0], ebx
0x18001bc36  call    numberOfBands
0x18001bc3b  mov     esi, eax
0x18001bc3d  cmp     bl, dil
0x18001bc40  jb      loc_18001BE4D
0x18001bc46  cmp     sil, dil
0x18001bc49  jb      loc_18001BE4D
0x18001bc4f  mov     r9b, bl
0x18001bc52  lea     rcx, [rbp+4Fh+var_B0]
0x18001bc56  mov     r8b, r13b
0x18001bc59  mov     dl, r14b
0x18001bc5c  call    CalcBands
0x18001bc61  mov     dl, bl; unsigned __int8
0x18001bc63  lea     rcx, [rbp+4Fh+var_B0]; unsigned __int8 *
0x18001bc67  call    ?shellsort@@YAXPEAEE@Z; shellsort(uchar *,uchar)
0x18001bc6c  cmp     [rbp+4Fh+var_B0], 0
0x18001bc70  jz      loc_18001BE4D
0x18001bc76  mov     r9, [rsp+20h]
0x18001bc7b  lea     rdx, [rbp+4Fh+var_B0]
0x18001bc7f  mov     r8b, bl
0x18001bc82  mov     cl, r14b
0x18001bc85  call    cumSum
0x18001bc8a  mov     r8b, r12b
0x18001bc8d  lea     rcx, [rbp+4Fh+var_93]
0x18001bc91  mov     r9b, sil
0x18001bc94  mov     dl, r13b
0x18001bc97  call    CalcBands
0x18001bc9c  mov     dl, sil; unsigned __int8
0x18001bc9f  lea     rcx, [rbp+4Fh+var_93]; unsigned __int8 *
0x18001bca3  call    ?shellsort@@YAXPEAEE@Z; shellsort(uchar *,uchar)
0x18001bca8  movzx   r14d, bl
0x18001bcac  mov     cl, [rbp+r14+4Fh+var_B1]
0x18001bcb1  cmp     cl, [rbp+4Fh+var_93]
0x18001bcb4  jbe     short loc_18001BCCA
0x18001bcb6  mov     r8b, sil
0x18001bcb9  lea     rdx, [rbp+4Fh+var_93]
0x18001bcbd  call    modifyBands
0x18001bcc2  test    eax, eax
0x18001bcc4  jnz     loc_18001BE4D
0x18001bcca  mov     r9, [rsp+20h]
0x18001bccf  lea     rdx, [rbp+4Fh+var_93]
0x18001bcd3  mov     bl, sil
0x18001bcd6  add     bl, byte ptr [rbp+4Fh+var_C0]
0x18001bcd9  add     r9, r14
0x18001bcdc  jmp     short loc_18001BD2F
0x18001bcde  mov     r8d, r12d
0x18001bce1  call    numberOfBands
0x18001bce6  mov     ebx, eax
0x18001bce8  cmp     al, dil
0x18001bceb  jb      loc_18001BE4D
0x18001bcf1  mov     r9b, bl
0x18001bcf4  lea     rcx, [rbp+4Fh+var_B0]
0x18001bcf8  mov     r8b, r12b
0x18001bcfb  mov     dl, r14b
0x18001bcfe  call    CalcBands
0x18001bd03  mov     dl, bl; unsigned __int8
0x18001bd05  lea     rcx, [rbp+4Fh+var_B0]; unsigned __int8 *
0x18001bd09  call    ?shellsort@@YAXPEAEE@Z; shellsort(uchar *,uchar)
0x18001bd0e  cmp     [rbp+4Fh+var_B0], 0
0x18001bd12  jz      loc_18001BE4D
0x18001bd18  mov     rax, [rbp+4Fh+var_C8]
0x18001bd1c  lea     rdx, [rbp+4Fh+var_B0]
0x18001bd20  mov     r9, [rsp+20h]
0x18001bd25  mov     r13b, r14b
0x18001bd28  mov     [rbp+4Fh+var_C8], rax
0x18001bd2c  mov     sil, bl
0x18001bd2f  mov     r8b, sil
0x18001bd32  mov     cl, r13b
0x18001bd35  call    cumSum
0x18001bd3a  mov     rdx, [rbp+4Fh+var_C8]
0x18001bd3e  mov     [rdx], bl
0x18001bd40  cmp     bl, dil
0x18001bd43  jb      loc_18001BE4D
0x18001bd49  mov     r13, [rsp+20h]
0x18001bd4e  jmp     loc_18001BE1A
0x18001bd53  mov     eax, r12d
0x18001bd56  mov     r15d, r14d
0x18001bd59  sub     eax, r14d
0x18001bd5c  mov     ebx, r12d
0x18001bd5f  movd    xmm0, eax
0x18001bd63  mov     al, [rsi+13h]
0x18001bd66  cvtdq2ps xmm0, xmm0
0x18001bd69  test    al, al
0x18001bd6b  jnz     short loc_18001BD77
0x18001bd6d  mulss   xmm0, cs:__real@3f000000
0x18001bd75  jmp     short loc_18001BD87
0x18001bd77  mulss   xmm0, cs:__real@3e800000
0x18001bd7f  addss   xmm0, cs:__real@3f000000
0x18001bd87  neg     al
0x18001bd89  mov     edi, 1
0x18001bd8e  cvttss2si esi, xmm0
0x18001bd92  sbb     edx, edx
0x18001bd94  neg     edx
0x18001bd96  add     edx, edi; Val
0x18001bd98  add     sil, sil
0x18001bd9b  cmp     sil, dil
0x18001bd9e  jb      loc_18001BE4D
0x18001bda4  movzx   eax, sil
0x18001bda8  lea     rcx, [rbp+4Fh+var_B0]; void *
0x18001bdac  imul    eax, edx
0x18001bdaf  xor     r12b, r12b
0x18001bdb2  movzx   r8d, sil; Size
0x18001bdb6  sub     ebx, eax
0x18001bdb8  sub     ebx, r14d
0x18001bdbb  call    memset_0
0x18001bdc0  add     r12b, dil
0x18001bdc3  cmp     r12b, sil
0x18001bdc6  jb      short loc_18001BDC0
0x18001bdc8  xor     ecx, ecx
0x18001bdca  movzx   eax, r12b
0x18001bdce  test    ebx, ebx
0x18001bdd0  cmovns  ecx, eax
0x18001bdd3  jle     short loc_18001BDE3
0x18001bdd5  or      edx, 0FFFFFFFFh
0x18001bdd8  mov     cl, sil
0x18001bddb  sub     cl, dil
0x18001bdde  mov     r8d, edx
0x18001bde1  jmp     short loc_18001BDEF
0x18001bde3  mov     edx, ebx
0x18001bde5  shr     edx, 1Fh
0x18001bde8  mov     r8d, edx
0x18001bdeb  test    ebx, ebx
0x18001bded  jz      short loc_18001BDFE
0x18001bdef  movzx   eax, cl
0x18001bdf2  add     cl, r8b
0x18001bdf5  sub     [rbp+rax+4Fh+var_B0], r8b
0x18001bdfa  add     ebx, edx
0x18001bdfc  jnz     short loc_18001BDEF
0x18001bdfe  mov     r9, r13
0x18001be01  lea     rdx, [rbp+4Fh+var_B0]
0x18001be05  mov     r8b, sil
0x18001be08  mov     cl, r14b
0x18001be0b  call    cumSum
0x18001be10  mov     rdx, [rbp+4Fh+var_C8]
0x18001be14  mov     bl, sil
0x18001be17  mov     [rdx], sil
0x18001be1a  cmp     [rbp+4Fh+var_BC], 0
0x18001be1e  jz      short loc_18001BE49
0x18001be20  mov     r8d, edi
0x18001be23  movzx   r9d, bl
0x18001be27  cmp     r8d, r9d
0x18001be2a  jge     short loc_18001BE49
0x18001be2c  movsxd  rcx, r8d
0x18001be2f  movzx   eax, byte ptr [rcx+r13-1]
0x18001be35  movzx   edx, byte ptr [rcx+r13]
0x18001be3a  sub     edx, eax
0x18001be3c  lea     eax, [r15-2]
0x18001be40  cmp     edx, eax
0x18001be42  jg      short loc_18001BE4D
0x18001be44  add     r8d, edi
0x18001be47  jmp     short loc_18001BE27
0x18001be49  xor     eax, eax
0x18001be4b  jmp     short loc_18001BE52
0x18001be4d  mov     eax, 6
0x18001be52  mov     rcx, [rbp+4Fh+var_60]
0x18001be56  xor     rcx, rsp; StackCookie
0x18001be59  call    __security_check_cookie
0x18001be5e  movaps  xmm6, [rsp+0F0h+var_58+8]
0x18001be66  add     rsp, 0B8h
0x18001be6d  pop     r15
0x18001be6f  pop     r14
0x18001be71  pop     r13
0x18001be73  pop     r12
0x18001be75  pop     rdi
0x18001be76  pop     rsi
0x18001be77  pop     rbx
0x18001be78  pop     rbp
0x18001be79  retn
```
