# CProgramConfigElement_Read

- ea: `0x180012bf8`
- end: `0x180012d87`
- name: `CProgramConfigElement_Read`
- size: `399`
- prototype: `__int64 __fastcall(struct CDK_BITSTREAM *, struct TRANSPORTDEC *, struct CProgramConfig *, unsigned int, unsigned int)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000c510`

## callees

- `0x1800127d8`
- `0x180012bf8`
- `0x18001308c`
- `0x180014078`
- `0x180046ebc`
- `0x18004b854`
- `0x18004d320`
- `0x18004dd14`

## pseudocode

```c
__int64 __fastcall CProgramConfigElement_Read(
        struct CDK_BITSTREAM *a1,
        struct TRANSPORTDEC *a2,
        struct CProgramConfig *a3,
        unsigned int a4,
        unsigned int a5)
{
  unsigned int v9; // r14d
  int started; // ebx
  int v11; // eax
  __int64 v12; // rcx
  _OWORD *v13; // rax
  __int128 v14; // xmm1
  __int128 v15; // xmm0
  __int128 v16; // xmm1
  __int128 v17; // xmm0
  __int128 v18; // xmm1
  __int128 v19; // xmm0
  __int128 v20; // xmm1
  __int128 v21; // xmm1
  __int128 v22; // xmm0
  __int128 v23; // xmm1
  __int128 v24; // xmm0
  char v25; // al
  _BYTE v27[480]; // [rsp+20h] [rbp-218h] BYREF

  v9 = 0;
  memset_0(v27, 0, 0x1D1u);
  v27[2] = 15;
  started = transportDec_CrcStartReg(a2, 0);
  CProgramConfig_Read((struct CProgramConfig *)v27, a1, a5);
  transportDec_CrcEndReg(a2, started);
  if ( v27[461] && v27[1] == 1 )
  {
    if ( *((_BYTE *)a3 + 461) )
      goto LABEL_7;
    if ( a4 )
      CProgramConfig_GetDefault(a3, a4);
    if ( *((_BYTE *)a3 + 461) )
    {
LABEL_7:
      v11 = CProgramConfig_Compare(a3, (const struct CProgramConfig *const)v27);
      if ( v11 == 1 )
      {
        v12 = 3;
        v13 = v27;
        do
        {
          v14 = v13[1];
          *(_OWORD *)a3 = *v13;
          v15 = v13[2];
          *((_OWORD *)a3 + 1) = v14;
          v16 = v13[3];
          *((_OWORD *)a3 + 2) = v15;
          v17 = v13[4];
          *((_OWORD *)a3 + 3) = v16;
          v18 = v13[5];
          *((_OWORD *)a3 + 4) = v17;
          v19 = v13[6];
          *((_OWORD *)a3 + 5) = v18;
          v20 = v13[7];
          v13 += 8;
          *((_OWORD *)a3 + 6) = v19;
          *((_OWORD *)a3 + 7) = v20;
          a3 = (struct CProgramConfig *)((char *)a3 + 128);
          --v12;
        }
        while ( v12 );
        v9 = 1;
        v21 = v13[1];
        *(_OWORD *)a3 = *v13;
        v22 = v13[2];
        *((_OWORD *)a3 + 1) = v21;
        v23 = v13[3];
        *((_OWORD *)a3 + 2) = v22;
        v24 = v13[4];
        v25 = *((_BYTE *)v13 + 80);
        *((_OWORD *)a3 + 3) = v23;
        *((_OWORD *)a3 + 4) = v24;
        *((_BYTE *)a3 + 80) = v25;
      }
      else if ( v11 == -1 || v11 == 2 )
      {
        return (unsigned int)-1;
      }
    }
  }
  return v9;
}

```

## disassembly

