# MSCryptEcDhSecretAgreement

- ea: `0x18001fad0`
- end: `0x18001ff91`
- name: `MSCryptEcDhSecretAgreement`
- size: `1217`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `broker_com_uri`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x18001fad0`
- `0x18001ffa0`
- `0x180020210`
- `0x180020408`
- `0x1800215e4`
- `0x180056cf0`
- `0x180063180`
- `0x18007f790`

## string_xrefs

- `0x18001ff77`: `onecore\ds\security\cryptoapi\ncrypt\common\audit.c`
- `0x18001fb23`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEcDhSecretAgreement(__int64 a1, int a2, _QWORD *a3, int a4)
{
  unsigned int i; // edx
  _QWORD *v9; // r8
  int v10; // ecx
  __int64 v11; // rax
  __int64 v12; // rdi
  int v13; // eax
  int v14; // edx
  int v15; // r8d
  int v16; // r9d
  unsigned int v17; // ebp
  __int64 v18; // rbx
  unsigned int v19; // eax
  int Secret; // eax
  int v21; // edx
  int v22; // r8d
  _QWORD *v23; // rcx
  __int64 v24; // rcx
  _BYTE *v25; // rax
  wchar_t *v26; // r10
  unsigned int j; // ecx
  __int64 k; // rcx
  int v29; // eax
  unsigned int v31; // eax
  int v32; // edx
  int v33; // r8d
  __int64 v34; // [rsp+40h] [rbp-E8h] BYREF
  __int64 v35; // [rsp+48h] [rbp-E0h]
  _BYTE Src[144]; // [rsp+50h] [rbp-D8h] BYREF

  v34 = 0;
  v35 = 0;
  memset_0(Src, 0, 0x84u);
  if ( !a1 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      i,
      (_DWORD)v9,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      51);
LABEL_21:
    v23 = WPP_GLOBAL_Control;
    goto LABEL_22;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297304409 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      i,
      (_DWORD)v9,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      60);
    goto LABEL_21;
  }
  v9 = *(_QWORD **)(a1 + 16);
  if ( !v9 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control == (_UNKNOWN *)&WPP_GLOBAL_Control || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0 )
      goto LABEL_22;
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      i,
      0,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      67);
    goto LABEL_21;
  }
  for ( i = 0; ; ++i )
  {
    if ( i >= 4 )
    {
      v23 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          i,
          (_DWORD)v9,
          (unsigned int)"Status",
          13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          116);
        goto LABEL_21;
      }
      goto LABEL_22;
    }
    if ( *(_DWORD *)(a1 + 8) == *((_DWORD *)&off_1800847D0 + 12 * i + 2) )
      break;
  }
  i = *((_DWORD *)&off_1800847D0 + 12 * i + 5);
  v10 = *(_DWORD *)(*v9 + 12LL);
  if ( i )
  {
    if ( i != v10 )
    {
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 613);
      goto LABEL_21;
    }
  }
  else if ( (unsigned int)(v10 - 14) > 0x34 )
  {
    v23 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        0,
        (_DWORD)v9,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        91);
      goto LABEL_21;
    }
    goto LABEL_22;
  }
  v11 = *(_QWORD *)(a1 + 24);
  if ( v11 && *(_BYTE *)(v11 + 4) )
  {
    v12 = *(unsigned int *)(v9[1] + 20LL);
    v13 = ValidateEccKey(a2, 0, 0, 1, (__int64)&v34);
    v17 = v13;
    if ( v13 < 0 )
    {
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v14,
          v15,
          (unsigned int)"Status",
          v13,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
          92);
    }
    else if ( !a3 || a4 )
    {
      v17 = -1073741811;
      DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 4453);
    }
    else if ( (*(_BYTE *)(a1 + 32) & 2) != 0 && (v18 = v34, (*(_BYTE *)(v34 + 32) & 2) != 0) )
    {
      v19 = SymCryptEcDhSecretAgreement(
              *(_QWORD *)(a1 + 24),
              *(_QWORD *)(v34 + 24),
              (unsigned int)(*(_DWORD *)(**(_QWORD **)(a1 + 16) + 4LL) != 3) + 1,
              v16,
              Src,
              v12);
      if ( v19 )
      {
        v31 = SymcryptErrorCodeToNtStatus(v19);
        v17 = v31;
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            v32,
            v33,
            (unsigned int)"Status",
            v31,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            130);
      }
      else
      {
        Secret = MSCryptCreateSecret(Src, (unsigned int)v12, *(_DWORD *)(v18 + 8));
        v17 = Secret;
        if ( Secret < 0 )
        {
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v21,
              v22,
              (unsigned int)"Status",
              Secret,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
              140);
        }
        else
        {
          *a3 = v35;
        }
      }
    }
    else
    {
      v17 = -1073741816;
      DebugTraceError(3221225480LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 4461);
    }
    goto LABEL_25;
  }
  v23 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
  {
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      i,
      (_DWORD)v9,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      125);
    goto LABEL_21;
  }
LABEL_22:
  a1 = 0;
  v17 = -1073741811;
  if ( v23 != &WPP_GLOBAL_Control && (*((_BYTE *)v23 + 28) & 1) != 0 )
    WPP_SF_sDsd(
      v23[2],
      i,
      (_DWORD)v9,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
      80);
LABEL_25:
  v24 = 132;
  v25 = Src;
  do
  {
    *v25++ = 0;
    --v24;
  }
  while ( v24 );
  v26 = 0;
  for ( j = 0; j < 4; ++j )
  {
    if ( *(_DWORD *)(a1 + 8) == *((_DWORD *)&off_1800847D0 + 12 * j + 2) )
    {
      v26 = (&off_1800847D0)[6 * j];
      break;
    }
  }
  for ( k = 0; (unsigned int)k < 0x84; k = (unsigned int)(k + 1) )
  {
    if ( Src[(unsigned int)k] )
    {
      v29 = MSCryptAuditPrimitiveFailure(k, v26, 2438, 0);
      if ( v29 < 0 )
        DebugTraceError((unsigned int)v29, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\audit.c", 491);
      return v17;
    }
  }
  return v17;
}

```

