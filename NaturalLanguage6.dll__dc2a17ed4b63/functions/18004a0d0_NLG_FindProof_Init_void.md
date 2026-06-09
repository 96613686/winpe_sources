# NLG::FindProof::Init(void)

- ea: `0x18004a0d0`
- end: `0x18004a4f1`
- name: `?Init@FindProof@NLG@@QEAAXXZ`
- size: `1057`
- prototype: `void __fastcall(NLG::FindProof *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x18004952c`

## callees

- `0x180017858`
- `0x180035640`
- `0x18003ed6c`
- `0x18004a0d0`
- `0x18009e300`

## string_xrefs

- `0x18004a1ba`: `nlsdata%04x.dll`
- `0x18004a1d4`: `nlsdata%04x.dll`
- `0x18004a208`: `msspell6.dll`
- `0x18004a2b7`: `msspell3.dll`
- `0x18004a290`: `mshyph2.dll`
- `0x18004a280`: `msthes3.dll`
- `0x18004a39d`: `%s.dll`
- `0x18004a3b8`: `%s.dll`

## pseudocode

```c
void __fastcall NLG::FindProof::Init(NLG::FindProof *this)
{
  unsigned int v1; // edx
  int i; // ecx
  wchar_t *v4; // r15
  int j; // ecx
  char *v6; // r14
  unsigned int v7; // eax
  int v8; // ecx
  int v9; // ecx
  const wchar_t *v10; // r8
  const wchar_t *v11; // rcx
  bool v12; // zf
  const wchar_t *v13; // rdx
  int v14; // ecx
  int v15; // ecx
  int v16; // ecx
  const wchar_t *v17; // r14
  unsigned int v18; // eax
  unsigned int v19; // eax
  const wchar_t *v20; // r12
  const wchar_t *v21; // rax
  unsigned int v22; // eax
  unsigned int v23; // eax
  _BYTE v24[64]; // [rsp+30h] [rbp-79h] BYREF
  unsigned __int16 pExceptionObject[32]; // [rsp+70h] [rbp-39h] BYREF
  const void *retaddr; // [rsp+108h] [rbp+5Fh]

  v1 = *((unsigned __int16 *)this + 12);
  for ( i = 0; aEn[5 * i] != 0xFFFF; ++i )
  {
    if ( (_WORD)v1 == aEn[5 * i] )
    {
      v4 = &aEn[5 * i + 1];
      goto LABEL_12;
    }
  }
  for ( j = 0; aEn[5 * j] != 0xFFFF; ++j )
  {
    if ( (v1 & 0x3FF) == aEn[5 * j] )
    {
      v4 = &aEn[5 * j + 1];
      goto LABEL_12;
    }
  }
  v4 = (wchar_t *)&byte_1800BCA00;
LABEL_12:
  if ( *v4 )
  {
    if ( (v1 & 0x3FF) != 9 || (v8 = *((_DWORD *)this + 7), v8 == 3) )
    {
      v14 = *((_DWORD *)this + 7);
      if ( v14 )
      {
        v15 = v14 - 1;
        if ( v15 )
        {
          v16 = v15 - 1;
          if ( v16 )
          {
            if ( v16 != 1 )
            {
              CNLException::CNLException((CNLException *)v24, 2147942487LL, retaddr);
              throw (CNLException *)v24;
            }
            v17 = L"gr3";
          }
          else
          {
            v17 = L"th3";
          }
        }
        else
        {
          v17 = L"hy3";
        }
      }
      else
      {
        v17 = L"sp3";
      }
      if ( StringCchPrintfW(pExceptionObject, 0x14u, L"ms%s%s", v17, v4) < 0 )
      {
        v18 = StringCchPrintfW(pExceptionObject, 0x14u, L"ms%s%s", v17, v4);
        CNLException::CNLException((CNLException *)v24, v18, retaddr);
        throw (CNLException *)v24;
      }
      if ( StringCchPrintfW((unsigned __int16 *)this + 24, 0x14u, L"%s.dll", pExceptionObject) < 0 )
      {
        v19 = StringCchPrintfW((unsigned __int16 *)this + 24, 0x14u, L"%s.dll", pExceptionObject);
        CNLException::CNLException((CNLException *)v24, v19, retaddr);
        throw (CNLException *)v24;
      }
      v6 = (char *)this + 88;
      if ( (*((_WORD *)this + 12) & 0x3FF) == 7 )
      {
        v20 = L"A";
        v21 = L"A";
        if ( !*((_BYTE *)this + 26) )
          v21 = L"P";
        if ( StringCchPrintfW((unsigned __int16 *)this + 44, 0x14u, L"%s%s.lex", pExceptionObject, v21) < 0 )
        {
          if ( !*((_BYTE *)this + 26) )
            v20 = L"P";
          v22 = StringCchPrintfW((unsigned __int16 *)this + 44, 0x14u, L"%s%s.lex", pExceptionObject, v20);
          CNLException::CNLException((CNLException *)v24, v22, retaddr);
          throw (CNLException *)v24;
        }
      }
      else if ( StringCchPrintfW((unsigned __int16 *)this + 44, 0x14u, L"%s.lex", pExceptionObject) < 0 )
      {
        v23 = StringCchPrintfW((unsigned __int16 *)this + 44, 0x14u, L"%s.lex", pExceptionObject);
        CNLException::CNLException((CNLException *)v24, v23, retaddr);
        throw (CNLException *)v24;
      }
      *((_QWORD *)this + 4) = (char *)this + 48;
      goto LABEL_53;
    }
    if ( v8 )
    {
      v9 = v8 - 1;
      if ( !v9 )
      {
        v11 = L"mshy2_en.lex";
        v13 = L"mshyph2.dll";
LABEL_29:
        *((_QWORD *)this + 4) = v13;
        *((_QWORD *)this + 5) = v11;
        return;
      }
      if ( v9 != 1 )
      {
        CNLException::CNLException((CNLException *)pExceptionObject, 2147942487LL, retaddr);
        throw (CNLException *)pExceptionObject;
      }
      v10 = L"msth3br.lex";
      v11 = L"msth3am.lex";
      v12 = (v1 & 0xFC00) == 1024;
      v13 = L"msthes3.dll";
    }
    else
    {
      v10 = L"mssp3en.lex";
      v11 = L"mssp3ena.lex";
      v12 = (v1 & 0xFC00) == 3072;
      v13 = L"msspell3.dll";
    }
    if ( !v12 )
      v11 = v10;
    goto LABEL_29;
  }
  if ( *((_DWORD *)this + 7) )
  {
    CNLException::CNLException((CNLException *)pExceptionObject, 3241213954LL, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  v6 = (char *)this + 88;
  if ( StringCchPrintfW((unsigned __int16 *)this + 44, 0x14u, L"nlsdata%04x.dll", v1) < 0 )
  {
    v7 = StringCchPrintfW((unsigned __int16 *)this + 44, 0x14u, L"nlsdata%04x.dll", *((unsigned __int16 *)this + 12));
    CNLException::CNLException((CNLException *)pExceptionObject, v7, retaddr);
    throw (CNLException *)pExceptionObject;
  }
  *((_QWORD *)this + 4) = L"msspell6.dll";
LABEL_53:
  *((_QWORD *)this + 5) = v6;
}

```

