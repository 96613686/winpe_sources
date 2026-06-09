# AccessVariantData(tagVARIANT const *,uchar * *,ulong *,ulong *,bool *,ushort *)

- ea: `0x18000a730`
- end: `0x18000ae5a`
- name: `?AccessVariantData@@YAJPEBUtagVARIANT@@PEAPEAEPEAK2PEA_NPEAG@Z`
- size: `1834`
- prototype: `__int64 __fastcall(const struct tagVARIANT *, unsigned __int8 **, unsigned int *, unsigned int *, bool *, unsigned __int16 *)`
- caller_count: `17`
- callee_count: `3`
- tags: ``

## callers

- `0x18000a300`
- `0x180033880`
- `0x180038f18`
- `0x1800a59f0`
- `0x1800a7ed0`
- `0x1800b9920`
- `0x1800bf2e0`
- `0x1800c0b30`
- `0x1800ccc04`
- `0x1800cecf0`
- `0x1800d0cd0`
- `0x1800d0f40`
- `0x1800d65f0`
- `0x1800d7090`
- `0x1800dfb30`
- `0x1800efe58`
- `0x1800f42d4`

## callees

- `0x180002740`
- `0x18000a730`
- `0x180010350`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x18000a95c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a978`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a994`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a95c`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a978`
- `OLEAUT32!__imp_SysStringLen` at `0x18000a994`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000aa2f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000aaa7`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000aa2f`
- `OLEAUT32!__imp_SafeArrayAccessData` at `0x18000aaa7`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000aa78`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000aca0`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000aa78`
- `OLEAUT32!__imp_SafeArrayUnaccessData` at `0x18000aca0`

## pseudocode

```c
__int64 __fastcall AccessVariantData(
        struct tagVARIANT *pvarVal,
        unsigned __int8 **a2,
        unsigned int *a3,
        unsigned int *a4,
        bool *a5,
        unsigned __int16 *a6)
{
  unsigned __int8 *p_bVal; // r10
  unsigned int vt; // eax
  HRESULT v12; // esi
  unsigned __int16 v13; // bx
  unsigned int v14; // edi
  unsigned int v15; // ebp
  char v16; // r13
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *p_llVal; // rbx
  SAFEARRAY **p_parray; // rcx
  BSTR *pbstrVal; // rcx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v20; // rbp
  BSTR *llVal; // rcx
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v22; // rdi
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v23; // rcx
  SAFEARRAY *v24; // rcx
  LONGLONG v25; // rax
  SAFEARRAY *v26; // rcx
  unsigned int v27; // r8d
  __int64 v28; // r13
  _BYTE *v29; // r10
  __int64 v30; // r9
  _BYTE *v31; // rcx
  unsigned __int64 v32; // rax
  SAFEARRAY **v33; // rax
  unsigned int v34; // [rsp+20h] [rbp-58h]
  void *ppvData; // [rsp+28h] [rbp-50h] BYREF
  void *v36; // [rsp+30h] [rbp-48h] BYREF
  SAFEARRAY ***v37; // [rsp+38h] [rbp-40h]
  __int64 v38; // [rsp+40h] [rbp-38h]
  _BYTE *v39; // [rsp+48h] [rbp-30h]
  union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *v40; // [rsp+80h] [rbp+8h]
  char v41; // [rsp+80h] [rbp+8h]

  ppvData = 0;
  p_bVal = 0;
  if ( !pvarVal )
    return 2147549183LL;
  *a2 = 0;
  if ( a3 )
    *a3 = 0;
  if ( a4 )
    *a4 = 0;
  if ( a5 )
    *a5 = 0;
  if ( pvarVal->vt == 16396 )
  {
    pvarVal = pvarVal->pvarVal;
    if ( !pvarVal )
      return 2147942487LL;
  }
  vt = pvarVal->vt;
  v12 = 0;
  v13 = vt & 0xBFFF;
  v14 = 0;
  v15 = 0;
  if ( !pvarVal->vt )
    goto LABEL_19;
  v16 = 0;
  if ( vt <= 0x2002 )
  {
    if ( vt != 8194 )
    {
      switch ( pvarVal->vt )
      {
        case 1u:
          goto LABEL_19;
        case 2u:
        case 0xBu:
        case 0x12u:
          v14 = 2;
          break;
        case 3u:
        case 4u:
        case 0x13u:
        case 0x16u:
        case 0x17u:
          v14 = 4;
          break;
        case 5u:
        case 7u:
        case 0x14u:
        case 0x15u:
          v14 = 8;
          break;
        case 8u:
          goto LABEL_43;
        case 0xEu:
          v14 = 16;
          p_bVal = (unsigned __int8 *)pvarVal;
          goto LABEL_18;
        case 0x10u:
        case 0x11u:
          v14 = 1;
          break;
        default:
          return (unsigned int)-2147024809;
      }
      p_bVal = &pvarVal->bVal;
LABEL_18:
      v15 = v14;
      goto LABEL_19;
    }
    goto LABEL_60;
  }
  if ( vt <= 0x4002 )
  {
    if ( vt != 16386 )
    {
      switch ( pvarVal->vt )
      {
        case 0x2003u:
        case 0x2004u:
        case 0x2013u:
        case 0x2016u:
        case 0x2017u:
          goto LABEL_62;
        case 0x2005u:
        case 0x2007u:
        case 0x2014u:
        case 0x2015u:
          goto LABEL_64;
        case 0x200Bu:
        case 0x2012u:
          goto LABEL_60;
        case 0x200Cu:
          p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarVal->llVal;
          p_parray = &pvarVal->parray;
          goto LABEL_80;
        case 0x200Eu:
          goto LABEL_66;
        case 0x2010u:
        case 0x2011u:
          goto LABEL_58;
        default:
          return (unsigned int)-2147024809;
      }
    }
LABEL_38:
    p_bVal = pvarVal->pbVal;
    v14 = 2;
    goto LABEL_18;
  }
  if ( vt <= 0x6002 )
  {
    if ( vt != 24578 )
    {
      switch ( pvarVal->vt )
      {
        case 0x4003u:
        case 0x4004u:
        case 0x4013u:
        case 0x4016u:
        case 0x4017u:
          p_bVal = pvarVal->pbVal;
          v14 = 4;
          goto LABEL_18;
        case 0x4005u:
        case 0x4007u:
        case 0x4014u:
        case 0x4015u:
          p_bVal = pvarVal->pbVal;
          v14 = 8;
          goto LABEL_18;
        case 0x4008u:
          v16 = 1;
LABEL_43:
          if ( a5 )
            *a5 = 1;
          v40 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarVal->llVal;
          pbstrVal = pvarVal->pbstrVal;
          if ( v16 )
          {
            if ( !SysStringLen(*pbstrVal) )
              goto LABEL_127;
            v20 = v40;
            llVal = (BSTR *)v40->llVal;
          }
          else
          {
            if ( !SysStringLen((BSTR)pbstrVal) )
              goto LABEL_127;
            v20 = v40;
            llVal = (BSTR *)v40;
          }
          v14 = 2 * SysStringLen(*llVal);
          if ( v14 < 2 )
          {
            p_bVal = (unsigned __int8 *)ppvData;
            v14 = 0;
          }
          else
          {
            if ( v16 )
              v20 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)v20->llVal;
            p_bVal = (unsigned __int8 *)v20->llVal;
          }
          v15 = 2;
          break;
        case 0x400Bu:
        case 0x4012u:
          goto LABEL_38;
        case 0x400Eu:
          p_bVal = pvarVal->pbVal;
          v14 = 16;
          goto LABEL_18;
        case 0x4010u:
        case 0x4011u:
          p_bVal = pvarVal->pbVal;
          v14 = 1;
          goto LABEL_18;
        default:
          return (unsigned int)-2147024809;
      }
      goto LABEL_19;
    }
LABEL_59:
    v16 = 1;
LABEL_60:
    v15 = 2;
LABEL_67:
    v22 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarVal->llVal;
    if ( v16 )
      v23 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)v22->llVal;
    else
      v23 = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarVal->llVal;
    v12 = SafeArrayAccessData(v23->parray, &ppvData);
    if ( v12 < 0 )
      return (unsigned int)v12;
    v24 = (SAFEARRAY *)v22->llVal;
    if ( v16 )
      v25 = *(_QWORD *)&v24->cDims;
    else
      v25 = v22->llVal;
    p_bVal = (unsigned __int8 *)ppvData;
    v14 = *(_DWORD *)(v25 + 24) * v15;
    if ( v14 && !ppvData )
    {
      v12 = -2147467261;
      if ( v16 )
        v24 = *(SAFEARRAY **)&v24->cDims;
      SafeArrayUnaccessData(v24);
      return (unsigned int)v12;
    }
