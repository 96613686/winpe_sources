# CAppSwitch::_WindowEnumCallback(CWindowData *,CStoryboard::EnumWindowFlags,long *)

- ea: `0x1800c76c0`
- end: `0x1800c7c3f`
- name: `?_WindowEnumCallback@CAppSwitch@@EEAA_NPEAVCWindowData@@W4EnumWindowFlags@CStoryboard@@PEAJ@Z`
- size: `1407`
- prototype: ``
- caller_count: `0`
- callee_count: `20`
- tags: `broker_com_uri`

## callees

- `0x180005ab0`
- `0x180008350`
- `0x180008384`
- `0x18001ce00`
- `0x18001f43c`
- `0x18002d0c4`
- `0x180045c80`
- `0x180061a6c`
- `0x180063e00`
- `0x180068aa4`
- `0x180071758`
- `0x1800724a0`
- `0x18008e8f8`
- `0x180095130`
- `0x1800c283c`
- `0x1800c2eb0`
- `0x1800c5700`
- `0x1800c6150`
- `0x1800c76c0`
- `0x1800c7d80`

## import_xrefs

- `USER32!OffsetRect` at `0x1800c7abf`
- `USER32!OffsetRect` at `0x1800c7abf`
- `USER32!IsRectEmpty` at `0x1800c774a`
- `USER32!IsRectEmpty` at `0x1800c774a`

## pseudocode

