# UIProperty::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)

- ea: `0x1800a3c10`
- end: `0x1800a4335`
- name: `?Paint@UIProperty@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU3@2@Z`
- size: `1829`
- prototype: `void __usercall(UIProperty *__hidden this@<rcx>, HDC hdc@<rdx>, const struct tagRECT *@<r8>, const struct tagRECT *@<r9>, struct tagRECT *, struct tagRECT *)`
- caller_count: `0`
- callee_count: `8`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18000dd48`
- `0x180016790`
- `0x1800a3c10`
- `0x180124710`
- `0x18012ea9c`
- `0x180130024`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_Set` at `0x1800a3da0`
- `SHCORE!IUnknown_Set` at `0x1800a3da0`
- `USER32!SetRect` at `0x1800a4073`
- `USER32!SetRect` at `0x1800a4073`
- `GDI32!SelectObject` at `0x1800a3f4d`
- `GDI32!SelectObject` at `0x1800a417b`
- `GDI32!SelectObject` at `0x1800a3f4d`
- `GDI32!SelectObject` at `0x1800a417b`
- `GDI32!SetBkMode` at `0x1800a4128`
- `GDI32!SetBkMode` at `0x1800a4153`
- `GDI32!SetBkMode` at `0x1800a4128`
- `GDI32!SetBkMode` at `0x1800a4153`
- `GDI32!GetLayout` at `0x1800a3e66`
- `GDI32!GetLayout` at `0x1800a3e66`
- `DUI70!?GetFill@Value@DirectUI@@QEAAPEBUFill@2@XZ` at `0x1800a40fb`
- `DUI70!?GetFill@Value@DirectUI@@QEAAPEBUFill@2@XZ` at `0x1800a40fb`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x1800a3d11`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x1800a3d11`
- `DUI70!ARGBColorFromEnumI` at `0x1800a4329`
- `DUI70!ARGBColorFromEnumI` at `0x1800a4329`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800a3c8b`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800a3f93`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800a4267`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800a3c8b`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800a3f93`
- `DUI70!?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z` at `0x1800a4267`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800a3fee`
- `DUI70!?GetParent@Element@DirectUI@@QEAAPEAV12@XZ` at `0x1800a3fee`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800a3d1c`
- `DUI70!?IsRTL@Element@DirectUI@@QEAA_NXZ` at `0x1800a3d1c`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a3e08`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a3e50`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a3f66`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a423f`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a3e08`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a3e50`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a3f66`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x1800a423f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a3dfd`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a3e45`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a4321`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a3dfd`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a3e45`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x1800a4321`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x1800a41fe`
- `DUI70!?GetContentString@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x1800a41fe`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800a40e9`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800a430f`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800a40e9`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x1800a430f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a3df1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a3e39`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a40d9`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a3df1`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a3e39`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x1800a40d9`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800a4003`
- `DUI70!?GetSelected@Element@DirectUI@@QEAA_NXZ` at `0x1800a4003`
- `DUI70!?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x1800a40cf`
- `DUI70!?GetFontFace@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x1800a3f09`
- `DUI70!?GetFontFace@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z` at `0x1800a3f09`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x1800a3efa`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x1800a404a`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x1800a3efa`
- `DUI70!?GetFontSize@Element@DirectUI@@QEAAHXZ` at `0x1800a404a`
- `DUI70!?GetFontWeight@Element@DirectUI@@QEAAHXZ` at `0x1800a3eef`
- `DUI70!?GetFontWeight@Element@DirectUI@@QEAAHXZ` at `0x1800a3eef`
- `DUI70!?GetFontStyle@Element@DirectUI@@QEAAHXZ` at `0x1800a3ee4`
- `DUI70!?GetFontStyle@Element@DirectUI@@QEAAHXZ` at `0x1800a3ee4`
- `DUI70!?GetFontQuality@Element@DirectUI@@QEAAHXZ` at `0x1800a3ed8`
- `DUI70!?GetFontQuality@Element@DirectUI@@QEAAHXZ` at `0x1800a3ed8`
- `DUI70!GetFontCache` at `0x1800a3eb0`
- `DUI70!GetFontCache` at `0x1800a3eb0`
- `DUI70!?PaintFocusRect@Element@DirectUI@@QEAAXPEAUHDC__@@PEBUtagRECT@@1@Z` at `0x1800a3fa6`
- `DUI70!?PaintFocusRect@Element@DirectUI@@QEAAXPEAUHDC__@@PEBUtagRECT@@1@Z` at `0x1800a427a`
- `DUI70!?PaintFocusRect@Element@DirectUI@@QEAAXPEAUHDC__@@PEBUtagRECT@@1@Z` at `0x1800a3fa6`
- `DUI70!?PaintFocusRect@Element@DirectUI@@QEAAXPEAUHDC__@@PEBUtagRECT@@1@Z` at `0x1800a427a`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
void __fastcall UIProperty::Paint(
        IUnknown **this,
        HDC hdc,
        const struct tagRECT *a3,
        const struct tagRECT *a4,
        struct tagRECT *a5)
{
  HDC v7; // r15
  struct tagRECT *v9; // rdx
  const struct tagRECT *v10; // r8
  const struct tagRECT *v11; // r9
  unsigned int v12; // esi
  __int64 v13; // rax
  __int64 v14; // r14
  char ContentAlign; // di
  int v16; // edi
  int v17; // eax
  struct DirectUI::Value *v18; // r14
  void (__fastcall *v19)(struct DirectUI::Value *, _QWORD); // rsi
  DirectUI::Value *Value; // rbx
  unsigned int Int; // edi
  struct DirectUI::Value *v22; // r14
  void (__fastcall *v23)(struct DirectUI::Value *, _QWORD); // rsi
  DirectUI::Value *v24; // rbx
  unsigned int v25; // edi
  DWORD Layout; // eax
  const char *v27; // r9
  char v28; // bl
  struct DirectUI::Value *v29; // rcx
  __int64 (__fastcall ***FontCache)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD, int, int, _DWORD); // rax
  __int64 (__fastcall *v31)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD, int, int, _DWORD); // r15
  int FontQuality; // r14d
  int FontStyle; // esi
  unsigned int FontWeight; // edi
  unsigned int FontSize; // ebx
  const unsigned __int16 *FontFace; // rax
  void *v37; // rax
  DirectUI::Value *v38; // rcx
  int v39; // r14d
  struct DirectUI::IClassInfo *v40; // rdi
  DirectUI::Element *Parent; // rbx
  __int64 v42; // rax
  int v43; // eax
  int v44; // ecx
  int v45; // ecx
  LONG right; // eax
  int v47; // eax
  LONG bottom; // ecx
  IUnknown *v49; // r14
  ULONG (__stdcall *AddRef)(IUnknown *); // r12
  DirectUI::Value *v51; // rbx
  __int64 v52; // rax
  int v53; // ebx
  IUnknown *v54; // rcx
  const unsigned __int16 *v55; // rdx
  const unsigned __int16 *ContentString; // rax
  const unsigned __int16 *v57; // r14
  IUnknown *v58; // rcx
  unsigned int v59; // eax
  unsigned int v60; // [rsp+40h] [rbp-79h] BYREF
  struct DirectUI::Value *v61; // [rsp+48h] [rbp-71h] BYREF
  IUnknown *ppunk; // [rsp+50h] [rbp-69h] BYREF
  int v63; // [rsp+58h] [rbp-61h] BYREF
  HDC hdca; // [rsp+60h] [rbp-59h]
  void *v65; // [rsp+68h] [rbp-51h]
  __int64 (__fastcall ***v66)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD); // [rsp+70h] [rbp-49h]
  HGDIOBJ h; // [rsp+78h] [rbp-41h]
  HDC v68; // [rsp+80h] [rbp-39h]
  struct tagRECT *v69; // [rsp+88h] [rbp-31h]
  struct tagRECT v70; // [rsp+90h] [rbp-29h] BYREF
  struct tagRECT rc; // [rsp+A0h] [rbp-19h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+4Fh]

  *(_QWORD *)&rc.left = a4;
  v7 = hdc;
  hdca = hdc;
  v69 = a5;
  if ( (unsigned __int8)ATL::CComPtrBase<IDrawPropertyControl>::operator!(this + 75) )
  {
    if ( (unsigned __int8)ATL::CComPtrBase<IDrawPropertyControl>::operator!(this + 26) )
    {
      DirectUI::Element::Paint((DirectUI::Element *)this, v7, v10, v11, a5, v9);
    }
    else
    {
      if ( *((_DWORD *)this + 136) != 2 || *((_DWORD *)this + 128) )
      {
        *((_DWORD *)this + 136) = 2;
        v55 = (const unsigned __int16 *)this[61];
        if ( v55 )
        {
          if ( UIProperty::_UpdateTextService((UIProperty *)this, v55) )
          {
            ((void (__fastcall *)(IUnknown *, IUnknown *))this[26]->lpVtbl[4].Release)(this[26], this[61]);
            *((_DWORD *)this + 128) = 0;
          }
        }
        else
        {
          ppunk = 0;
          ContentString = DirectUI::Element::GetContentString(
                            (DirectUI::Element *)this,
                            (struct DirectUI::Value **)&ppunk);
          v57 = ContentString;
          if ( ContentString && UIProperty::_UpdateTextService((UIProperty *)this, ContentString) )
            ((void (__fastcall *)(IUnknown *, const unsigned __int16 *))this[26]->lpVtbl[4].Release)(this[26], v57);
          v58 = ppunk;
          if ( ppunk )
          {
            ppunk = 0;
            DirectUI::Value::Release((DirectUI::Value *)v58);
          }
        }
      }
      v70 = 0;
      DirectUI::Element::Paint((DirectUI::Element *)this, v7, a3, a4, a5, &v70);
      DirectUI::Element::PaintFocusRect((DirectUI::Element *)this, v7, a3, &v70);
    }
    return;
  }
  v12 = 0;
  ppunk = 0;
  ((void (__fastcall *)(IUnknown *, IUnknown *))this[75]->lpVtbl[3].Release)(this[75], this[76]);
  v13 = ATL::CComPtrBase<IUICommandHandler>::operator->(this + 75);
  (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v13 + 112LL))(v13, *((unsigned int *)this + 148));
  v14 = ATL::CComPtrBase<IUICommandHandler>::operator->(this + 75);
  if ( v14 )
  {
    ContentAlign = DirectUI::Element::GetContentAlign((DirectUI::Element *)this);
    if ( DirectUI::Element::IsRTL((DirectUI::Element *)this) )
    {
      v12 = 512;
      if ( (ContentAlign & 3) != 0 )
      {
        if ( (ContentAlign & 3) == 2 )
          ContentAlign &= ~2u;
      }
      else
      {
        ContentAlign |= 2u;
      }
    }
    if ( (ContentAlign & 3) != 0 )
    {
      if ( (ContentAlign & 3) == 1 )
      {
        v12 |= 0x40u;
      }
      else if ( (ContentAlign & 3) == 2 )
      {
        v12 |= 0x80u;
      }
    }
    v16 = ContentAlign & 0xC;
    if ( v16 == 4 )
    {
      v12 |= 0x10u;
    }
    else if ( v16 == 8 )
    {
      v12 |= 0x20u;
    }
    v60 = 0;
    (*(void (__fastcall **)(__int64, unsigned int *))(*(_QWORD *)v14 + 64LL))(v14, &v60);
    if ( (v60 & 0x6F0) != v12 )
      (*(void (__fastcall **)(__int64, _QWORD, __int64))(*(_QWORD *)v14 + 72LL))(v14, v12, 1776);
  }
  ppunk = 0;
  IUnknown_Set(&ppunk, this[75]);
  v61 = 0;
  v17 = ((__int64 (__fastcall *)(IUnknown *, GUID *, struct DirectUI::Value **))ppunk->lpVtbl->QueryInterface)(
          ppunk,
          &GUID_cf599b9b_8917_4417_9874_1af7148fa8d1,
          &v61);
  v60 = -1;
  if ( v17 >= 0 )
  {
    v18 = v61;
    v19 = *(void (__fastcall **)(struct DirectUI::Value *, _QWORD))(*(_QWORD *)v61 + 24LL);
    Value = DirectUI::Element::GetValue((DirectUI::Element *)this, UIProperty::IconDisplayLimitProp, 2, 0);
    Int = DirectUI::Value::GetInt(Value);
    DirectUI::Value::Release(Value);
    v19(v18, Int);
    v22 = v61;
    v23 = *(void (__fastcall **)(struct DirectUI::Value *, _QWORD))(*(_QWORD *)v61 + 40LL);
    v24 = DirectUI::Element::GetValue((DirectUI::Element *)this, UIProperty::IconSizeProp, 2, 0);
    v25 = DirectUI::Value::GetInt(v24);
    DirectUI::Value::Release(v24);
    v23(v22, v25);
    Layout = GetLayout(v7);
    v28 = Layout;
    if ( Layout == -1 )
      wil::details::in1diag3::_Log_GetLastError(
        retaddr,
        (void *)0x13A,
        (unsigned int)"shell\\explorerframe\\itemsview\\uiproperty.cpp",
        v27);
    (*(void (__fastcall **)(struct DirectUI::Value *, _QWORD))(*(_QWORD *)v61 + 48LL))(v61, v28 & 1);
  }
  v29 = v61;
  if ( v61 )
  {
    v61 = 0;
    (*(void (__fastcall **)(struct DirectUI::Value *))(*(_QWORD *)v29 + 16LL))(v29);
  }
  v65 = 0;
  FontCache = (__int64 (__fastcall ***)(_QWORD, const unsigned __int16 *, _QWORD, _QWORD, int, int, _DWORD))GetFontCache();
  v66 = (__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD))FontCache;
  h = 0;
  v68 = v7;
  if ( FontCache )
  {
    v61 = 0;
    v31 = **FontCache;
    FontQuality = DirectUI::Element::GetFontQuality((DirectUI::Element *)this);
    FontStyle = DirectUI::Element::GetFontStyle((DirectUI::Element *)this);
    FontWeight = DirectUI::Element::GetFontWeight((DirectUI::Element *)this);
    FontSize = DirectUI::Element::GetFontSize((DirectUI::Element *)this);
    FontFace = DirectUI::Element::GetFontFace((DirectUI::Element *)this, &v61);
    v37 = (void *)v31(v66, FontFace, FontSize, FontWeight, FontStyle, FontQuality, 0);
    v65 = v37;
    v7 = hdca;
    if ( v37 && hdca )
      h = SelectObject(hdca, v37);
    v38 = v61;
    if ( v61 )
    {
      v61 = 0;
      DirectUI::Value::Release(v38);
    }
  }
  v70 = 0;
  DirectUI::Element::Paint((DirectUI::Element *)this, v7, a3, *(const struct tagRECT **)&rc.left, v69, &v70);
  DirectUI::Element::PaintFocusRect((DirectUI::Element *)this, v7, a3, &v70);
  v39 = 0;
  LODWORD(v61) = 0;
  v40 = UIItem::Class;
  Parent = (DirectUI::Element *)this;
  while ( 1 )
  {
    v42 = (*(__int64 (__fastcall **)(DirectUI::Element *))(*(_QWORD *)Parent + 280LL))(Parent);
    if ( (*(unsigned __int8 (__fastcall **)(__int64, struct DirectUI::IClassInfo *))(*(_QWORD *)v42 + 80LL))(v42, v40) )
      break;
    Parent = DirectUI::Element::GetParent(Parent);
    if ( !Parent )
      goto LABEL_33;
  }
  if ( DirectUI::Element::GetSelected(Parent) )
    v39 = 1;
  LODWORD(v61) = v39;
LABEL_33:
  v63 = 0;
  if ( ((int (__fastcall *)(IUnknown *, int *))ppunk->lpVtbl[5].AddRef)(ppunk, &v63) >= 0 && (v63 & 8) != 0 )
  {
    rc = 0;
    v43 = DirectUI::Element::GetFontSize((DirectUI::Element *)this);
    v44 = -v43;
    if ( v43 > 0 )
      v44 = v43;
    SetRect(&rc, v44 / 6, 0, v44 / 6, 0);
    v45 = rc.left + v70.left;
    v70.left = v45;
    right = v70.right;
    if ( v45 > v70.right )
    {
      v70.left = v70.right;
    }
    else
    {
      v70.right -= rc.right;
      if ( right - rc.right < v45 )
        v70.right = v45;
    }
    v47 = rc.top + v70.top;
    v70.top = v47;
    bottom = v70.bottom;
    if ( v47 > v70.bottom )
    {
      v70.top = v70.bottom;
    }
    else
    {
      v70.bottom -= rc.bottom;
      if ( bottom - rc.bottom < v47 )
        v70.bottom = v47;
    }
  }
  v49 = ppunk;
  AddRef = ppunk->lpVtbl[2].AddRef;
  v51 = DirectUI::Element::GetValue(
          (DirectUI::Element *)this,
          (const struct DirectUI::PropertyInfo *(*)(void))DirectUI::Element::ForegroundProp,
          2,
          0);
  *(_QWORD *)&rc.left = v51;
  if ( DirectUI::Value::GetType(v51) == 9 )
  {
    LODWORD(v52) = *((_DWORD *)DirectUI::Value::GetFill(v51) + 2);
  }
  else
  {
    if ( DirectUI::Value::GetType(v51) != 1 )
      goto LABEL_46;
    v59 = DirectUI::Value::GetInt(v51);
    v52 = ARGBColorFromEnumI(v59);
  }
  v60 = v52 & 0xFFFFFF;
LABEL_46:
  CValuePtr::~CValuePtr((CValuePtr *)&rc);
  ((void (__fastcall *)(IUnknown *, _QWORD))AddRef)(v49, v60);
  v53 = SetBkMode(v7, 1);
  ((void (__fastcall *)(IUnknown *, HDC, struct tagRECT *, _QWORD))ppunk->lpVtbl[5].Release)(
    ppunk,
    v7,
    &v70,
    (unsigned int)v61);
  SetBkMode(v7, v53);
  if ( v66 )
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD)))(*v66)[1])(v66);
  if ( v7 )
    SelectObject(v7, h);
  v54 = ppunk;
  if ( ppunk )
  {
    ppunk = 0;
    ((void (__fastcall *)(IUnknown *))v54->lpVtbl->Release)(v54);
  }
}

```

