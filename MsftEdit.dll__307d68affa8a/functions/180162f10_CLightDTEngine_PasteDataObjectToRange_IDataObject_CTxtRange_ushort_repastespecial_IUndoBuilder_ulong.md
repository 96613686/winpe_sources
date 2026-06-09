# CLightDTEngine::PasteDataObjectToRange(IDataObject *,CTxtRange *,ushort,_repastespecial *,IUndoBuilder *,ulong)

- ea: `0x180162f10`
- end: `0x180163967`
- name: `?PasteDataObjectToRange@CLightDTEngine@@QEAAJPEAUIDataObject@@PEAVCTxtRange@@GPEAU_repastespecial@@PEAVIUndoBuilder@@K@Z`
- size: `2647`
- prototype: `__int64 __usercall@<rax>(CLightDTEngine *__hidden this@<rcx>, struct IDataObject *@<rdx>, struct CTxtRange *@<r8>, unsigned __int16@<r9w>, struct _repastespecial *, struct IUndoBuilder *, unsigned int)`
- caller_count: `2`
- callee_count: `23`
- tags: ``

## callers

- `0x18012db4c`
- `0x18016bdd4`

## callees

- `0x18000a9b0`
- `0x180017838`
- `0x18003730c`
- `0x1800693d4`
- `0x18006b8f0`
- `0x180074a58`
- `0x180091f84`
- `0x1800b6034`
- `0x1800f026c`
- `0x1800f7f98`
- `0x180100c98`
- `0x18012d23c`
- `0x180133be8`
- `0x1801479e4`
- `0x180147da4`
- `0x180149788`
- `0x180162a68`
- `0x180162f10`
- `0x180163970`
- `0x18016aa90`
- `0x180178650`
- `0x180205240`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180163888`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801638c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x180163888`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalUnlock` at `0x1801638c2`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180163547`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801637ae`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x180163547`
- `api-ms-win-core-heap-obsolete-l1-1-0!GlobalLock` at `0x1801637ae`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180163288`
- `ext-ms-win-ntuser-misc-l1-2-0!CloseClipboard` at `0x180163288`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180163260`
- `ext-ms-win-ntuser-misc-l1-2-0!OpenClipboard` at `0x180163260`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801630ea`
- `ext-ms-win-ntuser-misc-l1-2-0!GetClipboardOwner` at `0x1801630ea`

## pseudocode

```c
__int64 __fastcall CLightDTEngine::PasteDataObjectToRange(
        CLightDTEngine *this,
        struct IDataObject *a2,
        struct CTxtRange *a3,
        unsigned __int16 a4,
        struct _repastespecial *a5,
        struct IUndoBuilder *a6,
        unsigned int a7)
{
  __int64 v7; // r11
  struct IDataObject *v11; // r10
  int v12; // r14d
  bool v13; // cf
  __int64 v14; // rsi
  __int64 v15; // rax
  int inserted; // edi
  __int64 v17; // rdx
  struct _repastespecial *v18; // r12
  bool v19; // r14
  HWND ClipboardOwner; // r14
  __int64 v21; // rdx
  struct IDataObject *v22; // rcx
  unsigned int v24; // esi
  struct IUndoBuilder *dwParam; // rcx
  int v26; // eax
  int v27; // r14d
  CTxtEdit *v28; // rcx
  struct IUndoBuilder *v29; // r12
  int v30; // esi
  struct IDataObject *v31; // r14
  __int64 v32; // r8
  CTxtEdit *v33; // rcx
  HBITMAP v34; // r13
  CTxtEdit *v35; // rcx
  struct tagFORMATETC *v36; // rdx
  int v37; // eax
  int v38; // eax
  HBITMAP hBitmap; // r14
  int v40; // eax
  bool v41; // r8
  struct _repastespecial *v42; // r9
  unsigned __int64 v43; // rcx
  HBITMAP v44; // r8
  unsigned __int16 *v45; // rax
  int OleObjFromDataObj; // eax
  char v47; // si
  __int16 *v48; // rcx
  struct IUndoBuilder *v49; // [rsp+30h] [rbp-89h]
  int v50; // [rsp+58h] [rbp-61h] BYREF
  CDataTransferObj *v51; // [rsp+60h] [rbp-59h] BYREF
  char *v52; // [rsp+68h] [rbp-51h]
  HBITMAP v53; // [rsp+70h] [rbp-49h]
  __int64 v54; // [rsp+78h] [rbp-41h]
  struct tagFORMATETC *v55; // [rsp+80h] [rbp-39h]
  __int128 v56; // [rsp+88h] [rbp-31h] BYREF
  unsigned __int64 v57; // [rsp+98h] [rbp-21h]
  __int64 v58; // [rsp+A0h] [rbp-19h]
  struct tagSTGMEDIUM v59; // [rsp+A8h] [rbp-11h] BYREF
  struct IDataObject *v60; // [rsp+C0h] [rbp+7h]
  HWND hWndNewOwner; // [rsp+108h] [rbp+4Fh] BYREF
  struct IDataObject *v62; // [rsp+110h] [rbp+57h] BYREF
  struct CTxtRange *v63; // [rsp+118h] [rbp+5Fh]

  v63 = a3;
  v62 = a2;
  v7 = *(_QWORD *)this;
  v11 = a2;
  v12 = *(_DWORD *)(*(_QWORD *)this + 176LL) >> 19;
  memset(&v59, 0, sizeof(v59));
  v13 = *(_WORD *)(v7 + 56) != 0;
  v50 = v12;
  v14 = ((v7 & -(__int64)v13) + 48) & -(__int64)((v7 & -(__int64)v13) != 0);
  v15 = *(_QWORD *)(v7 + 240);
  if ( v15 )
    v54 = *(_QWORD *)(v15 + 24);
  else
    v54 = 0;
  if ( (*(_BYTE *)(v7 + 176) & 4) != 0 )
    return 2147942405LL;
  v60 = a2;
  if ( *(int *)(v7 + 280) >= 0 || *((_BYTE *)this + 28) )
    goto LABEL_9;
  v57 = 2048;
  v56 = 0;
  if ( !(unsigned int)CTxtEdit::TxNotify((CTxtEdit *)v7, 0x800u, &v56) )
    return 2147942405LL;
  v11 = v62;
  *((_BYTE *)this + 28) = 1;
LABEL_9:
  inserted = -2147221404;
  if ( v11 )
    goto LABEL_33;
  if ( !*((_QWORD *)this + 2) )
    goto LABEL_15;
  if ( !(*(unsigned int (__fastcall **)(struct IClipboard *))(*(_QWORD *)g_pIClipboard + 40LL))(g_pIClipboard)
    && !*((_BYTE *)this + 24) )
  {
    v62 = (struct IDataObject *)*((_QWORD *)this + 2);
    ((void (__fastcall *)(struct IDataObject *, __int64, _QWORD))v62->lpVtbl->AddRef)(v62, v17, 0);
  }
  v11 = v62;
  if ( v62 )
  {
LABEL_33:
    v18 = a5;
  }
  else
  {
LABEL_15:
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)this + 8LL))(*(_QWORD *)this);
    v18 = a5;
    v49 = (struct IUndoBuilder *)&v62;
    inserted = (*(__int64 (__fastcall **)(struct IClipboard *, struct CTxtRange *, _QWORD, struct _repastespecial *, unsigned int))(*(_QWORD *)g_pIClipboard + 16LL))(
                 g_pIClipboard,
                 a3,
                 a4,
                 a5,
                 a7);
    v19 = (*(_DWORD *)(*(_QWORD *)this + 280LL) & 0x2000000) != 0;
    (*(void (**)(void))(**(_QWORD **)this + 16LL))();
    if ( inserted == 1 || v19 )
      return 0;
    if ( *((_BYTE *)this + 28) )
    {
      if ( v14 )
        *(_DWORD *)(v14 + 12) |= 0x800u;
      *((_BYTE *)this + 28) = 0;
    }
    if ( inserted >= 0 )
    {
      v11 = v62;
      if ( v62 )
      {
        LOBYTE(v12) = v50;
        goto LABEL_34;
      }
      return 0;
    }
    ClipboardOwner = GetClipboardOwner();
    hWndNewOwner = 0;
    if ( ClipboardOwner
      && !(unsigned int)CTxtEdit::TxGetWindow(*(CTxtEdit **)this, &hWndNewOwner)
      && ClipboardOwner == hWndNewOwner )
    {
      v22 = (struct IDataObject *)*((_QWORD *)this + 2);
      v62 = v22;
      if ( !v22 )
        goto LABEL_28;
      ((void (__fastcall *)(struct IDataObject *, __int64, _QWORD))v22->lpVtbl->AddRef)(v22, v21, 0);
      v11 = v62;
      LOBYTE(v12) = v50;
    }
    else
    {
      LOBYTE(v12) = v50;
      v11 = 0;
      v62 = 0;
    }
  }