LABEL_19:
    *a2 = p_bVal;
    if ( a3 )
      *a3 = v14;
    if ( a4 )
      *a4 = v15;
    if ( a6 )
      *a6 = v13;
    return (unsigned int)v12;
  }
  switch ( pvarVal->vt )
  {
    case 0x6003u:
    case 0x6004u:
    case 0x6013u:
    case 0x6016u:
    case 0x6017u:
      v16 = 1;
LABEL_62:
      v15 = 4;
      goto LABEL_67;
    case 0x6005u:
    case 0x6007u:
    case 0x6014u:
    case 0x6015u:
      v16 = 1;
LABEL_64:
      v15 = 8;
      goto LABEL_67;
    case 0x600Cu:
      p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)&pvarVal->llVal;
      v16 = 1;
      p_parray = pvarVal->pparray;
LABEL_80:
      v36 = 0;
      v26 = *p_parray;
      v37 = (SAFEARRAY ***)p_llVal;
      v41 = v16;
      v12 = SafeArrayAccessData(v26, &v36);
      if ( v12 < 0 )
        return (unsigned int)v12;
      if ( v16 )
        p_llVal = (union tagVARIANT::$::$65D68C826D16CA47CF95571D7BFCD657::$E09503A454170B491AC1C4312CE36FE6 *)p_llVal->llVal;
      v27 = *(_DWORD *)(p_llVal->llVal + 24);
      v34 = v27;
      if ( v27 )
        v13 = *(_WORD *)v36 | 0x2000;
      else
        v13 = 0;
      v28 = 0;
      break;
    case 0x600Eu:
      v16 = 1;
