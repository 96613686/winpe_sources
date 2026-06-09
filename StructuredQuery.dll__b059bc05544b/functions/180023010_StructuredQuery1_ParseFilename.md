# StructuredQuery1::ParseFilename

- ea: `0x180023010`
- end: `0x1800236af`
- name: `StructuredQuery1::ParseFilename`
- size: `1695`
- prototype: `__int64 __usercall@<rax>(wchar_t *@<rcx>, unsigned int@<edx>, __int64, __int64, __int64, __int64, __int64, __int64, __int64, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x180023710`

## callees

- `0x180023010`
- `0x1800236c0`
- `0x180023e34`
- `0x180025a80`
- `0x1800263c4`
- `0x18003af18`
- `0x18005daf0`

## import_xrefs

- `OLEAUT32!__imp_VarI4FromStr` at `0x18002357b`
- `OLEAUT32!__imp_VarI4FromStr` at `0x18002357b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002311b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002315c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800231a2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800231ff`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002311b`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18002315c`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800231a2`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x1800231ff`

## pseudocode

```c
char __fastcall StructuredQuery1::ParseFilename(
        wchar_t *a1,
        unsigned int a2,
        LCID a3,
        int a4,
        _DWORD *a5,
        wchar_t **a6,
        wchar_t **a7,
        struct tagPROPVARIANT **a8,
        wchar_t **a9,
        int *a10,
        int *a11,
        __int64 a12)
{
  int v12; // r15d
  unsigned int v13; // esi
  DWORD v14; // r11d
  wchar_t *v17; // rdi
  char v18; // bl
  int v19; // r12d
  int v20; // ebp
  __int64 v21; // rdx
  wchar_t v22; // dx
  struct tagPROPVARIANT *v23; // rax
  unsigned __int16 v24; // r10
  struct tagPROPVARIANT *v25; // rdx
  wchar_t *v26; // rax
  wchar_t *v27; // r8
  int v28; // r11d
  wchar_t v29; // cx
  bool v30; // cl
  unsigned __int64 v31; // r9
  int v32; // r11d
  WCHAR v33; // ax
  wchar_t *v34; // rbx
  struct tagPROPVARIANT *v36; // rsi
  wchar_t *v37; // r13
  unsigned __int64 v38; // rax
  OLECHAR *v39; // rdx
  OLECHAR *v40; // r9
  __int64 v41; // r8
  OLECHAR *v42; // rcx
  wchar_t *v43; // rax
  _BYTE *v44; // rcx
  unsigned __int64 v45; // r10
  unsigned __int16 v46; // cx
  unsigned __int64 v47; // r9
  wchar_t v48; // cx
  bool IsReverseSolidus; // cl
  struct tagPROPVARIANT *v50; // kr00_8
  struct tagPROPVARIANT *v51; // kr10_8
  char v52; // [rsp+30h] [rbp-E8h]
  char v53; // [rsp+31h] [rbp-E7h]
  LONG plOut[2]; // [rsp+38h] [rbp-E0h] BYREF
  wchar_t *v55; // [rsp+40h] [rbp-D8h]
  LCID lcid; // [rsp+48h] [rbp-D0h]
  wchar_t *v57; // [rsp+50h] [rbp-C8h]
  _DWORD *v58; // [rsp+58h] [rbp-C0h]
  wchar_t **v59; // [rsp+60h] [rbp-B8h]
  wchar_t **v60; // [rsp+68h] [rbp-B0h]
  struct tagPROPVARIANT **v61; // [rsp+70h] [rbp-A8h]
  wchar_t **v62; // [rsp+78h] [rbp-A0h]
  int *v63; // [rsp+80h] [rbp-98h]
  int *v64; // [rsp+88h] [rbp-90h]
  __int64 v65; // [rsp+90h] [rbp-88h]
  OLECHAR strIn[32]; // [rsp+98h] [rbp-80h] BYREF

  v58 = a5;
  v12 = 0;
  v13 = a2 - a4;
  v59 = a6;
  v14 = 1;
  v60 = a7;
  v61 = a8;
  v62 = a9;
  v63 = a10;
  v64 = a11;
  v65 = a12;
  lcid = a3;
  v17 = &a1[a4];
  if ( a2 != a4
    && SemanticsUM::Syntax::IsDoubleQuote(a1[a4])
    && !SemanticsUM::Syntax::QuoteIsPartOfHebrewNumber(v45, a1, a2) )
  {
    ++v17;
    v12 = v14;
    --v13;
  }
  v53 = 0;
  v18 = 0;
  v57 = v17;
  v55 = 0;
  v19 = 2;
  *(_QWORD *)plOut = 0;
  if ( v13 < 8 )
  {
    if ( v13 < 4 )
      goto LABEL_8;
  }
  else
  {
    if ( CompareStringW(0x7Fu, v14, v17, 8, L"\\\\?\\UNC\\", -1) == 2 )
    {
      v17 += 8;
      v52 = 1;
      v13 -= 8;
      v20 = 2;
      goto LABEL_14;
    }
    v14 = 1;
  }
  if ( CompareStringW(0x7Fu, v14, v17, 4, L"\\\\?\\", -1) == 2 )
  {
    v13 -= 4;
    v17 += 4;
    v52 = 1;
    v20 = 2;
    if ( v13 >= 2 )
      goto LABEL_10;
LABEL_13:
    v18 = 1;
    goto LABEL_14;
  }
  v14 = 1;
LABEL_8:
  v20 = 0;
  v52 = 0;
  if ( v13 < 2 )
    goto LABEL_13;
  if ( CompareStringW(0x7Fu, v14, v17, 2, L"\\\\", -1) != 2 )
  {
LABEL_10:
    v21 = 0x3FFFFFF03FFFFFFLL;
    if ( (unsigned __int16)(*v17 - 65) <= 0x39u && _bittest64(&v21, (unsigned __int16)(*v17 - 65))
      || (v46 = *v17 + 223, v46 <= 0x39u) && _bittest64(&v21, v46) )
    {
      if ( CompareStringW(0x7Fu, 1u, v17 + 1, 1, L":", -1) == 2 )
      {
        if ( v13 >= 3 && StructuredQuery1::IsPathSeparator((StructuredQuery1 *)v17[2], v22) )
        {
          v48 = v17[2];
          v17 += 3;
          v55 = v17;
          v13 -= 3;
          IsReverseSolidus = SemanticsUM::Syntax::IsReverseSolidus(v48);
          if ( (unsigned int)IsReverseSolidus + 1 > v20 )
            v20 = IsReverseSolidus + 1;
        }
        else
        {
          v17 += 2;
          v13 -= 2;
          if ( !v20 )
            v20 = 1;
        }
        v52 = 1;
      }
    }
    goto LABEL_13;
  }
  v17 += 2;
  v52 = 1;
  v13 -= 2;
  v20 = 2;
LABEL_14:
  v23 = 0;
  v24 = -246;
  if ( !v18 )
    v23 = *(struct tagPROPVARIANT **)plOut;
  v25 = v23;
  *(_QWORD *)plOut = v23;
  v26 = v17;
  if ( !v18 )
    v26 = v55;
  v55 = v26;
  v27 = v26;
  if ( v13 )
  {
    while ( 1 )
    {
      v28 = a1[v17 - a1];
      if ( (_BYTE)v12 )
      {
        if ( SemanticsUM::Syntax::IsDoubleQuote(v28) )
        {
          if ( !SemanticsUM::Syntax::QuoteIsPartOfHebrewNumber(v31, a1, a2) )
            goto LABEL_23;
          v27 = v55;
          v24 = -246;
        }
        if ( v32 == 92 || (_WORD)v32 == 0xFF3C || v32 == 47 || (_WORD)v32 == 0xFF0F )
          goto LABEL_23;
      }
      else
      {
        if ( (unsigned __int16)(v28 - 33) > 6u && (unsigned __int16)(v28 - 42) > 0xFEDDu && (unsigned __int16)v28 < v24
          || (_WORD)v28 == 0xFF5C )
        {
          goto LABEL_23;
        }
        if ( (unsigned __int16)v28 <= 0x2260u )
        {
          if ( (_WORD)v28 != 8800 )
          {
            v50 = v25;
            v25 = &_ImageBase;
            switch ( a1[v17 - a1] )
            {
              case '"':
              case '(':
              case ')':
              case '/':
              case ':':
              case '<':
              case '=':
              case '>':
              case '\\':
              case '|':
              case '~':
                break;
              default:
                v25 = v50;
                goto LABEL_31;
            }
          }
LABEL_23:
          if ( !StructuredQuery1::IsPathSeparator((StructuredQuery1 *)*v17, (wchar_t)v25) )
            goto LABEL_44;
          ++v17;
          --v13;
          v18 = 1;
          v30 = SemanticsUM::Syntax::IsReverseSolidus(v29);
          if ( v30 + 1 > v20 )
            v20 = v30 + 1;
          goto LABEL_14;
        }
        if ( (unsigned __int16)v28 > 0xFF02u )
        {
          v51 = v25;
          v25 = &_ImageBase;
          switch ( a1[v17 - a1] )
          {
            case 0xFF08u:
            case 0xFF09u:
            case 0xFF0Fu:
            case 0xFF1Au:
            case 0xFF1Cu:
            case 0xFF1Du:
            case 0xFF1Eu:
            case 0xFF3Cu:
            case 0xFF5Eu:
              goto LABEL_23;
            default:
              v25 = v51;
              goto LABEL_31;
          }
        }
        if ( (_WORD)v28 == 0xFF02 || (unsigned int)(v28 - 8804) < 2 )
          goto LABEL_23;
      }
LABEL_31:
      if ( v20 < 1 )
        v20 = 1;
      v33 = *v17;
      if ( (*v17 == 46 || v33 == 0xFF0E) && v27 )
      {
        *(_QWORD *)plOut = v17 + 1;
      }
      else if ( v33 == 63 || v33 == 0xFF1F || (v33 == v24 || v33 == 42) && v13 > 1 )
      {
        v20 = 2;
      }
      else if ( v33 == 64 || v33 == 0xFF20 )
      {
        v53 = 1;
      }
      ++v17;
      if ( !--v13 )
        goto LABEL_44;
    }
  }
  *(_QWORD *)plOut = v25;
LABEL_44:
  v34 = v17;
  if ( v12 && v13 )
  {
    if ( SemanticsUM::Syntax::IsDoubleQuote(a1[v17 - a1])
      && !SemanticsUM::Syntax::QuoteIsPartOfHebrewNumber(v47, a1, a2) )
    {
      ++v17;
      if ( v13 == 1 || !SemanticsUM::Syntax::IsStar(*v17) )
      {
        v12 = 2;
      }
      else
      {
        ++v17;
        v12 = 3;
      }
      goto LABEL_45;
    }
    return 0;
  }
  else
  {
LABEL_45:
    if ( !v20 )
      return 0;
    v36 = *(struct tagPROPVARIANT **)plOut;
    if ( *(_QWORD *)plOut && !v53 )
      v20 = 2;
    v37 = v57;
    v38 = v34 - v57;
    if ( v38 <= 0x7FFFFFFE )
    {
      v39 = v57;
      v40 = strIn;
      v41 = 30;
      do
      {
        if ( !v38 )
          break;
        if ( !*v39 )
          break;
        *v40++ = *v39++;
        --v38;
        --v41;
      }
      while ( v41 );
      v42 = v40 - 1;
      if ( v41 )
        v42 = v40;
      *v42 = 0;
      if ( v41 )
      {
        plOut[0] = 0;
        if ( VarI4FromStr(strIn, lcid, 0, plOut) >= 0 )
          v20 = 1;
      }
    }
    v43 = v55;
    if ( !v55 )
      v43 = v34;
    *v58 = v17 - a1;
    *v59 = v37;
    *v60 = v43;
    v44 = (_BYTE *)v65;
    *v61 = v36;
    *v62 = v34;
    *v63 = v12;
    if ( v20 != 2 )
      v19 = 0;
    *v64 = v19;
    *v44 = v52;
    return 1;
  }
}

```