LABEL_34:
  LOBYTE(hWndNewOwner) = 0;
  if ( *((_BYTE *)this + 28) )
  {
    if ( v14 )
    {
      *(_DWORD *)(v14 + 12) |= 0x800u;
      v11 = v62;
    }
    *((_BYTE *)this + 28) = 0;
  }
  v24 = a7;
  *((_BYTE *)this + 25) = 1;
  if ( v11 && (v24 & 1) == 0 && v54 )
  {
    LOWORD(v50) = a4;
    dwParam = 0;
    if ( v18 && v18->dwAspect == 4 )
      dwParam = (struct IUndoBuilder *)v18->dwParam;
    v49 = dwParam;
    v26 = (*(__int64 (__fastcall **)(__int64, struct IDataObject *, int *, _QWORD, int))(*(_QWORD *)v54 + 64LL))(
            v54,
            v11,
            &v50,
            (v24 >> 1) & 1,
            1);
    inserted = 0;
    if ( v26 != 262448 )
      inserted = v26;
    if ( inserted && inserted != -2147467263 )
      goto LABEL_172;
    if ( (_WORD)v50 )
    {
      if ( a4 )
      {
        if ( a4 != (_WORD)v50 )
        {
          inserted = -2147221404;
          goto LABEL_172;
        }
        goto LABEL_54;
      }
    }
    else if ( a4 )
    {
LABEL_54:
      v11 = v62;
      goto LABEL_55;
    }
    a4 = v50;
    goto LABEL_54;
  }
