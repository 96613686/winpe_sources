# CProgramConfig_Read(CProgramConfig *,CDK_BITSTREAM *,uint)

- ea: `0x1800127d8`
- end: `0x180012bef`
- name: `?CProgramConfig_Read@@YAXPEAUCProgramConfig@@PEAUCDK_BITSTREAM@@I@Z`
- size: `1047`
- prototype: `void __fastcall(struct CProgramConfig *, struct CDK_BITSTREAM *, unsigned int)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180010838`
- `0x18001262c`
- `0x180012bf8`
- `0x18007a4ac`

## callees

- `0x1800110c0`
- `0x1800127d8`
- `0x18002ce0c`
- `0x1800471fc`
- `0x1800477e4`
- `0x18004d320`

## pseudocode

```c
void __fastcall CProgramConfig_Read(struct CProgramConfig *a1, struct CDK_BITSTREAM *a2, __int64 a3)
{
  unsigned int v5; // r15d
  __int64 v6; // r8
  __int64 v7; // r8
  __int64 v8; // r8
  __int64 v9; // r8
  __int64 v10; // r8
  __int64 v11; // r8
  __int64 v12; // r8
  __int64 v13; // r8
  __int64 v14; // r8
  char v15; // al
  __int64 v16; // r8
  char v17; // al
  __int64 v18; // r8
  char v19; // al
  char *v20; // r8
  __int64 v21; // r8
  int v22; // r14d
  unsigned __int8 v23; // di
  __int64 v24; // r8
  unsigned __int8 v25; // al
  bool v26; // zf
  char v27; // cl
  int v28; // r14d
  unsigned __int8 v29; // di
  __int64 v30; // r8
  unsigned __int8 v31; // al
  int v32; // r14d
  unsigned __int8 v33; // di
  __int64 v34; // r8
  unsigned __int8 v35; // al
  int v36; // ebx
  unsigned __int8 v37; // al
  int v38; // ebx
  char v39; // al
  __int64 v40; // rcx
  int v41; // edi
  __int64 v42; // r8
  __int64 v43; // r8
  unsigned __int8 v44; // al
  __int64 v45; // r8
  int v46; // edi
  int i; // ebx
  char v48; // al
  int v49; // [rsp+20h] [rbp-78h] BYREF
  _OWORD v50[2]; // [rsp+28h] [rbp-70h] BYREF
  __int128 v51; // [rsp+48h] [rbp-50h]

  *(_WORD *)((char *)a1 + 461) = 1;
  *((_BYTE *)a1 + 463) = 0;
  v5 = a3;
  memset(v50, 0, sizeof(v50));
  v51 = 0;
  *(_BYTE *)a1 = CDKreadBits(a2, 4, a3);
  *((_BYTE *)a1 + 1) = CDKreadBits(a2, 2, v6);
  *((_BYTE *)a1 + 2) = CDKreadBits(a2, 4, v7);
  *((_BYTE *)a1 + 3) = CDKreadBits(a2, 4, v8);
  *((_BYTE *)a1 + 4) = CDKreadBits(a2, 4, v9);
  *((_BYTE *)a1 + 5) = CDKreadBits(a2, 4, v10);
  *((_BYTE *)a1 + 6) = CDKreadBits(a2, 2, v11);
  *((_BYTE *)a1 + 7) = CDKreadBits(a2, 3, v12);
  *((_BYTE *)a1 + 8) = CDKreadBits(a2, 4, v13);
  v15 = CDKreadBits(a2, 1, v14);
  *((_BYTE *)a1 + 9) = v15;
  if ( v15 )
    *((_BYTE *)a1 + 10) = CDKreadBits(a2, 4, v16);
  v17 = CDKreadBits(a2, 1, v16);
  *((_BYTE *)a1 + 11) = v17;
  if ( v17 )
    *((_BYTE *)a1 + 12) = CDKreadBits(a2, 4, v18);
  v19 = CDKreadBits(a2, 1, v18);
  *((_BYTE *)a1 + 13) = v19;
  if ( v19 )
  {
    *((_BYTE *)a1 + 14) = CDKreadBits(a2, 2, (__int64)v20);
    *((_BYTE *)a1 + 15) = CDKreadBits(a2, 1, v21);
  }
  v22 = 0;
  if ( *((_BYTE *)a1 + 3) )
  {
    do
    {
      v23 = CDKreadBits(a2, 1, (__int64)v20);
      *((_BYTE *)a1 + v22 + 16) = v23;
      v25 = CDKreadBits(a2, 4, v24);
      v26 = *((_BYTE *)a1 + v22 + 16) == 0;
      *((_BYTE *)a1 + v22 + 32) = v25;
      v27 = *((_BYTE *)a1 + 462) + !v26 + 1;
      v20 = (char *)v50 + v25;
      *((_BYTE *)a1 + 462) = v27;
      if ( v20[16 * v23] )
        *((_BYTE *)a1 + 461) = 0;
      else
        v20[16 * v23] = 1;
      ++v22;
    }
    while ( v22 < *((unsigned __int8 *)a1 + 3) );
  }
  else
  {
    v27 = *((_BYTE *)a1 + 462);
  }
  v28 = 0;
  if ( *((_BYTE *)a1 + 4) )
  {
    do
    {
      v29 = CDKreadBits(a2, 1, (__int64)v20);
      *((_BYTE *)a1 + v28 + 64) = v29;
      v31 = CDKreadBits(a2, 4, v30);
      v26 = *((_BYTE *)a1 + v28 + 64) == 0;
      *((_BYTE *)a1 + v28 + 80) = v31;
      v27 = *((_BYTE *)a1 + 462) + !v26 + 1;
      v20 = (char *)v50 + v31;
      *((_BYTE *)a1 + 462) = v27;
      if ( v20[16 * v29] )
        *((_BYTE *)a1 + 461) = 0;
      else
        v20[16 * v29] = 1;
      ++v28;
    }
    while ( v28 < *((unsigned __int8 *)a1 + 4) );
  }
  v32 = 0;
  if ( *((_BYTE *)a1 + 5) )
  {
    do
    {
      v33 = CDKreadBits(a2, 1, (__int64)v20);
      *((_BYTE *)a1 + v32 + 112) = v33;
      v35 = CDKreadBits(a2, 4, v34);
      v26 = *((_BYTE *)a1 + v32 + 112) == 0;
      *((_BYTE *)a1 + v32 + 128) = v35;
      v27 = *((_BYTE *)a1 + 462) + !v26 + 1;
      v20 = (char *)v50 + v35;
      *((_BYTE *)a1 + 462) = v27;
      if ( v20[16 * v33] )
        *((_BYTE *)a1 + 461) = 0;
      else
        v20[16 * v33] = 1;
      ++v32;
    }
    while ( v32 < *((unsigned __int8 *)a1 + 5) );
  }
  v36 = 0;
  *((_BYTE *)a1 + 463) = v27;
  if ( *((_BYTE *)a1 + 6) )
  {
    do
    {
      v37 = CDKreadBits(a2, 4, (__int64)v20);
      *((_BYTE *)a1 + v36 + 160) = v37;
      ++*((_BYTE *)a1 + 462);
      if ( *((_BYTE *)&v51 + v37) )
        *((_BYTE *)a1 + 461) = 0;
      else
        *((_BYTE *)&v51 + v37) = 1;
      ++v36;
    }
    while ( v36 < *((unsigned __int8 *)a1 + 6) );
  }
  v38 = 0;
  if ( *((_BYTE *)a1 + 7) )
  {
    do
    {
      v39 = CDKreadBits(a2, 4, (__int64)v20);
      v40 = v38++;
      *((_BYTE *)a1 + v40 + 164) = v39;
    }
    while ( v38 < *((unsigned __int8 *)a1 + 7) );
  }
  v41 = 0;
  if ( *((_BYTE *)a1 + 8) )
  {
    do
    {
      *((_BYTE *)a1 + v41 + 172) = CDKreadBits(a2, 1, (__int64)v20);
      *((_BYTE *)a1 + v41++ + 188) = CDKreadBits(a2, 4, v42);
    }
    while ( v41 < *((unsigned __int8 *)a1 + 8) );
  }
  CDKbyteAlign_0(a2, v5);
  v44 = CDKreadBits(a2, 8, v43);
  *((_BYTE *)a1 + 204) = v44;
  v49 = v44;
  if ( (unsigned int)CProgramConfig_ReadHeightExt(a1, a2, &v49, v5) )
    *((_BYTE *)a1 + 461) = 0;
  if ( (unsigned int)CProgramConfig_Check(a1) )
    *((_BYTE *)a1 + 461) = 0;
  v46 = v49;
  for ( i = 0; i < v46; ++i )
  {
    v48 = CDKreadBits(a2, 8, v45);
    if ( i < 256 )
      *((_BYTE *)a1 + i + 205) = v48;
  }
}

```

