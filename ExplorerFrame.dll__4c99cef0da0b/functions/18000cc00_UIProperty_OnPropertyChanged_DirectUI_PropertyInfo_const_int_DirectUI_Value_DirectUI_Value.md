# UIProperty::OnPropertyChanged(DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)

- ea: `0x18000cc00`
- end: `0x18000d356`
- name: `?OnPropertyChanged@UIProperty@@UEAAXPEBUPropertyInfo@DirectUI@@HPEAVValue@3@1@Z`
- size: `1878`
- prototype: `void __usercall(UIProperty *__hidden this@<rcx>, const struct DirectUI::PropertyInfo *@<rdx>, int@<r8d>, struct DirectUI::Value *@<r9>, struct DirectUI::Value *)`
- caller_count: `1`
- callee_count: `14`
- tags: `installer_update, broker_com_uri`

## callers

- `0x18000cb60`

## callees

- `0x18000a2cc`
- `0x18000cc00`
- `0x18000d360`
- `0x18000d3b0`
- `0x18000d440`
- `0x18000d594`
- `0x180016790`
- `0x1800218ac`
- `0x180026424`
- `0x1800acb44`
- `0x1800af5bc`
- `0x18012ea9c`
- `0x18013f7d0`
- `0x180210010`

## import_xrefs

- `GDI32!DeleteObject` at `0x18000cf5c`
- `GDI32!DeleteObject` at `0x18000cf5c`
- `GDI32!CreateFontIndirectW` at `0x18000cf1d`
- `GDI32!CreateFontIndirectW` at `0x18000cf1d`
- `GDI32!GetObjectW` at `0x18000cf02`
- `GDI32!GetObjectW` at `0x18000cf02`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000cd7d`
- `PROPSYS!PSGetPropertyKeyFromName` at `0x18000cd7d`
- `UxTheme!IsAppThemed` at `0x18000d091`
- `UxTheme!IsAppThemed` at `0x18000d091`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x18000d0c1`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x18000d326`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x18000d34b`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x18000d0c1`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x18000d326`
- `DUI70!?SetContentAlign@Element@DirectUI@@QEAAJH@Z` at `0x18000d34b`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18000d0b3`
- `DUI70!?GetContentAlign@Element@DirectUI@@QEAAHXZ` at `0x18000d0b3`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc47`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cdbd`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000ce1c`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc47`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cdbd`
- `DUI70!?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000ce1c`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000ce31`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z` at `0x18000ce31`
- `DUI70!?KeyFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cccf`
- `DUI70!?KeyFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cccf`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ce83`
- `DUI70!?Release@Value@DirectUI@@QEAAXXZ` at `0x18000ce83`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000ce77`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000d0a2`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000ce77`
- `DUI70!?GetBool@Value@DirectUI@@QEAA_NXZ` at `0x18000d0a2`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000d14f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000d27f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000d2fa`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000d14f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000d27f`
- `DUI70!?GetInt@Value@DirectUI@@QEAAHXZ` at `0x18000d2fa`
- `DUI70!?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc56`
- `DUI70!?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cdcc`
- `DUI70!?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc56`
- `DUI70!?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cdcc`
- `DUI70!?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z` at `0x18000ccff`
- `DUI70!?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z` at `0x18000ccff`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000cd6f`
- `DUI70!?GetString@Value@DirectUI@@QEAAPEBGXZ` at `0x18000cd6f`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x18000ce3f`
- `DUI70!?GetType@Value@DirectUI@@QEBAHXZ` at `0x18000ce3f`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000ce6b`
- `DUI70!?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z` at `0x18000ce6b`
- `DUI70!?GetActive@Element@DirectUI@@QEAAHXZ` at `0x18000d083`
- `DUI70!?GetActive@Element@DirectUI@@QEAAHXZ` at `0x18000d083`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000ccc0`
- `DUI70!?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000ccc0`
- `DUI70!?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cca2`
- `DUI70!?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cca2`
- `DUI70!?FontSizeProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc93`
- `DUI70!?FontSizeProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc93`
- `DUI70!?FontStyleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000ccb1`
- `DUI70!?FontStyleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000ccb1`
- `DUI70!?ContentAlignProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc65`
- `DUI70!?ContentAlignProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cde4`
- `DUI70!?ContentAlignProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc65`
- `DUI70!?ContentAlignProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cde4`
- `DUI70!?FontProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc84`
- `DUI70!?FontProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ` at `0x18000cc84`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall UIProperty::OnPropertyChanged(
        UIProperty *this,
        const struct DirectUI::PropertyInfo *a2,
        int a3,
        struct DirectUI::Value *a4,
        struct DirectUI::Value *a5)
{
  __int64 v9; // rax
  const WCHAR *String; // rax
  const struct DirectUI::PropertyInfo *v11; // rax
  DirectUI::Value *v12; // rsi
  bool Bool; // di
  int ObjectW; // edi
  HFONT v15; // rdi
  int ContentAlign; // eax
  struct IDrawPropertyControl *v17; // rsi
  int (__fastcall *v18)(struct IDrawPropertyControl *, GUID *, __int64); // rdi
  __int64 v19; // rax
  __int64 v20; // rsi
  void (__fastcall *v21)(__int64, _QWORD); // rdi
  unsigned int v22; // eax
  __int64 v23; // rcx
  struct IDrawPropertyControl *v24; // rcx
  struct IDrawPropertyControl *v25; // rcx
  unsigned int Int; // eax
  __int64 v27; // rdx
  int v28; // eax
  __int64 v29; // rdx
  int v30; // eax
  int v31; // eax
  __int64 v32; // rdx
  int v33; // eax
  struct IDrawPropertyControl *Value; // [rsp+30h] [rbp-91h] BYREF
  __int64 v35; // [rsp+38h] [rbp-89h] BYREF
  PROPERTYKEY ppropkey; // [rsp+40h] [rbp-81h] BYREF
  LOGFONTW pv; // [rsp+60h] [rbp-61h] BYREF

