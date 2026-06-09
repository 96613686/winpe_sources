# CILogRead::_DumpDataPage(char *,ulong,ulong,_RECORDPAGE *,_DUMP_TYPE,ulong *,ulong)

- ea: `0x18000341c`
- end: `0x180003925`
- name: `?_DumpDataPage@CILogRead@@AEAAJPEADKKPEAU_RECORDPAGE@@W4_DUMP_TYPE@@PEAKK@Z`
- size: `1289`
- prototype: `int __high(char *, unsigned int, unsigned int, struct _RECORDPAGE *, enum _DUMP_TYPE, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180002900`

## callees

- `0x180001300`
- `0x180003358`
- `0x18000341c`
- `0x18000392c`
- `0x1800127f2`
- `0x180012830`

## import_xrefs

- `msvcrt!isprint` at `0x1800036a0`
- `msvcrt!isprint` at `0x1800036a0`

## string_xrefs

- `0x1800034a7`: `Residue Data Page %d for Page %d\n`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CILogRead::_DumpDataPage(
        __int64 a1,
        char *a2,
        unsigned int a3,
        int a4,
        _DWORD *a5,
        int a6,
        _DWORD *a7,
        int a8)
{
  char *v9; // r13
  unsigned int v11; // ebx
  char *v12; // r14
  char *v13; // rdi
  unsigned int v15; // ebx
  char *v16; // rdi
  unsigned int v17; // ebx
  char *v18; // rdi
  unsigned int v19; // ebx
  char *v20; // rdi
  unsigned int v21; // ebx
  char *v22; // r14
  CILogRead *v23; // rcx
  unsigned int v24; // ebx
  struct _LOGRECHEADER *v25; // r15
  char *v26; // rdi
  int v27; // r14d
  int v28; // r12d
  unsigned int v29; // ebx
  char *v30; // rdi
  int i; // esi
  char v32; // al
  struct _LOGRECHEADER *v33; // r13
  int v34; // edx
  unsigned int v35; // r8d
  int v36; // r10d
  int v37; // r9d
  int v38; // eax
  int v39; // r15d
  int v40; // r12d
  const char *v41; // rax
  CILogRead *v42; // rcx
  char *v43; // r14
  unsigned int v44; // r12d
  int v45; // r15d
  unsigned int v46; // eax
  const char *v47; // rax
  char *v48; // r14
  unsigned int v49; // [rsp+30h] [rbp-78h] BYREF
  unsigned int v50; // [rsp+34h] [rbp-74h] BYREF
  char *v51; // [rsp+38h] [rbp-70h]
  _DWORD *v52; // [rsp+48h] [rbp-60h]
  char v53[24]; // [rsp+50h] [rbp-58h] BYREF

  v9 = a2;
  v51 = a2;
  v52 = a7;
  v49 = 0;
  if ( (unsigned int)(a4 - 2) <= 1 )
    TracedSafeStrPrintfA(
      a2,
      a3,
      &v49,
      "Residue Data Page %d for Page %d\n",
      a4,
      a5[3] / *(_DWORD *)(*(_QWORD *)(a1 + 16) + 632LL));
  else
    TracedSafeStrPrintfA(a2, a3, &v49, "Data Page %d \n", a4);
  if ( a3 < v49 )
    return 2147942934LL;
  v11 = a3 - v49;
  v12 = &v9[v49];
  if ( a8 == a5[1] )
  {
    v13 = &v9[v49];
  }
  else
  {
    TracedSafeStrPrintfA(v12, v11, &v49, "!!! BAD CHECKSUM !!!\n\tChecksum   :  %.8X\n", a8);
    if ( v11 < v49 )
      return 2147942934LL;
    v13 = &v12[v49];
    v11 -= v49;
  }
  TracedSafeStrPrintfA(v13, v11, &v49, "\tSignature  :  %.8X \tChecksum   :  %.8X\n", *a5, a5[1]);
  if ( v11 < v49 )
    return 2147942934LL;
  v15 = v11 - v49;
  v16 = &v13[v49];
  TracedSafeStrPrintfA(v16, v15, &v49, "\tGeneration :  %.8X \tPageOffset :  %.8X\n", a5[2], a5[3]);
  if ( v15 < v49 )
    return 2147942934LL;
  v17 = v15 - v49;
  v18 = &v16[v49];
  TracedSafeStrPrintfA(v18, v17, &v49, "\tVersion    :  %.8X \tOffset     :  %.8X\n", a5[4], a5[5]);
  if ( v17 < v49 )
    return 2147942934LL;
  v19 = v17 - v49;
  v20 = &v18[v49];
  TracedSafeStrPrintfA(v20, v19, &v49, "\tSpace      :  %.8X \tLastStart  :  %.8X\n", a5[6], a5[7]);
  if ( v19 < v49 )
    return 2147942934LL;
  v21 = v19 - v49;
  v22 = &v20[v49];
  TracedSafeStrPrintfA(v22, v21, &v49, "======================================================\n\n");
  if ( v21 < v49 )
    return 2147942934LL;
  v24 = v21 - v49;
  v25 = (struct _LOGRECHEADER *)(a5 + 8);
  v26 = &v22[v49];
  if ( a6 )
  {
    if ( a6 != 1 || !a5 )
      goto LABEL_70;
    v33 = 0;
    v34 = a5[3] + 32;
    v35 = 0;
    v36 = 1;
    do
    {
      if ( v35 >= 0x1FE0 )
        break;
      v37 = *(_DWORD *)v25;
      if ( *(_DWORD *)v25 == v34 )
        v33 = v25;
      else
        v25 = (struct _LOGRECHEADER *)((char *)v25 + 4);
      v38 = 0;
      if ( v37 != v34 )
        v38 = v36;
      v36 = v38;
      if ( v37 != v34 )
        v35 += 4;
      v23 = (CILogRead *)(unsigned int)(v34 + 4);
      if ( v37 != v34 )
        v34 += 4;
    }
    while ( v38 );
    if ( v33 )
    {
      v39 = *(_DWORD *)(*(_QWORD *)(a1 + 16) + 632LL);
      v40 = a5[3];
      v41 = CILogRead::_DumpLRH(v23, v33, &v50);
      v43 = (char *)v41;
      if ( v41 )
      {
        TracedSafeStrPrintfA(v26, v24, &v49, "%s\n", v41);
        operator delete(v43);
        v42 = (CILogRead *)v49;
        if ( v24 < v49 )
          return 2147942934LL;
        v26 += v49;
        v24 -= v49;
      }
      v44 = v39 + v40;
      v45 = 1;
      while ( v45 )
      {
        v46 = *((_DWORD *)v33 + 5);
        if ( v46 > v44 || v46 < *(_DWORD *)v33 )
        {
          v45 = 0;
        }
        else
        {
          v33 = (struct _LOGRECHEADER *)((char *)a5 + v46 - a5[3]);
          v47 = CILogRead::_DumpLRH(v42, v33, &v50);
          v48 = (char *)v47;
          if ( v47 )
          {
            TracedSafeStrPrintfA(v26, v24, &v49, "%s\n", v47);
            operator delete(v48);
            v42 = (CILogRead *)v49;
            if ( v24 < v49 )
              return 2147942934LL;
            v26 += v49;
            v24 -= v49;
          }
        }
      }
    }
  }
  else
  {
    v27 = 8160;
    v28 = a5[3] + 32;
    while ( v27 > 0 )
    {
      if ( v27 < 16 )
        memcpy_0((char *)v25 + v27, "0000000000000000", 16 - v27);
      TracedSafeStrPrintfA(v26, v24, &v49, "%.6X  ", v28);
      if ( v24 < v49 )
        return 2147942934LL;
      v29 = v24 - v49;
      v30 = &v26[v49];
      v53[16] = 0;
      for ( i = 0; i < 16; ++i )
      {
        v50 = *((unsigned __int8 *)v25 + i);
        if ( isprint(v50) )
          v32 = *((_BYTE *)v25 + i);
        else
          v32 = 46;
        v53[i] = v32;
        if ( i == 7 )
        {
          TracedSafeStrPrintfA(v30, v29, &v49, "%.2hX  ", v50);
          if ( v29 < v49 )
            return 2147942934LL;
          v29 -= v49;
          v30 += v49;
        }
        else
        {
          TracedSafeStrPrintfA(v30, v29, &v49, "%.2hX ", v50);
          if ( v29 < v49 )
            return 2147942934LL;
          v30 += v49;
          v29 -= v49;
        }
      }
      TracedSafeStrPrintfA(v30, v29, &v49, " %s\n", v53);
      if ( v29 < v49 )
        return 2147942934LL;
      v24 = v29 - v49;
      v26 = &v30[v49];
      if ( v27 <= 16 )
        v27 = 0;
      else
        v27 -= 16;
      v28 += 16;
      v25 = (struct _LOGRECHEADER *)((char *)v25 + 16);
    }
  }
  LODWORD(v9) = (_DWORD)v51;
LABEL_70:
  if ( v52 )
    *v52 = (_DWORD)v26 - (_DWORD)v9 + 1;
  return 0;
}