LABEL_55:
  v27 = v12 & 1;
  v50 = v27;
  if ( !v11 )
  {
    v28 = *(CTxtEdit **)this;
    hWndNewOwner = 0;
    if ( !(unsigned int)CTxtEdit::TxGetWindow(v28, &hWndNewOwner) && OpenClipboard(hWndNewOwner) )
    {
      inserted = CLightDTEngine::PasteFromClipboard(this, a3, a4, a6, v24, v27);
      CloseClipboard();
    }
    if ( inserted >= 0 )
      return (unsigned int)inserted;
LABEL_28:
    CTxtEdit::Beep(*(CTxtEdit **)this);
    return (unsigned int)inserted;
  }
  if ( a4 == 1 )
  {
    if ( v27 || (*(_WORD *)(*(_QWORD *)this + 276LL) & 0x400) != 0 )
      goto LABEL_71;
    v56 = 0xDu;
    v58 = 0;
    v57 = 0xFFFFFFFF00000000uLL;
    if ( ((unsigned int (__fastcall *)(struct IDataObject *, __int128 *))v11->lpVtbl->QueryGetData)(v11, &v56) )
    {
      LODWORD(v58) = 1;
      if ( ((unsigned int (__fastcall *)(struct IDataObject *, __int128 *))v62->lpVtbl->QueryGetData)(v62, &v56) )
        goto LABEL_71;
      a4 = 13;
    }
    else
    {
      a4 = 13;
    }
  }
  else if ( a4 != 13 )
  {
    goto LABEL_71;
  }
  if ( (*(_WORD *)(*(_QWORD *)this + 276LL) & 0x400) != 0 )
    a4 = 1;
LABEL_71:
  CDisplay::Freeze(*(CDisplay **)(*(_QWORD *)this + 136LL));
  v29 = a6;
  v30 = 0;
  if ( a6 )
  {
    (*(void (__fastcall **)(struct IUndoBuilder *))(*(_QWORD *)a6 + 48LL))(a6);
    (**(void (__fastcall ***)(struct IUndoBuilder *, __int64))v29)(v29, 5);
  }
  if ( !a4 )
  {
    v31 = v62;
    if ( v62 != *((struct IDataObject **)this + 2) || *((_BYTE *)this + 24) )
      goto LABEL_80;
    v51 = 0;
    if ( !((__int64 (__fastcall *)(struct IDataObject *, GUID *, CDataTransferObj **))v62->lpVtbl->QueryInterface)(
            v62,
            &IID_IRichEditDO,
            &v51)
      && v51 )
    {
      CTxtRange::AdjustEndEOP(a3, 0, v32);
      inserted = CDataTransferObj::InsertIntoRange(v51, a3, v29);
      (*(void (__fastcall **)(CDataTransferObj *))(*(_QWORD *)v51 + 16LL))(v51);
      goto LABEL_171;
    }
  }
  v31 = v62;
