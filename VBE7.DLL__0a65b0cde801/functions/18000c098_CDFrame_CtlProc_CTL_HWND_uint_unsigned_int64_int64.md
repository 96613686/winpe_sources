# CDFrame::CtlProc(CTL *,HWND__ *,uint,unsigned __int64,__int64)

- ea: `0x18000c098`
- end: `0x18000caf8`
- name: `?CtlProc@CDFrame@@SA_JPEAUCTL@@PEAUHWND__@@I_K_J@Z`
- size: `2656`
- prototype: `__int64 __fastcall(struct CTL *, HWND, unsigned int, unsigned __int64, __int64)`
- caller_count: `0`
- callee_count: `54`
- tags: `installer_update, broker_com_uri`

## callees

- `0x180003f00`
- `0x180004748`
- `0x1800049a8`
- `0x180004a90`
- `0x180004e7c`
- `0x180005054`
- `0x18000539c`
- `0x180006a98`
- `0x180006acc`
- `0x180006f8c`
- `0x18000a9a4`
- `0x18000c098`
- `0x18000da48`
- `0x18000e424`
- `0x18000e708`
- `0x18000fcd4`
- `0x1800122e4`
- `0x180012398`
- `0x180012474`
- `0x1800126e8`
- `0x180012a30`
- `0x180012a90`
- `0x180012ba4`
- `0x180013110`
- `0x180013194`
- `0x1800131d4`
- `0x1800132bc`
- `0x1800133c8`
- `0x18001340c`
- `0x180013de4`
- `0x180015ae8`
- `0x1800171e8`
- `0x18001bf84`
- `0x18002119c`
- `0x180021a90`
- `0x180021b54`
- `0x180021e38`
- `0x180023160`
- `0x18002afd8`
- `0x180037d40`
- `0x180037e20`
- `0x18003b114`
- `0x18003b174`
- `0x18003c748`
- `0x18003fefc`
- `0x18005a100`
- `0x18005a280`
- `0x1800751f8`
- `0x180093744`
- `0x1800b3310`

## import_xrefs

- `USER32!IsWindowVisible` at `0x18000c3fe`
- `USER32!IsWindowVisible` at `0x18000c6a0`
- `USER32!IsWindowVisible` at `0x18000c3fe`
- `USER32!IsWindowVisible` at `0x18000c6a0`
- `USER32!UpdateWindow` at `0x18000cac5`
- `USER32!UpdateWindow` at `0x18000cac5`
- `USER32!SetFocus` at `0x18000c1fa`
- `USER32!SetFocus` at `0x18000c1fa`
- `USER32!EnableWindow` at `0x18000c23a`
- `USER32!EnableWindow` at `0x18000c23a`
- `USER32!BringWindowToTop` at `0x18000c9d9`
- `USER32!BringWindowToTop` at `0x18000c9d9`
- `USER32!SetWindowLongA` at `0x18000c4ba`
- `USER32!SetWindowLongA` at `0x18000c4ba`
- `USER32!MessageBeep` at `0x18000c585`
- `USER32!MessageBeep` at `0x18000c585`
- `USER32!GetSystemMenu` at `0x18000c38d`
- `USER32!GetSystemMenu` at `0x18000c38d`
- `USER32!IsZoomed` at `0x18000c30f`
- `USER32!IsZoomed` at `0x18000c30f`
- `USER32!IsIconic` at `0x18000c528`
- `USER32!IsIconic` at `0x18000ca78`
- `USER32!IsIconic` at `0x18000c528`
- `USER32!IsIconic` at `0x18000ca78`
- `GDI32!DeleteObject` at `0x18000ca09`
- `GDI32!DeleteObject` at `0x18000ca09`

## pseudocode

