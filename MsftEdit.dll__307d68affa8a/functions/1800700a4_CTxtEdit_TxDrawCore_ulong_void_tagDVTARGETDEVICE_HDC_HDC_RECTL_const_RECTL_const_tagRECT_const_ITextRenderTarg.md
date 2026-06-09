# CTxtEdit::TxDrawCore(ulong,void *,tagDVTARGETDEVICE *,HDC__ *,HDC__ *,_RECTL const *,_RECTL const *,tagRECT const *,ITextRenderTarget *,long)

- ea: `0x1800700a4`
- end: `0x180070c42`
- name: `?TxDrawCore@CTxtEdit@@AEAAJKPEAXPEAUtagDVTARGETDEVICE@@PEAUHDC__@@2PEBU_RECTL@@3PEBUtagRECT@@PEAUITextRenderTarget@@J@Z`
- size: `2974`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, unsigned int@<edx>, void *@<r8>, struct tagDVTARGETDEVICE *@<r9>, HDC hdc, HDC, const struct _RECTL *, const struct _RECTL *, const struct tagRECT *, struct ITextRenderTarget *, int)`
- caller_count: `2`
- callee_count: `27`
- tags: `installer_update`

## callers

- `0x18006f570`
- `0x180105bc0`

## callees

- `0x1800228ac`
- `0x180022934`
- `0x18002ab44`
- `0x18002abb0`
- `0x180036bd0`
- `0x18006d67c`
- `0x18006eb58`
- `0x18006f6f0`
- `0x18006f8f0`
- `0x18006f958`
- `0x18006f9ac`
- `0x18006fd9c`
- `0x1800700a4`
- `0x1800714ac`
- `0x180072ec0`
- `0x180073184`
- `0x180074548`
- `0x1800807e8`
- `0x1800dfa30`
- `0x1800f7efc`
- `0x180105270`
- `0x18013bad0`
- `0x180169dac`
- `0x180172ef8`
- `0x1801741d4`
- `0x18018967c`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180070ba9`
- `ext-ms-win-gdi-dc-create-l1-1-0!DeleteDC` at `0x180070ba9`
- `ext-ms-win-gdi-dc-create-l1-1-1!CreateICW` at `0x180070892`
- `ext-ms-win-gdi-dc-create-l1-1-1!CreateICW` at `0x180070892`
- `ext-ms-win-gdi-draw-l1-1-0!StretchDIBits` at `0x18007077c`
- `ext-ms-win-gdi-draw-l1-1-0!StretchDIBits` at `0x18007077c`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800707d3`
- `ext-ms-win-rtcore-gdi-devcaps-l1-1-0!GetDeviceCaps` at `0x1800707d3`

## pseudocode

```c
__int64 __fastcall CTxtEdit::TxDrawCore(
        CTxtEdit *this,
        unsigned int a2,
        void *a3,
        struct tagDVTARGETDEVICE *a4,
        HDC hdc,
        HDC a6,
        struct tagRECT *a7,
        struct tagRECT *a8,
        struct tagRECT *a9,
        struct ITextRenderTarget *a10,
        int a11)
{
  __int64 v13; // r13
  _BYTE *v14; // r14
  int v15; // ebx
  const struct CDisplay *v16; // rdx
  CMsgCallBack *v17; // rcx
  __int64 v18; // rcx
  const struct IDpiAccessor *v19; // rdx
  bool v20; // cl
  struct IGraphicContext *v21; // rax
  __int64 v22; // rbx
  int v23; // eax
  HDC v24; // rax
  __int64 v25; // rcx
  void (__fastcall ****v26)(_QWORD, _QWORD **, unsigned int *, __int64 *, char *); // rbx
  void (__fastcall ***v27)(_QWORD, _QWORD **, unsigned int *, __int64 *, char *); // rbx
  struct IGraphicContext *v28; // rcx
  const struct IDpiAccessor *v29; // rbx
  char v30; // al
  __int64 v31; // rdx
  _QWORD *v32; // rbx
  struct tagDVTARGETDEVICE *v33; // r9
  unsigned int v34; // ebx
  __int64 v35; // rbx
  LONG v36; // eax
  __int64 v37; // rax
  void (__fastcall ****v38)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *); // rbx
  void (__fastcall ***v39)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *); // rbx
  struct IGraphicContext *v40; // rcx
  struct tagRECT *v41; // r15
  const struct CDisplay *v42; // rdx
  __int64 v43; // rcx
  __int64 result; // rax
  int top; // r8d
  int v46; // r9d
  int DestHeight; // eax
  int left; // edx
  __int64 v49; // rax
  struct OTx::ILineLayout **v50; // rcx
  struct OTx::ILineLayout *v51; // r9
  HDC ICW; // rax
  void (__fastcall **v53)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *); // rax
  int v54; // r8d
  int v55; // r9d
  CDisplay *v56; // rcx
  CDisplay *v57; // rax
  CDisplay *v58; // r15
  unsigned __int16 v59; // cx
  COleObject *v60; // r15
  _BYTE v61[4]; // [rsp+70h] [rbp-90h] BYREF
  unsigned int Bits; // [rsp+74h] [rbp-8Ch] BYREF
  struct IGraphicContext *v63; // [rsp+78h] [rbp-88h] BYREF
  char v64; // [rsp+80h] [rbp-80h]
  __int64 v65; // [rsp+84h] [rbp-7Ch] BYREF
  char v66; // [rsp+8Ch] [rbp-74h]
  unsigned int v67; // [rsp+90h] [rbp-70h]
  int v68; // [rsp+94h] [rbp-6Ch]
  _QWORD *v69; // [rsp+98h] [rbp-68h] BYREF
  struct tagRECT v70; // [rsp+A0h] [rbp-60h] BYREF
  HDC v71; // [rsp+B0h] [rbp-50h]
  CDevDesc *v72; // [rsp+B8h] [rbp-48h] BYREF
  struct IGraphicContext *GraphicContext; // [rsp+C0h] [rbp-40h] BYREF
  char v74; // [rsp+C8h] [rbp-38h]
  __int64 v75; // [rsp+CCh] [rbp-34h]
  char v76; // [rsp+D4h] [rbp-2Ch]
  void **v77; // [rsp+D8h] [rbp-28h] BYREF
  __int64 v78; // [rsp+E0h] [rbp-20h]
  struct IGraphicContext *v79; // [rsp+E8h] [rbp-18h] BYREF
  char v80; // [rsp+F0h] [rbp-10h]
  __int64 v81; // [rsp+F4h] [rbp-Ch] BYREF
  char v82; // [rsp+FCh] [rbp-4h]
  struct tagRECT *v83; // [rsp+100h] [rbp+0h]
  struct tagRECT *v84; // [rsp+108h] [rbp+8h]
  char v85[8]; // [rsp+110h] [rbp+10h] BYREF
  struct ITextRenderTarget *v86; // [rsp+118h] [rbp+18h]
  struct tagRECT *v87; // [rsp+120h] [rbp+20h]
  HDC v88; // [rsp+128h] [rbp+28h]
  _QWORD v89[2]; // [rsp+130h] [rbp+30h] BYREF
  struct IGraphicContext *v90; // [rsp+140h] [rbp+40h] BYREF
  char v91; // [rsp+148h] [rbp+48h]
  __int64 v92; // [rsp+14Ch] [rbp+4Ch]
  char v93; // [rsp+154h] [rbp+54h]
  __int16 v94; // [rsp+158h] [rbp+58h]
  __int64 v95; // [rsp+15Ch] [rbp+5Ch]
  int v96; // [rsp+168h] [rbp+68h]
  __int128 v97; // [rsp+170h] [rbp+70h]
  BITMAPINFO bmi; // [rsp+180h] [rbp+80h] BYREF

  v13 = *((_QWORD *)this + 17);
  v84 = a7;
  v83 = a8;
  v87 = a9;
  *(_QWORD *)&v70.left = a3;
  v86 = a10;
  v67 = a2;
  v71 = a6;
  _InterlockedAdd((volatile signed __int32 *)(v13 + 96), 1u);
  if ( *(int *)(*((_QWORD *)this + 17) + 96LL) > 2 )
    goto LABEL_73;
  CCallMgr::CCallMgr((CCallMgr *)v85, this);
  v72 = (CDevDesc *)(*((_QWORD *)this + 17) + 16LL);
  GraphicContext = CreateGraphicContext(
                     (*(_BYTE *)(*(_QWORD *)v72 + 276LL) & 0x40) != 0,
                     *(const struct IDpiAccessor **)(*(_QWORD *)v72 + 568LL),
                     0,
                     0);
  v74 = 0;
  v75 = 0;
  v76 = 0;
  (*(void (__fastcall **)(struct IGraphicContext *, _QWORD))(*(_QWORD *)GraphicContext + 8LL))(
    GraphicContext,
    *((_QWORD *)v72 + 1));
  v14 = (char *)this + 64;
  v74 = *((_BYTE *)v72 + 16);
  v75 = *(_QWORD *)((char *)v72 + 20);
  v76 = *((_BYTE *)v72 + 28);
  if ( hdc && (*v14 & 1) != 0
    || (v15 = 0,
        CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), 0, 0)) )
  {
    v15 = 1;
  }
  v68 = v15;
  *(_WORD *)v14 &= ~1u;
  CWriteLock::CWriteLock(&Bits, 0);
  if ( CLSLock::_cOLSBusy )
  {
    CWriteLock::~CWriteLock((CWriteLock *)&Bits);
    CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v15, hdc);
    CHDCScope::~CHDCScope((CHDCScope *)&v72);
    CCallMgr::~CCallMgr((CCallMgr *)v85);
    goto LABEL_73;
  }
  CWriteLock::~CWriteLock((CWriteLock *)&Bits);
  if ( (*((_BYTE *)this + 176) & 8) != 0 )
  {
    if ( *((_QWORD *)this + 38) )
    {
      v17 = (CMsgCallBack *)*((_QWORD *)this + 39);
      if ( v17 )
        CMsgCallBack::NotifyEvents(v17, 0x80u);
    }
  }
  if ( !a11 )
  {
    v18 = *(_QWORD *)(*((_QWORD *)this + 17) + 80LL);
    if ( v18 )
    {
      *(_DWORD *)(v18 + 16) |= 4u;
      CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v15, hdc);
      CDevDesc::SetDC(v72, (const struct CHDC *)&GraphicContext, -1, -1);
      CHDC::~CHDC((CHDC *)&GraphicContext);
      CCallMgr::~CCallMgr((CCallMgr *)v85);
LABEL_73:
      result = 2147549183LL;
      goto LABEL_59;
    }
  }
  if ( hdc && (*((_DWORD *)this + 46) & 0x40000000) != 0 )
  {
    v34 = -2147418113;
LABEL_84:
    CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v68, hdc);
    CHDCScope::~CHDCScope((CHDCScope *)&v72);
    goto LABEL_58;
  }
  if ( v67 != 1 && v67 != 8 )
  {
    v34 = -2147221397;
    goto LABEL_84;
  }
  if ( v71 && !a4 )
  {
    v34 = -2147024809;
    goto LABEL_84;
  }
  v88 = 0;
  if ( v71 || !a4 )
  {
LABEL_16:
    if ( (*((_DWORD *)this + 46) & 0x40000000) != 0 )
      LS::InvalidateLineCache(*((LS **)this + 17), v16);
    v19 = (const struct IDpiAccessor *)*((_QWORD *)this + 71);
    v20 = (*((_BYTE *)this + 276) & 0x40) != 0;
    v89[0] = 0;
    v89[1] = this;
    v21 = CreateGraphicContext(v20, v19, 0, 0);
    v22 = *((_QWORD *)this + 71);
    v90 = v21;
    v77 = &COverrideDpi::`vftable';
    v91 = 0;
    v92 = 0;
    v93 = 0;
    v94 = 0;
    v95 = 0;
    v96 = 0;
    v97 = 0;
    v78 = 0;
    if ( v22 )
    {
      LODWORD(v78) = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 8LL))(v22);
      v23 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v22 + 16LL))(v22);
    }
    else
    {
      LODWORD(v78) = CW32System::_xPerInchScreenDC;
      v23 = CW32System::_yPerInchScreenDC;
    }
    HIDWORD(v78) = v23;
    v24 = v71;
    if ( v71 )
    {
      COverrideDpi::UpdateDpi((COverrideDpi *)&v77, v71);
      v24 = v71;
    }
    v25 = *((_QWORD *)this + 32);
    if ( v25 && (v26 = *(void (__fastcall *****)(_QWORD, _QWORD **, unsigned int *, __int64 *, char *))(v25 + 80)) != 0 )
      v27 = *v26;
    else
      v27 = 0;
    v28 = CreateGraphicContext((*((_BYTE *)this + 276) & 0x40) != 0, (const struct IDpiAccessor *)&v77, v24, 0);
    v79 = v28;
    v80 = 0;
    v81 = 0;
    v82 = 0;
    if ( v27 )
    {
      LODWORD(v69) = 0;
      Bits = 0;
      v82 = 1;
      (**v27)(v27, &v69, &Bits, &v81, (char *)&v81 + 4);
      v28 = v79;
    }
    v69 = (_QWORD *)*((_QWORD *)this + 17);
    v29 = *(const struct IDpiAccessor **)(v69[2] + 568LL);
    v30 = (*(__int64 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v28 + 80LL))(v28);
    v63 = CreateGraphicContext(v30, v29, 0, 0);
    v64 = 0;
    v65 = 0;
    v66 = 0;
    (*(void (__fastcall **)(struct IGraphicContext *, struct IGraphicContext *))(*(_QWORD *)v63 + 8LL))(v63, v79);
    v64 = v80;
    v65 = v81;
    v66 = v82;
    if ( !v82 && !(*(unsigned __int8 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v63 + 24LL))(v63) )
    {
      v31 = v69[11];
      if ( v31 )
        CHDC::SetDC((CHDC *)&v63, (const struct CHDC *)(v31 + 8));
    }
    v32 = (_QWORD *)v69[8];
    if ( !v32 )
    {
      v69[8] = v89;
      v32 = v89;
    }
    v32[9] = a4;
    ++*(_DWORD *)v32;
    ++*((_DWORD *)v32 + 1);
    *((_DWORD *)v32 + 14) = v67;
    v32[8] = *(_QWORD *)&v70.left;
    if ( v66 || (*(unsigned __int8 (__fastcall **)(struct IGraphicContext *))(*(_QWORD *)v63 + 24LL))(v63) )
      CDevDesc::SetDC((CDevDesc *)(v32 + 1), (const struct CHDC *)&v63, -1, -1);
    CHDC::~CHDC((CHDC *)&v63);
    if ( a11 && a4 )
    {
      v70 = *v84;
      v34 = CTxtEdit::FormatAndPrint(this, hdc, v71, v33, &v70, v83);
      CTxtEdit::OnFormatRange(this, 0, 0, 0);
LABEL_50:
      if ( (*((_DWORD *)this + 46) & 0x40000000) != 0 )
        LS::InvalidateLineCache(*((LS **)this + 17), v42);
      CDisplay::ReleaseDrawInfo(*((CDisplay **)this + 17));
      if ( v88 )
        DeleteDC(v88);
      if ( (unsigned int)CTxtStory::GetObjectCount(*(CTxtStory **)(*((_QWORD *)this + 17) + 72LL)) )
      {
        v59 = *((_WORD *)this + 138);
        if ( (v59 & 0x300) != 0 )
        {
          v60 = *(COleObject **)(*((_QWORD *)this + 30) + 40LL);
          if ( v60 )
          {
            *((_WORD *)this + 138) = v59 ^ (v59 ^ ((HIBYTE(v59) - 1) << 8)) & 0x300;
            if ( (*((_WORD *)v60 + 77) & 0x200) != 0 )
            {
              COleObject::FetchObjectExtents(v60, 0);
              *((_WORD *)v60 + 77) &= ~0x200u;
            }
            COleObject::OnReposition(v60);
          }
        }
      }
      v43 = *((_QWORD *)this + 15);
      if ( v43 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v43 + 16LL))(v43, v67);
      CHDC::~CHDC((CHDC *)&v79);
      v77 = &IDpiAccessor::`vftable';
      CHDC::~CHDC((CHDC *)&v90);
      CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v68, hdc);
      CDevDesc::SetDC(v72, (const struct CHDC *)&GraphicContext, -1, -1);
      CHDC::~CHDC((CHDC *)&GraphicContext);
      goto LABEL_58;
    }
    v34 = 1;
    if ( !v83 )
    {
      LOBYTE(v69) = (*((_DWORD *)this + 44) & 8) != 0;
      if ( (_BYTE)v69 )
      {
        if ( !a11 )
          goto LABEL_40;
      }
      else if ( a11 == -1 )
      {
LABEL_40:
        v35 = *((_QWORD *)this + 71);
        *(_QWORD *)&v70.left = &COverrideDpi::`vftable';
        *(_QWORD *)&v70.right = 0;
        if ( v35 )
        {
          v70.right = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 8LL))(v35);
          v36 = (*(__int64 (__fastcall **)(__int64))(*(_QWORD *)v35 + 16LL))(v35);
        }
        else
        {
          v70.right = CW32System::_xPerInchScreenDC;
          v36 = CW32System::_yPerInchScreenDC;
        }
        v70.bottom = v36;
        if ( hdc && GetDeviceCaps(hdc, 2) == 2 )
          COverrideDpi::UpdateDpi((COverrideDpi *)&v70, hdc);
        v37 = *((_QWORD *)this + 32);
        if ( v37
          && (v38 = *(void (__fastcall *****)(_QWORD, unsigned int *, _QWORD **, __int64 *, char *))(v37 + 80)) != 0 )
        {
          v39 = *v38;
        }
        else
        {
          v39 = 0;
        }
        v63 = CreateGraphicContext((*((_BYTE *)this + 276) & 0x40) != 0, (const struct IDpiAccessor *)&v70, hdc, v86);
        v40 = v63;
        v64 = 0;
        v65 = 0;
        v66 = 0;
        if ( v39 )
        {
          v66 = 1;
          v53 = *v39;
          Bits = 0;
          LODWORD(v69) = 0;
          (*v53)(v39, &Bits, &v69, &v65, (char *)&v65 + 4);
          v40 = v63;
        }
        v61[0] = (*((_DWORD *)this + 70) & 0x100000) != 0;
        (*(void (__fastcall **)(struct IGraphicContext *, _BYTE *))(*(_QWORD *)v40 + 16LL))(v40, v61);
        v41 = v84;
        v34 = CDisplay::Draw(*((CDisplay **)this + 17), (const struct CHDC *)&v63, v84, 0, v87);
        if ( !v34 && (*((_DWORD *)this + 72) & 0x10000) != 0 && v41 && hdc )
        {
          top = v41->top;
          v46 = v41->right - v41->left;
          Bits = 0;
          DestHeight = v41->bottom - top;
          left = v41->left;
          memset(&bmi.bmiHeader.biSizeImage, 0, 24);
          bmi.bmiHeader.biSize = 40;
          bmi.bmiHeader.biWidth = 1;
          bmi.bmiHeader.biHeight = 1;
          *(_QWORD *)&bmi.bmiHeader.biPlanes = 2097153;
          HIBYTE(Bits) = -1;
          StretchDIBits(hdc, left, top, v46, DestHeight, 0, 0, 1, 1, &Bits, &bmi, 0, 0xEE0086u);
        }
        CHDC::~CHDC((CHDC *)&v63);
        if ( v34 != 1 )
          goto LABEL_50;
      }
    }
    v49 = *((_QWORD *)this + 32);
    if ( v49 && (v50 = *(struct OTx::ILineLayout ***)(v49 + 80)) != 0 )
      v51 = *v50;
    else
      v51 = 0;
    CHDC::CHDC(
      (CHDC *)&v63,
      (*((_BYTE *)this + 276) & 0x40) != 0,
      *((const struct IDpiAccessor **)this + 71),
      v51,
      hdc,
      v86);
    v61[0] = (*((_DWORD *)this + 70) & 0x100000) != 0;
    (*(void (__fastcall **)(struct IGraphicContext *, _BYTE *))(*(_QWORD *)v63 + 16LL))(v63, v61);
    if ( (unsigned int)CHDC::GetTechnology((CHDC *)&v63) == 5 )
    {
      Bits = 1;
    }
    else
    {
      v56 = (CDisplay *)*((_QWORD *)this + 17);
      Bits = 0;
      CDisplay::SetDC(v56, (const struct CHDC *)&v63, v54, v55);
    }
    v57 = (CDisplay *)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 472LL))(*((_QWORD *)this + 17));
    v58 = v57;
    if ( v57 )
    {
      *((_DWORD *)v57 + 29) |= 0x40u;
      v34 = CDisplay::Draw(v57, (const struct CHDC *)&v63, v84, v83, v87);
      (*(void (__fastcall **)(CDisplay *, __int64))(*(_QWORD *)v58 + 80LL))(v58, 1);
    }
    if ( !Bits )
      CDevDesc::ResetDCW((CDevDesc *)(*((_QWORD *)this + 17) + 16LL));
    CHDC::~CHDC((CHDC *)&v63);
    goto LABEL_50;
  }
  ICW = CreateICW(
          (LPCWSTR)((char *)a4 + a4->tdDriverNameOffset),
          (LPCWSTR)((char *)a4 + a4->tdDeviceNameOffset),
          (LPCWSTR)((char *)a4 + a4->tdPortNameOffset),
          (const DEVMODEW *)((char *)a4 + a4->tdExtDevmodeOffset));
  v88 = ICW;
  if ( ICW )
  {
    v71 = ICW;
    goto LABEL_16;
  }
  CMagellan::InvertMagellanDownBMP((CTxtEdit *)((char *)this + 64), *((struct CDisplay **)this + 17), v15, hdc);
  CDevDesc::SetDC(v72, (const struct CHDC *)&GraphicContext, -1, -1);
  CHDC::~CHDC((CHDC *)&GraphicContext);
  v34 = -2147467259;
LABEL_58:
  CCallMgr::~CCallMgr((CCallMgr *)v85);
  result = v34;
LABEL_59:
  _InterlockedAdd((volatile signed __int32 *)(v13 + 96), 0xFFFFFFFF);
  return result;
}

```

## disassembly

```asm
0x1800700a4  mov     [rsp-8+arg_10], rbx
0x1800700a9  push    rbp
0x1800700aa  push    rsi
0x1800700ab  push    rdi
0x1800700ac  push    r12
0x1800700ae  push    r13
0x1800700b0  push    r14
0x1800700b2  push    r15
0x1800700b4  lea     rbp, [rsp-0C0h]
0x1800700bc  sub     rsp, 1C0h
0x1800700c3  mov     rax, cs:__security_cookie
0x1800700ca  xor     rax, rsp
0x1800700cd  mov     [rbp+0F0h+var_40], rax
0x1800700d4  mov     rax, [rbp+0F0h+arg_30]
0x1800700db  mov     r15, r9
0x1800700de  mov     r12, [rbp+0F0h+hdc]
0x1800700e5  mov     rdi, rcx
0x1800700e8  mov     r13, [rcx+88h]
0x1800700ef  mov     esi, 1
0x1800700f4  mov     [rbp+0F0h+var_E8], rax
0x1800700f8  mov     rax, [rbp+0F0h+arg_38]
0x1800700ff  mov     [rbp+0F0h+var_F0], rax
0x180070103  mov     rax, [rbp+0F0h+arg_40]
0x18007010a  mov     [rbp+0F0h+var_D0], rax
0x18007010e  mov     rax, [rbp+0F0h+arg_48]
0x180070115  mov     qword ptr [rbp+0F0h+var_150.left], r8
0x180070119  mov     r8, [rbp+0F0h+arg_28]
0x180070120  mov     [rbp+0F0h+var_D8], rax
0x180070124  mov     [rbp+0F0h+var_160], edx
0x180070127  mov     [rbp+0F0h+var_140], r8
0x18007012b  lock add [r13+60h], esi
0x180070130  mov     rax, [rcx+88h]
0x180070137  cmp     dword ptr [rax+60h], 2
0x18007013b  jg      loc_18007080E
0x180070141  mov     rdx, rcx; struct CTxtEdit *
0x180070144  lea     rcx, [rbp+0F0h+var_E0]; this
0x180070148  call    ??0CCallMgr@@QEAA@PEAVCTxtEdit@@@Z; CCallMgr::CCallMgr(CTxtEdit *)
0x18007014d  mov     rbx, [rdi+88h]
0x180070154  xor     r9d, r9d; struct ITextRenderTarget *
0x180070157  add     rbx, 10h
0x18007015b  xor     r8d, r8d; HDC
0x18007015e  mov     [rbp+0F0h+var_138], rbx
0x180070162  mov     rdx, [rbx]
0x180070165  mov     cl, [rdx+114h]
0x18007016b  mov     rdx, [rdx+238h]; struct IDpiAccessor *
0x180070172  shr     cl, 6
0x180070175  and     cl, sil; bool
0x180070178  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x18007017d  mov     [rbp+0F0h+var_130], rax
0x180070181  xor     esi, esi
0x180070183  mov     [rbp+0F0h+var_128], sil
0x180070187  mov     r8, rax
0x18007018a  mov     [rbp+0F0h+var_124], rsi
0x18007018e  mov     [rbp+0F0h+var_11C], sil
0x180070192  mov     rcx, [rax]
0x180070195  mov     rdx, [rbx+8]
0x180070199  mov     rax, [rcx+8]
0x18007019d  mov     rcx, r8
0x1800701a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800701a5  mov     al, [rbx+10h]
0x1800701a8  lea     r14, [rdi+40h]
0x1800701ac  mov     [rbp+0F0h+var_128], al
0x1800701af  mov     eax, [rbx+14h]
0x1800701b2  mov     dword ptr [rbp+0F0h+var_124], eax
0x1800701b5  mov     eax, [rbx+18h]
0x1800701b8  mov     dword ptr [rbp+0F0h+var_124+4], eax
0x1800701bb  mov     al, [rbx+1Ch]
0x1800701be  mov     [rbp+0F0h+var_11C], al
0x1800701c1  test    r12, r12
0x1800701c4  jnz     loc_1800707A8
0x1800701ca  mov     rdx, [rdi+88h]; struct CDisplay *
0x1800701d1  xor     r9d, r9d; HDC
0x1800701d4  xor     r8d, r8d; int
0x1800701d7  mov     rcx, r14; this
0x1800701da  call    ?InvertMagellanDownBMP@CMagellan@@AEAAHPEAVCDisplay@@HPEAUHDC__@@@Z; CMagellan::InvertMagellanDownBMP(CDisplay *,int,HDC__ *)
0x1800701df  mov     ebx, esi
0x1800701e1  test    eax, eax
0x1800701e3  jnz     loc_1800707B2
0x1800701e9  mov     eax, 0FFFEh
0x1800701ee  mov     [rbp+0F0h+var_15C], ebx
0x1800701f1  and     [r14], ax
0x1800701f5  lea     rcx, [rsp+1F0h+Bits]
0x1800701fa  xor     edx, edx
0x1800701fc  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x180070201  cmp     cs:?_cOLSBusy@CLSLock@@1HA, esi; int CLSLock::_cOLSBusy
0x180070207  lea     rcx, [rsp+1F0h+Bits]; this
0x18007020c  jnz     loc_1800708F4
0x180070212  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x180070217  test    byte ptr [rdi+0B0h], 8
0x18007021e  jz      short loc_180070239
0x180070220  cmp     [rdi+130h], rsi
0x180070227  jz      short loc_180070239
0x180070229  mov     rcx, [rdi+138h]; this
0x180070230  test    rcx, rcx
0x180070233  jnz     loc_1800707BC
0x180070239  cmp     [rbp+0F0h+arg_50], esi
0x18007023f  jnz     short loc_180070255
0x180070241  mov     rax, [rdi+88h]
0x180070248  mov     rcx, [rax+50h]
0x18007024c  test    rcx, rcx
0x18007024f  jnz     loc_18007081B
0x180070255  or      esi, 0FFFFFFFFh
0x180070258  test    r12, r12
0x18007025b  jnz     loc_1800707F3
0x180070261  mov     eax, [rbp+0F0h+var_160]
0x180070264  cmp     eax, 1
0x180070267  jnz     loc_180070925
0x18007026d  mov     rax, [rbp+0F0h+var_140]
0x180070271  test    rax, rax
0x180070274  jnz     loc_180070935
0x18007027a  mov     [rbp+0F0h+var_C8], 0
0x180070282  test    rax, rax
0x180070285  jnz     short loc_180070290
0x180070287  test    r15, r15
0x18007028a  jnz     loc_180070872
0x180070290  mov     eax, [rdi+0B8h]
0x180070296  mov     ebx, 1
0x18007029b  shr     eax, 1Eh
0x18007029e  test    bl, al
0x1800702a0  jnz     loc_180070970
0x1800702a6  mov     cl, [rdi+114h]
0x1800702ac  xor     r9d, r9d; struct ITextRenderTarget *
0x1800702af  mov     rdx, [rdi+238h]; struct IDpiAccessor *
0x1800702b6  xor     r8d, r8d; HDC
0x1800702b9  shr     cl, 6
0x1800702bc  and     cl, bl; bool
0x1800702be  mov     [rbp+0F0h+var_C0], 0
0x1800702c6  mov     [rbp+0F0h+var_B8], rdi
0x1800702ca  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x1800702cf  mov     rbx, [rdi+238h]
0x1800702d6  xor     edx, edx
0x1800702d8  mov     [rbp+0F0h+var_B0], rax
0x1800702dc  lea     rax, ??_7COverrideDpi@@6B@; const COverrideDpi::`vftable'
0x1800702e3  mov     [rbp+0F0h+var_118], rax
0x1800702e7  xorps   xmm0, xmm0
0x1800702ea  mov     [rbp+0F0h+var_A8], dl
0x1800702ed  mov     [rbp+0F0h+var_A4], rdx
0x1800702f1  mov     [rbp+0F0h+var_9C], dl
0x1800702f4  mov     [rbp+0F0h+var_98], dx
0x1800702f8  mov     [rbp+0F0h+var_94], rdx
0x1800702fc  mov     [rbp+0F0h+var_88], edx
0x1800702ff  movdqa  [rbp+0F0h+var_80], xmm0
0x180070304  mov     [rbp+0F0h+var_110], rdx
0x180070308  test    rbx, rbx
0x18007030b  jz      loc_18007085E
0x180070311  mov     rax, [rbx]
0x180070314  mov     rcx, rbx
0x180070317  mov     rax, [rax+8]
0x18007031b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070320  mov     dword ptr [rbp+0F0h+var_110], eax
0x180070323  mov     rcx, rbx
0x180070326  mov     rax, [rbx]
0x180070329  mov     rax, [rax+10h]
0x18007032d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070332  xor     edx, edx
0x180070334  mov     dword ptr [rbp+0F0h+var_110+4], eax
0x180070337  mov     rax, [rbp+0F0h+var_140]
0x18007033b  test    rax, rax
0x18007033e  jnz     loc_180070981
0x180070344  mov     rcx, [rdi+100h]
0x18007034b  test    rcx, rcx
0x18007034e  jz      short loc_18007035D
0x180070350  mov     rbx, [rcx+50h]
0x180070354  test    rbx, rbx
0x180070357  jnz     loc_180070998
0x18007035d  mov     rbx, rdx
0x180070360  mov     cl, [rdi+114h]
0x180070366  lea     rdx, [rbp+0F0h+var_118]; struct IDpiAccessor *
0x18007036a  shr     cl, 6
0x18007036d  xor     r9d, r9d; struct ITextRenderTarget *
0x180070370  and     cl, 1; bool
0x180070373  mov     r8, rax; HDC
0x180070376  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x18007037b  mov     rcx, rax
0x18007037e  mov     [rbp+0F0h+var_108], rax
0x180070382  xor     eax, eax
0x180070384  mov     [rbp+0F0h+var_100], al
0x180070387  mov     [rbp+0F0h+var_FC], rax
0x18007038b  mov     [rbp+0F0h+var_F4], al
0x18007038e  test    rbx, rbx
0x180070391  jnz     loc_1800709A0
0x180070397  mov     rax, [rdi+88h]
0x18007039e  mov     [rbp+0F0h+var_158], rax
0x1800703a2  mov     rax, [rax+10h]
0x1800703a6  mov     rbx, [rax+238h]
0x1800703ad  mov     rax, [rcx]
0x1800703b0  mov     rax, [rax+50h]
0x1800703b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800703b9  xor     r9d, r9d; struct ITextRenderTarget *
0x1800703bc  xor     r8d, r8d; HDC
0x1800703bf  mov     rdx, rbx; struct IDpiAccessor *
0x1800703c2  mov     cl, al; bool
0x1800703c4  call    ?CreateGraphicContext@@YAPEAVIGraphicContext@@_NPEBVIDpiAccessor@@PEAUHDC__@@PEAUITextRenderTarget@@@Z; CreateGraphicContext(bool,IDpiAccessor const *,HDC__ *,ITextRenderTarget *)
0x1800703c9  mov     rdx, [rbp+0F0h+var_108]
0x1800703cd  xor     ebx, ebx
0x1800703cf  mov     [rsp+1F0h+var_178], rax
0x1800703d4  mov     r8, rax
0x1800703d7  mov     [rbp+0F0h+var_170], bl
0x1800703da  mov     [rbp+0F0h+var_16C], rbx
0x1800703de  mov     [rbp+0F0h+var_164], bl
0x1800703e1  mov     rcx, [rax]
0x1800703e4  mov     rax, [rcx+8]
0x1800703e8  mov     rcx, r8
0x1800703eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800703f0  mov     al, [rbp+0F0h+var_100]
0x1800703f3  mov     [rbp+0F0h+var_170], al
0x1800703f6  mov     eax, dword ptr [rbp+0F0h+var_FC]
0x1800703f9  mov     dword ptr [rbp+0F0h+var_16C], eax
0x1800703fc  mov     eax, dword ptr [rbp+0F0h+var_FC+4]
0x1800703ff  mov     dword ptr [rbp+0F0h+var_16C+4], eax
0x180070402  mov     al, [rbp+0F0h+var_F4]
0x180070405  mov     [rbp+0F0h+var_164], al
0x180070408  test    al, al
0x18007040a  jnz     short loc_180070432
0x18007040c  mov     rcx, [rsp+1F0h+var_178]
0x180070411  mov     rax, [rcx]
0x180070414  mov     rax, [rax+18h]
0x180070418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007041d  test    al, al
0x18007041f  jnz     short loc_180070432
0x180070421  mov     rdx, [rbp+0F0h+var_158]
0x180070425  mov     rdx, [rdx+58h]
0x180070429  test    rdx, rdx
0x18007042c  jnz     loc_1800709D8
0x180070432  mov     rdx, [rbp+0F0h+var_158]
0x180070436  mov     rbx, [rdx+40h]
0x18007043a  test    rbx, rbx
0x18007043d  jnz     short loc_18007044B
0x18007043f  lea     rax, [rbp+0F0h+var_C0]
0x180070443  mov     [rdx+40h], rax
0x180070447  lea     rbx, [rbp+0F0h+var_C0]
0x18007044b  mov     eax, 1
0x180070450  mov     [rbx+48h], r15
0x180070454  add     [rbx], eax
0x180070456  add     [rbx+4], eax
0x180070459  mov     eax, [rbp+0F0h+var_160]
0x18007045c  mov     [rbx+38h], eax
0x18007045f  mov     rax, qword ptr [rbp+0F0h+var_150.left]
0x180070463  mov     [rbx+40h], rax
0x180070467  cmp     [rbp+0F0h+var_164], 0
0x18007046b  jnz     short loc_180070482
0x18007046d  mov     rcx, [rsp+1F0h+var_178]
0x180070472  mov     rax, [rcx]
0x180070475  mov     rax, [rax+18h]
0x180070479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007047e  test    al, al
0x180070480  jz      short loc_180070496
0x180070482  lea     rcx, [rbx+8]; this
0x180070486  mov     r9d, esi; int
0x180070489  mov     r8d, esi; int
0x18007048c  lea     rdx, [rsp+1F0h+var_178]; struct CHDC *
0x180070491  call    ?SetDC@CDevDesc@@QEAAHAEBVCHDC@@JJ@Z; CDevDesc::SetDC(CHDC const &,long,long)
0x180070496  lea     rcx, [rsp+1F0h+var_178]; this
0x18007049b  call    ??1CHDC@@QEAA@XZ; CHDC::~CHDC(void)
0x1800704a0  mov     ecx, [rbp+0F0h+arg_50]
0x1800704a6  test    ecx, ecx
0x1800704a8  jnz     loc_1800709EB
0x1800704ae  xor     r15d, r15d
0x1800704b1  mov     r8d, 1
0x1800704b7  mov     ebx, r8d
0x1800704ba  cmp     [rbp+0F0h+var_F0], r15
0x1800704be  jnz     loc_180070787
0x1800704c4  mov     eax, [rdi+0B0h]
0x1800704ca  shr     eax, 3
0x1800704cd  and     al, r8b
0x1800704d0  mov     byte ptr [rbp+0F0h+var_158], al
0x1800704d3  jz      loc_180070A39
0x1800704d9  test    ecx, ecx
0x1800704db  jnz     loc_180070787
0x1800704e1  mov     rbx, [rdi+238h]
0x1800704e8  lea     rax, ??_7COverrideDpi@@6B@; const COverrideDpi::`vftable'
0x1800704ef  mov     qword ptr [rbp+0F0h+var_150.left], rax
0x1800704f3  mov     qword ptr [rbp+0F0h+var_150.right], r15
0x1800704f7  test    rbx, rbx
0x1800704fa  jz      loc_1800708E0
0x180070500  mov     rax, [rbx]
0x180070503  mov     rcx, rbx
0x180070506  mov     rax, [rax+8]
0x18007050a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007050f  mov     [rbp+0F0h+var_150.right], eax
0x180070512  mov     rcx, rbx
0x180070515  mov     rax, [rbx]
0x180070518  mov     rax, [rax+10h]
0x18007051c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180070521  mov     [rbp+0F0h+var_150.bottom], eax
0x180070524  test    r12, r12
0x180070527  jnz     loc_1800707CB
0x18007052d  mov     rax, [rdi+100h]
0x180070534  test    rax, rax
0x180070537  jz      short loc_180070546
0x180070539  mov     rbx, [rax+50h]
0x18007053d  test    rbx, rbx
0x180070540  jnz     loc_180070A46
0x180070546  mov     rbx, r15
0x180070549  mov     cl, [rdi+114h]
0x18007054f  lea     rdx, [rbp+0F0h+var_150]; struct IDpiAccessor *
0x180070553  mov     r9, [rbp+0F0h+var_D8]; struct ITextRenderTarget *
0x180070557  mov     r8, r12; HDC
0x18007055a  shr     cl, 6
0x18007055d  and     cl, 1; bool
  ... truncated ...
```
