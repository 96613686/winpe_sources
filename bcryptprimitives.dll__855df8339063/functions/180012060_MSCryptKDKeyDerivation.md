# MSCryptKDKeyDerivation

- ea: `0x180012060`
- end: `0x1800125d4`
- name: `MSCryptKDKeyDerivation`
- size: `1396`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x180053750`

## callees

- `0x18000ee60`
- `0x1800117d0`
- `0x180012060`
- `0x1800125dc`
- `0x180012ff4`
- `0x180053de4`
- `0x180058000`
- `0x180063170`
- `0x180063180`
- `0x18007f790`
- `0x180083010`

## string_xrefs

- `0x180012345`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800124f7`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x180012524`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\keyderivation.c`
- `0x1800123f1`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x180012578`: `onecore\ds\security\cryptoapi\ncrypt\msprim\keyderivation\kdfs.c`
- `0x1800123a7`: `onecore\ds\security\cryptoapi\ncrypt\kdf\hkdf.c`

## pseudocode

```c
__int64 __fastcall MSCryptKDKeyDerivation(_DWORD *a1, __int64 a2, char *a3, unsigned int a4, unsigned int *a5, int a6)
{
  unsigned int *v6; // rdi
  int v8; // edx
  unsigned __int64 v10; // rbx
  int v11; // eax
  _DWORD *v12; // r15
  int v13; // r14d
  unsigned int v14; // edx
  __int64 v15; // r8
  int i; // ecx
  __int64 v17; // r15
  size_t v18; // r13
  int v19; // r12d
  size_t v20; // r8
  _QWORD *v21; // rcx
  int v22; // esi
  char *v24; // rax
  size_t v25; // rsi
  char *v26; // rbx
  size_t v27; // r8
  unsigned int v28; // [rsp+48h] [rbp-C0h]
  __int64 v30; // [rsp+58h] [rbp-B0h]
  _DWORD *v31; // [rsp+60h] [rbp-A8h]
  _BYTE v32[16]; // [rsp+78h] [rbp-90h] BYREF
  _BYTE v33[4]; // [rsp+88h] [rbp-80h] BYREF
  int v34; // [rsp+8Ch] [rbp-7Ch]
  _QWORD Src[8]; // [rsp+198h] [rbp+90h] BYREF

  v6 = a5;
  v8 = a6;
  v10 = a4;
  if ( (a6 & 0xFFFFFFEF) == 0 )
  {
    if ( a1 )
    {
      if ( a1[1] == 1297304409 )
      {
        v11 = a1[2];
        if ( v11 != 393223 )
        {
          switch ( v11 )
          {
            case 393217:
              v22 = DeriveKeySP800108_CTR_HMAC((__int64)a1, a2, (__int64)a3, a4, a5, a6);
              goto LABEL_21;
            case 393218:
              v22 = DeriveKeySP80056A_CONCAT((_DWORD)a1, a2, (_DWORD)a3, a4, (__int64)a5, a6);
              goto LABEL_21;
            case 393219:
              v22 = DeriveKeyPBKDF2((__int64)a1, a2, a3, a4, a5, a6);
              goto LABEL_21;
            case 393220:
              v22 = DeriveKeyCAPI_KDF((_DWORD)a1, a2, (_DWORD)a3, a4, (__int64)a5, a6);
              goto LABEL_21;
            case 393221:
            case 393222:
              v22 = DeriveKeyTLS_KDF((_DWORD)a1, a2, (_DWORD)a3, a4, (__int64)a5, a6);
              goto LABEL_21;
            default:
              v21 = WPP_GLOBAL_Control;
              v22 = -1073741637;
              goto LABEL_40;
          }
        }
        if ( a6 || !a1[12] )
        {
          v22 = -1073741811;
          v21 = WPP_GLOBAL_Control;
          if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              a6,
              (_DWORD)a3,
              (unsigned int)"Status",
              13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
              25);
            goto LABEL_21;
          }
        }
        else
        {
          v12 = a1 + 20;
          v31 = a1 + 20;
          v13 = 0;
          v30 = 0;
          v28 = 0;
          if ( a2 )
          {
            v14 = *(_DWORD *)(a2 + 4);
            if ( v14 <= 0x7FFFFFFF )
            {
              v15 = *(_QWORD *)(a2 + 8);
              for ( i = 0; i < v14; ++i )
              {
                if ( *(_DWORD *)(v15 + 16LL * (unsigned int)i + 4) == 20 )
                {
                  if ( i >= 0 )
                  {
                    v30 = *(_QWORD *)(v15 + 16LL * i + 8);
                    v28 = *(_DWORD *)(v15 + 16LL * i);
                  }
                  break;
                }
              }
            }
          }
          v34 = 0;
          memset_0(v33, 0, 0x10Cu);
          v17 = *((_QWORD *)v12 + 68);
          v18 = *(_QWORD *)(v17 + 48);
          v32[0] = 1;
          if ( v10 > 255 * v18 )
          {
            v19 = 32771;
          }
          else
          {
            v19 = 0;
            (*(void (__fastcall **)(_BYTE *, _DWORD *))(v17 + 8))(v33, v31);
            (*(void (__fastcall **)(_BYTE *, __int64, _QWORD))(v17 + 16))(v33, v30, v28);
            (*(void (__fastcall **)(_BYTE *, _BYTE *, __int64))(v17 + 16))(v33, v32, 1);
            (*(void (__fastcall **)(_BYTE *, _QWORD *))(v17 + 24))(v33, Src);
            v20 = v10;
            if ( v10 >= v18 )
              v20 = v18;
            memcpy_0(a3, Src, v20);
            if ( v10 > v18 )
            {
              ++v32[0];
              v24 = &a3[v18];
              v25 = v10 - v18;
              if ( v10 != v18 )
              {
                v26 = v24;
                do
                {
                  (*(void (__fastcall **)(_BYTE *, _DWORD *))(v17 + 8))(v33, v31);
                  (*(void (__fastcall **)(_BYTE *, _QWORD *, size_t))(v17 + 16))(v33, Src, v18);
                  (*(void (__fastcall **)(_BYTE *, __int64, _QWORD))(v17 + 16))(v33, v30, v28);
                  (*(void (__fastcall **)(_BYTE *, _BYTE *, __int64))(v17 + 16))(v33, v32, 1);
                  (*(void (__fastcall **)(_BYTE *, _QWORD *))(v17 + 24))(v33, Src);
                  v27 = v25;
                  if ( v25 >= v18 )
                    v27 = v18;
                  memcpy_0(v26, Src, v27);
                  if ( v25 <= v18 )
                    break;
                  ++v32[0];
                  v26 += v18;
                  v25 -= v18;
                }
                while ( v25 );
                v13 = 0;
                v19 = 0;
                LODWORD(v10) = a4;
                v6 = a5;
              }
            }
          }
          v21 = WPP_GLOBAL_Control;
          memset(Src, 0, sizeof(Src));
          if ( v19
            && (v22 = -1073741823, v13 = -1073741823, WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control)
            && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              v8,
              (_DWORD)a3,
              (unsigned int)"Status",
              1,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\kdf\\hkdf.c",
              69);
            v21 = WPP_GLOBAL_Control;
          }
          else
          {
            v22 = v13;
            if ( !v13 )
            {
              *v6 = v10;
LABEL_21:
              v21 = WPP_GLOBAL_Control;
              goto LABEL_22;
            }
          }
          if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
          {
            WPP_SF_sDsd(
              v21[2],
              v8,
              (_DWORD)a3,
              (unsigned int)"Status",
              v13,
              (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\kdfs.c",
              42);
            goto LABEL_21;
          }
        }
LABEL_22:
        if ( v22 >= 0 )
          return 0;
LABEL_40:
        if ( v21 != &WPP_GLOBAL_Control && (*((_BYTE *)v21 + 28) & 1) != 0 )
          WPP_SF_sDsd(
            v21[2],
            v8,
            (_DWORD)a3,
            (unsigned int)"Status",
            v22,
            (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
            193);
        return (unsigned int)v22;
      }
      if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
        WPP_SF_sDsd(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          a6,
          (_DWORD)a3,
          (unsigned int)"Status",
          8,
          (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
          84);
    }
    else if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      WPP_SF_sDsd(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        a6,
        (_DWORD)a3,
        (unsigned int)"Status",
        8,
        (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
        75);
    }
    return 3221225480LL;
  }
  if ( WPP_GLOBAL_Control != (_UNKNOWN *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    WPP_SF_sDsd(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      a6,
      (_DWORD)a3,
      (unsigned int)"Status",
      13,
      (__int64)"onecore\\ds\\security\\cryptoapi\\ncrypt\\msprim\\keyderivation\\keyderivation.c",
      104);
  return 3221225485LL;
}

```

## disassembly

```asm
0x180012060  mov     r11, rsp
0x180012063  push    rbp
0x180012064  push    rbx
0x180012065  push    rsi
0x180012066  push    rdi
0x180012067  lea     rbp, [r11-128h]
0x18001206e  sub     rsp, 208h
0x180012075  mov     rax, cs:__security_cookie
0x18001207c  xor     rax, rsp
0x18001207f  mov     [rbp+120h+var_50], rax
0x180012086  mov     rdi, [rbp+120h+arg_20]
0x18001208d  mov     r10, rdx
0x180012090  mov     edx, [rbp+120h+arg_28]
0x180012096  mov     rsi, r8
0x180012099  mov     ebx, r9d
0x18001209c  mov     [rsp+44h], ebx
0x1800120a0  mov     qword ptr [rsp+220h+var_1B8], rdi
0x1800120a5  test    edx, 0FFFFFFEFh
0x1800120ab  jnz     loc_180012467
0x1800120b1  test    rcx, rcx
0x1800120b4  jz      loc_180012417
0x1800120ba  cmp     dword ptr [rcx+4], 4D534B59h
0x1800120c1  jnz     loc_1800122D5
0x1800120c7  mov     eax, [rcx+8]
0x1800120ca  mov     [r11-30h], r13
0x1800120ce  xor     r13d, r13d
0x1800120d1  mov     [r11-38h], r14
0x1800120d5  mov     [r11-40h], r15
0x1800120d9  lea     r15, WPP_GLOBAL_Control
0x1800120e0  cmp     eax, 60007h
0x1800120e5  jnz     loc_1800122F5
0x1800120eb  test    edx, edx
0x1800120ed  jnz     loc_180012551
0x1800120f3  cmp     [rcx+30h], r13d
0x1800120f7  jz      loc_180012551
0x1800120fd  mov     [r11-28h], r12
0x180012101  lea     r15, [rcx+50h]
0x180012105  mov     [rsp+58h], r15
0x18001210a  mov     r14d, r13d
0x18001210d  mov     dword ptr [rsp+220h+var_1D8], r13d
0x180012112  mov     [rsp+220h+var_1D0], r13
0x180012117  mov     [rsp+220h+var_1E0], r13d
0x18001211c  test    r10, r10
0x18001211f  jz      short loc_180012165
0x180012121  mov     edx, [r10+4]
0x180012125  cmp     edx, 7FFFFFFFh
0x18001212b  ja      short loc_180012165
0x18001212d  mov     r8, [r10+8]
0x180012131  mov     ecx, r13d
0x180012134  cmp     ecx, edx
0x180012136  jnb     short loc_180012165
0x180012138  mov     eax, ecx
0x18001213a  add     rax, rax
0x18001213d  cmp     dword ptr [r8+rax*8+4], 14h
0x180012143  jnz     loc_1800122CE
0x180012149  test    ecx, ecx
0x18001214b  js      short loc_180012165
0x18001214d  movsxd  rax, ecx
0x180012150  add     rax, rax
0x180012153  mov     rcx, [r8+rax*8+8]
0x180012158  mov     eax, [r8+rax*8]
0x18001215c  mov     [rsp+220h+var_1D0], rcx
0x180012161  mov     [rsp+220h+var_1E0], eax
0x180012165  xor     eax, eax
0x180012167  lea     rcx, [rbp+120h+var_1A0]; void *
0x18001216b  xor     edx, edx; Val
0x18001216d  mov     [rbp+120h+var_19C], eax
0x180012170  mov     r8d, 10Ch; Size
0x180012176  call    memset_0
0x18001217b  mov     r15, [r15+220h]
0x180012182  mov     r13, [r15+30h]
0x180012186  imul    rax, r13, 0FFh
0x18001218d  mov     byte ptr [rsp+70h], 1
0x180012192  cmp     rbx, rax
0x180012195  ja      loc_1800122C3
0x18001219b  mov     rdx, [rsp+58h]
0x1800121a0  lea     rcx, [rbp+120h+var_1A0]
0x1800121a4  mov     rax, [r15+8]
0x1800121a8  xor     r12d, r12d
0x1800121ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121b0  mov     r8d, [rsp+220h+var_1E0]
0x1800121b5  lea     rcx, [rbp+120h+var_1A0]
0x1800121b9  mov     rdx, [rsp+220h+var_1D0]
0x1800121be  mov     rax, [r15+10h]
0x1800121c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121c7  mov     rax, [r15+10h]
0x1800121cb  lea     rdx, [rsp+70h]
0x1800121d0  mov     r8d, 1
0x1800121d6  lea     rcx, [rbp+120h+var_1A0]
0x1800121da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121df  mov     rax, [r15+18h]
0x1800121e3  lea     rdx, [rbp+120h+Src]
0x1800121ea  lea     rcx, [rbp+120h+var_1A0]
0x1800121ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121f3  cmp     rbx, r13
0x1800121f6  lea     rdx, [rbp+120h+Src]; Src
0x1800121fd  mov     r8, rbx
0x180012200  mov     rcx, rsi; void *
0x180012203  cmovnb  r8, r13; Size
0x180012207  call    memcpy_0
0x18001220c  cmp     rbx, r13
0x18001220f  ja      loc_180012591
0x180012215  mov     rcx, cs:WPP_GLOBAL_Control
0x18001221c  xor     r13d, r13d
0x18001221f  mov     [rbp+120h+Src], r13
0x180012226  test    r12d, r12d
0x180012229  mov     r12, [rsp+200h]
0x180012231  mov     [rbp+120h+var_88], r13
0x180012238  mov     [rbp+120h+var_80], r13
0x18001223f  mov     [rbp+120h+var_78], r13
0x180012246  mov     [rbp+120h+var_70], r13
0x18001224d  mov     [rbp+120h+var_68], r13
0x180012254  mov     [rbp+120h+var_60], r13
0x18001225b  mov     [rbp+120h+var_58], r13
0x180012262  jnz     loc_180012490
0x180012268  lea     r15, WPP_GLOBAL_Control
0x18001226f  mov     esi, r14d
0x180012272  test    r14d, r14d
0x180012275  jnz     loc_1800123D6
0x18001227b  mov     [rdi], ebx
0x18001227d  mov     rcx, cs:WPP_GLOBAL_Control
0x180012284  test    esi, esi
0x180012286  js      loc_180012451
0x18001228c  mov     eax, r13d
0x18001228f  mov     r14, [rsp+220h+var_30]
0x180012297  mov     r13, [rsp+220h+var_28]
0x18001229f  mov     r15, [rsp+220h+var_38]
0x1800122a7  mov     rcx, [rbp+120h+var_50]
0x1800122ae  xor     rcx, rsp; StackCookie
0x1800122b1  call    __security_check_cookie
0x1800122b6  add     rsp, 208h
0x1800122bd  pop     rdi
0x1800122be  pop     rsi
0x1800122bf  pop     rbx
0x1800122c0  pop     rbp
0x1800122c1  retn
0x1800122c3  mov     r12d, 8003h
0x1800122c9  jmp     loc_180012215
0x1800122ce  inc     ecx
0x1800122d0  jmp     loc_180012134
0x1800122d5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800122dc  lea     rax, WPP_GLOBAL_Control
0x1800122e3  cmp     rcx, rax
0x1800122e6  jz      short loc_1800122EE
0x1800122e8  test    byte ptr [rcx+1Ch], 1
0x1800122ec  jnz     short loc_180012339
0x1800122ee  mov     eax, 0C0000008h
0x1800122f3  jmp     short loc_1800122A7
0x1800122f5  add     eax, 0FFF9FFFFh; switch 6 cases
0x1800122fa  cmp     eax, 5
0x1800122fd  ja      def_180012315; jumptable 0000000180012315 default case
0x180012303  lea     r8, cs:180000000h
0x18001230a  mov     eax, ds:(jpt_180012315 - 180000000h)[r8+rax*4]
0x180012312  add     rax, r8
0x180012315  jmp     rax; switch jump
0x18001231b  mov     [rsp+220h+var_1F8], edx; jumptable 0000000180012315 cases 393221,393222
0x18001231f  mov     r9d, ebx
0x180012322  mov     rdx, r10
0x180012325  mov     [rsp+220h+var_200], rdi
0x18001232a  mov     r8, rsi
0x18001232d  call    DeriveKeyTLS_KDF
0x180012332  mov     esi, eax
0x180012334  jmp     loc_18001227D
0x180012339  mov     dword ptr [rsp+30h], 154h
0x180012341  mov     rcx, [rcx+10h]
0x180012345  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001234c  mov     qword ptr [rsp+220h+var_1F8], rax
0x180012351  lea     r9, aStatus; "Status"
0x180012358  mov     dword ptr [rsp+220h+var_200], 0C0000008h
0x180012360  call    WPP_SF_sDsd
0x180012365  jmp     short loc_1800122EE
0x180012367  mov     [rsp+220h+var_1F8], edx; jumptable 0000000180012315 case 393217
0x18001236b  mov     r9d, ebx
0x18001236e  mov     rdx, r10
0x180012371  mov     [rsp+220h+var_200], rdi
0x180012376  mov     r8, rsi
0x180012379  call    DeriveKeySP800108_CTR_HMAC
0x18001237e  mov     esi, eax
0x180012380  jmp     loc_18001227D
0x180012385  mov     [rsp+220h+var_1F8], edx; jumptable 0000000180012315 case 393219
0x180012389  mov     r9d, ebx
0x18001238c  mov     rdx, r10
0x18001238f  mov     [rsp+220h+var_200], rdi
0x180012394  mov     r8, rsi
0x180012397  call    DeriveKeyPBKDF2
0x18001239c  mov     esi, eax
0x18001239e  jmp     loc_18001227D
0x1800123a3  mov     rcx, [rcx+10h]
0x1800123a7  lea     rax, aOnecoreDsSecur_19; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800123ae  mov     dword ptr [rsp+30h], 45h ; 'E'
0x1800123b6  lea     r9, aStatus; "Status"
0x1800123bd  mov     qword ptr [rsp+220h+var_1F8], rax
0x1800123c2  mov     dword ptr [rsp+220h+var_200], 0C0000001h
0x1800123ca  call    WPP_SF_sDsd
0x1800123cf  mov     rcx, cs:WPP_GLOBAL_Control
0x1800123d6  cmp     rcx, r15
0x1800123d9  jz      loc_180012284
0x1800123df  test    byte ptr [rcx+1Ch], 1
0x1800123e3  jz      loc_180012284
0x1800123e9  mov     dword ptr [rsp+30h], 72Ah
0x1800123f1  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800123f8  mov     qword ptr [rsp+220h+var_1F8], rax
0x1800123fd  mov     dword ptr [rsp+220h+var_200], r14d
0x180012402  mov     rcx, [rcx+10h]
0x180012406  lea     r9, aStatus; "Status"
0x18001240d  call    WPP_SF_sDsd
0x180012412  jmp     loc_18001227D
0x180012417  mov     rcx, cs:WPP_GLOBAL_Control
0x18001241e  lea     rax, WPP_GLOBAL_Control
0x180012425  cmp     rcx, rax
0x180012428  jz      loc_1800122EE
0x18001242e  test    byte ptr [rcx+1Ch], 1
0x180012432  jz      loc_1800122EE
0x180012438  mov     dword ptr [rsp+30h], 14Bh
0x180012440  jmp     loc_180012341
0x180012445  mov     rcx, cs:WPP_GLOBAL_Control; jumptable 0000000180012315 default case
0x18001244c  mov     esi, 0C00000BBh
0x180012451  cmp     rcx, r15
0x180012454  jz      short loc_180012460
0x180012456  test    byte ptr [rcx+1Ch], 1
0x18001245a  jnz     loc_1800124F3
0x180012460  mov     eax, esi
0x180012462  jmp     loc_18001228F
0x180012467  mov     esi, 0C000000Dh
0x18001246c  mov     rcx, cs:WPP_GLOBAL_Control
0x180012473  lea     rax, WPP_GLOBAL_Control
0x18001247a  cmp     rcx, rax
0x18001247d  jz      short loc_180012489
0x18001247f  test    byte ptr [rcx+1Ch], 1
0x180012483  jnz     loc_180012520
0x180012489  mov     eax, esi
0x18001248b  jmp     loc_1800122A7
0x180012490  mov     esi, 0C0000001h
0x180012495  mov     r14d, esi
0x180012498  lea     r15, WPP_GLOBAL_Control
0x18001249f  cmp     rcx, r15
0x1800124a2  jz      loc_18001226F
0x1800124a8  test    byte ptr [rcx+1Ch], 1
0x1800124ac  jz      loc_18001226F
0x1800124b2  jmp     loc_1800123A3
0x1800124b7  mov     [rsp+220h+var_1F8], edx; jumptable 0000000180012315 case 393218
0x1800124bb  mov     r9d, ebx
0x1800124be  mov     rdx, r10
0x1800124c1  mov     [rsp+220h+var_200], rdi
0x1800124c6  mov     r8, rsi
0x1800124c9  call    DeriveKeySP80056A_CONCAT
0x1800124ce  mov     esi, eax
0x1800124d0  jmp     loc_18001227D
0x1800124d5  mov     [rsp+220h+var_1F8], edx; jumptable 0000000180012315 case 393220
0x1800124d9  mov     r9d, ebx
0x1800124dc  mov     rdx, r10
0x1800124df  mov     [rsp+220h+var_200], rdi
0x1800124e4  mov     r8, rsi
0x1800124e7  call    DeriveKeyCAPI_KDF
0x1800124ec  mov     esi, eax
0x1800124ee  jmp     loc_18001227D
0x1800124f3  mov     rcx, [rcx+10h]
0x1800124f7  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x1800124fe  mov     dword ptr [rsp+30h], 6C1h
0x180012506  lea     r9, aStatus; "Status"
0x18001250d  mov     qword ptr [rsp+220h+var_1F8], rax
0x180012512  mov     dword ptr [rsp+220h+var_200], esi
0x180012516  call    WPP_SF_sDsd
0x18001251b  jmp     loc_180012460
0x180012520  mov     rcx, [rcx+10h]
0x180012524  lea     rax, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001252b  mov     dword ptr [rsp+30h], 668h
0x180012533  lea     r9, aStatus; "Status"
0x18001253a  mov     qword ptr [rsp+220h+var_1F8], rax
0x18001253f  mov     dword ptr [rsp+220h+var_200], 0C000000Dh
0x180012547  call    WPP_SF_sDsd
0x18001254c  jmp     loc_180012489
0x180012551  mov     esi, 0C000000Dh
0x180012556  mov     rcx, cs:WPP_GLOBAL_Control
0x18001255d  cmp     rcx, r15
0x180012560  jz      loc_180012284
0x180012566  test    byte ptr [rcx+1Ch], 1
0x18001256a  jz      loc_180012284
0x180012570  mov     dword ptr [rsp+30h], 719h
0x180012578  lea     rax, aOnecoreDsSecur_18; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001257f  mov     qword ptr [rsp+220h+var_1F8], rax
0x180012584  mov     dword ptr [rsp+220h+var_200], 0C000000Dh
0x18001258c  jmp     loc_180012402
0x180012591  inc     byte ptr [rsp+70h]
0x180012595  lea     rax, [rsi+r13]
0x180012599  mov     rsi, rbx
0x18001259c  sub     rsi, r13
0x18001259f  jz      loc_180012215
0x1800125a5  mov     r14, [rsp+220h+var_1D0]
0x1800125aa  mov     rbx, rax
0x1800125ad  mov     r12, [rsp+58h]
0x1800125b2  mov     edi, [rsp+220h+var_1E0]
0x1800125b6  jmp     loc_180080848
0x180080848  mov     rax, [r15+8]
0x18008084c  lea     rcx, [rbp+120h+var_1A0]
0x180080850  mov     rdx, r12
0x180080853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080858  mov     rax, [r15+10h]
0x18008085c  lea     rdx, [rbp+120h+Src]
0x180080863  mov     r8, r13
  ... truncated ...
```
