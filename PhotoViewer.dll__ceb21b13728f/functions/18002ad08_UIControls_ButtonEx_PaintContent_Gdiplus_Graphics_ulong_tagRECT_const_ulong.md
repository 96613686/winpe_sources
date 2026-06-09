# UIControls::ButtonEx::PaintContent(Gdiplus::Graphics &,ulong,tagRECT const &,ulong)

- ea: `0x18002ad08`
- end: `0x18002b2f2`
- name: `?PaintContent@ButtonEx@UIControls@@IEAAXAEAVGraphics@Gdiplus@@KAEBUtagRECT@@K@Z`
- size: `1514`
- prototype: `void __usercall(UIControls::ButtonEx *__hidden this@<rcx>, struct Gdiplus::Graphics *@<rdx>, unsigned int@<r8d>, const struct tagRECT *@<r9>, unsigned int)`
- caller_count: `1`
- callee_count: `18`
- tags: `loader_planting, installer_update`

## callers

- `0x180075580`

## callees

- `0x180003458`
- `0x180004908`
- `0x1800053e8`
- `0x180005f04`
- `0x180006144`
- `0x180024524`
- `0x180026724`
- `0x180027a84`
- `0x180028c04`
- `0x180029650`
- `0x180029b08`
- `0x18002ad08`
- `0x18002b2f8`
- `0x18002b548`
- `0x180035054`
- `0x1800367a4`
- `0x18005d730`
- `0x180074c2c`

## import_xrefs

