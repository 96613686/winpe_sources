# CTxtEdit::OnTxRButtonUp(int,int,int,int,ulong,int)

- ea: `0x18016b474`
- end: `0x18016ba20`
- name: `?OnTxRButtonUp@CTxtEdit@@AEAAJHHHHKH@Z`
- size: `1452`
- prototype: `__int64 __usercall@<rax>(CTxtEdit *__hidden this@<rcx>, int@<edx>, int@<r8d>, int@<r9d>, int, unsigned int, int)`
- caller_count: `8`
- callee_count: `23`
- tags: `loader_planting`

## callers

- `0x180074694`
- `0x180079cc0`
- `0x180115ea4`
- `0x18011a5d0`
- `0x1801698cc`
- `0x1801fdc20`
- `0x1802031b4`
- `0x180203820`

## callees

- `0x18002d2bc`
- `0x1800320c0`
- `0x1800372e4`
- `0x18003cfc8`
- `0x18006b8d4`
- `0x18006d350`
- `0x18007a49c`
- `0x180090884`
- `0x1800e055c`
- `0x1800eca80`
- `0x1800f7ca4`
- `0x180100c98`
- `0x18010aaa4`
- `0x18010c3b8`
- `0x180112704`
- `0x1801268a8`
- `0x180161f58`
- `0x18016b474`
- `0x1801ca1dc`
- `0x1801cafc4`
- `0x1801e5dc8`
- `0x18026e1e8`
- `0x18027a010`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016b8ba`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016b964`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016b8ba`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18016b964`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016b841`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016b95a`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016b841`
- `ext-ms-win-ntuser-window-l1-1-2!ClientToScreen` at `0x18016b95a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18016b8ed`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!PeekMessageW` at `0x18016b8ed`
- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x18016b7ed`
- `ext-ms-win-ntuser-menu-l1-1-0!CreatePopupMenu` at `0x18016b7ed`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016b903`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016b9f8`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016b903`
- `ext-ms-win-ntuser-menu-l1-1-0!DestroyMenu` at `0x18016b9f8`
- `ext-ms-win-ntuser-menu-l1-1-0!AppendMenuW` at `0x18016b804`
- `ext-ms-win-ntuser-menu-l1-1-0!AppendMenuW` at `0x18016b804`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016b885`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016b9d4`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016b885`
- `ext-ms-win-ntuser-menu-l1-1-0!TrackPopupMenu` at `0x18016b9d4`

## pseudocode

```c
_BOOL8 __fastcall CTxtEdit::OnTxRButtonUp(
        CTxtEdit *this,
        UINT a2,
        unsigned int a3,
        int a4,
        int a5,
        unsigned int a6,
        char a7)
{
  struct COleObject *FirstObjectInRange; // r14
  CDisplay *v11; // rcx
  int v12; // ecx
  CTxtSelection *Sel; // rax
  CTxtSelection *v15; // rdi
  __int64 v16; // r15
  char v17; // si
  void (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rcx
  int v19; // r14d
  char v20; // r14
  UINT v21; // eax
  int v22; // esi
  int v23; // r14d
  UINT v24; // eax
  __int64 seltyp; // rdx
  __int64 v26; // rcx
  HMENU PopupMenu; // rax
  HWND v28; // rcx
  unsigned __int8 v29; // al
  HWND Parent; // rax
  HMENU v31; // rcx
  HWND v32; // rdi
  __int64 v33; // rcx
  __int64 v34; // rcx
  const struct tagPOINT *nReserved; // [rsp+20h] [rbp-91h]
  HMENU hMenu; // [rsp+40h] [rbp-71h] BYREF
  struct tagPOINT Point; // [rsp+48h] [rbp-69h] BYREF
  struct tagPOINT v38; // [rsp+50h] [rbp-61h] BYREF
  __int64 v39; // [rsp+58h] [rbp-59h] BYREF
  __int64 v40; // [rsp+60h] [rbp-51h] BYREF
  tagMSG Msg; // [rsp+68h] [rbp-49h] BYREF
  struct _selchange v42; // [rsp+98h] [rbp-19h] BYREF
  HWND hWnd; // [rsp+100h] [rbp+4Fh] BYREF
  int v44; // [rsp+118h] [rbp+67h] BYREF

  v44 = a4;
  FirstObjectInRange = 0;
  v38 = (struct tagPOINT)__PAIR64__(a3, a2);
  Point = (struct tagPOINT)__PAIR64__(a3, a2);
  hMenu = 0;
  v40 = 0;
  v11 = (CDisplay *)*((_QWORD *)this + 17);
  v39 = 0;
  hWnd = 0;
  memset(&v42, 0, sizeof(v42));
  CDisplay::PointuvFromPoint(v11, (struct Ptls6::tagLSPOINTUV *)&v39, &v38);
  if ( *((char *)this + 176) >= 0 )
    CTxtEdit::TxSetFocus(this);
  v12 = *((_DWORD *)this + 44);
  if ( (v12 & 0x80u) == 0 && (*((_DWORD *)this + 46) & 0x80) != 0 )
    return 1;
  if ( (v12 & 0x20000) != 0 )
  {
    *((_DWORD *)this + 44) = v12 & 0xBFFDFFFF;
    CTxtEdit::TxKillTimer(this, 0x1B2u);
  }
  Sel = CTxtEdit::GetSel(this);
  v15 = Sel;
  if ( !Sel )
    return 0;
  v16 = 0;
  CTxtSelection::SetSelectionInfo(Sel, &v42);
  v17 = a7;
  if ( *((_QWORD *)this + 30) )
  {
    if ( (unsigned int)CRchTxtPtr::GetObjectCount((CTxtSelection *)((char *)v15 + 8)) )
    {
      if ( (unsigned int)CTxtSelection::PointInSel(v15, v39, 0, 0, -1) || (v17 & 2) != 0 )
      {
        FirstObjectInRange = CObjectMgr::GetFirstObjectInRange(
                               (CObjectMgr *)(*((_QWORD *)v15 + 3) - 8LL),
                               v42.chrg.cpMin,
                               v42.chrg.cpMax,
                               0,
                               (struct CTxtStory *)((*((_QWORD *)v15 + 3) - 8LL) & -(__int64)(*((_QWORD *)v15 + 3) != 0)));
      }
      else
      {
        LODWORD(nReserved) = 0;
        if ( (unsigned int)CObjectMgr::HandleClick(*((_QWORD *)this + 30), this, &v39, 0) == 3 )
        {
          FirstObjectInRange = *(struct COleObject **)(*((_QWORD *)this + 30) + 48LL);
          CTxtSelection::SetSelectionInfo(v15, &v42);
        }
      }
    }
    v16 = *(_QWORD *)(*((_QWORD *)this + 30) + 24LL);
    if ( FirstObjectInRange )
    {
      v18 = (void (__fastcall ***)(_QWORD, GUID *, __int64 *))*((_QWORD *)FirstObjectInRange + 7);
      if ( v18 )
        (**v18)(v18, &IID_IOleObject, &v40);
    }
  }
  v19 = v17 & 1;
  if ( (v17 & 1) == 0
    && *((_DWORD *)v15 + 26) == v19
    && (v17 & 2) == 0
    && !(unsigned int)CTxtSelection::PointInSel(v15, v39, 0, 0, -1) )
  {
    CTxtSelection::SetCaret(v15, v39, (unsigned int)(v19 + 1), 0);
  }
  LOBYTE(v44) = 0;
  if ( *((_QWORD *)this + 75)
    && !*((_DWORD *)v15 + 26)
    && (*(_DWORD *)CRchTxtPtr::GetCF((CTxtSelection *)((char *)v15 + 8)) & 0x10000000) == 0 )
  {
    if ( !v16 && (v17 & 1) == 0 && (v17 & 0x1C) == 0 )
      goto LABEL_44;
    CSpellChecker::MaybeShowContextMenu(
      *((CSpellChecker **)this + 75),
      (v17 & 0xC) != 0,
      *((_DWORD *)v15 + 10),
      &v38,
      nReserved,
      (bool *)&v44);
  }
  if ( !v16 || (_BYTE)v44 )
    goto LABEL_44;
  v20 = v17;
  Msg.hwnd = (HWND)v42.chrg;
  memset(&Msg.message, 0, 32);
  v21 = (v17 & 8) != 0;
  v22 = v17 & 0x10;
  Msg.message = v21;
  v23 = v20 & 4;
  if ( v23 )
  {
    v24 = v21 | 0x4000;
LABEL_37:
    Msg.message = v24;
    goto LABEL_38;
  }
  if ( !v22 )
  {
    v24 = v21 | 0x2000;
    goto LABEL_37;
  }
LABEL_38:
  CTxtEdit::AddSpellingInfoToContextMenu(this, v15, (struct _getcontextmenuexex *)&Msg);
  seltyp = v42.seltyp;
  *(&Msg.message + 1) = a2;
  LODWORD(Msg.wParam) = a3;
  if ( v23 )
  {
    LOWORD(seltyp) = v42.seltyp | 0x4000;
  }
  else if ( !v22 )
  {
    LOWORD(seltyp) = v42.seltyp | 0x2000;
  }
  (*(void (__fastcall **)(__int64, __int64, __int64, tagMSG *, HMENU *))(*(_QWORD *)v16 + 96LL))(
    v16,
    seltyp,
    v40,
    &Msg,
    &hMenu);
  if ( Msg.lParam )
    (*(void (__fastcall **)(LPARAM))(*(_QWORD *)Msg.lParam + 16LL))(Msg.lParam);
LABEL_44:
  if ( *((int *)v15 + 26) > 0 )
    CRunPtrBase::AdjustBackward((CTxtSelection *)((char *)v15 + 64));
  if ( *((_QWORD *)this + 69) )
  {
LABEL_62:
    v26 = v40;
    goto LABEL_63;
  }
  v26 = v40;
  if ( !v40 )
  {
    if ( (*(_DWORD *)CRchTxtPtr::GetCF((CTxtSelection *)((char *)v15 + 8)) & 0x10000000) != 0
      && !(unsigned int)CTxtEdit::TxGetWindow(this, &hWnd) )
    {
      if ( hMenu )
      {
        AppendMenuW(hMenu, 0x800u, 0, 0);
        PopupMenu = hMenu;
      }
      else
      {
        PopupMenu = CreatePopupMenu();
        hMenu = PopupMenu;
      }
      if ( PopupMenu )
      {
        CFreezeDisplay::CFreezeDisplay((CFreezeDisplay *)&v38, *((struct CDisplay **)this + 17));
        GetMathContextMenuInternal(v15, hMenu, 0, 0);
        ClientToScreen(hWnd, &Point);
        v28 = hWnd;
        v29 = CW32System::_fRightHanded;
        *((_DWORD *)this + 70) |= 0x100u;
        TrackPopupMenu(hMenu, v29 != 0 ? 10 : 2, Point.x, Point.y, 0, v28, 0);
        memset(&Msg, 0, sizeof(Msg));
        while ( PeekMessageW(&Msg, hWnd, 0x111u, 0x111u, 1u) )
        {
          if ( !(unsigned int)ProcessMathMenuID((struct ITextRange2 *)v15, Msg.wParam) )
          {
            Parent = GetParent(hWnd);
            if ( !Parent )
              Parent = hWnd;
            CW32System::SendMessage(Parent, 0x111u, Msg.wParam, Msg.lParam);
          }
        }
        v31 = hMenu;
        *((_DWORD *)this + 70) &= ~0x100u;
        DestroyMenu(v31);
        CFreezeDisplay::~CFreezeDisplay((CFreezeDisplay *)&v38);
      }
      return 0;
    }
    goto LABEL_62;
  }
LABEL_63:
  if ( hMenu )
  {
    if ( !(unsigned int)CTxtEdit::TxGetWindow(this, &hWnd) )
    {
      ClientToScreen(hWnd, &Point);
      v32 = GetParent(hWnd);
      if ( !v32 )
        v32 = hWnd;
      CTouchHandlerPtr::ShowGrippers((CTxtEdit *)((char *)this + 592), 0, 0);
      v33 = *((_QWORD *)this + 74);
      if ( v33 )
        (*(void (__fastcall **)(__int64, HMENU))(*(_QWORD *)v33 + 72LL))(v33, hMenu);
      TrackPopupMenu(hMenu, CW32System::_fRightHanded != 0 ? 10 : 2, Point.x, Point.y, 0, v32, 0);
      v34 = *((_QWORD *)this + 74);
      if ( v34 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v34 + 72LL))(v34, 0);
    }
    DestroyMenu(hMenu);
    v26 = v40;
  }
  if ( v26 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v26 + 16LL))(v26);
  return v16 == 0;
}