## disassembly

```asm
0x18004a0d0  push    rbp
0x18004a0d2  push    rbx
0x18004a0d3  push    rsi
0x18004a0d4  push    rdi
0x18004a0d5  push    r12
0x18004a0d7  push    r13
0x18004a0d9  push    r14
0x18004a0db  push    r15
0x18004a0dd  lea     rbp, [rsp-1Fh]
0x18004a0e2  sub     rsp, 0C8h
0x18004a0e9  mov     rax, cs:__security_cookie
0x18004a0f0  xor     rax, rsp
0x18004a0f3  mov     [rbp+57h+var_50], rax
0x18004a0f7  movzx   edx, word ptr [rcx+18h]
0x18004a0fb  lea     r10, aEn; "\tEN"
0x18004a102  xor     r13d, r13d
0x18004a105  mov     rdi, rcx
0x18004a108  mov     ecx, r13d
0x18004a10b  mov     r11d, 0FFFFh
0x18004a111  movsxd  rax, ecx
0x18004a114  lea     r8, [rax+rax*4]
0x18004a118  cmp     r11w, [r10+r8*2]
0x18004a11d  jz      short loc_18004A139
0x18004a11f  cmp     dx, [r10+r8*2]
0x18004a124  jz      short loc_18004A12A
0x18004a126  inc     ecx
0x18004a128  jmp     short loc_18004A111
0x18004a12a  lea     r15, [r10+2]
0x18004a12e  mov     ebx, 3FFh
0x18004a133  lea     r15, [r15+r8*2]
0x18004a137  jmp     short loc_18004A175
0x18004a139  movzx   r8d, dx
0x18004a13d  mov     ebx, 3FFh
0x18004a142  and     r8w, bx
0x18004a146  mov     ecx, r13d
0x18004a149  movsxd  rax, ecx
0x18004a14c  lea     r9, [rax+rax*4]
0x18004a150  cmp     r11w, [r10+r9*2]
0x18004a155  jz      short loc_18004A16E
0x18004a157  cmp     r8w, [r10+r9*2]
0x18004a15c  jz      short loc_18004A162
0x18004a15e  inc     ecx
0x18004a160  jmp     short loc_18004A149
0x18004a162  lea     r15, [r10+2]
0x18004a166  mov     ecx, ebx
0x18004a168  lea     r15, [r15+r9*2]
0x18004a16c  jmp     short loc_18004A178
0x18004a16e  lea     r15, byte_1800BCA00
0x18004a175  movzx   ecx, bx
0x18004a178  movzx   eax, dx
0x18004a17b  cmp     [r15], r13w
0x18004a17f  jnz     loc_18004A218
0x18004a185  cmp     [rdi+1Ch], r13d
0x18004a189  jz      short loc_18004A1AE
0x18004a18b  mov     r8, [rbp+5Fh]; void *
0x18004a18f  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004a193  mov     edx, 0C1310002h; int
0x18004a198  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a19d  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a1a4  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004a1a8  call    _CxxThrowException_0
0x18004a1ae  mov     r9d, edx
0x18004a1b1  lea     r14, [rdi+58h]
0x18004a1b5  mov     esi, 14h
0x18004a1ba  lea     r8, aNlsdata04xDll_0; "nlsdata%04x.dll"
0x18004a1c1  mov     edx, esi; unsigned __int64
0x18004a1c3  mov     rcx, r14; unsigned __int16 *
0x18004a1c6  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a1cb  test    eax, eax
0x18004a1cd  jns     short loc_18004A208
0x18004a1cf  movzx   r9d, word ptr [rdi+18h]
0x18004a1d4  lea     r8, aNlsdata04xDll_0; "nlsdata%04x.dll"
0x18004a1db  mov     rbx, [rbp+5Fh]
0x18004a1df  mov     edx, esi; unsigned __int64
0x18004a1e1  mov     rcx, r14; unsigned __int16 *
0x18004a1e4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a1e9  mov     edx, eax; int
0x18004a1eb  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004a1ef  mov     r8, rbx; void *
0x18004a1f2  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a1f7  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a1fe  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004a202  call    _CxxThrowException_0
0x18004a208  lea     rax, aMsspell6Dll; "msspell6.dll"
0x18004a20f  mov     [rdi+20h], rax
0x18004a213  jmp     loc_18004A4CD
0x18004a218  and     ax, cx
0x18004a21b  cmp     ax, 9
0x18004a21f  jnz     loc_18004A2D7
0x18004a225  mov     ecx, [rdi+1Ch]
0x18004a228  cmp     ecx, 3
0x18004a22b  jz      loc_18004A2D7
0x18004a231  test    ecx, ecx
0x18004a233  jz      short loc_18004A299
0x18004a235  sub     ecx, 1
0x18004a238  jz      short loc_18004A289
0x18004a23a  cmp     ecx, 1
0x18004a23d  jz      short loc_18004A262
0x18004a23f  mov     r8, [rbp+5Fh]; void *
0x18004a243  lea     rcx, [rbp+57h+pExceptionObject]; this
0x18004a247  mov     edx, 80070057h; int
0x18004a24c  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a251  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a258  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x18004a25c  call    _CxxThrowException_0
0x18004a262  mov     eax, 0FC00h
0x18004a267  lea     r8, aMsth3brLex; "msth3br.lex"
0x18004a26e  and     dx, ax
0x18004a271  lea     rcx, aMsth3amLex; "msth3am.lex"
0x18004a278  mov     eax, 400h
0x18004a27d  cmp     dx, ax
0x18004a280  lea     rdx, aMsthes3Dll; "msthes3.dll"
0x18004a287  jmp     short loc_18004A2BE
0x18004a289  lea     rcx, aMshy2EnLex; "mshy2_en.lex"
0x18004a290  lea     rdx, aMshyph2Dll; "mshyph2.dll"
0x18004a297  jmp     short loc_18004A2C2
0x18004a299  mov     eax, 0FC00h
0x18004a29e  lea     r8, aMssp3enLex; "mssp3en.lex"
0x18004a2a5  and     dx, ax
0x18004a2a8  lea     rcx, aMssp3enaLex; "mssp3ena.lex"
0x18004a2af  mov     eax, 0C00h
0x18004a2b4  cmp     dx, ax
0x18004a2b7  lea     rdx, aMsspell3Dll; "msspell3.dll"
0x18004a2be  cmovnz  rcx, r8
0x18004a2c2  mov     eax, 20h ; ' '
0x18004a2c7  mov     r8, rdi
0x18004a2ca  mov     [rax+rdi], rdx
0x18004a2ce  mov     [rdi+28h], rcx
0x18004a2d2  jmp     loc_18004A4D1
0x18004a2d7  mov     ecx, [rdi+1Ch]
0x18004a2da  test    ecx, ecx
0x18004a2dc  jz      short loc_18004A32B
0x18004a2de  sub     ecx, 1
0x18004a2e1  jz      short loc_18004A322
0x18004a2e3  sub     ecx, 1
0x18004a2e6  jz      short loc_18004A319
0x18004a2e8  cmp     ecx, 1
0x18004a2eb  jz      short loc_18004A310
0x18004a2ed  mov     r8, [rbp+5Fh]; void *
0x18004a2f1  lea     rcx, [rbp+57h+var_D0]; this
0x18004a2f5  mov     edx, 80070057h; int
0x18004a2fa  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a2ff  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a306  lea     rcx, [rbp+57h+var_D0]; pExceptionObject
0x18004a30a  call    _CxxThrowException_0
0x18004a310  lea     r14, aGr3; "gr3"
0x18004a317  jmp     short loc_18004A332
0x18004a319  lea     r14, aTh3; "th3"
0x18004a320  jmp     short loc_18004A332
0x18004a322  lea     r14, aHy3; "hy3"
0x18004a329  jmp     short loc_18004A332
0x18004a32b  lea     r14, aSp3; "sp3"
0x18004a332  mov     esi, 14h
0x18004a337  mov     [rsp+100h+var_E0], r15
0x18004a33c  mov     edx, esi; unsigned __int64
0x18004a33e  lea     r8, aMsSS; "ms%s%s"
0x18004a345  mov     r9, r14
0x18004a348  lea     rcx, [rbp+57h+pExceptionObject]; unsigned __int16 *
0x18004a34c  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a351  mov     edx, esi; unsigned __int64
0x18004a353  test    eax, eax
0x18004a355  jns     short loc_18004A392
0x18004a357  mov     rbx, [rbp+5Fh]
0x18004a35b  lea     r8, aMsSS; "ms%s%s"
0x18004a362  mov     r9, r14
0x18004a365  mov     [rsp+100h+var_E0], r15
0x18004a36a  lea     rcx, [rbp+57h+pExceptionObject]; unsigned __int16 *
0x18004a36e  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a373  mov     edx, eax; int
0x18004a375  lea     rcx, [rbp+57h+var_D0]; this
0x18004a379  mov     r8, rbx; void *
0x18004a37c  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a381  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a388  lea     rcx, [rbp+57h+var_D0]; pExceptionObject
0x18004a38c  call    _CxxThrowException_0
0x18004a392  lea     r15, [rdi+30h]
0x18004a396  mov     rcx, r15; unsigned __int16 *
0x18004a399  lea     r9, [rbp+57h+pExceptionObject]
0x18004a39d  lea     r8, aSDll; "%s.dll"
0x18004a3a4  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a3a9  lea     r9, [rbp+57h+pExceptionObject]
0x18004a3ad  mov     rdx, rsi; unsigned __int64
0x18004a3b0  test    eax, eax
0x18004a3b2  jns     short loc_18004A3E6
0x18004a3b4  mov     rbx, [rbp+5Fh]
0x18004a3b8  lea     r8, aSDll; "%s.dll"
0x18004a3bf  mov     rcx, r15; unsigned __int16 *
0x18004a3c2  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a3c7  mov     edx, eax; int
0x18004a3c9  lea     rcx, [rbp+57h+var_D0]; this
0x18004a3cd  mov     r8, rbx; void *
0x18004a3d0  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a3d5  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a3dc  lea     rcx, [rbp+57h+var_D0]; pExceptionObject
0x18004a3e0  call    _CxxThrowException_0
0x18004a3e6  movzx   eax, word ptr [rdi+18h]
0x18004a3ea  lea     r14, [rdi+58h]
0x18004a3ee  and     ax, bx
0x18004a3f1  cmp     ax, 7
0x18004a3f5  jnz     loc_18004A47D
0x18004a3fb  cmp     [rdi+1Ah], r13b
0x18004a3ff  lea     rcx, aP; "P"
0x18004a406  lea     r12, aA; "A"
0x18004a40d  mov     rax, r12
0x18004a410  lea     r8, aSSLex; "%s%s.lex"
0x18004a417  cmovz   rax, rcx
0x18004a41b  mov     rcx, r14; unsigned __int16 *
0x18004a41e  mov     [rsp+100h+var_E0], rax
0x18004a423  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a428  test    eax, eax
0x18004a42a  jns     loc_18004A4C9
0x18004a430  cmp     [rdi+1Ah], r13b
0x18004a434  lea     rax, aP; "P"
0x18004a43b  mov     rbx, [rbp+5Fh]
0x18004a43f  lea     r9, [rbp+57h+pExceptionObject]
0x18004a443  cmovz   r12, rax
0x18004a447  lea     r8, aSSLex; "%s%s.lex"
0x18004a44e  mov     rdx, rsi; unsigned __int64
0x18004a451  mov     [rsp+100h+var_E0], r12
0x18004a456  mov     rcx, r14; unsigned __int16 *
0x18004a459  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a45e  mov     edx, eax; int
0x18004a460  lea     rcx, [rbp+57h+var_D0]; this
0x18004a464  mov     r8, rbx; void *
0x18004a467  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a46c  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a473  lea     rcx, [rbp+57h+var_D0]; pExceptionObject
0x18004a477  call    _CxxThrowException_0
0x18004a47d  lea     r8, aSLex; "%s.lex"
0x18004a484  mov     rcx, r14; unsigned __int16 *
0x18004a487  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a48c  test    eax, eax
0x18004a48e  jns     short loc_18004A4C9
0x18004a490  mov     rbx, [rbp+5Fh]
0x18004a494  lea     r9, [rbp+57h+pExceptionObject]
0x18004a498  lea     r8, aSLex; "%s.lex"
0x18004a49f  mov     rdx, rsi; unsigned __int64
0x18004a4a2  mov     rcx, r14; unsigned __int16 *
0x18004a4a5  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18004a4aa  mov     edx, eax; int
0x18004a4ac  lea     rcx, [rbp+57h+var_D0]; this
0x18004a4b0  mov     r8, rbx; void *
0x18004a4b3  call    ??0CNLException@@QEAA@JPEBX@Z; CNLException::CNLException(long,void const *)
0x18004a4b8  lea     rdx, _TI2?AVCNLException@@; pThrowInfo
0x18004a4bf  lea     rcx, [rbp+57h+var_D0]; pExceptionObject
0x18004a4c3  call    _CxxThrowException_0
0x18004a4c9  mov     [rdi+20h], r15
0x18004a4cd  mov     [rdi+28h], r14
0x18004a4d1  mov     rcx, [rbp+57h+var_50]
0x18004a4d5  xor     rcx, rsp; StackCookie
0x18004a4d8  call    __security_check_cookie
0x18004a4dd  add     rsp, 0C8h
0x18004a4e4  pop     r15
0x18004a4e6  pop     r14
0x18004a4e8  pop     r13
0x18004a4ea  pop     r12
0x18004a4ec  pop     rdi
0x18004a4ed  pop     rsi
0x18004a4ee  pop     rbx
0x18004a4ef  pop     rbp
0x18004a4f0  retn
```
