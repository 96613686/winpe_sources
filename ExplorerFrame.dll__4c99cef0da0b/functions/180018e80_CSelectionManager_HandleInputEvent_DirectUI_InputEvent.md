# CSelectionManager::HandleInputEvent(DirectUI::InputEvent *)

- ea: `0x180018e80`
- end: `0x1800195ff`
- name: `?HandleInputEvent@CSelectionManager@@UEAAJPEAUInputEvent@DirectUI@@@Z`
- size: `1919`
- prototype: `int(CSelectionManager *__hidden this, struct DirectUI::InputEvent *)`
- caller_count: `0`
- callee_count: `30`
- tags: `registry_config, loader_planting, broker_com_uri`

## callees

- `0x1800167c0`
- `0x18001743c`
- `0x1800174e8`
- `0x1800185fc`
- `0x180018e80`
- `0x18001a1c4`
- `0x18001a1e0`
- `0x18001a9cc`
- `0x18001b8d0`
- `0x18001c560`
- `0x18001fadc`
- `0x18001fbdc`
- `0x1800210a8`
- `0x180021100`
- `0x1800217d8`
- `0x1800433d4`
- `0x18005a3ec`
- `0x1800714cc`
- `0x18007bb50`
- `0x18007d4ac`
- `0x18007d974`
- `0x18007d9dc`
- `0x18007ea30`
- `0x1800b9634`
- `0x18013f7d0`
- `0x1801e4fd0`
- `0x1801f60c0`
- `0x1801f7518`
- `0x1801f7630`
- `0x180210010`

## import_xrefs

