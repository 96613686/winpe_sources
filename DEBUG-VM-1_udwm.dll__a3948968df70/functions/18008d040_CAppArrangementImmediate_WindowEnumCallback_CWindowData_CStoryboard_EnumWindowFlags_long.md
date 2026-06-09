# CAppArrangementImmediate::_WindowEnumCallback(CWindowData *,CStoryboard::EnumWindowFlags,long *)

- ea: `0x18008d040`
- end: `0x18008da92`
- name: `?_WindowEnumCallback@CAppArrangementImmediate@@EEAA_NPEAVCWindowData@@W4EnumWindowFlags@CStoryboard@@PEAJ@Z`
- size: `2642`
- prototype: ``
- caller_count: `0`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180005ab0`
- `0x180008350`
- `0x180008384`
- `0x18001ce00`
- `0x18001f43c`
- `0x18002d098`
- `0x180045c80`
- `0x180064974`
- `0x180068aa4`
- `0x180068af0`
- `0x180071758`
- `0x180077390`
- `0x18008985c`
- `0x18008b31c`
- `0x18008d040`
- `0x18008da98`
- `0x18008e8f8`
- `0x180095130`
- `0x1800c2e30`
- `0x1800c3580`
- `0x1800c5288`
- `0x1800c5464`
- `0x1800c5700`
- `0x1800c5b40`
- `0x1800c5bac`
- `0x1800c5c6c`
- `0x1800c5f88`
- `0x1800c5fc4`
- `0x1800c62d8`
- `0x1800c6900`
- `0x1800ced50`
- `0x1800cede4`

## import_xrefs

- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18008d2db`
- `api-ms-win-core-kernel32-legacy-l1-1-0!MulDiv` at `0x18008d2db`
- `USER32!OffsetRect` at `0x18008d80e`
- `USER32!OffsetRect` at `0x18008d821`
- `USER32!OffsetRect` at `0x18008d80e`
- `USER32!OffsetRect` at `0x18008d821`
- `USER32!IsRectEmpty` at `0x18008d5bb`
- `USER32!IsRectEmpty` at `0x18008d5bb`

## pseudocode

