# AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)

- ea: `0x18005e4f8`
- end: `0x18005eb55`
- name: `?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z`
- size: `1629`
- prototype: `__int64 __fastcall(const struct tagVARIANT *, unsigned __int8 **, unsigned int *, unsigned int *, bool *ppvData, unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x18003c020`

## callees

- `0x18000677c`
- `0x180007bec`
- `0x18005e4f8`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18005e5dd`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e774`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e787`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e5dd`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e774`
- `OLEAUT32!__imp_SysStringLen` at `0x18005e787`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005e8a9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005eb04`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005e8a9`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18005eb04`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ea7f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005eb4a`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005ea7f`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18005eb4a`

## pseudocode

```c
__int64 __fastcall AccessVariantData(
        const struct tagVARIANT *a1,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned int *a4,
        bool *ppvData,
        __int64 a6)
{
  unsigned __int8 *p_bVal; // r9
  unsigned int *v7; // r12
  const struct tagVARIANT *pvarVal; // r10
  unsigned int vt; // ecx
  HRESULT v11; // ebx
  char v12; // di
  unsigned int v13; // esi
  unsigned int v14; // ecx
  unsigned int v15; // ecx
  unsigned int v16; // ecx
  unsigned int v17; // ecx
  unsigned int v18; // ecx
  unsigned int v19; // ecx
  unsigned int v20; // ecx
  OLECHAR ***p_pbstrVal; // r14
  OLECHAR *v22; // rcx
  unsigned int v23; // ecx
  unsigned int v24; // ecx
  unsigned int v25; // ecx
  unsigned int v26; // ecx
  unsigned int v27; // ecx
  unsigned int v28; // ecx
  unsigned int v29; // ecx
  unsigned int v30; // ecx
  unsigned int v31; // ecx
  unsigned int v32; // ecx
  unsigned int v33; // ecx
  unsigned int v34; // ecx
  unsigned int v35; // ecx
  unsigned int v36; // ecx
  unsigned int v37; // ecx
  unsigned int v38; // ecx
  unsigned int v39; // ecx
  unsigned int v40; // ecx
  unsigned int v41; // ecx
  unsigned int v42; // ecx
  unsigned int v43; // ecx
  unsigned int v44; // ecx
  unsigned int v45; // ecx
  unsigned int v46; // ecx
  unsigned int v47; // ecx
  unsigned int v48; // ecx
  unsigned int v49; // ecx
  unsigned int v50; // ecx
  unsigned int v51; // ecx
  unsigned int v52; // ecx
  unsigned int v53; // ecx
  unsigned int v54; // ecx
  unsigned int v55; // ecx
  unsigned int v56; // ecx
  int v57; // esi
  SAFEARRAY **v58; // r12
  SAFEARRAY *v59; // rcx
  unsigned int v60; // r14d
  void *v61; // rax
  __int64 v62; // r13
  unsigned int v63; // edx
  bool *v64; // r9
  __int64 v65; // r8
  unsigned int v66; // ecx
  unsigned int v67; // ecx
  unsigned int v68; // ecx
  unsigned int v69; // ecx
  unsigned int v70; // ecx
  unsigned int v71; // ecx
  unsigned int v72; // ecx
  unsigned int v73; // ecx
  unsigned int v74; // ecx
  unsigned int v75; // ecx
  unsigned int v76; // ecx
  _BYTE *v77; // rax
  _BYTE *v78; // rcx
  unsigned __int64 v79; // rax
  unsigned int v80; // ecx
  unsigned int v81; // ecx
  unsigned int v82; // ecx
  unsigned int v83; // ecx
  SAFEARRAY ***p_pparray; // r14
  SAFEARRAY **p_parray; // rcx
  SAFEARRAY *v86; // rcx
  SAFEARRAY **v87; // rax
  bool *v88; // [rsp+20h] [rbp-10h]
  void *Block; // [rsp+70h] [rbp+40h] BYREF
  unsigned __int8 **v90; // [rsp+78h] [rbp+48h]
  unsigned int *v91; // [rsp+80h] [rbp+50h]
  unsigned int *v92; // [rsp+88h] [rbp+58h]

  v92 = a4;
  v91 = a3;
  v90 = a2;
  p_bVal = 0;
  v7 = a3;
  Block = 0;
  pvarVal = a1;
  if ( !a1 )
    return 2147549183LL;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a1->vt == 16396 )
  {
    pvarVal = a1->pvarVal;
    if ( !pvarVal )
      return 2147942487LL;
  }
  vt = pvarVal->vt;
  v11 = 0;
  v12 = 0;
  v13 = 0;
  if ( vt <= 0x2002 )
  {
    if ( vt != 8194 )
    {
      if ( vt <= 0xE )
      {
        if ( vt == 14 )
        {
          v13 = 16;
          p_bVal = (unsigned __int8 *)pvarVal;
        }
        else if ( pvarVal->vt )
        {
          v14 = vt - 1;
          if ( v14 )
          {
            v15 = v14 - 1;
            if ( v15 )
            {
              v16 = v15 - 1;
              if ( v16 )
              {
                v17 = v16 - 1;
                if ( v17 )
                {
                  v18 = v17 - 1;
                  if ( v18 )
                  {
                    v19 = v18 - 2;
                    if ( v19 )
                    {
                      v20 = v19 - 1;
                      if ( v20 )
                      {
                        if ( v20 != 3 )
                          return (unsigned int)-2147024809;
                        goto LABEL_88;
                      }
                      p_pbstrVal = &pvarVal->pbstrVal;
                      if ( !SysStringLen(pvarVal->bstrVal) )
                        goto LABEL_71;
                      v22 = (OLECHAR *)*p_pbstrVal;
LABEL_66:
                      v13 = 2 * SysStringLen(v22);
                      if ( v13 < 2 )
                      {
                        v13 = 0;
                        goto LABEL_71;
                      }
                      if ( v12 )
                        p_pbstrVal = (OLECHAR ***)*p_pbstrVal;
                      p_bVal = (unsigned __int8 *)*p_pbstrVal;
                      goto LABEL_72;
                    }
                  }
LABEL_84:
                  v13 = 8;
                  goto LABEL_85;
                }
              }
LABEL_82:
              v13 = 4;
              goto LABEL_85;
            }
LABEL_88:
            v13 = 2;
            goto LABEL_85;
          }
        }
LABEL_72:
        *v90 = p_bVal;
        if ( v7 )
          *v7 = v13;
        return (unsigned int)v11;
      }
      v23 = vt - 16;
      if ( v23 )
      {
        v24 = v23 - 1;
        if ( v24 )
        {
          v25 = v24 - 1;
          if ( !v25 )
            goto LABEL_88;
          v26 = v25 - 1;
          if ( !v26 )
            goto LABEL_82;
          v27 = v26 - 1;
          if ( !v27 )
            goto LABEL_84;
          v28 = v27 - 1;
          if ( !v28 )
            goto LABEL_84;
          if ( v28 - 1 <= 1 )
            goto LABEL_82;
          return (unsigned int)-2147024809;
        }
      }
LABEL_90:
      v13 = 1;
LABEL_85:
      p_bVal = &pvarVal->bVal;
      if ( v12 )
        p_bVal = *(unsigned __int8 **)p_bVal;
      goto LABEL_72;
    }
    goto LABEL_177;
  }
  if ( vt <= 0x4002 )
  {
    if ( vt != 16386 )
    {
      if ( vt > 0x2010 )
      {
        v35 = vt - 8209;
        if ( v35 )
        {
          v36 = v35 - 1;
          if ( !v36 )
            goto LABEL_177;
          v37 = v36 - 1;
          if ( v37 )
          {
            v38 = v37 - 1;
            if ( !v38 )
              goto LABEL_173;
            v39 = v38 - 1;
            if ( !v39 )
              goto LABEL_173;
            if ( v39 - 1 >= 2 )
              return (unsigned int)-2147024809;
          }
          goto LABEL_175;
        }
      }
      else if ( vt != 8208 )
      {
        v29 = vt - 8195;
        if ( v29 )
        {
          v30 = v29 - 1;
          if ( v30 )
          {
            v31 = v30 - 1;
            if ( v31 )
            {
              v32 = v31 - 2;
              if ( v32 )
              {
                v33 = v32 - 4;
                if ( v33 )
                {
                  v34 = v33 - 1;
                  if ( v34 )
                  {
                    if ( v34 != 2 )
                      return (unsigned int)-2147024809;
                    goto LABEL_103;
                  }
                  goto LABEL_105;
                }
LABEL_177:
                v57 = 2;
LABEL_178:
                p_pparray = &pvarVal->pparray;
                if ( v12 )
                  p_parray = *p_pparray;
                else
                  p_parray = &pvarVal->parray;
                v11 = SafeArrayAccessData(*p_parray, &Block);
                if ( v11 < 0 )
                  return (unsigned int)v11;
                v86 = (SAFEARRAY *)*p_pparray;
                if ( v12 )
                  v87 = *(SAFEARRAY ***)&v86->cDims;
                else
                  v87 = *p_pparray;
                v13 = *((_DWORD *)v87 + 6) * v57;
                if ( v13 )
                {
                  p_bVal = (unsigned __int8 *)Block;
                  if ( !Block )
                  {
                    v11 = -2147467261;
                    if ( v12 )
                      v86 = *(SAFEARRAY **)&v86->cDims;
                    SafeArrayUnaccessData(v86);
                    return (unsigned int)v11;
                  }
                }
                else
                {
LABEL_71:
                  p_bVal = (unsigned __int8 *)Block;
                }
                goto LABEL_72;
              }
            }
LABEL_173:
            v57 = 8;
            goto LABEL_178;
          }
        }
LABEL_175:
        v57 = 4;
        goto LABEL_178;
      }
LABEL_101:
      v57 = 1;
      goto LABEL_178;
    }
LABEL_87:
    v12 = 1;
    goto LABEL_88;
  }
  if ( vt <= 0x6002 )
  {
    if ( vt != 24578 )
    {
      if ( vt > 0x4010 )
      {
        v46 = vt - 16401;
        if ( v46 )
        {
          v47 = v46 - 1;
          if ( !v47 )
            goto LABEL_87;
          v48 = v47 - 1;
          if ( v48 )
          {
            v49 = v48 - 1;
            if ( !v49 )
              goto LABEL_83;
            v50 = v49 - 1;
            if ( !v50 )
              goto LABEL_83;
            if ( v50 - 1 > 1 )
              return (unsigned int)-2147024809;
          }
LABEL_81:
          v12 = 1;
          goto LABEL_82;
        }
      }
      else if ( vt != 16400 )
      {
        v40 = vt - 16387;
        if ( v40 )
        {
          v41 = v40 - 1;
          if ( v41 )
          {
            v42 = v41 - 1;
            if ( v42 )
            {
              v43 = v42 - 2;
              if ( v43 )
              {
                v44 = v43 - 1;
                if ( !v44 )
                {
                  p_pbstrVal = &pvarVal->pbstrVal;
                  if ( !SysStringLen(*pvarVal->pbstrVal) )
                    goto LABEL_71;
                  v12 = 1;
                  v22 = **p_pbstrVal;
                  goto LABEL_66;
                }
                v45 = v44 - 3;
                if ( v45 )
                {
                  if ( v45 == 3 )
                  {
                    p_bVal = pvarVal->pbVal;
                    v13 = 16;
                    goto LABEL_72;
                  }
                  return (unsigned int)-2147024809;
                }
                goto LABEL_87;
              }
            }
LABEL_83:
            v12 = 1;
            goto LABEL_84;
          }
        }
        goto LABEL_81;
      }
      v12 = 1;
      goto LABEL_90;
    }
LABEL_176:
    v12 = 1;
    goto LABEL_177;
  }
  if ( vt > 0x6011 )
  {
    v80 = vt - 24594;
    if ( !v80 )
      goto LABEL_176;
    v81 = v80 - 1;
    if ( v81 )
    {
      v82 = v81 - 1;
      if ( !v82 )
        goto LABEL_172;
      v83 = v82 - 1;
      if ( !v83 )
        goto LABEL_172;
      if ( v83 - 1 >= 2 )
        return (unsigned int)-2147024809;
    }
LABEL_174:
    v12 = 1;
    goto LABEL_175;
  }
  if ( vt == 24593 )
  {
LABEL_100:
    v12 = 1;
    goto LABEL_101;
  }
  v51 = vt - 24579;
  if ( !v51 )
    goto LABEL_174;
  v52 = v51 - 1;
  if ( !v52 )
    goto LABEL_174;
  v53 = v52 - 1;
  if ( !v53 || (v54 = v53 - 2) == 0 )
  {
LABEL_172:
    v12 = 1;
    goto LABEL_173;
  }
  v55 = v54 - 5;
  if ( v55 )
  {
    v56 = v55 - 2;
    if ( !v56 )
    {
      v12 = 1;
LABEL_103:
      v57 = 16;
      goto LABEL_178;
    }
    if ( v56 != 2 )
      return (unsigned int)-2147024809;
    goto LABEL_100;
  }
  v12 = 1;
