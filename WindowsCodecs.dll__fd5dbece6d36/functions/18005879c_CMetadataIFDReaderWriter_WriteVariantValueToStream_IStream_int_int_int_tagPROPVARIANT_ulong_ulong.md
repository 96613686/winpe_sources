# CMetadataIFDReaderWriter::WriteVariantValueToStream(IStream *,int,int,int,tagPROPVARIANT *,ulong,ulong *)

- ea: `0x18005879c`
- end: `0x180059033`
- name: `?WriteVariantValueToStream@CMetadataIFDReaderWriter@@IEAAJPEAUIStream@@HHHPEAUtagPROPVARIANT@@KPEAK@Z`
- size: `2199`
- prototype: `int(CMetadataIFDReaderWriter *__hidden this, struct IStream *, int, int, int, struct tagPROPVARIANT *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x1800573d0`
- `0x1800bab80`

## callees

- `0x180020e7c`
- `0x180025d00`
- `0x180035678`
- `0x180041898`
- `0x1800545f4`
- `0x1800554f0`
- `0x180056d64`
- `0x18005879c`
- `0x18009abd4`
- `0x1800b4bf4`
- `0x1800bb784`
- `0x1800e2f90`
- `0x1801a94cc`
- `0x1801ca010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058f35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058eab`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180058f35`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059004`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180059004`

## pseudocode

```c
__int64 __fastcall CMetadataIFDReaderWriter::WriteVariantValueToStream(
        CMetadataIFDReaderWriter *this,
        struct IStream *a2,
        int a3,
        __int64 a4,
        int a5,
        struct tagPROPVARIANT *a6,
        unsigned int cb,
        unsigned int *a8)
{
  unsigned int *v8; // rbx
  ULONG v9; // r13d
  VARTYPE vt; // ax
  unsigned __int16 v12; // ax
  unsigned __int8 *pData; // rsi
  BOOL v14; // r14d
  __int64 v15; // rcx
  int PaddingSizeForEmbeddedHandler; // eax
  unsigned int v17; // edi
  bool v18; // zf
  int v19; // ecx
  unsigned int ulVal; // r14d
  ULONG v21; // ebx
  unsigned int v22; // eax
  bool v23; // zf
  HRESULT v24; // eax
  int v25; // r9d
  unsigned int v26; // r10d
  bool v27; // zf
  int v28; // ecx
  int v29; // r10d
  __int64 i; // rax
  __int64 (__fastcall ***v31)(_QWORD, GUID *, __int64 *); // rcx
  int v32; // r9d
  ULONG v33; // edx
  __int64 v34; // r8
  int v35; // r10d
  bool v36; // zf
  LONG lVal; // r9d
  int v38; // edx
  int v39; // eax
  BYTE *v40; // rdx
  CMetadataIFDReaderWriter *v41; // rcx
  unsigned __int8 *v42; // rax
  unsigned __int8 *v43; // rdx
  _BYTE v45[4]; // [rsp+30h] [rbp-A9h] BYREF
  ULONG v46; // [rsp+34h] [rbp-A5h] BYREF
  unsigned int v47[2]; // [rsp+38h] [rbp-A1h] BYREF
  int v48; // [rsp+40h] [rbp-99h] BYREF
  ULONG pulResult; // [rsp+44h] [rbp-95h] BYREF
  __int64 v50; // [rsp+48h] [rbp-91h] BYREF
  ULONGLONG ullOperand; // [rsp+50h] [rbp-89h] BYREF
  ULONGLONG ullMinuend; // [rsp+58h] [rbp-81h] BYREF
  void *v53; // [rsp+60h] [rbp-79h]
  ULONG v54; // [rsp+68h] [rbp-71h] BYREF
  unsigned int *v55; // [rsp+70h] [rbp-69h]
  unsigned int v56; // [rsp+78h] [rbp-61h]
  int v57; // [rsp+7Ch] [rbp-5Dh]
  ULONGLONG pullResult; // [rsp+80h] [rbp-59h] BYREF
  unsigned __int64 v59; // [rsp+88h] [rbp-51h] BYREF
  __int64 v60; // [rsp+90h] [rbp-49h]
  _BYTE v61[32]; // [rsp+98h] [rbp-41h] BYREF
  _BYTE v62[24]; // [rsp+B8h] [rbp-21h] BYREF

  v8 = a8;
  LOBYTE(v9) = cb;
  v53 = this;
  vt = a6->vt;
  v57 = a3;
  v12 = vt & 0xFFF;
  v55 = a8;
  v50 = 0;
  pData = 0;
  v14 = a3 != 0;
  ullOperand = 0;
  v47[0] = v14;
  ullMinuend = 0;
  v59 = 0;
  pullResult = 0;
  v48 = 0;
  if ( v12 > 0x1Eu )
  {
    if ( v12 != 65 )
      goto LABEL_126;
    if ( !a6->lVal )
    {
      ulVal = 0;
LABEL_136:
      v17 = 0;
      goto LABEL_137;
    }
    pData = a6->bstrblobVal.pData;
    if ( a5 )
    {
      v42 = (unsigned __int8 *)CoTaskMemAlloc(a6->ulVal);
      pData = v42;
      if ( !v42 )
        goto LABEL_119;
      v43 = a6->bstrblobVal.pData;
      v48 = 1;
      CopyCommentWithEndiannessSwap(v42, v43, cb);
    }
    v40 = pData;
    goto LABEL_132;
  }
  if ( v12 == 30 )
  {
    v47[0] = 0;
    pData = (unsigned __int8 *)CoTaskMemAlloc(cb);
    if ( pData )
    {
      v48 = 1;
      PaddingSizeForEmbeddedHandler = CMetadataIFDReaderWriter::WriteAsciiVariantToBuffer(v41, a6, pData, cb, v47);
      v17 = PaddingSizeForEmbeddedHandler;
      if ( PaddingSizeForEmbeddedHandler < 0 )
      {
        v18 = (_DWORD)g_doStackCaptures == 0;
LABEL_13:
        if ( v18 )
          goto LABEL_143;
        goto LABEL_14;
      }
      goto LABEL_111;
    }
LABEL_119:
    v23 = (_DWORD)g_doStackCaptures == 0;
    v17 = -2147024882;
    goto LABEL_120;
  }
  if ( v12 > 0x10u )
  {
    if ( v12 != 17 )
    {
      v15 = (unsigned int)v12 - 18;
      if ( v12 != 18 )
      {
        v15 = (unsigned int)v12 - 19;
        if ( v12 != 19 )
        {
          v15 = (unsigned int)v12 - 20;
          if ( (unsigned int)v15 > 1 )
            goto LABEL_126;
          goto LABEL_94;
        }
        goto LABEL_104;
      }
LABEL_106:
      pData = a6->bstrblobVal.pData;
      *(_QWORD *)v47 = pData;
      if ( !a3 )
        goto LABEL_111;
      v38 = 3;
      goto LABEL_108;
    }
    goto LABEL_115;
  }
  if ( v12 == 16 )
  {
LABEL_115:
    v40 = a6->bstrblobVal.pData;
LABEL_132:
    PaddingSizeForEmbeddedHandler = WriteFullBufferToStream(a2, v40, a6->ulVal);
    v17 = PaddingSizeForEmbeddedHandler;
    if ( PaddingSizeForEmbeddedHandler >= 0 )
    {
      ulVal = a6->ulVal;
      goto LABEL_137;
    }
    if ( (_DWORD)g_doStackCaptures )
      goto LABEL_14;
    goto LABEL_143;
  }
  v15 = (unsigned int)v12 - 2;
  if ( v12 == 2 )
    goto LABEL_106;
  v15 = (unsigned int)v12 - 3;
  if ( v12 == 3 || (v15 = (unsigned int)v12 - 4, v12 == 4) )
  {
LABEL_104:
    pData = a6->bstrblobVal.pData;
    *(_QWORD *)v47 = pData;
    if ( !a3 )
      goto LABEL_111;
    v38 = 4;
LABEL_108:
    lVal = a6->lVal;
LABEL_109:
    v39 = CMetadataIFDReaderWriter::SwapByteOrder(v15, v38, (void **)v47, lVal, 0, &v48);
    v17 = v39;
    if ( v39 < 0 )
    {
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v39);
      pData = *(unsigned __int8 **)v47;
      goto LABEL_143;
    }
    pData = *(unsigned __int8 **)v47;
    goto LABEL_111;
  }
  v15 = (unsigned int)v12 - 5;
  if ( v12 != 5 )
  {
    if ( v12 != 12 )
    {
      if ( v12 == 13 )
      {
        PaddingSizeForEmbeddedHandler = (**(__int64 (__fastcall ***)(LARGE_INTEGER, GUID *, __int64 *))a6->hVal.QuadPart)(
                                          a6->hVal,
                                          &IID_IWICPersistStream,
                                          &v50);
        v17 = PaddingSizeForEmbeddedHandler;
        if ( PaddingSizeForEmbeddedHandler < 0 )
        {
          v18 = (_DWORD)g_doStackCaptures == 0;
          goto LABEL_13;
        }
        if ( v55
          && (PaddingSizeForEmbeddedHandler = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONGLONG *))(*(_QWORD *)a2 + 40LL))(
                                                a2,
                                                0,
                                                1,
                                                &ullOperand),
              v17 = PaddingSizeForEmbeddedHandler,
              PaddingSizeForEmbeddedHandler < 0)
          || (PaddingSizeForEmbeddedHandler = (*(__int64 (__fastcall **)(__int64, struct IStream *, BOOL, _QWORD))(*(_QWORD *)v50 + 72LL))(
                                                v50,
                                                a2,
                                                v14,
                                                0),
              v17 = PaddingSizeForEmbeddedHandler,
              PaddingSizeForEmbeddedHandler < 0) )
        {
          v18 = (_DWORD)g_doStackCaptures == 0;
          goto LABEL_13;
        }
        PaddingSizeForEmbeddedHandler = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONGLONG *))(*(_QWORD *)a2 + 40LL))(
                                          a2,
                                          0,
                                          1,
                                          &ullMinuend);
        v17 = PaddingSizeForEmbeddedHandler;
        if ( PaddingSizeForEmbeddedHandler < 0 )
        {
          v18 = (_DWORD)g_doStackCaptures == 0;
          goto LABEL_13;
        }
        if ( ullMinuend < ullOperand || (ulVal = ullMinuend - ullOperand, ullMinuend - ullOperand > 0xFFFFFFFF) )
        {
          v23 = (_DWORD)g_doStackCaptures == 0;
          v17 = -2147024362;
          goto LABEL_120;
        }
        v46 = 0;
        PaddingSizeForEmbeddedHandler = GetPaddingSizeForEmbeddedHandler(
                                          *((const struct _GUID **)v53 + 19),
                                          a6,
                                          ulVal,
                                          &v46);
        v17 = PaddingSizeForEmbeddedHandler;
        if ( PaddingSizeForEmbeddedHandler < 0 )
        {
          if ( !(_DWORD)g_doStackCaptures )
            goto LABEL_143;
LABEL_14:
          v19 = PaddingSizeForEmbeddedHandler;
LABEL_122:
          DoStackCapture(v19);
          goto LABEL_143;
        }
        v21 = v46;
        if ( v46 )
        {
          PaddingSizeForEmbeddedHandler = WriteFullBufferToStream(a2, &qword_1801F2118, v46);
          v17 = PaddingSizeForEmbeddedHandler;
          if ( PaddingSizeForEmbeddedHandler < 0 )
          {
LABEL_28:
            v18 = (_DWORD)g_doStackCaptures == 0;
            goto LABEL_13;
          }
          v22 = v21 + ulVal;
          if ( v21 + ulVal < ulVal )
          {
LABEL_31:
            v17 = -2147024362;
LABEL_32:
            v23 = (_DWORD)g_doStackCaptures == 0;
LABEL_120:
            if ( v23 )
              goto LABEL_143;
            v19 = v17;
            goto LABEL_122;
          }
          v8 = v55;
          ulVal = v22;
          goto LABEL_136;
        }
        v8 = v55;