- `USER32!GetWindowLongW` at `0x18002b175`
- `USER32!GetWindowLongW` at `0x18002b175`
- `gdiplus!GdipDeleteBrush` at `0x18002b2b7`
- `gdiplus!GdipDeleteBrush` at `0x18002b2b7`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ad5c`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002ad5c`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall UIControls::ButtonEx::PaintContent(
        UIControls::ButtonEx *this,
        struct Gdiplus::Graphics *a2,
        int a3,
        const struct tagRECT *a4,
        unsigned int a5)
{
  const struct tagRECT *v5; // rsi
  char v6; // r15
  UIControls::ButtonEx *v7; // r14
  __int64 v8; // rdx
  __int64 v9; // rcx
  __int64 BaseStringManager; // rdx
  __int64 v11; // rdx
  unsigned int v12; // r12d
  unsigned int v13; // r13d
  int v14; // edi
  wchar_t *v15; // rbx
  int v16; // eax
  __int64 v17; // rdx
  struct Gdiplus::Font *Font; // rax
  int v19; // esi
  int v20; // r10d
  int v21; // r11d
  int v22; // esi
  int v23; // edx
  int v24; // r9d
  int v25; // r12d
  int v26; // edi
  int v27; // r8d
  int v28; // ecx
  int v29; // r13d
  int v30; // r9d
  int v31; // r10d
  int v32; // r10d
  int v33; // r10d
  HWND *v34; // r15
  unsigned int ImageOffset; // eax
  UIBase *v36; // rdi
  const unsigned __int16 *v37; // rax
  bool v38[16]; // [rsp+60h] [rbp-88h] BYREF
  unsigned __int64 v39; // [rsp+70h] [rbp-78h] BYREF
  __int64 v40; // [rsp+78h] [rbp-70h]
  wchar_t *String; // [rsp+88h] [rbp-60h] BYREF
  __int64 v42; // [rsp+90h] [rbp-58h]
  HWND *v43; // [rsp+98h] [rbp-50h]
  __int64 v44; // [rsp+A0h] [rbp-48h] BYREF
  unsigned int v45; // [rsp+A8h] [rbp-40h]
  UIControls::ButtonEx *v46; // [rsp+F0h] [rbp+8h] BYREF
  HWND v47; // [rsp+F8h] [rbp+10h]
  struct tagSIZE *v48; // [rsp+100h] [rbp+18h]
  const struct tagRECT *v49; // [rsp+108h] [rbp+20h] BYREF

  v49 = a4;
  LODWORD(v48) = a3;
  v47 = (HWND)a2;
  v46 = this;
  v5 = a4;
  v6 = a3;
  v7 = this;
  GdipUtil::SetPageUnitAndRestore::SetPageUnitAndRestore(&v44);
  UIControls::ButtonEx::UpdateImage(v7);
  v42 = *((_QWORD *)v7 + 24);
  *(_QWORD *)v38 = v42;
  BaseStringManager = Base::String::GetBaseStringManager(v9, v8);
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&String, BaseStringManager);
  try
  {
    v43 = (HWND *)((char *)v7 + 8);
    ATL::CWindow::GetWindowTextW((char *)v7 + 8, &String);
    v11 = v42;
  }
  catch ( ... )
  {
    v7 = v46;
    v11 = *(_QWORD *)v38;
    v42 = *(_QWORD *)v38;
    v5 = v49;
    v6 = (char)v48;
  }
  v12 = 1;
  v13 = 1;
  v14 = 0;
  v39 = 0;
  v15 = String;
  if ( *((_DWORD *)String - 4) )
  {
    if ( (v6 & 3) != 1 )
    {
      if ( (v6 & 3) == 2 )
      {
LABEL_20:
        v12 = 2;
        goto LABEL_12;
      }
      if ( (v6 & 3) == 3 || !v11 )
      {
LABEL_12:
        v16 = (unsigned __int8)v48 & 0xC;
        if ( v16 != 4 )
        {
          if ( v16 == 8 )
          {
LABEL_19:
            v13 = 2;
            goto LABEL_22;
          }
          if ( v16 == 12 || !v11 || *((_DWORD *)v7 + 52) == 1 )
          {
LABEL_22:
            Gdiplus::StringFormat::SetAlignment((char *)v7 + 496, v12);
            Gdiplus::StringFormat::SetLineAlignment((char *)v7 + 496, v13);
            if ( ((unsigned __int16)v48 & 0x800) != 0 )
              v17 = 1;
            else
              v17 = ~((unsigned int)v48 >> 12) & 2;
            Gdiplus::StringFormat::SetHotkeyPrefix((char *)v7 + 496, v17);
            *(_DWORD *)v38 = v5->right - v5->left;
            *(_DWORD *)&v38[4] = v5->bottom - v5->top;
            UIControls::ButtonEx::GetMaximumTextSize(
              v7,
              (const struct Gdiplus::Graphics *)&v46,
              (unsigned int)v47,
              (const struct tagSIZE *)(unsigned int)v48,
              (bool)v38);
            if ( (int)v46 <= 0 || SHIDWORD(v46) <= 0 )
            {
              ATL::CSimpleStringT<unsigned short,0>::Empty(&String);
              v15 = String;
            }
            else
            {
              Font = UIControls::ButtonEx::GetFont(v7);
              GdipUtil::MeasureStringHelper(v47, Font, v15);
              v14 = v39;
            }
            goto LABEL_29;
          }
          if ( *((_DWORD *)v7 + 52) != 2 )
          {
            if ( *((_DWORD *)v7 + 52) == 4 )
              goto LABEL_19;
            goto LABEL_22;
          }
        }
        v13 = 0;
        goto LABEL_22;
      }
      if ( *((_DWORD *)v7 + 52) != 1 )
      {
        if ( *((_DWORD *)v7 + 52) == 2 )
          goto LABEL_12;
        if ( *((_DWORD *)v7 + 52) != 3 )
        {
          if ( *((_DWORD *)v7 + 52) == 4 )
            goto LABEL_12;
          goto LABEL_11;
        }
        goto LABEL_20;
      }
    }
LABEL_11:
    v12 = 0;
    goto LABEL_12;
  }
