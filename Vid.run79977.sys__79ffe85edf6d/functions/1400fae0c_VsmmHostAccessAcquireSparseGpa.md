# VsmmHostAccessAcquireSparseGpa

- ea: `0x1400fae0c`
- end: `0x1400fb374`
- name: `VsmmHostAccessAcquireSparseGpa`
- size: `1384`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x1400063d0`

## callees

- `0x1400029c0`
- `0x140006b40`
- `0x140006b68`
- `0x14000a010`
- `0x14000efa0`
- `0x14001b440`
- `0x140021c60`
- `0x140021e00`
- `0x14002e270`
- `0x140074030`
- `0x140074630`
- `0x140075c78`
- `0x1400768a0`
- `0x1400ec584`
- `0x1400ec9fc`
- `0x1400fae0c`

## import_xrefs

- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400faf0a`
- `ntoskrnl!RtlTestBitNoFenceEx` at `0x1400faf0a`
- `winhvr!WinHvFlushCache` at `0x1400fb31a`
- `winhvr!WinHvFlushCache` at `0x1400fb31a`

## string_xrefs

- `0x1400fb072`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400fb1ef`: `onecore\vm\vid\sys\vsmm\vsmmhostaccess.c`
- `0x1400fb062`: `VsmmHostAccesspAcquire`
- `0x1400fb1df`: `VsmmHostAccesspAcquire`

## pseudocode

```c
__int64 __fastcall VsmmHostAccessAcquireSparseGpa(_QWORD *a1, __int64 a2, __int64 a3, int a4, int a5, __int64 a6)
{
  char v10; // r12
  __int64 v11; // r13
  __int64 v12; // rcx
  __int64 v13; // r8
  int v14; // ebx
  unsigned __int64 v15; // r15
  __int64 v16; // rbx
  unsigned __int64 v17; // rdi
  __int64 *v18; // r8
  __int64 v19; // rcx
  unsigned int v20; // r8d
  unsigned int v21; // r8d
  unsigned int v22; // r8d
  __int64 BackingPage; // rdi
  __int64 v24; // rdx
  int v25; // r8d
  int v26; // r10d
  int v27; // r9d
  __int64 v28; // rax
  __int64 v29; // rax
  int v30; // edx
  __int64 v31; // rcx
  void *v32; // rdx
  unsigned __int64 v33; // rcx
  __int64 *v34; // rax
  int v35; // r9d
  __int64 v36; // rax
  __int64 v37; // rax
  int v38; // edx
  __int64 v39; // rcx
  unsigned __int64 v40; // rcx
  int v42; // [rsp+40h] [rbp-C0h] BYREF
  int v43; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v44[2]; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int64 v45; // [rsp+50h] [rbp-B0h] BYREF
  unsigned __int64 v46; // [rsp+58h] [rbp-A8h] BYREF
  _QWORD v47[30]; // [rsp+60h] [rbp-A0h] BYREF
  char v48[32]; // [rsp+150h] [rbp+50h] BYREF
  _BYTE v49[16]; // [rsp+170h] [rbp+70h] BYREF
  _BYTE v50[16]; // [rsp+180h] [rbp+80h] BYREF
  int *v51; // [rsp+190h] [rbp+90h]
  __int64 v52; // [rsp+198h] [rbp+98h]
  int *v53; // [rsp+1A0h] [rbp+A0h]
  __int64 v54; // [rsp+1A8h] [rbp+A8h]
  __int64 v55; // [rsp+1B0h] [rbp+B0h]
  __int64 v56; // [rsp+1B8h] [rbp+B8h]
  int *v57; // [rsp+1C0h] [rbp+C0h]
  __int64 v58; // [rsp+1C8h] [rbp+C8h]
  __int64 v59; // [rsp+1D0h] [rbp+D0h]
  int v60; // [rsp+1D8h] [rbp+D8h] BYREF
  int v61; // [rsp+1DCh] [rbp+DCh]
  __int64 *v62; // [rsp+1E0h] [rbp+E0h]
  __int64 v63; // [rsp+1E8h] [rbp+E8h]
  __int64 *v64; // [rsp+1F0h] [rbp+F0h]
  __int64 v65; // [rsp+1F8h] [rbp+F8h]
  _DWORD *v66; // [rsp+200h] [rbp+100h]
  __int64 v67; // [rsp+208h] [rbp+108h]

  memset(v47, 0, 0xE8u);
  VsmmHostAccesspAcquireContextInitialize((unsigned int)v47, 3, a1[48], a4, a3, 0, a6);
  v47[25] = a1;
  v47[26] = a2;
  v10 = VsmmHostAccesspAcqRelBySpa(v47);
  v11 = *(_QWORD *)(v47[20] + 8LL);
  if ( SLODWORD(v47[2]) <= (int)VsmmHostAccessMinimumForMemoryBlock() )
    goto LABEL_2;
  v15 = 0;
  if ( !v47[21] )
  {
LABEL_37:
    v14 = VsmmHostAccesspAcqRelFlush(v47);
    if ( v14 < 0 )
    {
LABEL_38:
      if ( v14 == -1070268408 )
      {
        v14 = -1070137302;
        if ( !v10 && v47[23] && SLODWORD(v47[2]) > 1 )
          VsmmHostAccesspCheckVtlAccessInjectIntercept(v47);
      }
      goto LABEL_43;
    }
LABEL_2:
    v14 = 0;
    goto LABEL_43;
  }
  while ( 1 )
  {
    v16 = v47[20];
    v17 = a1[49] + *(_QWORD *)(v47[26] + 8 * v15) - a1[32];
    if ( *(_DWORD *)(v47[20] + 268LL) != 2
      && *(_QWORD *)(v47[20] + 288LL)
      && !(unsigned __int8)RtlTestBitNoFenceEx(v47[20] + 272LL, v17 >> 9) )
    {
      VsmmMbpUpgradeChunk(v16, v17 >> 9);
    }
    v12 = *(_QWORD *)(v16 + 256);
    v18 = (__int64 *)((*(_DWORD *)(v16 + 264) & 8) != 0 ? v12 + 8 * v17 : v12 + 16 * v17 + 8);
    v13 = *v18;
    if ( !v10 )
      break;
    if ( (v13 & 0xF) != 1 )
    {
      v14 = -1073741811;
      if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
      {
        tlgCreate1Sz_char(v49, "VsmmHostAccesspAcquire");
        tlgCreate1Sz_char(v50, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
        v43 = v27;
        v51 = &v42;
        v42 = 1958;
        v52 = 4;
        v53 = &v43;
        v54 = 4;
        v28 = *(_QWORD *)(v47[20] + 8LL);
        v56 = 16;
        v55 = v28 + 656;
        v29 = *(_QWORD *)(v47[20] + 8LL);
        v30 = *(unsigned __int16 *)(v29 + 120);
        v31 = *(_QWORD *)(v29 + 128);
        v57 = &v60;
        v60 = v30;
        v32 = &unk_14005C372;
        v58 = 2;
        v59 = v31;
        v61 = 0;
        v33 = *(_QWORD *)(*(_QWORD *)(v47[20] + 8LL) + 648LL);
        v62 = (__int64 *)&v45;
        v34 = (__int64 *)&v46;
        v45 = v33;
        v46 = v17;
LABEL_33:
        v64 = v34;
        v44[0] = v25;
        v66 = v44;
        v67 = 8;
        v44[1] = v26;
        v65 = 8;
        v63 = 8;
        tlgWriteTransfer_EtwWriteTransfer(&dword_140065110, v32, 0, 0, 12, v48);
        goto LABEL_43;
      }
      goto LABEL_43;
    }
    v19 = v47[20];
    v20 = v13 & 0xF;
    if ( v20 > 5 )
    {
      v21 = v20 - 6;
      if ( v21 )
      {
        v22 = v21 - 1;
        if ( !v22 || v22 - 1 >= 2 )
        {
LABEL_19:
          LOBYTE(v19) = *(_BYTE *)(v47[20] + 240LL);
          BackingPage = VsmmNumaGetBackingPage(v19, 0);
          goto LABEL_23;
        }
      }
    }
    else if ( v20 != 1 )
    {
      goto LABEL_19;
    }
    BackingPage = *(_QWORD *)(*(_QWORD *)(v47[20] + 256LL) + 16 * v17) & 0xFFFFFFFFFFLL;
LABEL_23:
    v24 = v47[17];
    if ( v47[17] )
    {
      if ( BackingPage == v47[17] + v47[16] )
        goto LABEL_28;
      v14 = VsmmHostAccesspAcqRelCompleteRun(v47);
      if ( v14 < 0 )
        goto LABEL_38;
      v24 = 0;
    }
    v47[16] = BackingPage;
LABEL_28:
    ++v15;
    v47[17] = v24 + 1;
    if ( v15 >= v47[21] )
      goto LABEL_37;
    a1 = (_QWORD *)v47[25];
  }
  if ( (v13 & 0xF) != 0 )
  {
    BackingPage = *(_QWORD *)(v47[26] + 8 * v15);
    goto LABEL_23;
  }
  v14 = -1073741811;
  if ( (unsigned int)dword_140065110 > 2 && (unsigned __int8)tlgKeywordOn(&dword_140065110, 256) )
  {
    tlgCreate1Sz_char(v49, "VsmmHostAccesspAcquire");
    tlgCreate1Sz_char(v50, "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostaccess.c");
    v42 = v35;
    v51 = &v43;
    v43 = 1990;
    v52 = 4;
    v53 = &v42;
    v54 = 4;
    v36 = *(_QWORD *)(v47[20] + 8LL);
    v56 = 16;
    v55 = v36 + 656;
    v37 = *(_QWORD *)(v47[20] + 8LL);
    v38 = *(unsigned __int16 *)(v37 + 120);
    v39 = *(_QWORD *)(v37 + 128);
    v57 = &v60;
    v60 = v38;
    v32 = &unk_14005C2ED;
    v58 = 2;
    v59 = v39;
    v61 = 0;
    v40 = *(_QWORD *)(*(_QWORD *)(v47[20] + 8LL) + 648LL);
    v62 = (__int64 *)&v46;
    v34 = (__int64 *)&v45;
    v46 = v40;
    v45 = v17;
    goto LABEL_33;
  }
LABEL_43:
  if ( v47[24] && (v47[22] & 1) != 0 && (*(_BYTE *)(v11 + 40) & 0x10) != 0 )
    WinHvFlushCache();
  if ( LODWORD(v47[19]) <= 1 && v47[27] )
  {
    LOBYTE(v13) = 1;
    VsmmGpaRangeRelease(v12, v47[27], v13);
  }
  VsmmHostAccesspAcqRelContextDestroy(v47);
  return (unsigned int)v14;
}

```

## disassembly

```asm
0x1400fae0c  mov     [rsp-8+arg_10], rbx
0x1400fae11  push    rbp
0x1400fae12  push    rsi
0x1400fae13  push    rdi
0x1400fae14  push    r12
0x1400fae16  push    r13
0x1400fae18  push    r14
0x1400fae1a  push    r15
0x1400fae1c  lea     rbp, [rsp-120h]
0x1400fae24  sub     rsp, 220h
0x1400fae2b  mov     rax, cs:__security_cookie
0x1400fae32  xor     rax, rsp
0x1400fae35  mov     [rbp+150h+var_40], rax
0x1400fae3c  mov     rbx, r8
0x1400fae3f  mov     rsi, rdx
0x1400fae42  mov     r14, rcx
0x1400fae45  xor     edx, edx; Val
0x1400fae47  mov     r8d, 0E8h; Size
0x1400fae4d  lea     rcx, [rsp+250h+var_1F0]; void *
0x1400fae52  mov     edi, r9d
0x1400fae55  call    memset
0x1400fae5a  mov     rax, [rbp+150h+arg_28]
0x1400fae61  lea     rcx, [rsp+250h+var_1F0]
0x1400fae66  mov     r8, [r14+180h]
0x1400fae6d  mov     r9d, edi
0x1400fae70  mov     [rsp+250h+var_220], rax
0x1400fae75  mov     edx, 3
0x1400fae7a  mov     dword ptr [rsp+250h+var_228], 0
0x1400fae82  mov     [rsp+250h+var_230], rbx
0x1400fae87  call    VsmmHostAccesspAcquireContextInitialize
0x1400fae8c  lea     rcx, [rsp+250h+var_1F0]
0x1400fae91  mov     [rbp+150h+var_128], r14
0x1400fae95  mov     [rbp+150h+var_120], rsi
0x1400fae99  call    VsmmHostAccesspAcqRelBySpa
0x1400fae9e  mov     rcx, [rbp+150h+var_150]
0x1400faea2  mov     r12b, al
0x1400faea5  mov     r13, [rcx+8]
0x1400faea9  call    VsmmHostAccessMinimumForMemoryBlock
0x1400faeae  xor     esi, esi
0x1400faeb0  cmp     [rsp+250h+var_1E0], eax
0x1400faeb4  jg      short loc_1400FAEBD
0x1400faeb6  mov     ebx, esi
0x1400faeb8  jmp     loc_1400FB307
0x1400faebd  mov     r15, rsi
0x1400faec0  cmp     [rbp+150h+var_148], rsi
0x1400faec4  jbe     loc_1400FB2CA
0x1400faeca  mov     rax, [rbp+150h+var_120]
0x1400faece  mov     rbx, [rbp+150h+var_150]
0x1400faed2  mov     rdi, [rax+r15*8]
0x1400faed6  sub     rdi, [r14+100h]
0x1400faedd  add     rdi, [r14+188h]
0x1400faee4  cmp     dword ptr [rbx+10Ch], 2
0x1400faeeb  jz      short loc_1400FAF28
0x1400faeed  mov     rax, [rbx+120h]
0x1400faef4  test    rax, rax
0x1400faef7  jz      short loc_1400FAF27
0x1400faef9  mov     rsi, rdi
0x1400faefc  lea     rcx, [rbx+110h]
0x1400faf03  shr     rsi, 9
0x1400faf07  mov     rdx, rsi
0x1400faf0a  call    cs:__imp_RtlTestBitNoFenceEx
0x1400faf11  nop     dword ptr [rax+rax+00h]
0x1400faf16  test    al, al
0x1400faf18  jnz     short loc_1400FAF25
0x1400faf1a  mov     rdx, rsi
0x1400faf1d  mov     rcx, rbx
0x1400faf20  call    VsmmMbpUpgradeChunk
0x1400faf25  xor     esi, esi
0x1400faf27  nop
0x1400faf28  mov     eax, [rbx+108h]
0x1400faf2e  mov     rcx, [rbx+100h]
0x1400faf35  test    al, 8
0x1400faf37  jnz     short loc_1400FAF49
0x1400faf39  mov     r8, rdi
0x1400faf3c  shl     r8, 4
0x1400faf40  add     r8, 8
0x1400faf44  add     r8, rcx
0x1400faf47  jmp     short loc_1400FAF4D
0x1400faf49  lea     r8, [rcx+rdi*8]
0x1400faf4d  mov     r8, [r8]
0x1400faf50  mov     r10, r8
0x1400faf53  mov     rax, r8
0x1400faf56  shr     r10, 20h
0x1400faf5a  and     eax, 0Fh
0x1400faf5d  test    r12b, r12b
0x1400faf60  jz      short loc_1400FAFD2
0x1400faf62  cmp     rax, 1
0x1400faf66  jnz     loc_1400FB031
0x1400faf6c  mov     rcx, [rbp+150h+var_150]
0x1400faf70  and     r8d, 0Fh
0x1400faf74  cmp     r8d, 5
0x1400faf78  ja      short loc_1400FAF8B
0x1400faf7a  jz      short loc_1400FAFA3
0x1400faf7c  test    r8d, r8d
0x1400faf7f  jz      short loc_1400FAFA3
0x1400faf81  sub     r8d, eax
0x1400faf84  jz      short loc_1400FAFB5
0x1400faf86  sub     r8d, eax
0x1400faf89  jmp     short loc_1400FAFA3
0x1400faf8b  sub     r8d, 6
0x1400faf8f  jz      short loc_1400FAFB5
0x1400faf91  sub     r8d, 1
0x1400faf95  jz      short loc_1400FAFA3
0x1400faf97  sub     r8d, 1
0x1400faf9b  jz      short loc_1400FAFB5
0x1400faf9d  cmp     r8d, 1
0x1400fafa1  jz      short loc_1400FAFB5
0x1400fafa3  mov     cl, [rcx+0F0h]
0x1400fafa9  xor     edx, edx
0x1400fafab  call    VsmmNumaGetBackingPage
0x1400fafb0  mov     rdi, rax
0x1400fafb3  jmp     short loc_1400FAFE3
0x1400fafb5  mov     rax, [rcx+100h]
0x1400fafbc  add     rdi, rdi
0x1400fafbf  mov     rdi, [rax+rdi*8]
0x1400fafc3  mov     rax, 0FFFFFFFFFFh
0x1400fafcd  and     rdi, rax
0x1400fafd0  jmp     short loc_1400FAFE3
0x1400fafd2  test    rax, rax
0x1400fafd5  jz      loc_1400FB1AE
0x1400fafdb  mov     rax, [rbp+150h+var_120]
0x1400fafdf  mov     rdi, [rax+r15*8]
0x1400fafe3  mov     rdx, [rbp+150h+var_168]
0x1400fafe7  test    rdx, rdx
0x1400fafea  jz      short loc_1400FB00F
0x1400fafec  mov     rcx, [rbp+150h+var_170]
0x1400faff0  add     rcx, rdx
0x1400faff3  cmp     rdi, rcx
0x1400faff6  jz      short loc_1400FB013
0x1400faff8  lea     rcx, [rsp+250h+var_1F0]
0x1400faffd  call    VsmmHostAccesspAcqRelCompleteRun
0x1400fb002  mov     ebx, eax
0x1400fb004  test    eax, eax
0x1400fb006  js      loc_1400FB2DE
0x1400fb00c  mov     rdx, rsi
0x1400fb00f  mov     [rbp+150h+var_170], rdi
0x1400fb013  inc     r15
0x1400fb016  lea     rax, [rdx+1]
0x1400fb01a  mov     [rbp+150h+var_168], rax
0x1400fb01e  cmp     r15, [rbp+150h+var_148]
0x1400fb022  jnb     loc_1400FB2CA
0x1400fb028  mov     r14, [rbp+150h+var_128]
0x1400fb02c  jmp     loc_1400FAECA
0x1400fb031  mov     eax, cs:dword_140065110
0x1400fb037  mov     r9d, 0C000000Dh
0x1400fb03d  mov     ebx, r9d
0x1400fb040  cmp     eax, 2
0x1400fb043  jbe     loc_1400FB307
0x1400fb049  mov     edx, 100h
0x1400fb04e  lea     rcx, dword_140065110
0x1400fb055  call    _tlgKeywordOn
0x1400fb05a  test    al, al
0x1400fb05c  jz      loc_1400FB307
0x1400fb062  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400fb069  lea     rcx, [rbp+150h+var_E0]
0x1400fb06d  call    _tlgCreate1Sz_char
0x1400fb072  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400fb079  lea     rcx, [rbp+150h+var_D0]
0x1400fb080  call    _tlgCreate1Sz_char
0x1400fb085  mov     [rsp+250h+var_20C], r9d
0x1400fb08a  lea     rax, [rsp+250h+var_210]
0x1400fb08f  mov     r9, [rbp+150h+var_150]
0x1400fb093  lea     rcx, [rsp+250h+var_20C]
0x1400fb098  mov     [rbp+150h+var_C0], rax
0x1400fb09f  mov     [rsp+250h+var_210], 7A6h
0x1400fb0a7  mov     [rbp+150h+var_B8], 4
0x1400fb0b2  mov     [rbp+150h+var_B0], rcx
0x1400fb0b9  mov     [rbp+150h+var_A8], 4
0x1400fb0c4  mov     rax, [r9+8]
0x1400fb0c8  add     rax, 290h
0x1400fb0ce  mov     [rbp+150h+var_98], 10h
0x1400fb0d9  mov     [rbp+150h+var_A0], rax
0x1400fb0e0  mov     rax, [r9+8]
0x1400fb0e4  movzx   edx, word ptr [rax+78h]
0x1400fb0e8  mov     rcx, [rax+80h]
0x1400fb0ef  lea     rax, [rbp+150h+var_78]
0x1400fb0f6  mov     [rbp+150h+var_90], rax
0x1400fb0fd  mov     [rbp+150h+var_78], edx
0x1400fb103  lea     rdx, unk_14005C372
0x1400fb10a  mov     [rbp+150h+var_88], 2
0x1400fb115  mov     [rbp+150h+var_80], rcx
0x1400fb11c  mov     [rbp+150h+var_74], esi
0x1400fb122  mov     rax, [r9+8]
0x1400fb126  mov     rcx, [rax+288h]
0x1400fb12d  lea     rax, [rsp+250h+var_200]
0x1400fb132  mov     [rbp+150h+var_70], rax
0x1400fb139  lea     rax, [rsp+250h+var_1F8]
0x1400fb13e  mov     [rsp+250h+var_200], rcx
0x1400fb143  mov     [rsp+250h+var_1F8], rdi
0x1400fb148  mov     [rbp+150h+var_60], rax
0x1400fb14f  lea     rcx, dword_140065110
0x1400fb156  lea     rax, [rsp+250h+var_208]
0x1400fb15b  mov     [rsp+250h+var_208], r8d
0x1400fb160  mov     [rbp+150h+var_50], rax
0x1400fb167  xor     r9d, r9d
0x1400fb16a  lea     rax, [rbp+150h+var_100]
0x1400fb16e  mov     [rbp+150h+var_48], 8
0x1400fb179  mov     [rsp+250h+var_228], rax
0x1400fb17e  xor     r8d, r8d
0x1400fb181  mov     dword ptr [rsp+250h+var_230], 0Ch
0x1400fb189  mov     [rsp+250h+var_204], r10d
0x1400fb18e  mov     [rbp+150h+var_58], 8
0x1400fb199  mov     [rbp+150h+var_68], 8
0x1400fb1a4  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400fb1a9  jmp     loc_1400FB307
0x1400fb1ae  mov     eax, cs:dword_140065110
0x1400fb1b4  mov     r9d, 0C000000Dh
0x1400fb1ba  mov     ebx, r9d
0x1400fb1bd  cmp     eax, 2
0x1400fb1c0  jbe     loc_1400FB307
0x1400fb1c6  mov     edx, 100h
0x1400fb1cb  lea     rcx, dword_140065110
0x1400fb1d2  call    _tlgKeywordOn
0x1400fb1d7  test    al, al
0x1400fb1d9  jz      loc_1400FB307
0x1400fb1df  lea     rdx, aVsmmhostaccess_0; "VsmmHostAccesspAcquire"
0x1400fb1e6  lea     rcx, [rbp+150h+var_E0]
0x1400fb1ea  call    _tlgCreate1Sz_char
0x1400fb1ef  lea     rdx, aOnecoreVmVidSy_33; "onecore\\vm\\vid\\sys\\vsmm\\vsmmhostac"...
0x1400fb1f6  lea     rcx, [rbp+150h+var_D0]
0x1400fb1fd  call    _tlgCreate1Sz_char
0x1400fb202  mov     [rsp+250h+var_210], r9d
0x1400fb207  lea     rax, [rsp+250h+var_20C]
0x1400fb20c  mov     r9, [rbp+150h+var_150]
0x1400fb210  lea     rcx, [rsp+250h+var_210]
0x1400fb215  mov     [rbp+150h+var_C0], rax
0x1400fb21c  mov     [rsp+250h+var_20C], 7C6h
0x1400fb224  mov     [rbp+150h+var_B8], 4
0x1400fb22f  mov     [rbp+150h+var_B0], rcx
0x1400fb236  mov     [rbp+150h+var_A8], 4
0x1400fb241  mov     rax, [r9+8]
0x1400fb245  add     rax, 290h
0x1400fb24b  mov     [rbp+150h+var_98], 10h
0x1400fb256  mov     [rbp+150h+var_A0], rax
0x1400fb25d  mov     rax, [r9+8]
0x1400fb261  movzx   edx, word ptr [rax+78h]
0x1400fb265  mov     rcx, [rax+80h]
0x1400fb26c  lea     rax, [rbp+150h+var_78]
0x1400fb273  mov     [rbp+150h+var_90], rax
0x1400fb27a  mov     [rbp+150h+var_78], edx
0x1400fb280  lea     rdx, unk_14005C2ED
0x1400fb287  mov     [rbp+150h+var_88], 2
0x1400fb292  mov     [rbp+150h+var_80], rcx
0x1400fb299  mov     [rbp+150h+var_74], esi
0x1400fb29f  mov     rax, [r9+8]
0x1400fb2a3  mov     rcx, [rax+288h]
0x1400fb2aa  lea     rax, [rsp+250h+var_1F8]
0x1400fb2af  mov     [rbp+150h+var_70], rax
0x1400fb2b6  lea     rax, [rsp+250h+var_200]
0x1400fb2bb  mov     [rsp+250h+var_1F8], rcx
0x1400fb2c0  mov     [rsp+250h+var_200], rdi
0x1400fb2c5  jmp     loc_1400FB148
0x1400fb2ca  lea     rcx, [rsp+250h+var_1F0]
0x1400fb2cf  call    VsmmHostAccesspAcqRelFlush
0x1400fb2d4  mov     ebx, eax
0x1400fb2d6  test    eax, eax
0x1400fb2d8  jns     loc_1400FAEB6
0x1400fb2de  cmp     ebx, 0C0350008h
0x1400fb2e4  jnz     short loc_1400FB307
0x1400fb2e6  mov     ebx, 0C037002Ah
0x1400fb2eb  test    r12b, r12b
0x1400fb2ee  jnz     short loc_1400FB307
0x1400fb2f0  cmp     [rbp+150h+var_138], rsi
0x1400fb2f4  jz      short loc_1400FB307
0x1400fb2f6  cmp     [rsp+250h+var_1E0], 1
0x1400fb2fb  jle     short loc_1400FB307
0x1400fb2fd  lea     rcx, [rsp+250h+var_1F0]
0x1400fb302  call    VsmmHostAccesspCheckVtlAccessInjectIntercept
0x1400fb307  cmp     [rbp+150h+var_130], rsi
0x1400fb30b  jbe     short loc_1400FB326
0x1400fb30d  test    [rbp+150h+var_140], 1
0x1400fb311  jz      short loc_1400FB326
0x1400fb313  test    byte ptr [r13+28h], 10h
0x1400fb318  jz      short loc_1400FB326
0x1400fb31a  call    cs:__imp_WinHvFlushCache
0x1400fb321  nop     dword ptr [rax+rax+00h]
0x1400fb326  cmp     [rbp+150h+var_158], 1
0x1400fb32a  ja      short loc_1400FB33D
0x1400fb32c  mov     rdx, [rbp+150h+var_118]
0x1400fb330  test    rdx, rdx
0x1400fb333  jz      short loc_1400FB33D
0x1400fb335  mov     r8b, 1
0x1400fb338  call    VsmmGpaRangeRelease
0x1400fb33d  lea     rcx, [rsp+250h+var_1F0]
0x1400fb342  call    VsmmHostAccesspAcqRelContextDestroy
0x1400fb347  mov     eax, ebx
0x1400fb349  mov     rcx, [rbp+150h+var_40]
0x1400fb350  xor     rcx, rsp; StackCookie
0x1400fb353  call    __security_check_cookie
0x1400fb358  mov     rbx, [rsp+250h+arg_10]
0x1400fb360  add     rsp, 220h
0x1400fb367  pop     r15
0x1400fb369  pop     r14
0x1400fb36b  pop     r13
0x1400fb36d  pop     r12
0x1400fb36f  pop     rdi
0x1400fb370  pop     rsi
0x1400fb371  pop     rbp
0x1400fb372  retn
```
