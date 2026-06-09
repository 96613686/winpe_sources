# CPreviewDC::ComputeDeltas(int &,ushort const *,uint &,int,uint,int *,int,ushort *,int *,int &)

- ea: `0x18004db00`
- end: `0x18004debf`
- name: `?ComputeDeltas@CPreviewDC@@IEAA?AVCSize@@AEAHPEBGAEAIHIPEAHHPEAG30@Z`
- size: `959`
- prototype: `struct CSize __high(int *, const unsigned __int16 *, unsigned int *, int, unsigned int, int *, int, unsigned __int16 *, int *, int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18004e050`
- `0x18004ef90`

## callees

- `0x18002da20`
- `0x18004db00`
- `0x1800d1fe0`

## import_xrefs

- `USER32!GetTabbedTextExtentA` at `0x18004dc4a`
- `USER32!GetTabbedTextExtentA` at `0x18004dc4a`
- `GDI32!GetTextExtentPoint32A` at `0x18004dbcb`
- `GDI32!GetTextExtentPoint32A` at `0x18004dbcb`
- `GDI32!MoveToEx` at `0x18004de86`
- `GDI32!MoveToEx` at `0x18004de86`
- `GDI32!GetCurrentPositionEx` at `0x18004dbf1`
- `GDI32!GetCurrentPositionEx` at `0x18004dbf1`
- `GDI32!GetTextAlign` at `0x18004dbd5`
- `GDI32!GetTextAlign` at `0x18004dbd5`
- `GDI32!GetCharWidthW` at `0x18004dd84`
- `GDI32!GetCharWidthW` at `0x18004dda8`
- `GDI32!GetCharWidthW` at `0x18004dd84`
- `GDI32!GetCharWidthW` at `0x18004dda8`
- `GDI32!GetTextExtentPoint32W` at `0x18004dcdb`
- `GDI32!GetTextExtentPoint32W` at `0x18004dcdb`
- `GDI32!GetTextMetricsW` at `0x18004dba0`
- `GDI32!GetTextMetricsW` at `0x18004dbae`
- `GDI32!GetTextMetricsW` at `0x18004dba0`
- `GDI32!GetTextMetricsW` at `0x18004dbae`

## pseudocode