LABEL_29:
  *(struct tagRECT *)v38 = *v5;
  if ( !v42 )
  {
    v36 = (UIBase *)v47;
    v34 = v43;
    goto LABEL_68;
  }
  if ( *((_DWORD *)v15 - 4) )
    v19 = *((_DWORD *)v7 + 60);
  else
    v19 = 0;
  LODWORD(v46) = v19;
  UIControls::ButtonEx::UpdateImage(v7);
  v20 = *((_DWORD *)v7 + 52);
  if ( ((v20 - 1) & 0xFFFFFFFD) != 0 )
  {
    v21 = v19 + HIDWORD(v39) + *((_DWORD *)v7 + 51);
    v22 = *((_DWORD *)v7 + 50);
  }
  else
  {
    v22 = *((_DWORD *)v7 + 50);
    v14 += (_DWORD)v46 + v22;
    v21 = HIDWORD(v39);
  }
  v23 = v22;
  LODWORD(v39) = v22;
  v24 = v49->right - v49->left;
  if ( v14 < v24 )
    v24 = v14;
  if ( v21 >= v49->bottom - v49->top )
    v21 = v49->bottom - v49->top;
  if ( v12 )
  {
    if ( v12 == 2 )
    {
      v25 = *(_DWORD *)&v38[8];
      v26 = *(_DWORD *)&v38[8] - v24;
      *(_DWORD *)v38 = *(_DWORD *)&v38[8] - v24;
      v27 = *(_DWORD *)&v38[8] - v22;
      LODWORD(v49) = *(_DWORD *)&v38[8] - v24;
      goto LABEL_46;
    }
    v27 = (*(_DWORD *)&v38[8] - *(_DWORD *)v38 - v22) / 2 + *(_DWORD *)v38;
    v26 = (*(_DWORD *)&v38[8] - *(_DWORD *)v38 - v24) / 2 + *(_DWORD *)v38;
    *(_DWORD *)v38 = v26;
    v25 = v26 + v24;
    v23 = v39;
    v22 = v39;
    LODWORD(v49) = v26;
  }
  else
  {
    v27 = *(_DWORD *)v38;
    v25 = v24 + *(_DWORD *)v38;
    v26 = *(_DWORD *)v38;
    LODWORD(v49) = *(_DWORD *)v38;
  }
  *(_DWORD *)&v38[8] = v25;
LABEL_46:
  if ( v13 )
  {
    if ( v13 == 2 )
    {
      v28 = *(_DWORD *)&v38[12];
      v29 = *(_DWORD *)&v38[12] - v21;
      *(_DWORD *)&v38[4] = *(_DWORD *)&v38[12] - v21;
      v30 = *(_DWORD *)&v38[12] - *((_DWORD *)v7 + 51);
      goto LABEL_52;
    }
    v30 = (*(_DWORD *)&v38[12] - *(_DWORD *)&v38[4] - *((_DWORD *)v7 + 51)) / 2 + *(_DWORD *)&v38[4];
    v29 = (*(_DWORD *)&v38[12] - *(_DWORD *)&v38[4] - v21) / 2 + *(_DWORD *)&v38[4];
    *(_DWORD *)&v38[4] = v29;
    v28 = v21 + v29;
    v23 = v39;
  }
  else
  {
    v30 = *(_DWORD *)&v38[4];
    v28 = v21 + *(_DWORD *)&v38[4];
    v29 = *(_DWORD *)&v38[4];
  }
  *(_DWORD *)&v38[12] = v28;
LABEL_52:
  if ( v20 )
  {
    v31 = v20 - 1;
    if ( v31 )
    {
      v32 = v31 - 1;
      if ( !v32 )
      {
        *(_DWORD *)&v38[4] = (_DWORD)v46 + v29 + *((_DWORD *)v7 + 51);
        v30 = v29;
        goto LABEL_58;
      }
      v33 = v32 - 1;
      if ( !v33 )
      {
        *(_DWORD *)&v38[8] = v25 - (v23 + (_DWORD)v46);
        v26 = v25 - v23;
        v27 = v25 - v23;
        v22 = v23;
        goto LABEL_59;
      }
      if ( v33 == 1 )
      {
        v30 = v28 - *((_DWORD *)v7 + 51);
        *(_DWORD *)&v38[12] = v30 - (_DWORD)v46;
LABEL_58:
        v26 = v27;
        goto LABEL_59;
      }
    }
  }
  else if ( !*((_DWORD *)v15 - 4) )
  {
    goto LABEL_58;
  }
  *(_DWORD *)v38 = (_DWORD)v46 + v26 + v23;
  v22 = v23;
  v27 = (int)v49;