```c
char __fastcall CAppSwitch::_WindowEnumCallback(__int64 a1, __int64 a2, char a3, _DWORD *a4)
{
  int v7; // eax
  unsigned int v8; // r15d
  struct tagRECT *v9; // rdi
  CBaseObject *v10; // r13
  char v11; // r14
  struct tagRECT *v12; // rax
  int v13; // eax
  int v14; // eax
  int v15; // eax
  int v16; // eax
  int v17; // eax
  int v18; // eax
  int v19; // eax
  CBaseObject *v20; // rax
  int v21; // eax
  int v22; // eax
  int v23; // eax
  CBaseObject *v24; // r14
  int PVLTarget; // eax
  int v26; // eax
  bool v27; // zf
  int v28; // edx
  CBaseObject *v29; // r14
  int v30; // eax
  CAnimatedTransitionVisual *v31; // rcx
  CAnimatedTransitionVisual *v32; // rcx
  CBaseObject *v33; // rbx
  char result; // al
  CBaseObject *v35; // [rsp+40h] [rbp-49h] BYREF
  CBaseObject *v36; // [rsp+48h] [rbp-41h] BYREF
  LONG v37; // [rsp+50h] [rbp-39h] BYREF
  struct tagRECT v38; // [rsp+58h] [rbp-31h] BYREF
  CBaseObject *v39; // [rsp+68h] [rbp-21h] BYREF
  _DWORD *v40; // [rsp+70h] [rbp-19h]
  struct tagRECT rc; // [rsp+80h] [rbp-9h] BYREF
  struct tagRECT v42; // [rsp+90h] [rbp+7h] BYREF

  v40 = a4;
  CGroupingStoryboard::_WindowEnumCallback();
  v7 = *(_DWORD *)(a2 + 744);
  v36 = 0;
  v8 = v7 & 0xFFF;
  v39 = 0;
  v35 = 0;
  v9 = 0;
  v10 = 0;
  if ( (a3 & 1) == 0 )
  {
    if ( (a3 & 4) == 0 )
      goto LABEL_86;
    if ( v8 == 2 )
    {
      *(_BYTE *)(a1 + 168) = 0;
      goto LABEL_86;
    }
    if ( v8 != 3 )
      goto LABEL_86;
    CLaunchSwitchBase::_RecordMonitorRectForWindow((CLaunchSwitchBase *)a1, (const struct CWindowData *)a2);
    goto LABEL_78;
  }
  v38 = 0;
  v42 = 0;
  rc = 0;
  if ( (v7 & 0x1000000) == 0 || (v11 = 1, IsRectEmpty((const RECT *)(a2 + 748))) )
    v11 = 0;
  CTransitionVisualController::GetMonitorRectFromRectImpl((const struct tagRECT *)(a2 + 48), &v38);
  v12 = (struct tagRECT *)(a2 + 764);
  if ( !v11 )
    v12 = &v38;
  v42 = *v12;
  rc = v42;
  switch ( v8 )
  {
    case 2u:
      if ( *(_DWORD *)(a2 + 128) == 1 )
        *(_DWORD *)(a2 + 744) |= 0x4000000u;
      if ( v11 )
        v9 = (struct tagRECT *)(a2 + 748);
      PVLTarget = CAppSwitch::GetPVLTarget(a1, *(unsigned int *)(a2 + 744));
      v26 = CStoryboard::_CreateAndAddAnimationComponentWithRect(
              (CStoryboard *)a1,
              (struct CWindowData *)a2,
              0,
              PVLTarget,
              v9,
              0,
              17,
              &v36);
      LODWORD(v9) = v26;
      if ( v26 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v26, 0x9A9u, 0);
        goto LABEL_78;
      }
      if ( *((_DWORD *)v36 + 17) != 2 )
        *((_DWORD *)v36 + 17) = 1;
      v27 = !CStoryboard::IsRTL();
      v28 = 0;
      if ( v27 )
      {
        if ( v38.right - v38.left >= 0 )
          v28 = v38.right - v38.left;
        v28 = -v28;
      }
      else if ( v38.right - v38.left >= 0 )
      {
        v28 = v38.right - v38.left;
      }
      OffsetRect(&rc, v28, 0);
      goto LABEL_62;
    case 3u:
      if ( *(_DWORD *)(a2 + 128) == 1 )
        *(_DWORD *)(a2 + 744) |= 0x4000000u;
      if ( *(_BYTE *)(a1 + 168) )
        v21 = 3;
      else
        v21 = CAppSwitch::GetPVLTarget(a1, *(unsigned int *)(a2 + 744));
      if ( v11 )
      {
        v22 = CStoryboard::_CreateAndAddAnimationComponentWithRect(
                (CStoryboard *)a1,
                (struct CWindowData *)a2,
                0,
                v21,
                (struct tagRECT *)(a2 + 748),
                0,
                -1,
                &v36);
        LODWORD(v9) = v22;
        if ( v22 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v22,
            0x967u,
            0);
          goto LABEL_78;
        }
      }
      else
      {
        v23 = CStoryboard::_CreateAndAddAnimationComponent((CStoryboard *)a1, (struct CWindowData *)a2, 0, v21, &v36);
        LODWORD(v9) = v23;
        if ( v23 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v23,
            0x96Bu,
            0);
          goto LABEL_78;
        }
      }
      v24 = v36;
      CAnimatedTransitionVisual::SetBeginAlpha(*((CAnimatedTransitionVisual **)v36 + 5), 0.0);
      if ( *((_DWORD *)v24 + 17) != 2 )
        *((_DWORD *)v24 + 17) = 1;
      goto LABEL_62;
    case 0x16u:
      if ( !CWindowData::IsWindowVisibleAndUncloaked((CWindowData *)a2)
        || !ContainsRect((const struct tagRECT *)(a1 + 152), (const struct tagRECT *)(a2 + 48)) )
      {
        goto LABEL_86;
      }
      if ( *(_BYTE *)(a1 + 168) )
        v18 = 7;
      else
        v18 = CAppSwitch::GetPVLTarget(a1, *(unsigned int *)(a2 + 744));
      v19 = CStoryboard::_CreateAndAddAnimationComponent((CStoryboard *)a1, (struct CWindowData *)a2, 0, v18, &v36);
      LODWORD(v9) = v19;
      if ( v19 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v19, 0x980u, 0);
        goto LABEL_78;
      }
      v20 = v36;
      if ( *((_DWORD *)v36 + 17) != 2 )
        *((_DWORD *)v36 + 17) = 1;
      v42 = *(struct tagRECT *)((char *)v20 + 88);
      rc = v42;
      goto LABEL_62;
    case 0x1Cu:
      if ( *(_BYTE *)(a1 + 168) )
        v15 = 5;
      else
        v15 = CAppSwitch::GetPVLTarget(a1, *(unsigned int *)(a2 + 744));
      if ( v11 )
      {
        v16 = CStoryboard::_CreateAndAddAnimationComponentWithRect(
                (CStoryboard *)a1,
                (struct CWindowData *)a2,
                0,
                v15,
                (struct tagRECT *)(a2 + 748),
                0,
                -1,
                &v36);
        LODWORD(v9) = v16;
        if ( v16 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v16,
            0x991u,
            0);
          goto LABEL_78;
        }
      }
      else
      {
        v17 = CStoryboard::_CreateAndAddAnimationComponent((CStoryboard *)a1, (struct CWindowData *)a2, 0, v15, &v36);
        LODWORD(v9) = v17;
        if ( v17 < 0 )
        {
          MilInstrumentationCheckHR_MaybeFailFast(
            0x14u,
            &CStoryboard::MILINSTRUMENTATIONHRESULTLIST,
            1u,
            v17,
            0x995u,
            0);
          goto LABEL_78;
        }
      }
      if ( *((_DWORD *)v36 + 17) != 2 )
        *((_DWORD *)v36 + 17) = 1;
LABEL_62:
      v29 = v36;
      if ( !v36 )
        goto LABEL_86;
      if ( v8 <= 0x1C )
      {
        v30 = 272629772;
        if ( _bittest(&v30, v8) )
        {
          v31 = (CAnimatedTransitionVisual *)*((_QWORD *)v36 + 5);
          v37 = 0;
          CAnimatedTransitionVisual::GetBeginAlpha(v31, (float *)&v37);
          v32 = (CAnimatedTransitionVisual *)*((_QWORD *)v29 + 5);
          v38.right = v37;
          *(_QWORD *)&v38.left = a1;
          CAnimatedTransitionVisual::SetBeginRect(v32, &v42);
          CAnimatedTransitionVisual::SetEndRect(*((CAnimatedTransitionVisual **)v29 + 5), &rc);
          if ( v8 - 2 <= 1 )
            CAppSwitch::_WindowEnumCallback_::_81_::_lambda_1_::operator()(&v38, v29);
          if ( (*(_DWORD *)(a2 + 744) & 0x18000) != 0 )
          {
            CGroupingStoryboard::_CreateGuttersForApp(a1, a2, &v42, &rc, v8, &v39, &v35);
            v10 = v39;
            if ( v39 )
              CAppSwitch::_WindowEnumCallback_::_81_::_lambda_1_::operator()(&v38, v39);
            v33 = v35;
            if ( v35 )
              CAppSwitch::_WindowEnumCallback_::_81_::_lambda_1_::operator()(&v38, v10);
            goto LABEL_79;
          }
        }
      }
LABEL_78:
      v33 = v35;
LABEL_79:
      if ( v36 )
        CBaseObject::Release(v36);
      goto LABEL_82;
    case 0x2Bu:
      v13 = CAppSwitch::GetPVLTarget(a1, *(unsigned int *)(a2 + 744));
      v14 = CStoryboard::_CreateAndAddNullComponentWithWindow((CStoryboard *)a1, (struct CWindowData *)a2, v13, &v36);
      LODWORD(v9) = v14;
      if ( v14 < 0 )
      {
        MilInstrumentationCheckHR_MaybeFailFast(0x14u, &CStoryboard::MILINSTRUMENTATIONHRESULTLIST, 1u, v14, 0x9B2u, 0);
        goto LABEL_78;
      }
      goto LABEL_62;
  }
  v33 = v35;
LABEL_82:
  if ( v10 )
    CBaseObject::Release(v10);
  if ( v33 )
    CBaseObject::Release(v33);
LABEL_86:
  result = 1;
  *v40 = (_DWORD)v9;
  return result;
}

```