## disassembly

```asm
0x1800a3c10  push    rbp
0x1800a3c12  push    rbx
0x1800a3c13  push    rsi
0x1800a3c14  push    rdi
0x1800a3c15  push    r12
0x1800a3c17  push    r13
0x1800a3c19  push    r14
0x1800a3c1b  push    r15
0x1800a3c1d  lea     rbp, [rsp-0Fh]
0x1800a3c22  sub     rsp, 0C8h
0x1800a3c29  mov     rax, cs:__security_cookie
0x1800a3c30  xor     rax, rsp
0x1800a3c33  mov     [rbp+47h+var_50], rax
0x1800a3c37  mov     rdi, r9
0x1800a3c3a  mov     qword ptr [rbp+47h+rc.left], r9
0x1800a3c3e  mov     r12, r8
0x1800a3c41  mov     r15, rdx
0x1800a3c44  mov     [rbp+47h+hdc], rdx
0x1800a3c48  mov     r13, rcx
0x1800a3c4b  mov     rsi, [rbp+47h+arg_20]
0x1800a3c4f  mov     [rbp+47h+var_78], rsi
0x1800a3c53  mov     rdx, [rbp+47h+arg_28]
0x1800a3c57  add     rcx, 258h
0x1800a3c5e  call    ??7?$CComPtrBase@UIDrawPropertyControl@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IDrawPropertyControl>::operator!(void)
0x1800a3c63  test    al, al
0x1800a3c65  jz      short loc_1800A3CB1
0x1800a3c67  lea     rcx, [r13+0D0h]
0x1800a3c6e  call    ??7?$CComPtrBase@UIDrawPropertyControl@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IDrawPropertyControl>::operator!(void)
0x1800a3c73  test    al, al
0x1800a3c75  jz      loc_1800A41C2
0x1800a3c7b  mov     [rsp+100h+var_D8], rdx
0x1800a3c80  mov     qword ptr [rsp+100h+yBottom], rsi
0x1800a3c85  mov     rdx, r15
0x1800a3c88  mov     rcx, r13
0x1800a3c8b  call    cs:__imp_?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z; DirectUI::Element::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)
0x1800a3c91  mov     rcx, [rbp+47h+var_50]
0x1800a3c95  xor     rcx, rsp; StackCookie
0x1800a3c98  call    __security_check_cookie
0x1800a3c9d  add     rsp, 0C8h
0x1800a3ca4  pop     r15
0x1800a3ca6  pop     r14
0x1800a3ca8  pop     r13
0x1800a3caa  pop     r12
0x1800a3cac  pop     rdi
0x1800a3cad  pop     rsi
0x1800a3cae  pop     rbx
0x1800a3caf  pop     rbp
0x1800a3cb0  retn
0x1800a3cb1  xor     esi, esi
0x1800a3cb3  mov     [rbp+47h+ppunk], rsi
0x1800a3cb7  mov     rcx, [r13+258h]
0x1800a3cbe  mov     rax, [rcx]
0x1800a3cc1  mov     rdx, [r13+260h]
0x1800a3cc8  mov     rax, [rax+58h]
0x1800a3ccc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3cd1  lea     rcx, [r13+258h]
0x1800a3cd8  call    ??C?$CComPtrBase@UIUICommandHandler@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIUICommandHandler@@@1@XZ; ATL::CComPtrBase<IUICommandHandler>::operator->(void)
0x1800a3cdd  mov     r8, rax
0x1800a3ce0  mov     rcx, [rax]
0x1800a3ce3  mov     rax, [rcx+70h]
0x1800a3ce7  mov     edx, [r13+250h]
0x1800a3cee  mov     rcx, r8
0x1800a3cf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3cf6  lea     rcx, [r13+258h]
0x1800a3cfd  call    ??C?$CComPtrBase@UIUICommandHandler@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UIUICommandHandler@@@1@XZ; ATL::CComPtrBase<IUICommandHandler>::operator->(void)
0x1800a3d02  mov     r14, rax
0x1800a3d05  test    rax, rax
0x1800a3d08  jz      loc_1800A3D91
0x1800a3d0e  mov     rcx, r13
0x1800a3d11  call    cs:__imp_?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x1800a3d17  mov     edi, eax
0x1800a3d19  mov     rcx, r13
0x1800a3d1c  call    cs:__imp_?IsRTL@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::IsRTL(void)
0x1800a3d22  test    al, al
0x1800a3d24  jnz     loc_1800A428E
0x1800a3d2a  mov     ecx, edi
0x1800a3d2c  and     ecx, 3
0x1800a3d2f  jz      short loc_1800A3D43
0x1800a3d31  sub     ecx, 1
0x1800a3d34  jz      loc_1800A42F1
0x1800a3d3a  cmp     ecx, 1
0x1800a3d3d  jz      loc_1800A4285
0x1800a3d43  and     edi, 0Ch
0x1800a3d46  cmp     edi, 4
0x1800a3d49  jnz     loc_1800A41A1
0x1800a3d4f  or      esi, 10h
0x1800a3d52  mov     [rbp+47h+var_C0], 0
0x1800a3d59  mov     rax, [r14]
0x1800a3d5c  lea     rdx, [rbp+47h+var_C0]
0x1800a3d60  mov     rcx, r14
0x1800a3d63  mov     rax, [rax+40h]
0x1800a3d67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3d6c  mov     eax, [rbp+47h+var_C0]
0x1800a3d6f  and     eax, 6F0h
0x1800a3d74  cmp     eax, esi
0x1800a3d76  jz      short loc_1800A3D8F
0x1800a3d78  mov     rax, [r14]
0x1800a3d7b  mov     r8d, 6F0h
0x1800a3d81  mov     edx, esi
0x1800a3d83  mov     rcx, r14
0x1800a3d86  mov     rax, [rax+48h]
0x1800a3d8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3d8f  xor     esi, esi
0x1800a3d91  mov     [rbp+47h+ppunk], rsi
0x1800a3d95  mov     rdx, [r13+258h]; punk
0x1800a3d9c  lea     rcx, [rbp+47h+ppunk]; ppunk
0x1800a3da0  call    cs:__imp_IUnknown_Set
0x1800a3da6  mov     [rbp+47h+var_B8], rsi
0x1800a3daa  mov     rcx, [rbp+47h+ppunk]
0x1800a3dae  mov     rax, [rcx]
0x1800a3db1  lea     r8, [rbp+47h+var_B8]
0x1800a3db5  lea     rdx, _GUID_cf599b9b_8917_4417_9874_1af7148fa8d1
0x1800a3dbc  mov     rax, [rax]
0x1800a3dbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3dc4  mov     [rbp+47h+var_C0], 0FFFFFFFFh
0x1800a3dcb  test    eax, eax
0x1800a3dcd  js      loc_1800A3E92
0x1800a3dd3  mov     r14, [rbp+47h+var_B8]
0x1800a3dd7  mov     rax, [r14]
0x1800a3dda  mov     rsi, [rax+18h]
0x1800a3dde  xor     r9d, r9d
0x1800a3de1  mov     r8d, 2
0x1800a3de7  lea     rdx, ?IconDisplayLimitProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::IconDisplayLimitProp(void)
0x1800a3dee  mov     rcx, r13
0x1800a3df1  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800a3df7  mov     rbx, rax
0x1800a3dfa  mov     rcx, rax
0x1800a3dfd  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800a3e03  mov     edi, eax
0x1800a3e05  mov     rcx, rbx
0x1800a3e08  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800a3e0e  mov     edx, edi
0x1800a3e10  mov     rcx, r14
0x1800a3e13  mov     rax, rsi
0x1800a3e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e1b  mov     r14, [rbp+47h+var_B8]
0x1800a3e1f  mov     rax, [r14]
0x1800a3e22  mov     rsi, [rax+28h]
0x1800a3e26  xor     r9d, r9d
0x1800a3e29  mov     r8d, 2
0x1800a3e2f  lea     rdx, ?IconSizeProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::IconSizeProp(void)
0x1800a3e36  mov     rcx, r13
0x1800a3e39  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x1800a3e3f  mov     rbx, rax
0x1800a3e42  mov     rcx, rax
0x1800a3e45  call    cs:__imp_?GetInt@Value@DirectUI@@QEAAHXZ; DirectUI::Value::GetInt(void)
0x1800a3e4b  mov     edi, eax
0x1800a3e4d  mov     rcx, rbx
0x1800a3e50  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800a3e56  mov     edx, edi
0x1800a3e58  mov     rcx, r14
0x1800a3e5b  mov     rax, rsi
0x1800a3e5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e63  mov     rcx, r15; hdc
0x1800a3e66  call    cs:__imp_GetLayout
0x1800a3e6c  mov     ebx, eax
0x1800a3e6e  mov     rcx, [rbp+4Fh]; this
0x1800a3e72  cmp     eax, 0FFFFFFFFh
0x1800a3e75  jz      loc_1800A42F9
0x1800a3e7b  mov     rcx, [rbp+47h+var_B8]
0x1800a3e7f  mov     rax, [rcx]
0x1800a3e82  and     ebx, 1
0x1800a3e85  mov     edx, ebx
0x1800a3e87  mov     rax, [rax+30h]
0x1800a3e8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3e90  xor     esi, esi
0x1800a3e92  mov     rcx, [rbp+47h+var_B8]
0x1800a3e96  test    rcx, rcx
0x1800a3e99  jz      short loc_1800A3EAC
0x1800a3e9b  mov     [rbp+47h+var_B8], rsi
0x1800a3e9f  mov     rax, [rcx]
0x1800a3ea2  mov     rax, [rax+10h]
0x1800a3ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3eab  nop
0x1800a3eac  mov     [rbp+47h+var_98], rsi
0x1800a3eb0  call    cs:__imp_GetFontCache
0x1800a3eb6  mov     [rbp+47h+var_90], rax
0x1800a3eba  mov     [rbp+47h+h], rsi
0x1800a3ebe  mov     [rbp+47h+var_80], r15
0x1800a3ec2  test    rax, rax
0x1800a3ec5  jz      loc_1800A3F6D
0x1800a3ecb  mov     [rbp+47h+var_B8], rsi
0x1800a3ecf  mov     rax, [rax]
0x1800a3ed2  mov     r15, [rax]
0x1800a3ed5  mov     rcx, r13
0x1800a3ed8  call    cs:__imp_?GetFontQuality@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontQuality(void)
0x1800a3ede  mov     r14d, eax
0x1800a3ee1  mov     rcx, r13
0x1800a3ee4  call    cs:__imp_?GetFontStyle@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontStyle(void)
0x1800a3eea  mov     esi, eax
0x1800a3eec  mov     rcx, r13
0x1800a3eef  call    cs:__imp_?GetFontWeight@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontWeight(void)
0x1800a3ef5  mov     edi, eax
0x1800a3ef7  mov     rcx, r13
0x1800a3efa  call    cs:__imp_?GetFontSize@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontSize(void)
0x1800a3f00  mov     ebx, eax
0x1800a3f02  lea     rdx, [rbp+47h+var_B8]
0x1800a3f06  mov     rcx, r13
0x1800a3f09  call    cs:__imp_?GetFontFace@Element@DirectUI@@QEAAPEBGPEAPEAVValue@2@@Z; DirectUI::Element::GetFontFace(DirectUI::Value * *)
0x1800a3f0f  mov     [rsp+100h+var_D0], 0
0x1800a3f17  mov     dword ptr [rsp+100h+var_D8], r14d
0x1800a3f1c  mov     [rsp+100h+yBottom], esi
0x1800a3f20  mov     r9d, edi
0x1800a3f23  mov     r8d, ebx
0x1800a3f26  mov     rdx, rax
0x1800a3f29  mov     rcx, [rbp+47h+var_90]
0x1800a3f2d  mov     rax, r15
0x1800a3f30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3f35  mov     [rbp+47h+var_98], rax
0x1800a3f39  mov     r15, [rbp+47h+hdc]
0x1800a3f3d  test    rax, rax
0x1800a3f40  jz      short loc_1800A3F57
0x1800a3f42  test    r15, r15
0x1800a3f45  jz      short loc_1800A3F57
0x1800a3f47  mov     rdx, rax; h
0x1800a3f4a  mov     rcx, r15; hdc
0x1800a3f4d  call    cs:__imp_SelectObject
0x1800a3f53  mov     [rbp+47h+h], rax
0x1800a3f57  mov     rcx, [rbp+47h+var_B8]
0x1800a3f5b  xor     esi, esi
0x1800a3f5d  test    rcx, rcx
0x1800a3f60  jz      short loc_1800A3F6D
0x1800a3f62  mov     [rbp+47h+var_B8], rsi
0x1800a3f66  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x1800a3f6c  nop
0x1800a3f6d  xorps   xmm0, xmm0
0x1800a3f70  movups  [rbp+47h+var_70], xmm0
0x1800a3f74  lea     rax, [rbp+47h+var_70]
0x1800a3f78  mov     [rsp+100h+var_D8], rax
0x1800a3f7d  mov     rax, [rbp+47h+var_78]
0x1800a3f81  mov     qword ptr [rsp+100h+yBottom], rax
0x1800a3f86  mov     r9, qword ptr [rbp+47h+rc.left]
0x1800a3f8a  mov     r8, r12
0x1800a3f8d  mov     rdx, r15
0x1800a3f90  mov     rcx, r13
0x1800a3f93  call    cs:__imp_?Paint@Element@DirectUI@@UEAAXPEAUHDC__@@PEBUtagRECT@@1PEAU4@2@Z; DirectUI::Element::Paint(HDC__ *,tagRECT const *,tagRECT const *,tagRECT *,tagRECT *)
0x1800a3f99  lea     r9, [rbp+47h+var_70]
0x1800a3f9d  mov     r8, r12
0x1800a3fa0  mov     rdx, r15
0x1800a3fa3  mov     rcx, r13
0x1800a3fa6  call    cs:__imp_?PaintFocusRect@Element@DirectUI@@QEAAXPEAUHDC__@@PEBUtagRECT@@1@Z; DirectUI::Element::PaintFocusRect(HDC__ *,tagRECT const *,tagRECT const *)
0x1800a3fac  mov     r14d, esi
0x1800a3faf  mov     dword ptr [rbp+47h+var_B8], esi
0x1800a3fb2  mov     rdi, cs:?Class@UIItem@@2PEAUIClassInfo@DirectUI@@EA; DirectUI::IClassInfo * UIItem::Class
0x1800a3fb9  mov     rbx, r13
0x1800a3fbc  nop     dword ptr [rax+00h]
0x1800a3fc0  mov     rax, [rbx]
0x1800a3fc3  mov     rcx, rbx
0x1800a3fc6  mov     rax, [rax+118h]
0x1800a3fcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fd2  mov     r8, rax
0x1800a3fd5  mov     rcx, [rax]
0x1800a3fd8  mov     rax, [rcx+50h]
0x1800a3fdc  mov     rdx, rdi
0x1800a3fdf  mov     rcx, r8
0x1800a3fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3fe7  mov     rcx, rbx
0x1800a3fea  test    al, al
0x1800a3fec  jnz     short loc_1800A4003
0x1800a3fee  call    cs:__imp_?GetParent@Element@DirectUI@@QEAAPEAV12@XZ; DirectUI::Element::GetParent(void)
0x1800a3ff4  mov     rbx, rax
0x1800a3ff7  test    rax, rax
0x1800a3ffa  jnz     short loc_1800A3FC0
0x1800a3ffc  mov     edi, 1
0x1800a4001  jmp     short loc_1800A4018
0x1800a4003  call    cs:__imp_?GetSelected@Element@DirectUI@@QEAA_NXZ; DirectUI::Element::GetSelected(void)
0x1800a4009  mov     edi, 1
0x1800a400e  test    al, al
0x1800a4010  cmovnz  r14d, edi
0x1800a4014  mov     dword ptr [rbp+47h+var_B8], r14d
0x1800a4018  mov     [rbp+47h+var_A8], esi
0x1800a401b  mov     rcx, [rbp+47h+ppunk]
0x1800a401f  mov     rax, [rcx]
0x1800a4022  lea     rdx, [rbp+47h+var_A8]
0x1800a4026  mov     rax, [rax+80h]
0x1800a402d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4032  test    eax, eax
0x1800a4034  js      loc_1800A40BB
0x1800a403a  test    byte ptr [rbp+47h+var_A8], 8
0x1800a403e  jz      short loc_1800A40BB
0x1800a4040  xorps   xmm0, xmm0
0x1800a4043  movups  xmmword ptr [rbp+47h+rc.left], xmm0
0x1800a4047  mov     rcx, r13
0x1800a404a  call    cs:__imp_?GetFontSize@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetFontSize(void)
0x1800a4050  mov     ecx, eax
0x1800a4052  neg     ecx
0x1800a4054  cmovs   ecx, eax
0x1800a4057  mov     eax, 2AAAAAABh
0x1800a405c  imul    ecx
0x1800a405e  mov     eax, edx
0x1800a4060  shr     eax, 1Fh
0x1800a4063  add     edx, eax; xLeft
0x1800a4065  mov     [rsp+100h+yBottom], esi; yBottom
0x1800a4069  mov     r9d, edx; xRight
0x1800a406c  xor     r8d, r8d; yTop
0x1800a406f  lea     rcx, [rbp+47h+rc]; lprc
0x1800a4073  call    cs:__imp_SetRect
0x1800a4079  mov     ecx, dword ptr [rbp+47h+var_70]
0x1800a407c  add     ecx, [rbp+47h+rc.left]
0x1800a407f  mov     dword ptr [rbp+47h+var_70], ecx
  ... truncated ...
```