```

## disassembly

```asm
0x18016b474  mov     [rsp-8+arg_8], rbx
0x18016b479  mov     [rsp-8+arg_18], r9d
0x18016b47e  push    rbp
0x18016b47f  push    rsi
0x18016b480  push    rdi
0x18016b481  push    r12
0x18016b483  push    r13
0x18016b485  push    r14
0x18016b487  push    r15
0x18016b489  lea     rbp, [rsp-0Fh]
0x18016b48e  sub     rsp, 0C0h
0x18016b495  xor     r14d, r14d
0x18016b498  mov     [rbp+3Fh+var_A0.x], edx
0x18016b49b  mov     [rbp+3Fh+var_A0.y], r8d
0x18016b49f  xorps   xmm0, xmm0
0x18016b4a2  mov     rax, qword ptr [rbp+3Fh+var_A0.x]
0x18016b4a6  mov     r12d, r8d
0x18016b4a9  mov     qword ptr [rbp+3Fh+Point.x], rax
0x18016b4ad  lea     r8, [rbp+3Fh+var_A0]; struct tagPOINT *
0x18016b4b1  xor     eax, eax
0x18016b4b3  mov     [rbp+3Fh+hMenu], r14
0x18016b4b7  mov     r13d, edx
0x18016b4ba  mov     dword ptr [rbp+3Fh+var_58.seltyp], eax
0x18016b4bd  mov     rbx, rcx
0x18016b4c0  mov     [rbp+3Fh+var_90], r14
0x18016b4c4  mov     rcx, [rcx+88h]; this
0x18016b4cb  lea     rdx, [rbp+3Fh+var_98]; struct Ptls6::tagLSPOINTUV *
0x18016b4cf  mov     [rbp+3Fh+var_98], r14
0x18016b4d3  mov     [rbp+3Fh+hWnd], r14
0x18016b4d7  movups  xmmword ptr [rbp+3Fh+var_58.nmhdr.hwndFrom], xmm0
0x18016b4db  movups  xmmword ptr [rbp+3Fh+var_58.nmhdr.code], xmm0
0x18016b4df  call    ?PointuvFromPoint@CDisplay@@QEBAXAEAUtagLSPOINTUV@Ptls6@@AEBUtagPOINT@@@Z; CDisplay::PointuvFromPoint(Ptls6::tagLSPOINTUV &,tagPOINT const &)
0x18016b4e4  test    byte ptr [rbx+0B0h], 80h
0x18016b4eb  jnz     short loc_18016B4F5
0x18016b4ed  mov     rcx, rbx; this
0x18016b4f0  call    ?TxSetFocus@CTxtEdit@@QEAAXXZ; CTxtEdit::TxSetFocus(void)
0x18016b4f5  mov     ecx, [rbx+0B0h]
0x18016b4fb  mov     edx, 1
0x18016b500  test    cl, cl
0x18016b502  js      short loc_18016B518
0x18016b504  mov     eax, [rbx+0B8h]
0x18016b50a  shr     eax, 7
0x18016b50d  test    dl, al
0x18016b50f  jz      short loc_18016B518
0x18016b511  mov     eax, edx
0x18016b513  jmp     loc_18016B914
0x18016b518  bt      ecx, 11h
0x18016b51c  jnb     short loc_18016B537
0x18016b51e  and     ecx, 0BFFDFFFFh
0x18016b524  mov     edx, 1B2h; unsigned int
0x18016b529  mov     [rbx+0B0h], ecx
0x18016b52f  mov     rcx, rbx; this
0x18016b532  call    ?TxKillTimer@CTxtEdit@@QEAAXI@Z; CTxtEdit::TxKillTimer(uint)
0x18016b537  mov     rcx, rbx; this
0x18016b53a  call    ?GetSel@CTxtEdit@@QEAAPEAVCTxtSelection@@XZ; CTxtEdit::GetSel(void)
0x18016b53f  mov     rdi, rax
0x18016b542  test    rax, rax
0x18016b545  jz      loc_18016B912
0x18016b54b  lea     rdx, [rbp+3Fh+var_58]; struct _selchange *
0x18016b54f  mov     rcx, rax; this
0x18016b552  mov     r15, r14
0x18016b555  call    ?SetSelectionInfo@CTxtSelection@@QEAAXPEAU_selchange@@@Z; CTxtSelection::SetSelectionInfo(_selchange *)
0x18016b55a  mov     esi, [rbp+3Fh+arg_30]
0x18016b55d  cmp     [rbx+0F0h], r14
0x18016b564  jz      loc_18016B62F
0x18016b56a  lea     rcx, [rdi+8]; this
0x18016b56e  call    ?GetObjectCount@CRchTxtPtr@@QEBAJXZ; CRchTxtPtr::GetObjectCount(void)
0x18016b573  test    eax, eax
0x18016b575  jz      loc_18016B600
0x18016b57b  mov     rdx, [rbp+3Fh+var_98]
0x18016b57f  xor     r9d, r9d
0x18016b582  xor     r8d, r8d
0x18016b585  mov     [rsp+0F0h+nReserved], 0FFFFFFFFh
0x18016b58d  mov     rcx, rdi
0x18016b590  call    ?PointInSel@CTxtSelection@@QEBAHUtagLSPOINTUV@Ptls6@@PEBURECTUV@@W4HITTEST@@J@Z; CTxtSelection::PointInSel(Ptls6::tagLSPOINTUV,RECTUV const *,HITTEST,long)
0x18016b595  test    eax, eax
0x18016b597  jnz     short loc_18016B5D8
0x18016b599  test    sil, 2
0x18016b59d  jnz     short loc_18016B5D8
0x18016b59f  mov     rcx, [rbx+0F0h]
0x18016b5a6  lea     r8, [rbp+3Fh+var_98]
0x18016b5aa  xor     r9d, r9d
0x18016b5ad  mov     [rsp+0F0h+nReserved], r14d
0x18016b5b2  mov     rdx, rbx
0x18016b5b5  call    ?HandleClick@CObjectMgr@@QEAA?AW4ClickStatus@@PEAVCTxtEdit@@AEBUtagLSPOINTUV@Ptls6@@HH@Z; CObjectMgr::HandleClick(CTxtEdit *,Ptls6::tagLSPOINTUV const &,int,int)
0x18016b5ba  cmp     eax, 3
0x18016b5bd  jnz     short loc_18016B600
0x18016b5bf  mov     rax, [rbx+0F0h]
0x18016b5c6  lea     rdx, [rbp+3Fh+var_58]; struct _selchange *
0x18016b5ca  mov     rcx, rdi; this
0x18016b5cd  mov     r14, [rax+30h]
0x18016b5d1  call    ?SetSelectionInfo@CTxtSelection@@QEAAXPEAU_selchange@@@Z; CTxtSelection::SetSelectionInfo(_selchange *)
0x18016b5d6  jmp     short loc_18016B600
0x18016b5d8  mov     rax, [rdi+18h]
0x18016b5dc  mov     r8d, [rbp+3Fh+var_58.chrg.cpMax]; int
0x18016b5e0  mov     edx, [rbp+3Fh+var_58.chrg.cpMin]; int
0x18016b5e3  lea     rcx, [rax-8]; this
0x18016b5e7  neg     rax
0x18016b5ea  sbb     rax, rax
0x18016b5ed  xor     r9d, r9d; int *
0x18016b5f0  and     rax, rcx
0x18016b5f3  mov     qword ptr [rsp+0F0h+nReserved], rax; struct CTxtStory *
0x18016b5f8  call    ?GetFirstObjectInRange@CObjectMgr@@QEAAPEAVCOleObject@@JJPEAJPEAVCTxtStory@@@Z; CObjectMgr::GetFirstObjectInRange(long,long,long *,CTxtStory *)
0x18016b5fd  mov     r14, rax
0x18016b600  mov     rcx, [rbx+0F0h]
0x18016b607  mov     r15, [rcx+18h]
0x18016b60b  test    r14, r14
0x18016b60e  jz      short loc_18016B62F
0x18016b610  mov     rcx, [r14+38h]
0x18016b614  test    rcx, rcx
0x18016b617  jz      short loc_18016B62F
0x18016b619  mov     rax, [rcx]
0x18016b61c  lea     r8, [rbp+3Fh+var_90]
0x18016b620  lea     rdx, IID_IOleObject
0x18016b627  mov     rax, [rax]
0x18016b62a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b62f  mov     r14d, esi
0x18016b632  and     r14d, 1
0x18016b636  jnz     short loc_18016B675
0x18016b638  cmp     [rdi+68h], r14d
0x18016b63c  jnz     short loc_18016B675
0x18016b63e  test    sil, 2
0x18016b642  jnz     short loc_18016B675
0x18016b644  mov     rdx, [rbp+3Fh+var_98]
0x18016b648  xor     r9d, r9d
0x18016b64b  xor     r8d, r8d
0x18016b64e  mov     [rsp+0F0h+nReserved], 0FFFFFFFFh; struct tagPOINT *
0x18016b656  mov     rcx, rdi
0x18016b659  call    ?PointInSel@CTxtSelection@@QEBAHUtagLSPOINTUV@Ptls6@@PEBURECTUV@@W4HITTEST@@J@Z; CTxtSelection::PointInSel(Ptls6::tagLSPOINTUV,RECTUV const *,HITTEST,long)
0x18016b65e  test    eax, eax
0x18016b660  jnz     short loc_18016B675
0x18016b662  mov     rdx, [rbp+3Fh+var_98]
0x18016b666  lea     r8d, [r14+1]
0x18016b66a  xor     r9d, r9d
0x18016b66d  mov     rcx, rdi
0x18016b670  call    ?SetCaret@CTxtSelection@@QEAAXUtagLSPOINTUV@Ptls6@@HH@Z; CTxtSelection::SetCaret(Ptls6::tagLSPOINTUV,int,int)
0x18016b675  xor     eax, eax
0x18016b677  mov     byte ptr [rbp+3Fh+arg_18], al
0x18016b67a  cmp     [rbx+258h], rax
0x18016b681  jz      short loc_18016B6D1
0x18016b683  cmp     [rdi+68h], eax
0x18016b686  jnz     short loc_18016B6D1
0x18016b688  lea     rcx, [rdi+8]; this
0x18016b68c  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18016b691  test    dword ptr [rax], 10000000h
0x18016b697  jnz     short loc_18016B6D1
0x18016b699  test    r15, r15
0x18016b69c  jnz     short loc_18016B6AD
0x18016b69e  test    r14d, r14d
0x18016b6a1  jnz     short loc_18016B6AD
0x18016b6a3  test    sil, 1Ch
0x18016b6a7  jz      loc_18016B791
0x18016b6ad  mov     r8d, [rdi+28h]; int
0x18016b6b1  lea     rax, [rbp+3Fh+arg_18]
0x18016b6b5  mov     rcx, [rbx+258h]; this
0x18016b6bc  lea     r9, [rbp+3Fh+var_A0]; struct tagPOINT *
0x18016b6c0  test    sil, 0Ch
0x18016b6c4  mov     [rsp+0F0h+var_C8], rax; bool *
0x18016b6c9  setnz   dl; bool
0x18016b6cc  call    ?MaybeShowContextMenu@CSpellChecker@@QEAAJ_NJPEBUtagPOINT@@1PEA_N@Z; CSpellChecker::MaybeShowContextMenu(bool,long,tagPOINT const *,tagPOINT const *,bool *)
0x18016b6d1  test    r15, r15
0x18016b6d4  jz      loc_18016B791
0x18016b6da  cmp     byte ptr [rbp+3Fh+arg_18], 0
0x18016b6de  jnz     loc_18016B791
0x18016b6e4  mov     rax, qword ptr [rbp+3Fh+var_58.chrg.cpMin]
0x18016b6e8  mov     r14d, esi
0x18016b6eb  mov     [rbp+3Fh+Msg.hwnd], rax
0x18016b6ef  xorps   xmm0, xmm0
0x18016b6f2  xor     eax, eax
0x18016b6f4  mov     qword ptr [rbp+3Fh+Msg.time], 0
0x18016b6fc  test    sil, 8
0x18016b700  mov     [rbp+3Fh+Msg.lParam], rax
0x18016b704  movdqu  xmmword ptr [rbp+3Fh+Msg.message], xmm0
0x18016b709  lea     ecx, [rax+1]
0x18016b70c  cmovnz  eax, ecx
0x18016b70f  and     esi, 10h
0x18016b712  mov     [rbp+3Fh+Msg.message], eax
0x18016b715  and     r14d, 4
0x18016b719  jz      short loc_18016B721
0x18016b71b  bts     eax, 0Eh
0x18016b71f  jmp     short loc_18016B729
0x18016b721  test    esi, esi
0x18016b723  jnz     short loc_18016B72C
0x18016b725  bts     eax, 0Dh
0x18016b729  mov     [rbp+3Fh+Msg.message], eax
0x18016b72c  lea     r8, [rbp+3Fh+Msg]; struct _getcontextmenuexex *
0x18016b730  mov     rdx, rdi; struct CTxtRange *
0x18016b733  mov     rcx, rbx; this
0x18016b736  call    ?AddSpellingInfoToContextMenu@CTxtEdit@@AEAAJPEBVCTxtRange@@AEAU_getcontextmenuexex@@@Z; CTxtEdit::AddSpellingInfoToContextMenu(CTxtRange const *,_getcontextmenuexex &)
0x18016b73b  movzx   edx, [rbp+3Fh+var_58.seltyp]
0x18016b73f  mov     dword ptr [rbp+3Fh+Msg+0Ch], r13d
0x18016b743  mov     dword ptr [rbp+3Fh+Msg.wParam], r12d
0x18016b747  test    r14d, r14d
0x18016b74a  jz      short loc_18016B753
0x18016b74c  or      dx, 4000h
0x18016b751  jmp     short loc_18016B75C
0x18016b753  test    esi, esi
0x18016b755  jnz     short loc_18016B75C
0x18016b757  or      dx, 2000h
0x18016b75c  mov     rax, [r15]
0x18016b75f  lea     rcx, [rbp+3Fh+hMenu]
0x18016b763  mov     r8, [rbp+3Fh+var_90]
0x18016b767  lea     r9, [rbp+3Fh+Msg]
0x18016b76b  mov     qword ptr [rsp+0F0h+nReserved], rcx
0x18016b770  mov     rcx, r15
0x18016b773  mov     rax, [rax+60h]
0x18016b777  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b77c  mov     rcx, [rbp+3Fh+Msg.lParam]
0x18016b780  test    rcx, rcx
0x18016b783  jz      short loc_18016B791
0x18016b785  mov     rax, [rcx]
0x18016b788  mov     rax, [rax+10h]
0x18016b78c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18016b791  cmp     dword ptr [rdi+68h], 0
0x18016b795  jle     short loc_18016B7A0
0x18016b797  lea     rcx, [rdi+40h]; this
0x18016b79b  call    ?AdjustBackward@CRunPtrBase@@QEAAXXZ; CRunPtrBase::AdjustBackward(void)
0x18016b7a0  cmp     qword ptr [rbx+228h], 0
0x18016b7a8  jnz     loc_18016B92F
0x18016b7ae  mov     rcx, [rbp+3Fh+var_90]
0x18016b7b2  test    rcx, rcx
0x18016b7b5  jnz     loc_18016B933
0x18016b7bb  lea     rcx, [rdi+8]; this
0x18016b7bf  call    ?GetCF@CRchTxtPtr@@QEBAPEBVCCharFormat@@XZ; CRchTxtPtr::GetCF(void)
0x18016b7c4  test    dword ptr [rax], 10000000h
0x18016b7ca  jz      loc_18016B92F
0x18016b7d0  lea     rdx, [rbp+3Fh+hWnd]; HWND *
0x18016b7d4  mov     rcx, rbx; this
0x18016b7d7  call    ?TxGetWindow@CTxtEdit@@QEAAJPEAPEAUHWND__@@@Z; CTxtEdit::TxGetWindow(HWND__ * *)
0x18016b7dc  test    eax, eax
0x18016b7de  jnz     loc_18016B92F
0x18016b7e4  mov     rcx, [rbp+3Fh+hMenu]; hMenu
0x18016b7e8  test    rcx, rcx
0x18016b7eb  jnz     short loc_18016B7F9
0x18016b7ed  call    cs:__imp_CreatePopupMenu
0x18016b7f3  mov     [rbp+3Fh+hMenu], rax
0x18016b7f7  jmp     short loc_18016B80E
0x18016b7f9  xor     r9d, r9d; lpNewItem
0x18016b7fc  xor     r8d, r8d; uIDNewItem
0x18016b7ff  mov     edx, 800h; uFlags
0x18016b804  call    cs:__imp_AppendMenuW
0x18016b80a  mov     rax, [rbp+3Fh+hMenu]
0x18016b80e  test    rax, rax
0x18016b811  jz      loc_18016B912
0x18016b817  mov     rdx, [rbx+88h]; struct CDisplay *
0x18016b81e  lea     rcx, [rbp+3Fh+var_A0]; this
0x18016b822  call    ??0CFreezeDisplay@@QEAA@PEAVCDisplay@@@Z; CFreezeDisplay::CFreezeDisplay(CDisplay *)
0x18016b827  mov     rdx, [rbp+3Fh+hMenu]
0x18016b82b  xor     r9d, r9d
0x18016b82e  xor     r8d, r8d
0x18016b831  mov     rcx, rdi
0x18016b834  call    GetMathContextMenuInternal
0x18016b839  mov     rcx, [rbp+3Fh+hWnd]; hWnd
0x18016b83d  lea     rdx, [rbp+3Fh+Point]; lpPoint
0x18016b841  call    cs:__imp_ClientToScreen
0x18016b847  mov     rcx, [rbp+3Fh+hWnd]
0x18016b84b  mov     al, cs:?_fRightHanded@CW32System@@0EA; uchar CW32System::_fRightHanded
0x18016b851  bts     dword ptr [rbx+118h], 8
0x18016b859  mov     r9d, [rbp+3Fh+Point.y]; y
0x18016b85d  neg     al
0x18016b85f  mov     r8d, [rbp+3Fh+Point.x]; x
0x18016b863  sbb     edx, edx
0x18016b865  mov     [rsp+0F0h+prcRect], 0; prcRect
0x18016b86e  mov     [rsp+0F0h+var_C8], rcx; hWnd
0x18016b873  and     edx, 8
0x18016b876  mov     rcx, [rbp+3Fh+hMenu]; hMenu
0x18016b87a  add     edx, 2; uFlags
0x18016b87d  mov     [rsp+0F0h+nReserved], 0; nReserved
0x18016b885  call    cs:__imp_TrackPopupMenu
0x18016b88b  xorps   xmm0, xmm0
0x18016b88e  mov     esi, 1
0x18016b893  movups  xmmword ptr [rbp+3Fh+Msg.hwnd], xmm0
0x18016b897  mov     r14d, 111h
0x18016b89d  movups  xmmword ptr [rbp-39h], xmm0
0x18016b8a1  movups  xmmword ptr [rbp+3Fh+Msg.time], xmm0
0x18016b8a5  jmp     short loc_18016B8DB
0x18016b8a7  mov     edx, dword ptr [rbp+3Fh+Msg.wParam]; unsigned int
0x18016b8aa  mov     rcx, rdi; struct ITextRange2 *
0x18016b8ad  call    ?ProcessMathMenuID@@YAJPEAUITextRange2@@K@Z; ProcessMathMenuID(ITextRange2 *,ulong)
0x18016b8b2  test    eax, eax
0x18016b8b4  jnz     short loc_18016B8DB
0x18016b8b6  mov     rcx, [rbp+3Fh+hWnd]; hWnd
0x18016b8ba  call    cs:__imp_GetParent
0x18016b8c0  mov     r9, [rbp+3Fh+Msg.lParam]; __int64
0x18016b8c4  mov     edx, r14d; unsigned int
0x18016b8c7  mov     r8, [rbp+3Fh+Msg.wParam]; unsigned __int64
0x18016b8cb  test    rax, rax
0x18016b8ce  cmovz   rax, [rbp+3Fh+hWnd]
0x18016b8d3  mov     rcx, rax; hWnd
0x18016b8d6  call    ?SendMessage@CW32System@@SA_JPEAUHWND__@@I_K_J@Z; CW32System::SendMessage(HWND__ *,uint,unsigned __int64,__int64)
0x18016b8db  mov     rdx, [rbp+3Fh+hWnd]; hWnd
0x18016b8df  lea     rcx, [rbp+3Fh+Msg]; lpMsg
0x18016b8e3  mov     r9d, r14d; wMsgFilterMax
0x18016b8e6  mov     [rsp+0F0h+nReserved], esi; wRemoveMsg
0x18016b8ea  mov     r8d, r14d; wMsgFilterMin
0x18016b8ed  call    cs:__imp_PeekMessageW
0x18016b8f3  test    eax, eax
0x18016b8f5  jnz     short loc_18016B8A7
0x18016b8f7  mov     rcx, [rbp+3Fh+hMenu]; hMenu
0x18016b8fb  btr     dword ptr [rbx+118h], 8
  ... truncated ...
```