LABEL_105:
  ppvData = 0;
  v58 = &pvarVal->parray;
  if ( v12 )
    v59 = *v58;
  else
    v59 = (SAFEARRAY *)&pvarVal->decVal.8;
  v11 = SafeArrayAccessData(*(SAFEARRAY **)&v59->cDims, (void **)&ppvData);
  if ( v11 < 0 )
    return (unsigned int)v11;
  v60 = 0;
  if ( v12 )
    v61 = *v58;
  else
    v61 = v58;
  v62 = 0;
  v63 = *(_DWORD *)(*(_QWORD *)v61 + 24LL);
  LODWORD(v92) = v63;
  while ( 1 )
  {
    if ( (unsigned int)v62 >= v63 )
    {
      v13 = v63 * v60;
      goto LABEL_164;
    }
    v64 = ppvData;
    v65 = 3 * v62;
    v88 = ppvData;
    a6 = 3 * v62;
    v66 = *(unsigned __int16 *)&ppvData[24 * v62];
    if ( v66 > 0x11 )
    {
      v73 = v66 - 18;
      if ( !v73 )
        goto LABEL_140;
      v74 = v73 - 1;
      if ( v74 )
      {
        v75 = v74 - 1;
        if ( !v75 || (v76 = v75 - 1) == 0 )
        {
LABEL_137:
          if ( (_DWORD)v62 && v60 != 8 )
            goto LABEL_158;
          v60 = 8;
          goto LABEL_143;
        }
        if ( v76 - 1 > 1 )
          goto LABEL_158;
      }
LABEL_134:
      if ( (_DWORD)v62 && v60 != 4 )
      {
LABEL_158:
        v11 = -2147024809;
        goto LABEL_160;
      }
      v60 = 4;
      goto LABEL_143;
    }
    if ( v66 == 17 )
      goto LABEL_123;
    v67 = v66 - 2;
    if ( !v67 )
    {
LABEL_140:
      if ( (_DWORD)v62 && v60 != 2 )
        goto LABEL_158;
      v60 = 2;
      goto LABEL_143;
    }
    v68 = v67 - 1;
    if ( !v68 )
      goto LABEL_134;
    v69 = v68 - 2;
    if ( !v69 )
      goto LABEL_137;
    v70 = v69 - 2;
    if ( !v70 )
      goto LABEL_137;
    v71 = v70 - 4;
    if ( !v71 )
      goto LABEL_140;
    v72 = v71 - 3;
    if ( v72 )
    {
      if ( v72 != 2 )
        goto LABEL_158;
LABEL_123:
      if ( (_DWORD)v62 && v60 != 1 )
        goto LABEL_158;
      v60 = 1;
      goto LABEL_143;
    }
    if ( (_DWORD)v62 && v60 != 16 )
      goto LABEL_158;
    v60 = 16;
LABEL_143:
    if ( (_DWORD)v62 )
    {
      v78 = Block;
    }
    else
    {
      v77 = operator new[](v60 * v63);
      v65 = a6;
      v78 = v77;
      v64 = v88;
      Block = v77;
    }
    v79 = (unsigned int)v62 * (unsigned __int64)v60;
    if ( v79 > 0xFFFFFFFF )
      break;
    if ( v60 == 1 )
    {
      v62 = (unsigned int)(v62 + 1);
      v78[(unsigned int)v79] = v64[8 * v65 + 8];
    }
    else
    {
      switch ( v60 )
      {
        case 2u:
          *(_WORD *)&v78[(unsigned int)v79] = *(_WORD *)&v64[8 * v65 + 8];
          break;
        case 0x10u:
          *(_OWORD *)&v78[(unsigned int)v79] = *(_OWORD *)&v64[8 * v65];
          break;
        case 8u:
          *(_QWORD *)&v78[(unsigned int)v79] = *(_QWORD *)&v64[8 * v65 + 8];
          break;
        default:
          *(_DWORD *)&v78[(unsigned int)v79] = *(_DWORD *)&v64[8 * v65 + 8];
          break;
      }
      v62 = (unsigned int)(v62 + 1);
    }
    v63 = (unsigned int)v92;
  }
  v11 = -2147418113;
