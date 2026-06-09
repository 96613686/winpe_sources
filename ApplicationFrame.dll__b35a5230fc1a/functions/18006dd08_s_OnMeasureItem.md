# s_OnMeasureItem

- ea: `0x18006dd08`
- end: `0x18006e0fe`
- name: `s_OnMeasureItem`
- size: `1014`
- prototype: `__int64 __fastcall(HWND hwnd)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18006c8cc`

## callees

- `0x180030aec`
- `0x180041ec0`
- `0x180043c30`
- `0x1800446fc`
- `0x1800532a8`
- `0x18006b984`
- `0x18006c42c`
- `0x18006dd08`
- `0x18006e51c`
- `0x18006e750`

## import_xrefs

- `UxTheme!CloseThemeData` at `0x18006e0cb`
- `UxTheme!CloseThemeData` at `0x18006e0cb`
- `UxTheme!OpenThemeData` at `0x18006dd8b`
- `UxTheme!OpenThemeData` at `0x18006dd8b`
- `ext-ms-win-ntuser-window-l1-1-0!FindWindowW` at `0x18006ddf5`
- `ext-ms-win-ntuser-window-l1-1-0!FindWindowW` at `0x18006ddf5`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeFont` at `0x18006dedc`
- `ext-ms-win-uxtheme-themes-l1-1-0!GetThemeFont` at `0x18006dedc`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18006de91`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!SystemParametersInfoW` at `0x18006de91`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x18006dda9`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!MonitorFromWindow` at `0x18006dda9`
- `GDI32!CreateFontIndirectW` at `0x18006df47`
- `GDI32!CreateFontIndirectW` at `0x18006df47`
- `GDI32!SelectObject` at `0x18006df6b`
- `GDI32!SelectObject` at `0x18006dfda`
- `GDI32!SelectObject` at `0x18006df6b`
- `GDI32!SelectObject` at `0x18006dfda`
- `USER32!GetWindowLongW` at `0x18006de0f`
- `USER32!GetWindowLongW` at `0x18006de0f`
- `USER32!SetWindowLongW` at `0x18006de32`
- `USER32!SetWindowLongW` at `0x18006de32`
- `USER32!GetDC` at `0x18006de5a`
- `USER32!GetDC` at `0x18006de5a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall s_OnMeasureItem(HWND hwnd, __int64 a2, char a3, unsigned int a4)
{
  int Error; // r15d
  struct ContextMenuRenderingData *ContextMenuDataForItem; // rax
  struct ContextMenuRenderingData *v8; // rsi
  _BYTE *v9; // r14
  const WCHAR *v10; // rdx
  unsigned int v11; // edi
  __int64 v12; // rdx
  HWND WindowW; // rax
  HWND v14; // rbx
  LONG WindowLongW; // eax
  HFONT v16; // rax
  HGDIOBJ v17; // rbx
  __int64 v18; // rdx
  double v19; // xmm0_8
  __int64 v20; // rdx
  HTHEME hTheme; // [rsp+78h] [rbp-88h]
  void **v24; // [rsp+90h] [rbp-70h] BYREF
  HDC hdc; // [rsp+98h] [rbp-68h]
  HWND v26; // [rsp+A0h] [rbp-60h]
  HFONT v27; // [rsp+A8h] [rbp-58h] BYREF
  LOGFONTW lf; // [rsp+B0h] [rbp-50h] BYREF
  int pvParam; // [rsp+110h] [rbp+10h] BYREF
  _BYTE v30[220]; // [rsp+114h] [rbp+14h] BYREF
  __int128 v31; // [rsp+1F0h] [rbp+F0h]
  __int128 v32; // [rsp+200h] [rbp+100h]
  __int128 v33; // [rsp+210h] [rbp+110h]
  __int128 v34; // [rsp+220h] [rbp+120h]
  _OWORD v35[14]; // [rsp+230h] [rbp+130h]

  Error = -2147418113;
  ContextMenuDataForItem = ImmersiveContextMenuHelper::GetContextMenuDataForItem(
                             hwnd,
                             *(HWND *)(a2 + 24),
                             *(unsigned int *)(a2 + 8),
                             a4);
  v8 = ContextMenuDataForItem;
  if ( ContextMenuDataForItem )
  {
    v9 = (char *)ContextMenuDataForItem + 69;
    if ( *((_BYTE *)ContextMenuDataForItem + 68) )
    {
      v10 = L"DarkMode_ImmersiveStart::Menu";
    }
    else
    {
      v10 = L"LightMode_ImmersiveStart::Menu";
      if ( !*v9 )
        v10 = L"ImmersiveStart::Menu";
    }
    hTheme = OpenThemeData(0, v10);
    if ( hTheme )
    {
      v11 = 2;
      if ( !MonitorFromWindow(hwnd, 2u) )
      {
LABEL_49:
        CloseThemeData(hTheme);
        return (unsigned int)Error;
      }
      if ( *((_DWORD *)v8 + 6) == 2048 )
      {
        if ( *v9 || (v12 = 7, (*((_BYTE *)v8 + 56) & 4) != 0) )
          v12 = 9;
        *(_DWORD *)(a2 + 16) = DPIToPPIHelpers::ScaleByType(
                                 *((unsigned int *)v8 + 15),
                                 v12,
                                 hwnd,
                                 *((unsigned int *)v8 + 16));
        goto LABEL_49;
      }
      WindowW = FindWindowW(L"#32768", 0);
      v14 = WindowW;
      if ( !WindowW )
      {
LABEL_39:
        if ( (*((_BYTE *)v8 + 56) & 1) != 0 )
        {
          if ( *v9 || (v20 = 2, (*((_BYTE *)v8 + 56) & 4) != 0) )
            v20 = 6;
          *(_DWORD *)(a2 + 16) += DPIToPPIHelpers::ScaleByType(
                                    *((unsigned int *)v8 + 15),
                                    v20,
                                    hwnd,
                                    *((unsigned int *)v8 + 16));
        }
        if ( (*((_BYTE *)v8 + 56) & 2) != 0 )
        {
          if ( *v9 || (*((_BYTE *)v8 + 56) & 4) != 0 )
            v11 = 6;
          *(_DWORD *)(a2 + 16) += DPIToPPIHelpers::ScaleByType(
                                    *((unsigned int *)v8 + 15),
                                    v11,
                                    hwnd,
                                    *((unsigned int *)v8 + 16));
        }
        goto LABEL_49;
      }
      WindowLongW = GetWindowLongW(WindowW, -20);
      if ( a3 && (WindowLongW & 0x400000) == 0 )
        SetWindowLongW(v14, -20, WindowLongW | 0x400000);
      v24 = &Microsoft::WRL::Wrappers::ClientDC::`vftable';
      v26 = v14;
      hdc = GetDC(v14);
      if ( !hdc
        || (memset_0(v30, 0, 0x1F4u), pvParam = 504, !SystemParametersInfoW(0x29u, 0x1F8u, &pvParam, 0))
        && (Error = ResultFromKnownLastError(), Error < 0) )
      {
LABEL_38:
        Microsoft::WRL::Wrappers::ClientDC::~ClientDC((Microsoft::WRL::Wrappers::ClientDC *)&v24);
        goto LABEL_39;
      }
      memset_0(&lf, 0, sizeof(lf));
      if ( GetThemeFont(hTheme, 0, 27, 0, 210, &lf) < 0 )
      {
        *(_OWORD *)&lf.lfHeight = v31;
        *(_OWORD *)&lf.lfWeight = v32;
        *(_OWORD *)&lf.lfFaceName[2] = v33;
        *(_OWORD *)&lf.lfFaceName[10] = v34;
        *(_OWORD *)&lf.lfFaceName[18] = v35[0];
        *(_OWORD *)&lf.lfFaceName[24] = *(_OWORD *)((char *)v35 + 12);
      }
      else
      {
        if ( (int)v31 <= 0 )
        {
          if ( (int)v31 >= lf.lfHeight )
            goto LABEL_27;
        }
        else if ( (int)v31 <= lf.lfHeight )
        {
          goto LABEL_27;
        }
        lf.lfHeight = v31;
      }
LABEL_27:
      v16 = CreateFontIndirectW(&lf);
      v27 = v16;
      if ( v16 )
      {
        v17 = SelectObject(hdc, v16);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_EnsureCount(v8);
        Error = DPIToPPIHelpers::GetThemeTextExtentPPI(hwnd, *((unsigned int *)v8 + 15), (char *)v8 + 64, hTheme, hdc);
        SelectObject(hdc, v17);
        v11 = 2;
      }
      else
      {
        Error = -2147467259;
      }
      CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(&v27);
      if ( Error >= 0 )
      {
        *(_DWORD *)(a2 + 12) = DPIToPPIHelpers::ScaleByType(
                                 *((unsigned int *)v8 + 15),
                                 93,
                                 hwnd,
                                 *((unsigned int *)v8 + 16));
        if ( (*((_BYTE *)v8 + 56) & 4) != 0 )
        {
          v18 = 36;
        }
        else
        {
          if ( *v9 )
            v19 = DOUBLE_24_0;
          else
            v19 = DOUBLE_16_0;
          v18 = (unsigned int)(int)v19;
        }
        *(_DWORD *)(a2 + 16) = DPIToPPIHelpers::ScaleByType(
                                 *((unsigned int *)v8 + 15),
                                 v18,
                                 hwnd,
                                 *((unsigned int *)v8 + 16));
      }
      goto LABEL_38;
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x18006dd08  mov     [rsp-8+arg_10], rbx
0x18006dd0d  push    rbp
0x18006dd0e  push    rsi
0x18006dd0f  push    rdi
0x18006dd10  push    r12
0x18006dd12  push    r13
0x18006dd14  push    r14
0x18006dd16  push    r15
0x18006dd18  lea     rbp, [rsp-220h]
0x18006dd20  sub     rsp, 320h
0x18006dd27  mov     rax, cs:__security_cookie
0x18006dd2e  xor     rax, rsp
0x18006dd31  mov     [rbp+250h+var_40], rax
0x18006dd38  mov     [rsp+350h+var_2E0], r8b
0x18006dd3d  mov     r13, rdx
0x18006dd40  mov     r12, rcx
0x18006dd43  mov     r15d, 8000FFFFh
0x18006dd49  mov     r8d, [rdx+8]; unsigned __int64
0x18006dd4d  mov     rdx, [rdx+18h]; HWND
0x18006dd51  call    ?GetContextMenuDataForItem@ImmersiveContextMenuHelper@@YAPEAUContextMenuRenderingData@@PEAUHWND__@@_KI@Z; ImmersiveContextMenuHelper::GetContextMenuDataForItem(HWND__ *,unsigned __int64,uint)
0x18006dd56  mov     rsi, rax
0x18006dd59  xor     ebx, ebx
0x18006dd5b  test    rax, rax
0x18006dd5e  jz      loc_18006E0D1
0x18006dd64  lea     r14, [rax+45h]
0x18006dd68  cmp     [rax+44h], bl
0x18006dd6b  jz      short loc_18006DD76
0x18006dd6d  lea     rdx, aDarkmodeImmers; "DarkMode_ImmersiveStart::Menu"
0x18006dd74  jmp     short loc_18006DD89
0x18006dd76  cmp     [r14], bl
0x18006dd79  lea     rdx, aLightmodeImmer; "LightMode_ImmersiveStart::Menu"
0x18006dd80  jnz     short loc_18006DD89
0x18006dd82  lea     rdx, aImmersivestart; "ImmersiveStart::Menu"
0x18006dd89  xor     ecx, ecx; hwnd
0x18006dd8b  call    cs:__imp_OpenThemeData
0x18006dd91  mov     [rsp+350h+hTheme], rax
0x18006dd96  test    rax, rax
0x18006dd99  jz      loc_18006E0D1
0x18006dd9f  mov     edi, 2
0x18006dda4  mov     edx, edi; dwFlags
0x18006dda6  mov     rcx, r12; hwnd
0x18006dda9  call    cs:__imp_MonitorFromWindow
0x18006ddaf  test    rax, rax
0x18006ddb2  jz      loc_18006E0C6
0x18006ddb8  cmp     dword ptr [rsi+18h], 800h
0x18006ddbf  jnz     short loc_18006DDEC
0x18006ddc1  cmp     [r14], bl
0x18006ddc4  jnz     short loc_18006DDCF
0x18006ddc6  test    byte ptr [rsi+38h], 4
0x18006ddca  lea     edx, [rdi+5]
0x18006ddcd  jz      short loc_18006DDD4
0x18006ddcf  mov     edx, 9
0x18006ddd4  mov     r9d, [rsi+40h]
0x18006ddd8  mov     r8, r12
0x18006dddb  mov     ecx, [rsi+3Ch]
0x18006ddde  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006dde3  mov     [r13+10h], eax
0x18006dde7  jmp     loc_18006E0C6
0x18006ddec  xor     edx, edx; lpWindowName
0x18006ddee  lea     rcx, a32768; "#32768"
0x18006ddf5  call    cs:__imp_FindWindowW
0x18006ddfb  mov     rbx, rax
0x18006ddfe  test    rax, rax
0x18006de01  jz      loc_18006E06F
0x18006de07  mov     edx, 0FFFFFFECh; nIndex
0x18006de0c  mov     rcx, rax; hWnd
0x18006de0f  call    cs:__imp_GetWindowLongW
0x18006de15  cmp     [rsp+350h+var_2E0], 0
0x18006de1a  jz      short loc_18006DE38
0x18006de1c  mov     ecx, 400000h
0x18006de21  test    ecx, eax
0x18006de23  jnz     short loc_18006DE38
0x18006de25  or      eax, ecx
0x18006de27  mov     r8d, eax; dwNewLong
0x18006de2a  mov     edx, 0FFFFFFECh; nIndex
0x18006de2f  mov     rcx, rbx; hWnd
0x18006de32  call    cs:__imp_SetWindowLongW
0x18006de38  xorps   xmm0, xmm0
0x18006de3b  movdqu  [rbp+250h+var_2D0], xmm0
0x18006de40  mov     [rbp+250h+hdc], 0
0x18006de48  lea     rax, ??_7ClientDC@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::ClientDC::`vftable'
0x18006de4f  mov     [rbp+250h+var_2C0], rax
0x18006de53  mov     [rbp+250h+var_2B0], rbx
0x18006de57  mov     rcx, rbx; hWnd
0x18006de5a  call    cs:__imp_GetDC
0x18006de60  mov     [rbp+250h+hdc], rax
0x18006de64  test    rax, rax
0x18006de67  jz      loc_18006E066
0x18006de6d  xor     edx, edx; Val
0x18006de6f  mov     r8d, 1F4h; Size
0x18006de75  lea     rcx, [rbp+250h+var_23C]; void *
0x18006de79  call    memset_0
0x18006de7e  mov     edx, 1F8h; uiParam
0x18006de83  mov     [rbp+250h+pvParam], edx
0x18006de86  xor     r9d, r9d; fWinIni
0x18006de89  lea     r8, [rbp+250h+pvParam]; pvParam
0x18006de8d  lea     ecx, [r9+29h]; uiAction
0x18006de91  call    cs:__imp_SystemParametersInfoW
0x18006de97  test    eax, eax
0x18006de99  jnz     short loc_18006DEAB
0x18006de9b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006dea0  mov     r15d, eax
0x18006dea3  test    eax, eax
0x18006dea5  js      loc_18006E066
0x18006deab  xor     edx, edx; Val
0x18006dead  lea     r8d, [rdx+5Ch]; Size
0x18006deb1  lea     rcx, [rbp+250h+lf]; void *
0x18006deb5  call    memset_0
0x18006deba  lea     rax, [rbp+250h+lf]
0x18006debe  mov     [rsp+350h+pFont], rax; pFont
0x18006dec3  mov     [rsp+350h+iPropId], 0D2h; iPropId
0x18006decb  xor     r9d, r9d; iStateId
0x18006dece  xor     edx, edx; hdc
0x18006ded0  lea     r8d, [r9+1Bh]; iPartId
0x18006ded4  mov     r15, [rsp+350h+hTheme]
0x18006ded9  mov     rcx, r15; hTheme
0x18006dedc  call    cs:__imp_GetThemeFont
0x18006dee2  test    eax, eax
0x18006dee4  js      short loc_18006DF01
0x18006dee6  mov     eax, dword ptr [rbp+250h+var_160]
0x18006deec  test    eax, eax
0x18006deee  jle     short loc_18006DEF7
0x18006def0  cmp     eax, [rbp+250h+lf.lfHeight]
0x18006def3  jle     short loc_18006DF43
0x18006def5  jmp     short loc_18006DEFC
0x18006def7  cmp     eax, [rbp+250h+lf.lfHeight]
0x18006defa  jge     short loc_18006DF43
0x18006defc  mov     [rbp+250h+lf.lfHeight], eax
0x18006deff  jmp     short loc_18006DF43
0x18006df01  movaps  xmm0, [rbp+250h+var_160]
0x18006df08  movaps  xmmword ptr [rbp+250h+lf.lfHeight], xmm0
0x18006df0c  movaps  xmm1, [rbp+250h+var_150]
0x18006df13  movaps  xmmword ptr [rbp+250h+lf.lfWeight], xmm1
0x18006df17  movaps  xmm0, [rbp+250h+var_140]
0x18006df1e  movaps  xmmword ptr [rbp+250h+lf.lfFaceName+4], xmm0
0x18006df22  movaps  xmm1, [rbp+250h+var_130]
0x18006df29  movaps  xmmword ptr [rbp+250h+lf.lfFaceName+14h], xmm1
0x18006df2d  movaps  xmm0, [rbp+250h+var_120]
0x18006df34  movaps  xmmword ptr [rbp+250h+lf.lfFaceName+24h], xmm0
0x18006df38  movups  xmm1, [rbp+250h+var_120+0Ch]
0x18006df3f  movups  xmmword ptr [rbp+250h+lf.lfFaceName+30h], xmm1
0x18006df43  lea     rcx, [rbp+250h+lf]; lplf
0x18006df47  call    cs:__imp_CreateFontIndirectW
0x18006df4d  mov     [rbp+250h+var_2A8], rax
0x18006df51  test    rax, rax
0x18006df54  jnz     short loc_18006DF61
0x18006df56  mov     r15d, 80004005h
0x18006df5c  jmp     loc_18006DFE5
0x18006df61  mov     rdi, [rbp+250h+hdc]
0x18006df65  mov     rdx, rax; h
0x18006df68  mov     rcx, rdi; hdc
0x18006df6b  call    cs:__imp_SelectObject
0x18006df71  mov     rbx, rax
0x18006df74  mov     rcx, rsi
0x18006df77  call    ?_EnsureCount@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_EnsureCount(void)
0x18006df7c  lea     r8, [rsi+40h]
0x18006df80  lea     rax, [rbp+250h+var_2D0]
0x18006df84  mov     [rsp+350h+var_2F0], rax
0x18006df89  mov     [rsp+350h+var_2F8], 0
0x18006df92  mov     [rsp+350h+var_300], 0
0x18006df9b  mov     [rsp+350h+var_308], 24h ; '$'
0x18006dfa3  mov     eax, [rsi+8]
0x18006dfa6  mov     [rsp+350h+var_310], eax
0x18006dfaa  mov     rax, [rsi]
0x18006dfad  mov     [rsp+350h+var_318], rax
0x18006dfb2  mov     [rsp+350h+var_320], 1
0x18006dfba  mov     rax, [rbp+250h+hdc]
0x18006dfbe  mov     qword ptr [rsp+350h+iPropId], rax
0x18006dfc3  mov     r9, r15
0x18006dfc6  mov     edx, [rsi+3Ch]
0x18006dfc9  mov     rcx, r12
0x18006dfcc  call    ?GetThemeTextExtentPPI@DPIToPPIHelpers@@YAJPEAUHWND__@@W4ScaleType@1@PEAIPEAXPEAUHDC__@@HHPEBGHKPEAU_DTTOPTS@@PEAUtagRECT@@7@Z; DPIToPPIHelpers::GetThemeTextExtentPPI(HWND__ *,DPIToPPIHelpers::ScaleType,uint *,void *,HDC__ *,int,int,ushort const *,int,ulong,_DTTOPTS *,tagRECT *,tagRECT *)
0x18006dfd1  mov     r15d, eax
0x18006dfd4  mov     rdx, rbx; h
0x18006dfd7  mov     rcx, rdi; hdc
0x18006dfda  call    cs:__imp_SelectObject
0x18006dfe0  mov     edi, 2
0x18006dfe5  lea     rcx, [rbp+250h+var_2A8]
0x18006dfe9  call    ??1?$CAutoHandle@PEAUHBITMAP__@@@@QEAA@XZ; CAutoHandle<HBITMAP__ *>::~CAutoHandle<HBITMAP__ *>(void)
0x18006dfee  nop
0x18006dfef  test    r15d, r15d
0x18006dff2  js      short loc_18006E066
0x18006dff4  mov     ebx, dword ptr [rbp+250h+var_2D0+0Ch]
0x18006dff7  sub     ebx, dword ptr [rbp+250h+var_2D0+4]
0x18006dffa  mov     eax, 0Ch
0x18006dfff  cmp     ebx, 0Dh
0x18006e002  cmovz   ebx, eax
0x18006e005  mov     r9d, [rsi+40h]
0x18006e009  mov     r8, r12
0x18006e00c  mov     edx, cs:dword_18007DA70
0x18006e012  mov     ecx, [rsi+3Ch]
0x18006e015  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006e01a  mov     ecx, eax
0x18006e01c  mov     eax, dword ptr [rbp+250h+var_2D0+8]
0x18006e01f  sub     eax, dword ptr [rbp+250h+var_2D0]
0x18006e022  add     ecx, eax
0x18006e024  mov     [r13+0Ch], ecx
0x18006e028  test    byte ptr [rsi+38h], 4
0x18006e02c  jz      short loc_18006E035
0x18006e02e  mov     edx, 24h ; '$'
0x18006e033  jmp     short loc_18006E051
0x18006e035  cmp     byte ptr [r14], 0
0x18006e039  jz      short loc_18006E045
0x18006e03b  movsd   xmm0, cs:__real@4038000000000000
0x18006e043  jmp     short loc_18006E04D
0x18006e045  movsd   xmm0, cs:__real@4030000000000000
0x18006e04d  cvttsd2si edx, xmm0
0x18006e051  mov     r9d, [rsi+40h]
0x18006e055  mov     r8, r12
0x18006e058  mov     ecx, [rsi+3Ch]
0x18006e05b  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006e060  add     eax, ebx
0x18006e062  mov     [r13+10h], eax
0x18006e066  lea     rcx, [rbp+250h+var_2C0]; this
0x18006e06a  call    ??1ClientDC@Wrappers@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Wrappers::ClientDC::~ClientDC(void)
0x18006e06f  mov     ebx, 6
0x18006e074  test    byte ptr [rsi+38h], 1
0x18006e078  jz      short loc_18006E09D
0x18006e07a  cmp     byte ptr [r14], 0
0x18006e07e  jnz     short loc_18006E088
0x18006e080  test    byte ptr [rsi+38h], 4
0x18006e084  mov     edx, edi
0x18006e086  jz      short loc_18006E08A
0x18006e088  mov     edx, ebx
0x18006e08a  mov     r9d, [rsi+40h]
0x18006e08e  mov     r8, r12
0x18006e091  mov     ecx, [rsi+3Ch]
0x18006e094  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006e099  add     [r13+10h], eax
0x18006e09d  test    [rsi+38h], dil
0x18006e0a1  jz      short loc_18006E0C6
0x18006e0a3  cmp     byte ptr [r14], 0
0x18006e0a7  jnz     short loc_18006E0AF
0x18006e0a9  test    byte ptr [rsi+38h], 4
0x18006e0ad  jz      short loc_18006E0B1
0x18006e0af  mov     edi, ebx
0x18006e0b1  mov     r9d, [rsi+40h]
0x18006e0b5  mov     r8, r12
0x18006e0b8  mov     edx, edi
0x18006e0ba  mov     ecx, [rsi+3Ch]
0x18006e0bd  call    ?ScaleByType@DPIToPPIHelpers@@YAHW4ScaleType@1@HPEAUHWND__@@HW4ScaleModifier@1@@Z; DPIToPPIHelpers::ScaleByType(DPIToPPIHelpers::ScaleType,int,HWND__ *,int,DPIToPPIHelpers::ScaleModifier)
0x18006e0c2  add     [r13+10h], eax
0x18006e0c6  mov     rcx, [rsp+350h+hTheme]; hTheme
0x18006e0cb  call    cs:__imp_CloseThemeData
0x18006e0d1  mov     eax, r15d
0x18006e0d4  mov     rcx, [rbp+250h+var_40]
0x18006e0db  xor     rcx, rsp; StackCookie
0x18006e0de  call    __security_check_cookie
0x18006e0e3  mov     rbx, [rsp+350h+arg_10]
0x18006e0eb  add     rsp, 320h
0x18006e0f2  pop     r15
0x18006e0f4  pop     r14
0x18006e0f6  pop     r13
0x18006e0f8  pop     r12
0x18006e0fa  pop     rdi
0x18006e0fb  pop     rsi
0x18006e0fc  pop     rbp
0x18006e0fd  retn
```
