# CProgramConfig_ReadHeightExt

- ea: `0x1800471fc`
- end: `0x180047425`
- name: `CProgramConfig_ReadHeightExt`
- size: `553`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config`

## callers

- `0x1800127d8`

## callees

- `0x18000e9b0`
- `0x1800110c0`
- `0x180012580`
- `0x1800130d8`
- `0x180013fd0`
- `0x18002ce0c`
- `0x1800471fc`
- `0x18004d320`
- `0x18004dd14`

## pseudocode

```c
__int64 __fastcall CProgramConfig_ReadHeightExt(__int64 a1, __int64 a2, int *a3, unsigned int a4)
{
  int v4; // r15d
  int *v5; // r12
  unsigned int v8; // edi
  __int64 v9; // rcx
  __int64 v10; // rax
  int started; // r13d
  __int64 v12; // r8
  unsigned int v13; // esi
  __int64 v14; // r8
  unsigned __int8 v15; // al
  __int64 v16; // rcx
  int v17; // r15d
  unsigned __int8 v18; // al
  __int64 v19; // rcx
  int v20; // r15d
  unsigned __int8 v21; // al
  __int64 v22; // rcx
  __int64 v23; // r8
  __int16 v24; // ax
  __int64 result; // rax
  _BYTE v28[48]; // [rsp+30h] [rbp-49h] BYREF
  __int64 v29; // [rsp+60h] [rbp-19h]
  int v30; // [rsp+68h] [rbp-11h]
  __int16 v31; // [rsp+6Ch] [rbp-Dh]
  char v32; // [rsp+6Eh] [rbp-Bh]
  __int64 v33; // [rsp+70h] [rbp-9h]
  __int16 v34; // [rsp+78h] [rbp-1h]

  v4 = 0;
  v5 = a3;
  v8 = 0;
  memset_0(v28, 0, 0x50u);
  v32 = 8;
  v31 = 255;
  v34 = 255;
  v9 = 0;
  v30 = 8388615;
  do
  {
    v10 = v9++;
    v28[16 * v10] = 0;
  }
  while ( v9 != 3 );
  v33 = 0;
  v29 = 0;
  started = CDKcrcStartReg((struct CDK_CRCINFO *)v28, (struct CDK_BITSTREAM *const)a2, 0);
  CDKsyncCache_0((int *)a2);
  v13 = *(_DWORD *)(a2 + 8);
  if ( v13 < 0x18 || *v5 < 3 || (unsigned int)CDKreadBits((_DWORD *)a2, 8, v12) != 172 )
  {
    CDKsyncCache_0((int *)a2);
    CDKpushBack_0(a2, v13 - *(_DWORD *)(a2 + 8));
    goto LABEL_26;
  }
  if ( *(_BYTE *)(a1 + 3) )
  {
    do
    {
      v15 = CDKreadBits((_DWORD *)a2, 2, v14);
      v16 = v4;
      if ( v15 >= 3u )
        v8 = -2;
      ++v4;
      *(_BYTE *)(v16 + a1 + 48) = v15;
    }
    while ( v4 < *(unsigned __int8 *)(a1 + 3) );
    v5 = a3;
  }
  v17 = 0;
  if ( *(_BYTE *)(a1 + 4) )
  {
    do
    {
      v18 = CDKreadBits((_DWORD *)a2, 2, v14);
      v19 = v17;
      if ( v18 >= 3u )
        v8 = -2;
      ++v17;
      *(_BYTE *)(v19 + a1 + 96) = v18;
    }
    while ( v17 < *(unsigned __int8 *)(a1 + 4) );
    v5 = a3;
  }
  v20 = 0;
  if ( *(_BYTE *)(a1 + 5) )
  {
    do
    {
      v21 = CDKreadBits((_DWORD *)a2, 2, v14);
      v22 = v20;
      if ( v21 >= 3u )
        v8 = -2;
      ++v20;
      *(_BYTE *)(v22 + a1 + 144) = v21;
    }
    while ( v20 < *(unsigned __int8 *)(a1 + 5) );
    v5 = a3;
  }
  CDKbyteAlign_0(a2, a4);
  CDKcrcEndReg((struct CDK_CRCINFO *)v28, (struct CDK_BITSTREAM *const)a2, started);
  v24 = CDKreadBits((_DWORD *)a2, 8, v23);
  if ( v24 != ((unsigned __int16)v34 & (unsigned __int16)(2 * (HIWORD(v30) - 1) + 1)) )
  {
    v8 = -1;
LABEL_24:
    *(_OWORD *)(a1 + 48) = 0;
    *(_OWORD *)(a1 + 96) = 0;
    *(_OWORD *)(a1 + 144) = 0;
    goto LABEL_26;
  }
  if ( v8 )
    goto LABEL_24;
LABEL_26:
  CDKsyncCache_0((int *)a2);
  result = v8;
  *v5 -= (v13 - *(_DWORD *)(a2 + 8)) >> 3;
  return result;
}