  if ( a2 == (const struct DirectUI::PropertyInfo *)&off_18028FCB0 && (*((_DWORD *)a2 + 2) & 3) == a3 )
  {
    memset(&ppropkey, 0, sizeof(ppropkey));
    if ( !*((_DWORD *)this + 147) )
    {
      v9 = *(_QWORD *)((char *)this + 572) - *(_QWORD *)&PKEY_Null.fmtid.Data1;
      if ( !v9 )
        v9 = *(_QWORD *)((char *)this + 580) - *(_QWORD *)PKEY_Null.fmtid.Data4;
      if ( !v9 )
      {
        String = DirectUI::Value::GetString(a5);
        if ( PSGetPropertyKeyFromName(String, &ppropkey) >= 0 )
          *(PROPERTYKEY *)((char *)this + 572) = ppropkey;
      }
    }
  }
  else if ( a2 == DirectUI::Element::ContentProp() && (*((_DWORD *)a2 + 2) & 3) == a3
         || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::ExtentProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3
         || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::ContentAlignProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3
         || a2 == (const struct DirectUI::PropertyInfo *)&off_18028FD40 && (*((_DWORD *)a2 + 2) & 3) == a3 )
  {
    if ( a2 == DirectUI::Element::ContentProp() && (*((_DWORD *)a2 + 2) & 3) == a3 )
    {
      *(_QWORD *)((char *)this + 540) = 0;
      *((_DWORD *)this + 130) = 1;
    }
    else if ( a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::ExtentProp()
           && (*((_DWORD *)a2 + 2) & 3) == a3 )
    {
      *((_DWORD *)this + 129) = 1;
      *((_DWORD *)this + 130) = 1;
    }
    else if ( a2 == (const struct DirectUI::PropertyInfo *)&off_18028FD40 && (*((_DWORD *)a2 + 2) & 3) == a3 )
    {
      if ( !(unsigned __int8)ATL::CComPtrBase<IDrawPropertyControl>::operator!((char *)this + 208) )
      {
        LODWORD(v35) = 0;
        if ( (*(int (__fastcall **)(char *, __int64, __int64 *))(*((_QWORD *)this + 25) + 296LL))(
               (char *)this + 200,
               1026,
               &v35) >= 0 )
          (*(void (__fastcall **)(_QWORD, __int64, _QWORD))(**((_QWORD **)this + 26) + 152LL))(
            *((_QWORD *)this + 26),
            1026,
            (unsigned int)v35);
      }
    }
    else if ( a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::ContentAlignProp()
           && (*((_DWORD *)a2 + 2) & 3) == a3
           && !(unsigned __int8)ATL::CComPtrBase<IDrawPropertyControl>::operator!((char *)this + 600)
           && (DirectUI::Value::GetInt(a5) & 0x550) != 0 )
    {
      Value = 0;
      Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&Value);
      UIProperty::_GetSharedDrawControl(this, &Value);
      LODWORD(v35) = 0;
      if ( (*(int (__fastcall **)(struct IDrawPropertyControl *, __int64 *))(*(_QWORD *)Value + 128LL))(Value, &v35) >= 0
        && (v35 & 0x10) == 0 )
      {
        Int = DirectUI::Value::GetInt(a5);
        v28 = DUI_TransformContentAlign(this, v27, Int, 0);
        v30 = DUI_TransformContentAlign(this, v29, v28 & 0xFFFFFAAF, 0);
        DirectUI::Element::SetContentAlign(this, v30);
      }
      v25 = Value;
      if ( Value )
      {
        Value = 0;
        (*(void (__fastcall **)(struct IDrawPropertyControl *))(*(_QWORD *)v25 + 16LL))(v25);
      }
    }
    if ( *((_DWORD *)this + 129) )
    {
      v11 = DirectUI::Element::ContentProp();
      Value = DirectUI::Element::GetValue(this, v11, 1, 0);
      if ( DirectUI::Value::GetType(Value) == -1 )
      {
        CValuePtr::~CValuePtr((CValuePtr *)&Value);
      }
      else
      {
        CValuePtr::~CValuePtr((CValuePtr *)&Value);
        v12 = DirectUI::Element::GetValue(this, UIProperty::EnableHitHighlightingProp, 2, 0);
        Bool = DirectUI::Value::GetBool(v12);
        DirectUI::Value::Release(v12);
        if ( Bool )
          UIProperty::_UpdateHitHighlightingContent(this);
      }
    }
  }
  else if ( a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::FontProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3
         || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::FontSizeProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3
         || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::ForegroundProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3
         || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::FontStyleProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3
         || a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::BackgroundProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3 )
  {
    if ( !(unsigned __int8)ATL::CComPtrBase<IDrawPropertyControl>::operator!((char *)this + 208) )
    {
      memset(&pv, 0, sizeof(pv));
      ObjectW = 0;
      CAutoFont::CAutoFont((CAutoFont *)&ppropkey, this, 0);
      if ( *(_QWORD *)&ppropkey.fmtid.Data1 )
        ObjectW = GetObjectW(*(HANDLE *)&ppropkey.fmtid.Data1, 92, &pv);
      CAutoFont::Release((CAutoFont *)&ppropkey);
      if ( ObjectW )
      {
        v15 = CreateFontIndirectW(&pv);
        if ( v15 )
        {
          (*(void (__fastcall **)(_QWORD, __int64, HFONT, _QWORD, _QWORD))(**((_QWORD **)this + 26) + 24LL))(
            *((_QWORD *)this + 26),
            48,
            v15,
            0,
            0);
          DeleteObject(*((HGDIOBJ *)this + 59));
          *((_QWORD *)this + 59) = v15;
        }
      }
      *(_OWORD *)((char *)this + 388) = 0;
      *(_OWORD *)((char *)this + 404) = 0;
      *(_OWORD *)((char *)this + 420) = 0;
      *(_OWORD *)((char *)this + 436) = 0;
      *(_OWORD *)((char *)this + 452) = 0;
      *((_DWORD *)this + 117) = 0;
      *((_DWORD *)this + 95) = 92;
      *((_DWORD *)this + 96) = 0x40000000;
      *((_DWORD *)this + 100) = DUI_GetForegroundColor(this);
      (*(void (__fastcall **)(_QWORD, __int64, __int64))(**((_QWORD **)this + 26) + 152LL))(
        *((_QWORD *)this + 26),
        0x20000,
        0x20000);
    }
  }
  else if ( a2 == (const struct DirectUI::PropertyInfo *)DirectUI::Element::KeyFocusedProp()
         && (*((_DWORD *)a2 + 2) & 3) == a3
         && (DirectUI::Element::GetActive(this) & 2) != 0
         && !IsAppThemed() )
  {
    if ( DirectUI::Value::GetBool(a5) )
    {
      ContentAlign = DirectUI::Element::GetContentAlign(this);
      DirectUI::Element::SetContentAlign(this, ContentAlign | 0x20);
    }
    else
    {
      v31 = DUI_GetContentAlign(this, 0);
      v33 = DUI_TransformContentAlign(this, v32, v31 & 0xFFFFFFDF, 0);
      DirectUI::Element::SetContentAlign(this, v33);
    }
  }
  else if ( a2 == (const struct DirectUI::PropertyInfo *)&off_18028FE90
         && (*((_DWORD *)a2 + 2) & 3) == a3
         && !(unsigned __int8)ATL::CComPtrBase<IDrawPropertyControl>::operator!((char *)this + 600) )
  {
    Value = 0;
    Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&Value);
    UIProperty::_GetSharedDrawControl(this, &Value);
    v35 = 0;
    v17 = Value;
    v18 = **(int (__fastcall ***)(struct IDrawPropertyControl *, GUID *, __int64))Value;
    v19 = IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(&v35);
    if ( v18(v17, &GUID_cf599b9b_8917_4417_9874_1af7148fa8d1, v19) >= 0 )
    {
      v20 = v35;
      v21 = *(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v35 + 32LL);
      v22 = DirectUI::Value::GetInt(a5);
      v21(v20, v22);
    }
    v23 = v35;
    if ( v35 )
    {
      v35 = 0;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    }
    v24 = Value;
    if ( Value )
    {
      Value = 0;
      (*(void (__fastcall **)(struct IDrawPropertyControl *))(*(_QWORD *)v24 + 16LL))(v24);
    }
  }
  DirectUI::Element::OnPropertyChanged(this, a2, a3, a4, a5);
}