- `SHELL32!SHChangeNotify` at `0x180019178`
- `SHELL32!SHChangeNotify` at `0x180019178`
- `USER32!SystemParametersInfoW` at `0x1800191cd`
- `USER32!SystemParametersInfoW` at `0x1800191e9`
- `USER32!SystemParametersInfoW` at `0x1800191cd`
- `USER32!SystemParametersInfoW` at `0x1800191e9`
- `USER32!TrackMouseEvent` at `0x180019299`
- `USER32!TrackMouseEvent` at `0x180019299`
- `USER32!GetForegroundWindow` at `0x1800194cb`
- `USER32!GetForegroundWindow` at `0x1800194cb`
- `USER32!IsChild` at `0x1800194d7`
- `USER32!IsChild` at `0x1800194d7`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180018ff1`
- `DUI70!?StartDefer@Element@DirectUI@@QEAAXPEAK@Z` at `0x180018ff1`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800190f8`
- `DUI70!?EndDefer@Element@DirectUI@@QEAAXK@Z` at `0x1800190f8`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001905a`
- `DUI70!?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z` at `0x18001905a`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180019567`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180019583`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180019567`
- `DUI70!?Destroy@Element@DirectUI@@QEAAJ_N@Z` at `0x180019583`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018f2a`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x1800190c5`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x180018f2a`
- `DUI70!?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z` at `0x1800190c5`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800193c8`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800193c8`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001908b`
- `DUI70!?Add@Element@DirectUI@@QEAAJPEAV12@@Z` at `0x18001908b`
- `DUI70!?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z` at `0x180018f56`
- `DUI70!?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z` at `0x180018f56`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CSelectionManager::HandleInputEvent(CSelectionManager *this, __m128i *a2)
{
  int v4; // edi
  __int32 v5; // edx
  char *v6; // r12
  __int64 v7; // r13
  struct DirectUI::Element *DescendentElement; // rbx
  DirectUI::Element *v9; // r15
  __int32 v10; // eax
  DirectUI::Element *v12; // rcx
  CDUIResourceManager *v13; // rcx
  struct DirectUI::Element *LineViewer; // r15
  DirectUI::DUIXmlParser **RefCountedParserForThread; // rax
  DirectUI::Element *v16; // rbx
  __int16 v17; // ax
  HWND v18; // rax
  double v19; // xmm0_8
  int v20; // edx
  int v21; // eax
  int v22; // eax
  __int8 v23; // al
  UIMarqueeSelector *v24; // rcx
  __m128i v25; // xmm2
  __m128i v26; // xmm1
  __m128i v27; // xmm0
  __int64 v28; // rcx
  __int64 v29; // rbx
  int v30; // r15d
  DirectUI::Element *Ancestor; // rbx
  __int64 v32; // rax
  struct DirectUI::Element *Parent; // rax
  UIItemsView *v34; // r15
  __int64 v35; // rax
  HWND v36; // rbx
  HWND ForegroundWindow; // rax
  struct DirectUI::Element *pvParam; // [rsp+30h] [rbp-49h] BYREF
  _BYTE EventTrack[32]; // [rsp+38h] [rbp-41h] BYREF
  __m128i v40; // [rsp+58h] [rbp-21h]
  __int64 v41; // [rsp+68h] [rbp-11h]
  struct DirectUI::Element *dwItem1; // [rsp+70h] [rbp-9h] BYREF
  int v43; // [rsp+78h] [rbp-1h]

  v4 = 0;
  v5 = a2[1].m128i_i32[0];
  if ( v5 )
  {
    if ( v5 == 1 && !a2[1].m128i_i32[1] )
    {
      v17 = a2[2].m128i_i16[0];
      if ( v17 == 32 )
      {
        v4 = CSelectionManager::_HandleSpaceKey(
               (CSelectionManager *)((char *)this - 16),
               (struct DirectUI::KeyboardEvent *)a2);
        a2->m128i_i8[8] = 1;
      }
      else if ( v17 == 27 )
      {
        (*(void (__fastcall **)(char *, _QWORD))(*((_QWORD *)this - 1) + 32LL))((char *)this - 8, 0);
        HIWORD(dwItem1) = 0;
        v43 = 0;
        LOWORD(dwItem1) = 10;
        *(_DWORD *)((char *)&dwItem1 + 2) = 15;
        SHChangeNotify(0x4000000, 0x3000u, &dwItem1, 0);
        a2->m128i_i8[8] = 1;
      }
    }
    return (unsigned int)v4;
  }
  v6 = (char *)this - 16;
  if ( !*((_QWORD *)this + 43) && (v6[388] & 1) == 0 )
  {
    v4 = -2147467259;
    v12 = (DirectUI::Element *)*((_QWORD *)v6 + 50);
    if ( v12 )
    {
      *(_QWORD *)EventTrack = *((_QWORD *)v6 + 50);
      *(_DWORD *)&EventTrack[8] = 0;
      DirectUI::Element::StartDefer(v12, (unsigned int *)&EventTrack[8]);
      LineViewer = UIItemsView::GetLineViewer(*((UIItemsView **)v6 + 50));
      if ( !LineViewer )
        goto LABEL_30;
      pvParam = 0;
      dwItem1 = 0;
      RefCountedParserForThread = (DirectUI::DUIXmlParser **)CDUIResourceManager::_GetRefCountedParserForThread(v13);
      if ( RefCountedParserForThread && *RefCountedParserForThread )
      {
        v4 = DirectUI::DUIXmlParser::CreateElement(*RefCountedParserForThread, L"Marquee", 0, LineViewer, 0, &dwItem1);
        if ( v4 < 0 )
          goto LABEL_30;
        v4 = ElementCast<UIMarqueeSelector>(dwItem1, &pvParam);
        if ( v4 < 0 )
        {
          DirectUI::Element::Destroy(dwItem1, 1);
        }
        else
        {
          v16 = pvParam;
          v4 = DirectUI::Element::Add(LineViewer, pvParam);
          if ( v4 >= 0 )
          {
            CSafeElementPtr<ItemRowLayout>::Unassign(v6 + 352);
            v4 = -2147024809;
            if ( v16
              && (*((_QWORD *)v6 + 45) = v16,
                  v4 = DirectUI::Element::AddListener(v16, (struct DirectUI::IElementListener *)(v6 + 352)),
                  v4 < 0) )
            {
              *((_QWORD *)v6 + 45) = 0;
            }
            else if ( v4 >= 0 )
            {
              ATL::CComPtr<IShellSearchTarget>::operator=((char *)v16 + 256, v6);
              goto LABEL_30;
            }
          }
          DirectUI::Element::Destroy(v16, 1);
        }
      }
      else
      {
        v4 = -2147467259;
      }
LABEL_30:
      if ( *(_DWORD *)&EventTrack[8] )
      {
        DirectUI::Element::EndDefer(*(DirectUI::Element **)EventTrack, *(unsigned int *)&EventTrack[8]);
        *(_DWORD *)&EventTrack[8] = 0;
      }
    }
  }
  v7 = *((_QWORD *)v6 + 50);
  if ( !v7 )
  {
    v9 = 0;
    goto LABEL_9;
  }
  DescendentElement = *(struct DirectUI::Element **)(v7 + 368);
  if ( DescendentElement )
    goto LABEL_8;
  v9 = 0;
  DescendentElement = _FindDescendentElement(*((struct DirectUI::Element **)v6 + 50), LineScroller::Class);
  CSafeElementPtr<ItemRowLayout>::Unassign(v7 + 360);
  if ( DescendentElement )
  {
    *(_QWORD *)(v7 + 368) = DescendentElement;
    if ( (int)DirectUI::Element::AddListener(DescendentElement, (struct DirectUI::IElementListener *)(v7 + 360)) < 0 )
      *(_QWORD *)(v7 + 368) = 0;
LABEL_8:
    v9 = (DirectUI::Element *)*((_QWORD *)DescendentElement + 34);
  }
LABEL_9:
  if ( v4 < 0
    || !v9
    || v9 != (DirectUI::Element *)a2->m128i_i64[0]
    && !DirectUI::Element::IsDescendent(v9, (struct DirectUI::Element *)a2->m128i_i64[0]) )
  {
    return (unsigned int)v4;
  }
  v10 = a2[1].m128i_i32[1];
  if ( v10 == 1 )
  {
    *((_DWORD *)this + 91) = a2[1].m128i_i32[2];
    if ( !a2[3].m128i_i32[0] )
    {
      v23 = a2[2].m128i_i8[8];
      if ( v23 == 1 )
      {
        v4 = CSelectionManager::_HandleLeftMouseDown((CSelectionManager *)v6, (struct DirectUI::MouseEvent *)a2);
        a2->m128i_i8[8] = 1;
      }
      else if ( v23 == 2 )
      {
        v4 = CSelectionManager::_HandleRightMouseDown((CSelectionManager *)v6, (struct DirectUI::MouseEvent *)a2);
        a2->m128i_i8[8] = 1;
      }
    }
  }
  else
  {
    if ( v10 != 2 )
    {
      if ( v10 == 3 )
      {
        v24 = (UIMarqueeSelector *)*((_QWORD *)this + 43);
        if ( v24 && *((_DWORD *)v24 + 52) )
        {
          UIMarqueeSelector::OnMouseMoved(v24, (struct DirectUI::MouseDragEvent *)a2);
          a2->m128i_i8[8] = 1;
        }
        else
        {
          ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(&dwItem1);
          v29 = a2->m128i_i64[0];
          if ( !element_cast<DirectUI::Button>(a2->m128i_i64[0]) )
          {
            v30 = -2147467259;
            Ancestor = (DirectUI::Element *)FindAncestorElement<UIBase>(v29);
            if ( Ancestor )
            {
              do
              {
                if ( (UIBase::GetCapabilities(Ancestor) & 1) != 0 )
                {
                  v32 = element_cast<UIItem>(Ancestor);
                  if ( v32 )
                    v30 = (*(__int64 (__fastcall **)(__int64, struct DirectUI::Element **))(*(_QWORD *)v32 + 440LL))(
                            v32,
                            &dwItem1);
                  else
                    v30 = -2147467259;
                }
                Parent = DirectUI::Element::GetParent(Ancestor);
                Ancestor = (DirectUI::Element *)FindAncestorElement<UIBase>(Parent);
              }
              while ( Ancestor );
              if ( v30 >= 0
                && !(*(unsigned int (__fastcall **)(char *, struct DirectUI::Element *))(*(_QWORD *)v6 + 32LL))(
                      v6,
                      dwItem1) )
              {
                *(__m128i *)EventTrack = *a2;
                *(__m128i *)&EventTrack[16] = a2[1];
                v40 = a2[2];
                *(_DWORD *)&EventTrack[24] = *((_DWORD *)this + 91);
                if ( (unsigned int)ItemSelectionTypeFromMouseEvent(EventTrack) == 1 )
                {
                  if ( (unsigned int)DUI_IsDragDelta((struct DirectUI::MouseDragEvent *)a2) )
                  {
                    CSelectionManager::_HandleLeftMouseUp(
                      (CSelectionManager *)v6,
                      (struct DirectUI::MouseEvent *)EventTrack);
                    *((_DWORD *)this + 91) = 0;
                  }
                }
              }
            }
          }
          ATL::CComPtr<IQueryParser2>::~CComPtr<IQueryParser2>(&dwItem1);
        }
      }
      else if ( (*((_BYTE *)this + 372) & 4) != 0 )
      {
        if ( v10 == 4 )
        {
          v35 = *((_QWORD *)this + 43);
          if ( !v35 || !*(_DWORD *)(v35 + 208) )
          {
            v36 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 360LL))(*((_QWORD *)this + 48));
            ForegroundWindow = GetForegroundWindow();
            if ( IsChild(ForegroundWindow, v36) )
            {
              if ( !(unsigned int)UIItemsView::IsInRenameMode(*((UIItemsView **)this + 48))
                && !(unsigned int)EditBoxHasFocus()
                && !UIItemsView::IsContextMenuOpen(*((UIItemsView **)this + 48)) )
              {
                return (unsigned int)CSelectionManager::_HandleHoverSelect(
                                       (CSelectionManager *)v6,
                                       (struct DirectUI::MouseEvent *)a2);
              }
            }
          }
        }
        else if ( !v10 )
        {
          LODWORD(dwItem1) = 0;
          LODWORD(pvParam) = 0;
          v18 = (HWND)(*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 360LL))(*((_QWORD *)this + 48));
          v19 = SHComputeSystemToMonitorDPIRatio(v18);
          if ( SystemParametersInfoW(0x64u, 0, &pvParam, 0) )
          {
            if ( SystemParametersInfoW(0x62u, 0, &dwItem1, 0) )
            {
              LODWORD(pvParam) = (int)((double)(int)pvParam * v19);
              v20 = (int)((double)(int)dwItem1 * v19);
              LODWORD(dwItem1) = v20;
              v21 = a2[2].m128i_i32[0] - *((_DWORD *)this + 94);
              if ( v21 < 0 )
                v21 = *((_DWORD *)this + 94) - a2[2].m128i_i32[0];
              if ( v21 > v20 )
                goto LABEL_49;
              v22 = a2[2].m128i_i32[1] - *((_DWORD *)this + 95);
              if ( v22 < 0 )
                v22 = *((_DWORD *)this + 95) - a2[2].m128i_i32[1];
              if ( v22 > v20 )
              {
LABEL_49:
                *((_QWORD *)this + 47) = a2[2].m128i_i64[0];
                *(_OWORD *)&EventTrack[8] = 0;
                *(_QWORD *)EventTrack = 0x100000018LL;
                *(_QWORD *)&EventTrack[8] = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 48) + 360LL))(*((_QWORD *)this + 48));
                *(_DWORD *)&EventTrack[16] = -1;
                TrackMouseEvent((LPTRACKMOUSEEVENT)EventTrack);
              }
            }
          }
        }
      }
      return (unsigned int)v4;
    }
    v25 = *a2;
    *(__m128i *)EventTrack = *a2;
    *(__m128i *)&EventTrack[16] = a2[1];
    v26 = a2[2];
    v40 = v26;
    v27 = (__m128i)a2[3].m128i_u64[0];
    v41 = a2[3].m128i_i64[0];
    *(_DWORD *)&EventTrack[24] = *((_DWORD *)this + 91);
    v28 = *((_QWORD *)this + 43);
    if ( !v28 || !*(_DWORD *)(v28 + 208) )
    {
      if ( _mm_cvtsi128_si32(v27) == 1 && (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128(v26, 8)) == 1 )
        v4 = CSelectionManager::_HandleLeftMouseUp((CSelectionManager *)v6, (struct DirectUI::MouseEvent *)EventTrack);
      goto LABEL_59;
    }
    if ( (unsigned int)_mm_cvtsi128_si32(v27) > 1 )
    {
LABEL_59:
      a2->m128i_i8[8] = 1;
      return (unsigned int)v4;
    }
    if ( !*(_DWORD *)(v28 + 212) )
    {
      v34 = (UIItemsView *)*((_QWORD *)this + 48);
      if ( (struct UICollection *)v25.m128i_i64[0] == UIItemsView::GetRootUICollection(v34)
        || (struct LineViewer *)v25.m128i_i64[0] == UIItemsView::GetLineViewer(v34) )
      {
        CSelectionManager::_ClearSelectionForBackgroundClick(
          (CSelectionManager *)v6,
          (struct DirectUI::MouseEvent *)EventTrack);
      }
    }
    UIMarqueeSelector::EndMarquee(*((UIMarqueeSelector **)this + 43));
    a2->m128i_i8[8] = 1;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180018e80  mov     [rsp-8+arg_10], rbx