LABEL_137:
        if ( (v9 & 1) == 0 )
          goto LABEL_141;
        v45[0] = 0;
        PaddingSizeForEmbeddedHandler = WriteFullBufferToStream(a2, v45, 1u);
        v17 = PaddingSizeForEmbeddedHandler;
        if ( PaddingSizeForEmbeddedHandler < 0 )
          goto LABEL_28;
        if ( ulVal + 1 >= ulVal )
        {
          ++ulVal;
          v17 = 0;
LABEL_141:
          if ( v8 )
            *v8 = ulVal;
          goto LABEL_143;
        }
        goto LABEL_31;
      }
LABEL_126:
      v17 = -2147024809;
      goto LABEL_32;
    }
    v54 = 0;
    DynArrayImpl<1>::DynArrayImpl<1>(v61, v62, 5);
    v56 = a6->ulVal;
    v53 = 0;
    v46 = 0;
    pulResult = 0;
    v24 = ULongLongToULong(4LL * v56, &pulResult);
    v17 = v24;
    if ( v24 >= 0 )
    {
      v24 = DynArrayImpl<1>::AddMultiple(v61, 4, v26);
      v17 = v24;
      if ( v24 >= 0 )
      {
        v24 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, unsigned __int64 *))(*(_QWORD *)a2 + 40LL))(
                a2,
                0,
                1,
                &v59);
        v17 = v24;
        if ( v24 >= 0 )
        {
          v9 = pulResult;
          v24 = WriteFullBufferToStream(a2, v53, pulResult);
          v17 = v24;
          if ( v24 >= 0 )
          {
            v29 = (int)g_doStackCaptures;
            ulVal = v9;
            for ( i = 0; ; i = pulResult + 1 )
            {
              pulResult = i;
              if ( (unsigned int)i >= v56 )
                break;
              v60 = i;
              v31 = *(__int64 (__fastcall ****)(_QWORD, GUID *, __int64 *))&a6->bstrblobVal.pData[24 * i + 8];
              v24 = (**v31)(v31, &IID_IWICPersistStream, &v50);
              v17 = v24;
              if ( v24 < 0 )
              {
                if ( (_DWORD)g_doStackCaptures )
                  goto LABEL_38;
                goto LABEL_40;
              }
              v24 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONGLONG *))(*(_QWORD *)a2 + 40LL))(
                      a2,
                      0,
                      1,
                      &ullOperand);
              v17 = v24;
              if ( v24 < 0 )
              {
                if ( (_DWORD)g_doStackCaptures )
                  goto LABEL_38;
                goto LABEL_40;
              }
              v24 = ULongLongToULong(ullOperand, &v46);
              v17 = v24;
              if ( v24 < 0 )
              {
                if ( v32 )
                  goto LABEL_38;
                goto LABEL_40;
              }
              if ( v57 )
              {
                v33 = ((v46 & 0xFF00 | (v46 << 16)) << 8) | ((HIWORD(v46) | v46 & 0xFF0000) >> 8);
                v46 = v33;
              }
              else
              {
                v33 = v46;
              }
              v34 = v47[0];
              *((_DWORD *)v53 + v60) = v33;
              v24 = (*(__int64 (__fastcall **)(__int64, struct IStream *, __int64, _QWORD))(*(_QWORD *)v50 + 72LL))(
                      v50,
                      a2,
                      v34,
                      0);
              v17 = v24;
              if ( v24 < 0 )
              {
                if ( (_DWORD)g_doStackCaptures )
                  goto LABEL_38;
                goto LABEL_40;
              }
              v24 = (*(__int64 (__fastcall **)(struct IStream *, _QWORD, __int64, ULONGLONG *))(*(_QWORD *)a2 + 40LL))(
                      a2,
                      0,
                      1,
                      &ullMinuend);
              v29 = (int)g_doStackCaptures;
              v17 = v24;
              if ( v24 < 0 )
              {
                if ( (_DWORD)g_doStackCaptures )
                  goto LABEL_38;
                goto LABEL_40;
              }
              if ( v55 )
              {
                v24 = ULongLongSub(ullMinuend, ullOperand, &pullResult);
                v17 = v24;
                if ( v24 < 0 )
                {
                  if ( v35 )
                    goto LABEL_38;
                  goto LABEL_40;
                }
                v24 = ULongLongToULong(pullResult, &v54);
                v17 = v24;
                if ( v24 < 0 )
                {
                  if ( v29 )
                    goto LABEL_38;
                  goto LABEL_40;
                }
                if ( ulVal + v54 < ulVal )
                  goto LABEL_78;
                ulVal += v54;
              }
              if ( v50 )
              {
                (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
                v29 = (int)g_doStackCaptures;
                v50 = 0;
              }
            }
            if ( v59 > 0x7FFFFFFFFFFFFFFFLL )
            {
LABEL_78:
              v36 = v29 == 0;
            }
            else
            {
              v24 = (*(__int64 (__fastcall **)(struct IStream *, unsigned __int64, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(
                      a2,
                      v59,
                      0,
                      0);
              v17 = v24;
              if ( v24 < 0 )
                goto LABEL_42;
              v24 = WriteFullBufferToStream(a2, v53, v9);
              v17 = v24;
              if ( v24 < 0 )
                goto LABEL_42;
              if ( ullMinuend <= 0x7FFFFFFFFFFFFFFFLL )
              {
                v24 = (*(__int64 (__fastcall **)(struct IStream *, ULONGLONG, _QWORD, _QWORD))(*(_QWORD *)a2 + 40LL))(
                        a2,
                        ullMinuend,
                        0,
                        0);
                v17 = v24;
                if ( v24 >= 0 )
                {
                  DynArrayImpl<1>::~DynArrayImpl<1>(v61);
                  v8 = v55;
                  goto LABEL_137;
                }
                if ( (_DWORD)g_doStackCaptures )
                  goto LABEL_38;
LABEL_40:
                DynArrayImpl<1>::~DynArrayImpl<1>(v61);
                goto LABEL_143;
              }
              v36 = (_DWORD)g_doStackCaptures == 0;
            }
            v17 = -2147024362;
            if ( v36 )
              goto LABEL_40;
            v28 = -2147024362;
            goto LABEL_39;
          }
        }
        v27 = (_DWORD)g_doStackCaptures == 0;
      }
      else
      {
LABEL_42:
        v27 = (_DWORD)g_doStackCaptures == 0;
      }
    }
    else
    {
      v27 = (_DWORD)g_doStackCaptures == v25;
    }
    if ( !v27 )
    {
LABEL_38:
      v28 = v24;
LABEL_39:
      DoStackCapture(v28);
    }
    goto LABEL_40;
  }
