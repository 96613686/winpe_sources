# AppendPropVariant_0

- ea: `0x18021cf40`
- end: `0x18021d975`
- name: `AppendPropVariant_0`
- size: `2613`
- prototype: `__int64 __fastcall(PROPVARIANT *pvar, PROPVARIANT *pvarSrc)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x1802724e0`

## callees

- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x180050d6c`
- `0x1800ec0e0`
- `0x180111d68`
- `0x18019d300`
- `0x1801c1658`
- `0x1801dae40`
- `0x18021cf40`
- `0x180344ce4`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021d952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18021d952`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d5d7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d398`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d54d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18021d5d7`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021cf9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d082`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d1ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d306`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d3cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d609`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d7ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d8a9`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021cf9f`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d082`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d1ba`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d306`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d3cc`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d57e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d609`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d7ee`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021d8a9`

## pseudocode

```c
__int64 __fastcall AppendPropVariant_0(PROPVARIANT *pvar, PROPVARIANT *pvarSrc)
{
  __int64 v4; // rcx
  __int64 *v5; // rbx
  int v6; // edi
  __int64 v7; // rax
  __int64 v8; // rax
  __int64 v9; // rdx
  unsigned __int16 v10; // cx
  __int64 v11; // rcx
  __int64 *v12; // rbx
  __int64 v13; // rax
  __int64 v14; // rax
  __int16 v15; // dx
  unsigned int v16; // ebx
  int v17; // r12d
  __int64 v18; // rcx
  __int64 v19; // r8
  __int64 *v20; // rbx
  __int64 v21; // rax
  __int64 v22; // r8
  __int64 v23; // rax
  __int64 v24; // rdx
  SIZE_T *p_cb; // rcx
  int v26; // eax
  __int64 v27; // rcx
  char v28; // r9
  __int64 *v29; // rbx
  __int64 v30; // rax
  __int64 v31; // r8
  int v32; // eax
  __int64 v33; // rax
  __int64 v34; // rcx
  __int64 *v35; // rbx
  __int64 v36; // rax
  __int64 v37; // rax
  __int16 v38; // cx
  PROPVARIANT *v39; // rax
  PROPVARIANT *v40; // rdx
  __int16 v41; // cx
  unsigned int v42; // ecx
  unsigned int *v43; // r9
  PROPVARIANT *v44; // r15
  size_t v45; // rax
  size_t v46; // r8
  PROPVARIANT v47; // rdx
  unsigned int *v48; // rcx
  unsigned int v49; // r8d
  unsigned int *v50; // rax
  __int64 *v51; // rcx
  __int64 v52; // rax
  __int64 *v53; // rcx
  __int64 v54; // rax
  __int64 v55; // r8
  __int64 v56; // r8
  __int64 v57; // rax
  __int64 v58; // rdx
  __int64 v59; // rax
  PROPVARIANT *v60; // r15
  __int64 *v61; // rbx
  __int64 v62; // rax
  __int64 v63; // r8
  __int64 v64; // rax
  __int64 v65; // rcx
  __int64 *v66; // rbx
  __int64 v67; // rax
  __int64 v68; // rax
  unsigned int v70; // [rsp+30h] [rbp-39h]
  unsigned int *v71; // [rsp+38h] [rbp-31h]
  PROPVARIANT *v72; // [rsp+40h] [rbp-29h]
  size_t Size; // [rsp+48h] [rbp-21h]
  size_t Sizea; // [rsp+48h] [rbp-21h]
  unsigned int *v75; // [rsp+50h] [rbp-19h]
  _DWORD v76[2]; // [rsp+58h] [rbp-11h]
  PROPVARIANT *v77; // [rsp+60h] [rbp-9h]
  int v78; // [rsp+68h] [rbp-1h]
  PROPVARIANT *v79; // [rsp+70h] [rbp+7h]
  PROPVARIANT *v80; // [rsp+D0h] [rbp+67h] BYREF
  SIZE_T cb; // [rsp+D8h] [rbp+6Fh] BYREF
  unsigned int v82; // [rsp+E0h] [rbp+77h] BYREF
  int v83; // [rsp+E8h] [rbp+7Fh]

  v80 = pvar;
  v82 = 0;
  if ( pvar == pvarSrc )
  {
    sub_18002FEE0(&v80, "CMFPropVariantConvert::Concatenate", 1161);
    v5 = (__int64 *)qword_1803CEF18;
    v6 = -2147467261;
    if ( !qword_1803CEF18 )
    {
      v7 = MFGetCallStackTracingWeakReference(v4);
      qword_1803CEF18 = v7;
      if ( v7 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v7 + 8LL))(v7, 2032) )
      {
        v5 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v5 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v5 + 8) )
    {
      v8 = sub_1800402C0(v5);
      if ( *(_DWORD *)(v8 + 1996) != -2147467261 )
        sub_1800EC0E0(v8, "CMFPropVariantConvert::Concatenate", 1161, 2147500035LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_159;
    v9 = 73;
LABEL_158:
    sub_180050D6C(*((_QWORD *)RequestContext + 2), v9, qword_18035FAF0, 0, v6);
LABEL_159:
    p_cb = (SIZE_T *)&v80;
    goto LABEL_160;
  }
  v10 = *(_WORD *)pvarSrc;
  if ( *(_WORD *)pvarSrc && *(_WORD *)pvar && ((v10 ^ *(_WORD *)pvar) & 0xFFF) != 0 )
  {
    sub_18002FEE0(&v80, "CMFPropVariantConvert::Concatenate", 1168);
    v12 = (__int64 *)qword_1803CEF18;
    v6 = -1072875801;
    if ( !qword_1803CEF18 )
    {
      v13 = MFGetCallStackTracingWeakReference(v11);
      qword_1803CEF18 = v13;
      if ( v13 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v13 + 8LL))(v13, 2032) )
      {
        v12 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v12 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v12 + 8) )
    {
      v14 = sub_1800402C0(v12);
      if ( *(_DWORD *)(v14 + 1996) != -1072875801 )
        sub_1800EC0E0(v14, "CMFPropVariantConvert::Concatenate", 1168, 3222091495LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_159;
    v9 = 74;
    goto LABEL_158;
  }
  v15 = *(_WORD *)pvar;
  if ( (*(_WORD *)pvar & 0xFFF) == 0xE || (v10 & 0xFFF) == 0xE )
  {
    sub_18002FEE0(&v80, "CMFPropVariantConvert::Concatenate", 1174);
    v66 = (__int64 *)qword_1803CEF18;
    v6 = -1072875800;
    if ( !qword_1803CEF18 )
    {
      v67 = MFGetCallStackTracingWeakReference(v65);
      qword_1803CEF18 = v67;
      if ( v67 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v67 + 8LL))(v67, 2032) )
      {
        v66 = (__int64 *)qword_1803CEF18;
      }
      else
      {
        v66 = &qword_1803CE250;
        qword_1803CEF18 = (__int64)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v66 + 8) )
    {
      v68 = sub_1800402C0(v66);
      if ( *(_DWORD *)(v68 + 1996) != -1072875800 )
        sub_1800EC0E0(v68, "CMFPropVariantConvert::Concatenate", 1174, 3222091496LL);
    }
    if ( !byte_1803CECE8 )
      goto LABEL_159;
    v9 = 75;
    goto LABEL_158;
  }
  if ( v15 )
  {
    v16 = 1;
    if ( (v15 & 0x1000) != 0 )
      v16 = *((_DWORD *)pvar + 2);
  }
  else
  {
    v16 = 0;
  }
  if ( v10 )
  {
    v17 = 1;
    if ( (v10 & 0x1000) != 0 )
      v17 = *((_DWORD *)pvarSrc + 2);
    v6 = sub_1801C1658(pvar, &v82, 4096, 4095);
    sub_18002FEE0(&cb, "CMFPropVariantConvert::Concatenate", 1210);
    if ( v6 < 0 )
    {
      v20 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v21 = MFGetCallStackTracingWeakReference(v18);
        qword_1803CEF18 = v21;
        if ( v21
          && (*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v21 + 8LL))(
               v21,
               2032,
               v22,
               0) )
        {
          v20 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v20 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v20 + 8) )
      {
        v23 = sub_1800402C0(v20);
        if ( *(_DWORD *)(v23 + 1996) != v6 )
          sub_1800EC0E0(v23, "CMFPropVariantConvert::Concatenate", 1210, (unsigned int)v6);
      }
      if ( byte_1803CECE8 )
      {
        v24 = 76;
LABEL_46:
        sub_180050D6C(*((_QWORD *)RequestContext + 2), v24, qword_18035FAF0, 0, v6);
        goto LABEL_47;
      }
      goto LABEL_47;
    }
    if ( !v16 && v17 == 1 )
    {
      if ( (*(_WORD *)pvarSrc & 0x1000) != 0 )
        v26 = sub_1801DAE40(pvar);
      else
        v26 = sub_18019D300(pvar, pvarSrc);
      v6 = v26;
      goto LABEL_47;
    }
    if ( v17 + v16 < v16 )
    {
      v61 = (__int64 *)qword_1803CEF18;
      v6 = -2147024362;
      if ( !qword_1803CEF18 )
      {
        v62 = MFGetCallStackTracingWeakReference(v18);
        qword_1803CEF18 = v62;
        if ( v62
          && (*(unsigned int (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v62 + 8LL))(
               v62,
               2032,
               v63,
               0) )
        {
          v61 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v61 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v61 + 8) )
      {
        v64 = sub_1800402C0(v61);
        if ( *(_DWORD *)(v64 + 1996) != -2147024362 )
          sub_1800EC0E0(v64, "CMFPropVariantConvert::Concatenate", 1263, 2147942934LL);
      }
      if ( byte_1803CECE8 )
      {
        v24 = 77;
        goto LABEL_46;
      }
      goto LABEL_47;
    }
    LODWORD(cb) = v17 + v16;
    v6 = sub_180111D68(v82 * (unsigned __int64)(v17 + v16), &cb, v19, 0);
    if ( v6 < 0 )
    {
      v29 = (__int64 *)qword_1803CEF18;
      if ( !qword_1803CEF18 )
      {
        v30 = MFGetCallStackTracingWeakReference(v27);
        v28 = 0;
        qword_1803CEF18 = v30;
        if ( v30
          && (v32 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, _QWORD))(*(_QWORD *)v30 + 8LL))(
                      v30,
                      2032,
                      v31,
                      0),
              v28 = 0,
              v32) )
        {
          v29 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v29 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v29 + 8) != v28 )
      {
        v33 = sub_1800402C0(v29);
        if ( *(_DWORD *)(v33 + 1996) != v6 )
          sub_1800EC0E0(v33, "CMFPropVariantConvert::Concatenate", 1264, (unsigned int)v6);
      }
      if ( byte_1803CECE8 )
      {
        v24 = 78;
        goto LABEL_46;
      }
LABEL_47:
      p_cb = &cb;
LABEL_160:
      sub_18003ECB0(p_cb);
      goto LABEL_161;
    }
    v75 = (unsigned int *)CoTaskMemAlloc((unsigned int)cb);
    if ( !v75 )
    {
      v35 = (__int64 *)qword_1803CEF18;
      v6 = -2147024882;
      if ( !qword_1803CEF18 )
      {
        v36 = MFGetCallStackTracingWeakReference(v34);
        qword_1803CEF18 = v36;
        if ( v36 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v36 + 8LL))(v36, 2032) )
        {
          v35 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v35 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v35 + 8) )
      {
        v37 = sub_1800402C0(v35);
        if ( *(_DWORD *)(v37 + 1996) != -2147024882 )
          sub_1800EC0E0(v37, "CMFPropVariantConvert::Concatenate", 1266, 2147942414LL);
      }
      if ( byte_1803CECE8 )
        sub_180050D6C(*((_QWORD *)RequestContext + 2), 79, qword_18035FAF0, 0, -2147024882);
      goto LABEL_47;
    }
    v38 = *(_WORD *)pvar;
    v76[0] = v16;
    v72 = pvar + 1;
    if ( (v38 & 0x1000) != 0 )
    {
      v39 = (PROPVARIANT *)pvar[2];
    }
    else
    {
      v39 = pvar + 1;
      v72 = pvar + 1;
    }
    v40 = pvarSrc + 1;
    v41 = *(_WORD *)pvarSrc & 0x1000;
    v77 = v39;
    v78 = v17;
    if ( v41 )
      v40 = (PROPVARIANT *)pvarSrc[2];
    else
      v72 = pvar + 1;
    v42 = 0;
    v79 = v40;
    LODWORD(cb) = 0;
    v43 = v75;
    v71 = v75;
    while ( 1 )
    {
      v83 = 0;
      v44 = (&v77)[2 * (int)v42];
      v70 = v76[4 * v42];
      if ( v70 )
        break;
LABEL_136:
      LODWORD(cb) = ++v42;
      if ( v42 >= 2 )
      {
        v60 = v80;
        *(_OWORD *)v80 = 0;
        v60[2] = 0;
        *(_WORD *)v60 = *(_WORD *)pvarSrc | 0x1000;
        *(_DWORD *)v72 = v17 + v16;
        v60[2] = v75;
        goto LABEL_47;
      }
    }
    v45 = v82;
    while ( 1 )
    {
      if ( !v42 )
      {
        v46 = v45;
        goto LABEL_88;
      }
      v49 = 0;
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 8 )
        goto LABEL_109;
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x1E )
      {
        v55 = -1;
        do
          ++v55;
        while ( *((_BYTE *)*v44 + v55) );
        v49 = v55 + 1;
        goto LABEL_95;
      }
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x1F )
      {
LABEL_109:
        v56 = -1;
        do
          ++v56;
        while ( *((_WORD *)*v44 + v56) );
        v49 = 2 * v56 + 2;
      }
      else
      {
        if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x41 )
        {
          v49 = *(_DWORD *)v44;
          goto LABEL_101;
        }
        if ( (*(_WORD *)pvarSrc & 0xFFF) == 0x48 )
        {
          v49 = 16;
LABEL_95:
          Size = v49;
          v50 = (unsigned int *)CoTaskMemAlloc(v49);
          *(_QWORD *)v71 = v50;
          if ( v50 )
          {
            v46 = Size;
            v47 = *v44;
            goto LABEL_133;
          }
          v51 = (__int64 *)qword_1803CEF18;
          v6 = -2147024882;
          if ( !qword_1803CEF18 )
          {
            v52 = MFGetCallStackTracingWeakReference(0);
            qword_1803CEF18 = v52;
            if ( v52 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v52 + 8LL))(v52, 2032) )
            {
              v51 = (__int64 *)qword_1803CEF18;
            }
            else
            {
              v51 = &qword_1803CE250;
              qword_1803CEF18 = (__int64)&qword_1803CE250;
            }
          }
          if ( *((_BYTE *)v51 + 8) )
          {
            v59 = sub_1800402C0(v51);
            if ( *(_DWORD *)(v59 + 1996) != -2147024882 )
              sub_1800EC0E0(v59, "CMFPropVariantConvert::Concatenate", 1328, 2147942414LL);
          }
          if ( !byte_1803CECE8 )
            goto LABEL_135;
          v58 = 80;
          goto LABEL_131;
        }
      }
      if ( (*(_WORD *)pvarSrc & 0xFFF) == 8
        || (*(_WORD *)pvarSrc & 0xFFF) == 0x1E
        || (*(_WORD *)pvarSrc & 0xFFF) == 0x1F )
      {
        goto LABEL_95;
      }
      if ( (*(_WORD *)pvarSrc & 0xFFF) != 0x41 )
      {
        if ( (*(_WORD *)pvarSrc & 0xFFF) != 0x48 )
        {
          v46 = v82;
LABEL_88:
          v47 = v44;
          v48 = v43;
LABEL_134:
          memcpy(v48, v47, v46);
          goto LABEL_135;
        }
        goto LABEL_95;
      }
LABEL_101:
      Sizea = v49;
      *v43 = v49;
      v50 = (unsigned int *)CoTaskMemAlloc(v49);
      *((_QWORD *)v71 + 1) = v50;
      if ( v50 )
      {
        v46 = Sizea;
        v47 = v44[1];
LABEL_133:
        v48 = v50;
        goto LABEL_134;
      }
      v53 = (__int64 *)qword_1803CEF18;
      v6 = -2147024882;
      if ( !qword_1803CEF18 )
      {
        v54 = MFGetCallStackTracingWeakReference(0);
        qword_1803CEF18 = v54;
        if ( v54 && (*(unsigned int (__fastcall **)(__int64, __int64))(*(_QWORD *)v54 + 8LL))(v54, 2032) )
        {
          v53 = (__int64 *)qword_1803CEF18;
        }
        else
        {
          v53 = &qword_1803CE250;
          qword_1803CEF18 = (__int64)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v53 + 8) )
      {
        v57 = sub_1800402C0(v53);
        if ( *(_DWORD *)(v57 + 1996) != -2147024882 )
          sub_1800EC0E0(v57, "CMFPropVariantConvert::Concatenate", 1335, 2147942414LL);
      }
      if ( !byte_1803CECE8 )
        goto LABEL_135;
      v58 = 81;
LABEL_131:
      sub_180050D6C(*((_QWORD *)RequestContext + 2), v58, qword_18035FAF0, 0, -2147024882);
LABEL_135:
      v45 = v82;
      v44 = (PROPVARIANT *)((char *)v44 + v82);
      v43 = (unsigned int *)((char *)v71 + v82);
      v42 = cb;
      v71 = v43;
      if ( v70 <= ++v83 )
        goto LABEL_136;
    }
  }
  v6 = 0;
LABEL_161:
  CoTaskMemFree(0);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18021cf40  mov     [rsp-8+arg_0], rcx
0x18021cf45  push    rbp
0x18021cf46  push    rbx
0x18021cf47  push    rsi
0x18021cf48  push    rdi
0x18021cf49  push    r12
0x18021cf4b  push    r13
0x18021cf4d  push    r14
0x18021cf4f  push    r15
0x18021cf51  lea     rbp, [rsp-1Fh]
0x18021cf56  sub     rsp, 88h
0x18021cf5d  xor     r12d, r12d
0x18021cf60  mov     r13, rdx
0x18021cf63  mov     [rbp+57h+arg_10], r12d
0x18021cf67  mov     r15, rcx
0x18021cf6a  cmp     rcx, rdx
0x18021cf6d  jnz     loc_18021D028
0x18021cf73  mov     esi, 489h
0x18021cf78  lea     r14, aCmfpropvariant_10; "CMFPropVariantConvert::Concatenate"
0x18021cf7f  mov     r8d, esi
0x18021cf82  lea     rcx, [rbp+57h+arg_0]
0x18021cf86  mov     rdx, r14
0x18021cf89  call    sub_18002FEE0
0x18021cf8e  mov     rbx, cs:qword_1803CEF18
0x18021cf95  mov     edi, 80004003h
0x18021cf9a  test    rbx, rbx
0x18021cf9d  jnz     short loc_18021CFE7
0x18021cf9f  call    cs:MFGetCallStackTracingWeakReference
0x18021cfa6  nop     dword ptr [rax+rax+00h]
0x18021cfab  mov     cs:qword_1803CEF18, rax
0x18021cfb2  mov     rcx, rax
0x18021cfb5  test    rax, rax
0x18021cfb8  jz      short loc_18021CFD9
0x18021cfba  mov     rax, [rax]
0x18021cfbd  mov     edx, 7F0h
0x18021cfc2  mov     rax, [rax+8]
0x18021cfc6  call    cs:__guard_dispatch_icall_fptr
0x18021cfcc  test    eax, eax
0x18021cfce  jz      short loc_18021CFD9
0x18021cfd0  mov     rbx, cs:qword_1803CEF18
0x18021cfd7  jmp     short loc_18021CFE7
0x18021cfd9  lea     rbx, qword_1803CE250
0x18021cfe0  mov     cs:qword_1803CEF18, rbx
0x18021cfe7  cmp     [rbx+8], r12b
0x18021cfeb  jz      short loc_18021D00E
0x18021cfed  mov     rcx, rbx
0x18021cff0  call    sub_1800402C0
0x18021cff5  cmp     [rax+7CCh], edi
0x18021cffb  jz      short loc_18021D00E
0x18021cffd  mov     r9d, edi
0x18021d000  mov     r8d, esi
0x18021d003  mov     rdx, r14
0x18021d006  mov     rcx, rax
0x18021d009  call    sub_1800EC0E0
0x18021d00e  mov     esi, 1
0x18021d013  cmp     cs:byte_1803CECE8, sil
0x18021d01a  jb      loc_18021D947
0x18021d020  lea     edx, [rsi+48h]
0x18021d023  jmp     loc_18021D929
0x18021d028  movzx   ecx, word ptr [rdx]
0x18021d02b  mov     r9d, 0FFFh
0x18021d031  cmp     r12w, cx
0x18021d035  jz      loc_18021D10B
0x18021d03b  movzx   edx, word ptr [r15]
0x18021d03f  cmp     r12w, dx
0x18021d043  jz      loc_18021D10B
0x18021d049  xor     dx, cx
0x18021d04c  test    r9w, dx
0x18021d050  jz      loc_18021D10B
0x18021d056  mov     esi, 490h
0x18021d05b  lea     r14, aCmfpropvariant_10; "CMFPropVariantConvert::Concatenate"
0x18021d062  mov     r8d, esi
0x18021d065  lea     rcx, [rbp+57h+arg_0]
0x18021d069  mov     rdx, r14
0x18021d06c  call    sub_18002FEE0
0x18021d071  mov     rbx, cs:qword_1803CEF18
0x18021d078  mov     edi, 0C00D36E7h
0x18021d07d  test    rbx, rbx
0x18021d080  jnz     short loc_18021D0CA
0x18021d082  call    cs:MFGetCallStackTracingWeakReference
0x18021d089  nop     dword ptr [rax+rax+00h]
0x18021d08e  mov     cs:qword_1803CEF18, rax
0x18021d095  mov     rcx, rax
0x18021d098  test    rax, rax
0x18021d09b  jz      short loc_18021D0BC
0x18021d09d  mov     rax, [rax]
0x18021d0a0  mov     edx, 7F0h
0x18021d0a5  mov     rax, [rax+8]
0x18021d0a9  call    cs:__guard_dispatch_icall_fptr
0x18021d0af  test    eax, eax
0x18021d0b1  jz      short loc_18021D0BC
0x18021d0b3  mov     rbx, cs:qword_1803CEF18
0x18021d0ba  jmp     short loc_18021D0CA
0x18021d0bc  lea     rbx, qword_1803CE250
0x18021d0c3  mov     cs:qword_1803CEF18, rbx
0x18021d0ca  cmp     [rbx+8], r12b
0x18021d0ce  jz      short loc_18021D0F1
0x18021d0d0  mov     rcx, rbx
0x18021d0d3  call    sub_1800402C0
0x18021d0d8  cmp     [rax+7CCh], edi
0x18021d0de  jz      short loc_18021D0F1
0x18021d0e0  mov     r9d, edi
0x18021d0e3  mov     r8d, esi
0x18021d0e6  mov     rdx, r14
0x18021d0e9  mov     rcx, rax
0x18021d0ec  call    sub_1800EC0E0
0x18021d0f1  mov     esi, 1
0x18021d0f6  cmp     cs:byte_1803CECE8, sil
0x18021d0fd  jb      loc_18021D947
0x18021d103  lea     edx, [rsi+49h]
0x18021d106  jmp     loc_18021D929
0x18021d10b  movzx   edx, word ptr [r15]
0x18021d10f  mov     r8d, 0Eh
0x18021d115  movzx   eax, dx
0x18021d118  and     ax, r9w
0x18021d11c  cmp     r8w, ax
0x18021d120  jz      loc_18021D87D
0x18021d126  movzx   eax, cx
0x18021d129  and     ax, r9w
0x18021d12d  cmp     r8w, ax
0x18021d131  jz      loc_18021D87D
0x18021d137  lea     esi, [r8-0Dh]
0x18021d13b  mov     r8d, 1000h
0x18021d141  cmp     r12w, dx
0x18021d145  jnz     short loc_18021D14C
0x18021d147  mov     ebx, r12d
0x18021d14a  jmp     short loc_18021D15C
0x18021d14c  and     dx, r8w
0x18021d150  mov     ebx, esi
0x18021d152  cmp     r12w, dx
0x18021d156  jz      short loc_18021D15C
0x18021d158  mov     ebx, [r15+8]
0x18021d15c  cmp     r12w, cx
0x18021d160  jnz     short loc_18021D16A
0x18021d162  mov     edi, r12d
0x18021d165  jmp     loc_18021D950
0x18021d16a  and     cx, r8w
0x18021d16e  xor     eax, eax
0x18021d170  mov     r12d, esi
0x18021d173  cmp     ax, cx
0x18021d176  jz      short loc_18021D17C
0x18021d178  mov     r12d, [r13+8]
0x18021d17c  lea     rdx, [rbp+57h+arg_10]
0x18021d180  mov     rcx, r15
0x18021d183  call    sub_1801C1658
0x18021d188  lea     r14, aCmfpropvariant_10; "CMFPropVariantConvert::Concatenate"
0x18021d18f  mov     r8d, 4BAh
0x18021d195  mov     rdx, r14
0x18021d198  lea     rcx, [rbp+57h+cb]
0x18021d19c  mov     edi, eax
0x18021d19e  call    sub_18002FEE0
0x18021d1a3  xor     r9d, r9d
0x18021d1a6  test    edi, edi
0x18021d1a8  jns     loc_18021D267
0x18021d1ae  mov     rbx, cs:qword_1803CEF18
0x18021d1b5  test    rbx, rbx
0x18021d1b8  jnz     short loc_18021D208
0x18021d1ba  call    cs:MFGetCallStackTracingWeakReference
0x18021d1c1  nop     dword ptr [rax+rax+00h]
0x18021d1c6  xor     r9d, r9d
0x18021d1c9  mov     cs:qword_1803CEF18, rax
0x18021d1d0  mov     rcx, rax
0x18021d1d3  test    rax, rax
0x18021d1d6  jz      short loc_18021D1FA
0x18021d1d8  mov     rax, [rax]
0x18021d1db  mov     edx, 7F0h
0x18021d1e0  mov     rax, [rax+8]
0x18021d1e4  call    cs:__guard_dispatch_icall_fptr
0x18021d1ea  xor     r9d, r9d
0x18021d1ed  test    eax, eax
0x18021d1ef  jz      short loc_18021D1FA
0x18021d1f1  mov     rbx, cs:qword_1803CEF18
0x18021d1f8  jmp     short loc_18021D208
0x18021d1fa  lea     rbx, qword_1803CE250
0x18021d201  mov     cs:qword_1803CEF18, rbx
0x18021d208  cmp     [rbx+8], r9b
0x18021d20c  jz      short loc_18021D232
0x18021d20e  mov     rcx, rbx
0x18021d211  call    sub_1800402C0
0x18021d216  cmp     [rax+7CCh], edi
0x18021d21c  jz      short loc_18021D232
0x18021d21e  mov     r9d, edi
0x18021d221  mov     r8d, 4BAh
0x18021d227  mov     rdx, r14
0x18021d22a  mov     rcx, rax
0x18021d22d  call    sub_1800EC0E0
0x18021d232  cmp     cs:byte_1803CECE8, sil
0x18021d239  jb      short loc_18021D25E
0x18021d23b  mov     edx, 4Ch ; 'L'
0x18021d240  mov     [rsp+0C0h+var_A0], edi
0x18021d244  mov     rcx, cs:RequestContext
0x18021d24b  lea     r8, qword_18035FAF0
0x18021d252  xor     r9d, r9d
0x18021d255  mov     rcx, [rcx+10h]
0x18021d259  call    sub_180050D6C
0x18021d25e  lea     rcx, [rbp+57h+cb]
0x18021d262  jmp     loc_18021D94B
0x18021d267  test    ebx, ebx
0x18021d269  jnz     short loc_18021D2CC
0x18021d26b  cmp     r12d, esi
0x18021d26e  jnz     short loc_18021D2CC
0x18021d270  movzx   edx, word ptr [r13+0]
0x18021d275  mov     r8d, 1000h
0x18021d27b  movzx   ecx, dx
0x18021d27e  and     cx, r8w
0x18021d282  cmp     r9w, cx
0x18021d286  jz      short loc_18021D2BD
0x18021d288  lea     eax, [r8-1]
0x18021d28c  and     dx, ax
0x18021d28f  cmp     dx, 1Fh
0x18021d293  ja      short loc_18021D2A1
0x18021d295  mov     r8d, 0C0002300h
0x18021d29b  bt      r8d, edx
0x18021d29f  jb      short loc_18021D2A4
0x18021d2a1  mov     esi, r9d
0x18021d2a4  mov     r8, [r13+10h]
0x18021d2a8  mov     rcx, r15; pvar
0x18021d2ab  mov     r9d, [rbp+57h+arg_10]
0x18021d2af  test    esi, esi
0x18021d2b1  jz      short loc_18021D2B6
0x18021d2b3  mov     r8, [r8]
0x18021d2b6  call    sub_1801DAE40
0x18021d2bb  jmp     short loc_18021D2C8
0x18021d2bd  mov     rdx, r13; pvarSrc
0x18021d2c0  mov     rcx, r15; pvarDest
0x18021d2c3  call    sub_18019D300
0x18021d2c8  mov     edi, eax
0x18021d2ca  jmp     short loc_18021D25E
0x18021d2cc  lea     eax, [r12+rbx]
0x18021d2d0  mov     [rbp+57h+var_8C], eax
0x18021d2d3  cmp     eax, ebx
0x18021d2d5  jb      loc_18021D7DD
0x18021d2db  mov     edx, [rbp+57h+arg_10]
0x18021d2de  mov     ecx, eax
0x18021d2e0  imul    rcx, rdx
0x18021d2e4  lea     rdx, [rbp+57h+cb]
0x18021d2e8  mov     dword ptr [rbp+57h+cb], eax
0x18021d2eb  call    sub_180111D68
0x18021d2f0  mov     edi, eax
0x18021d2f2  test    eax, eax
0x18021d2f4  jns     loc_18021D395
0x18021d2fa  mov     rbx, cs:qword_1803CEF18
0x18021d301  test    rbx, rbx
0x18021d304  jnz     short loc_18021D354
0x18021d306  call    cs:MFGetCallStackTracingWeakReference
0x18021d30d  nop     dword ptr [rax+rax+00h]
0x18021d312  xor     r9d, r9d
0x18021d315  mov     cs:qword_1803CEF18, rax
0x18021d31c  mov     rcx, rax
0x18021d31f  test    rax, rax
0x18021d322  jz      short loc_18021D346
0x18021d324  mov     rax, [rax]
0x18021d327  mov     edx, 7F0h
0x18021d32c  mov     rax, [rax+8]
0x18021d330  call    cs:__guard_dispatch_icall_fptr
0x18021d336  xor     r9d, r9d
0x18021d339  test    eax, eax
0x18021d33b  jz      short loc_18021D346
0x18021d33d  mov     rbx, cs:qword_1803CEF18
0x18021d344  jmp     short loc_18021D354
0x18021d346  lea     rbx, qword_1803CE250
0x18021d34d  mov     cs:qword_1803CEF18, rbx
0x18021d354  cmp     [rbx+8], r9b
0x18021d358  jz      short loc_18021D37E
0x18021d35a  mov     rcx, rbx
0x18021d35d  call    sub_1800402C0
0x18021d362  cmp     [rax+7CCh], edi
0x18021d368  jz      short loc_18021D37E
0x18021d36a  mov     r9d, edi
0x18021d36d  mov     r8d, 4F0h
0x18021d373  mov     rdx, r14
0x18021d376  mov     rcx, rax
0x18021d379  call    sub_1800EC0E0
0x18021d37e  cmp     cs:byte_1803CECE8, sil
0x18021d385  jb      loc_18021D25E
0x18021d38b  mov     edx, 4Eh ; 'N'
0x18021d390  jmp     loc_18021D240
0x18021d395  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x18021d398  call    cs:CoTaskMemAlloc
0x18021d39f  nop     dword ptr [rax+rax+00h]
0x18021d3a4  xor     r11d, r11d
0x18021d3a7  mov     [rbp+57h+var_70], rax
0x18021d3ab  mov     r10, rax
0x18021d3ae  test    rax, rax
0x18021d3b1  jnz     loc_18021D461
0x18021d3b7  mov     rbx, cs:qword_1803CEF18
0x18021d3be  mov     r12d, 8007000Eh
0x18021d3c4  mov     edi, r12d
0x18021d3c7  test    rbx, rbx
0x18021d3ca  jnz     short loc_18021D41A
0x18021d3cc  call    cs:MFGetCallStackTracingWeakReference
0x18021d3d3  nop     dword ptr [rax+rax+00h]
0x18021d3d8  xor     r11d, r11d
0x18021d3db  mov     cs:qword_1803CEF18, rax
0x18021d3e2  mov     rcx, rax
0x18021d3e5  test    rax, rax
0x18021d3e8  jz      short loc_18021D40C
0x18021d3ea  mov     rax, [rax]
0x18021d3ed  mov     edx, 7F0h
0x18021d3f2  mov     rax, [rax+8]
  ... truncated ...
```