## disassembly

```asm
0x180023010  mov     [rsp+arg_8], rbx
0x180023015  push    rbp
0x180023016  push    rsi
0x180023017  push    rdi
0x180023018  push    r12
0x18002301a  push    r13
0x18002301c  push    r14
0x18002301e  push    r15
0x180023020  sub     rsp, 0E0h
0x180023027  mov     rax, cs:__security_cookie
0x18002302e  xor     rax, rsp
0x180023031  mov     [rsp+118h+var_40], rax
0x180023039  mov     rax, [rsp+118h+arg_20]
0x180023041  mov     esi, edx
0x180023043  mov     [rsp+118h+var_C0], rax
0x180023048  xor     r15d, r15d
0x18002304b  mov     rax, [rsp+118h+arg_28]
0x180023053  sub     esi, r9d
0x180023056  mov     [rsp+118h+var_B8], rax
0x18002305b  mov     r11d, 1
0x180023061  mov     rax, [rsp+118h+arg_30]
0x180023069  mov     r13, rdx
0x18002306c  mov     [rsp+118h+var_B0], rax
0x180023071  mov     r14, rcx
0x180023074  mov     rax, [rsp+118h+arg_38]
0x18002307c  mov     [rsp+118h+var_A8], rax
0x180023081  mov     rax, [rsp+118h+arg_40]
0x180023089  mov     [rsp+118h+var_A0], rax
0x18002308e  mov     rax, [rsp+118h+arg_48]
0x180023096  mov     [rsp+118h+var_98], rax
0x18002309e  mov     rax, [rsp+118h+arg_50]
0x1800230a6  mov     r10d, r9d
0x1800230a9  mov     [rsp+118h+var_90], rax
0x1800230b1  mov     rax, [rsp+118h+arg_58]
0x1800230b9  mov     [rsp+118h+var_88], rax
0x1800230c1  mov     [rsp+118h+lcid], r8d
0x1800230c6  lea     rdi, [rcx+r10*2]
0x1800230ca  cmp     esi, r11d
0x1800230cd  jnb     loc_1800234CE
0x1800230d3  xor     eax, eax
0x1800230d5  mov     [rsp+118h+var_E7], 0
0x1800230da  xor     bl, bl
0x1800230dc  mov     [rsp+118h+var_C8], rdi
0x1800230e1  mov     [rsp+118h+var_D8], rax
0x1800230e6  mov     r12d, 2
0x1800230ec  mov     qword ptr [rsp+118h+plOut], rax
0x1800230f1  cmp     esi, 8
0x1800230f4  jb      short loc_180023132
0x1800230f6  lea     rax, aUnc; "\\\\?\\UNC\\"
0x1800230fd  mov     [rsp+118h+cchCount2], 0FFFFFFFFh; cchCount2
0x180023105  mov     r9d, 8; cchCount1
0x18002310b  mov     [rsp+118h+lpString2], rax; lpString2
0x180023110  mov     r8, rdi; lpString1
0x180023113  mov     edx, r11d; dwCmpFlags
0x180023116  mov     ecx, 7Fh; Locale
0x18002311b  call    cs:__imp_CompareStringW
0x180023121  cmp     eax, r12d
0x180023124  jz      loc_180023504
0x18002312a  mov     r11d, 1
0x180023130  jmp     short loc_180023137
0x180023132  cmp     esi, 4
0x180023135  jb      short loc_180023171
0x180023137  lea     rax, asc_18009A980; "\\\\?\\"
0x18002313e  mov     [rsp+118h+cchCount2], 0FFFFFFFFh; cchCount2
0x180023146  mov     r9d, 4; cchCount1
0x18002314c  mov     [rsp+118h+lpString2], rax; lpString2
0x180023151  mov     r8, rdi; lpString1
0x180023154  mov     edx, r11d; dwCmpFlags
0x180023157  mov     ecx, 7Fh; Locale
0x18002315c  call    cs:__imp_CompareStringW
0x180023162  cmp     eax, r12d
0x180023165  jz      loc_180023672
0x18002316b  mov     r11d, 1
0x180023171  xor     ebp, ebp
0x180023173  mov     [rsp+118h+var_E8], bl
0x180023177  cmp     esi, r12d
0x18002317a  jb      loc_18002320E
0x180023180  lea     rax, asc_18009A9A4; "\\\\"
0x180023187  mov     [rsp+118h+cchCount2], 0FFFFFFFFh; cchCount2
0x18002318f  mov     r9d, r12d; cchCount1
0x180023192  mov     [rsp+118h+lpString2], rax; lpString2
0x180023197  mov     r8, rdi; lpString1
0x18002319a  mov     edx, r11d; dwCmpFlags
0x18002319d  mov     ecx, 7Fh; Locale
0x1800231a2  call    cs:__imp_CompareStringW
0x1800231a8  cmp     eax, r12d
0x1800231ab  jz      loc_18002353C
0x1800231b1  movzx   ecx, word ptr [rdi]
0x1800231b4  mov     rdx, 3FFFFFF03FFFFFFh
0x1800231be  lea     eax, [rcx-41h]
0x1800231c1  cmp     ax, 39h ; '9'
0x1800231c5  ja      loc_180023518
0x1800231cb  movzx   eax, ax
0x1800231ce  bt      rdx, rax
0x1800231d2  jnb     loc_180023518
0x1800231d8  mov     ebx, 1
0x1800231dd  mov     [rsp+118h+cchCount2], 0FFFFFFFFh; cchCount2
0x1800231e5  lea     rax, asc_18009A9AC; ":"
0x1800231ec  mov     r9d, ebx; cchCount1
0x1800231ef  mov     edx, ebx; dwCmpFlags
0x1800231f1  mov     [rsp+118h+lpString2], rax; lpString2
0x1800231f6  lea     r8, [rdi+2]; lpString1
0x1800231fa  mov     ecx, 7Fh; Locale
0x1800231ff  call    cs:__imp_CompareStringW
0x180023205  cmp     eax, r12d
0x180023208  jz      loc_18002362E
0x18002320e  mov     bl, 1
0x180023210  xor     eax, eax
0x180023212  mov     r10d, 0FF0Ah
0x180023218  test    bl, bl
0x18002321a  mov     ecx, 0FEDDh
0x18002321f  cmovz   rax, qword ptr [rsp+118h+plOut]
0x180023225  mov     rdx, rax; wchar_t
0x180023228  mov     qword ptr [rsp+118h+plOut], rax
0x18002322d  mov     rax, rdi
0x180023230  cmovz   rax, [rsp+118h+var_D8]
0x180023236  mov     [rsp+118h+var_D8], rax
0x18002323b  mov     r8, rax
0x18002323e  cmp     esi, 1
0x180023241  jb      loc_180023379
0x180023247  nop     word ptr [rax+rax+00000000h]
0x180023250  mov     r9, rdi
0x180023253  sub     r9, r14
0x180023256  sar     r9, 1
0x180023259  movzx   r11d, word ptr [r14+r9*2]
0x18002325e  test    r15b, r15b
0x180023261  jnz     short loc_1800232CA
0x180023263  lea     eax, [r11-21h]
0x180023267  cmp     ax, 6
0x18002326b  jbe     loc_1800233C5
0x180023271  lea     eax, [r11-2Ah]
0x180023275  cmp     ax, cx
0x180023278  jbe     loc_1800233C5
0x18002327e  cmp     r11w, r10w
0x180023282  jnb     loc_1800233C5
0x180023288  cmp     esi, 1; jumptable 0000000180088C90 cases 34,40,41,47,58,60-62,92,124,126
0x18002328b  jb      loc_18002337E
0x180023291  movzx   ecx, word ptr [rdi]; this
0x180023294  call    ?IsPathSeparator@StructuredQuery1@@YA_N_W@Z; StructuredQuery1::IsPathSeparator(wchar_t)
0x180023299  test    al, al
0x18002329b  jz      loc_18002337E
0x1800232a1  add     rdi, r12
0x1800232a4  dec     esi
0x1800232a6  mov     bl, 1
0x1800232a8  call    ?IsReverseSolidus@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsReverseSolidus(wchar_t)
0x1800232ad  movzx   ecx, al
0x1800232b0  lea     eax, [rcx+1]
0x1800232b3  cmp     eax, ebp
0x1800232b5  jle     loc_180023210
0x1800232bb  xor     ebp, ebp
0x1800232bd  test    cl, cl
0x1800232bf  setnz   bpl
0x1800232c3  inc     ebp
0x1800232c5  jmp     loc_180023210
0x1800232ca  movzx   ecx, r11w; wchar_t
0x1800232ce  call    ?IsDoubleQuote@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsDoubleQuote(wchar_t)
0x1800232d3  test    al, al
0x1800232d5  jnz     loc_180023590
0x1800232db  cmp     r11d, 5Ch ; '\'
0x1800232df  jz      short loc_180023288; jumptable 0000000180088C90 cases 34,40,41,47,58,60-62,92,124,126
0x1800232e1  mov     eax, 0FF3Ch
0x1800232e6  cmp     r11w, ax
0x1800232ea  jz      short loc_180023288; jumptable 0000000180088C90 cases 34,40,41,47,58,60-62,92,124,126
0x1800232ec  cmp     r11d, 2Fh ; '/'
0x1800232f0  jz      short loc_180023288; jumptable 0000000180088C90 cases 34,40,41,47,58,60-62,92,124,126
0x1800232f2  mov     eax, 0FF0Fh
0x1800232f7  cmp     r11w, ax
0x1800232fb  jz      short loc_180023288; jumptable 0000000180088C90 cases 34,40,41,47,58,60-62,92,124,126
0x1800232fd  cmp     ebp, 1; jumptable 0000000180088C90 default case, cases 35-39,42-46,48-57,59,63-91,93-123,125
0x180023300  jl      loc_1800233BB
0x180023306  movzx   eax, word ptr [rdi]
0x180023309  cmp     ax, 2Eh ; '.'
0x18002330d  jz      loc_1800233D9
0x180023313  mov     ecx, 0FF0Eh
0x180023318  cmp     ax, cx
0x18002331b  jz      loc_1800233D9
0x180023321  cmp     ax, 3Fh ; '?'
0x180023325  jz      loc_1800235BF
0x18002332b  mov     ecx, 0FF1Fh
0x180023330  cmp     ax, cx
0x180023333  jz      loc_1800235BF
0x180023339  cmp     ax, r10w
0x18002333d  jz      loc_1800235B6
0x180023343  cmp     ax, 2Ah ; '*'
0x180023347  jz      loc_1800235B6
0x18002334d  cmp     ax, 40h ; '@'
0x180023351  jz      loc_18002369D
0x180023357  mov     ecx, 0FF20h
0x18002335c  cmp     ax, cx
0x18002335f  jz      loc_18002369D
0x180023365  add     rdi, r12
0x180023368  dec     esi
0x18002336a  cmp     esi, 1
0x18002336d  jb      short loc_18002337E
0x18002336f  mov     ecx, 0FEDDh
0x180023374  jmp     loc_180023250
0x180023379  mov     qword ptr [rsp+118h+plOut], rdx
0x18002337e  mov     rbx, rdi
0x180023381  test    r15d, r15d
0x180023384  jnz     loc_1800235C7
0x18002338a  test    ebp, ebp
0x18002338c  jnz     short loc_1800233F0
0x18002338e  xor     al, al
0x180023390  mov     rcx, [rsp+118h+var_40]
0x180023398  xor     rcx, rsp; StackCookie
0x18002339b  call    __security_check_cookie
0x1800233a0  mov     rbx, [rsp+118h+arg_8]
0x1800233a8  add     rsp, 0E0h
0x1800233af  pop     r15
0x1800233b1  pop     r14
0x1800233b3  pop     r13
0x1800233b5  pop     r12
0x1800233b7  pop     rdi
0x1800233b8  pop     rsi
0x1800233b9  pop     rbp
0x1800233ba  retn
0x1800233bb  mov     ebp, 1
0x1800233c0  jmp     loc_180023306
0x1800233c5  mov     eax, 0FF5Ch
0x1800233ca  cmp     r11w, ax
0x1800233ce  jz      loc_180023288; jumptable 0000000180088C90 cases 34,40,41,47,58,60-62,92,124,126
0x1800233d4  jmp     loc_180088C54
0x1800233d9  test    r8, r8
0x1800233dc  jz      loc_180023321
0x1800233e2  lea     rax, [rdi+2]
0x1800233e6  mov     qword ptr [rsp+118h+plOut], rax
0x1800233eb  jmp     loc_180023365
0x1800233f0  mov     rsi, qword ptr [rsp+118h+plOut]
0x1800233f5  test    rsi, rsi
0x1800233f8  jnz     loc_180023550
0x1800233fe  mov     r13, [rsp+118h+var_C8]
0x180023403  mov     rax, rbx
0x180023406  sub     rax, r13
0x180023409  sar     rax, 1
0x18002340c  cmp     rax, 7FFFFFFEh
0x180023412  ja      short loc_18002345E
0x180023414  mov     rdx, r13
0x180023417  lea     r9, [rsp+118h+strIn]
0x18002341f  mov     r8d, 1Eh
0x180023425  test    rax, rax
0x180023428  jz      short loc_180023445
0x18002342a  movzx   ecx, word ptr [rdx]
0x18002342d  test    cx, cx
0x180023430  jz      short loc_180023445
0x180023432  mov     [r9], cx
0x180023436  add     rdx, r12
0x180023439  add     r9, r12
0x18002343c  dec     rax
0x18002343f  sub     r8, 1
0x180023443  jnz     short loc_180023425
0x180023445  test    r8, r8
0x180023448  lea     rcx, [r9-2]
0x18002344c  cmovnz  rcx, r9
0x180023450  xor     eax, eax
0x180023452  mov     [rcx], ax
0x180023455  test    r8, r8
0x180023458  jnz     loc_180023563
0x18002345e  mov     rax, [rsp+118h+var_D8]
0x180023463  test    rax, rax
0x180023466  jz      loc_1800236A7
0x18002346c  mov     rcx, [rsp+118h+var_C0]
0x180023471  sub     rdi, r14
0x180023474  sar     rdi, 1
0x180023477  mov     [rcx], edi
0x180023479  mov     rcx, [rsp+118h+var_B8]
0x18002347e  mov     [rcx], r13
0x180023481  mov     rcx, [rsp+118h+var_B0]
0x180023486  mov     [rcx], rax
0x180023489  mov     rax, [rsp+118h+var_A8]
0x18002348e  mov     rcx, [rsp+118h+var_88]
0x180023496  mov     [rax], rsi
0x180023499  mov     rax, [rsp+118h+var_A0]
0x18002349e  mov     [rax], rbx
0x1800234a1  mov     rax, [rsp+118h+var_98]
0x1800234a9  mov     [rax], r15d
0x1800234ac  xor     eax, eax
0x1800234ae  cmp     ebp, r12d
0x1800234b1  cmovnz  r12d, eax
0x1800234b5  mov     rax, [rsp+118h+var_90]
0x1800234bd  mov     [rax], r12d
0x1800234c0  movzx   eax, [rsp+118h+var_E8]
0x1800234c5  mov     [rcx], al
0x1800234c7  mov     al, 1
0x1800234c9  jmp     loc_180023390
0x1800234ce  movzx   ecx, word ptr [rcx+r10*2]; wchar_t
0x1800234d3  call    ?IsDoubleQuote@Syntax@SemanticsUM@@SA_N_W@Z; SemanticsUM::Syntax::IsDoubleQuote(wchar_t)
0x1800234d8  test    al, al
0x1800234da  jz      loc_1800230D3
0x1800234e0  mov     r8d, r13d; unsigned int
0x1800234e3  mov     rdx, r14; wchar_t *
0x1800234e6  mov     rcx, r10; unsigned __int64
0x1800234e9  call    ?QuoteIsPartOfHebrewNumber@Syntax@SemanticsUM@@SA_N_KPEB_WK@Z; SemanticsUM::Syntax::QuoteIsPartOfHebrewNumber(unsigned __int64,wchar_t const *,ulong)
0x1800234ee  test    al, al
0x1800234f0  jnz     loc_1800230D3
0x1800234f6  add     rdi, 2
0x1800234fa  mov     r15d, r11d
0x1800234fd  dec     esi
0x1800234ff  jmp     loc_1800230D3
0x180023504  add     rdi, 10h
0x180023508  mov     [rsp+118h+var_E8], 1
  ... truncated ...
```