0x180018e85  push    rbp
0x180018e86  push    rsi
0x180018e87  push    rdi
0x180018e88  push    r12
0x180018e8a  push    r13
0x180018e8c  push    r14
0x180018e8e  push    r15
0x180018e90  lea     rbp, [rsp-27h]
0x180018e95  sub     rsp, 0A0h
0x180018e9c  movaps  [rsp+0D0h+var_40], xmm6
0x180018ea4  mov     rax, cs:__security_cookie
0x180018eab  xor     rax, rsp
0x180018eae  mov     [rbp+57h+var_50], rax
0x180018eb2  mov     rsi, rdx
0x180018eb5  mov     r14, rcx
0x180018eb8  xor     edi, edi
0x180018eba  mov     edx, [rdx+10h]
0x180018ebd  test    edx, edx
0x180018ebf  jnz     loc_180019112
0x180018ec5  lea     r12, [rcx-10h]
0x180018ec9  cmp     [rcx+158h], rdi
0x180018ed0  jz      loc_180018FBD
0x180018ed6  mov     r13, [r12+190h]
0x180018ede  test    r13, r13
0x180018ee1  jz      loc_18001910A
0x180018ee7  mov     rbx, [r13+170h]
0x180018eee  test    rbx, rbx
0x180018ef1  jnz     short loc_180018F3B
0x180018ef3  xor     r15d, r15d
0x180018ef6  mov     rdx, cs:?Class@LineScroller@@2PEAUIClassInfo@DirectUI@@EA; struct DirectUI::IClassInfo *
0x180018efd  mov     rcx, r13; struct DirectUI::Element *
0x180018f00  call    ?_FindDescendentElement@@YAPEAVElement@DirectUI@@PEAV12@PEAUIClassInfo@2@@Z; _FindDescendentElement(DirectUI::Element *,DirectUI::IClassInfo *)
0x180018f05  mov     rbx, rax
0x180018f08  lea     rcx, [r13+168h]
0x180018f0f  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x180018f14  test    rbx, rbx
0x180018f17  jz      short loc_180018F42
0x180018f19  mov     [r13+170h], rbx
0x180018f20  lea     rdx, [r13+168h]
0x180018f27  mov     rcx, rbx
0x180018f2a  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x180018f30  test    eax, eax
0x180018f32  jns     short loc_180018F3B
0x180018f34  mov     [r13+170h], r15
0x180018f3b  mov     r15, [rbx+110h]
0x180018f42  test    edi, edi
0x180018f44  js      short loc_180018F8C
0x180018f46  test    r15, r15
0x180018f49  jz      short loc_180018F8C
0x180018f4b  mov     rdx, [rsi]
0x180018f4e  cmp     r15, rdx
0x180018f51  jz      short loc_180018F60
0x180018f53  mov     rcx, r15
0x180018f56  call    cs:__imp_?IsDescendent@Element@DirectUI@@QEAA_NPEAV12@@Z; DirectUI::Element::IsDescendent(DirectUI::Element *)
0x180018f5c  test    al, al
0x180018f5e  jz      short loc_180018F8C
0x180018f60  mov     eax, [rsi+14h]
0x180018f63  cmp     eax, 1
0x180018f66  jz      loc_1800192A4
0x180018f6c  cmp     eax, 2
0x180018f6f  jz      loc_180019300
0x180018f75  cmp     eax, 3
0x180018f78  jz      loc_1800192DA
0x180018f7e  test    byte ptr [r14+174h], 4
0x180018f86  jnz     loc_180019187
0x180018f8c  mov     eax, edi
0x180018f8e  mov     rcx, [rbp+57h+var_50]
0x180018f92  xor     rcx, rsp; StackCookie
0x180018f95  call    __security_check_cookie
0x180018f9a  mov     rbx, [rsp+0D0h+arg_10]
0x180018fa2  movaps  xmm6, [rsp+0D0h+var_40]
0x180018faa  add     rsp, 0A0h
0x180018fb1  pop     r15
0x180018fb3  pop     r14
0x180018fb5  pop     r13
0x180018fb7  pop     r12
0x180018fb9  pop     rdi
0x180018fba  pop     rsi
0x180018fbb  pop     rbp
0x180018fbc  retn
0x180018fbd  test    byte ptr [r12+184h], 1
0x180018fc6  jnz     loc_180018ED6
0x180018fcc  mov     edi, 80004005h
0x180018fd1  mov     rcx, [r12+190h]
0x180018fd9  test    rcx, rcx
0x180018fdc  jz      loc_180018ED6
0x180018fe2  mov     qword ptr [rbp+57h+EventTrack], rcx
0x180018fe6  mov     dword ptr [rbp+57h+EventTrack+8], 0
0x180018fed  lea     rdx, [rbp+57h+EventTrack+8]
0x180018ff1  call    cs:__imp_?StartDefer@Element@DirectUI@@QEAAXPEAK@Z; DirectUI::Element::StartDefer(ulong *)
0x180018ff7  nop
0x180018ff8  mov     rcx, [r12+190h]; this
0x180019000  call    ?GetLineViewer@UIItemsView@@QEAAPEAVLineViewer@@XZ; UIItemsView::GetLineViewer(void)
0x180019005  mov     r15, rax
0x180019008  test    rax, rax
0x18001900b  jz      loc_1800190ED
0x180019011  mov     [rbp+57h+pvParam], 0
0x180019019  mov     [rbp+57h+dwItem1], 0
0x180019021  call    ?_GetRefCountedParserForThread@CDUIResourceManager@@AEBAPEAUREFCOUNTEDPARSER@1@XZ; CDUIResourceManager::_GetRefCountedParserForThread(void)
0x180019026  test    rax, rax
0x180019029  jz      loc_180019464
0x18001902f  mov     rcx, [rax]
0x180019032  test    rcx, rcx
0x180019035  jz      loc_180019464
0x18001903b  lea     rax, [rbp+57h+dwItem1]
0x18001903f  mov     [rsp+0D0h+var_A8], rax
0x180019044  mov     [rsp+0D0h+var_B0], 0
0x18001904d  mov     r9, r15
0x180019050  xor     r8d, r8d
0x180019053  lea     rdx, aMarquee; "Marquee"
0x18001905a  call    cs:__imp_?CreateElement@DUIXmlParser@DirectUI@@QEAAJPEBGPEAVElement@2@1PEAKPEAPEAV32@@Z; DirectUI::DUIXmlParser::CreateElement(ushort const *,DirectUI::Element *,DirectUI::Element *,ulong *,DirectUI::Element * *)
0x180019060  mov     edi, eax
0x180019062  test    eax, eax
0x180019064  js      loc_1800190ED
0x18001906a  lea     rdx, [rbp+57h+pvParam]
0x18001906e  mov     rcx, [rbp+57h+dwItem1]
0x180019072  call    ??$ElementCast@VUIMarqueeSelector@@@@YAJPEAVElement@DirectUI@@PEAPEAVUIMarqueeSelector@@@Z; ElementCast<UIMarqueeSelector>(DirectUI::Element *,UIMarqueeSelector * *)
0x180019077  mov     edi, eax
0x180019079  test    eax, eax
0x18001907b  js      loc_180019561
0x180019081  mov     rbx, [rbp+57h+pvParam]
0x180019085  mov     rdx, rbx
0x180019088  mov     rcx, r15
0x18001908b  call    cs:__imp_?Add@Element@DirectUI@@QEAAJPEAV12@@Z; DirectUI::Element::Add(DirectUI::Element *)
0x180019091  mov     edi, eax
0x180019093  test    eax, eax
0x180019095  js      loc_18001957E
0x18001909b  lea     rcx, [r12+160h]
0x1800190a3  call    ?Unassign@?$CSafeElementPtr@VItemRowLayout@@@@QEAAXXZ; CSafeElementPtr<ItemRowLayout>::Unassign(void)
0x1800190a8  mov     edi, 80070057h
0x1800190ad  test    rbx, rbx
0x1800190b0  jz      short loc_1800190D5
0x1800190b2  mov     [r12+168h], rbx
0x1800190ba  lea     rdx, [r12+160h]
0x1800190c2  mov     rcx, rbx
0x1800190c5  call    cs:__imp_?AddListener@Element@DirectUI@@QEAAJPEAUIElementListener@2@@Z; DirectUI::Element::AddListener(DirectUI::IElementListener *)
0x1800190cb  mov     edi, eax
0x1800190cd  test    eax, eax
0x1800190cf  js      loc_180019572
0x1800190d5  test    edi, edi
0x1800190d7  js      loc_18001957E
0x1800190dd  lea     rcx, [rbx+100h]
0x1800190e4  mov     rdx, r12
0x1800190e7  call    ??4?$CComPtr@UIShellSearchTarget@@@ATL@@QEAAPEAUIShellSearchTarget@@PEAU2@@Z; ATL::CComPtr<IShellSearchTarget>::operator=(IShellSearchTarget *)
0x1800190ec  nop
0x1800190ed  mov     edx, dword ptr [rbp+57h+EventTrack+8]
0x1800190f0  test    edx, edx
0x1800190f2  jz      short loc_180019105
0x1800190f4  mov     rcx, qword ptr [rbp+57h+EventTrack]
0x1800190f8  call    cs:__imp_?EndDefer@Element@DirectUI@@QEAAXK@Z; DirectUI::Element::EndDefer(ulong)
0x1800190fe  mov     dword ptr [rbp+57h+EventTrack+8], 0
0x180019105  jmp     loc_180018ED6
0x18001910a  xor     r15d, r15d
0x18001910d  jmp     loc_180018F42
0x180019112  cmp     edx, 1
0x180019115  jnz     loc_180018F8C
0x18001911b  cmp     [rsi+14h], edi
0x18001911e  jnz     loc_180018F8C
0x180019124  movzx   eax, word ptr [rsi+20h]
0x180019128  cmp     ax, 20h ; ' '
0x18001912c  jz      loc_18001954A
0x180019132  cmp     ax, 1Bh
0x180019136  jnz     loc_180018F8C
0x18001913c  add     rcx, 0FFFFFFFFFFFFFFF8h
0x180019140  mov     rax, [rcx]
0x180019143  xor     edx, edx
0x180019145  mov     rax, [rax+20h]
0x180019149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001914e  xor     eax, eax
0x180019150  mov     [rbp+57h+dwItem1], rax
0x180019154  mov     [rbp+57h+var_58], eax
0x180019157  mov     eax, 0Ah
0x18001915c  mov     word ptr [rbp+57h+dwItem1], ax
0x180019160  mov     dword ptr [rbp+57h+dwItem1+2], 0Fh
0x180019167  xor     r9d, r9d; dwItem2
0x18001916a  lea     r8, [rbp+57h+dwItem1]; dwItem1
0x18001916e  mov     edx, 3000h; uFlags
0x180019173  mov     ecx, 4000000h; wEventId
0x180019178  call    cs:__imp_SHChangeNotify
0x18001917e  mov     byte ptr [rsi+8], 1
0x180019182  jmp     loc_180018F8C
0x180019187  cmp     eax, 4
0x18001918a  jz      loc_1800194A2
0x180019190  test    eax, eax
0x180019192  jnz     loc_180018F8C
0x180019198  mov     dword ptr [rbp+57h+dwItem1], eax
0x18001919b  mov     dword ptr [rbp+57h+pvParam], eax
0x18001919e  mov     rcx, [r14+180h]
0x1800191a5  mov     rax, [rcx]
0x1800191a8  mov     rax, [rax+168h]
0x1800191af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800191b4  mov     rcx, rax; HWND
0x1800191b7  call    ?SHComputeSystemToMonitorDPIRatio@@YANPEAUHWND__@@@Z; SHComputeSystemToMonitorDPIRatio(HWND__ *)
0x1800191bc  movaps  xmm6, xmm0
0x1800191bf  xor     r9d, r9d; fWinIni
0x1800191c2  lea     r8, [rbp+57h+pvParam]; pvParam
0x1800191c6  xor     edx, edx; uiParam
0x1800191c8  mov     ecx, 64h ; 'd'; uiAction
0x1800191cd  call    cs:__imp_SystemParametersInfoW
0x1800191d3  test    eax, eax
0x1800191d5  jz      loc_180018F8C
0x1800191db  xor     r9d, r9d; fWinIni
0x1800191de  lea     r8, [rbp+57h+dwItem1]; pvParam
0x1800191e2  xor     edx, edx; uiParam
0x1800191e4  mov     ecx, 62h ; 'b'; uiAction
0x1800191e9  call    cs:__imp_SystemParametersInfoW
0x1800191ef  test    eax, eax
0x1800191f1  jz      loc_180018F8C
0x1800191f7  mov     eax, dword ptr [rbp+57h+pvParam]
0x1800191fa  xorps   xmm0, xmm0
0x1800191fd  cvtsi2sd xmm0, rax
0x180019202  mulsd   xmm0, xmm6
0x180019206  cvttsd2si rax, xmm0
0x18001920b  mov     dword ptr [rbp+57h+pvParam], eax
0x18001920e  mov     eax, dword ptr [rbp+57h+dwItem1]
0x180019211  xorps   xmm0, xmm0
0x180019214  cvtsi2sd xmm0, rax
0x180019219  mulsd   xmm0, xmm6
0x18001921d  cvttsd2si rdx, xmm0
0x180019222  mov     dword ptr [rbp+57h+dwItem1], edx
0x180019225  mov     ecx, [r14+178h]
0x18001922c  sub     ecx, [rsi+20h]
0x18001922f  mov     eax, ecx
0x180019231  neg     eax
0x180019233  cmovs   eax, ecx
0x180019236  cmp     eax, edx
0x180019238  jg      short loc_180019253
0x18001923a  mov     ecx, [r14+17Ch]
0x180019241  sub     ecx, [rsi+24h]
0x180019244  mov     eax, ecx
0x180019246  neg     eax
0x180019248  cmovs   eax, ecx
0x18001924b  cmp     eax, edx
0x18001924d  jle     loc_180018F8C
0x180019253  mov     rax, [rsi+20h]
0x180019257  mov     [r14+178h], rax
0x18001925e  xorps   xmm0, xmm0
0x180019261  movdqu  xmmword ptr [rbp+57h+EventTrack+8], xmm0
0x180019266  mov     dword ptr [rbp+57h+EventTrack], 18h
0x18001926d  mov     dword ptr [rbp+57h+EventTrack+4], 1
0x180019274  mov     rcx, [r14+180h]
0x18001927b  mov     rax, [rcx]
0x18001927e  mov     rax, [rax+168h]
0x180019285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001928a  mov     qword ptr [rbp+57h+EventTrack+8], rax
0x18001928e  mov     dword ptr [rbp+57h+EventTrack+10h], 0FFFFFFFFh
0x180019295  lea     rcx, [rbp+57h+EventTrack]; lpEventTrack
0x180019299  call    cs:__imp_TrackMouseEvent
0x18001929f  jmp     loc_180018F8C
0x1800192a4  mov     eax, [rsi+18h]
0x1800192a7  mov     [r14+16Ch], eax
0x1800192ae  cmp     dword ptr [rsi+30h], 0
0x1800192b2  jnz     loc_180018F8C
0x1800192b8  movzx   eax, byte ptr [rsi+28h]
0x1800192bc  cmp     al, 1
0x1800192be  jnz     loc_18001952C
0x1800192c4  mov     rdx, rsi; struct DirectUI::MouseEvent *
0x1800192c7  mov     rcx, r12; this
0x1800192ca  call    ?_HandleLeftMouseDown@CSelectionManager@@AEAAJPEAUMouseEvent@DirectUI@@@Z; CSelectionManager::_HandleLeftMouseDown(DirectUI::MouseEvent *)
0x1800192cf  mov     edi, eax
0x1800192d1  mov     byte ptr [rsi+8], 1
0x1800192d5  jmp     loc_180018F8C
0x1800192da  mov     rcx, [r14+158h]; this
0x1800192e1  test    rcx, rcx
0x1800192e4  jz      short loc_18001935A
0x1800192e6  cmp     dword ptr [rcx+0D0h], 0
0x1800192ed  jz      short loc_18001935A
0x1800192ef  mov     rdx, rsi; struct DirectUI::MouseDragEvent *
0x1800192f2  call    ?OnMouseMoved@UIMarqueeSelector@@QEAAXPEAUMouseDragEvent@DirectUI@@@Z; UIMarqueeSelector::OnMouseMoved(DirectUI::MouseDragEvent *)
0x1800192f7  mov     byte ptr [rsi+8], 1
0x1800192fb  jmp     loc_180018F8C
0x180019300  movups  xmm2, xmmword ptr [rsi]
0x180019303  movups  xmmword ptr [rbp+57h+EventTrack], xmm2
0x180019307  movups  xmm0, xmmword ptr [rsi+10h]
0x18001930b  movups  xmmword ptr [rbp+57h+EventTrack+10h], xmm0
0x18001930f  movups  xmm1, xmmword ptr [rsi+20h]
0x180019313  movups  [rbp+57h+var_78], xmm1
0x180019317  movsd   xmm0, qword ptr [rsi+30h]
0x18001931c  movsd   [rbp+57h+var_68], xmm0
0x180019321  mov     eax, [r14+16Ch]
0x180019328  mov     dword ptr [rbp+57h+EventTrack+18h], eax
0x18001932b  mov     rcx, [r14+158h]
0x180019332  test    rcx, rcx
0x180019335  jz      short loc_180019344
0x180019337  cmp     dword ptr [rcx+0D0h], 0
0x18001933e  jnz     loc_180019415
0x180019344  movd    eax, xmm0
0x180019348  cmp     eax, 1
0x18001934b  jz      loc_180019440
0x180019351  mov     byte ptr [rsi+8], 1
0x180019355  jmp     loc_180018F8C
0x18001935a  lea     rcx, [rbp+57h+dwItem1]; void *
0x18001935e  call    ??0?$CComPtr@UIQueryParser2@@@ATL@@QEAA@XZ; ATL::CComPtr<IQueryParser2>::CComPtr<IQueryParser2>(void)
0x180019363  nop
0x180019364  mov     rbx, [rsi]
0x180019367  mov     rcx, rbx
0x18001936a  call    ??$element_cast@VButton@DirectUI@@@@YAPEAVButton@DirectUI@@PEAVElement@1@@Z; element_cast<DirectUI::Button>(DirectUI::Element *)
0x18001936f  test    rax, rax
0x180019372  jnz     loc_1800193FF
  ... truncated ...
```