LABEL_59:
  v39 = __PAIR64__(v30, v27);
  LODWORD(v40) = v22;
  HIDWORD(v40) = *((_DWORD *)v7 + 51);
  v34 = v43;
  if ( (GetWindowLongW(*v43, -20) & 0x400000) != 0 && *((_DWORD *)v7 + 43) == 1 )
  {
    LODWORD(v39) = v22 + v26;
    LODWORD(v40) = -v22;
  }
  ImageOffset = UIControls::ButtonEx::GetImageOffset(v7, (unsigned int)v48);
  v36 = (UIBase *)v47;
  Gdiplus::Graphics::DrawImage(v47, v42, &v39, ImageOffset);
LABEL_68:
  if ( *((_DWORD *)v15 - 4) )
  {
    LODWORD(v49) = a5;
    Gdiplus::SolidBrush::SolidBrush((Gdiplus::SolidBrush *)&v39, (const struct Gdiplus::Color *)&v49);
    v37 = (const unsigned __int16 *)UIControls::ButtonEx::GetFont(v7);
    UIBase::DrawTextHandleRTL(
      *v34,
      v36,
      v15,
      v37,
      (const struct Gdiplus::Font *)v38,
      (const struct tagRECT *)v7 + 31,
      (struct Gdiplus::StringFormat *)&v39);
    GdipDeleteBrush(v40);
  }
  Base::String::~String((Base::String *)&String);
  Gdiplus::Graphics::SetPageUnit(v44, v45);
}

