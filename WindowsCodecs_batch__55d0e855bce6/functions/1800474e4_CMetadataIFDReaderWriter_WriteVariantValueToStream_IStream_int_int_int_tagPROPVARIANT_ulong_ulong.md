# CMetadataIFDReaderWriter::WriteVariantValueToStream(IStream *,int,int,int,tagPROPVARIANT *,ulong,ulong *)

- ea: `0x1800474e4`
- end: `0x180047d8e`
- name: `?WriteVariantValueToStream@CMetadataIFDReaderWriter@@IEAAJPEAUIStream@@HHHPEAUtagPROPVARIANT@@KPEAK@Z`
- size: `2218`
- prototype: `int(CMetadataIFDReaderWriter *__hidden this, struct IStream *, int, int, int, struct tagPROPVARIANT *, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `14`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x18004b9d0`
- `0x1800bcdd0`

## callees

- `0x18002cb08`
- `0x1800351e0`
- `0x180046a78`
- `0x1800474e4`
- `0x18004943c`
- `0x18004a800`
- `0x18004b36c`
- `0x180055dbc`
- `0x18009c2d8`
- `0x1800b6d34`
- `0x1800bd9d4`
- `0x1800e5e60`
- `0x1801ac9b0`
- `0x1801ce010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047bf3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180047c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180047d58`

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
  int v24; // eax
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
  void *v53; // [rsp+60h] [rbp-79h] BYREF
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
          PaddingSizeForEmbeddedHandler = WriteFullBufferToStream(a2, &qword_1801F5388, v46);
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
      v24 = DynArrayImpl<1>::AddMultiple((__int64)v61, 4, v26, &v53);
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
0x1800474e4  mov     [rsp-8+arg_10], rbx
0x1800474e9  push    rbp
0x1800474ea  push    rsi
0x1800474eb  push    rdi
0x1800474ec  push    r12
0x1800474ee  push    r13
0x1800474f0  push    r14
0x1800474f2  push    r15
0x1800474f4  lea     rbp, [rsp-7]
0x1800474f9  sub     rsp, 0E0h
0x180047500  mov     rax, cs:__security_cookie
0x180047507  xor     rax, rsp
0x18004750a  mov     [rbp+37h+var_40], rax
0x18004750e  mov     r12, [rbp+37h+arg_28]
0x180047512  xor     r11d, r11d
0x180047515  mov     rbx, [rbp+37h+arg_38]
0x180047519  mov     r10d, r8d
0x18004751c  mov     r13d, dword ptr [rbp+37h+cb]
0x180047520  mov     r14d, r11d
0x180047523  mov     [rbp+37h+var_B0], rcx
0x180047527  mov     r15, rdx
0x18004752a  movzx   eax, word ptr [r12]
0x18004752f  lea     edi, [r11+1]
0x180047533  mov     ecx, 0FFFh
0x180047538  mov     [rbp+37h+var_94], r8d
0x18004753c  and     ax, cx
0x18004753f  mov     [rbp+37h+var_A0], rbx
0x180047543  test    r10d, r10d
0x180047546  movzx   r8d, ax
0x18004754a  mov     [rsp+110h+var_C8], r11
0x18004754f  mov     esi, r11d
0x180047552  setnz   r14b
0x180047556  mov     [rsp+110h+ullOperand], r11
0x18004755b  mov     [rsp+110h+var_D8], r14d
0x180047560  mov     [rsp+110h+ullMinuend], r11
0x180047565  mov     [rbp+37h+var_88], r11
0x180047569  mov     [rbp+37h+pullResult], r11
0x18004756d  mov     [rsp+110h+var_D0], r11d
0x180047572  cmp     r8d, 1Eh
0x180047576  ja      loc_180047C57
0x18004757c  jz      loc_180047BEB
0x180047582  cmp     r8d, 10h
0x180047586  ja      loc_180047AD6
0x18004758c  jz      loc_180047BCF
0x180047592  mov     ecx, r8d
0x180047595  sub     ecx, 2
0x180047598  jz      loc_180047B5E
0x18004759e  sub     ecx, edi
0x1800475a0  jz      loc_180047B48
0x1800475a6  sub     ecx, edi
0x1800475a8  jz      loc_180047B48
0x1800475ae  sub     ecx, edi
0x1800475b0  jz      loc_180047AF6
0x1800475b6  sub     ecx, 7
0x1800475b9  jz      loc_18004774A
0x1800475bf  cmp     ecx, edi
0x1800475c1  jnz     loc_180047C5D
0x1800475c7  mov     rcx, [r12+8]
0x1800475cc  lea     r8, [rsp+110h+var_C8]
0x1800475d1  lea     rdx, IID_IWICPersistStream
0x1800475d8  mov     rax, [rcx]
0x1800475db  mov     rax, [rax]
0x1800475de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800475e3  mov     edi, eax
0x1800475e5  test    eax, eax
0x1800475e7  jns     short loc_1800475FC
0x1800475e9  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800475ef  jz      loc_180047D2A
0x1800475f5  mov     ecx, eax
0x1800475f7  jmp     loc_180047C1B
0x1800475fc  xor     ebx, ebx
0x1800475fe  cmp     [rbp+37h+var_A0], rbx
0x180047602  jz      short loc_18004762C
0x180047604  mov     rax, [r15]
0x180047607  lea     r9, [rsp+110h+ullOperand]
0x18004760c  lea     r8d, [rbx+1]
0x180047610  mov     edx, ebx
0x180047612  mov     rcx, r15
0x180047615  mov     rax, [rax+28h]
0x180047619  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004761e  mov     edi, eax
0x180047620  test    eax, eax
0x180047622  jns     short loc_18004762C
0x180047624  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18004762a  jmp     short loc_1800475EF
0x18004762c  mov     rcx, [rsp+110h+var_C8]
0x180047631  xor     r9d, r9d
0x180047634  mov     r8d, r14d
0x180047637  mov     rdx, r15
0x18004763a  mov     rax, [rcx]
0x18004763d  mov     rax, [rax+48h]
0x180047641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047646  mov     edi, eax
0x180047648  test    eax, eax
0x18004764a  js      short loc_180047624
0x18004764c  mov     rax, [r15]
0x18004764f  lea     r9, [rsp+110h+ullMinuend]
0x180047654  mov     r8d, 1
0x18004765a  mov     rdx, rbx
0x18004765d  mov     rcx, r15
0x180047660  mov     rax, [rax+28h]
0x180047664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047669  xor     ecx, ecx
0x18004766b  mov     edi, eax
0x18004766d  test    eax, eax
0x18004766f  jns     short loc_18004767C
0x180047671  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x180047677  jmp     loc_1800475EF
0x18004767c  mov     r14, [rsp+110h+ullMinuend]
0x180047681  cmp     r14, [rsp+110h+ullOperand]
0x180047686  jb      loc_18004773A
0x18004768c  sub     r14, [rsp+110h+ullOperand]
0x180047691  mov     eax, 0FFFFFFFFh
0x180047696  cmp     r14, rax
0x180047699  ja      loc_18004773A
0x18004769f  mov     [rsp+110h+var_DC], ecx
0x1800476a3  lea     r9, [rsp+110h+var_DC]; unsigned int *
0x1800476a8  mov     rcx, [rbp+37h+var_B0]
0x1800476ac  mov     r8d, r14d; unsigned int
0x1800476af  mov     rdx, r12; struct tagPROPVARIANT *
0x1800476b2  mov     rcx, [rcx+98h]; struct _GUID *
0x1800476b9  call    ?GetPaddingSizeForEmbeddedHandler@@YAJPEBU_GUID@@PEBUtagPROPVARIANT@@IPEAI@Z; GetPaddingSizeForEmbeddedHandler(_GUID const *,tagPROPVARIANT const *,uint,uint *)
0x1800476be  xor     r11d, r11d
0x1800476c1  mov     edi, eax
0x1800476c3  test    eax, eax
0x1800476c5  jns     short loc_1800476DC
0x1800476c7  cmp     cs:?g_doStackCaptures@@3HA, r11d; int g_doStackCaptures
0x1800476ce  jnz     loc_1800475F5
0x1800476d4  test    eax, eax
0x1800476d6  js      loc_180047D2A
0x1800476dc  mov     ebx, [rsp+110h+var_DC]
0x1800476e0  test    ebx, ebx
0x1800476e2  jz      short loc_180047731
0x1800476e4  mov     r8d, ebx; unsigned int
0x1800476e7  lea     rdx, qword_1801F5388; void *
0x1800476ee  mov     rcx, r15; struct IStream *
0x1800476f1  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x1800476f6  xor     r11d, r11d
0x1800476f9  mov     edi, eax
0x1800476fb  test    eax, eax
0x1800476fd  jns     short loc_18004770B
0x1800476ff  cmp     cs:?g_doStackCaptures@@3HA, r11d; int g_doStackCaptures
0x180047706  jmp     loc_1800475EF
0x18004770b  lea     eax, [rbx+r14]
0x18004770f  cmp     eax, r14d
0x180047712  jb      short loc_180047720
0x180047714  mov     rbx, [rbp+37h+var_A0]
0x180047718  mov     r14d, eax
0x18004771b  jmp     loc_180047CE1
0x180047720  mov     edi, 80070216h
0x180047725  cmp     cs:?g_doStackCaptures@@3HA, r11d; int g_doStackCaptures
0x18004772c  jmp     loc_180047C13
0x180047731  mov     rbx, [rbp+37h+var_A0]
0x180047735  jmp     loc_180047CE4
0x18004773a  cmp     cs:?g_doStackCaptures@@3HA, ecx; int g_doStackCaptures
0x180047740  mov     edi, 80070216h
0x180047745  jmp     loc_180047C13
0x18004774a  mov     r8d, 5
0x180047750  mov     [rbp+37h+var_A8], r11d
0x180047754  lea     rdx, [rbp+37h+var_58]
0x180047758  mov     dword ptr [rsp+110h+var_F0], 4
0x180047760  lea     rcx, [rbp+37h+var_78]
0x180047764  call    ??0?$DynArrayImpl@$00@@IEAA@PEAXIII@Z; DynArrayImpl<1>::DynArrayImpl<1>(void *,uint,uint,uint)
0x180047769  mov     r10d, [r12+8]
0x18004776e  lea     rdx, [rsp+110h+pulResult]; pulResult
0x180047773  xor     r9d, r9d
0x180047776  mov     [rbp+37h+var_98], r10d
0x18004777a  mov     ecx, r10d
0x18004777d  mov     [rbp+37h+var_B0], r9
0x180047781  shl     rcx, 2; ullOperand
0x180047785  mov     [rsp+110h+var_DC], r9d
0x18004778a  mov     [rsp+110h+pulResult], r9d
0x18004778f  call    ULongLongToULong
0x180047794  mov     edi, eax
0x180047796  test    eax, eax
0x180047798  jns     short loc_1800477B8
0x18004779a  cmp     cs:?g_doStackCaptures@@3HA, r9d; int g_doStackCaptures
0x1800477a1  jz      short loc_1800477AA
0x1800477a3  mov     ecx, eax; int
0x1800477a5  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1800477aa  lea     rcx, [rbp+37h+var_78]
0x1800477ae  call    ??1?$DynArrayImpl@$00@@IEAA@XZ; DynArrayImpl<1>::~DynArrayImpl<1>(void)
0x1800477b3  jmp     loc_180047D2A
0x1800477b8  lea     r9, [rbp+37h+var_B0]
0x1800477bc  mov     r8d, r10d
0x1800477bf  mov     edx, 4
0x1800477c4  lea     rcx, [rbp+37h+var_78]
0x1800477c8  call    ?AddMultiple@?$DynArrayImpl@$00@@IEAAJIIPEAPEAX@Z; DynArrayImpl<1>::AddMultiple(uint,uint,void * *)
0x1800477cd  mov     edi, eax
0x1800477cf  test    eax, eax
0x1800477d1  jns     short loc_1800477DB
0x1800477d3  cmp     cs:?g_doStackCaptures@@3HA, esi; int g_doStackCaptures
0x1800477d9  jmp     short loc_1800477A1
0x1800477db  mov     rax, [r15]
0x1800477de  lea     r9, [rbp+37h+var_88]
0x1800477e2  xor     ebx, ebx
0x1800477e4  mov     rcx, r15
0x1800477e7  mov     edx, ebx
0x1800477e9  mov     rax, [rax+28h]
0x1800477ed  lea     r8d, [rbx+1]
0x1800477f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477f6  mov     edi, eax
0x1800477f8  test    eax, eax
0x1800477fa  jns     short loc_180047804
0x1800477fc  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180047802  jmp     short loc_1800477A1
0x180047804  mov     r13d, [rsp+110h+pulResult]
0x180047809  mov     rcx, r15; struct IStream *
0x18004780c  mov     rdx, [rbp+37h+var_B0]; void *
0x180047810  mov     r8d, r13d; unsigned int
0x180047813  call    ?WriteFullBufferToStream@@YAJPEAUIStream@@PEBXI@Z; WriteFullBufferToStream(IStream *,void const *,uint)
0x180047818  mov     edi, eax
0x18004781a  test    eax, eax
0x18004781c  js      short loc_1800477FC
0x18004781e  mov     r10d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x180047825  mov     r14d, r13d
0x180047828  xor     eax, eax
0x18004782a  mov     [rsp+110h+pulResult], eax
0x18004782e  cmp     eax, [rbp+37h+var_98]
0x180047831  jnb     loc_180047A32
0x180047837  lea     rcx, [rax+rax*2]
0x18004783b  mov     [rbp+37h+var_80], rax
0x18004783f  mov     rax, [r12+10h]
0x180047844  lea     r8, [rsp+110h+var_C8]
0x180047849  lea     rdx, IID_IWICPersistStream
0x180047850  mov     rcx, [rax+rcx*8+8]
0x180047855  mov     rax, [rcx]
0x180047858  mov     rax, [rax]
0x18004785b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047860  mov     edi, eax
0x180047862  test    eax, eax
0x180047864  jns     short loc_18004787A
0x180047866  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x18004786c  jnz     loc_1800477A3
0x180047872  test    eax, eax
0x180047874  js      loc_1800477AA
0x18004787a  mov     rax, [r15]
0x18004787d  lea     r9, [rsp+110h+ullOperand]
0x180047882  mov     r8d, 1
0x180047888  mov     rdx, rbx
0x18004788b  mov     rcx, r15
0x18004788e  mov     rax, [rax+28h]
0x180047892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047897  mov     r9d, cs:?g_doStackCaptures@@3HA; int g_doStackCaptures
0x18004789e  mov     edi, eax
0x1800478a0  test    eax, eax
0x1800478a2  jns     short loc_1800478B5
0x1800478a4  test    r9d, r9d
0x1800478a7  jnz     loc_1800477A3
0x1800478ad  test    eax, eax
0x1800478af  js      loc_1800477AA
0x1800478b5  mov     rcx, [rsp+110h+ullOperand]; ullOperand
0x1800478ba  lea     rdx, [rsp+110h+var_DC]; pulResult
0x1800478bf  call    ULongLongToULong
0x1800478c4  mov     edi, eax
0x1800478c6  test    eax, eax
0x1800478c8  jns     short loc_1800478DB
0x1800478ca  test    r9d, r9d
0x1800478cd  jnz     loc_1800477A3
0x1800478d3  test    eax, eax
0x1800478d5  js      loc_1800477AA
0x1800478db  cmp     [rbp+37h+var_94], ebx
0x1800478de  jz      short loc_18004790E
0x1800478e0  mov     ecx, [rsp+110h+var_DC]
0x1800478e4  mov     edx, ecx
0x1800478e6  and     edx, 0FF0000h
0x1800478ec  mov     eax, ecx
0x1800478ee  shr     eax, 10h
0x1800478f1  or      edx, eax
0x1800478f3  mov     eax, ecx
0x1800478f5  shl     eax, 10h
0x1800478f8  and     ecx, 0FF00h
0x1800478fe  or      eax, ecx
0x180047900  shr     edx, 8
0x180047903  shl     eax, 8
0x180047906  or      edx, eax
0x180047908  mov     [rsp+110h+var_DC], edx
0x18004790c  jmp     short loc_180047912
0x18004790e  mov     edx, [rsp+110h+var_DC]
0x180047912  mov     rax, [rbp+37h+var_80]
0x180047916  xor     r9d, r9d
0x180047919  mov     rcx, [rbp+37h+var_B0]
0x18004791d  mov     r8d, [rsp+110h+var_D8]
0x180047922  mov     [rcx+rax*4], edx
0x180047925  mov     rdx, r15
0x180047928  mov     rcx, [rsp+110h+var_C8]
0x18004792d  mov     rax, [rcx]
0x180047930  mov     rax, [rax+48h]
0x180047934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047939  mov     edi, eax
0x18004793b  test    eax, eax
0x18004793d  jns     short loc_180047953
0x18004793f  cmp     cs:?g_doStackCaptures@@3HA, ebx; int g_doStackCaptures
0x180047945  jnz     loc_1800477A3
0x18004794b  test    eax, eax
0x18004794d  js      loc_1800477AA
0x180047953  mov     rax, [r15]
0x180047956  lea     r9, [rsp+110h+ullMinuend]
0x18004795b  mov     r8d, 1
0x180047961  mov     rdx, rbx
  ... truncated ...
```