```

## disassembly

```asm
0x18000341c  push    rbx
0x18000341e  push    rsi
0x18000341f  push    rdi
0x180003420  push    r12
0x180003422  push    r13
0x180003424  push    r14
0x180003426  push    r15
0x180003428  sub     rsp, 70h
0x18000342c  mov     rax, cs:__security_cookie
0x180003433  xor     rax, rsp
0x180003436  mov     [rsp+0A8h+var_40], rax
0x18000343b  mov     ebx, r8d
0x18000343e  mov     r13, rdx
0x180003441  mov     [rsp+0A8h+var_70], rdx
0x180003446  mov     r12, rcx
0x180003449  mov     rsi, [rsp+0A8h+arg_20]
0x180003451  mov     rax, [rsp+0A8h+arg_30]
0x180003459  mov     [rsp+0A8h+var_60], rax
0x18000345e  mov     [rsp+0A8h+var_78], 0
0x180003466  lea     eax, [r9-2]
0x18000346a  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x18000346f  cmp     eax, 1
0x180003472  jbe     short loc_18000348C
0x180003474  mov     edx, ebx; unsigned __int64
0x180003476  mov     dword ptr [rsp+0A8h+var_88], r9d
0x18000347b  lea     r9, aDataPageD; "Data Page %d \n"
0x180003482  mov     rcx, r13; char *
0x180003485  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x18000348a  jmp     short loc_1800034B6
0x18000348c  mov     rcx, [rcx+10h]
0x180003490  xor     edx, edx
0x180003492  mov     eax, [rsi+0Ch]
0x180003495  div     dword ptr [rcx+278h]
0x18000349b  mov     rdx, rbx; unsigned __int64
0x18000349e  mov     [rsp+0A8h+var_80], eax
0x1800034a2  mov     dword ptr [rsp+0A8h+var_88], r9d
0x1800034a7  lea     r9, aResidueDataPag; "Residue Data Page %d for Page %d\n"
0x1800034ae  mov     rcx, r13; char *
0x1800034b1  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800034b6  mov     eax, [rsp+0A8h+var_78]
0x1800034ba  cmp     ebx, eax
0x1800034bc  jb      loc_1800038F6
0x1800034c2  sub     ebx, eax
0x1800034c4  mov     edi, ebx
0x1800034c6  lea     r14, [rax+r13]
0x1800034ca  mov     eax, [rsp+0A8h+arg_38]
0x1800034d1  cmp     eax, [rsi+4]
0x1800034d4  jz      short loc_18000350A
0x1800034d6  mov     edx, edi; unsigned __int64
0x1800034d8  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800034dc  lea     r9, aBadChecksumChe; "!!! BAD CHECKSUM !!!\n\tChecksum   :  %"...
0x1800034e3  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x1800034e8  mov     rcx, r14; char *
0x1800034eb  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800034f0  mov     eax, [rsp+0A8h+var_78]
0x1800034f4  cmp     edi, eax
0x1800034f6  jb      short loc_180003500
0x1800034f8  lea     rdi, [r14+rax]
0x1800034fc  sub     ebx, eax
0x1800034fe  jmp     short loc_18000350D
0x180003500  mov     eax, 80070216h
0x180003505  jmp     loc_180003907
0x18000350a  mov     rdi, r14
0x18000350d  mov     edx, ebx; unsigned __int64
0x18000350f  mov     eax, [rsi+4]
0x180003512  mov     [rsp+0A8h+var_80], eax
0x180003516  mov     eax, [rsi]
0x180003518  mov     dword ptr [rsp+0A8h+var_88], eax
0x18000351c  lea     r9, aSignature8xChe; "\tSignature  :  %.8X \tChecksum   :  %."...
0x180003523  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x180003528  mov     rcx, rdi; char *
0x18000352b  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003530  mov     eax, [rsp+0A8h+var_78]
0x180003534  cmp     ebx, eax
0x180003536  jb      loc_1800038EF
0x18000353c  sub     ebx, eax
0x18000353e  add     rdi, rax
0x180003541  mov     edx, ebx; unsigned __int64
0x180003543  mov     eax, [rsi+0Ch]
0x180003546  mov     [rsp+0A8h+var_80], eax
0x18000354a  mov     eax, [rsi+8]
0x18000354d  mov     dword ptr [rsp+0A8h+var_88], eax
0x180003551  lea     r9, aGeneration8xPa; "\tGeneration :  %.8X \tPageOffset :  %."...
0x180003558  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x18000355d  mov     rcx, rdi; char *
0x180003560  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003565  mov     eax, [rsp+0A8h+var_78]
0x180003569  cmp     ebx, eax
0x18000356b  jb      loc_1800038E8
0x180003571  sub     ebx, eax
0x180003573  add     rdi, rax
0x180003576  mov     edx, ebx; unsigned __int64
0x180003578  mov     eax, [rsi+14h]
0x18000357b  mov     [rsp+0A8h+var_80], eax
0x18000357f  mov     eax, [rsi+10h]
0x180003582  mov     dword ptr [rsp+0A8h+var_88], eax
0x180003586  lea     r9, aVersion8xOffse; "\tVersion    :  %.8X \tOffset     :  %."...
0x18000358d  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x180003592  mov     rcx, rdi; char *
0x180003595  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x18000359a  mov     eax, [rsp+0A8h+var_78]
0x18000359e  cmp     ebx, eax
0x1800035a0  jb      loc_1800038E1
0x1800035a6  sub     ebx, eax
0x1800035a8  add     rdi, rax
0x1800035ab  mov     edx, ebx; unsigned __int64
0x1800035ad  mov     eax, [rsi+1Ch]
0x1800035b0  mov     [rsp+0A8h+var_80], eax
0x1800035b4  mov     eax, [rsi+18h]
0x1800035b7  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800035bb  lea     r9, aSpace8xLaststa; "\tSpace      :  %.8X \tLastStart  :  %."...
0x1800035c2  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x1800035c7  mov     rcx, rdi; char *
0x1800035ca  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800035cf  mov     eax, [rsp+0A8h+var_78]
0x1800035d3  cmp     ebx, eax
0x1800035d5  jb      loc_1800038DA
0x1800035db  sub     ebx, eax
0x1800035dd  lea     r14, [rdi+rax]
0x1800035e1  mov     edx, ebx; unsigned __int64
0x1800035e3  lea     r9, asc_180017348; "======================================="...
0x1800035ea  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x1800035ef  mov     rcx, r14; char *
0x1800035f2  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800035f7  mov     eax, [rsp+0A8h+var_78]
0x1800035fb  cmp     ebx, eax
0x1800035fd  jb      loc_1800038D3
0x180003603  sub     ebx, eax
0x180003605  lea     r15, [rsi+20h]
0x180003609  lea     rdi, [r14+rax]
0x18000360d  mov     eax, [rsp+0A8h+arg_28]
0x180003614  test    eax, eax
0x180003616  jnz     loc_18000377A
0x18000361c  mov     r14d, 1FE0h
0x180003622  mov     r12d, [rsi+0Ch]
0x180003626  add     r12d, 20h ; ' '
0x18000362a  test    r14d, r14d
0x18000362d  jle     loc_1800038B9
0x180003633  cmp     r14d, 10h
0x180003637  jge     short loc_180003656
0x180003639  mov     eax, 10h
0x18000363e  sub     eax, r14d
0x180003641  movsxd  r8, eax; Size
0x180003644  movsxd  rcx, r14d
0x180003647  add     rcx, r15; void *
0x18000364a  lea     rdx, a00000000000000; "0000000000000000"
0x180003651  call    memcpy_0
0x180003656  mov     edx, ebx; unsigned __int64
0x180003658  mov     dword ptr [rsp+0A8h+var_88], r12d
0x18000365d  lea     r9, a6x; "%.6X  "
0x180003664  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x180003669  mov     rcx, rdi; char *
0x18000366c  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x180003671  mov     eax, [rsp+0A8h+var_78]
0x180003675  cmp     ebx, eax
0x180003677  jb      loc_180003770
0x18000367d  sub     ebx, eax
0x18000367f  add     rdi, rax
0x180003682  mov     [rsp+0A8h+var_48], 0
0x180003687  xor     esi, esi
0x180003689  cmp     esi, 10h
0x18000368c  jge     loc_18000371D
0x180003692  movsxd  r13, esi
0x180003695  movzx   eax, byte ptr [r15+r13]
0x18000369a  mov     [rsp+0A8h+var_74], eax
0x18000369e  mov     ecx, eax; C
0x1800036a0  call    cs:__imp_isprint
0x1800036a6  test    eax, eax
0x1800036a8  jz      short loc_1800036B0
0x1800036aa  mov     al, [r15+r13]
0x1800036ae  jmp     short loc_1800036B2
0x1800036b0  mov     al, 2Eh ; '.'
0x1800036b2  mov     [rsp+r13+0A8h+var_58], al
0x1800036b7  mov     edx, ebx; unsigned __int64
0x1800036b9  mov     eax, [rsp+0A8h+var_74]
0x1800036bd  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x1800036c2  mov     rcx, rdi; char *
0x1800036c5  mov     dword ptr [rsp+0A8h+var_88], eax
0x1800036c9  cmp     esi, 7
0x1800036cc  jnz     short loc_1800036F3
0x1800036ce  lea     r9, a2hx; "%.2hX  "
0x1800036d5  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800036da  mov     eax, [rsp+0A8h+var_78]
0x1800036de  cmp     ebx, eax
0x1800036e0  jb      short loc_1800036E9
0x1800036e2  sub     ebx, eax
0x1800036e4  add     rdi, rax
0x1800036e7  jmp     short loc_18000370C
0x1800036e9  mov     eax, 80070216h
0x1800036ee  jmp     loc_180003907
0x1800036f3  lea     r9, a2hx_0; "%.2hX "
0x1800036fa  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x1800036ff  mov     ecx, [rsp+0A8h+var_78]
0x180003703  cmp     ebx, ecx
0x180003705  jb      short loc_180003713
0x180003707  add     rdi, rcx
0x18000370a  sub     ebx, ecx
0x18000370c  inc     esi
0x18000370e  jmp     loc_180003689
0x180003713  mov     eax, 80070216h
0x180003718  jmp     loc_180003907
0x18000371d  mov     edx, ebx; unsigned __int64
0x18000371f  lea     rax, [rsp+0A8h+var_58]
0x180003724  mov     [rsp+0A8h+var_88], rax
0x180003729  lea     r9, aS; " %s\n"
0x180003730  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x180003735  mov     rcx, rdi; char *
0x180003738  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x18000373d  mov     eax, [rsp+0A8h+var_78]
0x180003741  cmp     ebx, eax
0x180003743  jb      short loc_180003766
0x180003745  sub     ebx, eax
0x180003747  add     rdi, rax
0x18000374a  cmp     r14d, 10h
0x18000374e  jle     short loc_180003756
0x180003750  sub     r14d, 10h
0x180003754  jmp     short loc_180003759
0x180003756  xor     r14d, r14d
0x180003759  add     r12d, 10h
0x18000375d  add     r15, 10h
0x180003761  jmp     loc_18000362A
0x180003766  mov     eax, 80070216h
0x18000376b  jmp     loc_180003907
0x180003770  mov     eax, 80070216h
0x180003775  jmp     loc_180003907
0x18000377a  cmp     eax, 1
0x18000377d  jnz     loc_1800038BE
0x180003783  test    rsi, rsi
0x180003786  jz      loc_1800038BE
0x18000378c  xor     r13d, r13d
0x18000378f  mov     edx, [rsi+0Ch]
0x180003792  add     edx, 20h ; ' '
0x180003795  xor     r8d, r8d
0x180003798  mov     r10d, eax
0x18000379b  mov     r14d, 1FE0h
0x1800037a1  cmp     r8d, r14d
0x1800037a4  jnb     short loc_1800037D6
0x1800037a6  mov     r9d, [r15]
0x1800037a9  cmp     r9d, edx
0x1800037ac  jnz     short loc_1800037B3
0x1800037ae  mov     r13, r15
0x1800037b1  jmp     short loc_1800037B7
0x1800037b3  add     r15, 4
0x1800037b7  xor     eax, eax
0x1800037b9  cmp     r9d, edx
0x1800037bc  cmovnz  eax, r10d
0x1800037c0  mov     r10d, eax
0x1800037c3  lea     eax, [r8+4]
0x1800037c7  cmovnz  r8d, eax
0x1800037cb  lea     ecx, [rdx+4]; this
0x1800037ce  cmovnz  edx, ecx
0x1800037d1  test    r10d, r10d
0x1800037d4  jnz     short loc_1800037A1
0x1800037d6  test    r13, r13
0x1800037d9  jz      loc_1800038B9
0x1800037df  mov     rax, [r12+10h]
0x1800037e4  mov     r15d, [rax+278h]
0x1800037eb  mov     r12d, [rsi+0Ch]
0x1800037ef  lea     r8, [rsp+0A8h+var_74]; unsigned int *
0x1800037f4  mov     rdx, r13; struct _LOGRECHEADER *
0x1800037f7  call    ?_DumpLRH@CILogRead@@AEAAPEADPEAU_LOGRECHEADER@@PEAK@Z; CILogRead::_DumpLRH(_LOGRECHEADER *,ulong *)
0x1800037fc  mov     r14, rax
0x1800037ff  test    rax, rax
0x180003802  jz      short loc_180003840
0x180003804  mov     edx, ebx; unsigned __int64
0x180003806  mov     [rsp+0A8h+var_88], rax
0x18000380b  lea     r9, aS_2; "%s\n"
0x180003812  lea     r8, [rsp+0A8h+var_78]; unsigned int *
0x180003817  mov     rcx, rdi; char *
0x18000381a  call    ?TracedSafeStrPrintfA@@YAXPEAD_KPEAKPEBDZZ; TracedSafeStrPrintfA(char *,unsigned __int64,ulong *,char const *,...)
0x18000381f  mov     rcx, r14; Block
0x180003822  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003827  mov     ecx, [rsp+0A8h+var_78]
0x18000382b  cmp     ebx, ecx
0x18000382d  jb      short loc_180003836
0x18000382f  add     rdi, rcx
0x180003832  sub     ebx, ecx
0x180003834  jmp     short loc_180003840
0x180003836  mov     eax, 80070216h
0x18000383b  jmp     loc_180003907
0x180003840  add     r12d, r15d
0x180003843  mov     r15d, 1
0x180003849  test    r15d, r15d
0x18000384c  jz      short loc_1800038B9
0x18000384e  mov     eax, [r13+14h]
0x180003852  cmp     eax, r12d
0x180003855  ja      short loc_1800038B4
0x180003857  cmp     eax, [r13+0]
0x18000385b  jb      short loc_1800038B4
0x18000385d  sub     eax, [rsi+0Ch]
0x180003860  mov     r13d, eax
0x180003863  add     r13, rsi
0x180003866  lea     r8, [rsp+0A8h+var_74]; unsigned int *
0x18000386b  mov     rdx, r13; struct _LOGRECHEADER *
0x18000386e  call    ?_DumpLRH@CILogRead@@AEAAPEADPEAU_LOGRECHEADER@@PEAK@Z; CILogRead::_DumpLRH(_LOGRECHEADER *,ulong *)
0x180003873  mov     r14, rax
0x180003876  test    rax, rax
0x180003879  jz      short loc_180003849
0x18000387b  mov     edx, ebx; unsigned __int64
0x18000387d  mov     [rsp+0A8h+var_88], rax
  ... truncated ...
```
