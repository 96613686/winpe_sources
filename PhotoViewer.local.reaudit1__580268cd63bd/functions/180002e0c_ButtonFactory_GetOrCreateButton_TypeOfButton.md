# ButtonFactory::GetOrCreateButton(TypeOfButton)

- ea: `0x180002e0c`
- end: `0x1800032ad`
- name: `?GetOrCreateButton@ButtonFactory@@QEAAAEAV?$ButtonExTransparentBack@VNavBarBitMapOnlyButton@@@UIControls@@W4TypeOfButton@@@Z`
- size: `1185`
- prototype: ``
- caller_count: `1`
- callee_count: `19`
- tags: ``

## callers

- `0x1800710ac`

## callees

- `0x180002420`
- `0x1800026fc`
- `0x180002e0c`
- `0x1800037d8`
- `0x180003d60`
- `0x180004080`
- `0x1800043a4`
- `0x180004500`
- `0x18000461c`
- `0x1800046b8`
- `0x180004748`
- `0x180004908`
- `0x18002c4ec`
- `0x18002c994`
- `0x180032154`
- `0x180033d0c`
- `0x18003f800`
- `0x18005bcb4`
- `0x18007b000`

## import_xrefs

- `USER32!SetWindowPos` at `0x1800031b9`
- `USER32!SetWindowPos` at `0x1800031b9`
- `USER32!IsWindow` at `0x180002e4a`
- `USER32!IsWindow` at `0x180002e4a`
- `gdiplus!GdipCreateFromHWND` at `0x18000314a`
- `gdiplus!GdipCreateFromHWND` at `0x18000314a`
- `gdiplus!GdipDeleteGraphics` at `0x1800031ce`
- `gdiplus!GdipDeleteGraphics` at `0x1800031ce`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180002eaa`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000312c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180002eaa`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18000312c`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x1800031c3`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x1800031c3`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
_QWORD *__fastcall ButtonFactory::GetOrCreateButton(_QWORD *a1, int a2)
{
  __int64 v4; // rdi
  unsigned int DpiOffset; // eax
  int v7; // edx
  int v8; // ebx
  int v9; // ebx
  int v10; // ebx
  int v11; // ebx
  int v12; // ebx
  int v13; // ebx
  int v14; // ebx
  _QWORD *v15; // rbx
  int v16; // edi
  int v17; // ebx
  int v18; // esi
  _QWORD *v19; // r15
  __int64 v20; // r14
  const unsigned __int16 **v21; // rax
  UIBase *v22; // rcx
  int v23; // eax
  int v24; // eax
  UIBase *v25; // rcx
  struct Gdiplus::Bitmap *v26; // rax
  unsigned __int16 Id; // ax
  const unsigned __int16 *v28; // r8
  const unsigned __int16 *v29; // r9
  __int64 v30; // rdx
  __int64 v31; // rcx
  int v32; // edx
  int v33; // eax
  Base *v34; // rcx
  __int16 v35; // [rsp+38h] [rbp-41h]
  __int64 v36; // [rsp+60h] [rbp-19h] BYREF
  struct tagSIZE cy; // [rsp+68h] [rbp-11h] BYREF
  __int64 v38; // [rsp+70h] [rbp-9h] BYREF
  int v39; // [rsp+78h] [rbp-1h]
  _BYTE pExceptionObject[24]; // [rsp+80h] [rbp+7h] BYREF
  __m128i si128; // [rsp+98h] [rbp+1Fh] BYREF

  v4 = 70LL * a2;
  if ( IsWindow((HWND)a1[v4 + 2]) )
    return &a1[v4 + 1];
  DpiOffset = GetDpiOffset();
  v8 = a2 - 1;
  if ( !v8 )
  {
    v15 = a1 + 71;
    UIControls::ButtonEx::CreateButton(
      a1 + 71,
      *a1,
      4001,
      (unsigned int)dword_18008B280[DpiOffset],
      dword_18008B288[DpiOffset],
      dword_18008B270[DpiOffset],
      42000);
    return v15;
  }
  v9 = v8 - 1;
  if ( !v9 )
  {
    v15 = a1 + 141;
    UIControls::ButtonEx::CreateButton(
      a1 + 141,
      *a1,
      4005,
      (unsigned int)dword_18008B278[DpiOffset],
      dword_18008B260[DpiOffset],
      dword_18008B268[DpiOffset],
      42001);
    UIControls::ButtonEx::ChangeImageMirroring(a1 + 141);
    return v15;
  }
  v10 = v9 - 1;
  if ( v10 )
  {
    v11 = v10 - 1;
    if ( v11 )
    {
      v12 = v11 - 1;
      if ( v12 )
      {
        v13 = v12 - 1;
        if ( v13 )
        {
          v14 = v13 - 1;
          if ( v14 )
          {
            if ( v14 != 1 )
            {
              Base::Throw((Base *)0x80004005LL, v7);
              __debugbreak();
            }
            v15 = a1 + 561;
            UIControls::ButtonEx::CreateButton(
              a1 + 561,
              *a1,
              4125,
              (unsigned int)dword_18008B1C0[DpiOffset],
              dword_18008B1A8[DpiOffset],
              dword_18008B1B0[DpiOffset],
              42010);
          }
          else
          {
            v15 = a1 + 491;
            UIControls::ButtonEx::CreateButton(
              a1 + 491,
              *a1,
              4020,
              (unsigned int)dword_18008B1F0[DpiOffset],
              dword_18008B1F8[DpiOffset],
              dword_18008B1E8[DpiOffset],
              42006);
            *((_BYTE *)a1 + 4472) = 1;
          }
        }
        else
        {
          v15 = a1 + 421;
          UIControls::ButtonEx::CreateButton(
            a1 + 421,
            *a1,
            4016,
            (unsigned int)dword_18008B218[DpiOffset],
            dword_18008B200[DpiOffset],
            dword_18008B208[DpiOffset],
            42005);
        }
      }
      else
      {
        v15 = a1 + 351;
        UIControls::ButtonEx::CreateButton(
          a1 + 351,
          *a1,
          4013,
          (unsigned int)dword_18008B220[DpiOffset],
          dword_18008B228[DpiOffset],
          dword_18008B210[DpiOffset],
          42004);
      }
    }
    else
    {
      v15 = a1 + 281;
      UIControls::ButtonEx::CreateButton(
        a1 + 281,
        *a1,
        4010,
        (unsigned int)dword_18008B248[DpiOffset],
        dword_18008B230[DpiOffset],
        dword_18008B238[DpiOffset],
        42003);
    }
    return v15;
  }
  v16 = dword_18008B240[DpiOffset];
  v17 = dword_18008B258[DpiOffset];
  v18 = dword_18008B250[DpiOffset];
  v19 = a1 + 211;
  v20 = *a1;
  v21 = (const unsigned __int16 **)Base::ResourceString::ResourceString((Base::ResourceString *)&v36, 0xFA8u);
  UIControls::ButtonEx::SetToolTip((UIControls::ButtonEx *)v19, *v21);
  Base::String::~String((Base::String *)&v36);
  *((_DWORD *)v19 + 131) = v18;
  v23 = v18;
  if ( v17 )
    v23 = v17;
  *((_DWORD *)v19 + 132) = v23;
  v24 = v18;
  if ( v16 )
    v24 = v16;
  *((_DWORD *)v19 + 133) = v24;
  *((_BYTE *)v19 + 536) = UIBase::IsHighContrastOn(v22);
  *((_BYTE *)v19 + 537) = UIBase::IsForegroundWindowColorDarker(v25);
  if ( v18 )
  {
    Id = UIBase::ThemedImageResource::GetId((UIBase::ThemedImageResource *)((char *)v19 + 524));
    v26 = GdipUtil::GdiplusBitmapFromResourceEx((GdipUtil *)hInstance, (HINSTANCE)Id, v28, v29);
  }
  else
  {
    v26 = 0;
  }
  UIControls::ButtonEx::SetImageInternal(v19, v26, 0, 0);
  si128 = _mm_load_si128((const __m128i *)&_xmm);
  if ( !qword_1800A32A0 )
    qword_1800A32A0 = 0;
  v35 = ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(
          v31,
          v30,
          &qword_1800A3250,
          v19 + 8);
  if ( !ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(
          v19,
          v20,
          &si128,
          0,
          1409351680,
          0,
          42002,
          v35) )
  {
    Base::Throw((Base *)0x80004005LL, v32);
    __debugbreak();
  }
  UIControls::ButtonEx::ChangeHoverStyle(v19);
  v36 = 0;
  v33 = GdipCreateFromHWND(v20, &v36);
  v38 = v36;
  v39 = 0;
  if ( v33 )
  {
    Base::GdiException::GdiException((Base::GdiException *)pExceptionObject, v33);
    throw (Base::GdiException *)pExceptionObject;
  }
  cy = 0;
  UIControls::ButtonEx::Measure((UIControls::ButtonEx *)v19, (const struct Gdiplus::Graphics *)&v38, &cy);
  if ( !SetWindowPos((HWND)v19[1], 0, 0, 0, cy.cx, cy.cy, 0x16u) )
    Base::ThrowLastError(v34);
  GdipDeleteGraphics(v38);
  UIControls::ButtonEx::ChangeImageMirroring(v19);
  return v19;
}

```