```c
char __fastcall CAppArrangementImmediate::_WindowEnumCallback(__int64 a1, __int64 a2, char a3, int *a4)
{
  int v4; // r15d
  struct CAnimationComponent *v5; // r14
  int *v6; // r12
  unsigned int v10; // esi
  unsigned __int64 v11; // rax
  __int64 v12; // rcx
  unsigned __int64 v13; // rax
  __int64 v14; // rcx
  char SpecialTargetInfo; // bl
  unsigned int PVLTarget; // eax
  int v17; // eax
  int BitmapRects; // eax
  __int64 v19; // rdx
  int *v20; // rax
  int v21; // ebx
  int v22; // r12d
  __int64 v23; // rdx
  __int64 v24; // rbx
  int *v25; // rcx
  int v26; // r12d
  int v27; // edx
  int v28; // eax
  __int64 v29; // rdx
  int v30; // r11d
  unsigned int v31; // r9d
  int v32; // r12d
  bool v33; // zf
  unsigned int v34; // ecx
  int v35; // eax
  int v36; // eax
  int v37; // ebx
  __int64 v38; // rdx
  int v39; // eax
  int v40; // eax
  int v41; // eax
  bool v42; // zf
  struct tagRECT *v43; // rbx
  int v44; // eax
  int v45; // eax
  int v46; // eax
  int v47; // eax
  unsigned int v48; // ebx
  int v49; // r9d
  int v50; // eax
  int v51; // eax
  unsigned __int64 v52; // rax
  __int64 v53; // rcx
  struct tagRECT v54; // xmm0
  float v55; // xmm6_4
  float v56; // xmm1_4
  const struct CDesktopManager::WindowAnimationSettings *WindowAnimationSettings; // rax
  const struct CDesktopManager::WindowAnimationSettings *v58; // rbx
  float v59; // xmm1_4
  struct tagRECT *v60; // rax
  CAnimatedTransitionVisual **v61; // rbx
  CBaseObject *v62; // rsi
  CBaseObject *v63; // rdi
  bool v65; // [rsp+58h] [rbp-B0h]
  char v66; // [rsp+59h] [rbp-AFh]
  char v67; // [rsp+5Ah] [rbp-AEh]
  struct CAnimationComponent *v68; // [rsp+60h] [rbp-A8h] BYREF
  int nNumber[2]; // [rsp+68h] [rbp-A0h] BYREF
  CBaseObject *v70; // [rsp+70h] [rbp-98h] BYREF
  CBaseObject *v71; // [rsp+78h] [rbp-90h] BYREF
  int dy[2]; // [rsp+80h] [rbp-88h]
  int v73; // [rsp+88h] [rbp-80h]
  int v74; // [rsp+8Ch] [rbp-7Ch]
  int *v75; // [rsp+90h] [rbp-78h]
  CBaseObject *v76; // [rsp+98h] [rbp-70h] BYREF
  struct tagRECT v77; // [rsp+A0h] [rbp-68h] BYREF
  struct tagRECT v78; // [rsp+B8h] [rbp-50h] BYREF
  struct tagRECT rc; // [rsp+C8h] [rbp-40h] BYREF
  struct tagRECT v80; // [rsp+D8h] [rbp-30h] BYREF
  struct tagRECT v81; // [rsp+E8h] [rbp-20h] BYREF

  v75 = a4;
  v4 = 0;
  v68 = 0;
  v5 = 0;
  v71 = 0;
  v70 = 0;
  v6 = a4;
  v76 = 0;
  CAppArrangementBase::_WindowEnumCallback();
  if ( (a3 & 1) == 0 )
    goto LABEL_169;
  v10 = *(_DWORD *)(a2 + 744) & 0xFFF;
  *(_QWORD *)dy = 0;
  v78 = 0;
  v11 = v10 - 29;
  rc = 0;
  v77 = 0;
  v81 = 0;
  if ( (unsigned int)v11 > 0x25 || (v12 = 0x2000020491LL, v65 = 1, !_bittest64(&v12, v11)) )
    v65 = 0;
  v13 = v10 - 23;
  if ( (unsigned int)v13 <= 0x2D && (v14 = 0x280000210061LL, _bittest64(&v14, v13))
    || (v66 = 0, CGroupingStoryboard::_IsPartOfGroup((CGroupingStoryboard *)a1, (struct CWindowData *)a2)) )
  {
    v66 = 1;
  }
  SpecialTargetInfo = CAppArrangementImmediate::GetSpecialTargetInfo(a1, v10);
  if ( CStoryboard::_HasUsableBitmapResource((CStoryboard *)a1, *(HWND *)(a2 + 40)) )
  {
    PVLTarget = CAppArrangementImmediate::GetPVLTarget(a1, v10);
    v17 = CStoryboard::_CreateAndAddBitmapAnimationComponent(a1, *(_QWORD *)(a2 + 40), v10, PVLTarget, &v76);
    v4 = v17;
    if ( v17 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v17, 0xCB4u, 0);
      goto LABEL_167;
    }
    BitmapRects = CTransitionVisualController::GetBitmapRects(
                    *((CTransitionVisualController **)CDesktopManager::s_pDesktopManagerInstance + 24),
                    *(HWND *)(a2 + 40),
                    &v77,
                    &v81);
    v4 = BitmapRects;
    if ( BitmapRects < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(
        0x14u,
        &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
        1u,
        BitmapRects,
        0xCB5u,
        0);
      goto LABEL_167;
    }
  }
  v67 = 0;
  v73 = SpecialTargetInfo & 8;
  if ( (SpecialTargetInfo & 8) != 0 )
  {
    v19 = *(unsigned int *)(a2 + 744);
    v20 = (int *)(a2 + 764);
    if ( (v19 & 0x1000000) == 0 )
      v20 = (int *)(a2 + 48);
    v21 = *v20;
    v22 = v20[2];
    v80 = 0;
    if ( (int)CGroupingStoryboard::_GetUnionRect(a1, v19, &v80) >= 0 )
    {
      if ( v21 == v80.left )
        *(_DWORD *)(a2 + 744) &= ~0x10000u;
      if ( v22 == v80.right )
        *(_DWORD *)(a2 + 744) &= ~0x8000u;
    }
    v23 = *(unsigned int *)(a2 + 744);
    nNumber[0] = 0;
    if ( (int)CGroupingStoryboard::_GroupingIndexByTarget(a1, v23, nNumber) >= 0 )
    {
      v24 = 48LL * (unsigned int)nNumber[0];
      if ( *(_QWORD *)(v24 + *(_QWORD *)(a1 + 128) + 32) - *(_QWORD *)(v24 + *(_QWORD *)(a1 + 128) + 24) == 32 )
      {
        v25 = (int *)(a2 + 796);
        if ( (*(_DWORD *)(a2 + 744) & 0x800000) == 0 )
          v25 = (int *)(a2 + 48);
        v26 = v25[2];
        v27 = 0;
        v74 = *v25;
        if ( v25[3] - v25[1] >= 0 )
          v27 = v25[3] - v25[1];
        nNumber[0] = 0;
        if ( (int)CTransitionVisualController::GetGutterWidth(
                    *((CTransitionVisualController **)CDesktopManager::s_pDesktopManagerInstance + 24),
                    v27,
                    nNumber) >= 0 )
        {
          v28 = MulDiv(nNumber[0], 11, 10);
          v29 = *(_QWORD *)(a1 + 128);
          if ( (__int64)(*(_QWORD *)(v24 + v29 + 32) - *(_QWORD *)(v24 + v29 + 24)) >> 4 )
          {
            v30 = v74;
            v31 = 0;
            do
            {
              if ( v30 - *(_DWORD *)(*(_QWORD *)(v29 + v24 + 24) + 16LL * v31 + 8) > v28 )
                *(_DWORD *)(a2 + 744) &= ~0x10000u;
              if ( *(_DWORD *)(*(_QWORD *)(*(_QWORD *)(a1 + 128) + v24 + 24) + 16LL * v31) - v26 > v28 )
                *(_DWORD *)(a2 + 744) &= ~0x8000u;
              v29 = *(_QWORD *)(a1 + 128);
              ++v31;
            }
            while ( v31 < (unsigned __int64)((__int64)(*(_QWORD *)(v29 + v24 + 32) - *(_QWORD *)(v24 + v29 + 24)) >> 4) );
          }
        }
      }
    }
  }
  v32 = 22;
  if ( v10 > 0x2C )
  {
    if ( v10 <= 0x42 )
    {
      if ( v10 == 66 || v10 == 45 || v10 == 46 || v10 == 47 || v10 == 53 )
        goto LABEL_51;
      v34 = v10 - 54;
      v33 = v10 == 54;
      goto LABEL_72;
    }
    if ( v10 == 70 )
      goto LABEL_51;
    if ( v10 != 71 && v10 != 72 && v10 != 73 && v10 != 74 )
    {
      v42 = v10 == 84;
LABEL_80:
      if ( !v42 )
      {
LABEL_103:
        if ( v5 && !v67 )
        {
          if ( (*(_DWORD *)(a2 + 744) & 0x1000000) != 0 )
          {
            if ( CAnimationComponent::IsSnapshot(v5) )
            {
              v52 = v10 - 23;
              if ( (unsigned int)v52 <= 0x2F )
              {
                v53 = 0x800000000121LL;
                if ( _bittest64(&v53, v52) )
                {
                  CStoryboard::ResizeToSnapshot(*(HWND *)(a2 + 40), (const struct tagRECT *)(a2 + 764), &v78);
LABEL_113:
                  CAnimatedTransitionVisual::SetBeginRect(*((CAnimatedTransitionVisual **)v5 + 5), &v78);
                  if ( (*(_DWORD *)(a2 + 744) & 0x800000) != 0 )
                    rc = *(struct tagRECT *)(a2 + 796);
                  else
                    rc = v78;
                  OffsetRect(&rc, dy[0], dy[1]);
                  OffsetRect(&v81, dy[0], dy[1]);
                  CAnimatedTransitionVisual::SetEndRect(*((CAnimatedTransitionVisual **)v5 + 5), &rc);
                  v55 = 0.0;
                  if ( v10 == 20 || v10 == 33 )
                  {
                    *(_BYTE *)(*((_QWORD *)v5 + 5) + 907LL) = 1;
                    if ( *((_DWORD *)v5 + 17) != 2 )
                      *((_DWORD *)v5 + 17) = 1;
                    CAnimatedTransitionVisual::SetEndAlpha(*((CAnimatedTransitionVisual **)v5 + 5), 0.0);
                  }
                  if ( v10 - 72 <= 2 )
                  {
                    WindowAnimationSettings = CDesktopManager::GetWindowAnimationSettings();
                    v58 = WindowAnimationSettings;
                    if ( v10 == 72 )
                      v59 = *(float *)WindowAnimationSettings;
                    else
                      v59 = 0.0;
                    CAnimatedTransitionVisual::SetBeginAlpha(*((CAnimatedTransitionVisual **)v5 + 5), v59);
                    if ( v10 != 72 )
                      v55 = *(float *)v58;
                    CAnimatedTransitionVisual::SetEndAlpha(*((CAnimatedTransitionVisual **)v5 + 5), v55);
                  }
                  else
                  {
                    if ( v10 - 45 <= 1 )
                      v56 = FLOAT_0_44999999;
                    else
                      v56 = FLOAT_1_0;
                    CAnimatedTransitionVisual::SetBeginAlpha(*((CAnimatedTransitionVisual **)v5 + 5), v56);
                  }
                  if ( v10 - 53 <= 1 )
                  {
                    *(_BYTE *)(*((_QWORD *)v5 + 5) + 908LL) = v10 == 54;
                    *(_BYTE *)(*((_QWORD *)v5 + 5) + 920LL) = 1;
                    *(_BYTE *)(*((_QWORD *)v5 + 5) + 907LL) = 1;
                  }
                  goto LABEL_142;
                }
              }
            }
            v54 = *(struct tagRECT *)(a2 + 764);
          }
          else
          {
            v54 = *(struct tagRECT *)((char *)v5 + 88);
          }
          v78 = v54;
          goto LABEL_113;
        }
        if ( v10 == 68 || v10 == 32 )
        {
          v33 = (*(_DWORD *)(a2 + 744) & 0x800000) == 0;
          v60 = (struct tagRECT *)(a2 + 796);
          v78 = *(struct tagRECT *)(a2 + 764);
          if ( v33 )
            v60 = &v78;
          rc = *v60;
LABEL_142:
          v61 = (CAnimatedTransitionVisual **)v76;
          if ( v76 )
          {
            CAnimatedTransitionVisual::SetBeginRect(*((CAnimatedTransitionVisual **)v76 + 5), &v77);
            CAnimatedTransitionVisual::SetEndRect(v61[5], &v81);
          }
          if ( v66 )
          {
            if ( v73 )
              v32 = v10;
            CGroupingStoryboard::_CreateGuttersForApp(a1, a2, &v78, &rc, v32, &v71, &v70);
          }
          if ( v73 )
          {
            if ( v5 )
              CGroupingStoryboard::_SetUnifiedCenter((CGroupingStoryboard *)a1, v5);
            v62 = v71;
            if ( v71 )
              CGroupingStoryboard::_SetUnifiedCenter((CGroupingStoryboard *)a1, v71);
            v63 = v70;
            if ( v70 )
              CGroupingStoryboard::_SetUnifiedCenter((CGroupingStoryboard *)a1, v70);
            if ( v61 )
              CGroupingStoryboard::_SetUnifiedCenter((CGroupingStoryboard *)a1, (struct CAnimationComponent *)v61);
            goto LABEL_160;
          }
LABEL_159:
          v63 = v70;
          v62 = v71;
LABEL_160:
          if ( v5 )
            CBaseObject::Release(v5);
          if ( v62 )
            CBaseObject::Release(v62);
          if ( v63 )
            CBaseObject::Release(v63);
          goto LABEL_166;
        }
        if ( v10 == 36 || v10 == 35 )
          goto LABEL_142;
LABEL_138:
        v66 = 0;
        goto LABEL_142;
      }
LABEL_51:
      if ( v65 )
      {
        v38 = *(unsigned int *)(a2 + 744);
        v80 = *(struct tagRECT *)(a2 + 48);
        if ( (v38 & 0x1000000) != 0 )
          v80 = *(struct tagRECT *)(a2 + 748);
        v39 = CAppArrangementImmediate::GetPVLTarget(a1, v38);
        v40 = CStoryboard::_CreateAndAddDesktopAnimationComponent(
                (CStoryboard *)a1,
                (struct CWindowData *)a2,
                v39,
                &v80,
                1,
                &v68);
        v4 = v40;
        if ( v40 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v40,
            0xD16u,
            0);
          goto LABEL_158;
        }
      }
      else
      {
        if ( v10 == 47 )
        {
          v46 = CAppArrangementImmediate::GetPVLTarget(a1, *(unsigned int *)(a2 + 744));
          v47 = CStoryboard::_CreateAndAddAnimationComponentWithRect(
                  (CStoryboard *)a1,
                  (struct CWindowData *)a2,
                  0,
                  v46,
                  (struct tagRECT *)(a2 + 748),
                  0,
                  -1,
                  &v68);
          v4 = v47;
          if ( v47 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              0x14u,
              &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v47,
              0xD1Eu,
              0);
            goto LABEL_158;
          }
          goto LABEL_100;
        }
        if ( v10 != 44 )
          LOBYTE(v5) = 1;
        v48 = *(_DWORD *)(a2 + 744);
        v49 = CAppArrangementImmediate::GetPVLTarget(a1, v48);
        if ( (v48 & 0x1000000) != 0 )
        {
          v50 = CStoryboard::_CreateAndAddAnimationComponentWithRect(
                  (CStoryboard *)a1,
                  (struct CWindowData *)a2,
                  (bool)v5,
                  v49,
                  (struct tagRECT *)(a2 + 748),
                  0,
                  -1,
                  &v68);
          v4 = v50;
          if ( v50 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              0x14u,
              &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v50,
              0xD25u,
              0);
            goto LABEL_158;
          }
        }
        else
        {
          v51 = CStoryboard::_CreateAndAddAnimationComponent(
                  (CStoryboard *)a1,
                  (struct CWindowData *)a2,
                  (bool)v5,
                  v49,
                  &v68);
          v4 = v51;
          if ( v51 < 0 )
          {
            MilInstrumentationCheckHR_MaybeFailFast(
              0x14u,
              &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
              1u,
              v51,
              0xD29u,
              0);
            goto LABEL_158;
          }
        }
      }
      if ( v10 - 45 <= 1 )
      {
        v5 = v68;
        if ( *((_DWORD *)v68 + 17) != 2 )
          *((_DWORD *)v68 + 17) = 3;
        goto LABEL_101;
      }
LABEL_100:
      v5 = v68;
LABEL_101:
      if ( (unsigned int)CAppArrangementImmediate::GetPVLTarget(a1, v10) == 4 )
        *((_BYTE *)v5 + 73) = 0;
      goto LABEL_103;
    }
    if ( (*(_DWORD *)(a2 + 744) & 0x1000000) == 0
      || (v43 = (struct tagRECT *)(a2 + 748), IsRectEmpty((const RECT *)(a2 + 748))) )
    {
      v43 = 0;
    }
    v44 = CAppArrangementImmediate::GetPVLTarget(a1, *(unsigned int *)(a2 + 744));
    v45 = CStoryboard::_CreateAndAddAnimationComponentControlReuse(
            (CStoryboard *)a1,
            (struct CWindowData *)a2,
            v10 - 71 <= 1,
            v44,
            v43,
            0,
            -1,
            0,
            &v68);
    v4 = v45;
    if ( v45 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v45, 0xD5Du, 0);
      goto LABEL_158;
    }
LABEL_87:
    v5 = v68;
    goto LABEL_103;
  }
  if ( v10 == 44 )
    goto LABEL_51;
  if ( v10 <= 0x1F )
  {
    switch ( v10 )
    {
      case 0x1Fu:
        goto LABEL_51;
      case 7u:
        v37 = (int)(*((double *)CDesktopManager::s_pDesktopManagerInstance + 52) * -50.0);
        dy[0] = v37;
        if ( CStoryboard::IsRTL() )
          dy[0] = -v37;
        goto LABEL_51;
      case 0x14u:
        goto LABEL_51;
    }
    if ( v10 != 22 )
    {
      if ( v10 == 23 )
        goto LABEL_51;
      v34 = v10 - 28;
      v33 = v10 == 28;
LABEL_72:
      if ( v33 )
        goto LABEL_51;
      v42 = v34 == 1;
      goto LABEL_80;
    }
    if ( !CAppArrangementBase::_IsOnAnimatingMonitor((CAppArrangementBase *)a1, (const struct tagRECT *)(a2 + 48))
      || CImmersiveState::IsLauncherShownAboveWindow(*(CImmersiveState **)(a1 + 184), (const struct CWindowData *)a2) )
    {
      goto LABEL_138;
    }
    goto LABEL_47;
  }
  if ( v10 == 32 )
  {
LABEL_47:
    v67 = 1;
    v35 = CAppArrangementImmediate::GetPVLTarget(a1, v10);
    v36 = CStoryboard::_CreateAndAddNullComponentWithWindow((CStoryboard *)a1, (struct CWindowData *)a2, v35, &v68);
    v4 = v36;
    if ( v36 < 0 )
    {
      MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v36, 0xD4Bu, 0);
LABEL_158:
      v5 = v68;
      goto LABEL_159;
    }
    goto LABEL_87;
  }
  if ( v10 == 33 )
    goto LABEL_51;
  if ( v10 != 35 && v10 != 36 )
  {
    if ( v10 == 39 )
      goto LABEL_51;
    if ( v10 != 43 )
      goto LABEL_103;
    goto LABEL_47;
  }
  v41 = CAppArrangementImmediate::_HandleThumbnailTag((CAppArrangementImmediate *)a1, (struct CWindowData *)a2, v65);
  v4 = v41;
  if ( v41 >= 0 )
    goto LABEL_103;
  MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v41, 0xCF1u, 0);
LABEL_166:
  v6 = v75;
LABEL_167:
  if ( v76 )
    CBaseObject::Release(v76);
LABEL_169:
  *v6 = v4;
  return 1;
}

```