```asm
0x180012bf8  mov     [rsp+arg_18], rbx
0x180012bfd  push    rbp
0x180012bfe  push    rsi
0x180012bff  push    rdi
0x180012c00  push    r14
0x180012c02  push    r15
0x180012c04  sub     rsp, 210h
0x180012c0b  mov     rax, cs:__security_cookie
0x180012c12  xor     rax, rsp
0x180012c15  mov     [rsp+238h+var_38], rax
0x180012c1d  mov     rbp, r8
0x180012c20  mov     rsi, rdx
0x180012c23  mov     rdi, rcx
0x180012c26  xor     edx, edx; Val
0x180012c28  mov     r8d, 1D1h; Size
0x180012c2e  lea     rcx, [rsp+238h+var_218]; void *
0x180012c33  mov     r15d, r9d
0x180012c36  xor     r14d, r14d
0x180012c39  call    memset_0
0x180012c3e  xor     edx, edx; int
0x180012c40  mov     [rsp+238h+var_216], 0Fh
0x180012c45  mov     rcx, rsi; struct TRANSPORTDEC *
0x180012c48  call    ?transportDec_CrcStartReg@@YAHQEAUTRANSPORTDEC@@H@Z; transportDec_CrcStartReg(TRANSPORTDEC * const,int)
0x180012c4d  mov     r8d, [rsp+238h+arg_20]; unsigned int
0x180012c55  lea     rcx, [rsp+238h+var_218]; struct CProgramConfig *
0x180012c5a  mov     rdx, rdi; struct CDK_BITSTREAM *
0x180012c5d  mov     ebx, eax
0x180012c5f  call    ?CProgramConfig_Read@@YAXPEAUCProgramConfig@@PEAUCDK_BITSTREAM@@I@Z; CProgramConfig_Read(CProgramConfig *,CDK_BITSTREAM *,uint)
0x180012c64  mov     edx, ebx; int
0x180012c66  mov     rcx, rsi; struct TRANSPORTDEC *
0x180012c69  call    ?transportDec_CrcEndReg@@YAXQEAUTRANSPORTDEC@@H@Z; transportDec_CrcEndReg(TRANSPORTDEC * const,int)
0x180012c6e  cmp     [rsp+238h+var_4B], r14b
0x180012c76  jz      loc_180012D4C
0x180012c7c  cmp     [rsp+238h+var_217], 1
0x180012c81  jnz     loc_180012D4C
0x180012c87  cmp     [rbp+1CDh], r14b
0x180012c8e  jnz     short loc_180012CAD
0x180012c90  test    r15d, r15d
0x180012c93  jz      short loc_180012CA0
0x180012c95  mov     edx, r15d; unsigned int
0x180012c98  mov     rcx, rbp; struct CProgramConfig *
0x180012c9b  call    ?CProgramConfig_GetDefault@@YAXPEAUCProgramConfig@@I@Z; CProgramConfig_GetDefault(CProgramConfig *,uint)
0x180012ca0  cmp     [rbp+1CDh], r14b
0x180012ca7  jz      loc_180012D4C
0x180012cad  lea     rdx, [rsp+238h+var_218]; struct CProgramConfig *
0x180012cb2  mov     rcx, rbp; struct CProgramConfig *
0x180012cb5  call    ?CProgramConfig_Compare@@YAHQEBUCProgramConfig@@0@Z; CProgramConfig_Compare(CProgramConfig const * const,CProgramConfig const * const)
0x180012cba  cmp     eax, 1
0x180012cbd  jnz     loc_180012D77
0x180012cc3  mov     ecx, 3
0x180012cc8  lea     rax, [rsp+238h+var_218]
0x180012ccd  lea     edx, [rcx+7Dh]
0x180012cd0  movups  xmm0, xmmword ptr [rax]
0x180012cd3  movups  xmm1, xmmword ptr [rax+10h]
0x180012cd7  movups  xmmword ptr [rbp+0], xmm0
0x180012cdb  movups  xmm0, xmmword ptr [rax+20h]
0x180012cdf  movups  xmmword ptr [rbp+10h], xmm1
0x180012ce3  movups  xmm1, xmmword ptr [rax+30h]
0x180012ce7  movups  xmmword ptr [rbp+20h], xmm0
0x180012ceb  movups  xmm0, xmmword ptr [rax+40h]
0x180012cef  movups  xmmword ptr [rbp+30h], xmm1
0x180012cf3  movups  xmm1, xmmword ptr [rax+50h]
0x180012cf7  movups  xmmword ptr [rbp+40h], xmm0
0x180012cfb  movups  xmm0, xmmword ptr [rax+60h]
0x180012cff  movups  xmmword ptr [rbp+50h], xmm1
0x180012d03  movups  xmm1, xmmword ptr [rax+70h]
0x180012d07  add     rax, rdx
0x180012d0a  movups  xmmword ptr [rbp+60h], xmm0
0x180012d0e  movups  xmmword ptr [rbp+70h], xmm1
0x180012d12  add     rbp, rdx
0x180012d15  sub     rcx, 1
0x180012d19  jnz     short loc_180012CD0
0x180012d1b  movups  xmm0, xmmword ptr [rax]
0x180012d1e  lea     r14d, [rcx+1]
0x180012d22  movups  xmm1, xmmword ptr [rax+10h]
0x180012d26  movups  xmmword ptr [rbp+0], xmm0
0x180012d2a  movups  xmm0, xmmword ptr [rax+20h]
0x180012d2e  movups  xmmword ptr [rbp+10h], xmm1
0x180012d32  movups  xmm1, xmmword ptr [rax+30h]
0x180012d36  movups  xmmword ptr [rbp+20h], xmm0
0x180012d3a  movups  xmm0, xmmword ptr [rax+40h]
0x180012d3e  mov     al, [rax+50h]
0x180012d41  movups  xmmword ptr [rbp+30h], xmm1
0x180012d45  movups  xmmword ptr [rbp+40h], xmm0
0x180012d49  mov     [rbp+50h], al
0x180012d4c  mov     eax, r14d
0x180012d4f  mov     rcx, [rsp+238h+var_38]
0x180012d57  xor     rcx, rsp; StackCookie
0x180012d5a  call    __security_check_cookie
0x180012d5f  mov     rbx, [rsp+238h+arg_18]
0x180012d67  add     rsp, 210h
0x180012d6e  pop     r15
0x180012d70  pop     r14
0x180012d72  pop     rdi
0x180012d73  pop     rsi
0x180012d74  pop     rbp
0x180012d75  retn
0x180012d77  cmp     eax, 0FFFFFFFFh
0x180012d7a  jz      short loc_180012D81
0x180012d7c  cmp     eax, 2
0x180012d7f  jnz     short loc_180012D4C
0x180012d81  or      r14d, 0FFFFFFFFh
0x180012d85  jmp     short loc_180012D4C
```
