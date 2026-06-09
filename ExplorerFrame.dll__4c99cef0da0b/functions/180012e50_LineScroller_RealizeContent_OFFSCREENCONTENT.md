# LineScroller::_RealizeContent(OFFSCREENCONTENT)

- ea: `0x180012e50`
- end: `0x18001357c`
- name: `?_RealizeContent@LineScroller@@AEAAXW4OFFSCREENCONTENT@@@Z`
- size: `1836`
- prototype: ``
- caller_count: `1`
- callee_count: `14`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800126dc`

## callees

- `0x1800125f8`
- `0x180012ccc`
- `0x180012d74`
- `0x180012e50`
- `0x180013590`
- `0x1800141d0`
- `0x180015640`
- `0x180016790`
- `0x180047410`
- `0x1800a0660`
- `0x1800b8e88`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `USER32!GetDC` at `0x1800133d3`
- `USER32!GetDC` at `0x1800133d3`
- `USER32!ReleaseDC` at `0x180013455`
- `USER32!ReleaseDC` at `0x180013455`
- `USER32!SetRect` at `0x180013198`
- `USER32!SetRect` at `0x180013198`
- `DUI70!?LastDSConstProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800133f9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180012fb9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180013001`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180012fb9`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x180013001`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180012fad`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180012ff5`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180012fad`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x180012ff5`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180012fa1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180012fe9`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180013407`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180012fa1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180012fe9`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x180013407`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x180012f53`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x180013380`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x180012f53`
- `DUI70!?IsHosted@Element@DirectUI@@QEAA_NXZ` at `0x180013380`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180012e94`
- `DUI70!?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ` at `0x180012e94`
- `DUI70!??0DCSurface@DirectUI@@QEAA@PEAUHDC__@@@Z` at `0x1800133ec`
- `DUI70!??0DCSurface@DirectUI@@QEAA@PEAUHDC__@@@Z` at `0x1800133ec`
- `DUI70!??1DCSurface@DirectUI@@UEAA@XZ` at `0x180013460`
- `DUI70!??1DCSurface@DirectUI@@UEAA@XZ` at `0x180013460`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18001344a`
- `DUI70!?_UpdateDesiredSize@Element@DirectUI@@QEAA?AUtagSIZE@@HHPEAVSurface@2@@Z` at `0x18001344a`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180013033`
- `DUI70!?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z` at `0x180013033`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180013415`
- `DUI70!?GetSize@Value@DirectUI@@QEAAPEBUtagSIZE@@XZ` at `0x180013415`
- `DUI70!?MarkNeedsDSUpdate@Element@DirectUI@@QEAAXXZ` at `0x180012f22`
- `DUI70!?MarkNeedsDSUpdate@Element@DirectUI@@QEAAXXZ` at `0x180012f22`
- `DUI70!?_SetNeedsLayout@Element@DirectUI@@QEAAHI@Z` at `0x180012f34`
- `DUI70!?_SetNeedsLayout@Element@DirectUI@@QEAAHI@Z` at `0x180012f34`
- `DUser!DeleteHandle` at `0x180012f0b`
- `DUser!DeleteHandle` at `0x180012f0b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall LineScroller::_RealizeContent(__int64 a1, int a2, __int64 a3)
{
  struct DirectUI::Element *TopLevel; // rax
  struct DirectUI::Element *v5; // rbx
  UIItemsView *v6; // r14
  __int64 v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rcx
  int v10; // ecx
  __int64 v11; // r12
  int v12; // edi
  DirectUI::Value *Value; // rbx
  int Int; // r15d
  DirectUI::Value *v15; // rbx
  int RealXTarget; // r13d
  int v17; // eax
  DirectUI::Element *v18; // rcx
  int v19; // edi
  __int64 v20; // rbx
  int v21; // ecx
  int *v22; // rbx
  int v23; // ecx
  int v24; // r8d
  int v25; // edi
  struct IVirtualizedUI *v26; // rdx
  int v27; // eax
  LONG v28; // ecx
  LONG v29; // eax
  LONG v30; // edx
  LONG v31; // r8d
  LONG right; // edx
  LONG left; // ecx
  LONG top; // eax
  LONG bottom; // eax
  int v36; // ecx
  int v37; // eax
  int v38; // edx
  __int64 v39; // rcx
  int v40; // r13d
  int v41; // edi
  int v42; // r8d
  __int64 v43; // rcx
  __int64 v44; // rdx
  __int64 v45; // r8
  HDC DC; // rax
  HDC v47; // rdi
  __int64 v48; // rbx
  int xLeft[2]; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v50; // [rsp+48h] [rbp-B8h] BYREF
  int v51; // [rsp+50h] [rbp-B0h]
  int v52; // [rsp+54h] [rbp-ACh]
  struct DirectUI::Value *v53; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v54; // [rsp+60h] [rbp-A0h]
  _BYTE v55[4]; // [rsp+68h] [rbp-98h] BYREF
  int v56; // [rsp+6Ch] [rbp-94h]
  _QWORD v57[3]; // [rsp+80h] [rbp-80h] BYREF
  int v58; // [rsp+98h] [rbp-68h]
  int v59; // [rsp+A0h] [rbp-60h]
  int v60; // [rsp+D8h] [rbp-28h]
  __int64 v61; // [rsp+DCh] [rbp-24h]
  LONG v62; // [rsp+E4h] [rbp-1Ch]
  LONG v63; // [rsp+E8h] [rbp-18h]
  LONG v64; // [rsp+ECh] [rbp-14h]
  LONG v65; // [rsp+F0h] [rbp-10h]
  int v66; // [rsp+F4h] [rbp-Ch]
  struct tagRECT rc; // [rsp+100h] [rbp+0h] BYREF

  LODWORD(v54) = a2;
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ItemsView_LineScroller_RealizeContent_Start,
      a3,
      1);
  TopLevel = DirectUI::Element::GetTopLevel((DirectUI::Element *)a1);
  v5 = TopLevel;
  v6 = 0;
  if ( TopLevel )
  {
    v7 = (*(__int64 (__fastcall **)(struct DirectUI::Element *))(*(_QWORD *)TopLevel + 280LL))(TopLevel);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v7 + 80LL))(
           v7,
           UIItemsView::Class) )
    {
      if ( !*((_DWORD *)v5 + 122) )
      {
        *((_DWORD *)v5 + 195) = 1;
        v8 = *((_QWORD *)v5 + 74);
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 32LL))(v8);
        v9 = *((_QWORD *)v5 + 73);
        if ( v9 )
        {
          DeleteHandle(v9);
          *((_QWORD *)v5 + 73) = 0;
        }
      }
      v6 = v5;
    }
  }
  DirectUI::Element::MarkNeedsDSUpdate(*(DirectUI::Element **)(a1 + 304));
  DirectUI::Element::_SetNeedsLayout(*(DirectUI::Element **)(a1 + 304), 2u);
  v10 = 0;
  v51 = 0;
  do
  {
    if ( v10 > 0 && v6 )
    {
      *(_DWORD *)(a1 + 564) = 0;
      UIItemsView::PreProcessEventQueue(v6);
      *(_DWORD *)(a1 + 564) = 1;
    }
    v11 = *(_QWORD *)(a1 + 224);
    if ( DirectUI::Element::IsHosted((DirectUI::Element *)a1) && v11 && *(int *)(a1 + 488) > 0 )
    {
      *(_DWORD *)(a1 + 512) = 0;
      v12 = *(_DWORD *)(a1 + 488);
      if ( *(_DWORD *)(a1 + 608) == 2 )
      {
        Value = DirectUI::Element::GetValue((DirectUI::Element *)a1, LineScroller::RealYAnchorProp, 1, 0);
        Int = DirectUI::Value::GetInt(Value);
        DirectUI::Value::Release(Value);
      }
      else
      {
        Int = LineScroller::GetRealXAnchor((LineScroller *)a1);
      }
      if ( Int >= 0 )
      {
        if ( Int > 100 * v12 - 1 )
          Int = 100 * v12 - 1;
      }
      else
      {
        Int = 0;
      }
      if ( *(_DWORD *)(a1 + 608) == 2 )
      {
        v15 = DirectUI::Element::GetValue((DirectUI::Element *)a1, LineScroller::RealYTargetProp, 1, 0);
        RealXTarget = DirectUI::Value::GetInt(v15);
        DirectUI::Value::Release(v15);
      }
      else
      {
        RealXTarget = LineScroller::GetRealXTarget((LineScroller *)a1);
      }
      v17 = RealXTarget + 1;
      v52 = RealXTarget + 1;
      v18 = *(DirectUI::Element **)(a1 + 272);
      if ( v18 )
      {
        v19 = *(_DWORD *)(a1 + 608);
        v53 = 0;
        v20 = (__int64)*DirectUI::Element::GetExtent(v18, &v53);
        v50 = v20;
        CValuePtr::~CValuePtr((CValuePtr *)&v53);
        if ( v19 != 1 )
          LODWORD(v20) = HIDWORD(v50);
        v17 = v52;
      }
      else
      {
        LODWORD(v20) = 0;
      }
      v21 = v20 - RealXTarget + 1;
      LODWORD(v53) = v21;
      v22 = (int *)(a1 + 496);
      *(_DWORD *)(a1 + 496) = 0;
      *(_QWORD *)(a1 + 500) = 0;
      *(_DWORD *)(a1 + 508) = 0;
      LODWORD(v50) = v21 + v17;
      v23 = *(_DWORD *)(a1 + 488);
      v24 = v23 - 1;
      if ( v23 <= 0 )
        v24 = 0;
      v25 = Int / 100;
      if ( Int / 100 >= 0 )
      {
        if ( v25 > v24 )
          v25 = v24;
      }
      else
      {
        v25 = 0;
      }
      v26 = *(struct IVirtualizedUI **)(a1 + 224);
      if ( v26 )
        v27 = LineScroller::_RealizeScrollTickWorker((LineScroller *)a1, v26, v25);
      else
        v27 = -2147467259;
      if ( v27 < 0 )
        goto LABEL_67;
      memset_0(v57, 0, 0x58u);
      v58 = -1;
      v61 = 0;
      v60 = -1;
      LineScroller::_GetScrollRow<int>(
        a1,
        (unsigned int) IVirtualizedUI::`vcall'{72,{flat}},
        (unsigned int)s_StepInsideByTick,
        *(_QWORD *)(a1 + 224),
        v25,
        (__int64)v57);
      if ( v59 )
      {
        v28 = v63;
        v29 = v64;
        if ( v66 == 1 )
        {
          v30 = v62;
          v31 = v65;
        }
        else
        {
          v30 = v63;
          v31 = v64;
          v29 = v65;
          v28 = v62;
        }
        rc.left = v28;
        rc.top = v30;
        rc.right = v31;
        rc.bottom = v29;
        xLeft[0] = v28;
        xLeft[1] = v30;
        DUI_MapElementPoint(*(_QWORD *)(a1 + 304), *(_QWORD *)(a1 + 272), 0, xLeft, xLeft);
        SetRect(&rc, xLeft[0], xLeft[1], xLeft[0] + rc.right - rc.left, xLeft[1] + rc.bottom - rc.top);
        right = rc.right;
        left = rc.left;
        top = rc.top;
        if ( v66 != 1 )
          top = rc.left;
        v62 = top;
        if ( v66 != 1 )
          left = rc.top;
        v63 = left;
        bottom = rc.bottom;
        if ( v66 != 1 )
          bottom = rc.right;
        v64 = bottom;
        if ( v66 != 1 )
          right = rc.bottom;
        v65 = right;
      }
      v36 = v60 + 1;
      if ( v60 + 1 >= v60 )
      {
        if ( *(_DWORD *)(a1 + 500) <= *v22 )
        {
          *v22 = v60;
        }
        else if ( *(_DWORD *)(a1 + 500) != v60 )
        {
          if ( v36 == *v22 )
            *v22 = v60;
          goto LABEL_52;
        }
        *(_DWORD *)(a1 + 500) = v36;
      }
