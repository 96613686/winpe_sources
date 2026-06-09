# MSCryptEccSetAlgProperty

- ea: `0x1800216d8`
- end: `0x180021a39`
- name: `MSCryptEccSetAlgProperty`
- size: `865`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180021c50`
- `0x180021de0`

## callees

- `0x18000ecb0`
- `0x18000ee60`
- `0x1800216d8`
- `0x180022340`
- `0x1800228b0`
- `0x18007f765`

## string_xrefs

- `0x1800216ec`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`
- `0x1800217ae`: `onecore\ds\security\cryptoapi\ncrypt\msprim\ecc\ecc.c`

## pseudocode

```c
__int64 __fastcall MSCryptEccSetAlgProperty(__int64 a1, wchar_t **a2, _DWORD *a3, unsigned int a4, int a5)
{
  unsigned __int64 v5; // rdi
  _DWORD *v6; // r12
  const wchar_t *v7; // r15
  unsigned int v9; // ecx
  unsigned int v10; // r13d
  _WORD *v11; // rdx
  int v12; // r8d
  unsigned __int64 v13; // rax
  unsigned __int64 v14; // rcx
  int Curve; // eax
  unsigned int v16; // ebx
  _QWORD *v18; // rcx
  _QWORD *v19; // rcx
  __int64 v20; // r9
  __int64 v21; // rcx
  char v22; // [rsp+30h] [rbp-58h]

  v5 = a4;
  v6 = a3;
  v7 = (const wchar_t *)a2;
  if ( !a1 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        231);
      goto LABEL_32;
    }
LABEL_26:
    v16 = -1073741811;
    if ( v18 != &WPP_GLOBAL_Control && (*((_BYTE *)v18 + 28) & 1) != 0 )
      WPP_SF_sDsd(
        v18[2],
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        29);
    return v16;
  }
  if ( *(_DWORD *)(a1 + 4) != 1297301836 || *(_DWORD *)a1 != 24 )
  {
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        241);
LABEL_32:
      v18 = WPP_GLOBAL_Control;
      goto LABEL_26;
    }
    goto LABEL_26;
  }
  a2 = &off_180084710;
  v9 = 0;
  if ( !a5 )
    a2 = &off_1800847D0;
  while ( 1 )
  {
    if ( v9 >= 4 )
      goto LABEL_29;
    v10 = *(_DWORD *)(a1 + 8);
    LODWORD(a3) = 6 * v9;
    if ( v10 == LODWORD(a2[6 * v9 + 1]) )
      break;
    ++v9;
  }
  if ( !a2[6 * v9] )
  {
LABEL_29:
    v18 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        (_DWORD)a2,
        (_DWORD)a3,
        (unsigned int)"Status",
        13,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        249);
      goto LABEL_32;
    }
    goto LABEL_26;
  }
  if ( !wcscmp_0(v7, L"ECCParameters") )
  {
    if ( *(_QWORD *)(a1 + 16) )
    {
      v16 = -1073741637;
      v20 = 3883;
      v21 = 3221225659LL;
      goto LABEL_50;
    }
    Curve = AssignGenericDomainParameters((_QWORD *)(a1 + 16), v10, v6, v5, 0, 0);
    v16 = Curve;
    if ( Curve < 0 )
    {
      v20 = 3890;
LABEL_53:
      v21 = (unsigned int)Curve;
      goto LABEL_50;
    }
  }
  else if ( !wcscmp_0(v7, L"ECCCurveName") )
  {
    if ( !*(_QWORD *)(a1 + 16) )
    {
      if ( (unsigned int)v5 < 2 || !v6 )
        goto LABEL_47;
      v11 = v6;
      v13 = v5 >> 1;
      if ( v5 >> 1 )
      {
        while ( *v11 )
        {
          ++v11;
          if ( !--v13 )
            goto LABEL_18;
        }
        v14 = (v5 >> 1) - v13;
      }
      else
      {
LABEL_18:
        v14 = 0;
      }
      if ( v13 )
      {
        if ( v5 != 2 * v14 )
        {
          Curve = LoadCurve((_QWORD *)(a1 + 16), v10, (wchar_t *)v6, 2 * (int)v14 + 2);
          v16 = Curve;
          if ( Curve >= 0 )
            return v16;
          v20 = 3922;
          goto LABEL_53;
        }
        DebugTraceError(3221225485LL, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", 1048);
      }
      else
      {
LABEL_47:
        if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          WPP_SF_sDsd(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            (_DWORD)v11,
            v12,
            (unsigned int)"Status",
            13,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
            17);
      }
      v16 = -1073741811;
      v20 = 3915;
      v21 = 3221225485LL;
LABEL_50:
      DebugTraceError(v21, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c", v20);
      return v16;
    }
    v16 = -1073741637;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 67;
      goto LABEL_39;
    }
  }
  else
  {
    v16 = -1073741637;
    v19 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v22 = 89;
LABEL_39:
      WPP_SF_sDsd(
        v19[2],
        (_DWORD)v11,
        v12,
        (unsigned int)"Status",
        187,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\ecc\\ecc.c",
        v22);
    }
  }
  return v16;
}

```