LABEL_66:
      v15 = 16;
      goto LABEL_67;
    case 0x6010u:
    case 0x6011u:
      v16 = 1;
LABEL_58:
      v15 = 1;
      goto LABEL_67;
    case 0x6012u:
      goto LABEL_59;
    default:
      return (unsigned int)-2147024809;
  }
  while ( 2 )
  {
    if ( (unsigned int)v28 >= v27 )
    {
      v14 = v15 * v27;
      goto LABEL_126;
    }
    v29 = v36;
    v30 = 3 * v28;
    v39 = v36;
    v38 = 3 * v28;
    switch ( *((_WORD *)v36 + 12 * v28) )
    {
      case 2:
      case 0xB:
      case 0x12:
        if ( (_DWORD)v28 && v15 != 2 )
          goto LABEL_121;
        v15 = 2;
        goto LABEL_104;
      case 3:
      case 0x13:
      case 0x16:
      case 0x17:
        if ( (_DWORD)v28 && v15 != 4 )
          goto LABEL_121;
        v15 = 4;
        goto LABEL_104;
      case 5:
      case 7:
      case 0x14:
      case 0x15:
        if ( (_DWORD)v28 && v15 != 8 )
          goto LABEL_121;
        v15 = 8;
        goto LABEL_104;
      case 0xE:
        if ( (_DWORD)v28 && v15 != 16 )
          goto LABEL_121;
        v15 = 16;
        goto LABEL_104;
      case 0x10:
      case 0x11:
        if ( (_DWORD)v28 && v15 != 1 )
          goto LABEL_121;
        v15 = 1;
LABEL_104:
        if ( (_DWORD)v28 )
        {
          v31 = ppvData;
        }
        else
        {
          ppvData = WinMalloc(v15 * v27);
          v31 = ppvData;
          if ( !ppvData )
          {
            v12 = -2147024882;
            goto LABEL_122;
          }
          v30 = v38;
          v29 = v39;
        }
        v32 = (unsigned int)v28 * (unsigned __int64)v15;
        if ( v32 <= 0xFFFFFFFF )
        {
          if ( v15 == 1 )
          {
            v28 = (unsigned int)(v28 + 1);
            v31[(unsigned int)v32] = v29[8 * v30 + 8];
            v27 = v34;
          }
          else
          {
            v28 = (unsigned int)(v28 + 1);
            if ( v15 == 2 )
            {
              *(_WORD *)&v31[(unsigned int)v32] = *(_WORD *)&v29[8 * v30 + 8];
              v27 = v34;
            }
            else if ( v15 == 16 )
            {
              *(_OWORD *)&v31[(unsigned int)v32] = *(_OWORD *)&v29[8 * v30];
              v27 = v34;
            }
            else
            {
              if ( v15 == 8 )
                *(_QWORD *)&v31[(unsigned int)v32] = *(_QWORD *)&v29[8 * v30 + 8];
              else
                *(_DWORD *)&v31[(unsigned int)v32] = *(_DWORD *)&v29[8 * v30 + 8];
              v27 = v34;
            }
          }
          continue;
        }
        v12 = -2147418113;
LABEL_122:
        v33 = (SAFEARRAY **)v37;
        if ( v41 )
          v33 = *v37;
        SafeArrayUnaccessData(*v33);
        WinFree(ppvData);
LABEL_126:
        if ( v12 >= 0 )
        {
LABEL_127:
          p_bVal = (unsigned __int8 *)ppvData;
          goto LABEL_19;
        }
        return (unsigned int)v12;
      default:
LABEL_121:
        v12 = -2147024809;
        goto LABEL_122;
    }
  }
}