```c
__int64 __fastcall CDFrame::CtlProc(struct CTL *a1, HWND a2, unsigned int a3, HMENU a4, LPARAM a5)
{
  int v5; // eax
  HWND lParam; // r12
  unsigned int v7; // edi
  struct CTL *v11; // rbx
  int v12; // r13d
  __int64 result; // rax
  int v14; // eax
  void *v15; // rcx
  CMsoComponent *v16; // rcx
  struct CTL *v17; // rcx
  HWND v18; // r8
  int v19; // edx
  struct DESK *v20; // rcx
  __int64 v21; // rcx
  const char *PrintFullPath; // rax
  _QWORD *v23; // rcx
  __int64 v24; // rax
  int v25; // eax
  int v26; // eax
  __int64 v27; // rcx
  HWND v28; // rcx
  HWND v29; // rdx
  __int64 v30; // rcx
  int v31; // eax
  unsigned int v32; // edx
  int v33; // ecx
  _QWORD *v34; // rcx
  _QWORD *v35; // rax
  __int64 v36; // rdx
  int v37; // r14d
  __int64 v38; // rdx
  __int64 v39; // rax
  int v40; // esi
  __int64 v41; // rax
  __int64 v42; // rcx
  void *v43; // rcx
  __int64 v44; // rcx
  __int64 v45; // [rsp+30h] [rbp-10h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-8h] BYREF
  __int64 v47; // [rsp+78h] [rbp+38h] BYREF

  lParam = (HWND)a5;
  v7 = 0;
  v11 = a1;
  v12 = v5 - 48;
  if ( a2
    && ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)a1 + 8) + 48LL)) != 0
    && (unsigned int)FDesFilter(a2, a3, (unsigned __int64)a4, a5, &v45) )
  {
    return v45;
  }
  if ( a3 <= 0x112 )
  {
    if ( a3 == 274 )
    {
      v14 = DeskWmSysCommand(v11, a2, (unsigned __int64)a4);
    }
    else
    {
      if ( a3 <= 0x18 )
      {
        switch ( a3 )
        {
          case 0x18u:
            v21 = *((_QWORD *)v11 + 8);
            if ( ((unsigned __int8)v12 & *(_BYTE *)(v21 + 48)) != 0 )
            {
              if ( a4 )
              {
                ProjNotifyDesignerWinVisible(*(struct CProjitemVisual **)(*(_QWORD *)(v21 + 136) + 120LL));
              }
              else if ( Pbrs_pprojwinitemVis == *(struct CProjWinItem **)(*(_QWORD *)(*(_QWORD *)(v21 + 136) + 120LL)
                                                                        + 200LL) )
              {
                PbrsUpdate(1);
              }
            }
            else if ( a4 == (HMENU)1 )
            {
              if ( !lParam
                && (!IsWindowVisible(a2) || ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 8) + 56LL)) == 0) )
              {
                (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v11 + 8) + 8LL))(*((_QWORD *)v11 + 8));
                *(_DWORD *)(*((_QWORD *)v11 + 8) + 56LL) |= v12;
              }
              MoveOfficeAssistant(a2);
            }
            else if ( !lParam && ((unsigned __int8)v12 & *(_BYTE *)(v21 + 56)) != 0 )
            {
              (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
              *(_DWORD *)(*((_QWORD *)v11 + 8) + 56LL) &= ~0x10u;
            }
            goto LABEL_179;
          case 1u:
            if ( ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 8) + 48LL)) == 0 )
              *((_QWORD *)v11 + 84) = GetSystemMenu(a2, 0);
            goto LABEL_179;
          case 2u:
            v20 = (struct DESK *)*((_QWORD *)v11 + 8);
            if ( (*((_DWORD *)v20 + 12) & 0x8000) != 0 )
            {
              if ( ((unsigned __int8)v12 & *((_BYTE *)v20 + 56)) != 0 )
              {
                (*(void (__fastcall **)(struct DESK *))(*(_QWORD *)v20 + 16LL))(v20);
                *(_DWORD *)(*((_QWORD *)v11 + 8) + 56LL) &= ~0x10u;
              }
              DeskWmDestroy(v11, a2);
            }
            else
            {
              DeskUnloadDesk(v20, 5u);
              v11 = CtlHctlOfHwnd(a2);
            }
            goto LABEL_179;
          case 3u:
            if ( IsZoomed(a2) )
              COcx::OnSize(v11);
            COcx::OnMove(v11);
            goto LABEL_179;
          case 5u:
            if ( !a4 )
              (*(void (__fastcall **)(__int64, struct CTL *, _QWORD))(*(_QWORD *)(*((_QWORD *)v11 + 8) + 40LL) + 120LL))(
                *((_QWORD *)v11 + 8) + 40LL,
                v11,
                0);
            COcx::OnSize(v11);
            if ( a4 != (HMENU)1 )
              EvtErrFire(v11, 0, 0);
            goto LABEL_179;
        }
        if ( a3 != 6 )
        {
          if ( a3 == 7 )
          {
            DefWmSetFocus(v11);
            if ( !Mode_break && (int)COcx::GetState(v11) >= 3 )
            {
              COcx::TransitionTo(v11, 5, 0);
              if ( ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 8) + 48LL)) != 0
                && ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 6) + 116LL)) != 0 )
              {
                v47 = 0;
                if ( (int)COcx::QueryCachedInterface(v11, 3, &v47) >= 0
                  && (*(int (__fastcall **)(__int64, HWND *))(*(_QWORD *)v47 + 24LL))(v47, &hWnd) >= 0
                  && hWnd )
                {
                  SetFocus(hWnd);
                }
                if ( v47 )
                  (*(void (__fastcall **)(__int64))(*(_QWORD *)v47 + 16LL))(v47);
              }
            }
            if ( ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 8) + 48LL)) == 0
              && ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 6) + 116LL)) != 0 )
            {
              if ( (*((_DWORD *)v11 + 10) & 0x800000) != 0 )
              {
                OleCFormActivate(v11, 1);
              }
              else
              {
                EnableWindow(*((HWND *)v11 + 11), 0);
                _ResetFocus(v11, *((HWND *)v11 + 11), *((HWND *)v11 + 11));
              }
            }
            return 0;
          }
          if ( a3 != 16 )
            goto LABEL_179;
          v14 = DeskWmClose(v11);
          goto LABEL_17;
        }
        PbrsUpdate(0);
        if ( v11 )
          v15 = *(void **)(*((_QWORD *)v11 + 8) + 80LL);
        else
          v15 = &g_ThreadData;
        if ( v15 )
        {
          v16 = (CMsoComponent *)*((_QWORD *)v15 + 124);
          if ( v16 )
            CMsoComponent::SetActiveComponent(v16, (_WORD)a4 != 0, 2u);
        }
        v17 = v11;
        if ( (_WORD)a4 )
          goto LABEL_41;
        v18 = 0;
        v19 = 0;
        goto LABEL_43;
      }
      switch ( a3 )
      {
        case 0x21u:
          if ( v11 )
            v23 = *(_QWORD **)(*((_QWORD *)v11 + 8) + 80LL);
          else
            v23 = &g_ThreadData;
          if ( v23 )
          {
            v24 = v23[124];
            if ( v24 )
            {
              if ( *(_DWORD *)(v24 + 48) )
              {
                MessageBeep(0);
                return 4;
              }
            }
          }
          goto LABEL_179;
        case 0x22u:
          goto LABEL_179;
        case 0x47u:
          if ( !IsIconic(a2) )
          {
            DeskStashClientRect(v11);
            PbrsUpdateCoord(v11);
          }
          goto LABEL_179;
        case 0x53u:
          PrintFullPath = CFileRep::GetPrintFullPath((CFileRep *)(*(_QWORD *)(*((_QWORD *)v11 + 66) + 40LL) + 256LL));
          if ( (*((_DWORD *)v11 + 160) & 0x2000) != 0 && PrintFullPath && *PrintFullPath )
            CallHelp(a2, PrintFullPath, *((_DWORD *)v11 + 62) != 0 ? 1 : 3, *((_DWORD *)v11 + 62));
          return 1;
        case 0x81u:
          if ( ((_DWORD)lParam[12] & 0xC00000) != 0xC00000 )
            SetWindowLongA(a2, -16, *((_DWORD *)lParam + 12));
          goto LABEL_179;
      }
      if ( a3 != 134 )
      {
LABEL_179:
        v45 = VBDefControlProc((int)v11, (int)a2, a3, (int)a4, (LPARAM)lParam);
        if ( a3 == 24 )
        {
          v44 = *((_QWORD *)v11 + 8);
          if ( ((unsigned __int8)v12 & *(_BYTE *)(v44 + 48)) != 0 && a4 )
            ProjNotifyDesignerWinVisible(*(struct CProjitemVisual **)(*(_QWORD *)(v44 + 136) + 120LL));
          if ( (_WORD)lParam == 3 )
            UpdateWindow(a2);
        }
        else if ( a3 > 0x84 )
        {
          if ( a3 <= 0x86 )
          {
            if ( !Sys_fWin95Shell && !IsIconic(a2) )
              DeskDraw3DFrame(a2);
          }
          else if ( a3 == 274 )
          {
            DeskPostWmSysCommand(v11, (unsigned __int64)a4);
          }
        }
        return v45;
      }
      v14 = DeskWmNcActivate(a2, v11, (unsigned __int64)a4);
    }
LABEL_17:
    if ( v14 )
      return 0;
    goto LABEL_179;
  }
  if ( a3 <= 0x104B )
  {
    switch ( a3 )
    {
      case 0x104Bu:
        goto LABEL_152;
      case 0x117u:
        if ( v11 )
        {
          v39 = *((_QWORD *)v11 + 6);
          if ( v39 )
          {
            if ( ((unsigned __int8)v12 & *(_BYTE *)(v39 + 116)) != 0 )
              return (int)_Form3InitSysMenu(a2, a4);
          }
        }
        goto LABEL_179;
      case 0x222u:
LABEL_152:
        (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v11 + 8) + 40LL) + 96LL))(*((_QWORD *)v11 + 8) + 40LL);
        if ( lParam == a2 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)(*((_QWORD *)v11 + 8) + 40LL) + 96LL))(*((_QWORD *)v11 + 8) + 40LL);
          v17 = v11;
LABEL_41:
          DeskUpdateActivation(v17, a2);
          return 1;
        }
        v18 = lParam;
        v19 = 1;
        v17 = v11;
LABEL_43:
        DeskUpdateDeactivation(v17, v19, v18);
        return 1;
    }
    if ( a3 != 4097 )
    {
      v25 = a3 - 4097 - v12;
      if ( v25 )
      {
        v26 = v25 - 33;
        if ( v26 )
        {
          if ( v26 == 17 )
          {
            DeskUpdateActivation(v11, a2);
            if ( v11 )
            {
              if ( *((_QWORD *)v11 + 68) )
              {
                v27 = *((_QWORD *)v11 + 8);
                if ( v27 )
                {
                  if ( (*(_DWORD *)(v27 + 48) & 0x4000) == 0 )
                    RestoreIPActiveObjectTools(*(struct IOleInPlaceActiveObject **)(v27 + 352));
                }
              }
            }
            PbarTrackCtl(v11);
            PbrsBrowseProjitem(*(struct Projitem **)(*(_QWORD *)(*((_QWORD *)v11 + 8) + 136LL) + 120LL));
          }
          goto LABEL_179;
        }
        COcx::Paint(v11, *(HDC *)lParam, *((struct _RECTL **)lParam + 2), *((struct _RECTL **)lParam + 3), 0);
        return 0;
      }
      if ( a4 == (HMENU)261 )
      {
        LODWORD(result) = ShowMethHide(v11, (__int64 *)lParam);
      }
      else if ( a4 == (HMENU)263 )
      {
        LODWORD(result) = PrntMethPrintForm(v11, (__int64 *)lParam);
      }
      else
      {
        if ( a4 != (HMENU)267 )
        {
          if ( a4 == (HMENU)300 )
          {
            v28 = (HWND)*((_QWORD *)v11 + 11);
            if ( v28 && IsWindowVisible(v28) && (*((_DWORD *)v11 + 160) & 0x2000) != 0 )
            {
              v29 = (HWND)*((_QWORD *)v11 + 11);
              LODWORD(v47) = 0;
              CommonGizWndProc(v11, v29, 0x112u, 0xF180u, 0, (unsigned int *)&v47);
            }
            return 0;
          }
          goto LABEL_179;
        }
        LODWORD(result) = ShowMethShow(v11, (__int64 *)lParam);
      }
      return (unsigned int)result;
    }
    if ( ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 8) + 48LL)) != 0 )
    {
      v30 = *((_QWORD *)v11 + 6);
      if ( *(_QWORD *)(v30 + 8) )
        v30 = *(_QWORD *)(v30 + 8);
      if ( (*(_WORD *)(v30 + 112) & 0x800) != 0 )
        StdErrSetCaption(v11, *(char **)(*((_QWORD *)v11 + 10) + 8LL));
    }
    if ( (unsigned int)COcx::GetState(v11) )
      goto LABEL_136;
    v31 = COcx::Load(v11, 1, *(_QWORD *)(*(_QWORD *)(*(_QWORD *)(*((_QWORD *)v11 + 8) + 136LL) + 120LL) + 48LL));
    if ( v31 >= 0 )
    {
      if ( ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 8) + 48LL)) == 0 )
      {
        v32 = *((_DWORD *)v11 + 170);
        if ( v32 )
          v31 = CDFrame::VerifyDynamicCookie(v11, v32);
      }
      if ( v31 >= 0 )
      {
LABEL_136:
        v34 = (_QWORD *)*((_QWORD *)v11 + 6);
        v35 = v34;
        if ( v34[1] )
          v35 = (_QWORD *)v34[1];
        if ( (v35[14] & 0x800) == 0 )
        {
          v36 = 13;
          if ( *(struct tagPROP * near ***)(*v34 + 56LL) == &XFRAME_DFrame_rgbpprop )
            v36 = 9;
          (*(void (__fastcall **)(struct CTL *, __int64, __int64 *))(*(_QWORD *)v11 + 80LL))(v11, v36, &v47);
          v37 = OleCEnableEmbedding(*((struct IUnknown **)v11 + 57), v47);
          if ( v37 < 0 )
            goto LABEL_145;
          v38 = 29;
          if ( *(struct tagPROP * near ***)(**((_QWORD **)v11 + 6) + 56LL) == &XFRAME_DFrame_rgbpprop )
            v38 = 69;
          (*(void (__fastcall **)(struct CTL *, __int64, __int64 *))(*(_QWORD *)v11 + 80LL))(v11, v38, &v47);
          v37 = OleCRightToLeftEmbedding(*((struct IUnknown **)v11 + 57), v47);
          BidiSetStyle32(a2, v47, 12288);
          COcx::FireAmbientChange(v11, -732);
          if ( v37 < 0 )
          {
LABEL_145:
            v33 = v37;
            goto LABEL_134;
          }
        }
        v31 = COcx::SetActivation(v11);
        if ( v31 >= 0 )
          return 0;
      }
    }
    v33 = v31;
LABEL_134:
    LODWORD(result) = _ErrFromHrDefault(v33);
    return (unsigned int)result;
  }
  switch ( a3 )
  {
    case 0x105Au:
      DeskVbmCheckFocus(v11);
      return 0;
    case 0x105Cu:
      v42 = *((_QWORD *)v11 + 81);
      if ( v42 )
      {
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v42 + 16LL))(v42);
        *((_QWORD *)v11 + 81) = 0;
      }
      v43 = (void *)*((_QWORD *)v11 + 82);
      if ( v43 )
      {
        DeleteObject(v43);
        *((_QWORD *)v11 + 82) = 0;
      }
      goto LABEL_179;
    case 0x105Du:
      v41 = *((_QWORD *)v11 + 8);
      if ( ((unsigned __int8)v12 & *(_BYTE *)(v41 + 48)) != 0 || (*(_DWORD *)(v41 + 48) & 0x1000) != 0 )
      {
        CtlShowWindow(v11, a4 != 0 ? 5 : 0);
        if ( ((unsigned __int8)v12 & *(_BYTE *)(*((_QWORD *)v11 + 8) + 48LL)) != 0 )
          BringWindowToTop(a2);
      }
      else
      {
        if ( a4 )
          DeskShowWindow(v11, (*((_DWORD *)v11 + 160) & 0x800) == 0);
        else
          DeskHideWindow(v11);
        *((_DWORD *)v11 + 160) &= ~0x800u;
      }
      return 0;
    case 0x105Fu:
      *(_DWORD *)(*((_QWORD *)v11 + 8) + 48LL) &= ~8u;
      goto LABEL_179;
    case 0x1081u:
      COcx::DiscardObject(v11);
      goto LABEL_179;
  }
  if ( a3 != 4235 )
    goto LABEL_179;
  DeskStashClientRect(v11);
  v40 = COcx::Load(v11, 0, 0);
  (*(void (__fastcall **)(struct CTL *))(*(_QWORD *)v11 + 184LL))(v11);
  if ( v40 < 0 )
    return _ErrFromHrDefault(v40);
  v40 = COcx::SetActivation(v11);
  if ( v40 < 0 )
    return _ErrFromHrDefault(v40);
  return v7;
}

```