## disassembly

```asm
0x1800c76c0  mov     [rsp-8+arg_10], rbx
0x1800c76c5  push    rbp
0x1800c76c6  push    rsi
0x1800c76c7  push    rdi
0x1800c76c8  push    r12
0x1800c76ca  push    r13
0x1800c76cc  push    r14
0x1800c76ce  push    r15
0x1800c76d0  lea     rbp, [rsp-27h]
0x1800c76d5  sub     rsp, 0B0h
0x1800c76dc  mov     rax, cs:__security_cookie
0x1800c76e3  xor     rax, rsp
0x1800c76e6  mov     [rbp+57h+var_40], rax
0x1800c76ea  mov     [rbp+57h+var_70], r9
0x1800c76ee  mov     r14d, r8d
0x1800c76f1  mov     rbx, rdx
0x1800c76f4  mov     rsi, rcx
0x1800c76f7  call    ?_WindowEnumCallback@CGroupingStoryboard@@MEAA_NPEAVCWindowData@@W4EnumWindowFlags@CStoryboard@@PEAJ@Z; CGroupingStoryboard::_WindowEnumCallback(CWindowData *,CStoryboard::EnumWindowFlags,long *)
0x1800c76fc  mov     eax, [rbx+2E8h]
0x1800c7702  xor     r12d, r12d
0x1800c7705  mov     r15d, eax
0x1800c7708  mov     [rbp+57h+var_98], r12
0x1800c770c  and     r15d, 0FFFh
0x1800c7713  mov     [rbp+57h+var_78], r12
0x1800c7717  mov     [rbp+57h+var_A0], r12
0x1800c771b  mov     edi, r12d
0x1800c771e  mov     r13d, r12d
0x1800c7721  test    r14b, 1
0x1800c7725  jz      loc_1800C7BB1
0x1800c772b  xorps   xmm0, xmm0
0x1800c772e  xorps   xmm1, xmm1
0x1800c7731  movups  xmmword ptr [rbp+57h+var_88.left], xmm0
0x1800c7735  movups  xmmword ptr [rbp+57h+var_50.left], xmm1
0x1800c7739  movups  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800c773d  bt      eax, 18h
0x1800c7741  jnb     short loc_1800C7757
0x1800c7743  lea     rcx, [rbx+2ECh]; lprc
0x1800c774a  call    cs:__imp_IsRectEmpty
0x1800c7750  mov     r14b, 1
0x1800c7753  test    eax, eax
0x1800c7755  jz      short loc_1800C775A
0x1800c7757  mov     r14b, r12b
0x1800c775a  lea     rdx, [rbp+57h+var_88]; struct tagRECT *
0x1800c775e  lea     rcx, [rbx+30h]; struct tagRECT *
0x1800c7762  call    ?GetMonitorRectFromRectImpl@CTransitionVisualController@@KAXPEBUtagRECT@@PEAU2@@Z; CTransitionVisualController::GetMonitorRectFromRectImpl(tagRECT const *,tagRECT *)
0x1800c7767  lea     rax, [rbx+2FCh]
0x1800c776e  test    r14b, r14b
0x1800c7771  jnz     short loc_1800C7777
0x1800c7773  lea     rax, [rbp+57h+var_88]
0x1800c7777  movups  xmm0, xmmword ptr [rax]
0x1800c777a  mov     ecx, r15d
0x1800c777d  movdqu  xmmword ptr [rbp+57h+var_50.left], xmm0
0x1800c7782  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800c7787  sub     ecx, 2
0x1800c778a  jz      loc_1800C7A27
0x1800c7790  sub     ecx, 1
0x1800c7793  jz      loc_1800C7954
0x1800c7799  sub     ecx, 13h
0x1800c779c  jz      loc_1800C78B9
0x1800c77a2  sub     ecx, 6
0x1800c77a5  jz      short loc_1800C7805
0x1800c77a7  cmp     ecx, 0Fh
0x1800c77aa  jnz     loc_1800C7BF2
0x1800c77b0  mov     edx, [rbx+2E8h]
0x1800c77b6  mov     rcx, rsi
0x1800c77b9  call    ?GetPVLTarget@CAppSwitch@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppSwitch::GetPVLTarget(DWMTRANSITION_TARGET)
0x1800c77be  mov     r8d, eax; int
0x1800c77c1  lea     r9, [rbp+57h+var_98]; struct CAnimationComponent **
0x1800c77c5  mov     rdx, rbx; struct CWindowData *
0x1800c77c8  mov     rcx, rsi; this
0x1800c77cb  call    ?_CreateAndAddNullComponentWithWindow@CStoryboard@@IEAAJPEAVCWindowData@@HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddNullComponentWithWindow(CWindowData *,int,CAnimationComponent * *)
0x1800c77d0  mov     edi, eax
0x1800c77d2  test    eax, eax
0x1800c77d4  jns     loc_1800C7AC5
0x1800c77da  mov     [rsp+0E0h+var_B8], r12; void *
0x1800c77df  mov     dword ptr [rsp+0E0h+var_C0], 9B2h; unsigned int
0x1800c77e7  mov     r8d, 1; unsigned int
0x1800c77ed  lea     rdx, ?MILINSTRUMENTATIONHRESULTLIST@CStoryboard@@2QBJB; int *
0x1800c77f4  mov     r9d, eax; int
0x1800c77f7  lea     ecx, [r8+13h]; unsigned int
0x1800c77fb  call    ?MilInstrumentationCheckHR_MaybeFailFast@@YAXKQEBJIJIPEAX@Z; MilInstrumentationCheckHR_MaybeFailFast(ulong,long const * const,uint,long,uint,void *)
0x1800c7800  jmp     loc_1800C7BDB
0x1800c7805  cmp     [rsi+0A8h], r12b
0x1800c780c  jz      short loc_1800C7815
0x1800c780e  mov     eax, 5
0x1800c7813  jmp     short loc_1800C7823
0x1800c7815  mov     edx, [rbx+2E8h]
0x1800c781b  mov     rcx, rsi
0x1800c781e  call    ?GetPVLTarget@CAppSwitch@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppSwitch::GetPVLTarget(DWMTRANSITION_TARGET)
0x1800c7823  xor     r8d, r8d; bool
0x1800c7826  mov     r9d, eax; int
0x1800c7829  test    r14b, r14b
0x1800c782c  jz      short loc_1800C7873
0x1800c782e  lea     rdx, [rbp+57h+var_98]
0x1800c7832  mov     [rsp+0E0h+var_A8], rdx; struct CAnimationComponent **
0x1800c7837  lea     rcx, [rbx+2ECh]
0x1800c783e  mov     [rsp+0E0h+var_B0], 0FFFFFFFFh; int
0x1800c7846  mov     rdx, rbx; struct CWindowData *
0x1800c7849  mov     [rsp+0E0h+var_B8], r12; struct tagRECT *
0x1800c784e  mov     [rsp+0E0h+var_C0], rcx; struct tagRECT *
0x1800c7853  mov     rcx, rsi; this
0x1800c7856  call    ?_CreateAndAddAnimationComponentWithRect@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAUtagRECT@@2HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponentWithRect(CWindowData *,bool,int,tagRECT *,tagRECT *,int,CAnimationComponent * *)
0x1800c785b  mov     edi, eax
0x1800c785d  test    eax, eax
0x1800c785f  jns     short loc_1800C788D
0x1800c7861  mov     [rsp+0E0h+var_B8], r12
0x1800c7866  mov     dword ptr [rsp+0E0h+var_C0], 991h
0x1800c786e  jmp     loc_1800C77E7
0x1800c7873  lea     rcx, [rbp+57h+var_98]
0x1800c7877  mov     rdx, rbx; struct CWindowData *
0x1800c787a  mov     [rsp+0E0h+var_C0], rcx; struct CAnimationComponent **
0x1800c787f  mov     rcx, rsi; this
0x1800c7882  call    ?_CreateAndAddAnimationComponent@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponent(CWindowData *,bool,int,CAnimationComponent * *)
0x1800c7887  mov     edi, eax
0x1800c7889  test    eax, eax
0x1800c788b  js      short loc_1800C78A7
0x1800c788d  mov     rax, [rbp+57h+var_98]
0x1800c7891  cmp     dword ptr [rax+44h], 2
0x1800c7895  jz      loc_1800C7AC5
0x1800c789b  mov     dword ptr [rax+44h], 1
0x1800c78a2  jmp     loc_1800C7AC5
0x1800c78a7  mov     [rsp+0E0h+var_B8], r12
0x1800c78ac  mov     dword ptr [rsp+0E0h+var_C0], 995h
0x1800c78b4  jmp     loc_1800C77E7
0x1800c78b9  mov     rcx, rbx; this
0x1800c78bc  call    ?IsWindowVisibleAndUncloaked@CWindowData@@QEBA_NXZ; CWindowData::IsWindowVisibleAndUncloaked(void)
0x1800c78c1  test    al, al
0x1800c78c3  jz      loc_1800C7C10
0x1800c78c9  lea     rcx, [rsi+98h]; struct tagRECT *
0x1800c78d0  lea     rdx, [rbx+30h]; struct tagRECT *
0x1800c78d4  call    ?ContainsRect@@YA_NAEBUtagRECT@@0@Z; ContainsRect(tagRECT const &,tagRECT const &)
0x1800c78d9  test    al, al
0x1800c78db  jz      loc_1800C7C10
0x1800c78e1  cmp     [rsi+0A8h], r12b
0x1800c78e8  jz      short loc_1800C78F1
0x1800c78ea  mov     eax, 7
0x1800c78ef  jmp     short loc_1800C78FF
0x1800c78f1  mov     edx, [rbx+2E8h]
0x1800c78f7  mov     rcx, rsi
0x1800c78fa  call    ?GetPVLTarget@CAppSwitch@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppSwitch::GetPVLTarget(DWMTRANSITION_TARGET)
0x1800c78ff  lea     rcx, [rbp+57h+var_98]
0x1800c7903  mov     r9d, eax; int
0x1800c7906  mov     [rsp+0E0h+var_C0], rcx; struct CAnimationComponent **
0x1800c790b  xor     r8d, r8d; bool
0x1800c790e  mov     rcx, rsi; this
0x1800c7911  mov     rdx, rbx; struct CWindowData *
0x1800c7914  call    ?_CreateAndAddAnimationComponent@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponent(CWindowData *,bool,int,CAnimationComponent * *)
0x1800c7919  mov     edi, eax
0x1800c791b  test    eax, eax
0x1800c791d  js      short loc_1800C7942
0x1800c791f  mov     rax, [rbp+57h+var_98]
0x1800c7923  cmp     dword ptr [rax+44h], 2
0x1800c7927  jz      short loc_1800C7930
0x1800c7929  mov     dword ptr [rax+44h], 1
0x1800c7930  movups  xmm0, xmmword ptr [rax+58h]
0x1800c7934  movaps  xmmword ptr [rbp+57h+var_50.left], xmm0
0x1800c7938  movdqa  xmmword ptr [rbp+57h+rc.left], xmm0
0x1800c793d  jmp     loc_1800C7AC5
0x1800c7942  mov     [rsp+0E0h+var_B8], r12
0x1800c7947  mov     dword ptr [rsp+0E0h+var_C0], 980h
0x1800c794f  jmp     loc_1800C77E7
0x1800c7954  cmp     dword ptr [rbx+80h], 1
0x1800c795b  jnz     short loc_1800C7965
0x1800c795d  bts     dword ptr [rbx+2E8h], 1Ah
0x1800c7965  cmp     [rsi+0A8h], r12b
0x1800c796c  jz      short loc_1800C7975
0x1800c796e  mov     eax, 3
0x1800c7973  jmp     short loc_1800C7983
0x1800c7975  mov     edx, [rbx+2E8h]
0x1800c797b  mov     rcx, rsi
0x1800c797e  call    ?GetPVLTarget@CAppSwitch@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppSwitch::GetPVLTarget(DWMTRANSITION_TARGET)
0x1800c7983  xor     r8d, r8d; bool
0x1800c7986  mov     r9d, eax; int
0x1800c7989  test    r14b, r14b
0x1800c798c  jz      short loc_1800C79D3
0x1800c798e  lea     rdx, [rbp+57h+var_98]
0x1800c7992  mov     [rsp+0E0h+var_A8], rdx; struct CAnimationComponent **
0x1800c7997  lea     rcx, [rbx+2ECh]
0x1800c799e  mov     [rsp+0E0h+var_B0], 0FFFFFFFFh; int
0x1800c79a6  mov     rdx, rbx; struct CWindowData *
0x1800c79a9  mov     [rsp+0E0h+var_B8], r12; struct tagRECT *
0x1800c79ae  mov     [rsp+0E0h+var_C0], rcx; struct tagRECT *
0x1800c79b3  mov     rcx, rsi; this
0x1800c79b6  call    ?_CreateAndAddAnimationComponentWithRect@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAUtagRECT@@2HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponentWithRect(CWindowData *,bool,int,tagRECT *,tagRECT *,int,CAnimationComponent * *)
0x1800c79bb  mov     edi, eax
0x1800c79bd  test    eax, eax
0x1800c79bf  jns     short loc_1800C79ED
0x1800c79c1  mov     [rsp+0E0h+var_B8], r12
0x1800c79c6  mov     dword ptr [rsp+0E0h+var_C0], 967h
0x1800c79ce  jmp     loc_1800C77E7
0x1800c79d3  lea     rcx, [rbp+57h+var_98]
0x1800c79d7  mov     rdx, rbx; struct CWindowData *
0x1800c79da  mov     [rsp+0E0h+var_C0], rcx; struct CAnimationComponent **
0x1800c79df  mov     rcx, rsi; this
0x1800c79e2  call    ?_CreateAndAddAnimationComponent@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponent(CWindowData *,bool,int,CAnimationComponent * *)
0x1800c79e7  mov     edi, eax
0x1800c79e9  test    eax, eax
0x1800c79eb  js      short loc_1800C7A15
0x1800c79ed  mov     r14, [rbp+57h+var_98]
0x1800c79f1  xorps   xmm1, xmm1; float
0x1800c79f4  mov     rcx, [r14+28h]; this
0x1800c79f8  call    ?SetBeginAlpha@CAnimatedTransitionVisual@@QEAAXM@Z; CAnimatedTransitionVisual::SetBeginAlpha(float)
0x1800c79fd  cmp     dword ptr [r14+44h], 2
0x1800c7a02  jz      loc_1800C7AC5
0x1800c7a08  mov     dword ptr [r14+44h], 1
0x1800c7a10  jmp     loc_1800C7AC5
0x1800c7a15  mov     [rsp+0E0h+var_B8], r12
0x1800c7a1a  mov     dword ptr [rsp+0E0h+var_C0], 96Bh
0x1800c7a22  jmp     loc_1800C77E7
0x1800c7a27  cmp     dword ptr [rbx+80h], 1
0x1800c7a2e  jnz     short loc_1800C7A38
0x1800c7a30  bts     dword ptr [rbx+2E8h], 1Ah
0x1800c7a38  test    r14b, r14b
0x1800c7a3b  jz      short loc_1800C7A44
0x1800c7a3d  lea     rdi, [rbx+2ECh]
0x1800c7a44  mov     edx, [rbx+2E8h]
0x1800c7a4a  mov     rcx, rsi
0x1800c7a4d  call    ?GetPVLTarget@CAppSwitch@@UEAAHW4DWMTRANSITION_TARGET@@@Z; CAppSwitch::GetPVLTarget(DWMTRANSITION_TARGET)
0x1800c7a52  mov     r9d, eax; int
0x1800c7a55  xor     r8d, r8d; bool
0x1800c7a58  lea     rax, [rbp+57h+var_98]
0x1800c7a5c  mov     rdx, rbx; struct CWindowData *
0x1800c7a5f  mov     [rsp+0E0h+var_A8], rax; struct CAnimationComponent **
0x1800c7a64  mov     rcx, rsi; this
0x1800c7a67  mov     [rsp+0E0h+var_B0], 11h; int
0x1800c7a6f  mov     [rsp+0E0h+var_B8], r12; struct tagRECT *
0x1800c7a74  mov     [rsp+0E0h+var_C0], rdi; struct tagRECT *
0x1800c7a79  call    ?_CreateAndAddAnimationComponentWithRect@CStoryboard@@IEAAJPEAVCWindowData@@_NHPEAUtagRECT@@2HPEAPEAVCAnimationComponent@@@Z; CStoryboard::_CreateAndAddAnimationComponentWithRect(CWindowData *,bool,int,tagRECT *,tagRECT *,int,CAnimationComponent * *)
0x1800c7a7e  mov     edi, eax
0x1800c7a80  test    eax, eax
0x1800c7a82  js      loc_1800C7B9F
0x1800c7a88  mov     rax, [rbp+57h+var_98]
0x1800c7a8c  cmp     dword ptr [rax+44h], 2
0x1800c7a90  jz      short loc_1800C7A99
0x1800c7a92  mov     dword ptr [rax+44h], 1
0x1800c7a99  call    ?IsRTL@CStoryboard@@SA_NXZ; CStoryboard::IsRTL(void)
0x1800c7a9e  test    al, al
0x1800c7aa0  mov     edx, r12d
0x1800c7aa3  mov     eax, [rbp+57h+var_88.right]
0x1800c7aa6  jz      short loc_1800C7AB0
0x1800c7aa8  sub     eax, [rbp+57h+var_88.left]
0x1800c7aab  cmovns  edx, eax
0x1800c7aae  jmp     short loc_1800C7AB8
0x1800c7ab0  sub     eax, [rbp+57h+var_88.left]
0x1800c7ab3  cmovns  edx, eax
0x1800c7ab6  neg     edx; dx
0x1800c7ab8  xor     r8d, r8d; dy
0x1800c7abb  lea     rcx, [rbp+57h+rc]; lprc
0x1800c7abf  call    cs:__imp_OffsetRect
0x1800c7ac5  mov     r14, [rbp+57h+var_98]
0x1800c7ac9  test    r14, r14
0x1800c7acc  jz      loc_1800C7C10
0x1800c7ad2  cmp     r15d, 1Ch
0x1800c7ad6  ja      loc_1800C7BDB
0x1800c7adc  mov     eax, 1040000Ch
0x1800c7ae1  bt      eax, r15d
0x1800c7ae5  jnb     loc_1800C7BDB
0x1800c7aeb  mov     rcx, [r14+28h]; this
0x1800c7aef  lea     rdx, [rbp+57h+var_90]; float *
0x1800c7af3  mov     [rbp+57h+var_90], r13d
0x1800c7af7  call    ?GetBeginAlpha@CAnimatedTransitionVisual@@UEAAJPEAM@Z; CAnimatedTransitionVisual::GetBeginAlpha(float *)
0x1800c7afc  movss   xmm0, [rbp+57h+var_90]
0x1800c7b01  lea     rdx, [rbp+57h+var_50]; struct tagRECT *
0x1800c7b05  mov     rcx, [r14+28h]; this
0x1800c7b09  movss   [rbp+57h+var_88.right], xmm0
0x1800c7b0e  mov     qword ptr [rbp+57h+var_88.left], rsi
0x1800c7b12  call    ?SetBeginRect@CAnimatedTransitionVisual@@QEAAXPEBUtagRECT@@@Z; CAnimatedTransitionVisual::SetBeginRect(tagRECT const *)
0x1800c7b17  mov     rcx, [r14+28h]; this
0x1800c7b1b  lea     rdx, [rbp+57h+rc]; struct tagRECT *
0x1800c7b1f  call    ?SetEndRect@CAnimatedTransitionVisual@@QEAAXPEBUtagRECT@@@Z; CAnimatedTransitionVisual::SetEndRect(tagRECT const *)
0x1800c7b24  lea     eax, [r15-2]
0x1800c7b28  cmp     eax, 1
0x1800c7b2b  ja      short loc_1800C7B39
0x1800c7b2d  mov     rdx, r14
0x1800c7b30  lea     rcx, [rbp+57h+var_88]
0x1800c7b34  call    _CAppSwitch___WindowEnumCallback____81____lambda_1___operator__
0x1800c7b39  test    dword ptr [rbx+2E8h], 18000h
0x1800c7b43  jz      loc_1800C7BDB
0x1800c7b49  lea     rax, [rbp+57h+var_A0]
0x1800c7b4d  mov     rdx, rbx
0x1800c7b50  mov     qword ptr [rsp+0E0h+var_B0], rax
0x1800c7b55  lea     r9, [rbp+57h+rc]
0x1800c7b59  lea     rax, [rbp+57h+var_78]
0x1800c7b5d  mov     rcx, rsi
0x1800c7b60  mov     [rsp+0E0h+var_B8], rax
0x1800c7b65  lea     r8, [rbp+57h+var_50]
0x1800c7b69  mov     dword ptr [rsp+0E0h+var_C0], r15d
0x1800c7b6e  call    ?_CreateGuttersForApp@CGroupingStoryboard@@IEAAJPEAVCWindowData@@PEBUtagRECT@@1W4DWMTRANSITION_TARGET@@PEAPEAVCAnimationComponent@@3@Z; CGroupingStoryboard::_CreateGuttersForApp(CWindowData *,tagRECT const *,tagRECT const *,DWMTRANSITION_TARGET,CAnimationComponent * *,CAnimationComponent * *)
0x1800c7b73  mov     r13, [rbp+57h+var_78]
0x1800c7b77  test    r13, r13
0x1800c7b7a  jz      short loc_1800C7B88
0x1800c7b7c  mov     rdx, r13
0x1800c7b7f  lea     rcx, [rbp+57h+var_88]
0x1800c7b83  call    _CAppSwitch___WindowEnumCallback____81____lambda_1___operator__
0x1800c7b88  mov     rbx, [rbp+57h+var_A0]
0x1800c7b8c  test    rbx, rbx
0x1800c7b8f  jz      short loc_1800C7BDF
0x1800c7b91  mov     rdx, r13
0x1800c7b94  lea     rcx, [rbp+57h+var_88]
0x1800c7b98  call    _CAppSwitch___WindowEnumCallback____81____lambda_1___operator__
  ... truncated ...
```