LABEL_160:
  if ( v12 )
    v58 = (SAFEARRAY **)*v58;
  SafeArrayUnaccessData(*v58);
  operator delete(Block);
LABEL_164:
  if ( v11 >= 0 )
  {
    v7 = v91;
    goto LABEL_71;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18005e4f8  mov     [rsp-38h+arg_18], r9
0x18005e4fd  mov     [rsp-38h+arg_10], r8
0x18005e502  mov     [rsp-38h+arg_8], rdx
0x18005e507  push    rbp
0x18005e508  push    rbx
0x18005e509  push    rsi
0x18005e50a  push    rdi
0x18005e50b  push    r12
0x18005e50d  push    r13
0x18005e50f  push    r14
0x18005e511  mov     rbp, rsp
0x18005e514  sub     rsp, 30h
0x18005e518  xor     r9d, r9d
0x18005e51b  mov     r12, r8
0x18005e51e  mov     [rbp+Block], r9
0x18005e522  mov     r10, rcx
0x18005e525  test    rcx, rcx
0x18005e528  jnz     short loc_18005E534
0x18005e52a  mov     eax, 8000FFFFh
0x18005e52f  jmp     loc_18005E7BB
0x18005e534  mov     [rdx], r9
0x18005e537  test    r8, r8
0x18005e53a  jz      short loc_18005E53F
0x18005e53c  mov     [r8], r9d
0x18005e53f  mov     eax, 400Ch
0x18005e544  cmp     [rcx], ax
0x18005e547  jnz     short loc_18005E55C
0x18005e549  mov     r10, [rcx+8]
0x18005e54d  test    r10, r10
0x18005e550  jnz     short loc_18005E55C
0x18005e552  mov     eax, 80070057h
0x18005e557  jmp     loc_18005E7BB
0x18005e55c  movzx   ecx, word ptr [r10]
0x18005e560  xor     ebx, ebx
0x18005e562  xor     dil, dil
0x18005e565  xor     esi, esi
0x18005e567  mov     eax, 2002h
0x18005e56c  lea     r13d, [rbx+2]
0x18005e570  cmp     ecx, eax
0x18005e572  ja      loc_18005E64D
0x18005e578  jz      loc_18005EAE9
0x18005e57e  cmp     ecx, 0Eh
0x18005e581  ja      short loc_18005E600
0x18005e583  jz      short loc_18005E5F3
0x18005e585  test    ecx, ecx
0x18005e587  jz      loc_18005E7A9
0x18005e58d  sub     ecx, 1
0x18005e590  jz      loc_18005E7A9
0x18005e596  sub     ecx, 1
0x18005e599  jz      loc_18005E817
0x18005e59f  sub     ecx, 1
0x18005e5a2  jz      loc_18005E7F7
0x18005e5a8  sub     ecx, 1
0x18005e5ab  jz      loc_18005E7F7
0x18005e5b1  sub     ecx, 1
0x18005e5b4  jz      loc_18005E801
0x18005e5ba  sub     ecx, r13d
0x18005e5bd  jz      loc_18005E801
0x18005e5c3  sub     ecx, 1
0x18005e5c6  jz      short loc_18005E5D6
0x18005e5c8  cmp     ecx, 3
0x18005e5cb  jz      loc_18005E817
0x18005e5d1  jmp     loc_18005EAC8
0x18005e5d6  lea     r14, [r10+8]
0x18005e5da  mov     rcx, [r14]; pbstr
0x18005e5dd  call    cs:__imp_SysStringLen
0x18005e5e3  test    eax, eax
0x18005e5e5  jz      loc_18005E7A5
0x18005e5eb  mov     rcx, [r14]
0x18005e5ee  jmp     loc_18005E787
0x18005e5f3  mov     esi, 10h
0x18005e5f8  mov     r9, r10
0x18005e5fb  jmp     loc_18005E7A9
0x18005e600  sub     ecx, 10h
0x18005e603  jz      loc_18005E81F
0x18005e609  sub     ecx, 1
0x18005e60c  jz      loc_18005E81F
0x18005e612  sub     ecx, 1
0x18005e615  jz      loc_18005E817
0x18005e61b  sub     ecx, 1
0x18005e61e  jz      loc_18005E7F7
0x18005e624  sub     ecx, 1
0x18005e627  jz      loc_18005E801
0x18005e62d  sub     ecx, 1
0x18005e630  jz      loc_18005E801
0x18005e636  sub     ecx, 1
0x18005e639  jz      loc_18005E7F7
0x18005e63f  cmp     ecx, 1
0x18005e642  jnz     loc_18005EAC8
0x18005e648  jmp     loc_18005E7F7
0x18005e64d  mov     eax, 4002h
0x18005e652  cmp     ecx, eax
0x18005e654  ja      loc_18005E6FD
0x18005e65a  jz      loc_18005E814
0x18005e660  mov     eax, 2010h
0x18005e665  cmp     ecx, eax
0x18005e667  ja      short loc_18005E6B6
0x18005e669  jz      loc_18005E872
0x18005e66f  sub     ecx, 2003h
0x18005e675  jz      loc_18005EADF
0x18005e67b  sub     ecx, 1
0x18005e67e  jz      loc_18005EADF
0x18005e684  sub     ecx, 1
0x18005e687  jz      loc_18005EAD5
0x18005e68d  sub     ecx, r13d
0x18005e690  jz      loc_18005EAD5
0x18005e696  sub     ecx, 4
0x18005e699  jz      loc_18005EAE9
0x18005e69f  sub     ecx, 1
0x18005e6a2  jz      loc_18005E88C
0x18005e6a8  cmp     ecx, r13d
0x18005e6ab  jz      loc_18005E87F
0x18005e6b1  jmp     loc_18005EAC8
0x18005e6b6  sub     ecx, 2011h
0x18005e6bc  jz      loc_18005E872
0x18005e6c2  sub     ecx, 1
0x18005e6c5  jz      loc_18005EAE9
0x18005e6cb  sub     ecx, 1
0x18005e6ce  jz      loc_18005EADF
0x18005e6d4  sub     ecx, 1
0x18005e6d7  jz      loc_18005EAD5
0x18005e6dd  sub     ecx, 1
0x18005e6e0  jz      loc_18005EAD5
0x18005e6e6  sub     ecx, 1
0x18005e6e9  jz      loc_18005EADF
0x18005e6ef  cmp     ecx, 1
0x18005e6f2  jz      loc_18005EADF
0x18005e6f8  jmp     loc_18005EAC8
0x18005e6fd  mov     eax, 6002h
0x18005e702  cmp     ecx, eax
0x18005e704  ja      loc_18005E826
0x18005e70a  jz      loc_18005EAE6
0x18005e710  mov     eax, 4010h
0x18005e715  cmp     ecx, eax
0x18005e717  ja      loc_18005E7CA
0x18005e71d  jz      loc_18005E81C
0x18005e723  sub     ecx, 4003h
0x18005e729  jz      loc_18005E7F4
0x18005e72f  sub     ecx, 1
0x18005e732  jz      loc_18005E7F4
0x18005e738  sub     ecx, 1
0x18005e73b  jz      loc_18005E7FE
0x18005e741  sub     ecx, r13d
0x18005e744  jz      loc_18005E7FE
0x18005e74a  sub     ecx, 1
0x18005e74d  jz      short loc_18005E76A
0x18005e74f  sub     ecx, 3
0x18005e752  jz      loc_18005E814
0x18005e758  cmp     ecx, 3
0x18005e75b  jnz     loc_18005EAC8
0x18005e761  mov     r9, [r10+8]
0x18005e765  lea     esi, [rcx+0Dh]
0x18005e768  jmp     short loc_18005E7A9
0x18005e76a  lea     r14, [r10+8]
0x18005e76e  mov     rcx, [r14]
0x18005e771  mov     rcx, [rcx]; pbstr
0x18005e774  call    cs:__imp_SysStringLen
0x18005e77a  test    eax, eax
0x18005e77c  jz      short loc_18005E7A5
0x18005e77e  mov     rax, [r14]
0x18005e781  mov     dil, 1
0x18005e784  mov     rcx, [rax]; pbstr
0x18005e787  call    cs:__imp_SysStringLen
0x18005e78d  mov     esi, eax
0x18005e78f  add     esi, esi
0x18005e791  cmp     esi, r13d
0x18005e794  jb      short loc_18005E7A3
0x18005e796  test    dil, dil
0x18005e799  jz      short loc_18005E79E
0x18005e79b  mov     r14, [r14]
0x18005e79e  mov     r9, [r14]
0x18005e7a1  jmp     short loc_18005E7A9
0x18005e7a3  xor     esi, esi
0x18005e7a5  mov     r9, [rbp+Block]
0x18005e7a9  mov     rax, [rbp+arg_8]
0x18005e7ad  mov     [rax], r9
0x18005e7b0  test    r12, r12
0x18005e7b3  jz      short loc_18005E7B9
0x18005e7b5  mov     [r12], esi
0x18005e7b9  mov     eax, ebx
0x18005e7bb  add     rsp, 30h
0x18005e7bf  pop     r14
0x18005e7c1  pop     r13
0x18005e7c3  pop     r12
0x18005e7c5  pop     rdi
0x18005e7c6  pop     rsi
0x18005e7c7  pop     rbx
0x18005e7c8  pop     rbp
0x18005e7c9  retn
0x18005e7ca  sub     ecx, 4011h
0x18005e7d0  jz      short loc_18005E81C
0x18005e7d2  sub     ecx, 1
0x18005e7d5  jz      short loc_18005E814
0x18005e7d7  sub     ecx, 1
0x18005e7da  jz      short loc_18005E7F4
0x18005e7dc  sub     ecx, 1
0x18005e7df  jz      short loc_18005E7FE
0x18005e7e1  sub     ecx, 1
0x18005e7e4  jz      short loc_18005E7FE
0x18005e7e6  sub     ecx, 1
0x18005e7e9  jz      short loc_18005E7F4
0x18005e7eb  cmp     ecx, 1
0x18005e7ee  jnz     loc_18005EAC8
0x18005e7f4  mov     dil, 1
0x18005e7f7  mov     esi, 4
0x18005e7fc  jmp     short loc_18005E806
0x18005e7fe  mov     dil, 1
0x18005e801  mov     esi, 8
0x18005e806  lea     r9, [r10+8]
0x18005e80a  test    dil, dil
0x18005e80d  jz      short loc_18005E7A9
0x18005e80f  mov     r9, [r9]
0x18005e812  jmp     short loc_18005E7A9
0x18005e814  mov     dil, 1
0x18005e817  mov     esi, r13d
0x18005e81a  jmp     short loc_18005E806
0x18005e81c  mov     dil, 1
0x18005e81f  mov     esi, 1
0x18005e824  jmp     short loc_18005E806
0x18005e826  mov     eax, 6011h
0x18005e82b  cmp     ecx, eax
0x18005e82d  ja      loc_18005EAA7
0x18005e833  jz      short loc_18005E86F
0x18005e835  sub     ecx, 6003h
0x18005e83b  jz      loc_18005EADC
0x18005e841  sub     ecx, 1
0x18005e844  jz      loc_18005EADC
0x18005e84a  sub     ecx, 1
0x18005e84d  jz      loc_18005EAD2
0x18005e853  sub     ecx, r13d
0x18005e856  jz      loc_18005EAD2
0x18005e85c  sub     ecx, 5
0x18005e85f  jz      short loc_18005E889
0x18005e861  sub     ecx, r13d
0x18005e864  jz      short loc_18005E87C
0x18005e866  cmp     ecx, r13d
0x18005e869  jnz     loc_18005EAC8
0x18005e86f  mov     dil, 1
0x18005e872  mov     esi, 1
0x18005e877  jmp     loc_18005EAEC
0x18005e87c  mov     dil, 1
0x18005e87f  mov     esi, 10h
0x18005e884  jmp     loc_18005EAEC
0x18005e889  mov     dil, 1
0x18005e88c  mov     [rbp+ppvData], rbx
0x18005e890  lea     r12, [r10+8]
0x18005e894  test    dil, dil
0x18005e897  jz      short loc_18005E89F
0x18005e899  mov     rcx, [r12]
0x18005e89d  jmp     short loc_18005E8A2
0x18005e89f  mov     rcx, r12
0x18005e8a2  mov     rcx, [rcx]; psa
0x18005e8a5  lea     rdx, [rbp+ppvData]; ppvData
0x18005e8a9  call    cs:__imp_SafeArrayAccessData
0x18005e8af  mov     ebx, eax
0x18005e8b1  test    eax, eax
0x18005e8b3  js      loc_18005E7B9
0x18005e8b9  xor     r14d, r14d
0x18005e8bc  test    dil, dil
0x18005e8bf  jz      short loc_18005E8C7
0x18005e8c1  mov     rax, [r12]
0x18005e8c5  jmp     short loc_18005E8CA
0x18005e8c7  mov     rax, r12
0x18005e8ca  mov     rax, [rax]
0x18005e8cd  xor     r13d, r13d
0x18005e8d0  mov     edx, [rax+18h]
0x18005e8d3  mov     dword ptr [rbp+arg_18], edx
0x18005e8d6  cmp     r13d, edx
0x18005e8d9  jnb     loc_18005EA90
0x18005e8df  mov     r9, [rbp+ppvData]
0x18005e8e3  lea     r8, ds:0[r13*2]
0x18005e8eb  add     r8, r13
0x18005e8ee  mov     [rbp+var_10], r9
0x18005e8f2  mov     [rbp+arg_28], r8
0x18005e8f6  movzx   ecx, word ptr [r9+r8*8]
0x18005e8fb  cmp     ecx, 11h
0x18005e8fe  ja      short loc_18005E963
0x18005e900  jz      short loc_18005E935
0x18005e902  sub     ecx, 2
0x18005e905  jz      loc_18005E9B3
0x18005e90b  sub     ecx, 1
0x18005e90e  jz      short loc_18005E985
0x18005e910  sub     ecx, 2
0x18005e913  jz      loc_18005E99C
0x18005e919  sub     ecx, 2
0x18005e91c  jz      short loc_18005E99C
0x18005e91e  sub     ecx, 4
0x18005e921  jz      loc_18005E9B3
0x18005e927  sub     ecx, 3
0x18005e92a  jz      short loc_18005E94C
0x18005e92c  cmp     ecx, 2
0x18005e92f  jnz     loc_18005EA66
0x18005e935  test    r13d, r13d
0x18005e938  jz      short loc_18005E944
0x18005e93a  cmp     r14d, 1
0x18005e93e  jnz     loc_18005EA66
0x18005e944  mov     r14d, 1
0x18005e94a  jmp     short loc_18005E9C8
0x18005e94c  test    r13d, r13d
0x18005e94f  jz      short loc_18005E95B
  ... truncated ...
```