## disassembly

```asm
0x18000c098  mov     [rsp-28h+arg_0], rbx
0x18000c09d  mov     [rsp-28h+arg_10], rsi
0x18000c0a2  mov     [rsp-28h+arg_18], rdi
0x18000c0a7  push    rbp
0x18000c0a8  push    r12
0x18000c0aa  push    r13
0x18000c0ac  push    r14
0x18000c0ae  push    r15
0x18000c0b0  mov     rbp, rsp
0x18000c0b3  mov     eax, 40h
0x18000c0b8  call    _alloca_probe
0x18000c0bd  sub     rsp, rax
0x18000c0c0  mov     r12, [rbp+arg_20]
0x18000c0c4  xor     edi, edi
0x18000c0c6  mov     r14, r9
0x18000c0c9  mov     r15d, r8d
0x18000c0cc  mov     rsi, rdx
0x18000c0cf  mov     rbx, rcx
0x18000c0d2  lea     r13d, [rax-30h]
0x18000c0d6  test    rdx, rdx
0x18000c0d9  jz      short loc_18000C10C
0x18000c0db  mov     rax, [rcx+40h]
0x18000c0df  test    [rax+30h], r13b
0x18000c0e3  jz      short loc_18000C10C
0x18000c0e5  lea     rax, [rbp+var_10]
0x18000c0e9  mov     r9, r12; __int64
0x18000c0ec  mov     r8, r14; unsigned __int64
0x18000c0ef  mov     edx, r15d; unsigned int
0x18000c0f2  mov     rcx, rsi; HWND
0x18000c0f5  mov     [rsp+40h+lParam], rax; __int64 *
0x18000c0fa  call    ?FDesFilter@@YAHPEAUHWND__@@I_K_JPEA_J@Z; FDesFilter(HWND__ *,uint,unsigned __int64,__int64,__int64 *)
0x18000c0ff  test    eax, eax
0x18000c101  jz      short loc_18000C10C
0x18000c103  mov     rax, [rbp+var_10]
0x18000c107  jmp     loc_18000CADA
0x18000c10c  mov     eax, 112h
0x18000c111  cmp     r15d, eax
0x18000c114  ja      loc_18000C5A8
0x18000c11a  jz      loc_18000C595
0x18000c120  cmp     r15d, 18h
0x18000c124  ja      loc_18000C458
0x18000c12a  jz      loc_18000C39F
0x18000c130  mov     eax, r15d
0x18000c133  dec     eax
0x18000c135  jz      loc_18000C37A
0x18000c13b  dec     eax
0x18000c13d  jz      loc_18000C32E
0x18000c143  dec     eax
0x18000c145  jz      loc_18000C30C
0x18000c14b  sub     eax, 2
0x18000c14e  jz      loc_18000C2CF
0x18000c154  dec     eax
0x18000c156  jz      loc_18000C266
0x18000c15c  dec     eax
0x18000c15e  jz      short loc_18000C182
0x18000c160  mov     ecx, 9
0x18000c165  cmp     eax, ecx
0x18000c167  jnz     loc_18000CA16
0x18000c16d  mov     rcx, rbx; struct CTL *
0x18000c170  call    ?DeskWmClose@@YAHPEAUCTL@@@Z; DeskWmClose(CTL *)
0x18000c175  test    eax, eax
0x18000c177  jz      loc_18000CA16
0x18000c17d  jmp     loc_18000CAD8
0x18000c182  mov     rcx, rbx; struct CTL *
0x18000c185  call    ?DefWmSetFocus@@YAXPEAUCTL@@@Z; DefWmSetFocus(CTL *)
0x18000c18a  cmp     cs:?Mode_break@@3W4BREAKMODE@@A, edi; BREAKMODE Mode_break
0x18000c190  jnz     short loc_18000C20F
0x18000c192  mov     rcx, rbx
0x18000c195  call    ?GetState@COcx@@IEAA?AW4OC_STATE@@XZ; COcx::GetState(void)
0x18000c19a  mov     r14d, 3
0x18000c1a0  cmp     eax, r14d
0x18000c1a3  jl      short loc_18000C20F
0x18000c1a5  lea     edx, [r14+2]
0x18000c1a9  xor     r8d, r8d
0x18000c1ac  mov     rcx, rbx
0x18000c1af  call    ?TransitionTo@COcx@@QEAAJW4OC_STATE@@PEAUtagMSG@@@Z; COcx::TransitionTo(OC_STATE,tagMSG *)
0x18000c1b4  mov     r11, [rbx+40h]
0x18000c1b8  test    [r11+30h], r13b
0x18000c1bc  jz      short loc_18000C20F
0x18000c1be  mov     rax, [rbx+30h]
0x18000c1c2  test    [rax+74h], r13b
0x18000c1c6  jz      short loc_18000C20F
0x18000c1c8  lea     r8, [rbp+arg_8]
0x18000c1cc  mov     edx, r14d
0x18000c1cf  mov     rcx, rbx
0x18000c1d2  mov     [rbp+arg_8], rdi
0x18000c1d6  call    ?QueryCachedInterface@COcx@@IEAAJW4ITFX@@PEAPEAX@Z; COcx::QueryCachedInterface(ITFX,void * *)
0x18000c1db  test    eax, eax
0x18000c1dd  js      short loc_18000C200
0x18000c1df  mov     rcx, [rbp+arg_8]
0x18000c1e3  lea     rdx, [rbp+hWnd]
0x18000c1e7  mov     rax, [rcx]
0x18000c1ea  call    qword ptr [rax+18h]
0x18000c1ed  test    eax, eax
0x18000c1ef  js      short loc_18000C200
0x18000c1f1  mov     rcx, [rbp+hWnd]; hWnd
0x18000c1f5  test    rcx, rcx
0x18000c1f8  jz      short loc_18000C200
0x18000c1fa  call    cs:__imp_SetFocus
0x18000c200  mov     rcx, [rbp+arg_8]
0x18000c204  test    rcx, rcx
0x18000c207  jz      short loc_18000C20F
0x18000c209  mov     rax, [rcx]
0x18000c20c  call    qword ptr [rax+10h]
0x18000c20f  mov     rax, [rbx+40h]
0x18000c213  test    [rax+30h], r13b
0x18000c217  jnz     loc_18000CAD8
0x18000c21d  mov     rax, [rbx+30h]
0x18000c221  test    [rax+74h], r13b
0x18000c225  jz      loc_18000CAD8
0x18000c22b  test    dword ptr [rbx+28h], 800000h
0x18000c232  jnz     short loc_18000C254
0x18000c234  mov     rcx, [rbx+58h]; hWnd
0x18000c238  xor     edx, edx; bEnable
0x18000c23a  call    cs:__imp_EnableWindow
0x18000c240  mov     rdx, [rbx+58h]; HWND
0x18000c244  mov     rcx, rbx; struct CTL *
0x18000c247  mov     r8, rdx; HWND
0x18000c24a  call    ?_ResetFocus@@YAHPEAUCTL@@PEAUHWND__@@1@Z; _ResetFocus(CTL *,HWND__ *,HWND__ *)
0x18000c24f  jmp     loc_18000CAD8
0x18000c254  mov     edx, 1; int
0x18000c259  mov     rcx, rbx; struct CTL *
0x18000c25c  call    ?OleCFormActivate@@YAXPEAUCTL@@H@Z; OleCFormActivate(CTL *,int)
0x18000c261  jmp     loc_18000CAD8
0x18000c266  xor     ecx, ecx; int
0x18000c268  call    ?PbrsUpdate@@YAXH@Z; PbrsUpdate(int)
0x18000c26d  test    rbx, rbx
0x18000c270  jz      short loc_18000C27C
0x18000c272  mov     rax, [rbx+40h]
0x18000c276  mov     rcx, [rax+50h]
0x18000c27a  jmp     short loc_18000C283
0x18000c27c  lea     rcx, ?g_ThreadData@@3VCThreadData@@A; CThreadData g_ThreadData
0x18000c283  test    rcx, rcx
0x18000c286  jz      short loc_18000C2A8
0x18000c288  mov     rcx, [rcx+3E0h]; this
0x18000c28f  test    rcx, rcx
0x18000c292  jz      short loc_18000C2A8
0x18000c294  test    r14w, r14w
0x18000c298  mov     edx, edi
0x18000c29a  mov     r8d, 2; unsigned int
0x18000c2a0  setnz   dl; int
0x18000c2a3  call    ?SetActiveComponent@CMsoComponent@@QEAAXHK@Z; CMsoComponent::SetActiveComponent(int,ulong)
0x18000c2a8  mov     rcx, rbx; struct CTL *
0x18000c2ab  test    r14w, r14w
0x18000c2af  jz      short loc_18000C2BB
0x18000c2b1  mov     rdx, rsi; HWND
0x18000c2b4  call    ?DeskUpdateActivation@@YAXPEAUCTL@@PEAUHWND__@@@Z; DeskUpdateActivation(CTL *,HWND__ *)
0x18000c2b9  jmp     short loc_18000C2C5
0x18000c2bb  xor     r8d, r8d; HWND
0x18000c2be  xor     edx, edx; int
0x18000c2c0  call    ?DeskUpdateDeactivation@@YAXPEAUCTL@@HPEAUHWND__@@@Z; DeskUpdateDeactivation(CTL *,int,HWND__ *)
0x18000c2c5  mov     eax, 1
0x18000c2ca  jmp     loc_18000CADA
0x18000c2cf  test    r14, r14
0x18000c2d2  jnz     short loc_18000C2E8
0x18000c2d4  mov     rcx, [rbx+40h]
0x18000c2d8  xor     r8d, r8d
0x18000c2db  mov     rdx, rbx
0x18000c2de  add     rcx, 28h ; '('
0x18000c2e2  mov     rax, [rcx]
0x18000c2e5  call    qword ptr [rax+78h]
0x18000c2e8  mov     rcx, rbx; this
0x18000c2eb  call    ?OnSize@COcx@@IEAAXXZ; COcx::OnSize(void)
0x18000c2f0  cmp     r14, 1
0x18000c2f4  jz      loc_18000CA16
0x18000c2fa  xor     r8d, r8d
0x18000c2fd  xor     edx, edx
0x18000c2ff  mov     rcx, rbx
0x18000c302  call    EvtErrFire
0x18000c307  jmp     loc_18000CA16
0x18000c30c  mov     rcx, rsi; hWnd
0x18000c30f  call    cs:__imp_IsZoomed
0x18000c315  test    eax, eax
0x18000c317  jz      short loc_18000C321
0x18000c319  mov     rcx, rbx; this
0x18000c31c  call    ?OnSize@COcx@@IEAAXXZ; COcx::OnSize(void)
0x18000c321  mov     rcx, rbx; this
0x18000c324  call    ?OnMove@COcx@@IEAAXXZ; COcx::OnMove(void)
0x18000c329  jmp     loc_18000CA16
0x18000c32e  mov     rcx, [rbx+40h]; struct DESK *
0x18000c332  test    dword ptr [rcx+30h], 8000h
0x18000c339  jnz     short loc_18000C355
0x18000c33b  mov     edx, 5; unsigned int
0x18000c340  call    ?DeskUnloadDesk@@YAJPEAVDESK@@I@Z; DeskUnloadDesk(DESK *,uint)
0x18000c345  mov     rcx, rsi; HWND
0x18000c348  call    ?CtlHctlOfHwnd@@YAPEAUCTL@@PEAUHWND__@@@Z; CtlHctlOfHwnd(HWND__ *)
0x18000c34d  mov     rbx, rax
0x18000c350  jmp     loc_18000CA16
0x18000c355  test    [rcx+38h], r13b
0x18000c359  jz      short loc_18000C36A
0x18000c35b  mov     rax, [rcx]
0x18000c35e  call    qword ptr [rax+10h]
0x18000c361  mov     r11, [rbx+40h]
0x18000c365  and     dword ptr [r11+38h], 0FFFFFFEFh
0x18000c36a  mov     rdx, rsi; HWND
0x18000c36d  mov     rcx, rbx; struct CTL *
0x18000c370  call    ?DeskWmDestroy@@YAXPEAUCTL@@PEAUHWND__@@@Z; DeskWmDestroy(CTL *,HWND__ *)
0x18000c375  jmp     loc_18000CA16
0x18000c37a  mov     rax, [rbx+40h]
0x18000c37e  test    [rax+30h], r13b
0x18000c382  jnz     loc_18000CA16
0x18000c388  xor     edx, edx; bRevert
0x18000c38a  mov     rcx, rsi; hWnd
0x18000c38d  call    cs:__imp_GetSystemMenu
0x18000c393  mov     [rbx+2A0h], rax
0x18000c39a  jmp     loc_18000CA16
0x18000c39f  mov     rcx, [rbx+40h]
0x18000c3a3  test    [rcx+30h], r13b
0x18000c3a7  jz      short loc_18000C3F0
0x18000c3a9  test    r14, r14
0x18000c3ac  jnz     short loc_18000C3DB
0x18000c3ae  mov     rax, [rcx+88h]
0x18000c3b5  mov     rcx, [rax+78h]
0x18000c3b9  mov     rax, [rcx+0C8h]
0x18000c3c0  cmp     cs:?Pbrs_pprojwinitemVis@@3PEAVCProjWinItem@@EA, rax; CProjWinItem * Pbrs_pprojwinitemVis
0x18000c3c7  jnz     loc_18000CA16
0x18000c3cd  lea     ecx, [r14+1]; int
0x18000c3d1  call    ?PbrsUpdate@@YAXH@Z; PbrsUpdate(int)
0x18000c3d6  jmp     loc_18000CA16
0x18000c3db  mov     rcx, [rcx+88h]
0x18000c3e2  mov     rcx, [rcx+78h]; struct CProjitemVisual *
0x18000c3e6  call    ?ProjNotifyDesignerWinVisible@@YAXPEAVCProjitemVisual@@@Z; ProjNotifyDesignerWinVisible(CProjitemVisual *)
0x18000c3eb  jmp     loc_18000CA16
0x18000c3f0  cmp     r14, 1
0x18000c3f4  jnz     short loc_18000C431
0x18000c3f6  test    r12, r12
0x18000c3f9  jnz     short loc_18000C424
0x18000c3fb  mov     rcx, rsi; hWnd
0x18000c3fe  call    cs:__imp_IsWindowVisible
0x18000c404  test    eax, eax
0x18000c406  jz      short loc_18000C412
0x18000c408  mov     rax, [rbx+40h]
0x18000c40c  test    [rax+38h], r13b
0x18000c410  jnz     short loc_18000C424
0x18000c412  mov     rcx, [rbx+40h]
0x18000c416  mov     rax, [rcx]
0x18000c419  call    qword ptr [rax+8]
0x18000c41c  mov     r11, [rbx+40h]
0x18000c420  or      [r11+38h], r13d
0x18000c424  mov     rcx, rsi; HWND
0x18000c427  call    ?MoveOfficeAssistant@@YAXPEAUHWND__@@@Z; MoveOfficeAssistant(HWND__ *)
0x18000c42c  jmp     loc_18000CA16
0x18000c431  test    r12, r12
0x18000c434  jnz     loc_18000CA16
0x18000c43a  test    [rcx+38h], r13b
0x18000c43e  jz      loc_18000CA16
0x18000c444  mov     rax, [rcx]
0x18000c447  call    qword ptr [rax+10h]
0x18000c44a  mov     r11, [rbx+40h]
0x18000c44e  and     dword ptr [r11+38h], 0FFFFFFEFh
0x18000c453  jmp     loc_18000CA16
0x18000c458  mov     eax, r15d
0x18000c45b  sub     eax, 21h ; '!'
0x18000c45e  jz      loc_18000C54B
0x18000c464  dec     eax
0x18000c466  jz      loc_18000CA16
0x18000c46c  sub     eax, 25h ; '%'
0x18000c46f  jz      loc_18000C525
0x18000c475  sub     eax, 0Ch
0x18000c478  jz      short loc_18000C4C5
0x18000c47a  sub     eax, 2Eh ; '.'
0x18000c47d  jz      short loc_18000C49B
0x18000c47f  cmp     eax, 5
0x18000c482  jnz     loc_18000CA16
0x18000c488  mov     r8, r14; unsigned __int64
0x18000c48b  mov     rdx, rbx; struct CTL *
0x18000c48e  mov     rcx, rsi; HWND
0x18000c491  call    ?DeskWmNcActivate@@YAHPEAUHWND__@@PEAUCTL@@_K@Z; DeskWmNcActivate(HWND__ *,CTL *,unsigned __int64)
0x18000c496  jmp     loc_18000C175
0x18000c49b  mov     r8d, [r12+30h]; dwNewLong
0x18000c4a0  mov     ecx, 0C00000h
0x18000c4a5  mov     eax, r8d
0x18000c4a8  and     eax, ecx
0x18000c4aa  cmp     eax, ecx
0x18000c4ac  jz      loc_18000CA16
0x18000c4b2  mov     edx, 0FFFFFFF0h; nIndex
0x18000c4b7  mov     rcx, rsi; hWnd
0x18000c4ba  call    cs:__imp_SetWindowLongA
0x18000c4c0  jmp     loc_18000CA16
0x18000c4c5  mov     rax, [rbx+210h]
0x18000c4cc  mov     rcx, [rax+28h]
0x18000c4d0  add     rcx, 100h; this
0x18000c4d7  call    ?GetPrintFullPath@CFileRep@@QEAAPEBDXZ; CFileRep::GetPrintFullPath(void)
0x18000c4dc  test    dword ptr [rbx+280h], 2000h
0x18000c4e6  jz      loc_18000C2C5
0x18000c4ec  test    rax, rax
0x18000c4ef  jz      loc_18000C2C5
0x18000c4f5  cmp     [rax], dil
0x18000c4f8  jz      loc_18000C2C5
0x18000c4fe  mov     r9d, [rbx+0F8h]; int
0x18000c505  mov     rdx, rax; char *
0x18000c508  mov     ecx, r9d
0x18000c50b  neg     ecx
0x18000c50d  mov     rcx, rsi; HWND
0x18000c510  sbb     r8d, r8d
0x18000c513  and     r8d, 0FFFFFFFEh
0x18000c517  add     r8d, 3; unsigned int
0x18000c51b  call    ?CallHelp@@YAHPEAUHWND__@@PEBDIJ@Z; CallHelp(HWND__ *,char const *,uint,long)
0x18000c520  jmp     loc_18000C2C5
0x18000c525  mov     rcx, rsi; hWnd
  ... truncated ...
```