```

## disassembly

```asm
0x18002ad08  mov     rax, rsp
0x18002ad0b  mov     [rax+20h], r9
0x18002ad0f  mov     [rax+18h], r8d
0x18002ad13  mov     [rax+10h], rdx
0x18002ad17  mov     [rax+8], rcx
0x18002ad1b  push    rbx
0x18002ad1c  push    rsi
0x18002ad1d  push    rdi
0x18002ad1e  push    r12
0x18002ad20  push    r13
0x18002ad22  push    r14
0x18002ad24  push    r15
0x18002ad26  sub     rsp, 0B0h
0x18002ad2d  mov     rsi, r9
0x18002ad30  mov     r15d, r8d
0x18002ad33  mov     r14, rcx
0x18002ad36  lea     rcx, [rax-48h]
0x18002ad3a  call    ??0SetPageUnitAndRestore@GdipUtil@@QEAA@AEAVGraphics@Gdiplus@@W4Unit@3@@Z; GdipUtil::SetPageUnitAndRestore::SetPageUnitAndRestore(Gdiplus::Graphics &,Gdiplus::Unit)
0x18002ad3f  nop
0x18002ad40  mov     rcx, r14; this
0x18002ad43  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x18002ad48  mov     rax, [r14+0C0h]
0x18002ad4f  mov     [rsp+0E8h+var_58], rax
0x18002ad57  mov     qword ptr [rsp+0E8h+var_88], rax
0x18002ad5c  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002ad62  nop
0x18002ad63  mov     rdx, rax
0x18002ad66  lea     rcx, [rsp+0E8h+String]
0x18002ad6e  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002ad73  nop
0x18002ad74  lea     rax, [r14+8]
0x18002ad78  mov     [rsp+0E8h+var_50], rax
0x18002ad80  lea     rdx, [rsp+0E8h+String]
0x18002ad88  mov     rcx, rax
0x18002ad8b  call    ?GetWindowTextW@CWindow@ATL@@QEBAHAEAV?$CSimpleStringT@G$0A@@2@@Z; ATL::CWindow::GetWindowTextW(ATL::CSimpleStringT<ushort,0> &)
0x18002ad90  nop
0x18002ad91  mov     rdx, [rsp+0E8h+var_58]
0x18002ad99  jmp     short loc_18002ADC0
0x18002ad9b  mov     r14, [rsp+0E8h+arg_0]
0x18002ada3  mov     rdx, qword ptr [rsp+0E8h+var_88]
0x18002ada8  mov     [rsp+0E8h+var_58], rdx
0x18002adb0  mov     rsi, [rsp+0E8h+arg_18]
0x18002adb8  mov     r15d, dword ptr [rsp+0E8h+arg_10]
0x18002adc0  mov     r8d, 1
0x18002adc6  mov     r12d, r8d
0x18002adc9  mov     r13d, r8d
0x18002adcc  xor     edi, edi
0x18002adce  mov     [rsp+0E8h+var_78], rdi
0x18002add3  mov     rbx, [rsp+0E8h+String]
0x18002addb  cmp     [rbx-10h], edi
0x18002adde  jz      loc_18002AF66
0x18002ade4  mov     eax, r15d
0x18002ade7  and     eax, 3
0x18002adea  sub     eax, r8d
0x18002aded  jz      short loc_18002AE19
0x18002adef  sub     eax, r8d
0x18002adf2  jz      short loc_18002AE60
0x18002adf4  cmp     eax, r8d
0x18002adf7  jz      short loc_18002AE1C
0x18002adf9  test    rdx, rdx
0x18002adfc  jz      short loc_18002AE1C
0x18002adfe  mov     ecx, [r14+0D0h]
0x18002ae05  sub     ecx, r8d
0x18002ae08  jz      short loc_18002AE19
0x18002ae0a  sub     ecx, r8d
0x18002ae0d  jz      short loc_18002AE1C
0x18002ae0f  sub     ecx, r8d
0x18002ae12  jz      short loc_18002AE60
0x18002ae14  cmp     ecx, r8d
0x18002ae17  jz      short loc_18002AE1C
0x18002ae19  xor     r12d, r12d
0x18002ae1c  mov     r15d, 2
0x18002ae22  mov     eax, dword ptr [rsp+0E8h+arg_10]
0x18002ae29  and     eax, 0Ch
0x18002ae2c  cmp     eax, 4
0x18002ae2f  jz      short loc_18002AE6B
0x18002ae31  cmp     eax, 8
0x18002ae34  jz      short loc_18002AE5B
0x18002ae36  cmp     eax, 0Ch
0x18002ae39  jz      short loc_18002AE6E
0x18002ae3b  test    rdx, rdx
0x18002ae3e  jz      short loc_18002AE6E
0x18002ae40  mov     ecx, [r14+0D0h]
0x18002ae47  sub     ecx, r8d
0x18002ae4a  jz      short loc_18002AE6E
0x18002ae4c  sub     ecx, r8d
0x18002ae4f  jz      short loc_18002AE6B
0x18002ae51  sub     ecx, r8d
0x18002ae54  jz      short loc_18002AE6E
0x18002ae56  cmp     ecx, r8d
0x18002ae59  jnz     short loc_18002AE6E
0x18002ae5b  mov     r13d, r15d
0x18002ae5e  jmp     short loc_18002AE6E
0x18002ae60  mov     r15d, 2
0x18002ae66  mov     r12d, r15d
0x18002ae69  jmp     short loc_18002AE22
0x18002ae6b  xor     r13d, r13d
0x18002ae6e  lea     rcx, [r14+1F0h]
0x18002ae75  mov     edx, r12d
0x18002ae78  call    ?SetAlignment@StringFormat@Gdiplus@@QEAA?AW4Status@2@W4StringAlignment@2@@Z; Gdiplus::StringFormat::SetAlignment(Gdiplus::StringAlignment)
0x18002ae7d  mov     edx, r13d
0x18002ae80  lea     rcx, [r14+1F0h]
0x18002ae87  call    ?SetLineAlignment@StringFormat@Gdiplus@@QEAA?AW4Status@2@W4StringAlignment@2@@Z; Gdiplus::StringFormat::SetLineAlignment(Gdiplus::StringAlignment)
0x18002ae8c  mov     eax, dword ptr [rsp+0E8h+arg_10]
0x18002ae93  bt      eax, 0Bh
0x18002ae97  jnb     short loc_18002AEA0
0x18002ae99  mov     edx, 1
0x18002ae9e  jmp     short loc_18002AEAA
0x18002aea0  mov     edx, eax
0x18002aea2  shr     edx, 0Ch
0x18002aea5  not     edx
0x18002aea7  and     edx, r15d
0x18002aeaa  lea     rcx, [r14+1F0h]
0x18002aeb1  call    ?SetHotkeyPrefix@StringFormat@Gdiplus@@QEAA?AW4Status@2@W4HotkeyPrefix@2@@Z; Gdiplus::StringFormat::SetHotkeyPrefix(Gdiplus::HotkeyPrefix)
0x18002aeb6  mov     eax, [rsi+8]
0x18002aeb9  sub     eax, [rsi]
0x18002aebb  mov     dword ptr [rsp+0E8h+var_88], eax
0x18002aebf  mov     eax, [rsi+0Ch]
0x18002aec2  sub     eax, [rsi+4]
0x18002aec5  mov     dword ptr [rsp+0E8h+var_88+4], eax
0x18002aec9  mov     byte ptr [rsp+0E8h+var_C0], dil
0x18002aece  lea     rax, [rsp+0E8h+var_88]
0x18002aed3  mov     [rsp+0E8h+var_C8], rax; bool
0x18002aed8  mov     r9d, dword ptr [rsp+0E8h+arg_10]; struct tagSIZE *
0x18002aee0  mov     r8, [rsp+0E8h+arg_8]; unsigned int
0x18002aee8  lea     rdx, [rsp+0E8h+arg_0]; struct Gdiplus::Graphics *
0x18002aef0  mov     rcx, r14; this
0x18002aef3  call    ?GetMaximumTextSize@ButtonEx@UIControls@@AEBA?AUtagSIZE@@AEBVGraphics@Gdiplus@@KAEBU3@_N@Z; UIControls::ButtonEx::GetMaximumTextSize(Gdiplus::Graphics const &,ulong,tagSIZE const &,bool)
0x18002aef8  cmp     dword ptr [rsp+0E8h+arg_0], edi
0x18002aeff  jle     short loc_18002AF4F
0x18002af01  cmp     dword ptr [rsp+0E8h+arg_0+4], edi
0x18002af08  jle     short loc_18002AF4F
0x18002af0a  mov     rcx, r14; this
0x18002af0d  call    ?GetFont@ButtonEx@UIControls@@QEAAPEAVFont@Gdiplus@@XZ; UIControls::ButtonEx::GetFont(void)
0x18002af12  lea     rcx, [rsp+0E8h+arg_0]
0x18002af1a  mov     [rsp+0E8h+var_B8], rcx
0x18002af1f  lea     rcx, [r14+1F0h]
0x18002af26  mov     [rsp+0E8h+var_C0], rcx
0x18002af2b  lea     rcx, [rsp+0E8h+var_78]
0x18002af30  mov     [rsp+0E8h+var_C8], rcx
0x18002af35  mov     r8, rbx
0x18002af38  mov     rdx, rax
0x18002af3b  mov     rcx, [rsp+0E8h+arg_8]
0x18002af43  call    ?MeasureStringHelper@GdipUtil@@YA?AW4Status@Gdiplus@@AEBVGraphics@3@PEBVFont@3@PEBGHAEAUtagSIZE@@PEBVStringFormat@3@PEBU6@PEAH6@Z; GdipUtil::MeasureStringHelper(Gdiplus::Graphics const &,Gdiplus::Font const *,ushort const *,int,tagSIZE &,Gdiplus::StringFormat const *,tagSIZE const *,int *,int *)
0x18002af48  mov     rdi, [rsp+0E8h+var_78]
0x18002af4d  jmp     short loc_18002AF6C
0x18002af4f  lea     rcx, [rsp+0E8h+String]
0x18002af57  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x18002af5c  mov     rbx, [rsp+0E8h+String]
0x18002af64  jmp     short loc_18002AF6C
0x18002af66  mov     r15d, 2
0x18002af6c  movups  xmm0, xmmword ptr [rsi]
0x18002af6f  movdqu  xmmword ptr [rsp+0E8h+var_88], xmm0
0x18002af75  cmp     [rsp+0E8h+var_58], 0
0x18002af7e  jz      loc_18002B243
0x18002af84  cmp     dword ptr [rbx-10h], 0
0x18002af88  jnz     short loc_18002AF8E
0x18002af8a  xor     esi, esi
0x18002af8c  jmp     short loc_18002AF95
0x18002af8e  mov     esi, [r14+0F0h]
0x18002af95  mov     dword ptr [rsp+0E8h+arg_0], esi
0x18002af9c  mov     rcx, r14; this
0x18002af9f  call    ?UpdateImage@ButtonEx@UIControls@@AEBAXXZ; UIControls::ButtonEx::UpdateImage(void)
0x18002afa4  mov     r10d, [r14+0D0h]
0x18002afab  lea     eax, [r10-1]
0x18002afaf  test    eax, 0FFFFFFFDh
0x18002afb4  jz      short loc_18002AFCE
0x18002afb6  mov     r11d, [r14+0CCh]
0x18002afbd  add     r11d, dword ptr [rsp+0E8h+var_78+4]
0x18002afc2  add     r11d, esi
0x18002afc5  mov     esi, [r14+0C8h]
0x18002afcc  jmp     short loc_18002AFE3
0x18002afce  mov     esi, [r14+0C8h]
0x18002afd5  add     edi, esi
0x18002afd7  add     edi, dword ptr [rsp+0E8h+arg_0]
0x18002afde  mov     r11d, dword ptr [rsp+0E8h+var_78+4]
0x18002afe3  mov     edx, esi
0x18002afe5  mov     dword ptr [rsp+0E8h+var_78], edx
0x18002afe9  mov     rcx, [rsp+0E8h+arg_18]
0x18002aff1  mov     r9d, [rcx+8]
0x18002aff5  sub     r9d, [rcx]
0x18002aff8  cmp     edi, r9d
0x18002affb  cmovl   r9d, edi
0x18002afff  mov     eax, [rcx+0Ch]
0x18002b002  sub     eax, [rcx+4]
0x18002b005  cmp     r11d, eax
0x18002b008  cmovge  r11d, eax
0x18002b00c  test    r12d, r12d
0x18002b00f  jz      short loc_18002B073
0x18002b011  sub     r12d, 1
0x18002b015  jz      short loc_18002B03B
0x18002b017  cmp     r12d, 1
0x18002b01b  jnz     short loc_18002B03B
0x18002b01d  mov     r12d, dword ptr [rsp+0E8h+var_88+8]
0x18002b022  mov     edi, r12d
0x18002b025  sub     edi, r9d
0x18002b028  mov     dword ptr [rsp+0E8h+var_88], edi
0x18002b02c  mov     r8d, r12d
0x18002b02f  sub     r8d, edx
0x18002b032  mov     dword ptr [rsp+0E8h+arg_18], edi
0x18002b039  jmp     short loc_18002B08C
0x18002b03b  mov     ecx, dword ptr [rsp+0E8h+var_88+8]
0x18002b03f  mov     edi, dword ptr [rsp+0E8h+var_88]
0x18002b043  sub     ecx, edi
0x18002b045  mov     eax, ecx
0x18002b047  sub     eax, edx
0x18002b049  cdq
0x18002b04a  idiv    r15d
0x18002b04d  lea     r8d, [rax+rdi]
0x18002b051  sub     ecx, r9d
0x18002b054  mov     eax, ecx
0x18002b056  cdq
0x18002b057  idiv    r15d
0x18002b05a  add     edi, eax
0x18002b05c  mov     dword ptr [rsp+0E8h+var_88], edi
0x18002b060  lea     r12d, [rdi+r9]
0x18002b064  mov     edx, dword ptr [rsp+0E8h+var_78]
0x18002b068  mov     esi, edx
0x18002b06a  mov     dword ptr [rsp+0E8h+arg_18], edi
0x18002b071  jmp     short loc_18002B087
0x18002b073  mov     r8d, dword ptr [rsp+0E8h+var_88]
0x18002b078  lea     r12d, [r9+r8]
0x18002b07c  mov     edi, r8d
0x18002b07f  mov     dword ptr [rsp+0E8h+arg_18], r8d
0x18002b087  mov     dword ptr [rsp+0E8h+var_88+8], r12d
0x18002b08c  test    r13d, r13d
0x18002b08f  jz      short loc_18002B0F0
0x18002b091  sub     r13d, 1
0x18002b095  jz      short loc_18002B0B8
0x18002b097  cmp     r13d, 1
0x18002b09b  jnz     short loc_18002B0B8
0x18002b09d  mov     ecx, dword ptr [rsp+0E8h+var_88+0Ch]
0x18002b0a1  mov     r13d, ecx
0x18002b0a4  sub     r13d, r11d
0x18002b0a7  mov     dword ptr [rsp+0E8h+var_88+4], r13d
0x18002b0ac  mov     r9d, ecx
0x18002b0af  sub     r9d, [r14+0CCh]
0x18002b0b6  jmp     short loc_18002B100
0x18002b0b8  mov     ecx, dword ptr [rsp+0E8h+var_88+0Ch]
0x18002b0bc  mov     r13d, dword ptr [rsp+0E8h+var_88+4]
0x18002b0c1  sub     ecx, r13d
0x18002b0c4  mov     eax, ecx
0x18002b0c6  sub     eax, [r14+0CCh]
0x18002b0cd  cdq
0x18002b0ce  idiv    r15d
0x18002b0d1  lea     r9d, [rax+r13]
0x18002b0d5  sub     ecx, r11d
0x18002b0d8  mov     eax, ecx
0x18002b0da  cdq
0x18002b0db  idiv    r15d
0x18002b0de  add     r13d, eax
0x18002b0e1  mov     dword ptr [rsp+0E8h+var_88+4], r13d
0x18002b0e6  lea     ecx, [r11+r13]
0x18002b0ea  mov     edx, dword ptr [rsp+0E8h+var_78]
0x18002b0ee  jmp     short loc_18002B0FC
0x18002b0f0  mov     r9d, dword ptr [rsp+0E8h+var_88+4]
0x18002b0f5  lea     ecx, [r11+r9]
0x18002b0f9  mov     r13d, r9d
0x18002b0fc  mov     dword ptr [rsp+0E8h+var_88+0Ch], ecx
0x18002b100  test    r10d, r10d
0x18002b103  jz      loc_18002B21C
0x18002b109  sub     r10d, 1
0x18002b10d  jz      loc_18002B226
0x18002b113  sub     r10d, 1
0x18002b117  jz      loc_18002B1FF
0x18002b11d  sub     r10d, 1
0x18002b121  jz      loc_18002B1DF
0x18002b127  cmp     r10d, 1
0x18002b12b  jnz     loc_18002B226
0x18002b131  mov     r9d, ecx
0x18002b134  sub     r9d, [r14+0CCh]
0x18002b13b  mov     eax, r9d
0x18002b13e  sub     eax, dword ptr [rsp+0E8h+arg_0]
0x18002b145  mov     dword ptr [rsp+0E8h+var_88+0Ch], eax
0x18002b149  mov     edi, r8d
0x18002b14c  mov     dword ptr [rsp+0E8h+var_78], r8d
0x18002b151  mov     dword ptr [rsp+0E8h+var_78+4], r9d
0x18002b156  mov     dword ptr [rsp+0E8h+var_70], esi
0x18002b15a  mov     eax, [r14+0CCh]
0x18002b161  mov     dword ptr [rsp+0E8h+var_70+4], eax
0x18002b165  mov     edx, 0FFFFFFECh; nIndex
0x18002b16a  mov     r15, [rsp+0E8h+var_50]
0x18002b172  mov     rcx, [r15]; hWnd
0x18002b175  call    cs:__imp_GetWindowLongW
0x18002b17b  bt      eax, 16h
0x18002b17f  jnb     short loc_18002B198
0x18002b181  cmp     dword ptr [r14+0ACh], 1
0x18002b189  jnz     short loc_18002B198
0x18002b18b  lea     eax, [rsi+rdi]
0x18002b18e  mov     dword ptr [rsp+0E8h+var_78], eax
0x18002b192  neg     esi
0x18002b194  mov     dword ptr [rsp+0E8h+var_70], esi
0x18002b198  mov     edi, [r14+0CCh]
0x18002b19f  mov     esi, [r14+0C8h]
0x18002b1a6  mov     edx, dword ptr [rsp+0E8h+arg_10]; unsigned int
0x18002b1ad  mov     rcx, r14; this
0x18002b1b0  call    ?GetImageOffset@ButtonEx@UIControls@@IEBAHK@Z; UIControls::ButtonEx::GetImageOffset(ulong)
0x18002b1b5  mov     dword ptr [rsp+0E8h+var_B8], edi
0x18002b1b9  mov     dword ptr [rsp+0E8h+var_C0], esi
0x18002b1bd  mov     r9d, eax
  ... truncated ...
```