```c
struct tagSIZE *__fastcall CPreviewDC::ComputeDeltas(
        __int64 a1,
        struct tagSIZE *a2,
        int *a3,
        const WCHAR *a4,
        unsigned int *a5,
        int a6,
        unsigned int a7,
        int *a8,
        int a9,
        __int64 a10,
        LPINT lpBuffer,
        _DWORD *a12)
{
  int *v12; // rbx
  __int64 v14; // rsi
  const WCHAR *v15; // r15
  HDC v17; // rcx
  char TextAlign; // r13
  HDC v19; // rcx
  int v20; // r14d
  int v21; // r12d
  unsigned int v22; // ecx
  const WCHAR *v23; // rdx
  unsigned int v24; // r8d
  int v25; // esi
  UINT v26; // eax
  int v27; // r15d
  unsigned int v28; // r8d
  int v29; // esi
  int *v30; // rcx
  unsigned int i; // eax
  int v32; // edx
  int v33; // eax
  int v34; // ecx
  int v35; // eax
  unsigned int v36; // r8d
  struct tagSIZE *v37; // r15
  _DWORD *v38; // rax
  int v39; // r13d
  int Buffer[2]; // [rsp+30h] [rbp-D0h] BYREF
  int TabbedTextExtentA; // [rsp+38h] [rbp-C8h]
  unsigned int v43; // [rsp+3Ch] [rbp-C4h]
  unsigned int v44; // [rsp+40h] [rbp-C0h]
  int v45; // [rsp+44h] [rbp-BCh]
  __int64 v46; // [rsp+48h] [rbp-B8h]
  int *v47; // [rsp+50h] [rbp-B0h]
  unsigned int *v48; // [rsp+58h] [rbp-A8h]
  __int64 v49; // [rsp+60h] [rbp-A0h]
  struct tagPOINT pt; // [rsp+68h] [rbp-98h] BYREF
  struct tagSIZE psizl; // [rsp+70h] [rbp-90h] BYREF
  __int64 v52; // [rsp+78h] [rbp-88h]
  struct tagSIZE *v53; // [rsp+80h] [rbp-80h]
  _DWORD *v54; // [rsp+88h] [rbp-78h]
  struct tagTEXTMETRICW tm; // [rsp+90h] [rbp-70h] BYREF
  struct tagTEXTMETRICW v56; // [rsp+D0h] [rbp-30h] BYREF

  v12 = lpBuffer;
  v48 = a5;
  v14 = a1;
  v52 = a10;
  v15 = a4;
  v54 = a12;
  v53 = a2;
  v46 = a1;
  v17 = *(HDC *)(a1 + 16);
  *(_QWORD *)Buffer = a4;
  v47 = lpBuffer;
  memset(&tm, 0, sizeof(tm));
  memset(&v56, 0, sizeof(v56));
  GetTextMetricsW(v17, &tm);
  GetTextMetricsW(*(HDC *)(v14 + 8), &v56);
  GetTextExtentPoint32A(*(HDC *)(v14 + 16), "A", 1, a2);
  TextAlign = GetTextAlign(*(HDC *)(v14 + 16));
  if ( (TextAlign & 1) != 0 )
  {
    v19 = *(HDC *)(v14 + 8);
    v45 = 1;
    GetCurrentPositionEx(v19, &pt);
    *a3 = pt.x;
  }
  else
  {
    v45 = 0;
  }
  v20 = *a3;
  v21 = 0;
  TabbedTextExtentA = 0;
  if ( a6 )
  {
    if ( a7 == 1 )
      TabbedTextExtentA = *a8;
    else
      TabbedTextExtentA = (unsigned __int16)GetTabbedTextExtentA(*(HDC *)(v14 + 16), "\t", 1, 0, 0);
  }
  v22 = *v48;
  if ( *v48 )
  {
    v23 = v15;
    v44 = 0;
    v24 = 0;
    v49 = (__int64)v15;
    v43 = 0;
    v25 = v20;
    while ( 1 )
    {
      if ( v24 >= v22 )
      {
LABEL_38:
        v14 = v46;
        goto LABEL_39;
      }
      v26 = *v15;
      if ( (_WORD)v26 == tm.tmBreakChar )
        break;
      if ( a6 )
      {
        v27 = 0;
        if ( v26 == 9 )
          goto LABEL_15;
        v15 = *(const WCHAR **)Buffer;
      }
      Buffer[0] = 0;
      if ( !GetCharWidthW(*(HDC *)(v46 + 8), v26, v26, Buffer) )
        Buffer[0] = v56.tmAveCharWidth;
      if ( !GetCharWidthW(*(HDC *)(v46 + 16), *v15, *v15, v12) )
        *v12 = tm.tmAveCharWidth;
      *v12 -= tm.tmOverhang;
      v34 = *v12;
      v20 += *v12;
      if ( v12 != v47 )
      {
        v35 = (v56.tmOverhang + v34 - Buffer[0]) / 2;
        *(v12 - 1) += v35;
        *v12 = v34 - v35;
      }
      v36 = v43;
      ++v12;
      *(_WORD *)(v52 + 2LL * v43) = *v15;
      v24 = v36 + 1;
      v23 = (const WCHAR *)v49;
      ++v15;
      v43 = v24;
LABEL_37:
      *(_QWORD *)Buffer = v15;
      ++v44;
      v22 = *v48;
      if ( v44 >= *v48 )
        goto LABEL_38;
    }
    v27 = 1;
LABEL_15:
    v28 = v27 + ((__int64)(*(_QWORD *)Buffer - (_QWORD)v23) >> 1);
    if ( v28 > v22 )
      v28 = v22;
    GetTextExtentPoint32W(*(HDC *)(v46 + 16), v23, v28, &psizl);
    v25 += psizl.cx - tm.tmOverhang;
    if ( !v27 )
    {
      v29 = v25 - a9;
      v30 = a8;
      for ( i = 0; i < a7; ++i )
      {
        v32 = *v30;
        if ( *v30 > v29 )
          goto LABEL_24;
        ++v30;
      }
      if ( TabbedTextExtentA <= 0 )
        AfxThrowInvalidArgException();
      v32 = v29 - v29 % TabbedTextExtentA + TabbedTextExtentA;
LABEL_24:
      v25 = v32 + a9;
    }
    v33 = v25 - v20;
    if ( v12 == v47 )
      v21 += v33;
    else
      *(v12 - 1) += v33;
    v20 = v25;
    v24 = v43;
    v15 = (const WCHAR *)(*(_QWORD *)Buffer + 2LL);
    v23 = (const WCHAR *)(*(_QWORD *)Buffer + 2LL);
    v49 = *(_QWORD *)Buffer + 2LL;
    goto LABEL_37;
  }
LABEL_39:
  v37 = v53;
  v38 = v54;
  v53->cx = v20 - *a3;
  *v38 = 0;
  v39 = TextAlign & 6;
  if ( v39 )
  {
    if ( v39 == 6 )
    {
      *a3 += v21 / 2;
    }
    else if ( v39 == 2 )
    {
      *v38 = v21;
    }
  }
  else
  {
    *a3 += v21;
  }
  if ( v45 )
    MoveToEx(*(HDC *)(v14 + 8), *a3, pt.y, 0);
  *v48 = v12 - v47;
  return v37;
}

```