LABEL_80:
  v33 = *(CTxtEdit **)this;
  v55 = &g_rgFETC;
  v34 = 0;
  LODWORD(v51) = 0;
  v53 = 0;
  v52 = 0;
  if ( (unsigned int)CTxtEdit::IsPlaceHolderStorySelected(v33) )
  {
    v35 = *(CTxtEdit **)this;
    LOBYTE(hWndNewOwner) = 1;
    CTxtEdit::OnSelectStory(v35, 0xFFFFFFFFFFFFFFFFuLL, 0);
    v31 = v62;
  }
  v36 = &g_rgFETC;
  while ( v30 < 26 )
  {
    if ( (!a4 || a4 == v36->cfFormat)
      && ((unsigned int)CRchTxtPtr::IsRich((struct CTxtRange *)((char *)v63 + 8))
       && (*(_DWORD *)(*(_QWORD *)this + 176LL) & 0x10) == 0
       || (*((_BYTE *)&g_rgDOI + 4 * v30) & 2) != 0) )
    {
      if ( ((unsigned int (__fastcall *)(struct IDataObject *))v31->lpVtbl->QueryGetData)(v31)
        || v30 == 17 && (*(_WORD *)(*(_QWORD *)this + 276LL) & 0x400) != 0
        || (*(_DWORD *)(*(_QWORD *)this + 180LL) & 0x4000) != 0 && ((unsigned int)(v30 - 8) <= 2 || v30 == 13) )
      {
        goto LABEL_138;
      }
      if ( (unsigned int)v30 <= 0x14 )
      {
        v37 = 1376260;
        if ( _bittest(&v37, v30) )
          goto LABEL_103;
      }
      v38 = v30 - 1;
      if ( v50 )
      {
        if ( (v38 & 0xFFFFFFED) == 0 && v30 != 19 || (unsigned int)(v30 - 22) <= 2 || !v30 )
          goto LABEL_138;
      }
      else if ( (v38 & 0xFFFFFFED) == 0 && v30 != 19
             || (unsigned int)(v30 - 22) <= 2
             || (unsigned int)(v30 - 8) <= 2
             || !v30 )
      {
LABEL_103:
        if ( ((unsigned int (__fastcall *)(struct IDataObject *, struct tagFORMATETC *, struct tagSTGMEDIUM *))v62->lpVtbl->GetData)(
               v62,
               v55,
               &v59) )
        {
          goto LABEL_138;
        }
        hBitmap = v59.hBitmap;
        v53 = v59.hBitmap;
        v52 = (char *)GlobalLock(v59.hBitmap);
        if ( !v52 )
        {
          CW32System::ReleaseStgMedium(&v59);
          inserted = -2147024882;
          goto LABEL_171;
        }
        if ( (unsigned int)(v30 - 1) <= 1 || v30 == 16 )
        {
          v40 = CW32System::GlobalSize(hBitmap);
          if ( !IsRTF(v52, v40, v41) )
          {
            v30 = 18;
            goto LABEL_117;
          }
        }
        if ( !v30 && *(_QWORD *)(*(_QWORD *)this + 552LL) )
          goto LABEL_138;
LABEL_117:
        CTxtRange::AdjustEndEOP(v63, 0, 0);
        LODWORD(v51) = 1;
        if ( v30 > 12 )
        {
          if ( v30 > 19 )
          {
            if ( v30 == 20 )
            {
LABEL_150:
              v34 = (HBITMAP)CW32System::TextHGlobalAtoW(hBitmap);
              v45 = (unsigned __int16 *)GlobalLock(v34);
              if ( v45 )
              {
                v44 = v34;
                goto LABEL_163;
              }
              inserted = -2147024882;
LABEL_165:
              v47 = v30 + 1;
            }
            else
            {
              if ( v30 == 21 )
                goto LABEL_165;
              if ( v30 == 22 || (unsigned int)(v30 - 23) < 2 )
                goto LABEL_160;
LABEL_159:
              LODWORD(v51) = 0;
              v47 = 0;
            }
            *(_WORD *)(*(_QWORD *)this + 278LL) ^= ((unsigned __int8)*(_WORD *)(*(_QWORD *)this + 278LL)
                                                  ^ (unsigned __int8)(4 * v47))
                                                 & 0x7C;
            if ( hBitmap )
            {
              GlobalUnlock(hBitmap);
              CW32System::ReleaseStgMedium(&v59);
            }
            break;
          }
          if ( v30 == 19 )
          {
            if ( (*(_DWORD *)(*(_QWORD *)this + 180LL) & 0x4000) != 0 )
            {
              OleObjFromDataObj = CLightDTEngine::CreateOleObjFromDataObj(this, v62, v63, a5, 19, v29);
              goto LABEL_153;
            }
            v59.tymed = 1;
            inserted = ((__int64 (__fastcall *)(struct IDataObject *, __int16 *, struct tagSTGMEDIUM *))v62->lpVtbl->GetData)(
                         v62,
                         &word_1802DCC00,
                         &v59);
            if ( !inserted
              && !CTxtRange::InsertImageHelper(v63, 0, 0, 0, 0, *(const unsigned __int16 **)v59.hBitmap, 0, 0, v29) )
            {
              goto LABEL_165;
            }
            goto LABEL_135;
          }
          v44 = hBitmap;
          v43 = (unsigned int)(v30 - 13);
          if ( v30 != 13 )
          {
            if ( v30 != 14 )
            {
              if ( v30 != 15 )
              {
                if ( v30 != 16 )
                {
                  if ( v30 != 17 )
                    goto LABEL_150;
                  v45 = (unsigned __int16 *)v52;
LABEL_163:
                  inserted = CLightDTEngine::HGlobalToRange(this, v30, v44, v45, v63, v29, a7);
                  if ( v34 )
                  {
                    GlobalUnlock(v34);
                    CW32System::GlobalFree(v34);
                  }
                  goto LABEL_165;
                }
LABEL_160:
                OleObjFromDataObj = CLightDTEngine::HGlobalToRange(
                                      this,
                                      v30,
                                      hBitmap,
                                      (unsigned __int16 *)v52,
                                      v63,
                                      v29,
                                      a7);
LABEL_153:
                inserted = OleObjFromDataObj;
                goto LABEL_165;
              }
              goto LABEL_135;
            }
            v43 = *(_DWORD *)(*(_QWORD *)this + 180LL) >> 14;
            if ( (*(_DWORD *)(*(_QWORD *)this + 180LL) & 0x4000) != 0 )
            {
              OleObjFromDataObj = CLightDTEngine::CreateOleObjFromDataObj(this, v62, v63, a5, 14, v29);
              goto LABEL_153;
            }
          }
        }
        else
        {
          if ( v30 == 12 )
            goto LABEL_135;
          if ( v30 <= 6 )
          {
            if ( v30 != 6 )
            {
              if ( (unsigned int)v30 < 4 )
                goto LABEL_160;
              LODWORD(v43) = v30 - 4;
              if ( v30 != 4 )
                goto LABEL_123;
LABEL_135:
              if ( (*(_BYTE *)(*(_QWORD *)this + 276LL) & 0x40) == 0 )
              {
                if ( v54 )
                {
                  inserted = CLightDTEngine::CreateOleObjFromDataObj(this, v62, v63, a5, v30, v29);
                  if ( inserted >= 0 )
                    goto LABEL_165;
                }
              }
            }
LABEL_138:
            v31 = v62;
            v36 = v55;
            goto LABEL_139;
          }
          if ( v30 == 7 )
            goto LABEL_135;
          v43 = (unsigned int)(v30 - 8);
          if ( v30 != 8 )
          {
            v43 = (unsigned int)(v30 - 9);
            if ( v30 != 9 )
            {
              v43 = (unsigned int)(v30 - 10);
              if ( v30 != 10 )
              {
LABEL_123:
                if ( (_DWORD)v43 != 1 )
                  goto LABEL_159;
                goto LABEL_135;
              }
            }
          }
        }
        inserted = CLightDTEngine::CreateImageFromDataObj((CLightDTEngine *)v43, v62, v63, v42, v30, v49);
        if ( inserted >= 0 )
          goto LABEL_165;
        goto LABEL_135;
      }
      hBitmap = v53;
      goto LABEL_117;
    }
LABEL_139:
    ++v30;
    v55 = ++v36;
  }
  if ( !(_DWORD)v51 && v50 )
    inserted = -2147221404;