## disassembly

```asm
0x1800127d8  mov     [rsp+arg_18], rbx
0x1800127dd  push    rbp
0x1800127de  push    rsi
0x1800127df  push    rdi
0x1800127e0  push    r12
0x1800127e2  push    r13
0x1800127e4  push    r14
0x1800127e6  push    r15
0x1800127e8  sub     rsp, 60h
0x1800127ec  mov     rax, cs:__security_cookie
0x1800127f3  xor     rax, rsp
0x1800127f6  mov     [rsp+98h+var_40], rax
0x1800127fb  mov     rbp, rdx
0x1800127fe  mov     r13d, 1
0x180012804  mov     rsi, rcx
0x180012807  mov     [rcx+1CDh], r13w
0x18001280f  xorps   xmm1, xmm1
0x180012812  xor     r12d, r12d
0x180012815  mov     [rcx+1CFh], r12b
0x18001281c  xorps   xmm0, xmm0
0x18001281f  lea     ebx, [r13+3]
0x180012823  mov     rcx, rbp
0x180012826  mov     edx, ebx
0x180012828  mov     r15d, r8d
0x18001282b  movups  [rsp+98h+var_70], xmm0
0x180012830  movups  [rsp+98h+var_60], xmm1
0x180012835  movups  [rsp+98h+var_50], xmm1
0x18001283a  call    CDKreadBits
0x18001283f  lea     edi, [rbx-2]
0x180012842  mov     [rsi], al
0x180012844  mov     edx, edi
0x180012846  mov     rcx, rbp
0x180012849  call    CDKreadBits
0x18001284e  mov     edx, ebx
0x180012850  mov     [rsi+1], al
0x180012853  mov     rcx, rbp
0x180012856  call    CDKreadBits
0x18001285b  mov     edx, ebx
0x18001285d  mov     [rsi+2], al
0x180012860  mov     rcx, rbp
0x180012863  call    CDKreadBits
0x180012868  mov     edx, ebx
0x18001286a  mov     [rsi+3], al
0x18001286d  mov     rcx, rbp
0x180012870  call    CDKreadBits
0x180012875  mov     edx, ebx
0x180012877  mov     [rsi+4], al
0x18001287a  mov     rcx, rbp
0x18001287d  call    CDKreadBits
0x180012882  mov     edx, edi
0x180012884  mov     [rsi+5], al
0x180012887  mov     rcx, rbp
0x18001288a  call    CDKreadBits
0x18001288f  lea     edx, [rbx-1]
0x180012892  mov     [rsi+6], al
0x180012895  mov     rcx, rbp
0x180012898  call    CDKreadBits
0x18001289d  mov     edx, ebx
0x18001289f  mov     [rsi+7], al
0x1800128a2  mov     rcx, rbp
0x1800128a5  call    CDKreadBits
0x1800128aa  mov     edx, r13d
0x1800128ad  mov     [rsi+8], al
0x1800128b0  mov     rcx, rbp
0x1800128b3  call    CDKreadBits
0x1800128b8  mov     [rsi+9], al
0x1800128bb  test    al, al
0x1800128bd  jz      short loc_1800128CC
0x1800128bf  mov     edx, ebx
0x1800128c1  mov     rcx, rbp
0x1800128c4  call    CDKreadBits
0x1800128c9  mov     [rsi+0Ah], al
0x1800128cc  mov     edx, r13d
0x1800128cf  mov     rcx, rbp
0x1800128d2  call    CDKreadBits
0x1800128d7  mov     [rsi+0Bh], al
0x1800128da  test    al, al
0x1800128dc  jz      short loc_1800128EB
0x1800128de  mov     edx, ebx
0x1800128e0  mov     rcx, rbp
0x1800128e3  call    CDKreadBits
0x1800128e8  mov     [rsi+0Ch], al
0x1800128eb  mov     edx, r13d
0x1800128ee  mov     rcx, rbp
0x1800128f1  call    CDKreadBits
0x1800128f6  mov     [rsi+0Dh], al
0x1800128f9  test    al, al
0x1800128fb  jz      short loc_180012918
0x1800128fd  mov     edx, edi
0x1800128ff  mov     rcx, rbp
0x180012902  call    CDKreadBits
0x180012907  mov     edx, r13d
0x18001290a  mov     [rsi+0Eh], al
0x18001290d  mov     rcx, rbp
0x180012910  call    CDKreadBits
0x180012915  mov     [rsi+0Fh], al
0x180012918  mov     r14d, r12d
0x18001291b  cmp     [rsi+3], r12b
0x18001291f  jbe     short loc_180012991
0x180012921  mov     edx, r13d
0x180012924  mov     rcx, rbp
0x180012927  call    CDKreadBits
0x18001292c  mov     edi, eax
0x18001292e  mov     edx, 4
0x180012933  movsxd  rbx, r14d
0x180012936  mov     rcx, rbp
0x180012939  mov     [rbx+rsi+10h], dil
0x18001293e  call    CDKreadBits
0x180012943  cmp     [rbx+rsi+10h], r12b
0x180012948  lea     r8, [rsp+98h+var_70]
0x18001294d  mov     [rbx+rsi+20h], al
0x180012951  setnz   cl
0x180012954  movzx   edx, dil
0x180012958  add     cl, r13b
0x18001295b  movzx   eax, al
0x18001295e  add     cl, [rsi+1CEh]
0x180012964  add     rdx, rdx
0x180012967  add     r8, rax
0x18001296a  mov     [rsi+1CEh], cl
0x180012970  cmp     [r8+rdx*8], r12b
0x180012974  jnz     short loc_18001297C
0x180012976  mov     [r8+rdx*8], r13b
0x18001297a  jmp     short loc_180012983
0x18001297c  mov     [rsi+1CDh], r12b
0x180012983  movzx   eax, byte ptr [rsi+3]
0x180012987  add     r14d, r13d
0x18001298a  cmp     r14d, eax
0x18001298d  jl      short loc_180012921
0x18001298f  jmp     short loc_180012997
0x180012991  mov     cl, [rsi+1CEh]
0x180012997  mov     r14d, r12d
0x18001299a  cmp     [rsi+4], r12b
0x18001299e  jbe     short loc_180012A0E
0x1800129a0  mov     edx, r13d
0x1800129a3  mov     rcx, rbp
0x1800129a6  call    CDKreadBits
0x1800129ab  mov     edi, eax
0x1800129ad  mov     edx, 4
0x1800129b2  movsxd  rbx, r14d
0x1800129b5  mov     rcx, rbp
0x1800129b8  mov     [rbx+rsi+40h], dil
0x1800129bd  call    CDKreadBits
0x1800129c2  cmp     [rbx+rsi+40h], r12b
0x1800129c7  lea     r8, [rsp+98h+var_70]
0x1800129cc  mov     [rbx+rsi+50h], al
0x1800129d0  setnz   cl
0x1800129d3  movzx   edx, dil
0x1800129d7  add     cl, r13b
0x1800129da  movzx   eax, al
0x1800129dd  add     cl, [rsi+1CEh]
0x1800129e3  add     rdx, rdx
0x1800129e6  add     r8, rax
0x1800129e9  mov     [rsi+1CEh], cl
0x1800129ef  cmp     [r8+rdx*8], r12b
0x1800129f3  jnz     short loc_1800129FB
0x1800129f5  mov     [r8+rdx*8], r13b
0x1800129f9  jmp     short loc_180012A02
0x1800129fb  mov     [rsi+1CDh], r12b
0x180012a02  movzx   eax, byte ptr [rsi+4]
0x180012a06  add     r14d, r13d
0x180012a09  cmp     r14d, eax
0x180012a0c  jl      short loc_1800129A0
0x180012a0e  mov     r14d, r12d
0x180012a11  cmp     [rsi+5], r12b
0x180012a15  jbe     short loc_180012A88
0x180012a17  mov     edx, r13d
0x180012a1a  mov     rcx, rbp
0x180012a1d  call    CDKreadBits
0x180012a22  mov     edi, eax
0x180012a24  mov     edx, 4
0x180012a29  movsxd  rbx, r14d
0x180012a2c  mov     rcx, rbp
0x180012a2f  mov     [rbx+rsi+70h], dil
0x180012a34  call    CDKreadBits
0x180012a39  cmp     [rbx+rsi+70h], r12b
0x180012a3e  lea     r8, [rsp+98h+var_70]
0x180012a43  mov     [rbx+rsi+80h], al
0x180012a4a  setnz   cl
0x180012a4d  movzx   edx, dil
0x180012a51  add     cl, r13b
0x180012a54  movzx   eax, al
0x180012a57  add     cl, [rsi+1CEh]
0x180012a5d  add     rdx, rdx
0x180012a60  add     r8, rax
0x180012a63  mov     [rsi+1CEh], cl
0x180012a69  cmp     [r8+rdx*8], r12b
0x180012a6d  jnz     short loc_180012A75
0x180012a6f  mov     [r8+rdx*8], r13b
0x180012a73  jmp     short loc_180012A7C
0x180012a75  mov     [rsi+1CDh], r12b
0x180012a7c  movzx   eax, byte ptr [rsi+5]
0x180012a80  add     r14d, r13d
0x180012a83  cmp     r14d, eax
0x180012a86  jl      short loc_180012A17
0x180012a88  mov     ebx, r12d
0x180012a8b  mov     [rsi+1CFh], cl
0x180012a91  cmp     [rsi+6], r12b
0x180012a95  jbe     short loc_180012AD8
0x180012a97  mov     edx, 4
0x180012a9c  mov     rcx, rbp
0x180012a9f  call    CDKreadBits
0x180012aa4  movsxd  rcx, ebx
0x180012aa7  mov     [rcx+rsi+0A0h], al
0x180012aae  add     [rsi+1CEh], r13b
0x180012ab5  movzx   ecx, al
0x180012ab8  cmp     byte ptr [rsp+rcx+98h+var_50], r12b
0x180012abd  jnz     short loc_180012AC6
0x180012abf  mov     byte ptr [rsp+rcx+98h+var_50], r13b
0x180012ac4  jmp     short loc_180012ACD
0x180012ac6  mov     [rsi+1CDh], r12b
0x180012acd  movzx   eax, byte ptr [rsi+6]
0x180012ad1  add     ebx, r13d
0x180012ad4  cmp     ebx, eax
0x180012ad6  jl      short loc_180012A97
0x180012ad8  mov     ebx, r12d
0x180012adb  cmp     [rsi+7], r12b
0x180012adf  jbe     short loc_180012B03
0x180012ae1  mov     edx, 4
0x180012ae6  mov     rcx, rbp
0x180012ae9  call    CDKreadBits
0x180012aee  movsxd  rcx, ebx
0x180012af1  add     ebx, r13d
0x180012af4  mov     [rcx+rsi+0A4h], al
0x180012afb  movzx   eax, byte ptr [rsi+7]
0x180012aff  cmp     ebx, eax
0x180012b01  jl      short loc_180012AE1
0x180012b03  mov     edi, r12d
0x180012b06  cmp     [rsi+8], r12b
0x180012b0a  jbe     short loc_180012B40
0x180012b0c  mov     edx, r13d
0x180012b0f  movsxd  rbx, edi
0x180012b12  mov     rcx, rbp
0x180012b15  call    CDKreadBits
0x180012b1a  mov     edx, 4
0x180012b1f  mov     [rbx+rsi+0ACh], al
0x180012b26  mov     rcx, rbp
0x180012b29  call    CDKreadBits
0x180012b2e  mov     [rbx+rsi+0BCh], al
0x180012b35  add     edi, r13d
0x180012b38  movzx   eax, byte ptr [rsi+8]
0x180012b3c  cmp     edi, eax
0x180012b3e  jl      short loc_180012B0C
0x180012b40  mov     edx, r15d
0x180012b43  mov     rcx, rbp
0x180012b46  call    CDKbyteAlign_0
0x180012b4b  mov     r14d, 8
0x180012b51  mov     rcx, rbp
0x180012b54  mov     edx, r14d
0x180012b57  call    CDKreadBits
0x180012b5c  mov     [rsi+0CCh], al
0x180012b62  lea     r8, [rsp+98h+var_78]
0x180012b67  movzx   eax, al
0x180012b6a  mov     r9d, r15d
0x180012b6d  mov     rdx, rbp
0x180012b70  mov     [rsp+98h+var_78], eax
0x180012b74  mov     rcx, rsi
0x180012b77  call    CProgramConfig_ReadHeightExt
0x180012b7c  test    eax, eax
0x180012b7e  jz      short loc_180012B87
0x180012b80  mov     [rsi+1CDh], r12b
0x180012b87  mov     rcx, rsi
0x180012b8a  call    CProgramConfig_Check
0x180012b8f  test    eax, eax
0x180012b91  jz      short loc_180012B9A
0x180012b93  mov     [rsi+1CDh], r12b
0x180012b9a  mov     edi, [rsp+98h+var_78]
0x180012b9e  mov     ebx, r12d
0x180012ba1  test    edi, edi
0x180012ba3  jle     short loc_180012BC9
0x180012ba5  mov     edx, r14d
0x180012ba8  mov     rcx, rbp
0x180012bab  call    CDKreadBits
0x180012bb0  cmp     ebx, 100h
0x180012bb6  jge     short loc_180012BC2
0x180012bb8  movsxd  rcx, ebx
0x180012bbb  mov     [rcx+rsi+0CDh], al
0x180012bc2  add     ebx, r13d
0x180012bc5  cmp     ebx, edi
0x180012bc7  jl      short loc_180012BA5
0x180012bc9  mov     rcx, [rsp+98h+var_40]
0x180012bce  xor     rcx, rsp; StackCookie
0x180012bd1  call    __security_check_cookie
0x180012bd6  mov     rbx, [rsp+98h+arg_18]
0x180012bde  add     rsp, 60h
0x180012be2  pop     r15
0x180012be4  pop     r14
0x180012be6  pop     r13
0x180012be8  pop     r12
0x180012bea  pop     rdi
0x180012beb  pop     rsi
0x180012bec  pop     rbp
0x180012bed  retn
```