LABEL_94:
  pData = &a6->bVal;
  if ( (a6->vt & 0x1000) != 0 )
  {
    lVal = *(_DWORD *)pData;
    pData = a6->bstrblobVal.pData;
  }
  else
  {
    lVal = 1;
  }
  *(_QWORD *)v47 = pData;
  if ( a3 )
  {
    v38 = 12;
    if ( v12 != 5 )
      v38 = 5;
    goto LABEL_109;
  }
LABEL_111:
  PaddingSizeForEmbeddedHandler = WriteFullBufferToStream(a2, pData, cb);
  v17 = PaddingSizeForEmbeddedHandler;
  if ( PaddingSizeForEmbeddedHandler >= 0 )
  {
    ulVal = cb;
    goto LABEL_137;
  }
  if ( (_DWORD)g_doStackCaptures )
    goto LABEL_14;
LABEL_143:
  if ( v50 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v50 + 16LL))(v50);
    v50 = 0;
  }
  if ( v48 && pData )
    CoTaskMemFree(pData);
  return v17;
}

```

## disassembly

```asm
0x18005879c  mov     [rsp-8+arg_10], rbx
0x1800587a1  push    rbp
0x1800587a2  push    rsi
0x1800587a3  push    rdi
0x1800587a4  push    r12
0x1800587a6  push    r13
0x1800587a8  push    r14
0x1800587aa  push    r15
0x1800587ac  lea     rbp, [rsp-7]
0x1800587b1  sub     rsp, 0E0h
0x1800587b8  mov     rax, cs:__security_cookie
0x1800587bf  xor     rax, rsp
0x1800587c2  mov     [rbp+37h+var_40], rax
0x1800587c6  mov     r12, [rbp+37h+arg_28]
0x1800587ca  xor     r11d, r11d
0x1800587cd  mov     rbx, [rbp+37h+arg_38]
0x1800587d1  mov     r10d, r8d
0x1800587d4  mov     r13d, dword ptr [rbp+37h+cb]
0x1800587d8  mov     r14d, r11d
0x1800587db  mov     [rbp+37h+var_B0], rcx
0x1800587df  mov     r15, rdx
0x1800587e2  movzx   eax, word ptr [r12]
0x1800587e7  lea     edi, [r11+1]
0x1800587eb  mov     ecx, 0FFFh
0x1800587f0  mov     [rbp+37h+var_94], r8d
0x1800587f4  and     ax, cx
0x1800587f7  mov     [rbp+37h+var_A0], rbx
0x1800587fb  test    r10d, r10d
0x1800587fe  movzx   r8d, ax
0x180058802  mov     [rsp+110h+var_C8], r11
0x180058807  mov     esi, r11d
0x18005880a  setnz   r14b
0x18005880e  mov     [rsp+110h+ullOperand], r11
0x180058813  mov     [rsp+110h+var_D8], r14d
0x180058818  mov     [rsp+110h+ullMinuend], r11
0x18005881d  mov     [rbp+37h+var_88], r11
0x180058821  mov     [rbp+37h+pullResult], r11
0x180058825  mov     [rsp+110h+var_D0], r11d
0x18005882a  cmp     r8d, 1Eh
0x18005882e  ja      loc_180058F09
0x180058834  jz      loc_180058EA3
0x18005883a  cmp     r8d, 10h
0x18005883e  ja      loc_180058D8E
0x180058844  jz      loc_180058E87
0x18005884a  mov     ecx, r8d
0x18005884d  sub     ecx, 2
0x180058850  jz      loc_180058E16
0x180058856  sub     ecx, edi
0x180058858  jz      loc_180058E00
0x18005885e  sub     ecx, edi
0x180058860  jz      loc_180058E00
0x180058866  sub     ecx, edi
0x180058868  jz      loc_180058DAE
0x18005886e  sub     ecx, 7
0x180058871  jz      loc_180058A02
0x180058877  cmp     ecx, edi
0x180058879  jnz     loc_180058F0F
0x18005887f  mov     rcx, [r12+8]
0x180058884  lea     r8, [rsp+110h+var_C8]
0x180058889  lea     rdx, IID_IWICPersistStream
0x180058890  mov     rax, [rcx]
0x180058893  mov     rax, [rax]
0x180058896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005889b  mov     edi, eax
0x18005889d  test    eax, eax
0x18005889f  jns     short loc_1800588B4
0x1800588a1  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800588a7  jz      loc_180058FD6
0x1800588ad  mov     ecx, eax
0x1800588af  jmp     loc_180058ECD
0x1800588b4  xor     ebx, ebx
0x1800588b6  cmp     [rbp+37h+var_A0], rbx
0x1800588ba  jz      short loc_1800588E4
0x1800588bc  mov     rax, [r15]
0x1800588bf  lea     r9, [rsp+110h+ullOperand]
0x1800588c4  lea     r8d, [rbx+1]
0x1800588c8  mov     edx, ebx
0x1800588ca  mov     rcx, r15
0x1800588cd  mov     rax, [rax+28h]
0x1800588d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588d6  mov     edi, eax
0x1800588d8  test    eax, eax
0x1800588da  jns     short loc_1800588E4
0x1800588dc  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x1800588e2  jmp     short loc_1800588A7
0x1800588e4  mov     rcx, [rsp+110h+var_C8]
0x1800588e9  xor     r9d, r9d
0x1800588ec  mov     r8d, r14d
0x1800588ef  mov     rdx, r15
0x1800588f2  mov     rax, [rcx]
0x1800588f5  mov     rax, [rax+48h]
0x1800588f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800588fe  mov     edi, eax
0x180058900  test    eax, eax
0x180058902  js      short loc_1800588DC
0x180058904  mov     rax, [r15]
0x180058907  lea     r9, [rsp+110h+ullMinuend]
0x18005890c  mov     r8d, 1
0x180058912  mov     rdx, rbx
0x180058915  mov     rcx, r15
0x180058918  mov     rax, [rax+28h]
0x18005891c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058921  xor     ecx, ecx
0x180058923  mov     edi, eax
0x180058925  test    eax, eax
0x180058927  jns     short loc_180058934
0x180058929  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x18005892f  jmp     loc_1800588A7
0x180058934  mov     r14, [rsp+110h+ullMinuend]
0x180058939  cmp     r14, [rsp+110h+ullOperand]
0x18005893e  jb      loc_1800589F2
0x180058944  sub     r14, [rsp+110h+ullOperand]
0x180058949  mov     eax, 0FFFFFFFFh
0x18005894e  cmp     r14, rax
0x180058951  ja      loc_1800589F2
0x180058957  mov     [rsp+110h+var_DC], ecx
0x18005895b  lea     r9, [rsp+110h+var_DC]; unsigned int *
0x180058960  mov     rcx, [rbp+37h+var_B0]
0x180058964  mov     r8d, r14d; unsigned int
0x180058967  mov     rdx, r12; struct tagPROPVARIANT *
0x18005896a  mov     rcx, [rcx+98h]; struct _GUID *
0x180058971  call    ?GetPaddingSizeForEmbeddedHandler@@YAJPEBU_GUID@@PEBUtagPROPVARIANT@@IPEAI@Z; GetPaddingSizeForEmbeddedHandler(_GUID const *,tagPROPVARIANT const *,uint,uint *)
0x180058976  xor     r11d, r11d
0x180058979  mov     edi, eax
0x18005897b  test    eax, eax
0x18005897d  jns     short loc_180058994
0x18005897f  cmp     cs:?g_doStackCaptures@@3HA, r11d; int g_doStackCaptures
0x180058986  jnz     loc_1800588AD
0x18005898c  test    eax, eax
0x18005898e  js      loc_180058FD6
0x180058994  mov     ebx, [rsp+110h+var_DC]
0x180058998  test    ebx, ebx
0x18005899a  jz      short loc_1800589E9
0x18005899c  mov     r8d, ebx; unsigned int
0x18005899f  lea     rdx, qword_1801F2118; void *
0x1800589a6  mov     rcx, r15; struct IStream *
0x1800589a9  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800589ae  xor     r11d, r11d
0x1800589b1  mov     edi, eax
0x1800589b3  test    eax, eax
0x1800589b5  jns     short loc_1800589C3
0x1800589b7  cmp     cs:?g_doStackCaptures@@3HA, r11d; int g_doStackCaptures
0x1800589be  jmp     loc_1800588A7
0x1800589c3  lea     eax, [rbx+r14]
0x1800589c7  cmp     eax, r14d
0x1800589ca  jb      short loc_1800589D8
0x1800589cc  mov     rbx, [rbp+37h+var_A0]
0x1800589d0  mov     r14d, eax
0x1800589d3  jmp     loc_180058F8D
0x1800589d8  mov     edi, 80070216h
0x1800589dd  cmp     cs:?g_doStackCaptures@@3HA, r11d; int g_doStackCaptures
0x1800589e4  jmp     loc_180058EC5
0x1800589e9  mov     rbx, [rbp+37h+var_A0]
0x1800589ed  jmp     loc_180058F90
0x1800589f2  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x1800589f8  mov     edi, 80070216h
0x1800589fd  jmp     loc_180058EC5
0x180058a02  mov     r8d, 5
0x180058a08  mov     [rbp+37h+var_A8], r11d
0x180058a0c  lea     rdx, [rbp+37h+var_58]
0x180058a10  mov     dword ptr [rsp+110h+var_F0], 4
0x180058a18  lea     rcx, [rbp+37h+var_78]
0x180058a1c  call    ??0?$DynArrayImpl@$00@@IEAA@PEAXIII@Z; DynArrayImpl<1>::DynArrayImpl<1>(void *,uint,uint,uint)
0x180058a21  mov     r10d, [r12+8]
0x180058a26  lea     rdx, [rsp+110h+pulResult]; pulResult
0x180058a2b  xor     r9d, r9d
0x180058a2e  mov     [rbp+37h+var_98], r10d
0x180058a32  mov     ecx, r10d
0x180058a35  mov     [rbp+37h+var_B0], r9
0x180058a39  shl     rcx, 2; ullOperand
0x180058a3d  mov     [rsp+110h+var_DC], r9d
0x180058a42  mov     [rsp+110h+pulResult], r9d
0x180058a47  call    ULongLongToULong
0x180058a4c  mov     edi, eax
0x180058a4e  test    eax, eax
0x180058a50  jns     short loc_180058A70
0x180058a52  cmp     cs:?g_doStackCaptures@@3HA, r9d; int g_doStackCaptures
0x180058a59  jz      short loc_180058A62
0x180058a5b  mov     ecx, eax; int
0x180058a5d  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x180058a62  lea     rcx, [rbp+37h+var_78]
0x180058a66  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x180058a6b  jmp     loc_180058FD6
0x180058a70  lea     r9, [rbp+37h+var_B0]
0x180058a74  mov     r8d, r10d
0x180058a77  mov     edx, 4
0x180058a7c  lea     rcx, [rbp+37h+var_78]
0x180058a80  call    ?AddMultiple@?$DynArrayImpl@$00@@IEAAJIIPEAPEAX@Z; DynArrayImpl<1>::AddMultiple(uint,uint,void * *)
0x180058a85  mov     edi, eax
0x180058a87  test    eax, eax
0x180058a89  jns     short loc_180058A93
0x180058a8b  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x180058a91  jmp     short loc_180058A59
0x180058a93  mov     rax, [r15]
0x180058a96  lea     r9, [rbp+37h+var_88]
0x180058a9a  xor     ebx, ebx
0x180058a9c  mov     rcx, r15
0x180058a9f  mov     edx, ebx
0x180058aa1  mov     rax, [rax+28h]
0x180058aa5  lea     r8d, [rbx+1]
0x180058aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058aae  mov     edi, eax
0x180058ab0  test    eax, eax
0x180058ab2  jns     short loc_180058ABC
0x180058ab4  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180058aba  jmp     short loc_180058A59
0x180058abc  mov     r13d, [rsp+110h+pulResult]
0x180058ac1  mov     rcx, r15; struct IStream *
0x180058ac4  mov     rdx, [rbp+37h+var_B0]; void *
0x180058ac8  mov     r8d, r13d; unsigned int
0x180058acb  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x180058ad0  mov     edi, eax
0x180058ad2  test    eax, eax
0x180058ad4  js      short loc_180058AB4
0x180058ad6  mov     r10d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180058add  mov     r14d, r13d
0x180058ae0  xor     eax, eax
0x180058ae2  mov     [rsp+110h+pulResult], eax
0x180058ae6  cmp     eax, [rbp+37h+var_98]
0x180058ae9  jnb     loc_180058CEA
0x180058aef  lea     rcx, [rax+rax*2]
0x180058af3  mov     [rbp+37h+var_80], rax
0x180058af7  mov     rax, [r12+10h]
0x180058afc  lea     r8, [rsp+110h+var_C8]
0x180058b01  lea     rdx, IID_IWICPersistStream
0x180058b08  mov     rcx, [rax+rcx*8+8]
0x180058b0d  mov     rax, [rcx]
0x180058b10  mov     rax, [rax]
0x180058b13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b18  mov     edi, eax
0x180058b1a  test    eax, eax
0x180058b1c  jns     short loc_180058B32
0x180058b1e  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180058b24  jnz     loc_180058A5B
0x180058b2a  test    eax, eax
0x180058b2c  js      loc_180058A62
0x180058b32  mov     rax, [r15]
0x180058b35  lea     r9, [rsp+110h+ullOperand]
0x180058b3a  mov     r8d, 1
0x180058b40  mov     rdx, rbx
0x180058b43  mov     rcx, r15
0x180058b46  mov     rax, [rax+28h]
0x180058b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058b4f  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180058b56  mov     edi, eax
0x180058b58  test    eax, eax
0x180058b5a  jns     short loc_180058B6D
0x180058b5c  test    r9d, r9d
0x180058b5f  jnz     loc_180058A5B
0x180058b65  test    eax, eax
0x180058b67  js      loc_180058A62
0x180058b6d  mov     rcx, [rsp+110h+ullOperand]; ullOperand
0x180058b72  lea     rdx, [rsp+110h+var_DC]; pulResult
0x180058b77  call    ULongLongToULong
0x180058b7c  mov     edi, eax
0x180058b7e  test    eax, eax
0x180058b80  jns     short loc_180058B93
0x180058b82  test    r9d, r9d
0x180058b85  jnz     loc_180058A5B
0x180058b8b  test    eax, eax
0x180058b8d  js      loc_180058A62
0x180058b93  cmp     [rbp+37h+var_94], ebx
0x180058b96  jz      short loc_180058BC6
0x180058b98  mov     ecx, [rsp+110h+var_DC]
0x180058b9c  mov     edx, ecx
0x180058b9e  and     edx, 0FF0000h
0x180058ba4  mov     eax, ecx
0x180058ba6  shr     eax, 10h
0x180058ba9  or      edx, eax
0x180058bab  mov     eax, ecx
0x180058bad  shl     eax, 10h
0x180058bb0  and     ecx, 0FF00h
0x180058bb6  or      eax, ecx
0x180058bb8  shr     edx, 8
0x180058bbb  shl     eax, 8
0x180058bbe  or      edx, eax
0x180058bc0  mov     [rsp+110h+var_DC], edx
0x180058bc4  jmp     short loc_180058BCA
0x180058bc6  mov     edx, [rsp+110h+var_DC]
0x180058bca  mov     rax, [rbp+37h+var_80]
0x180058bce  xor     r9d, r9d
0x180058bd1  mov     rcx, [rbp+37h+var_B0]
0x180058bd5  mov     r8d, [rsp+110h+var_D8]
0x180058bda  mov     [rcx+rax*4], edx
0x180058bdd  mov     rdx, r15
0x180058be0  mov     rcx, [rsp+110h+var_C8]
0x180058be5  mov     rax, [rcx]
0x180058be8  mov     rax, [rax+48h]
0x180058bec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180058bf1  mov     edi, eax
0x180058bf3  test    eax, eax
0x180058bf5  jns     short loc_180058C0B
0x180058bf7  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180058bfd  jnz     loc_180058A5B
0x180058c03  test    eax, eax
0x180058c05  js      loc_180058A62
0x180058c0b  mov     rax, [r15]
0x180058c0e  lea     r9, [rsp+110h+ullMinuend]
0x180058c13  mov     r8d, 1
0x180058c19  mov     rdx, rbx
  ... truncated ...
```