## disassembly

```asm
0x18004db00  push    rbp
0x18004db02  push    rbx
0x18004db03  push    rsi
0x18004db04  push    rdi
0x18004db05  push    r12
0x18004db07  push    r13
0x18004db09  push    r14
0x18004db0b  push    r15
0x18004db0d  lea     rbp, [rsp-28h]
0x18004db12  sub     rsp, 128h
0x18004db19  mov     rax, cs:__security_cookie
0x18004db20  xor     rax, rsp
0x18004db23  mov     [rbp+60h+var_50], rax
0x18004db27  mov     rax, [rbp+60h+arg_20]
0x18004db2e  xorps   xmm0, xmm0
0x18004db31  mov     rbx, [rbp+60h+lpBuffer]
0x18004db38  xorps   xmm1, xmm1
0x18004db3b  mov     [rsp+160h+var_108], rax
0x18004db40  mov     r14, rdx
0x18004db43  mov     rax, [rbp+60h+arg_48]
0x18004db4a  mov     rsi, rcx
0x18004db4d  mov     [rsp+160h+var_E8], rax
0x18004db52  mov     r15, r9
0x18004db55  mov     rax, [rbp+60h+arg_58]
0x18004db5c  mov     rdi, r8
0x18004db5f  mov     [rbp+60h+var_D8], rax
0x18004db63  xor     eax, eax
0x18004db65  mov     [rbp+60h+var_E0], rdx
0x18004db69  lea     rdx, [rbp+60h+tm]; lptm
0x18004db6d  mov     [rsp+160h+var_118], rcx
0x18004db72  mov     rcx, [rcx+10h]; hdc
0x18004db76  movups  xmmword ptr [rbp+60h+tm.tmOverhang], xmm0
0x18004db7a  mov     qword ptr [rsp+160h+Buffer], r9
0x18004db7f  movups  xmmword ptr [rbp+60h+var_90.tmOverhang], xmm1
0x18004db83  mov     [rsp+160h+var_110], rbx
0x18004db88  movups  xmmword ptr [rbp+60h+tm.tmHeight], xmm0
0x18004db8c  movups  xmmword ptr [rbp+60h+tm.tmExternalLeading], xmm0
0x18004db90  movups  xmmword ptr [rbp+60h+tm.tmFirstChar], xmm0
0x18004db94  movups  xmmword ptr [rbp+60h+var_90.tmHeight], xmm1
0x18004db98  movups  xmmword ptr [rbp+60h+var_90.tmExternalLeading], xmm1
0x18004db9c  movups  xmmword ptr [rbp+60h+var_90.tmFirstChar], xmm1
0x18004dba0  call    cs:__imp_GetTextMetricsW
0x18004dba6  mov     rcx, [rsi+8]; hdc
0x18004dbaa  lea     rdx, [rbp+60h+var_90]; lptm
0x18004dbae  call    cs:__imp_GetTextMetricsW
0x18004dbb4  mov     rcx, [rsi+10h]; hdc
0x18004dbb8  lea     rdx, aA; "A"
0x18004dbbf  mov     r9, r14; psizl
0x18004dbc2  mov     r14d, 1
0x18004dbc8  mov     r8d, r14d; c
0x18004dbcb  call    cs:__imp_GetTextExtentPoint32A
0x18004dbd1  mov     rcx, [rsi+10h]; hdc
0x18004dbd5  call    cs:__imp_GetTextAlign
0x18004dbdb  mov     r13d, eax
0x18004dbde  test    r14b, al
0x18004dbe1  jz      short loc_18004DBFF
0x18004dbe3  mov     rcx, [rsi+8]; hdc
0x18004dbe7  lea     rdx, [rsp+160h+pt]; lppt
0x18004dbec  mov     [rsp+160h+var_11C], r14d
0x18004dbf1  call    cs:__imp_GetCurrentPositionEx
0x18004dbf7  mov     eax, [rsp+160h+pt.x]
0x18004dbfb  mov     [rdi], eax
0x18004dbfd  jmp     short loc_18004DC07
0x18004dbff  mov     [rsp+160h+var_11C], 0
0x18004dc07  mov     r14d, [rdi]
0x18004dc0a  xor     r12d, r12d
0x18004dc0d  mov     [rsp+160h+var_128], r12d
0x18004dc12  cmp     [rbp+60h+arg_28], r12d
0x18004dc19  jz      short loc_18004DC57
0x18004dc1b  cmp     [rbp+60h+arg_30], 1
0x18004dc22  jnz     short loc_18004DC33
0x18004dc24  mov     rax, [rbp+60h+arg_38]
0x18004dc2b  mov     eax, [rax]
0x18004dc2d  mov     [rsp+160h+var_128], eax
0x18004dc31  jmp     short loc_18004DC57
0x18004dc33  mov     rcx, [rsi+10h]; hdc
0x18004dc37  lea     rdx, asc_1800FBA34; "\t"
0x18004dc3e  xor     r9d, r9d; nTabPositions
0x18004dc41  mov     [rsp+160h+lpnTabStopPositions], r12; lpnTabStopPositions
0x18004dc46  lea     r8d, [r9+1]; chCount
0x18004dc4a  call    cs:__imp_GetTabbedTextExtentA
0x18004dc50  movzx   ecx, ax
0x18004dc53  mov     [rsp+160h+var_128], ecx
0x18004dc57  mov     rax, [rsp+160h+var_108]
0x18004dc5c  mov     r8d, 2
0x18004dc62  mov     ecx, [rax]
0x18004dc64  test    ecx, ecx
0x18004dc66  jz      loc_18004DE33
0x18004dc6c  mov     rdx, r15; lpString
0x18004dc6f  mov     [rsp+160h+var_120], r12d
0x18004dc74  xor     r8d, r8d
0x18004dc77  mov     [rsp+160h+var_100], rdx
0x18004dc7c  mov     [rsp+160h+var_124], r8d
0x18004dc81  mov     esi, r14d
0x18004dc84  cmp     r8d, ecx
0x18004dc87  jnb     loc_18004DE28
0x18004dc8d  movzx   eax, word ptr [r15]
0x18004dc91  cmp     ax, [rbp+60h+tm.tmBreakChar]
0x18004dc95  jnz     short loc_18004DC9F
0x18004dc97  mov     r15d, 1
0x18004dc9d  jmp     short loc_18004DCB8
0x18004dc9f  cmp     [rbp+60h+arg_28], 0
0x18004dca6  jz      loc_18004DD69
0x18004dcac  xor     r15d, r15d
0x18004dcaf  cmp     eax, 9
0x18004dcb2  jnz     loc_18004DD64
0x18004dcb8  mov     rax, [rsp+160h+var_118]
0x18004dcbd  lea     r9, [rsp+160h+psizl]; psizl
0x18004dcc2  mov     r8, qword ptr [rsp+160h+Buffer]
0x18004dcc7  sub     r8, rdx
0x18004dcca  sar     r8, 1
0x18004dccd  add     r8d, r15d
0x18004dcd0  cmp     r8d, ecx
0x18004dcd3  cmova   r8d, ecx; c
0x18004dcd7  mov     rcx, [rax+10h]; hdc
0x18004dcdb  call    cs:__imp_GetTextExtentPoint32W
0x18004dce1  mov     eax, [rsp+160h+psizl.cx]
0x18004dce5  sub     eax, [rbp+60h+tm.tmOverhang]
0x18004dce8  add     esi, eax
0x18004dcea  test    r15d, r15d
0x18004dced  jnz     short loc_18004DD32
0x18004dcef  mov     r8d, [rbp+60h+arg_40]
0x18004dcf6  sub     esi, r8d
0x18004dcf9  mov     rcx, [rbp+60h+arg_38]
0x18004dd00  xor     eax, eax
0x18004dd02  cmp     eax, [rbp+60h+arg_30]
0x18004dd08  jnb     short loc_18004DD18
0x18004dd0a  mov     edx, [rcx]
0x18004dd0c  cmp     edx, esi
0x18004dd0e  jg      short loc_18004DD2E
0x18004dd10  inc     eax
0x18004dd12  add     rcx, 4
0x18004dd16  jmp     short loc_18004DD02
0x18004dd18  mov     ecx, [rsp+160h+var_128]
0x18004dd1c  test    ecx, ecx
0x18004dd1e  jle     loc_18004DE52
0x18004dd24  mov     eax, esi
0x18004dd26  cdq
0x18004dd27  idiv    ecx
0x18004dd29  sub     esi, edx
0x18004dd2b  lea     edx, [rsi+rcx]
0x18004dd2e  lea     esi, [rdx+r8]
0x18004dd32  mov     eax, esi
0x18004dd34  sub     eax, r14d
0x18004dd37  cmp     rbx, [rsp+160h+var_110]
0x18004dd3c  jnz     short loc_18004DD43
0x18004dd3e  add     r12d, eax
0x18004dd41  jmp     short loc_18004DD46
0x18004dd43  add     [rbx-4], eax
0x18004dd46  mov     r15, qword ptr [rsp+160h+Buffer]
0x18004dd4b  mov     r14d, esi
0x18004dd4e  mov     r8d, [rsp+160h+var_124]
0x18004dd53  add     r15, 2
0x18004dd57  mov     rdx, r15
0x18004dd5a  mov     [rsp+160h+var_100], rdx
0x18004dd5f  jmp     loc_18004DE0A
0x18004dd64  mov     r15, qword ptr [rsp+160h+Buffer]
0x18004dd69  mov     edx, eax; iFirst
0x18004dd6b  mov     [rsp+160h+Buffer], 0
0x18004dd73  mov     r8d, eax; iLast
0x18004dd76  lea     r9, [rsp+160h+Buffer]; lpBuffer
0x18004dd7b  mov     rax, [rsp+160h+var_118]
0x18004dd80  mov     rcx, [rax+8]; hdc
0x18004dd84  call    cs:__imp_GetCharWidthW
0x18004dd8a  test    eax, eax
0x18004dd8c  jnz     short loc_18004DD95
0x18004dd8e  mov     eax, [rbp+60h+var_90.tmAveCharWidth]
0x18004dd91  mov     [rsp+160h+Buffer], eax
0x18004dd95  mov     rax, [rsp+160h+var_118]
0x18004dd9a  mov     r9, rbx; lpBuffer
0x18004dd9d  movzx   edx, word ptr [r15]; iFirst
0x18004dda1  mov     r8d, edx; iLast
0x18004dda4  mov     rcx, [rax+10h]; hdc
0x18004dda8  call    cs:__imp_GetCharWidthW
0x18004ddae  test    eax, eax
0x18004ddb0  jnz     short loc_18004DDB7
0x18004ddb2  mov     eax, [rbp+60h+tm.tmAveCharWidth]
0x18004ddb5  mov     [rbx], eax
0x18004ddb7  mov     eax, [rbp+60h+tm.tmOverhang]
0x18004ddba  sub     [rbx], eax
0x18004ddbc  mov     ecx, [rbx]
0x18004ddbe  add     r14d, ecx
0x18004ddc1  cmp     rbx, [rsp+160h+var_110]
0x18004ddc6  jz      short loc_18004DDE2
0x18004ddc8  mov     eax, ecx
0x18004ddca  mov     r8d, 2
0x18004ddd0  sub     eax, [rsp+160h+Buffer]
0x18004ddd4  add     eax, [rbp+60h+var_90.tmOverhang]
0x18004ddd7  cdq
0x18004ddd8  idiv    r8d
0x18004dddb  sub     ecx, eax
0x18004dddd  add     [rbx-4], eax
0x18004dde0  mov     [rbx], ecx
0x18004dde2  mov     r8d, [rsp+160h+var_124]
0x18004dde7  add     rbx, 4
0x18004ddeb  mov     rdx, [rsp+160h+var_E8]
0x18004ddf0  movzx   eax, word ptr [r15]
0x18004ddf4  mov     [rdx+r8*2], ax
0x18004ddf9  inc     r8d
0x18004ddfc  mov     rdx, [rsp+160h+var_100]
0x18004de01  add     r15, 2
0x18004de05  mov     [rsp+160h+var_124], r8d
0x18004de0a  mov     eax, [rsp+160h+var_120]
0x18004de0e  mov     rcx, [rsp+160h+var_108]
0x18004de13  inc     eax
0x18004de15  mov     qword ptr [rsp+160h+Buffer], r15
0x18004de1a  mov     [rsp+160h+var_120], eax
0x18004de1e  mov     ecx, [rcx]
0x18004de20  cmp     eax, ecx
0x18004de22  jb      loc_18004DC84
0x18004de28  mov     rsi, [rsp+160h+var_118]
0x18004de2d  mov     r8d, 2
0x18004de33  sub     r14d, [rdi]
0x18004de36  mov     r15, [rbp+60h+var_E0]
0x18004de3a  mov     rax, [rbp+60h+var_D8]
0x18004de3e  mov     [r15], r14d
0x18004de41  mov     dword ptr [rax], 0
0x18004de47  and     r13d, 6
0x18004de4b  jnz     short loc_18004DE58
0x18004de4d  add     [rdi], r12d
0x18004de50  jmp     short loc_18004DE71
0x18004de52  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x18004de58  cmp     r13d, 6
0x18004de5c  jnz     short loc_18004DE69
0x18004de5e  mov     eax, r12d
0x18004de61  cdq
0x18004de62  idiv    r8d
0x18004de65  add     [rdi], eax
0x18004de67  jmp     short loc_18004DE71
0x18004de69  cmp     r13d, r8d
0x18004de6c  jnz     short loc_18004DE71
0x18004de6e  mov     [rax], r12d
0x18004de71  cmp     [rsp+160h+var_11C], 0
0x18004de76  jz      short loc_18004DE8C
0x18004de78  mov     r8d, [rsp+160h+pt.y]; y
0x18004de7d  xor     r9d, r9d; lppt
0x18004de80  mov     edx, [rdi]; x
0x18004de82  mov     rcx, [rsi+8]; hdc
0x18004de86  call    cs:__imp_MoveToEx
0x18004de8c  mov     rax, [rsp+160h+var_108]
0x18004de91  sub     rbx, [rsp+160h+var_110]
0x18004de96  sar     rbx, 2
0x18004de9a  mov     [rax], ebx
0x18004de9c  mov     rax, r15
0x18004de9f  mov     rcx, [rbp+60h+var_50]
0x18004dea3  xor     rcx, rsp; StackCookie
0x18004dea6  call    __security_check_cookie
0x18004deab  add     rsp, 128h
0x18004deb2  pop     r15
0x18004deb4  pop     r14
0x18004deb6  pop     r13
0x18004deb8  pop     r12
0x18004deba  pop     rdi
0x18004debb  pop     rsi
0x18004debc  pop     rbx
0x18004debd  pop     rbp
0x18004debe  retn
```