```

## disassembly

```asm
0x18000cc00  push    rbp
0x18000cc02  push    rbx
0x18000cc03  push    rsi
0x18000cc04  push    rdi
0x18000cc05  push    r12
0x18000cc07  push    r13
0x18000cc09  push    r14
0x18000cc0b  push    r15
0x18000cc0d  lea     rbp, [rsp-17h]
0x18000cc12  sub     rsp, 0D8h
0x18000cc19  mov     rax, cs:__security_cookie
0x18000cc20  xor     rax, rsp
0x18000cc23  mov     [rbp+4Fh+var_50], rax
0x18000cc27  mov     r13, r9
0x18000cc2a  mov     r15d, r8d
0x18000cc2d  mov     rbx, rdx
0x18000cc30  mov     r14, rcx
0x18000cc33  mov     r12, [rbp+4Fh+arg_20]
0x18000cc37  lea     rax, off_18028FCB0; "PropertyCanonicalName"
0x18000cc3e  cmp     rdx, rax
0x18000cc41  jz      loc_18000CD25
0x18000cc47  call    cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x18000cc4d  cmp     rbx, rax
0x18000cc50  jz      loc_18000CDA7
0x18000cc56  call    cs:__imp_?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ExtentProp(void)
0x18000cc5c  cmp     rbx, rax
0x18000cc5f  jz      loc_18000CFE5
0x18000cc65  call    cs:__imp_?ContentAlignProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentAlignProp(void)
0x18000cc6b  cmp     rbx, rax
0x18000cc6e  jz      loc_18000CFF9
0x18000cc74  lea     rsi, off_18028FD40; "MaxNumTextLines"
0x18000cc7b  cmp     rbx, rsi
0x18000cc7e  jz      loc_18000D00D
0x18000cc84  call    cs:__imp_?FontProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::FontProp(void)
0x18000cc8a  cmp     rbx, rax
0x18000cc8d  jz      loc_18000CE9F
0x18000cc93  call    cs:__imp_?FontSizeProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::FontSizeProp(void)
0x18000cc99  cmp     rbx, rax
0x18000cc9c  jz      loc_18000D021
0x18000cca2  call    cs:__imp_?ForegroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ForegroundProp(void)
0x18000cca8  cmp     rbx, rax
0x18000ccab  jz      loc_18000D035
0x18000ccb1  call    cs:__imp_?FontStyleProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::FontStyleProp(void)
0x18000ccb7  cmp     rbx, rax
0x18000ccba  jz      loc_18000D049
0x18000ccc0  call    cs:__imp_?BackgroundProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::BackgroundProp(void)
0x18000ccc6  cmp     rbx, rax
0x18000ccc9  jz      loc_18000D05D
0x18000cccf  call    cs:__imp_?KeyFocusedProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::KeyFocusedProp(void)
0x18000ccd5  cmp     rbx, rax
0x18000ccd8  jz      loc_18000D071
0x18000ccde  lea     rax, off_18028FE90; "IconDisplayMinimum"
0x18000cce5  cmp     rbx, rax
0x18000cce8  jz      loc_18000D0CC
0x18000ccee  mov     [rsp+110h+var_F0], r12
0x18000ccf3  mov     r9, r13
0x18000ccf6  mov     r8d, r15d
0x18000ccf9  mov     rdx, rbx
0x18000ccfc  mov     rcx, r14
0x18000ccff  call    cs:__imp_?OnPropertyChanged@Element@DirectUI@@UEAAXPEBUPropertyInfo@2@HPEAVValue@2@1@Z; DirectUI::Element::OnPropertyChanged(DirectUI::PropertyInfo const *,int,DirectUI::Value *,DirectUI::Value *)
0x18000cd05  mov     rcx, [rbp+4Fh+var_50]
0x18000cd09  xor     rcx, rsp; StackCookie
0x18000cd0c  call    __security_check_cookie
0x18000cd11  add     rsp, 0D8h
0x18000cd18  pop     r15
0x18000cd1a  pop     r14
0x18000cd1c  pop     r13
0x18000cd1e  pop     r12
0x18000cd20  pop     rdi
0x18000cd21  pop     rsi
0x18000cd22  pop     rbx
0x18000cd23  pop     rbp
0x18000cd24  retn
0x18000cd25  mov     eax, [rdx+8]
0x18000cd28  and     eax, 3
0x18000cd2b  cmp     eax, r15d
0x18000cd2e  jnz     loc_18000CC47
0x18000cd34  xorps   xmm0, xmm0
0x18000cd37  xor     eax, eax
0x18000cd39  movups  xmmword ptr [rsp+110h+ppropkey.fmtid.Data1], xmm0
0x18000cd3e  mov     [rbp+4Fh+ppropkey.pid], eax
0x18000cd41  cmp     [rcx+24Ch], eax
0x18000cd47  jnz     short loc_18000CCEE
0x18000cd49  mov     rax, [rcx+23Ch]
0x18000cd50  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data1
0x18000cd57  jnz     short loc_18000CD67
0x18000cd59  mov     rax, [rcx+244h]
0x18000cd60  sub     rax, qword ptr cs:PKEY_Null.fmtid.Data4
0x18000cd67  test    rax, rax
0x18000cd6a  jnz     short loc_18000CCEE
0x18000cd6c  mov     rcx, r12
0x18000cd6f  call    cs:__imp_?GetString@Value@DirectUI@@QEAAPEBGXZ; DirectUI::Value::GetString(void)
0x18000cd75  mov     rcx, rax; pszName
0x18000cd78  lea     rdx, [rsp+110h+ppropkey]; ppropkey
0x18000cd7d  call    cs:__imp_PSGetPropertyKeyFromName
0x18000cd83  test    eax, eax
0x18000cd85  js      loc_18000CCEE
0x18000cd8b  movups  xmm0, xmmword ptr [rsp+110h+ppropkey.fmtid.Data1]
0x18000cd90  movups  xmmword ptr [r14+23Ch], xmm0
0x18000cd98  mov     eax, [rbp+4Fh+ppropkey.pid]
0x18000cd9b  mov     [r14+24Ch], eax
0x18000cda2  jmp     loc_18000CCEE
0x18000cda7  mov     eax, [rbx+8]
0x18000cdaa  and     eax, 3
0x18000cdad  cmp     eax, r15d
0x18000cdb0  jnz     loc_18000CC56
0x18000cdb6  lea     rsi, off_18028FD40; "MaxNumTextLines"
0x18000cdbd  call    cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x18000cdc3  cmp     rbx, rax
0x18000cdc6  jz      loc_18000D1B2
0x18000cdcc  call    cs:__imp_?ExtentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ExtentProp(void)
0x18000cdd2  cmp     rbx, rax
0x18000cdd5  jz      loc_18000D1DA
0x18000cddb  cmp     rbx, rsi
0x18000cdde  jz      loc_18000D204
0x18000cde4  call    cs:__imp_?ContentAlignProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentAlignProp(void)
0x18000cdea  cmp     rbx, rax
0x18000cded  jnz     short loc_18000CE0E
0x18000cdef  mov     eax, [rbx+8]
0x18000cdf2  and     eax, 3
0x18000cdf5  cmp     eax, r15d
0x18000cdf8  jnz     short loc_18000CE0E
0x18000cdfa  lea     rcx, [r14+258h]
0x18000ce01  call    ??7?$CComPtrBase@UIDrawPropertyControl@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IDrawPropertyControl>::operator!(void)
0x18000ce06  test    al, al
0x18000ce08  jz      loc_18000D27C
0x18000ce0e  cmp     dword ptr [r14+204h], 0
0x18000ce16  jz      loc_18000CCEE
0x18000ce1c  call    cs:__imp_?ContentProp@Element@DirectUI@@SAPEBUPropertyInfo@2@XZ; DirectUI::Element::ContentProp(void)
0x18000ce22  xor     r9d, r9d
0x18000ce25  mov     r8d, 1
0x18000ce2b  mov     rdx, rax
0x18000ce2e  mov     rcx, r14
0x18000ce31  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@PEBUPropertyInfo@2@HPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const *,int,DirectUI::UpdateCache *)
0x18000ce37  mov     [rsp+110h+var_E0], rax
0x18000ce3c  mov     rcx, rax
0x18000ce3f  call    cs:__imp_?GetType@Value@DirectUI@@QEBAHXZ; DirectUI::Value::GetType(void)
0x18000ce45  lea     rcx, [rsp+110h+var_E0]; this
0x18000ce4a  cmp     eax, 0FFFFFFFFh
0x18000ce4d  jz      loc_18000D1A8
0x18000ce53  call    ??1CValuePtr@@QEAA@XZ; CValuePtr::~CValuePtr(void)
0x18000ce58  xor     r9d, r9d
0x18000ce5b  mov     r8d, 2
0x18000ce61  lea     rdx, ?EnableHitHighlightingProp@UIProperty@@SAPEBUPropertyInfo@DirectUI@@XZ; UIProperty::EnableHitHighlightingProp(void)
0x18000ce68  mov     rcx, r14
0x18000ce6b  call    cs:__imp_?GetValue@Element@DirectUI@@QEAAPEAVValue@2@P6APEBUPropertyInfo@2@XZHPEAUUpdateCache@2@@Z; DirectUI::Element::GetValue(DirectUI::PropertyInfo const * (*)(void),int,DirectUI::UpdateCache *)
0x18000ce71  mov     rsi, rax
0x18000ce74  mov     rcx, rax
0x18000ce77  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x18000ce7d  movzx   edi, al
0x18000ce80  mov     rcx, rsi
0x18000ce83  call    cs:__imp_?Release@Value@DirectUI@@QEAAXXZ; DirectUI::Value::Release(void)
0x18000ce89  test    dil, dil
0x18000ce8c  jz      loc_18000CCEE
0x18000ce92  mov     rcx, r14; this
0x18000ce95  call    ?_UpdateHitHighlightingContent@UIProperty@@IEAAXXZ; UIProperty::_UpdateHitHighlightingContent(void)
0x18000ce9a  jmp     loc_18000CCEE
0x18000ce9f  mov     eax, [rbx+8]
0x18000cea2  and     eax, 3
0x18000cea5  cmp     eax, r15d
0x18000cea8  jnz     loc_18000CC93
0x18000ceae  lea     rcx, [r14+0D0h]
0x18000ceb5  call    ??7?$CComPtrBase@UIDrawPropertyControl@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IDrawPropertyControl>::operator!(void)
0x18000ceba  test    al, al
0x18000cebc  jnz     loc_18000CCEE
0x18000cec2  xorps   xmm0, xmm0
0x18000cec5  movups  [rbp+4Fh+pv], xmm0
0x18000cec9  movups  [rbp+4Fh+var_A0], xmm0
0x18000cecd  movups  [rbp+4Fh+var_90], xmm0
0x18000ced1  movups  [rbp+4Fh+var_80], xmm0
0x18000ced5  movups  [rbp+4Fh+var_70], xmm0
0x18000ced9  movups  [rbp+4Fh+var_70+0Ch], xmm0
0x18000cedd  xor     edi, edi
0x18000cedf  xor     r8d, r8d; HDC
0x18000cee2  mov     rdx, r14; struct DirectUI::Element *
0x18000cee5  lea     rcx, [rsp+110h+ppropkey]; this
0x18000ceea  call    ??0CAutoFont@@QEAA@PEAVElement@DirectUI@@PEAUHDC__@@@Z; CAutoFont::CAutoFont(DirectUI::Element *,HDC__ *)
0x18000ceef  mov     rcx, qword ptr [rsp+110h+ppropkey.fmtid.Data1]; h
0x18000cef4  test    rcx, rcx
0x18000cef7  jz      short loc_18000CF0A
0x18000cef9  lea     r8, [rbp+4Fh+pv]; pv
0x18000cefd  mov     edx, 5Ch ; '\'; c
0x18000cf02  call    cs:__imp_GetObjectW
0x18000cf08  mov     edi, eax
0x18000cf0a  lea     rcx, [rsp+110h+ppropkey]; this
0x18000cf0f  call    ?Release@CAutoFont@@QEAAXXZ; CAutoFont::Release(void)
0x18000cf14  nop
0x18000cf15  test    edi, edi
0x18000cf17  jz      short loc_18000CF69
0x18000cf19  lea     rcx, [rbp+4Fh+pv]; lplf
0x18000cf1d  call    cs:__imp_CreateFontIndirectW
0x18000cf23  mov     rdi, rax
0x18000cf26  test    rax, rax
0x18000cf29  jz      short loc_18000CF69
0x18000cf2b  mov     r10, [r14+0D0h]
0x18000cf32  mov     rcx, [r10]
0x18000cf35  mov     rax, [rcx+18h]
0x18000cf39  mov     [rsp+110h+var_F0], 0
0x18000cf42  xor     r9d, r9d
0x18000cf45  mov     r8, rdi
0x18000cf48  mov     edx, 30h ; '0'
0x18000cf4d  mov     rcx, r10
0x18000cf50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf55  mov     rcx, [r14+1D8h]; ho
0x18000cf5c  call    cs:__imp_DeleteObject
0x18000cf62  mov     [r14+1D8h], rdi
0x18000cf69  xorps   xmm0, xmm0
0x18000cf6c  xor     eax, eax
0x18000cf6e  movups  xmmword ptr [r14+184h], xmm0
0x18000cf76  movups  xmmword ptr [r14+194h], xmm0
0x18000cf7e  movups  xmmword ptr [r14+1A4h], xmm0
0x18000cf86  movups  xmmword ptr [r14+1B4h], xmm0
0x18000cf8e  movups  xmmword ptr [r14+1C4h], xmm0
0x18000cf96  mov     [r14+1D4h], eax
0x18000cf9d  mov     dword ptr [r14+17Ch], 5Ch ; '\'
0x18000cfa8  mov     dword ptr [r14+180h], 40000000h
0x18000cfb3  mov     rcx, r14; struct DirectUI::Element *
0x18000cfb6  call    ?DUI_GetForegroundColor@@YAKPEAVElement@DirectUI@@@Z; DUI_GetForegroundColor(DirectUI::Element *)
0x18000cfbb  mov     [r14+190h], eax
0x18000cfc2  mov     rcx, [r14+0D0h]
0x18000cfc9  mov     rax, [rcx]
0x18000cfcc  mov     edx, 20000h
0x18000cfd1  mov     r8d, edx
0x18000cfd4  mov     rax, [rax+98h]
0x18000cfdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cfe0  jmp     loc_18000CCEE
0x18000cfe5  mov     eax, [rbx+8]
0x18000cfe8  and     eax, 3
0x18000cfeb  cmp     eax, r15d
0x18000cfee  jnz     loc_18000CC65
0x18000cff4  jmp     loc_18000CDB6
0x18000cff9  mov     eax, [rbx+8]
0x18000cffc  and     eax, 3
0x18000cfff  cmp     eax, r15d
0x18000d002  jnz     loc_18000CC74
0x18000d008  jmp     loc_18000CDB6
0x18000d00d  mov     eax, [rbx+8]
0x18000d010  and     eax, 3
0x18000d013  cmp     eax, r15d
0x18000d016  jnz     loc_18000CC84
0x18000d01c  jmp     loc_18000CDBD
0x18000d021  mov     eax, [rbx+8]
0x18000d024  and     eax, 3
0x18000d027  cmp     eax, r15d
0x18000d02a  jnz     loc_18000CCA2
0x18000d030  jmp     loc_18000CEAE
0x18000d035  mov     eax, [rbx+8]
0x18000d038  and     eax, 3
0x18000d03b  cmp     eax, r15d
0x18000d03e  jnz     loc_18000CCB1
0x18000d044  jmp     loc_18000CEAE
0x18000d049  mov     eax, [rbx+8]
0x18000d04c  and     eax, 3
0x18000d04f  cmp     eax, r15d
0x18000d052  jnz     loc_18000CCC0
0x18000d058  jmp     loc_18000CEAE
0x18000d05d  mov     eax, [rbx+8]
0x18000d060  and     eax, 3
0x18000d063  cmp     eax, r15d
0x18000d066  jnz     loc_18000CCCF
0x18000d06c  jmp     loc_18000CEAE
0x18000d071  mov     eax, [rbx+8]
0x18000d074  and     eax, 3
0x18000d077  cmp     eax, r15d
0x18000d07a  jnz     loc_18000CCDE
0x18000d080  mov     rcx, r14
0x18000d083  call    cs:__imp_?GetActive@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetActive(void)
0x18000d089  test    al, 2
0x18000d08b  jz      loc_18000CCDE
0x18000d091  call    cs:__imp_IsAppThemed
0x18000d097  test    eax, eax
0x18000d099  jnz     loc_18000CCDE
0x18000d09f  mov     rcx, r12
0x18000d0a2  call    cs:__imp_?GetBool@Value@DirectUI@@QEAA_NXZ; DirectUI::Value::GetBool(void)
0x18000d0a8  mov     rcx, r14
0x18000d0ab  test    al, al
0x18000d0ad  jz      loc_18000D32E
0x18000d0b3  call    cs:__imp_?GetContentAlign@Element@DirectUI@@QEAAHXZ; DirectUI::Element::GetContentAlign(void)
0x18000d0b9  or      eax, 20h
0x18000d0bc  mov     edx, eax
0x18000d0be  mov     rcx, r14
0x18000d0c1  call    cs:__imp_?SetContentAlign@Element@DirectUI@@QEAAJH@Z; DirectUI::Element::SetContentAlign(int)
0x18000d0c7  jmp     loc_18000CCEE
0x18000d0cc  mov     eax, [rbx+8]
0x18000d0cf  and     eax, 3
0x18000d0d2  cmp     eax, r15d
0x18000d0d5  jnz     loc_18000CCEE
0x18000d0db  lea     rcx, [r14+258h]
0x18000d0e2  call    ??7?$CComPtrBase@UIDrawPropertyControl@@@ATL@@QEBA_NXZ; ATL::CComPtrBase<IDrawPropertyControl>::operator!(void)
0x18000d0e7  test    al, al
0x18000d0e9  jnz     loc_18000CCEE
0x18000d0ef  xor     edi, edi
0x18000d0f1  mov     [rsp+110h+var_E0], rdi
0x18000d0f6  lea     rcx, [rsp+110h+var_E0]
0x18000d0fb  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x18000d100  lea     rdx, [rsp+110h+var_E0]; struct IDrawPropertyControl **
0x18000d105  mov     rcx, r14; this
0x18000d108  call    ?_GetSharedDrawControl@UIProperty@@IEAAXPEAPEAUIDrawPropertyControl@@@Z; UIProperty::_GetSharedDrawControl(IDrawPropertyControl * *)
0x18000d10d  mov     [rsp+110h+var_D8], rdi
0x18000d112  mov     rsi, [rsp+110h+var_E0]
  ... truncated ...
```