LABEL_52:
      v37 = HIDWORD(v61);
      if ( SHIDWORD(v61) < (int)v61 )
        goto LABEL_59;
      v38 = *(_DWORD *)(a1 + 504);
      if ( *(_DWORD *)(a1 + 508) <= v38 )
      {
        *(_DWORD *)(a1 + 504) = v61;
      }
      else if ( *(_DWORD *)(a1 + 508) != (_DWORD)v61 )
      {
        if ( HIDWORD(v61) == v38 )
          *(_DWORD *)(a1 + 504) = v61;
LABEL_59:
        (*(void (__fastcall **)(_QWORD, _BYTE *, _QWORD *, _QWORD))(*(_QWORD *)v57[0] + 128LL))(v57[0], v55, v57, 0);
        v39 = *(_QWORD *)(a1 + 224);
        if ( v39 )
        {
          v40 = 100 * (HIDWORD(v61) - v61);
          v41 = v56 * (100 * HIDWORD(v61) - Int);
          v27 = LineScroller::_RealizeDirectionWorker(
                  a1,
                  v39,
                  (unsigned int)(*v22 - 1),
                  0xFFFFFFFFLL,
                  v52 - v56 * (Int - 100 * (int)v61) / v40,
                  &v50,
                  a1 + 496);
          if ( v27 < 0 )
            goto LABEL_67;
          v42 = v50;
          if ( (int)v50 < 0 )
            v42 = 0;
          v43 = *(_QWORD *)(a1 + 224);
          if ( !v43 )
            goto LABEL_95;
          v27 = LineScroller::_RealizeDirectionWorker(
                  a1,
                  v43,
                  *(unsigned int *)(a1 + 500),
                  1,
                  (int)v53 + v42 - v41 / v40,
                  &v50,
                  a1 + 496);
          if ( v27 < 0 )
          {
LABEL_67:
            *(_DWORD *)(a1 + 512) = v27;
            v10 = ++v51;
            continue;
          }
          v44 = *(_QWORD *)(a1 + 224);
          if ( v44 )
          {
            v27 = LineScroller::_RealizeDirectionWorker(
                    a1,
                    v44,
                    (unsigned int)(*v22 - 1),
                    0xFFFFFFFFLL,
                    v50,
                    &v50,
                    a1 + 496);
            goto LABEL_67;
          }
        }
LABEL_95:
        v27 = -2147467259;
        goto LABEL_67;
      }
      *(_DWORD *)(a1 + 508) = v37;
      goto LABEL_59;
    }
    *(_DWORD *)(a1 + 512) = -2147467259;
    v27 = -2147467259;
    if ( !v11 )
      break;
    v10 = v51;
  }
  while ( v27 == -2147217663 && v10 < 10 );
  if ( DirectUI::Element::IsHosted((DirectUI::Element *)a1) )
  {
    if ( !(_DWORD)v54 && v11 )
    {
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v11 + 8LL))(
        v11,
        0xFFFFFFFFLL,
        (unsigned int)(*(_DWORD *)(a1 + 504) - 1));
      (*(void (__fastcall **)(__int64, __int64, _QWORD))(*(_QWORD *)v11 + 8LL))(v11, 1, *(unsigned int *)(a1 + 508));
    }
    DC = GetDC(0);
    v47 = DC;
    if ( DC )
    {
      DirectUI::DCSurface::DCSurface((DirectUI::DCSurface *)&rc, DC);
      *(_QWORD *)xLeft = DirectUI::Element::GetValue(
                           *(DirectUI::Element **)(a1 + 304),
                           (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::LastDSConstProp,
                           1,
                           0);
      v48 = (__int64)*DirectUI::Value::GetSize(*(DirectUI::Value **)xLeft);
      v54 = v48;
      CValuePtr::~CValuePtr((CValuePtr *)xLeft);
      DirectUI::Element::_UpdateDesiredSize(
        *(DirectUI::Element **)(a1 + 304),
        (unsigned int)xLeft,
        v48,
        (struct DirectUI::Surface *)HIDWORD(v54));
      ReleaseDC(0, v47);
      DirectUI::DCSurface::~DCSurface((DirectUI::DCSurface *)&rc);
    }
  }
  if ( v6 )
    UIItemsView::OnRealizeEnd(v6);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 4) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ItemsView_LineScroller_RealizeContent_Stop,
      v45,
      1);
}