## disassembly

```asm
0x180002e0c  mov     [rsp-8+arg_10], rbx
0x180002e11  mov     [rsp-8+arg_18], rsi
0x180002e16  push    rbp
0x180002e17  push    rdi
0x180002e18  push    r12
0x180002e1a  push    r14
0x180002e1c  push    r15
0x180002e1e  lea     rbp, [rsp-37h]
0x180002e23  sub     rsp, 0B0h
0x180002e2a  mov     rax, cs:__security_cookie
0x180002e31  xor     rax, rsp
0x180002e34  mov     [rbp+57h+var_28], rax
0x180002e38  movsxd  rbx, edx
0x180002e3b  mov     r14, rcx
0x180002e3e  imul    rdi, rbx, 230h
0x180002e45  mov     rcx, [rdi+rcx+10h]; hWnd
0x180002e4a  call    cs:__imp_IsWindow
0x180002e50  test    eax, eax
0x180002e52  jz      short loc_180002E60
0x180002e54  lea     rax, [r14+8]
0x180002e58  add     rax, rdi
0x180002e5b  jmp     loc_180003285
0x180002e60  call    ?GetDpiOffset@@YAIXZ; GetDpiOffset(void)
0x180002e65  sub     ebx, 1
0x180002e68  jz      loc_180003238
0x180002e6e  sub     ebx, 1
0x180002e71  jz      loc_1800031E4
0x180002e77  sub     ebx, 1
0x180002e7a  jz      loc_180003007
0x180002e80  sub     ebx, 1
0x180002e83  jz      loc_180002FC7
0x180002e89  sub     ebx, 1
0x180002e8c  jz      loc_180002F87
0x180002e92  sub     ebx, 1
0x180002e95  jz      loc_180002F47
0x180002e9b  sub     ebx, 1
0x180002e9e  jz      short loc_180002EF1
0x180002ea0  cmp     ebx, 1
0x180002ea3  jz      short loc_180002EB1
0x180002ea5  mov     ecx, 80004005h
0x180002eaa  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180002eb0  int     3; Trap to Debugger
0x180002eb1  lea     rbx, [r14+1188h]
0x180002eb8  mov     r9d, eax
0x180002ebb  lea     rdx, __ImageBase
0x180002ec2  mov     [rsp+0D0h+uFlags], 0A41Ah
0x180002eca  mov     ecx, ds:rva dword_18008B1B0[rdx+r9*4]
0x180002ed2  mov     [rsp+0D0h+cy], ecx
0x180002ed6  mov     ecx, ds:rva dword_18008B1A8[rdx+r9*4]
0x180002ede  mov     r9d, ds:rva dword_18008B1C0[rdx+r9*4]
0x180002ee6  mov     r8d, 101Dh
0x180002eec  jmp     loc_180003273
0x180002ef1  lea     rbx, [r14+0F58h]
0x180002ef8  mov     r9d, eax
0x180002efb  lea     rdx, __ImageBase
0x180002f02  mov     [rsp+0D0h+uFlags], 0A416h
0x180002f0a  mov     ecx, ds:rva dword_18008B1E8[rdx+r9*4]
0x180002f12  mov     [rsp+0D0h+cy], ecx
0x180002f16  mov     ecx, ds:rva dword_18008B1F8[rdx+r9*4]
0x180002f1e  mov     [rsp+0D0h+var_B0], ecx
0x180002f22  mov     r9d, ds:rva dword_18008B1F0[rdx+r9*4]
0x180002f2a  mov     r8d, 0FB4h
0x180002f30  mov     rdx, [r14]
0x180002f33  mov     rcx, rbx
0x180002f36  call    ?CreateButton@ButtonEx@UIControls@@QEAAXPEAUHWND__@@IIIIIW4EImagePlacement@12@W4EHoverStyle@12@HI@Z; UIControls::ButtonEx::CreateButton(HWND__ *,uint,uint,uint,uint,uint,UIControls::ButtonEx::EImagePlacement,UIControls::ButtonEx::EHoverStyle,int,uint)
0x180002f3b  mov     byte ptr [rbx+220h], 1
0x180002f42  jmp     loc_180003282
0x180002f47  lea     rbx, [r14+0D28h]
0x180002f4e  mov     r9d, eax
0x180002f51  lea     rdx, __ImageBase
0x180002f58  mov     [rsp+0D0h+uFlags], 0A415h
0x180002f60  mov     ecx, ds:rva dword_18008B208[rdx+r9*4]
0x180002f68  mov     [rsp+0D0h+cy], ecx
0x180002f6c  mov     ecx, ds:rva dword_18008B200[rdx+r9*4]
0x180002f74  mov     r9d, ds:rva dword_18008B218[rdx+r9*4]
0x180002f7c  mov     r8d, 0FB0h
0x180002f82  jmp     loc_180003273
0x180002f87  lea     rbx, [r14+0AF8h]
0x180002f8e  mov     r9d, eax
0x180002f91  lea     rdx, __ImageBase
0x180002f98  mov     [rsp+0D0h+uFlags], 0A414h
0x180002fa0  mov     ecx, ds:rva dword_18008B210[rdx+r9*4]
0x180002fa8  mov     [rsp+0D0h+cy], ecx
0x180002fac  mov     ecx, ds:rva dword_18008B228[rdx+r9*4]
0x180002fb4  mov     r9d, ds:rva dword_18008B220[rdx+r9*4]
0x180002fbc  mov     r8d, 0FADh
0x180002fc2  jmp     loc_180003273
0x180002fc7  lea     rbx, [r14+8C8h]
0x180002fce  mov     r9d, eax
0x180002fd1  lea     rdx, __ImageBase
0x180002fd8  mov     [rsp+0D0h+uFlags], 0A413h
0x180002fe0  mov     ecx, ds:rva dword_18008B238[rdx+r9*4]
0x180002fe8  mov     [rsp+0D0h+cy], ecx
0x180002fec  mov     ecx, ds:rva dword_18008B230[rdx+r9*4]
0x180002ff4  mov     r9d, ds:rva dword_18008B248[rdx+r9*4]
0x180002ffc  mov     r8d, 0FAAh
0x180003002  jmp     loc_180003273
0x180003007  mov     eax, eax
0x180003009  lea     rdx, __ImageBase
0x180003010  mov     edi, ds:rva dword_18008B240[rdx+rax*4]
0x180003017  mov     ebx, ds:rva dword_18008B258[rdx+rax*4]
0x18000301e  mov     esi, ds:rva dword_18008B250[rdx+rax*4]
0x180003025  lea     r15, [r14+698h]
0x18000302c  mov     r14, [r14]
0x18000302f  mov     edx, 0FA8h; unsigned int
0x180003034  lea     rcx, [rbp+57h+var_70]; this
0x180003038  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x18000303d  mov     rdx, [rax]; unsigned __int16 *
0x180003040  mov     rcx, r15; this
0x180003043  call    ?SetToolTip@ButtonEx@UIControls@@QEAAXPEBG@Z; UIControls::ButtonEx::SetToolTip(ushort const *)
0x180003048  lea     rcx, [rbp+57h+var_70]; this
0x18000304c  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x180003051  lea     r12, [r15+20Ch]
0x180003058  mov     [r12], esi
0x18000305c  mov     eax, esi
0x18000305e  test    ebx, ebx
0x180003060  cmovnz  eax, ebx
0x180003063  mov     [r15+210h], eax
0x18000306a  mov     eax, esi
0x18000306c  test    edi, edi
0x18000306e  cmovnz  eax, edi
0x180003071  mov     [r15+214h], eax
0x180003078  call    ?IsHighContrastOn@UIBase@@YA_NXZ; UIBase::IsHighContrastOn(void)
0x18000307d  mov     [r15+218h], al
0x180003084  call    ?IsForegroundWindowColorDarker@UIBase@@YA_NXZ; UIBase::IsForegroundWindowColorDarker(void)
0x180003089  mov     [r15+219h], al
0x180003090  test    esi, esi
0x180003092  jnz     short loc_180003098
0x180003094  xor     eax, eax
0x180003096  jmp     short loc_1800030AF
0x180003098  mov     rcx, r12; this
0x18000309b  call    ?GetId@ThemedImageResource@UIBase@@QEBAIXZ; UIBase::ThemedImageResource::GetId(void)
0x1800030a0  movzx   edx, ax; HINSTANCE
0x1800030a3  mov     rcx, cs:hInstance; this
0x1800030aa  call    ?GdiplusBitmapFromResourceEx@GdipUtil@@YAPEAVBitmap@Gdiplus@@PEAUHINSTANCE__@@PEBG1@Z; GdipUtil::GdiplusBitmapFromResourceEx(HINSTANCE__ *,ushort const *,ushort const *)
0x1800030af  xor     r9d, r9d
0x1800030b2  xor     r8d, r8d
0x1800030b5  mov     rdx, rax
0x1800030b8  mov     rcx, r15
0x1800030bb  call    ?SetImageInternal@ButtonEx@UIControls@@AEAAXPEAVImage@Gdiplus@@W4EImagePlacement@12@H@Z; UIControls::ButtonEx::SetImageInternal(Gdiplus::Image *,UIControls::ButtonEx::EImagePlacement,int)
0x1800030c0  movdqa  xmm0, cs:__xmm@00000001000000010000000000000000
0x1800030c8  movdqu  [rbp+57h+var_38], xmm0
0x1800030cd  cmp     cs:qword_1800A32A0, 0
0x1800030d5  jnz     short loc_1800030E2
0x1800030d7  mov     cs:qword_1800A32A0, 0
0x1800030e2  lea     r9, [r15+40h]
0x1800030e6  lea     r8, qword_1800A3250
0x1800030ed  call    ??$AtlModuleRegisterWndClassInfoT@VAtlModuleRegisterWndClassInfoParamW@ATL@@@ATL@@YAGPEAU_ATL_BASE_MODULE70@0@PEAU_ATL_WIN_MODULE70@0@PEAU_ATL_WNDCLASSINFOW@0@PEAP6A_JPEAUHWND__@@I_K_J@ZVAtlModuleRegisterWndClassInfoParamW@0@@Z; ATL::AtlModuleRegisterWndClassInfoT<ATL::AtlModuleRegisterWndClassInfoParamW>(ATL::_ATL_BASE_MODULE70 *,ATL::_ATL_WIN_MODULE70 *,ATL::_ATL_WNDCLASSINFOW *,__int64 (**)(HWND__ *,uint,unsigned __int64,__int64),ATL::AtlModuleRegisterWndClassInfoParamW)
0x1800030f2  mov     [rsp+0D0h+var_98], ax
0x1800030f7  mov     qword ptr [rsp+0D0h+uFlags], 0A412h
0x180003100  mov     [rsp+0D0h+cy], 0
0x180003108  mov     [rsp+0D0h+var_B0], 54010000h
0x180003110  xor     r9d, r9d
0x180003113  lea     r8, [rbp+57h+var_38]
0x180003117  mov     rdx, r14
0x18000311a  mov     rcx, r15
0x18000311d  call    ?Create@?$CWindowImplBaseT@VCWindow@ATL@@V?$CWinTraits@$0FEABAAAA@$0A@@2@@ATL@@QEAAPEAUHWND__@@PEAU3@V_U_RECT@2@PEBGKKV_U_MENUorID@2@GPEAX@Z; ATL::CWindowImplBaseT<ATL::CWindow,ATL::CWinTraits<1409351680,0>>::Create(HWND__ *,ATL::_U_RECT,ushort const *,ulong,ulong,ATL::_U_MENUorID,ushort,void *)
0x180003122  test    rax, rax
0x180003125  jnz     short loc_180003133
0x180003127  mov     ecx, 80004005h
0x18000312c  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180003132  int     3; Trap to Debugger
0x180003133  mov     rcx, r15
0x180003136  call    ?ChangeHoverStyle@ButtonEx@UIControls@@QEAAXW4EHoverStyle@12@@Z; UIControls::ButtonEx::ChangeHoverStyle(UIControls::ButtonEx::EHoverStyle)
0x18000313b  mov     [rbp+57h+var_70], 0
0x180003143  lea     rdx, [rbp+57h+var_70]
0x180003147  mov     rcx, r14
0x18000314a  call    cs:__imp_GdipCreateFromHWND
0x180003150  mov     rcx, [rbp+57h+var_70]
0x180003154  mov     [rbp+57h+var_60], rcx
0x180003158  mov     [rbp+57h+var_58], 0
0x18000315f  test    eax, eax
0x180003161  jz      short loc_18000317F
0x180003163  mov     edx, eax; int
0x180003165  lea     rcx, [rbp+57h+pExceptionObject]; this
0x180003169  call    ??0GdiException@Base@@QEAA@H@Z; Base::GdiException::GdiException(int)
0x18000316e  lea     rdx, _TI2?AVGdiException@Base@@; pThrowInfo
0x180003175  lea     rcx, [rbp+57h+pExceptionObject]; pExceptionObject
0x180003179  call    _CxxThrowException_0
0x18000317f  mov     qword ptr [rbp+57h+var_68.cx], 0
0x180003187  lea     r8, [rbp+57h+var_68]; struct tagSIZE *
0x18000318b  lea     rdx, [rbp+57h+var_60]; struct Gdiplus::Graphics *
0x18000318f  mov     rcx, r15; this
0x180003192  call    ?Measure@ButtonEx@UIControls@@QEAAXAEBVGraphics@Gdiplus@@AEAUtagSIZE@@@Z; UIControls::ButtonEx::Measure(Gdiplus::Graphics const &,tagSIZE &)
0x180003197  mov     eax, [rbp+57h+var_68.cy]
0x18000319a  mov     ecx, [rbp+57h+var_68.cx]
0x18000319d  mov     [rsp+0D0h+uFlags], 16h; uFlags
0x1800031a5  mov     [rsp+0D0h+cy], eax; cy
0x1800031a9  mov     [rsp+0D0h+var_B0], ecx; cx
0x1800031ad  xor     r9d, r9d; Y
0x1800031b0  xor     r8d, r8d; X
0x1800031b3  xor     edx, edx; hWndInsertAfter
0x1800031b5  mov     rcx, [r15+8]; hWnd
0x1800031b9  call    cs:__imp_SetWindowPos
0x1800031bf  test    eax, eax
0x1800031c1  jnz     short loc_1800031CA
0x1800031c3  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x1800031c9  nop
0x1800031ca  mov     rcx, [rbp+57h+var_60]
0x1800031ce  call    cs:__imp_GdipDeleteGraphics
0x1800031d4  mov     rcx, r15
0x1800031d7  call    ?ChangeImageMirroring@ButtonEx@UIControls@@QEAAXW4EImageMirroring@12@@Z; UIControls::ButtonEx::ChangeImageMirroring(UIControls::ButtonEx::EImageMirroring)
0x1800031dc  mov     rax, r15
0x1800031df  jmp     loc_180003285
0x1800031e4  lea     rbx, [r14+468h]
0x1800031eb  mov     r9d, eax
0x1800031ee  lea     rdx, __ImageBase
0x1800031f5  mov     [rsp+0D0h+uFlags], 0A411h
0x1800031fd  mov     ecx, ds:rva dword_18008B268[rdx+r9*4]
0x180003205  mov     [rsp+0D0h+cy], ecx
0x180003209  mov     ecx, ds:rva dword_18008B260[rdx+r9*4]
0x180003211  mov     [rsp+0D0h+var_B0], ecx
0x180003215  mov     r9d, ds:rva dword_18008B278[rdx+r9*4]
0x18000321d  mov     r8d, 0FA5h
0x180003223  mov     rdx, [r14]
0x180003226  mov     rcx, rbx
0x180003229  call    ?CreateButton@ButtonEx@UIControls@@QEAAXPEAUHWND__@@IIIIIW4EImagePlacement@12@W4EHoverStyle@12@HI@Z; UIControls::ButtonEx::CreateButton(HWND__ *,uint,uint,uint,uint,uint,UIControls::ButtonEx::EImagePlacement,UIControls::ButtonEx::EHoverStyle,int,uint)
0x18000322e  mov     rcx, rbx
0x180003231  call    ?ChangeImageMirroring@ButtonEx@UIControls@@QEAAXW4EImageMirroring@12@@Z; UIControls::ButtonEx::ChangeImageMirroring(UIControls::ButtonEx::EImageMirroring)
0x180003236  jmp     short loc_180003282
0x180003238  lea     rbx, [r14+238h]
0x18000323f  mov     r9d, eax
0x180003242  lea     rdx, __ImageBase
0x180003249  mov     [rsp+0D0h+uFlags], 0A410h
0x180003251  mov     ecx, ds:rva dword_18008B270[rdx+r9*4]
0x180003259  mov     [rsp+0D0h+cy], ecx
0x18000325d  mov     ecx, ds:rva dword_18008B288[rdx+r9*4]
0x180003265  mov     r9d, ds:rva dword_18008B280[rdx+r9*4]
0x18000326d  mov     r8d, 0FA1h
0x180003273  mov     [rsp+0D0h+var_B0], ecx
0x180003277  mov     rdx, [r14]
0x18000327a  mov     rcx, rbx
0x18000327d  call    ?CreateButton@ButtonEx@UIControls@@QEAAXPEAUHWND__@@IIIIIW4EImagePlacement@12@W4EHoverStyle@12@HI@Z; UIControls::ButtonEx::CreateButton(HWND__ *,uint,uint,uint,uint,uint,UIControls::ButtonEx::EImagePlacement,UIControls::ButtonEx::EHoverStyle,int,uint)
0x180003282  mov     rax, rbx
0x180003285  mov     rcx, [rbp+57h+var_28]
0x180003289  xor     rcx, rsp; StackCookie
0x18000328c  call    __security_check_cookie
0x180003291  lea     r11, [rsp+0D0h+var_20]
0x180003299  mov     rbx, [r11+40h]
0x18000329d  mov     rsi, [r11+48h]
0x1800032a1  mov     rsp, r11
0x1800032a4  pop     r15
0x1800032a6  pop     r14
0x1800032a8  pop     r12
0x1800032aa  pop     rdi
0x1800032ab  pop     rbp
0x1800032ac  retn
```