LABEL_171:
  CDisplay::Thaw(*(CDisplay **)(*(_QWORD *)this + 136LL));
LABEL_172:
  if ( !v60 && v62 )
    ((void (__fastcall *)(struct IDataObject *))v62->lpVtbl->Release)(v62);
  if ( (_BYTE)hWndNewOwner )
  {
    if ( !(unsigned int)CTxtEdit::GetAdjustedTextLength(*(CTxtEdit **)this, 0) )
      CTxtEdit::OnSelectStory((CTxtEdit *)v48, v48[165], 0);
  }
  return (unsigned int)inserted;
}

```

## disassembly

```asm
0x180162f10  mov     rax, rsp
0x180162f13  mov     [rax+20h], rbx
0x180162f17  mov     [rax+18h], r8
0x180162f1b  mov     [rax+10h], rdx
0x180162f1f  push    rbp
0x180162f20  push    rsi
0x180162f21  push    rdi
0x180162f22  push    r12
0x180162f24  push    r13
0x180162f26  push    r14
0x180162f28  push    r15
0x180162f2a  lea     rbp, [rax-47h]
0x180162f2e  sub     rsp, 0C0h
0x180162f35  mov     r11, [rcx]
0x180162f38  mov     rbx, rcx
0x180162f3b  mov     r13, r8
0x180162f3e  xorps   xmm0, xmm0
0x180162f41  xor     r8d, r8d
0x180162f44  movzx   r15d, r9w
0x180162f48  mov     r10, rdx
0x180162f4b  mov     r14d, [r11+0B0h]
0x180162f52  shr     r14d, 13h
0x180162f56  mov     qword ptr [rbp+3Fh+var_50.tymed], r8
0x180162f5a  movdqu  xmmword ptr [rbp+3Fh+var_50.8], xmm0
0x180162f5f  movzx   eax, word ptr [r11+38h]
0x180162f64  neg     ax
0x180162f67  mov     [rbp+3Fh+var_A0], r14d
0x180162f6b  sbb     rcx, rcx
0x180162f6e  and     rcx, r11
0x180162f71  lea     rax, [rcx+30h]
0x180162f75  neg     rcx
0x180162f78  sbb     rsi, rsi
0x180162f7b  and     rsi, rax
0x180162f7e  mov     rax, [r11+0F0h]
0x180162f85  test    rax, rax
0x180162f88  jz      short loc_180162F94
0x180162f8a  mov     rax, [rax+18h]
0x180162f8e  mov     [rbp+3Fh+var_80], rax
0x180162f92  jmp     short loc_180162F98
0x180162f94  mov     [rbp+3Fh+var_80], r8
0x180162f98  test    byte ptr [r11+0B0h], 4
0x180162fa0  jnz     loc_180163947
0x180162fa6  mov     ecx, 800h
0x180162fab  mov     [rbp+3Fh+var_38], rdx
0x180162faf  cmp     [r11+118h], r8d
0x180162fb6  jge     short loc_180162FEC
0x180162fb8  cmp     [rbx+1Ch], r8b
0x180162fbc  jnz     short loc_180162FEC
0x180162fbe  xor     eax, eax
0x180162fc0  lea     r8, [rbp+3Fh+var_70]; void *
0x180162fc4  mov     [rbp+3Fh+var_60], rax
0x180162fc8  mov     edx, ecx; unsigned int
0x180162fca  mov     dword ptr [rbp+3Fh+var_60], ecx
0x180162fcd  mov     rcx, r11; this
0x180162fd0  movups  [rbp+3Fh+var_70], xmm0
0x180162fd4  call    ?TxNotify@CTxtEdit@@QEAAJKPEAX@Z; CTxtEdit::TxNotify(ulong,void *)
0x180162fd9  xor     r8d, r8d
0x180162fdc  test    eax, eax
0x180162fde  jz      loc_180163947
0x180162fe4  mov     r10, [rbp+3Fh+arg_8]
0x180162fe8  mov     byte ptr [rbx+1Ch], 1
0x180162fec  mov     edi, 80040064h
0x180162ff1  test    r10, r10
0x180162ff4  jnz     loc_180163161
0x180162ffa  mov     rdx, [rbx+10h]
0x180162ffe  test    rdx, rdx
0x180163001  jz      short loc_180163047
0x180163003  mov     rcx, cs:?g_pIClipboard@@3PEAVIClipboard@@EA; IClipboard * g_pIClipboard
0x18016300a  mov     rax, [rcx]
0x18016300d  mov     rax, [rax+28h]
0x180163011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163016  xor     r8d, r8d
0x180163019  test    eax, eax
0x18016301b  jnz     short loc_18016303A
0x18016301d  cmp     [rbx+18h], r8b
0x180163021  jnz     short loc_18016303A
0x180163023  mov     rcx, [rbx+10h]
0x180163027  mov     [rbp+3Fh+arg_8], rcx
0x18016302b  mov     rax, [rcx]
0x18016302e  mov     rax, [rax+8]
0x180163032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163037  xor     r8d, r8d
0x18016303a  mov     r10, [rbp+3Fh+arg_8]
0x18016303e  test    r10, r10
0x180163041  jnz     loc_180163161
0x180163047  mov     rcx, [rbx]
0x18016304a  mov     rax, [rcx]
0x18016304d  mov     rax, [rax+8]
0x180163051  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163056  mov     rcx, cs:?g_pIClipboard@@3PEAVIClipboard@@EA; IClipboard * g_pIClipboard
0x18016305d  lea     rdx, [rbp+3Fh+arg_8]
0x180163061  mov     r12, [rbp+3Fh+arg_20]
0x180163065  movzx   r8d, r15w
0x180163069  mov     [rsp+0F0h+var_C8], rdx
0x18016306e  mov     r9, r12
0x180163071  mov     edx, [rbp+3Fh+arg_30]
0x180163074  mov     rax, [rcx]
0x180163077  mov     dword ptr [rsp+0F0h+var_D0], edx
0x18016307b  mov     rdx, r13
0x18016307e  mov     rax, [rax+10h]
0x180163082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163087  mov     rcx, [rbx]
0x18016308a  mov     edi, eax
0x18016308c  mov     rdx, [rcx]
0x18016308f  mov     r14d, [rcx+118h]
0x180163096  shr     r14d, 19h
0x18016309a  and     r14b, 1
0x18016309e  mov     rax, [rdx+10h]
0x1801630a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801630a7  mov     edx, 1
0x1801630ac  cmp     edi, edx
0x1801630ae  jz      loc_18016315A
0x1801630b4  xor     r8d, r8d
0x1801630b7  test    r14b, r14b
0x1801630ba  jnz     loc_18016315A
0x1801630c0  cmp     [rbx+1Ch], r8b
0x1801630c4  jz      short loc_1801630D4
0x1801630c6  test    rsi, rsi
0x1801630c9  jz      short loc_1801630D0
0x1801630cb  bts     dword ptr [rsi+0Ch], 0Bh
0x1801630d0  mov     [rbx+1Ch], r8b
0x1801630d4  test    edi, edi
0x1801630d6  js      short loc_1801630EA
0x1801630d8  mov     r10, [rbp+3Fh+arg_8]
0x1801630dc  test    r10, r10
0x1801630df  jz      short loc_18016315A
0x1801630e1  mov     r14d, [rbp+3Fh+var_A0]
0x1801630e5  jmp     loc_18016316A
0x1801630ea  call    cs:__imp_GetClipboardOwner
0x1801630f0  xor     r8d, r8d
0x1801630f3  mov     r14, rax
0x1801630f6  mov     [rbp+3Fh+hWndNewOwner], r8
0x1801630fa  test    rax, rax
0x1801630fd  jz      short loc_18016314D
0x1801630ff  mov     rcx, [rbx]; this
0x180163102  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x180163106  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18016310b  xor     r8d, r8d
0x18016310e  test    eax, eax
0x180163110  jnz     short loc_18016314D
0x180163112  cmp     r14, [rbp+3Fh+hWndNewOwner]
0x180163116  jnz     short loc_18016314D
0x180163118  mov     rcx, [rbx+10h]
0x18016311c  mov     [rbp+3Fh+arg_8], rcx
0x180163120  test    rcx, rcx
0x180163123  jnz     short loc_180163134
0x180163125  mov     rcx, [rbx]; this
0x180163128  call    ?Beep@CTxtEdit@@QEAAXXZ; CTxtEdit::Beep(void)
0x18016312d  mov     eax, edi
0x18016312f  jmp     loc_18016394C
0x180163134  mov     rax, [rcx]
0x180163137  mov     rax, [rax+8]
0x18016313b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180163140  mov     r10, [rbp+3Fh+arg_8]
0x180163144  xor     r8d, r8d
0x180163147  mov     r14d, [rbp+3Fh+var_A0]
0x18016314b  jmp     short loc_180163165
0x18016314d  mov     r14d, [rbp+3Fh+var_A0]
0x180163151  mov     r10, r8
0x180163154  mov     [rbp+3Fh+arg_8], r8
0x180163158  jmp     short loc_180163165
0x18016315a  xor     eax, eax
0x18016315c  jmp     loc_18016394C
0x180163161  mov     r12, [rbp+3Fh+arg_20]
0x180163165  mov     edx, 1
0x18016316a  mov     byte ptr [rbp+3Fh+hWndNewOwner], r8b
0x18016316e  cmp     [rbx+1Ch], r8b
0x180163172  jz      short loc_180163186
0x180163174  test    rsi, rsi
0x180163177  jz      short loc_180163182
0x180163179  bts     dword ptr [rsi+0Ch], 0Bh
0x18016317e  mov     r10, [rbp+3Fh+arg_8]
0x180163182  mov     [rbx+1Ch], r8b
0x180163186  mov     esi, [rbp+3Fh+arg_30]
0x180163189  mov     [rbx+19h], dl
0x18016318c  test    r10, r10
0x18016318f  jz      loc_18016323C
0x180163195  test    dl, sil
0x180163198  jnz     loc_18016323C
0x18016319e  mov     r11, [rbp+3Fh+var_80]
0x1801631a2  test    r11, r11
0x1801631a5  jz      loc_18016323C
0x1801631ab  mov     word ptr [rbp+3Fh+var_A0], r15w
0x1801631b0  mov     rcx, r8
0x1801631b3  test    r12, r12
0x1801631b6  jz      short loc_1801631C4
0x1801631b8  cmp     dword ptr [r12], 4
0x1801631bd  jnz     short loc_1801631C4
0x1801631bf  mov     rcx, [r12+4]
0x1801631c4  mov     rax, [r11]
0x1801631c7  lea     r8, [rbp+3Fh+var_A0]
0x1801631cb  mov     [rsp+0F0h+var_C8], rcx; struct IUndoBuilder *
0x1801631d0  mov     r9d, esi
0x1801631d3  shr     r9d, 1
0x1801631d6  mov     rcx, r11
0x1801631d9  and     r9d, edx
0x1801631dc  mov     dword ptr [rsp+0F0h+var_D0], edx
0x1801631e0  mov     rax, [rax+40h]
0x1801631e4  mov     rdx, r10
0x1801631e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801631ec  xor     r8d, r8d
0x1801631ef  cmp     eax, 40130h
0x1801631f4  mov     edi, r8d
0x1801631f7  cmovnz  edi, eax
0x1801631fa  test    edi, edi
0x1801631fc  jz      short loc_18016320A
0x1801631fe  cmp     edi, 80004001h
0x180163204  jnz     loc_1801638F8
0x18016320a  movzx   eax, word ptr [rbp+3Fh+var_A0]
0x18016320e  test    ax, ax
0x180163211  jz      short loc_180163229
0x180163213  test    r15w, r15w
0x180163217  jz      short loc_18016322F
0x180163219  cmp     r15w, ax
0x18016321d  jz      short loc_180163233
0x18016321f  mov     edi, 80040064h
0x180163224  jmp     loc_1801638F8
0x180163229  test    r15w, r15w
0x18016322d  jnz     short loc_180163233
0x18016322f  movzx   r15d, ax
0x180163233  mov     r10, [rbp+3Fh+arg_8]
0x180163237  mov     edx, 1
0x18016323c  and     r14d, edx
0x18016323f  mov     [rbp+3Fh+var_A0], r14d
0x180163243  test    r10, r10
0x180163246  jnz     short loc_18016329B
0x180163248  mov     rcx, [rbx]; this
0x18016324b  lea     rdx, [rbp+3Fh+hWndNewOwner]; HWND *
0x18016324f  mov     [rbp+3Fh+hWndNewOwner], r8
0x180163253  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x180163258  test    eax, eax
0x18016325a  jnz     short loc_18016328E
0x18016325c  mov     rcx, [rbp+3Fh+hWndNewOwner]; hWndNewOwner
0x180163260  call    cs:__imp_OpenClipboard
0x180163266  test    eax, eax
0x180163268  jz      short loc_18016328E
0x18016326a  mov     r9, [rbp+3Fh+arg_28]; struct IUndoBuilder *
0x18016326e  movzx   r8d, r15w; unsigned __int16
0x180163272  mov     dword ptr [rsp+0F0h+var_C8], r14d; int
0x180163277  mov     rdx, r13; struct CTxtRange *
0x18016327a  mov     rcx, rbx; this
0x18016327d  mov     dword ptr [rsp+0F0h+var_D0], esi; unsigned int
0x180163281  call    ?PasteFromClipboard@CLightDTEngine@@AEAAJPEAVCTxtRange@@GPEAVIUndoBuilder@@KH@Z; CLightDTEngine::PasteFromClipboard(CTxtRange *,ushort,IUndoBuilder *,ulong,int)
0x180163286  mov     edi, eax
0x180163288  call    cs:__imp_CloseClipboard
0x18016328e  test    edi, edi
0x180163290  jns     loc_18016312D
0x180163296  jmp     loc_180163125
0x18016329b  mov     esi, 0Dh
0x1801632a0  mov     r12d, 400h
0x1801632a6  cmp     r15w, dx
0x1801632aa  jnz     short loc_180163328
0x1801632ac  test    r14d, r14d
0x1801632af  jnz     loc_18016333F
0x1801632b5  mov     rax, [rbx]
0x1801632b8  test    [rax+114h], r12w
0x1801632c0  jnz     short loc_18016333F
0x1801632c2  xor     eax, eax
0x1801632c4  mov     word ptr [rbp+3Fh+var_70], si
0x1801632c8  mov     dword ptr [rbp+3Fh+var_70+2], eax
0x1801632cb  lea     rdx, [rbp+3Fh+var_70]
0x1801632cf  mov     word ptr [rbp+3Fh+var_70+6], ax
0x1801632d3  mov     rcx, r10
0x1801632d6  mov     [rbp+3Fh+var_58], rax
0x1801632da  mov     qword ptr [rbp+3Fh+var_70+8], r8
0x1801632de  mov     dword ptr [rbp+3Fh+var_60], r8d
0x1801632e2  mov     dword ptr [rbp+3Fh+var_60+4], 0FFFFFFFFh
0x1801632e9  mov     rax, [r10]
0x1801632ec  mov     rax, [rax+28h]
0x1801632f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801632f5  test    eax, eax
0x1801632f7  jnz     short loc_180163303
0x1801632f9  mov     r15d, esi
0x1801632fc  mov     edx, 1
0x180163301  jmp     short loc_18016332E
0x180163303  mov     rcx, [rbp+3Fh+arg_8]
0x180163307  lea     rdx, [rbp+3Fh+var_70]
0x18016330b  mov     dword ptr [rbp+3Fh+var_58], 1
0x180163312  mov     rax, [rcx]
0x180163315  mov     rax, [rax+28h]
0x180163319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016331e  test    eax, eax
0x180163320  jnz     short loc_18016333F
0x180163322  movzx   r15d, si
0x180163326  jmp     short loc_1801632FC
0x180163328  cmp     r15w, si
0x18016332c  jnz     short loc_18016333F
0x18016332e  mov     rax, [rbx]
0x180163331  test    [rax+114h], r12w
0x180163339  jz      short loc_18016333F
0x18016333b  movzx   r15d, dx
0x18016333f  mov     rcx, [rbx]
0x180163342  mov     rcx, [rcx+88h]; this
0x180163349  call    ?Freeze@CDisplay@@QEAAXXZ; CDisplay::Freeze(void)
0x18016334e  mov     r12, [rbp+3Fh+arg_28]
0x180163352  xor     esi, esi
0x180163354  test    r12, r12
0x180163357  jz      short loc_18016337B
0x180163359  mov     rax, [r12]
0x18016335d  mov     rcx, r12
  ... truncated ...
```