```

## disassembly

```asm
0x180012e50  push    rbp
0x180012e52  push    rbx
0x180012e53  push    rsi
0x180012e54  push    rdi
0x180012e55  push    r12
0x180012e57  push    r13
0x180012e59  push    r14
0x180012e5b  push    r15
0x180012e5d  lea     rbp, [rsp-28h]
0x180012e62  sub     rsp, 128h
0x180012e69  mov     rax, cs:__security_cookie
0x180012e70  xor     rax, rsp
0x180012e73  mov     [rbp+60h+var_50], rax
0x180012e77  mov     dword ptr [rsp+160h+var_100], edx
0x180012e7b  mov     rsi, rcx
0x180012e7e  mov     r15d, 1
0x180012e84  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 4
0x180012e8b  jnz     loc_1800134BD
0x180012e91  mov     rcx, rsi
0x180012e94  call    cs:__imp_?GetTopLevel@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetTopLevel(void)
0x180012e9a  mov     rbx, rax
0x180012e9d  xor     r13d, r13d
0x180012ea0  mov     r14d, r13d
0x180012ea3  test    rax, rax
0x180012ea6  jz      short loc_180012F1B
0x180012ea8  mov     rcx, [rax]
0x180012eab  mov     rax, [rcx+118h]
0x180012eb2  mov     rcx, rbx
0x180012eb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eba  mov     r8, rax
0x180012ebd  mov     rcx, [rax]
0x180012ec0  mov     rax, [rcx+50h]
0x180012ec4  mov     rdx, cs:?Class@UIItemsView@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItemsView::Class
0x180012ecb  mov     rcx, r8
0x180012ece  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ed3  test    al, al
0x180012ed5  jz      short loc_180012F1B
0x180012ed7  cmp     [rbx+1E8h], r13d
0x180012ede  jnz     short loc_180012F18
0x180012ee0  mov     [rbx+30Ch], r15d
0x180012ee7  mov     rcx, [rbx+250h]
0x180012eee  test    rcx, rcx
0x180012ef1  jz      short loc_180012EFF
0x180012ef3  mov     rax, [rcx]
0x180012ef6  mov     rax, [rax+20h]
0x180012efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012eff  mov     rcx, [rbx+248h]
0x180012f06  test    rcx, rcx
0x180012f09  jz      short loc_180012F18
0x180012f0b  call    cs:__imp_DeleteHandle
0x180012f11  mov     [rbx+248h], r13
0x180012f18  mov     r14, rbx
0x180012f1b  mov     rcx, [rsi+130h]
0x180012f22  call    cs:__imp_?MarkNeedsDSUpdate@Element@DirectUI@@QEAAXXZ; DirectUI::Element::MarkNeedsDSUpdate(void)
0x180012f28  mov     edx, 2
0x180012f2d  mov     rcx, [rsi+130h]
0x180012f34  call    cs:__imp_?_SetNeedsLayout@Element@DirectUI@@QEAAHI@Z; DirectUI::Element::_SetNeedsLayout(uint)
0x180012f3a  mov     ecx, r13d
0x180012f3d  mov     [rsp+160h+var_110], ecx
0x180012f41  test    ecx, ecx
0x180012f43  jg      loc_180013558
0x180012f49  mov     r12, [rsi+0E0h]
0x180012f50  mov     rcx, rsi
0x180012f53  call    cs:__imp_?IsHosted@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsHosted(void)
0x180012f59  test    al, al
0x180012f5b  jz      loc_18001335A
0x180012f61  test    r12, r12
0x180012f64  jz      loc_18001335A
0x180012f6a  cmp     [rsi+1E8h], r13d
0x180012f71  jle     loc_18001335A
0x180012f77  mov     [rsi+200h], r13d
0x180012f7e  mov     edi, [rsi+1E8h]
0x180012f84  mov     rcx, rsi; this
0x180012f87  cmp     dword ptr [rsi+260h], 2
0x180012f8e  jnz     loc_1800134E1
0x180012f94  xor     r9d, r9d
0x180012f97  mov     r8d, r15d
0x180012f9a  lea     rdx, ?RealYAnchorProp@LineScroller@@SAPEBUPropertyInfo@DirectUI@@XZ; LineScroller::RealYAnchorProp(void)
0x180012fa1  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180012fa7  mov     rbx, rax
0x180012faa  mov     rcx, rax
0x180012fad  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180012fb3  mov     r15d, eax
0x180012fb6  mov     rcx, rbx
0x180012fb9  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180012fbf  test    r15d, r15d
0x180012fc2  jns     loc_1800134A0
0x180012fc8  mov     r15d, r13d
0x180012fcb  mov     rcx, rsi; this
0x180012fce  cmp     dword ptr [rsi+260h], 2
0x180012fd5  jnz     loc_1800134EE
0x180012fdb  xor     r9d, r9d
0x180012fde  lea     r8d, [r9+1]
0x180012fe2  lea     rdx, ?RealYTargetProp@LineScroller@@SAPEBUPropertyInfo@DirectUI@@XZ; LineScroller::RealYTargetProp(void)
0x180012fe9  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x180012fef  mov     rbx, rax
0x180012ff2  mov     rcx, rax
0x180012ff5  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x180012ffb  mov     r13d, eax
0x180012ffe  mov     rcx, rbx
0x180013001  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x180013007  lea     eax, [r13+1]
0x18001300b  mov     [rsp+160h+var_10C], eax
0x18001300f  mov     rcx, [rsi+110h]
0x180013016  test    rcx, rcx
0x180013019  jz      loc_180013523
0x18001301f  mov     edi, [rsi+260h]
0x180013025  mov     [rsp+160h+var_108], 0
0x18001302e  lea     rdx, [rsp+160h+var_108]
0x180013033  call    cs:__imp_?GetExtent@Element@DirectUI@@QEAAPEBUtagSIZE@@PEAPEAVValue@2@@Z; DirectUI::Element::GetExtent(DirectUI::Value * *)
0x180013039  mov     rbx, [rax]
0x18001303c  mov     [rsp+160h+var_118], rbx
0x180013041  lea     rcx, [rsp+160h+var_108]; this
0x180013046  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18001304b  cmp     edi, 1
0x18001304e  cmovnz  ebx, dword ptr [rsp+160h+var_118+4]
0x180013053  mov     eax, [rsp+160h+var_10C]
0x180013057  sub     ebx, r13d
0x18001305a  lea     ecx, [rbx+1]
0x18001305d  mov     dword ptr [rsp+160h+var_108], ecx
0x180013061  lea     rbx, [rsi+1F0h]
0x180013068  xor     r13d, r13d
0x18001306b  mov     [rbx], r13d
0x18001306e  mov     [rsi+1F4h], r13
0x180013075  mov     [rsi+1FCh], r13d
0x18001307c  add     eax, ecx
0x18001307e  mov     dword ptr [rsp+160h+var_118], eax
0x180013082  mov     ecx, [rsi+1E8h]
0x180013088  lea     r8d, [rcx-1]
0x18001308c  test    ecx, ecx
0x18001308e  cmovle  r8d, r13d
0x180013092  mov     eax, 51EB851Fh
0x180013097  imul    r15d
0x18001309a  mov     edi, edx
0x18001309c  sar     edi, 5
0x18001309f  mov     eax, edi
0x1800130a1  shr     eax, 1Fh
0x1800130a4  add     edi, eax
0x1800130a6  jns     loc_1800134B1
0x1800130ac  mov     edi, r13d
0x1800130af  mov     rdx, [rsi+0E0h]; struct IVirtualizedUI *
0x1800130b6  test    rdx, rdx
0x1800130b9  jz      loc_180013519
0x1800130bf  mov     r8d, edi; int
0x1800130c2  mov     rcx, rsi; this
0x1800130c5  call    ?_RealizeScrollTickWorker@LineScroller@@AEAAJPEAUIVirtualizedUI@@H@Z; LineScroller::_RealizeScrollTickWorker(IVirtualizedUI *,int)
0x1800130ca  test    eax, eax
0x1800130cc  js      loc_18001333E
0x1800130d2  xor     edx, edx; Val
0x1800130d4  lea     r8d, [rdx+58h]; Size
0x1800130d8  lea     rcx, [rbp+60h+var_E0]; void *
0x1800130dc  call    memset_0
0x1800130e1  or      eax, 0FFFFFFFFh
0x1800130e4  mov     [rbp+60h+var_C8], eax
0x1800130e7  mov     [rbp+60h+var_84], r13
0x1800130eb  mov     [rbp+60h+var_88], eax
0x1800130ee  lea     rax, [rbp+60h+var_E0]
0x1800130f2  mov     [rsp+160h+var_138], rax
0x1800130f7  mov     [rsp+160h+yBottom], edi
0x1800130fb  mov     r9, [rsi+0E0h]
0x180013102  lea     r8, ?s_StepInsideByTick@@YAHAEBVSectionInfo@@H@Z; s_StepInsideByTick(SectionInfo const &,int)
0x180013109  lea     rdx, ??_9IVirtualizedUI@@$BEI@AA; [thunk]: IVirtualizedUI::`vcall'{72,{flat}}
0x180013110  mov     rcx, rsi
0x180013113  call    ??$_GetScrollRow@H@LineScroller@@AEAAXP8IVirtualizedUI@@EAAXHPEAVSectionInfo@@@ZP6AHAEBV2@H@ZPEAU1@HPEAVRowInfo@@@Z; LineScroller::_GetScrollRow<int>(void (IVirtualizedUI::*)(int,SectionInfo *),int (*)(SectionInfo const &,int),IVirtualizedUI *,int,RowInfo *)
0x180013118  cmp     [rbp+60h+var_C0], r13d
0x18001311c  jz      loc_1800131D0
0x180013122  mov     ecx, [rbp+60h+var_78]
0x180013125  mov     eax, [rbp+60h+var_74]
0x180013128  cmp     [rbp+60h+var_6C], 1
0x18001312c  jnz     loc_180013509
0x180013132  mov     edx, [rbp+60h+var_7C]
0x180013135  mov     r8d, [rbp+60h+var_70]
0x180013139  mov     [rbp+60h+rc.left], ecx
0x18001313c  mov     [rbp+60h+rc.top], edx
0x18001313f  mov     [rbp+60h+rc.right], r8d
0x180013143  mov     [rbp+60h+rc.bottom], eax
0x180013146  mov     [rsp+160h+xLeft], ecx
0x18001314a  mov     [rsp+160h+xLeft+4], edx
0x18001314e  lea     rax, [rsp+160h+xLeft]
0x180013153  mov     qword ptr [rsp+160h+yBottom], rax
0x180013158  lea     r9, [rsp+160h+xLeft]
0x18001315d  xor     r8d, r8d
0x180013160  mov     rdx, [rsi+110h]
0x180013167  mov     rcx, [rsi+130h]
0x18001316e  call    ?DUI_MapElementPoint@@YAXPEAVElement@DirectUI@@0W4DUI_COORDINATES_SYSTEM@@PEBUtagPOINT@@PEAU4@@Z; DUI_MapElementPoint(DirectUI::Element *,DirectUI::Element *,DUI_COORDINATES_SYSTEM,tagPOINT const *,tagPOINT *)
0x180013173  mov     eax, [rbp+60h+rc.bottom]
0x180013176  sub     eax, [rbp+60h+rc.top]
0x180013179  mov     r8d, [rsp+160h+xLeft+4]; yTop
0x18001317e  add     eax, r8d
0x180013181  mov     r9d, [rbp+60h+rc.right]
0x180013185  sub     r9d, [rbp+60h+rc.left]
0x180013189  mov     edx, [rsp+160h+xLeft]; xLeft
0x18001318d  add     r9d, edx; xRight
0x180013190  mov     [rsp+160h+yBottom], eax; yBottom
0x180013194  lea     rcx, [rbp+60h+rc]; lprc
0x180013198  call    cs:__imp_SetRect
0x18001319e  mov     r8d, [rbp+60h+var_6C]
0x1800131a2  mov     edx, [rbp+60h+rc.right]
0x1800131a5  mov     ecx, [rbp+60h+rc.left]
0x1800131a8  mov     eax, [rbp+60h+rc.top]
0x1800131ab  cmp     r8d, 1
0x1800131af  cmovnz  eax, ecx
0x1800131b2  mov     [rbp+60h+var_7C], eax
0x1800131b5  cmovnz  ecx, [rbp+60h+rc.top]
0x1800131b9  mov     [rbp+60h+var_78], ecx
0x1800131bc  mov     eax, [rbp+60h+rc.bottom]
0x1800131bf  cmovnz  eax, edx
0x1800131c2  mov     [rbp+60h+var_74], eax
0x1800131c5  cmovnz  edx, [rbp+60h+rc.bottom]
0x1800131c9  mov     [rbp+60h+var_70], edx
0x1800131cc  mov     [rbp+60h+var_6C], r8d
0x1800131d0  mov     eax, [rbp+60h+var_88]
0x1800131d3  lea     ecx, [rax+1]
0x1800131d6  cmp     ecx, eax
0x1800131d8  jl      short loc_1800131F5
0x1800131da  mov     edx, [rbx]
0x1800131dc  cmp     [rbx+4], edx
0x1800131df  jl      short loc_1800131F0
0x1800131e1  jz      short loc_1800131F0
0x1800131e3  cmp     [rbx+4], eax
0x1800131e6  jz      short loc_1800131F2
0x1800131e8  cmp     ecx, edx
0x1800131ea  jnz     short loc_1800131F5
0x1800131ec  mov     [rbx], eax
0x1800131ee  jmp     short loc_1800131F5
0x1800131f0  mov     [rbx], eax
0x1800131f2  mov     [rbx+4], ecx
0x1800131f5  mov     eax, dword ptr [rbp+60h+var_84+4]
0x1800131f8  mov     ecx, dword ptr [rbp+60h+var_84]
0x1800131fb  cmp     eax, ecx
0x1800131fd  jl      short loc_18001321D
0x1800131ff  mov     edx, [rbx+8]
0x180013202  cmp     [rbx+0Ch], edx
0x180013205  jl      short loc_180013217
0x180013207  jz      short loc_180013217
0x180013209  cmp     [rbx+0Ch], ecx
0x18001320c  jz      short loc_18001321A
0x18001320e  cmp     eax, edx
0x180013210  jnz     short loc_18001321D
0x180013212  mov     [rbx+8], ecx
0x180013215  jmp     short loc_18001321D
0x180013217  mov     [rbx+8], ecx
0x18001321a  mov     [rbx+0Ch], eax
0x18001321d  mov     rcx, [rbp+60h+var_E0]
0x180013221  mov     rax, [rcx]
0x180013224  xor     r9d, r9d
0x180013227  lea     r8, [rbp+60h+var_E0]
0x18001322b  lea     rdx, [rsp+160h+var_F8]
0x180013230  mov     rax, [rax+80h]
0x180013237  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001323c  mov     rcx, [rsi+0E0h]
0x180013243  test    rcx, rcx
0x180013246  jz      loc_18001354E
0x18001324c  mov     eax, dword ptr [rbp+60h+var_84+4]
0x18001324f  sub     eax, dword ptr [rbp+60h+var_84]
0x180013252  imul    r13d, eax, 64h ; 'd'
0x180013256  imul    edi, dword ptr [rbp+60h+var_84+4], 64h ; 'd'
0x18001325a  sub     edi, r15d
0x18001325d  imul    edi, [rsp+160h+var_F4]
0x180013262  imul    eax, dword ptr [rbp+60h+var_84], 64h ; 'd'
0x180013266  sub     r15d, eax
0x180013269  imul    r15d, [rsp+160h+var_F4]
0x18001326f  mov     eax, r15d
0x180013272  cdq
0x180013273  idiv    r13d
0x180013276  mov     edx, [rsp+160h+var_10C]
0x18001327a  sub     edx, eax
0x18001327c  mov     r8d, [rbx]
0x18001327f  dec     r8d
0x180013282  mov     [rsp+160h+var_130], rbx
0x180013287  lea     rax, [rsp+160h+var_118]
0x18001328c  mov     [rsp+160h+var_138], rax
0x180013291  mov     [rsp+160h+yBottom], edx
0x180013295  or      r15d, 0FFFFFFFFh
0x180013299  mov     r9d, r15d
0x18001329c  mov     rdx, rcx
0x18001329f  mov     rcx, rsi
0x1800132a2  call    ?_RealizeDirectionWorker@LineScroller@@AEAAJPEAUIVirtualizedUI@@HW4REALIZEDIRECTION@@HPEAHPEAVCRealizedIntervalHelper@@@Z; LineScroller::_RealizeDirectionWorker(IVirtualizedUI *,int,REALIZEDIRECTION,int,int *,CRealizedIntervalHelper *)
0x1800132a7  test    eax, eax
0x1800132a9  js      loc_18001333E
0x1800132af  mov     r8d, dword ptr [rsp+160h+var_118]
0x1800132b4  xor     ecx, ecx
0x1800132b6  test    r8d, r8d
0x1800132b9  cmovs   r8d, ecx
0x1800132bd  mov     rcx, [rsi+0E0h]
0x1800132c4  test    rcx, rcx
0x1800132c7  jz      loc_18001354E
0x1800132cd  mov     eax, edi
0x1800132cf  cdq
0x1800132d0  idiv    r13d
0x1800132d3  sub     r8d, eax
0x1800132d6  add     r8d, dword ptr [rsp+160h+var_108]
0x1800132db  mov     [rsp+160h+var_130], rbx
0x1800132e0  lea     rax, [rsp+160h+var_118]
0x1800132e5  mov     [rsp+160h+var_138], rax
0x1800132ea  mov     [rsp+160h+yBottom], r8d
0x1800132ef  lea     r9d, [r15+2]
0x1800132f3  mov     r8d, [rbx+4]
0x1800132f7  mov     rdx, rcx
0x1800132fa  mov     rcx, rsi
  ... truncated ...
```