## disassembly

```asm
0x18008d040  mov     rax, rsp
0x18008d043  mov     [rax+18h], rbx
0x18008d047  push    rbp
0x18008d048  push    rsi
0x18008d049  push    rdi
0x18008d04a  push    r12
0x18008d04c  push    r13
0x18008d04e  push    r14
0x18008d050  push    r15
0x18008d052  lea     rbp, [rax-48h]
0x18008d056  sub     rsp, 110h
0x18008d05d  movaps  xmmword ptr [rax-48h], xmm6
0x18008d061  mov     rax, cs:__security_cookie
0x18008d068  xor     rax, rsp
0x18008d06b  mov     [rbp+40h+var_50], rax
0x18008d06f  xor     eax, eax
0x18008d071  mov     [rbp+40h+var_B8], r9
0x18008d075  mov     r15d, eax
0x18008d078  mov     [rsp+140h+var_E8], rax
0x18008d07d  mov     r14d, eax
0x18008d080  mov     [rsp+140h+var_D0], rax
0x18008d085  mov     [rsp+140h+var_D8], rax
0x18008d08a  mov     r12, r9
0x18008d08d  mov     [rbp+40h+var_B0], rax
0x18008d091  mov     ebx, r8d
0x18008d094  mov     rdi, rdx
0x18008d097  mov     r13, rcx
0x18008d09a  call    ?_WindowEnumCallback@CAppArrangementBase@@MEAA_NPEAVCWindowData@@W4EnumWindowFlags@CStoryboard@@PEAJ@Z; CAppArrangementBase::_WindowEnumCallback(CWindowData *,CStoryboard::EnumWindowFlags,long *)
0x18008d09f  test    bl, 1
0x18008d0a2  jz      loc_18008DA60
0x18008d0a8  mov     esi, [rdi+2E8h]
0x18008d0ae  xor     ebx, ebx
0x18008d0b0  and     esi, 0FFFh
0x18008d0b6  mov     qword ptr [rsp+140h+dy], rbx
0x18008d0bb  xorps   xmm0, xmm0
0x18008d0be  xorps   xmm1, xmm1
0x18008d0c1  movups  xmmword ptr [rbp+40h+var_90.left], xmm0
0x18008d0c5  lea     eax, [rsi-1Dh]
0x18008d0c8  movups  xmmword ptr [rbp+40h+rc.left], xmm1
0x18008d0cc  movups  xmmword ptr [rbp+40h+var_A8.left], xmm0
0x18008d0d0  movups  xmmword ptr [rbp+40h+var_60.left], xmm1
0x18008d0d4  cmp     eax, 25h ; '%'
0x18008d0d7  ja      short loc_18008D0EE
0x18008d0d9  mov     rcx, 2000020491h
0x18008d0e3  mov     [rsp+140h+var_F0], 1
0x18008d0e8  bt      rcx, rax
0x18008d0ec  jb      short loc_18008D0F2
0x18008d0ee  mov     [rsp+140h+var_F0], bl
0x18008d0f2  lea     eax, [rsi-17h]
0x18008d0f5  cmp     eax, 2Dh ; '-'
0x18008d0f8  ja      short loc_18008D10A
0x18008d0fa  mov     rcx, 280000210061h
0x18008d104  bt      rcx, rax
0x18008d108  jb      short loc_18008D11D
0x18008d10a  mov     rdx, rdi; struct CWindowData *
0x18008d10d  mov     rcx, r13; this
0x18008d110  call    ?_IsPartOfGroup@CGroupingStoryboard@@IEAA_NPEAVCWindowData@@@Z; CGroupingStoryboard::_IsPartOfGroup(CWindowData *)
0x18008d115  mov     [rsp+140h+var_F0+1], bl
0x18008d119  test    al, al
0x18008d11b  jz      short loc_18008D122
0x18008d11d  mov     [rsp+140h+var_F0+1], 1
0x18008d122  mov     edx, esi
0x18008d124  mov     rcx, r13
0x18008d127  call    ?GetSpecialTargetInfo@CAppArrangementImmediate@@UEAA?AW4SpecialTargetInfo@@W4DWMTRANSITION_TARGET@@@Z; CAppArrangementImmediate::GetSpecialTargetInfo(DWMTRANSITION_TARGET)
0x18008d12c  mov     rdx, [rdi+28h]; HWND
0x18008d130  mov     rcx, r13; this
0x18008d133  mov     ebx, eax
0x18008d135  call    ?_HasUsableBitmapResource@CStoryboard@@IEAA_NPEAUHWND__@@@Z; CStoryboard::_HasUsableBitmapResource(HWND__ *)
0x18008d13a  test    al, al
0x18008d13c  jz      loc_18008D1CE
0x18008d142  mov     edx, esi
0x18008d144  mov     rcx, r13
0x18008d147  call    ?GetPVLTarget@CAppArrangementImmediate@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppArrangementImmediate::GetPVLTarget(DWMTRANSITION_TARGET)
0x18008d14c  mov     rdx, [rdi+28h]
0x18008d150  mov     r9d, eax
0x18008d153  lea     rax, [rbp+40h+var_B0]
0x18008d157  mov     r8d, esi
0x18008d15a  mov     rcx, r13
0x18008d15d  mov     [rsp+140h+var_120], rax
0x18008d162  call    ?_CreateAndAddBitmapAnimationComponent@CStoryboard@@IEAAJPEAUHWND__@@W4DWMTRANSITION_TARGET@@HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddBitmapAnimationComponent(HWND__ *,DWMTRANSITION_TARGET,int,CAnimationComponent * *)
0x18008d167  mov     r15d, eax
0x18008d16a  test    eax, eax
0x18008d16c  js      short loc_18008D1BF
0x18008d16e  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18008d175  lea     r9, [rbp+40h+var_60]; struct tagRECT *
0x18008d179  mov     rdx, [rdi+28h]; HWND
0x18008d17d  lea     r8, [rbp+40h+var_A8]; struct tagRECT *
0x18008d181  mov     rcx, [rcx+0C0h]; this
0x18008d188  call    ?GetBitmapRects@CTransitionVisualController@@QEAAJPEAUHWND__@@PEAUtagRECT@@1@Z; CTransitionVisualController::GetBitmapRects(HWND__ *,tagRECT *,tagRECT *)
0x18008d18d  mov     r15d, eax
0x18008d190  test    eax, eax
0x18008d192  jns     short loc_18008D1CE
0x18008d194  mov     [rsp+140h+var_118], r14; void *
0x18008d199  mov     dword ptr [rsp+140h+var_120], 0CB5h; unsigned int
0x18008d1a1  mov     r8d, 1; unsigned int
0x18008d1a7  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CStoryboard@@2QBJB; int *
0x18008d1ae  mov     r9d, eax; int
0x18008d1b1  lea     ecx, [r8+13h]; unsigned int
0x18008d1b5  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x18008d1ba  jmp     loc_18008DA52
0x18008d1bf  mov     [rsp+140h+var_118], r14
0x18008d1c4  mov     dword ptr [rsp+140h+var_120], 0CB4h
0x18008d1cc  jmp     short loc_18008D1A1
0x18008d1ce  and     ebx, 8
0x18008d1d1  mov     [rsp+140h+var_F0+2], r14b
0x18008d1d6  mov     [rbp+40h+var_C0], ebx
0x18008d1d9  jz      loc_18008D366
0x18008d1df  mov     edx, [rdi+2E8h]
0x18008d1e5  lea     rax, [rdi+2FCh]
0x18008d1ec  bt      edx, 18h
0x18008d1f0  jb      short loc_18008D1F6
0x18008d1f2  lea     rax, [rdi+30h]
0x18008d1f6  mov     ebx, [rax]
0x18008d1f8  lea     r8, [rbp+40h+var_70]
0x18008d1fc  mov     r12d, [rax+8]
0x18008d200  xorps   xmm0, xmm0
0x18008d203  mov     rcx, r13
0x18008d206  movups  xmmword ptr [rbp+40h+var_70.left], xmm0
0x18008d20a  call    ?_GetUnionRect@CGroupingStoryboard@@IEAAJW4DWMTRANSITION_TARGET@@PEAUtagRECT@@@Z; CGroupingStoryboard::_GetUnionRect(DWMTRANSITION_TARGET,tagRECT *)
0x18008d20f  test    eax, eax
0x18008d211  js      short loc_18008D236
0x18008d213  cmp     ebx, [rbp+40h+var_70.left]
0x18008d216  jnz     short loc_18008D220
0x18008d218  btr     dword ptr [rdi+2E8h], 10h
0x18008d220  mov     eax, [rdi+2E8h]
0x18008d226  cmp     r12d, [rbp+40h+var_70.right]
0x18008d22a  jnz     short loc_18008D236
0x18008d22c  btr     eax, 0Fh
0x18008d230  mov     [rdi+2E8h], eax
0x18008d236  mov     edx, [rdi+2E8h]
0x18008d23c  lea     r8, [rsp+140h+nNumber]
0x18008d241  mov     rcx, r13
0x18008d244  mov     [rsp+140h+nNumber], r14d
0x18008d249  call    ?_GroupingIndexByTarget@CGroupingStoryboard@@IEAAJW4DWMTRANSITION_TARGET@@PEAI@Z; CGroupingStoryboard::_GroupingIndexByTarget(DWMTRANSITION_TARGET,uint *)
0x18008d24e  test    eax, eax
0x18008d250  js      loc_18008D366
0x18008d256  mov     eax, [rsp+140h+nNumber]
0x18008d25a  mov     rcx, [r13+80h]
0x18008d261  lea     rbx, [rax+rax*2]
0x18008d265  shl     rbx, 4
0x18008d269  mov     rax, [rbx+rcx+20h]
0x18008d26e  sub     rax, [rbx+rcx+18h]
0x18008d273  cmp     rax, 20h ; ' '
0x18008d277  jnz     loc_18008D366
0x18008d27d  test    dword ptr [rdi+2E8h], 800000h
0x18008d287  lea     rcx, [rdi+31Ch]
0x18008d28e  jnz     short loc_18008D294
0x18008d290  lea     rcx, [rdi+30h]
0x18008d294  mov     eax, [rcx]
0x18008d296  lea     r8, [rsp+140h+nNumber]; int *
0x18008d29b  mov     r12d, [rcx+8]
0x18008d29f  mov     edx, r14d
0x18008d2a2  mov     [rbp+40h+var_BC], eax
0x18008d2a5  mov     eax, [rcx+0Ch]
0x18008d2a8  sub     eax, [rcx+4]
0x18008d2ab  mov     rcx, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18008d2b2  cmovns  edx, eax; int
0x18008d2b5  mov     [rsp+140h+nNumber], r14d
0x18008d2ba  mov     rcx, [rcx+0C0h]; this
0x18008d2c1  call    ?GetGutterWidth@CTransitionVisualController@@QEAAJHPEAH@Z; CTransitionVisualController::GetGutterWidth(int,int *)
0x18008d2c6  test    eax, eax
0x18008d2c8  js      loc_18008D366
0x18008d2ce  mov     ecx, [rsp+140h+nNumber]; nNumber
0x18008d2d2  mov     edx, 0Bh; nNumerator
0x18008d2d7  lea     r8d, [rdx-1]; nDenominator
0x18008d2db  call    cs:__imp_MulDiv
0x18008d2e1  mov     rdx, [r13+80h]
0x18008d2e8  mov     r10d, eax
0x18008d2eb  mov     rcx, [rbx+rdx+20h]
0x18008d2f0  sub     rcx, [rbx+rdx+18h]
0x18008d2f5  sar     rcx, 4
0x18008d2f9  test    rcx, rcx
0x18008d2fc  jz      short loc_18008D366
0x18008d2fe  mov     r11d, [rbp+40h+var_BC]
0x18008d302  xor     r9d, r9d
0x18008d305  mov     rax, [rdx+rbx+18h]
0x18008d30a  mov     ecx, r11d
0x18008d30d  mov     r8d, r9d
0x18008d310  shl     r8, 4
0x18008d314  sub     ecx, [rax+r8+8]
0x18008d319  cmp     ecx, r10d
0x18008d31c  jle     short loc_18008D326
0x18008d31e  btr     dword ptr [rdi+2E8h], 10h
0x18008d326  mov     rax, [r13+80h]
0x18008d32d  mov     rcx, [rax+rbx+18h]
0x18008d332  mov     eax, [rcx+r8]
0x18008d336  sub     eax, r12d
0x18008d339  cmp     eax, r10d
0x18008d33c  jle     short loc_18008D346
0x18008d33e  btr     dword ptr [rdi+2E8h], 0Fh
0x18008d346  mov     rdx, [r13+80h]
0x18008d34d  inc     r9d
0x18008d350  mov     eax, r9d
0x18008d353  mov     rcx, [rdx+rbx+20h]
0x18008d358  sub     rcx, [rbx+rdx+18h]
0x18008d35d  sar     rcx, 4
0x18008d361  cmp     rax, rcx
0x18008d364  jb      short loc_18008D305
0x18008d366  mov     r12d, 16h
0x18008d36c  cmp     esi, 2Ch ; ','
0x18008d36f  ja      loc_18008D539
0x18008d375  jz      loc_18008D44C
0x18008d37b  cmp     esi, 1Fh
0x18008d37e  ja      loc_18008D4BE
0x18008d384  jz      loc_18008D44C
0x18008d38a  mov     ecx, esi
0x18008d38c  sub     ecx, 7
0x18008d38f  jz      loc_18008D41E
0x18008d395  sub     ecx, 0Dh
0x18008d398  jz      loc_18008D44C
0x18008d39e  sub     ecx, 2
0x18008d3a1  jz      short loc_18008D3B4
0x18008d3a3  sub     ecx, 1
0x18008d3a6  jz      loc_18008D44C
0x18008d3ac  sub     ecx, 5
0x18008d3af  jmp     loc_18008D56D
0x18008d3b4  lea     rdx, [rdi+30h]; struct tagRECT *
0x18008d3b8  mov     rcx, r13; this
0x18008d3bb  call    ?_IsOnAnimatingMonitor@CAppArrangementBase@@IEAA_NAEBUtagRECT@@@Z; CAppArrangementBase::_IsOnAnimatingMonitor(tagRECT const &)
0x18008d3c0  test    al, al
0x18008d3c2  jz      loc_18008D90C
0x18008d3c8  mov     rcx, [r13+0B8h]; this
0x18008d3cf  mov     rdx, rdi; struct CWindowData *
0x18008d3d2  call    ?IsLauncherShownAboveWindow@CImmersiveState@@QEAA_NPEBVCWindowData@@@Z; CImmersiveState::IsLauncherShownAboveWindow(CWindowData const *)
0x18008d3d7  test    al, al
0x18008d3d9  jnz     loc_18008D90C
0x18008d3df  mov     edx, esi
0x18008d3e1  mov     [rsp+140h+var_F0+2], 1
0x18008d3e6  mov     rcx, r13
0x18008d3e9  call    ?GetPVLTarget@CAppArrangementImmediate@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppArrangementImmediate::GetPVLTarget(DWMTRANSITION_TARGET)
0x18008d3ee  mov     r8d, eax; int
0x18008d3f1  lea     r9, [rsp+140h+var_E8]; struct CAnimationComponent **
0x18008d3f6  mov     rdx, rdi; struct CWindowData *
0x18008d3f9  mov     rcx, r13; this
0x18008d3fc  call    ?_CreateAndAddNullComponentWithWindow@CStoryboard@@IEAAJPEAVCWindowData@@HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddNullComponentWithWindow(CWindowData *,int,CAnimationComponent * *)
0x18008d401  mov     r15d, eax
0x18008d404  test    eax, eax
0x18008d406  jns     loc_18008D627
0x18008d40c  mov     [rsp+140h+var_118], r14
0x18008d411  mov     dword ptr [rsp+140h+var_120], 0D4Bh
0x18008d419  jmp     loc_18008D9FF
0x18008d41e  mov     rax, cs:?s_pDesktopManagerInstance@CDesktopManager@@0PEAV1@EA; CDesktopManager * CDesktopManager::s_pDesktopManagerInstance
0x18008d425  movsd   xmm0, qword ptr [rax+1A0h]
0x18008d42d  mulsd   xmm0, cs:__real@c049000000000000
0x18008d435  cvttsd2si ebx, xmm0
0x18008d439  mov     [rsp+140h+dy], ebx
0x18008d43d  call    ?IsRTL@CStoryboard@@SA_NXZ; CStoryboard::IsRTL(void)
0x18008d442  test    al, al
0x18008d444  jz      short loc_18008D44C
0x18008d446  neg     ebx
0x18008d448  mov     [rsp+140h+dy], ebx
0x18008d44c  cmp     [rsp+140h+var_F0], r14b
0x18008d451  jz      loc_18008D631
0x18008d457  movups  xmm0, xmmword ptr [rdi+30h]
0x18008d45b  mov     edx, [rdi+2E8h]
0x18008d461  movdqu  xmmword ptr [rbp+40h+var_70.left], xmm0
0x18008d466  bt      edx, 18h
0x18008d46a  jnb     short loc_18008D478
0x18008d46c  movups  xmm0, xmmword ptr [rdi+2ECh]
0x18008d473  movdqu  xmmword ptr [rbp+40h+var_70.left], xmm0
0x18008d478  mov     rcx, r13
0x18008d47b  call    ?GetPVLTarget@CAppArrangementImmediate@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppArrangementImmediate::GetPVLTarget(DWMTRANSITION_TARGET)
0x18008d480  mov     r8d, eax; int
0x18008d483  lea     r9, [rbp+40h+var_70]; struct tagRECT *
0x18008d487  lea     rax, [rsp+140h+var_E8]
0x18008d48c  mov     rdx, rdi; struct CWindowData *
0x18008d48f  mov     [rsp+140h+var_118], rax; struct CAnimationComponent **
0x18008d494  mov     rcx, r13; this
0x18008d497  mov     byte ptr [rsp+140h+var_120], 1; bool
0x18008d49c  call    ?_CreateAndAddDesktopAnimationComponent@CStoryboard@@IEAAJPEAVCWindowData@@HAEBUtagRECT@@_NPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddDesktopAnimationComponent(CWindowData *,int,tagRECT const &,bool,CAnimationComponent * *)
0x18008d4a1  mov     r15d, eax
0x18008d4a4  test    eax, eax
0x18008d4a6  jns     loc_18008D72D
0x18008d4ac  mov     [rsp+140h+var_118], r14
0x18008d4b1  mov     dword ptr [rsp+140h+var_120], 0D16h
0x18008d4b9  jmp     loc_18008D9FF
0x18008d4be  mov     ecx, esi
0x18008d4c0  sub     ecx, 20h ; ' '
0x18008d4c3  jz      loc_18008D3DF
0x18008d4c9  sub     ecx, 1
0x18008d4cc  jz      loc_18008D44C
0x18008d4d2  sub     ecx, 2
0x18008d4d5  jz      short loc_18008D4F3
0x18008d4d7  sub     ecx, 1
0x18008d4da  jz      short loc_18008D4F3
0x18008d4dc  sub     ecx, 3
0x18008d4df  jz      loc_18008D44C
0x18008d4e5  cmp     ecx, 4
0x18008d4e8  jz      loc_18008D3DF
0x18008d4ee  jmp     loc_18008D764
0x18008d4f3  mov     r8b, [rsp+140h+var_F0]; bool
0x18008d4f8  mov     rdx, rdi; struct CWindowData *
0x18008d4fb  mov     rcx, r13; this
0x18008d4fe  call    ?_HandleThumbnailTag@CAppArrangementImmediate@@AEAAJPEAVCWindowData@@_N@Z; CAppArrangementImmediate::_HandleThumbnailTag(CWindowData *,bool)
0x18008d503  mov     r15d, eax
0x18008d506  test    eax, eax
0x18008d508  jns     loc_18008D764
0x18008d50e  mov     r8d, 1; unsigned int
0x18008d514  mov     [rsp+140h+var_118], r14; void *
0x18008d519  mov     r9d, eax; int
  ... truncated ...
```