```

## disassembly

```asm
0x18000a730  push    rsi
0x18000a732  push    r12
0x18000a734  push    r14
0x18000a736  push    r15
0x18000a738  sub     rsp, 58h
0x18000a73c  mov     r15, r9
0x18000a73f  mov     r14, r8
0x18000a742  xor     r9d, r9d
0x18000a745  mov     r12, rdx
0x18000a748  mov     [rsp+78h+ppvData], r9
0x18000a74d  mov     r10d, r9d
0x18000a750  test    rcx, rcx
0x18000a753  jnz     short loc_18000A75F
0x18000a755  mov     eax, 8000FFFFh
0x18000a75a  jmp     loc_18000A85C
0x18000a75f  mov     [rdx], r9
0x18000a762  test    r14, r14
0x18000a765  jz      short loc_18000A76A
0x18000a767  mov     [r8], r9d
0x18000a76a  test    r15, r15
0x18000a76d  jz      short loc_18000A772
0x18000a76f  mov     [r15], r9d
0x18000a772  mov     rdx, [rsp+78h+arg_20]
0x18000a77a  test    rdx, rdx
0x18000a77d  jz      short loc_18000A782
0x18000a77f  mov     [rdx], r9b
0x18000a782  mov     eax, 400Ch
0x18000a787  cmp     [rcx], ax
0x18000a78a  jnz     short loc_18000A79F
0x18000a78c  mov     rcx, [rcx+8]
0x18000a790  test    rcx, rcx
0x18000a793  jnz     short loc_18000A79F
0x18000a795  mov     eax, 80070057h
0x18000a79a  jmp     loc_18000A85C
0x18000a79f  movzx   eax, word ptr [rcx]
0x18000a7a2  mov     r8d, 0BFFFh
0x18000a7a8  mov     [rsp+78h+arg_8], rbx
0x18000a7b0  mov     esi, r9d
0x18000a7b3  mov     [rsp+78h+arg_10], rbp
0x18000a7bb  movzx   ebx, ax
0x18000a7be  mov     [rsp+78h+arg_18], rdi
0x18000a7c6  and     bx, r8w
0x18000a7ca  mov     [rsp+78h+var_28], r13
0x18000a7cf  mov     edi, r9d
0x18000a7d2  mov     ebp, r9d
0x18000a7d5  test    eax, eax
0x18000a7d7  jz      short loc_18000A819; jumptable 000000018000A80C case 1
0x18000a7d9  xor     r13b, r13b
0x18000a7dc  cmp     eax, 2002h
0x18000a7e1  ja      loc_18000A887
0x18000a7e7  jz      loc_18000A9F3; jumptable 000000018000A8B1 cases 8203,8210
0x18000a7ed  dec     eax; switch 23 cases
0x18000a7ef  cmp     eax, 16h
0x18000a7f2  ja      def_18000A80C; jumptable 000000018000A80C default case, cases 6,9,10,12,13,15
0x18000a7f8  cdqe
0x18000a7fa  lea     r8, __ImageBase
0x18000a801  mov     eax, ds:(jpt_18000A80C - 180000000h)[r8+rax*4]
0x18000a809  add     rax, r8
0x18000a80c  jmp     rax; switch jump
0x18000a80e  mov     edi, 1; jumptable 000000018000A80C cases 16,17
0x18000a813  lea     r10, [rcx+8]
0x18000a817  mov     ebp, edi
0x18000a819  mov     [r12], r10; jumptable 000000018000A80C case 1
0x18000a81d  test    r14, r14
0x18000a820  jz      short loc_18000A825
0x18000a822  mov     [r14], edi
0x18000a825  test    r15, r15
0x18000a828  jz      short loc_18000A82D
0x18000a82a  mov     [r15], ebp
0x18000a82d  mov     rax, [rsp+78h+arg_28]
0x18000a835  test    rax, rax
0x18000a838  jz      short loc_18000A83D
0x18000a83a  mov     [rax], bx
0x18000a83d  mov     r13, [rsp+78h+var_28]
0x18000a842  mov     eax, esi
0x18000a844  mov     rdi, [rsp+78h+arg_18]
0x18000a84c  mov     rbp, [rsp+78h+arg_10]
0x18000a854  mov     rbx, [rsp+78h+arg_8]
0x18000a85c  add     rsp, 58h
0x18000a860  pop     r15
0x18000a862  pop     r14
0x18000a864  pop     r12
0x18000a866  pop     rsi
0x18000a867  retn
0x18000a868  mov     edi, 2; jumptable 000000018000A80C cases 2,11,18
0x18000a86d  jmp     short loc_18000A813
0x18000a86f  mov     edi, 4; jumptable 000000018000A80C cases 3,4,19,22,23
0x18000a874  jmp     short loc_18000A813
0x18000a876  mov     edi, 8; jumptable 000000018000A80C cases 5,7,20,21
0x18000a87b  jmp     short loc_18000A813
0x18000a87d  mov     edi, 10h; jumptable 000000018000A80C case 14
0x18000a882  mov     r10, rcx
0x18000a885  jmp     short loc_18000A817
0x18000a887  cmp     eax, 4002h
0x18000a88c  ja      short loc_18000A8BF
0x18000a88e  jz      short loc_18000A902; jumptable 000000018000A8F2 cases 16395,16402
0x18000a890  add     eax, 0FFFFDFFDh; switch 21 cases
0x18000a895  cmp     eax, 14h
0x18000a898  ja      def_18000A80C; jumptable 000000018000A80C default case, cases 6,9,10,12,13,15
0x18000a89e  cdqe
0x18000a8a0  lea     rdx, __ImageBase
0x18000a8a7  mov     eax, ds:(jpt_18000A8B1 - 180000000h)[rdx+rax*4]
0x18000a8ae  add     rax, rdx
0x18000a8b1  jmp     rax; switch jump
0x18000a8b3  lea     rbx, [rcx+8]; jumptable 000000018000A8B1 case 8204
0x18000a8b7  mov     rcx, rbx
0x18000a8ba  jmp     loc_18000AA8D
0x18000a8bf  cmp     eax, 6002h
0x18000a8c4  ja      loc_18000A9C3
0x18000a8ca  jz      loc_18000A9F0; jumptable 000000018000A9E4 case 24594
0x18000a8d0  add     eax, 0FFFFBFFDh; switch 21 cases
0x18000a8d5  cmp     eax, 14h
0x18000a8d8  ja      def_18000A80C; jumptable 000000018000A80C default case, cases 6,9,10,12,13,15
0x18000a8de  cdqe
0x18000a8e0  lea     r8, __ImageBase
0x18000a8e7  mov     eax, ds:(jpt_18000A8F2 - 180000000h)[r8+rax*4]
0x18000a8ef  add     rax, r8
0x18000a8f2  jmp     rax; switch jump
0x18000a8f4  mov     r10, [rcx+8]; jumptable 000000018000A8F2 cases 16400,16401
0x18000a8f8  mov     edi, 1
0x18000a8fd  jmp     loc_18000A817
0x18000a902  mov     r10, [rcx+8]; jumptable 000000018000A8F2 cases 16395,16402
0x18000a906  mov     edi, 2
0x18000a90b  jmp     loc_18000A817
0x18000a910  mov     r10, [rcx+8]; jumptable 000000018000A8F2 cases 16387,16388,16403,16406,16407
0x18000a914  mov     edi, 4
0x18000a919  jmp     loc_18000A817
0x18000a91e  mov     r10, [rcx+8]; jumptable 000000018000A8F2 cases 16389,16391,16404,16405
0x18000a922  mov     edi, 8
0x18000a927  jmp     loc_18000A817
0x18000a92c  mov     r10, [rcx+8]; jumptable 000000018000A8F2 case 16398
0x18000a930  mov     edi, 10h
0x18000a935  jmp     loc_18000A817
0x18000a93a  mov     r13b, 1; jumptable 000000018000A8F2 case 16392
0x18000a93d  test    rdx, rdx; jumptable 000000018000A80C case 8
0x18000a940  jz      short loc_18000A945
0x18000a942  mov     byte ptr [rdx], 1
0x18000a945  add     rcx, 8
0x18000a949  mov     [rsp+78h+arg_0], rcx
0x18000a951  mov     rcx, [rcx]; pbstr
0x18000a954  test    r13b, r13b
0x18000a957  jz      short loc_18000A978
0x18000a959  mov     rcx, [rcx]; pbstr
0x18000a95c  call    cs:__imp_SysStringLen
0x18000a962  test    eax, eax
0x18000a964  jz      loc_18000ACC0
0x18000a96a  mov     rbp, [rsp+78h+arg_0]
0x18000a972  mov     rcx, [rbp+0]
0x18000a976  jmp     short loc_18000A991
0x18000a978  call    cs:__imp_SysStringLen
0x18000a97e  test    eax, eax
0x18000a980  jz      loc_18000ACC0
0x18000a986  mov     rbp, [rsp+78h+arg_0]
0x18000a98e  mov     rcx, rbp
0x18000a991  mov     rcx, [rcx]; pbstr
0x18000a994  call    cs:__imp_SysStringLen
0x18000a99a  mov     edi, eax
0x18000a99c  add     edi, edi
0x18000a99e  cmp     edi, 2
0x18000a9a1  jb      short loc_18000A9B2
0x18000a9a3  test    r13b, r13b
0x18000a9a6  jz      short loc_18000A9AC
0x18000a9a8  mov     rbp, [rbp+0]
0x18000a9ac  mov     r10, [rbp+0]
0x18000a9b0  jmp     short loc_18000A9B9
0x18000a9b2  mov     r10, [rsp+78h+ppvData]
0x18000a9b7  xor     edi, edi
0x18000a9b9  mov     ebp, 2
0x18000a9be  jmp     loc_18000A819; jumptable 000000018000A80C case 1
0x18000a9c3  add     eax, 0FFFF9FFDh; switch 21 cases
0x18000a9c8  cmp     eax, 14h
0x18000a9cb  ja      def_18000A80C; jumptable 000000018000A80C default case, cases 6,9,10,12,13,15
0x18000a9d1  cdqe
0x18000a9d3  lea     rdx, __ImageBase
0x18000a9da  mov     eax, ds:(jpt_18000A9E4 - 180000000h)[rdx+rax*4]
0x18000a9e1  add     rax, rdx
0x18000a9e4  jmp     rax; switch jump
0x18000a9e6  mov     r13b, 1; jumptable 000000018000A9E4 cases 24592,24593
0x18000a9e9  mov     ebp, 1; jumptable 000000018000A8B1 cases 8208,8209
0x18000a9ee  jmp     short loc_18000AA16
0x18000a9f0  mov     r13b, 1; jumptable 000000018000A9E4 case 24594
0x18000a9f3  mov     ebp, 2; jumptable 000000018000A8B1 cases 8203,8210
0x18000a9f8  jmp     short loc_18000AA16
0x18000a9fa  mov     r13b, 1; jumptable 000000018000A9E4 cases 24579,24580,24595,24598,24599
0x18000a9fd  mov     ebp, 4; jumptable 000000018000A8B1 cases 8195,8196,8211,8214,8215
0x18000aa02  jmp     short loc_18000AA16
0x18000aa04  mov     r13b, 1; jumptable 000000018000A9E4 cases 24581,24583,24596,24597
0x18000aa07  mov     ebp, 8; jumptable 000000018000A8B1 cases 8197,8199,8212,8213
0x18000aa0c  jmp     short loc_18000AA16
0x18000aa0e  mov     r13b, 1; jumptable 000000018000A9E4 case 24590
0x18000aa11  mov     ebp, 10h; jumptable 000000018000A8B1 case 8206
0x18000aa16  lea     rdi, [rcx+8]
0x18000aa1a  test    r13b, r13b
0x18000aa1d  jz      short loc_18000AA24
0x18000aa1f  mov     rcx, [rdi]
0x18000aa22  jmp     short loc_18000AA27
0x18000aa24  mov     rcx, rdi
0x18000aa27  mov     rcx, [rcx]; psa
0x18000aa2a  lea     rdx, [rsp+78h+ppvData]; ppvData
0x18000aa2f  call    cs:__imp_SafeArrayAccessData
0x18000aa35  mov     esi, eax
0x18000aa37  test    eax, eax
0x18000aa39  js      loc_18000A83D
0x18000aa3f  mov     rcx, [rdi]
0x18000aa42  test    r13b, r13b
0x18000aa45  jz      short loc_18000AA4C
0x18000aa47  mov     rax, [rcx]
0x18000aa4a  jmp     short loc_18000AA4F
0x18000aa4c  mov     rax, rcx
0x18000aa4f  mov     r10, [rsp+78h+ppvData]
0x18000aa54  mov     edi, ebp
0x18000aa56  imul    edi, [rax+18h]
0x18000aa5a  test    edi, edi
0x18000aa5c  jz      loc_18000A819; jumptable 000000018000A80C case 1
0x18000aa62  test    r10, r10
0x18000aa65  jnz     loc_18000A819; jumptable 000000018000A80C case 1
0x18000aa6b  mov     esi, 80004003h
0x18000aa70  test    r13b, r13b
0x18000aa73  jz      short loc_18000AA78
0x18000aa75  mov     rcx, [rcx]; psa
0x18000aa78  call    cs:__imp_SafeArrayUnaccessData
0x18000aa7e  jmp     loc_18000A83D
0x18000aa83  lea     rbx, [rcx+8]; jumptable 000000018000A9E4 case 24588
0x18000aa87  mov     r13b, 1
0x18000aa8a  mov     rcx, [rbx]
0x18000aa8d  mov     [rsp+78h+var_48], r9
0x18000aa92  lea     rdx, [rsp+78h+var_48]; ppvData
0x18000aa97  mov     rcx, [rcx]; psa
0x18000aa9a  mov     [rsp+78h+var_40], rbx
0x18000aa9f  mov     byte ptr [rsp+78h+arg_0], r13b
0x18000aaa7  call    cs:__imp_SafeArrayAccessData
0x18000aaad  mov     esi, eax
0x18000aaaf  test    eax, eax
0x18000aab1  js      loc_18000A83D
0x18000aab7  test    r13b, r13b
0x18000aaba  jz      short loc_18000AABF
0x18000aabc  mov     rbx, [rbx]
0x18000aabf  mov     rax, [rbx]
0x18000aac2  mov     r8d, [rax+18h]
0x18000aac6  mov     [rsp+78h+var_58], r8d
0x18000aacb  test    r8d, r8d
0x18000aace  jz      short loc_18000AADF
0x18000aad0  mov     rax, [rsp+78h+var_48]
0x18000aad5  mov     ebx, 2000h
0x18000aada  or      bx, [rax]
0x18000aadd  jmp     short loc_18000AAE4
0x18000aadf  xor     eax, eax
0x18000aae1  movzx   ebx, ax
0x18000aae4  xor     r13d, r13d
0x18000aae7  lea     rdx, __ImageBase
0x18000aaee  cmp     r13d, r8d
0x18000aaf1  jnb     loc_18000ACB2
0x18000aaf7  mov     r10, [rsp+78h+var_48]
0x18000aafc  lea     r9, ds:0[r13*2]
0x18000ab04  add     r9, r13
0x18000ab07  mov     [rsp+78h+var_30], r10
0x18000ab0c  mov     [rsp+78h+var_38], r9
0x18000ab11  movzx   eax, word ptr [r10+r9*8]
0x18000ab16  add     eax, 0FFFFFFFEh; switch 22 cases
0x18000ab19  cmp     eax, 15h
0x18000ab1c  ja      def_18000AB36; jumptable 000000018000AB36 default case, cases 4,6,8-10,12,13,15
0x18000ab22  cdqe
0x18000ab24  movzx   eax, ds:(byte_18000AE44 - 180000000h)[rdx+rax]
0x18000ab2c  mov     ecx, ds:(jpt_18000AB36 - 180000000h)[rdx+rax*4]
0x18000ab33  add     rcx, rdx
0x18000ab36  jmp     rcx; switch jump
0x18000ab38  test    r13d, r13d; jumptable 000000018000AB36 cases 16,17
0x18000ab3b  jz      short loc_18000AB46
0x18000ab3d  cmp     ebp, 1
0x18000ab40  jnz     def_18000AB36; jumptable 000000018000AB36 default case, cases 4,6,8-10,12,13,15
0x18000ab46  mov     ebp, 1
0x18000ab4b  jmp     short loc_18000AB9F
0x18000ab4d  test    r13d, r13d; jumptable 000000018000AB36 cases 2,11,18
0x18000ab50  jz      short loc_18000AB5B
0x18000ab52  cmp     ebp, 2
0x18000ab55  jnz     def_18000AB36; jumptable 000000018000AB36 default case, cases 4,6,8-10,12,13,15
0x18000ab5b  mov     ebp, 2
0x18000ab60  jmp     short loc_18000AB9F
0x18000ab62  test    r13d, r13d; jumptable 000000018000AB36 cases 3,19,22,23
0x18000ab65  jz      short loc_18000AB70
0x18000ab67  cmp     ebp, 4
0x18000ab6a  jnz     def_18000AB36; jumptable 000000018000AB36 default case, cases 4,6,8-10,12,13,15
0x18000ab70  mov     ebp, 4
0x18000ab75  jmp     short loc_18000AB9F
0x18000ab77  test    r13d, r13d; jumptable 000000018000AB36 cases 5,7,20,21
0x18000ab7a  jz      short loc_18000AB85
0x18000ab7c  cmp     ebp, 8
0x18000ab7f  jnz     def_18000AB36; jumptable 000000018000AB36 default case, cases 4,6,8-10,12,13,15
0x18000ab85  mov     ebp, 8
0x18000ab8a  jmp     short loc_18000AB9F
0x18000ab8c  test    r13d, r13d; jumptable 000000018000AB36 case 14
0x18000ab8f  jz      short loc_18000AB9A
0x18000ab91  cmp     ebp, 10h
0x18000ab94  jnz     def_18000AB36; jumptable 000000018000AB36 default case, cases 4,6,8-10,12,13,15
0x18000ab9a  mov     ebp, 10h
0x18000ab9f  test    esi, esi
0x18000aba1  js      loc_18000AC8B
0x18000aba7  test    r13d, r13d
0x18000abaa  jnz     short loc_18000ABDB
0x18000abac  mov     ecx, r8d
  ... truncated ...
```