## disassembly

```asm
0x1800216d8  push    rbx
0x1800216da  push    rbp
0x1800216db  push    rsi
0x1800216dc  push    rdi
0x1800216dd  push    r12
0x1800216df  push    r13
0x1800216e1  push    r14
0x1800216e3  push    r15
0x1800216e5  sub     rsp, 48h
0x1800216e9  mov     edi, r9d
0x1800216ec  lea     rbp, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800216f3  xor     r9d, r9d
0x1800216f6  lea     rsi, aStatus; "Status"
0x1800216fd  mov     r12, r8
0x180021700  mov     r15, rdx
0x180021703  mov     rbx, rcx
0x180021706  mov     r14d, 0C000000Dh
0x18002170c  test    rcx, rcx
0x18002170f  jz      loc_180021844
0x180021715  cmp     dword ptr [rcx+4], 4D53414Ch
0x18002171c  jnz     loc_1800218D1
0x180021722  cmp     dword ptr [rcx], 18h
0x180021725  jnz     loc_1800218D1
0x18002172b  cmp     [rsp+88h+arg_20], r9d
0x180021733  lea     rax, off_1800847D0; "ECDH_P256"
0x18002173a  lea     rdx, off_180084710; "ECDSA_P256"
0x180021741  mov     ecx, r9d
0x180021744  cmovz   rdx, rax
0x180021748  cmp     ecx, 4
0x18002174b  jnb     loc_180021891
0x180021751  mov     r13d, [rbx+8]
0x180021755  mov     eax, ecx
0x180021757  lea     r8, [rax+rax*2]
0x18002175b  add     r8, r8
0x18002175e  cmp     r13d, [rdx+r8*8+8]
0x180021763  jz      short loc_180021769
0x180021765  inc     ecx
0x180021767  jmp     short loc_180021748
0x180021769  cmp     [rdx+r8*8], r9
0x18002176d  jz      loc_180021891
0x180021773  lea     rdx, aEccparameters; "ECCParameters"
0x18002177a  mov     rcx, r15; String1
0x18002177d  call    wcscmp_0
0x180021782  xor     r14d, r14d
0x180021785  test    eax, eax
0x180021787  jz      loc_18002193C
0x18002178d  lea     rdx, aEcccurvename; "ECCCurveName"
0x180021794  mov     rcx, r15; String1
0x180021797  call    wcscmp_0
0x18002179c  test    eax, eax
0x18002179e  jnz     loc_1800218FC
0x1800217a4  cmp     [rbx+10h], r14
0x1800217a8  jnz     loc_180021973
0x1800217ae  lea     rbp, aOnecoreDsSecur_25; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800217b5  mov     r14d, 0C000000Dh
0x1800217bb  lea     rsi, aStatus; "Status"
0x1800217c2  cmp     edi, 2
0x1800217c5  jb      loc_1800219A3
0x1800217cb  xor     r15d, r15d
0x1800217ce  test    r12, r12
0x1800217d1  jz      loc_1800219A3
0x1800217d7  mov     rax, rdi
0x1800217da  mov     rdx, r12
0x1800217dd  shr     rax, 1
0x1800217e0  mov     rcx, rax
0x1800217e3  jz      short loc_1800217F5
0x1800217e5  cmp     [rdx], r15w
0x1800217e9  jz      short loc_1800217FA
0x1800217eb  add     rdx, 2
0x1800217ef  sub     rax, 1
0x1800217f3  jnz     short loc_1800217E5
0x1800217f5  mov     rcx, r15
0x1800217f8  jmp     short loc_1800217FD
0x1800217fa  sub     rcx, rax
0x1800217fd  test    rax, rax
0x180021800  jz      loc_1800219A3
0x180021806  lea     r9, [rcx+rcx]
0x18002180a  cmp     rdi, r9
0x18002180d  jz      loc_1800219F6
0x180021813  add     r9d, 2
0x180021817  lea     rcx, [rbx+10h]
0x18002181b  mov     r8, r12
0x18002181e  mov     edx, r13d
0x180021821  call    LoadCurve
0x180021826  mov     ebx, eax
0x180021828  test    eax, eax
0x18002182a  js      loc_1800219EC
0x180021830  mov     eax, ebx
0x180021832  add     rsp, 48h
0x180021836  pop     r15
0x180021838  pop     r14
0x18002183a  pop     r13
0x18002183c  pop     r12
0x18002183e  pop     rdi
0x18002183f  pop     rsi
0x180021840  pop     rbp
0x180021841  pop     rbx
0x180021842  retn
0x180021844  mov     rcx, cs:WPP_GLOBAL_Control
0x18002184b  lea     rdi, WPP_GLOBAL_Control
0x180021852  cmp     rcx, rdi
0x180021855  jz      short loc_180021861
0x180021857  test    byte ptr [rcx+1Ch], 1
0x18002185b  jnz     loc_180021A2C
0x180021861  mov     ebx, 0C000000Dh
0x180021866  cmp     rcx, rdi
0x180021869  jz      short loc_180021830
0x18002186b  test    byte ptr [rcx+1Ch], 1
0x18002186f  jz      short loc_180021830
0x180021871  mov     dword ptr [rsp+88h+var_58], 0F1Dh
0x180021879  mov     [rsp+88h+var_60], rbp
0x18002187e  mov     dword ptr [rsp+88h+var_68], r14d
0x180021883  mov     rcx, [rcx+10h]
0x180021887  mov     r9, rsi
0x18002188a  call    WPP_SF_sDsd
0x18002188f  jmp     short loc_180021830
0x180021891  mov     rcx, cs:WPP_GLOBAL_Control
0x180021898  lea     rdi, WPP_GLOBAL_Control
0x18002189f  cmp     rcx, rdi
0x1800218a2  jz      short loc_180021861
0x1800218a4  test    byte ptr [rcx+1Ch], 1
0x1800218a8  jz      short loc_180021861
0x1800218aa  mov     dword ptr [rsp+88h+var_58], 1F9h
0x1800218b2  mov     rcx, [rcx+10h]
0x1800218b6  mov     r9, rsi
0x1800218b9  mov     [rsp+88h+var_60], rbp
0x1800218be  mov     dword ptr [rsp+88h+var_68], r14d
0x1800218c3  call    WPP_SF_sDsd
0x1800218c8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218cf  jmp     short loc_180021861
0x1800218d1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800218d8  lea     rdi, WPP_GLOBAL_Control
0x1800218df  cmp     rcx, rdi
0x1800218e2  jz      loc_180021861
0x1800218e8  test    byte ptr [rcx+1Ch], 1
0x1800218ec  jz      loc_180021861
0x1800218f2  mov     dword ptr [rsp+88h+var_58], 1F1h
0x1800218fa  jmp     short loc_1800218B2
0x1800218fc  mov     ebx, 0C00000BBh
0x180021901  mov     rcx, cs:WPP_GLOBAL_Control
0x180021908  lea     rdi, WPP_GLOBAL_Control
0x18002190f  cmp     rcx, rdi
0x180021912  jz      loc_180021830
0x180021918  test    byte ptr [rcx+1Ch], 1
0x18002191c  jz      loc_180021830
0x180021922  mov     dword ptr [rsp+88h+var_58], 0F59h
0x18002192a  mov     [rsp+88h+var_60], rbp
0x18002192f  mov     dword ptr [rsp+88h+var_68], 0C00000BBh
0x180021937  jmp     loc_180021883
0x18002193c  lea     rcx, [rbx+10h]
0x180021940  cmp     [rcx], r14
0x180021943  jnz     loc_1800219DA
0x180021949  mov     dword ptr [rsp+88h+var_60], r14d
0x18002194e  mov     r9d, edi
0x180021951  mov     r8, r12
0x180021954  mov     [rsp+88h+var_68], r14
0x180021959  mov     edx, r13d
0x18002195c  call    AssignGenericDomainParameters
0x180021961  mov     ebx, eax
0x180021963  test    eax, eax
0x180021965  jns     loc_180021830
0x18002196b  mov     r9d, 0F32h
0x180021971  jmp     short loc_1800219F2
0x180021973  mov     ebx, 0C00000BBh
0x180021978  mov     rcx, cs:WPP_GLOBAL_Control
0x18002197f  lea     rdi, WPP_GLOBAL_Control
0x180021986  cmp     rcx, rdi
0x180021989  jz      loc_180021830
0x18002198f  test    byte ptr [rcx+1Ch], 1
0x180021993  jz      loc_180021830
0x180021999  mov     dword ptr [rsp+88h+var_58], 0F43h
0x1800219a1  jmp     short loc_18002192A
0x1800219a3  mov     rcx, cs:WPP_GLOBAL_Control
0x1800219aa  lea     rdi, WPP_GLOBAL_Control
0x1800219b1  cmp     rcx, rdi
0x1800219b4  jz      short loc_1800219BC
0x1800219b6  test    byte ptr [rcx+1Ch], 1
0x1800219ba  jnz     short loc_180021A0C
0x1800219bc  mov     ebx, 0C000000Dh
0x1800219c1  mov     r9d, 0F4Bh
0x1800219c7  mov     ecx, r14d
0x1800219ca  mov     r8, rbp
0x1800219cd  mov     rdx, rsi
0x1800219d0  call    DebugTraceError
0x1800219d5  jmp     loc_180021830
0x1800219da  mov     ebx, 0C00000BBh
0x1800219df  mov     r9d, 0F2Bh
0x1800219e5  mov     ecx, 0C00000BBh
0x1800219ea  jmp     short loc_1800219CA
0x1800219ec  mov     r9d, 0F52h
0x1800219f2  mov     ecx, eax
0x1800219f4  jmp     short loc_1800219CA
0x1800219f6  mov     r9d, 418h
0x1800219fc  mov     r8, rbp
0x1800219ff  mov     rdx, rsi
0x180021a02  mov     ecx, r14d
0x180021a05  call    DebugTraceError
0x180021a0a  jmp     short loc_1800219BC
0x180021a0c  mov     rcx, [rcx+10h]
0x180021a10  mov     r9, rsi
0x180021a13  mov     dword ptr [rsp+88h+var_58], 411h
0x180021a1b  mov     [rsp+88h+var_60], rbp
0x180021a20  mov     dword ptr [rsp+88h+var_68], r14d
0x180021a25  call    WPP_SF_sDsd
0x180021a2a  jmp     short loc_1800219BC
0x180021a2c  mov     dword ptr [rsp+88h+var_58], 1E7h
0x180021a34  jmp     loc_1800218B2
```