```

## disassembly

```asm
0x1800471fc  push    rbp
0x1800471fe  push    rbx
0x1800471ff  push    rsi
0x180047200  push    rdi
0x180047201  push    r12
0x180047203  push    r13
0x180047205  push    r14
0x180047207  push    r15
0x180047209  lea     rbp, [rsp-1Fh]
0x18004720e  sub     rsp, 98h
0x180047215  mov     rax, cs:__security_cookie
0x18004721c  xor     rax, rsp
0x18004721f  mov     [rbp+57h+var_50], rax
0x180047223  xor     r15d, r15d
0x180047226  mov     [rbp+57h+var_A8], r8
0x18004722a  mov     r12, r8
0x18004722d  mov     [rbp+57h+var_B0], r9d
0x180047231  mov     rbx, rdx
0x180047234  mov     r14, rcx
0x180047237  xor     edx, edx; Val
0x180047239  lea     rcx, [rbp+57h+var_A0]; void *
0x18004723d  lea     r8d, [r15+50h]; Size
0x180047241  mov     edi, r15d
0x180047244  call    memset_0
0x180047249  mov     ecx, 0FFh
0x18004724e  mov     [rbp+57h+var_62], 8
0x180047252  mov     [rbp+57h+var_64], cx
0x180047256  mov     [rbp+57h+var_58], cx
0x18004725a  mov     ecx, r15d
0x18004725d  mov     [rbp+57h+var_68], 800007h
0x180047264  mov     rax, rcx
0x180047267  inc     rcx
0x18004726a  add     rax, rax
0x18004726d  mov     [rbp+rax*8+57h+var_A0], r15b
0x180047272  cmp     rcx, 3
0x180047276  jnz     short loc_180047264
0x180047278  xor     r8d, r8d; int
0x18004727b  mov     [rbp+57h+var_60], r15
0x18004727f  mov     rdx, rbx; struct CDK_BITSTREAM *
0x180047282  mov     [rbp+57h+var_70], r15
0x180047286  lea     rcx, [rbp+57h+var_A0]; struct CDK_CRCINFO *
0x18004728a  call    ?CDKcrcStartReg@@YAHPEAUCDK_CRCINFO@@QEAUCDK_BITSTREAM@@H@Z; CDKcrcStartReg(CDK_CRCINFO *,CDK_BITSTREAM * const,int)
0x18004728f  mov     rcx, rbx
0x180047292  mov     r13d, eax
0x180047295  call    CDKsyncCache_0
0x18004729a  mov     esi, [rbx+8]
0x18004729d  cmp     esi, 18h
0x1800472a0  jb      loc_1800473DB
0x1800472a6  cmp     dword ptr [r12], 3
0x1800472ab  jl      loc_1800473DB
0x1800472b1  mov     edx, 8
0x1800472b6  mov     rcx, rbx
0x1800472b9  call    CDKreadBits
0x1800472be  cmp     eax, 0ACh
0x1800472c3  jnz     loc_1800473DB
0x1800472c9  cmp     [r14+3], dil
0x1800472cd  jbe     short loc_180047301
0x1800472cf  mov     r12d, 0FFFFFFFEh
0x1800472d5  mov     edx, 2
0x1800472da  mov     rcx, rbx
0x1800472dd  call    CDKreadBits
0x1800472e2  cmp     al, 3
0x1800472e4  movsxd  rcx, r15d
0x1800472e7  cmovnb  edi, r12d
0x1800472eb  inc     r15d
0x1800472ee  mov     [rcx+r14+30h], al
0x1800472f3  movzx   eax, byte ptr [r14+3]
0x1800472f8  cmp     r15d, eax
0x1800472fb  jl      short loc_1800472D5
0x1800472fd  mov     r12, [rbp+57h+var_A8]
0x180047301  xor     r15d, r15d
0x180047304  cmp     [r14+4], r15b
0x180047308  jbe     short loc_18004733A
0x18004730a  lea     r12d, [r15-2]
0x18004730e  mov     edx, 2
0x180047313  mov     rcx, rbx
0x180047316  call    CDKreadBits
0x18004731b  cmp     al, 3
0x18004731d  movsxd  rcx, r15d
0x180047320  cmovnb  edi, r12d
0x180047324  inc     r15d
0x180047327  mov     [rcx+r14+60h], al
0x18004732c  movzx   eax, byte ptr [r14+4]
0x180047331  cmp     r15d, eax
0x180047334  jl      short loc_18004730E
0x180047336  mov     r12, [rbp+57h+var_A8]
0x18004733a  xor     r15d, r15d
0x18004733d  cmp     [r14+5], r15b
0x180047341  jbe     short loc_180047376
0x180047343  lea     r12d, [r15-2]
0x180047347  mov     edx, 2
0x18004734c  mov     rcx, rbx
0x18004734f  call    CDKreadBits
0x180047354  cmp     al, 3
0x180047356  movsxd  rcx, r15d
0x180047359  cmovnb  edi, r12d
0x18004735d  inc     r15d
0x180047360  mov     [rcx+r14+90h], al
0x180047368  movzx   eax, byte ptr [r14+5]
0x18004736d  cmp     r15d, eax
0x180047370  jl      short loc_180047347
0x180047372  mov     r12, [rbp+57h+var_A8]
0x180047376  mov     edx, [rbp+57h+var_B0]
0x180047379  mov     rcx, rbx
0x18004737c  call    CDKbyteAlign_0
0x180047381  mov     r8d, r13d; int
0x180047384  lea     rcx, [rbp+57h+var_A0]; struct CDK_CRCINFO *
0x180047388  mov     rdx, rbx; struct CDK_BITSTREAM *
0x18004738b  call    ?CDKcrcEndReg@@YAHPEAUCDK_CRCINFO@@QEAUCDK_BITSTREAM@@H@Z; CDKcrcEndReg(CDK_CRCINFO *,CDK_BITSTREAM * const,int)
0x180047390  mov     edx, 8
0x180047395  mov     rcx, rbx
0x180047398  call    CDKreadBits
0x18004739d  movzx   ecx, word ptr [rbp+57h+var_68+2]
0x1800473a1  mov     edx, 1
0x1800473a6  sub     cx, dx
0x1800473a9  add     cx, cx
0x1800473ac  add     cx, dx
0x1800473af  and     cx, [rbp+57h+var_58]
0x1800473b3  cmp     ax, cx
0x1800473b6  jz      short loc_1800473BD
0x1800473b8  or      edi, 0FFFFFFFFh
0x1800473bb  jmp     short loc_1800473C1
0x1800473bd  test    edi, edi
0x1800473bf  jz      short loc_1800473F0
0x1800473c1  xorps   xmm0, xmm0
0x1800473c4  xorps   xmm1, xmm1
0x1800473c7  movups  xmmword ptr [r14+30h], xmm0
0x1800473cc  movups  xmmword ptr [r14+60h], xmm1
0x1800473d1  movups  xmmword ptr [r14+90h], xmm0
0x1800473d9  jmp     short loc_1800473F0
0x1800473db  mov     rcx, rbx
0x1800473de  call    CDKsyncCache_0
0x1800473e3  mov     edx, esi
0x1800473e5  mov     rcx, rbx
0x1800473e8  sub     edx, [rbx+8]
0x1800473eb  call    CDKpushBack_0
0x1800473f0  mov     rcx, rbx
0x1800473f3  call    CDKsyncCache_0
0x1800473f8  sub     esi, [rbx+8]
0x1800473fb  mov     eax, edi
0x1800473fd  shr     esi, 3
0x180047400  sub     [r12], esi
0x180047404  mov     rcx, [rbp+57h+var_50]
0x180047408  xor     rcx, rsp; StackCookie
0x18004740b  call    __security_check_cookie
0x180047410  add     rsp, 98h
0x180047417  pop     r15
0x180047419  pop     r14
0x18004741b  pop     r13
0x18004741d  pop     r12
0x18004741f  pop     rdi
0x180047420  pop     rsi
0x180047421  pop     rbx
0x180047422  pop     rbp
0x180047423  retn
```