## disassembly

```asm
0x18001fad0  mov     [rsp+arg_0], rbx
0x18001fad5  push    rbp
0x18001fad6  push    rsi
0x18001fad7  push    rdi
0x18001fad8  push    r12
0x18001fada  push    r13
0x18001fadc  push    r14
0x18001fade  push    r15
0x18001fae0  sub     rsp, 0F0h
0x18001fae7  mov     rax, cs:__security_cookie
0x18001faee  xor     rax, rsp
0x18001faf1  mov     [rsp+128h+var_48], rax
0x18001faf9  mov     rsi, r8
0x18001fafc  mov     rbp, rdx
0x18001faff  mov     r14, rcx
0x18001fb02  xor     edi, edi
0x18001fb04  xor     edx, edx; Val
0x18001fb06  mov     [rsp+128h+var_E8], rdi
0x18001fb0b  mov     r8d, 84h; Size
0x18001fb11  mov     [rsp+128h+var_E0], rdi
0x18001fb16  lea     rcx, [rsp+128h+Src]; void *
0x18001fb1b  mov     ebx, r9d
0x18001fb1e  call    memset_0
0x18001fb23  lea     r12, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001fb2a  lea     r13, off_1800847D0; "ECDH_P256"
0x18001fb31  lea     r15, WPP_GLOBAL_Control
0x18001fb38  test    r14, r14
0x18001fb3b  jz      loc_18001FD62
0x18001fb41  cmp     dword ptr [r14+4], 4D534B59h
0x18001fb49  jnz     loc_18001FDAB
0x18001fb4f  mov     r8, [r14+10h]
0x18001fb53  test    r8, r8
0x18001fb56  jz      loc_18001FDD2
0x18001fb5c  mov     edx, edi
0x18001fb5e  xchg    ax, ax
0x18001fb60  cmp     edx, 4
0x18001fb63  jnb     loc_18001FF02
0x18001fb69  mov     eax, edx
0x18001fb6b  lea     rcx, [rax+rax*2]
0x18001fb6f  add     rcx, rcx
0x18001fb72  mov     eax, [r13+rcx*8+8]
0x18001fb77  cmp     [r14+8], eax
0x18001fb7b  jz      short loc_18001FB81
0x18001fb7d  inc     edx
0x18001fb7f  jmp     short loc_18001FB60
0x18001fb81  mov     edx, [r13+rcx*8+14h]
0x18001fb86  mov     rax, [r8]
0x18001fb89  mov     ecx, [rax+0Ch]
0x18001fb8c  test    edx, edx
0x18001fb8e  jnz     loc_18001FDF9
0x18001fb94  lea     eax, [rcx-0Eh]
0x18001fb97  cmp     eax, 34h ; '4'
0x18001fb9a  ja      loc_18001FE8D
0x18001fba0  mov     rax, [r14+18h]
0x18001fba4  test    rax, rax
0x18001fba7  jz      loc_18001FEDB
0x18001fbad  cmp     [rax+4], dil
0x18001fbb1  jz      loc_18001FEDB
0x18001fbb7  mov     rax, [r8+8]
0x18001fbbb  mov     r9d, 1
0x18001fbc1  xor     r8d, r8d
0x18001fbc4  xor     edx, edx
0x18001fbc6  mov     rcx, rbp
0x18001fbc9  mov     edi, [rax+14h]
0x18001fbcc  lea     rax, [rsp+128h+var_E8]
0x18001fbd1  mov     [rsp+128h+var_108], rax
0x18001fbd6  call    ValidateEccKey
0x18001fbdb  mov     ebp, eax
0x18001fbdd  test    eax, eax
0x18001fbdf  js      loc_18001FEB4
0x18001fbe5  test    rsi, rsi
0x18001fbe8  jz      loc_18001FF4D
0x18001fbee  test    ebx, ebx
0x18001fbf0  jnz     loc_18001FF4D
0x18001fbf6  test    byte ptr [r14+20h], 2
0x18001fbfb  jz      loc_18001FF29
0x18001fc01  mov     rbx, [rsp+128h+var_E8]
0x18001fc06  test    byte ptr [rbx+20h], 2
0x18001fc0a  jz      loc_18001FF29
0x18001fc10  mov     rax, [r14+10h]
0x18001fc14  xor     r8d, r8d
0x18001fc17  mov     rdx, [rbx+18h]; int
0x18001fc1b  mov     [rsp+128h+var_100], rdi; __int64
0x18001fc20  mov     rcx, [rax]
0x18001fc23  lea     rax, [rsp+128h+Src]
0x18001fc28  mov     [rsp+128h+var_108], rax; void *
0x18001fc2d  cmp     dword ptr [rcx+4], 3
0x18001fc31  mov     rcx, [r14+18h]; int
0x18001fc35  setnz   r8b
0x18001fc39  inc     r8d; int
0x18001fc3c  call    SymCryptEcDhSecretAgreement
0x18001fc41  test    eax, eax
0x18001fc43  jnz     loc_18001FE20
0x18001fc49  mov     eax, [rbx+8]
0x18001fc4c  lea     r8, [rsp+128h+var_E0]
0x18001fc51  mov     edx, edi; Size
0x18001fc53  mov     dword ptr [rsp+128h+var_108], eax; int
0x18001fc57  lea     rcx, [rsp+128h+Src]; Src
0x18001fc5c  call    MSCryptCreateSecret
0x18001fc61  mov     ebp, eax
0x18001fc63  test    eax, eax
0x18001fc65  js      loc_18001FE69
0x18001fc6b  mov     rax, [rsp+128h+var_E0]
0x18001fc70  mov     [rsi], rax
0x18001fc73  xor     edi, edi
0x18001fc75  jmp     short loc_18001FCBA
0x18001fc77  mov     [rsp+128h+var_F8], 233h
0x18001fc7f  mov     rcx, [rcx+10h]
0x18001fc83  lea     r9, aStatus; "Status"
0x18001fc8a  mov     [rsp+128h+var_100], r12
0x18001fc8f  mov     dword ptr [rsp+128h+var_108], 0C000000Dh
0x18001fc97  call    WPP_SF_sDsd
0x18001fc9c  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fca3  mov     r14, rdi
0x18001fca6  mov     ebp, 0C000000Dh
0x18001fcab  cmp     rcx, r15
0x18001fcae  jz      short loc_18001FCBA
0x18001fcb0  test    byte ptr [rcx+1Ch], 1
0x18001fcb4  jnz     loc_18001FD81
0x18001fcba  mov     ecx, 84h
0x18001fcbf  lea     rax, [rsp+128h+Src]
0x18001fcc4  nop     dword ptr [rax+00h]
0x18001fcc8  nop     dword ptr [rax+rax+00000000h]
0x18001fcd0  mov     byte ptr [rax], 0
0x18001fcd3  lea     rax, [rax+1]
0x18001fcd7  sub     rcx, 1
0x18001fcdb  jnz     short loc_18001FCD0
0x18001fcdd  mov     r10, rdi
0x18001fce0  mov     ecx, edi
0x18001fce2  cmp     ecx, 4
0x18001fce5  jnb     short loc_18001FD04
0x18001fce7  mov     eax, ecx
0x18001fce9  lea     rdx, [rax+rax*2]
0x18001fced  add     rdx, rdx
0x18001fcf0  mov     eax, [r13+rdx*8+8]
0x18001fcf5  cmp     [r14+8], eax
0x18001fcf9  jz      short loc_18001FCFF
0x18001fcfb  inc     ecx
0x18001fcfd  jmp     short loc_18001FCE2
0x18001fcff  mov     r10, [r13+rdx*8+0]
0x18001fd04  mov     ecx, edi
0x18001fd06  cmp     ecx, 84h
0x18001fd0c  jnb     short loc_18001FD34
0x18001fd0e  mov     eax, ecx
0x18001fd10  cmp     [rsp+rax+128h+Src], 0
0x18001fd15  jnz     short loc_18001FD1B
0x18001fd17  inc     ecx
0x18001fd19  jmp     short loc_18001FD06
0x18001fd1b  xor     r9d, r9d
0x18001fd1e  mov     r8d, 986h
0x18001fd24  mov     rdx, r10
0x18001fd27  call    MSCryptAuditPrimitiveFailure
0x18001fd2c  test    eax, eax
0x18001fd2e  js      loc_18001FF71
0x18001fd34  mov     eax, ebp
0x18001fd36  mov     rcx, [rsp+128h+var_48]
0x18001fd3e  xor     rcx, rsp; StackCookie
0x18001fd41  call    __security_check_cookie
0x18001fd46  mov     rbx, [rsp+128h+arg_0]
0x18001fd4e  add     rsp, 0F0h
0x18001fd55  pop     r15
0x18001fd57  pop     r14
0x18001fd59  pop     r13
0x18001fd5b  pop     r12
0x18001fd5d  pop     rdi
0x18001fd5e  pop     rsi
0x18001fd5f  pop     rbp
0x18001fd60  retn
0x18001fd62  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fd69  cmp     rcx, r15
0x18001fd6c  jz      loc_18001FCA3
0x18001fd72  test    byte ptr [rcx+1Ch], 1
0x18001fd76  jz      loc_18001FCA3
0x18001fd7c  jmp     loc_18001FC77
0x18001fd81  mov     rcx, [rcx+10h]
0x18001fd85  lea     r9, aStatus; "Status"
0x18001fd8c  mov     [rsp+128h+var_F8], 1150h
0x18001fd94  mov     [rsp+128h+var_100], r12
0x18001fd99  mov     dword ptr [rsp+128h+var_108], 0C000000Dh
0x18001fda1  call    WPP_SF_sDsd
0x18001fda6  jmp     loc_18001FCBA
0x18001fdab  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdb2  cmp     rcx, r15
0x18001fdb5  jz      loc_18001FCA3
0x18001fdbb  test    byte ptr [rcx+1Ch], 1
0x18001fdbf  jz      loc_18001FCA3
0x18001fdc5  mov     [rsp+128h+var_F8], 23Ch
0x18001fdcd  jmp     loc_18001FC7F
0x18001fdd2  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fdd9  cmp     rcx, r15
0x18001fddc  jz      loc_18001FCA3
0x18001fde2  test    byte ptr [rcx+1Ch], 1
0x18001fde6  jz      loc_18001FCA3
0x18001fdec  mov     [rsp+128h+var_F8], 243h
0x18001fdf4  jmp     loc_18001FC7F
0x18001fdf9  cmp     edx, ecx
0x18001fdfb  jz      loc_18001FBA0
0x18001fe01  mov     r9d, 265h
0x18001fe07  lea     rdx, aStatus; "Status"
0x18001fe0e  mov     r8, r12
0x18001fe11  mov     ecx, 0C000000Dh
0x18001fe16  call    DebugTraceError
0x18001fe1b  jmp     loc_18001FC9C
0x18001fe20  mov     ecx, eax
0x18001fe22  call    SymcryptErrorCodeToNtStatus
0x18001fe27  mov     ebp, eax
0x18001fe29  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe30  cmp     rcx, r15
0x18001fe33  jz      loc_18001FC73
0x18001fe39  test    byte ptr [rcx+1Ch], 1
0x18001fe3d  jz      loc_18001FC73
0x18001fe43  mov     [rsp+128h+var_F8], 1182h
0x18001fe4b  mov     rcx, [rcx+10h]
0x18001fe4f  lea     r9, aStatus; "Status"
0x18001fe56  mov     [rsp+128h+var_100], r12
0x18001fe5b  mov     dword ptr [rsp+128h+var_108], eax
0x18001fe5f  call    WPP_SF_sDsd
0x18001fe64  jmp     loc_18001FC73
0x18001fe69  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe70  cmp     rcx, r15
0x18001fe73  jz      loc_18001FC73
0x18001fe79  test    byte ptr [rcx+1Ch], 1
0x18001fe7d  jz      loc_18001FC73
0x18001fe83  mov     [rsp+128h+var_F8], 118Ch
0x18001fe8b  jmp     short loc_18001FE4B
0x18001fe8d  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fe94  cmp     rcx, r15
0x18001fe97  jz      loc_18001FCA3
0x18001fe9d  test    byte ptr [rcx+1Ch], 1
0x18001fea1  jz      loc_18001FCA3
0x18001fea7  mov     [rsp+128h+var_F8], 25Bh
0x18001feaf  jmp     loc_18001FC7F
0x18001feb4  mov     rcx, cs:WPP_GLOBAL_Control
0x18001febb  cmp     rcx, r15
0x18001febe  jz      loc_18001FC73
0x18001fec4  test    byte ptr [rcx+1Ch], 1
0x18001fec8  jz      loc_18001FC73
0x18001fece  mov     [rsp+128h+var_F8], 115Ch
0x18001fed6  jmp     loc_18001FE4B
0x18001fedb  mov     rcx, cs:WPP_GLOBAL_Control
0x18001fee2  cmp     rcx, r15
0x18001fee5  jz      loc_18001FCA3
0x18001feeb  test    byte ptr [rcx+1Ch], 1
0x18001feef  jz      loc_18001FCA3
0x18001fef5  mov     [rsp+128h+var_F8], 27Dh
0x18001fefd  jmp     loc_18001FC7F
0x18001ff02  mov     rcx, cs:WPP_GLOBAL_Control
0x18001ff09  cmp     rcx, r15
0x18001ff0c  jz      loc_18001FCA3
0x18001ff12  test    byte ptr [rcx+1Ch], 1
0x18001ff16  jz      loc_18001FCA3
0x18001ff1c  mov     [rsp+128h+var_F8], 274h
0x18001ff24  jmp     loc_18001FC7F
0x18001ff29  mov     r9d, 116Dh
0x18001ff2f  lea     rdx, aStatus; "Status"
0x18001ff36  mov     r8, r12
0x18001ff39  mov     ecx, 0C0000008h
0x18001ff3e  mov     ebp, 0C0000008h
0x18001ff43  call    DebugTraceError
0x18001ff48  jmp     loc_18001FC73
0x18001ff4d  mov     r9d, 1165h
0x18001ff53  lea     rdx, aStatus; "Status"
0x18001ff5a  mov     r8, r12
0x18001ff5d  mov     ecx, 0C000000Dh
0x18001ff62  mov     ebp, 0C000000Dh
0x18001ff67  call    DebugTraceError
0x18001ff6c  jmp     loc_18001FC73
0x18001ff71  mov     r9d, 1EBh
0x18001ff77  lea     r8, aOnecoreDsSecur_15; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001ff7e  lea     rdx, aStatus; "Status"
0x18001ff85  mov     ecx, eax
0x18001ff87  call    DebugTraceError
0x18001ff8c  jmp     loc_18001FD34
```
