# CShutdownBlockingApp::RuntimeClassInitialize(tagSHUTDOWN_BLOCK_DESCRIPTION *,uchar,DEVICE_SCALE_FACTOR)

- ea: `0x18001684c`
- end: `0x180016c23`
- name: `?RuntimeClassInitialize@CShutdownBlockingApp@@QEAAJPEAUtagSHUTDOWN_BLOCK_DESCRIPTION@@EW4DEVICE_SCALE_FACTOR@@@Z`
- size: `983`
- prototype: `__int64 __fastcall(CShutdownBlockingApp *__hidden this, struct tagSHUTDOWN_BLOCK_DESCRIPTION *, unsigned __int8, enum DEVICE_SCALE_FACTOR)`
- caller_count: `1`
- callee_count: `10`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180015da0`

## callees

- `0x180004c00`
- `0x18000df10`
- `0x180015b5c`
- `0x180016638`
- `0x18001684c`
- `0x180016c30`
- `0x180016eb8`
- `0x18005d488`
- `0x1800848d0`
- `0x18009d010`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800168a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800168f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800168a9`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800168f1`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800168be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016903`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x1800168be`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180016903`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016a6a`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x180016a6a`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180016b62`
- `SHCORE!CreateRandomAccessStreamOverStream` at `0x180016b62`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1800169a4`
- `ext-ms-win-gdi-dc-l1-2-0!GetObjectW` at `0x1800169a4`
- `ext-ms-win-ntuser-gui-l1-1-0!GetIconInfo` at `0x180016930`
- `ext-ms-win-ntuser-gui-l1-1-0!GetIconInfo` at `0x180016930`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016a13`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016a1d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016ba9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016bd3`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016a13`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016a1d`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016ba9`
- `ext-ms-win-rtcore-gdi-object-l1-1-0!DeleteObject` at `0x180016bd3`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
__int64 __fastcall CShutdownBlockingApp::RuntimeClassInitialize(
        CShutdownBlockingApp *this,
        struct tagSHUTDOWN_BLOCK_DESCRIPTION *a2,
        char a3,
        enum DEVICE_SCALE_FACTOR a4)
{
  const WCHAR *v7; // r15
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rsi
  HSTRING *v10; // rbx
  HRESULT String; // ebx
  HICON v12; // r14
  HBITMAP v13; // rdi
  int v14; // edx
  int v15; // r8d
  HBITMAP hbmColor; // rcx
  int HaveAlpha; // ebx
  float v18; // xmm0_4
  unsigned int v19; // esi
  int v20; // eax
  HRESULT Instance; // ebx
  enum WICBitmapAlphaChannelOption v22; // r8d
  __int64 v23; // r8
  __int64 (__fastcall ***v24)(_QWORD, GUID *, tagSIZE *); // rcx
  struct IWICBitmapSource *v25; // rcx
  struct IWICImagingFactory *v26; // rcx
  int v27; // eax
  tagSIZE v28; // rcx
  tagSIZE v29; // rcx
  __int64 v31; // rdx
  int ppv; // [rsp+20h] [rbp-49h]
  int ppva; // [rsp+20h] [rbp-49h]
  HBITMAP v34; // [rsp+30h] [rbp-39h] BYREF
  __int64 (__fastcall ***v35)(_QWORD, GUID *, tagSIZE *); // [rsp+38h] [rbp-31h] BYREF
  struct IWICBitmapSource *v36[2]; // [rsp+40h] [rbp-29h] BYREF
  ICONINFO piconinfo; // [rsp+50h] [rbp-19h] BYREF
  _OWORD pv[5]; // [rsp+70h] [rbp+7h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]
  tagSIZE v40; // [rsp+D0h] [rbp+67h] BYREF
  struct IWICImagingFactory *v41; // [rsp+D8h] [rbp+6Fh] BYREF
  bool v42; // [rsp+E0h] [rbp+77h] BYREF

  *((_BYTE *)this + 88) = a3;
  *((_DWORD *)this + 23) = *(_DWORD *)a2;
  v7 = (const WCHAR *)((char *)a2 + 538);
  v8 = -1;
  v9 = -1;
  do
    ++v9;
  while ( v7[v9] );
  if ( v9 > 0xFFFFFFFF )
  {
    String = -2147024362;
    goto LABEL_49;
  }
  v10 = (HSTRING *)((char *)this + 64);
  WindowsDeleteString(*((HSTRING *)this + 8));
  *v10 = 0;
  String = WindowsCreateString(v7, v9, v10);
  if ( String < 0 )
  {
LABEL_49:
    v31 = 27;
    goto LABEL_50;
  }
  do
    ++v8;
  while ( *((_WORD *)a2 + v8 + 8) );
  if ( v8 > 0xFFFFFFFF )
  {
    String = -2147024362;
    goto LABEL_47;
  }
  WindowsDeleteString(*((HSTRING *)this + 9));
  *((_QWORD *)this + 9) = 0;
  String = WindowsCreateString((PCNZWCH)a2 + 8, v8, (HSTRING *)this + 9);
  if ( String < 0 )
  {
LABEL_47:
    v31 = 28;
LABEL_50:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v31,
      (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\shutdownblockingapp.cpp",
      (const char *)(unsigned int)String,
      ppv);
    return (unsigned int)String;
  }
  v12 = (HICON)*((_QWORD *)a2 + 1);
  v13 = 0;
  v34 = 0;
  memset(&piconinfo, 0, sizeof(piconinfo));
  if ( !GetIconInfo(v12, &piconinfo) && (int)ResultFromKnownLastError() < 0 )
    goto LABEL_43;
  LOBYTE(v14) = 0;
  v42 = 0;
  hbmColor = piconinfo.hbmColor;
  if ( piconinfo.hbmColor )
  {
    HaveAlpha = _DoesBitmapHaveAlpha(piconinfo.hbmColor, &v42);
    if ( HaveAlpha < 0 )
      goto LABEL_22;
    hbmColor = piconinfo.hbmColor;
    LOBYTE(v14) = v42;
  }
  v18 = (float)((float)a4 * 32.0) / 100.0;
  v19 = (int)v18;
  if ( (_BYTE)v14 )
  {
    memset(pv, 0, 32);
    if ( GetObjectW(hbmColor, 32, pv) )
    {
      HaveAlpha = 0;
    }
    else
    {
      HaveAlpha = ResultFromKnownLastError();
      if ( HaveAlpha < 0 )
        goto LABEL_22;
    }
    if ( __PAIR64__(DWORD1(pv[0]), v19) == *(_QWORD *)((char *)pv + 4) )
    {
      v13 = piconinfo.hbmColor;
      v34 = piconinfo.hbmColor;
      piconinfo.hbmColor = 0;
      goto LABEL_24;
    }
    v20 = _ScaleBitmap(piconinfo.hbmColor, v19, &v34);
  }
  else
  {
    v40.cx = (int)v18;
    v40.cy = (int)v18;
    v20 = CreateBitmapFromIcon(v12, v14, v15, &v40, &v34);
  }
  v13 = v34;
  HaveAlpha = v20;
LABEL_22:
  if ( piconinfo.hbmColor )
    DeleteObject(piconinfo.hbmColor);
LABEL_24:
  DeleteObject(piconinfo.hbmMask);
  if ( HaveAlpha >= 0 )
  {
    v40 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v40);
    v40 = 0;
    v41 = 0;
    Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v41);
    Instance = CoCreateInstance(
                 &CLSID_WICImagingFactory2,
                 0,
                 1u,
                 &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
                 (LPVOID *)&v41);
    if ( Instance >= 0 )
    {
      v36[0] = 0;
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(v36);
      Instance = ConvertHBITMAPToWICBitmap(v41, v13, v22, v36);
      if ( Instance >= 0 )
      {
        v35 = 0;
        Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(&v35);
        *(GUID *)&piconinfo.fIcon = GUID_WICPixelFormat32bppBGRA;
        ppva = 1;
        Instance = GetStreamOfWICBitmapSourceWithOptions(v41, v36[0], v23, &piconinfo);
        if ( Instance >= 0 )
          Instance = (**v35)(v35, &GUID_0000000c_0000_0000_c000_000000000046, &v40);
        v24 = v35;
        if ( v35 )
        {
          v35 = 0;
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, tagSIZE *)))(*v24)[2])(v24);
        }
      }
      v25 = v36[0];
      if ( v36[0] )
      {
        v36[0] = 0;
        ((void (__fastcall *)(struct IWICBitmapSource *))v25->lpVtbl->Release)(v25);
      }
    }
    v26 = v41;
    if ( v41 )
    {
      v41 = 0;
      ((void (__fastcall *)(struct IWICImagingFactory *))v26->lpVtbl->Release)(v26);
    }
    if ( Instance >= 0 )
    {
      Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease((char *)this + 80);
      v27 = ((__int64 (__fastcall *)(_QWORD, _QWORD, _QWORD, _QWORD))CreateRandomAccessStreamOverStream)(
              v40,
              0,
              &GUID_905a0fe1_bc53_11df_8c49_001e4fc686da,
              (char *)this + 80);
      String = v27;
      if ( v27 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x27,
          (unsigned int)"pcshell\\shell\\auth\\authux\\controller\\lib\\shutdownblockingapp.cpp",
          (const char *)(unsigned int)v27,
          ppva);
        v28 = v40;
        if ( v40 )
        {
          v40 = 0;
          (*(void (__fastcall **)(tagSIZE))(**(_QWORD **)&v28 + 16LL))(v28);
        }
        if ( v13 )
          DeleteObject(v13);
        return (unsigned int)String;
      }
    }
    v29 = v40;
    if ( v40 )
    {
      v40 = 0;
      (*(void (__fastcall **)(tagSIZE))(**(_QWORD **)&v29 + 16LL))(v29);
    }
  }
LABEL_43:
  if ( v13 )
    DeleteObject(v13);
  return 0;
}

```

## disassembly

```asm
0x18001684c  mov     [rsp-8+arg_18], rbx
0x180016851  push    rbp
0x180016852  push    rsi
0x180016853  push    rdi
0x180016854  push    r12
0x180016856  push    r13
0x180016858  push    r14
0x18001685a  push    r15
0x18001685c  lea     rbp, [rsp-27h]
0x180016861  sub     rsp, 90h
0x180016868  mov     r12d, r9d
0x18001686b  mov     r14, rdx
0x18001686e  mov     r13, rcx
0x180016871  mov     [rcx+58h], r8b
0x180016875  mov     eax, [rdx]
0x180016877  mov     [rcx+5Ch], eax
0x18001687a  lea     r15, [rdx+21Ah]
0x180016881  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180016885  mov     rsi, rdi
0x180016888  xor     eax, eax
0x18001688a  inc     rsi
0x18001688d  cmp     [r15+rsi*2], ax
0x180016892  jnz     short loc_18001688A
0x180016894  mov     eax, 0FFFFFFFFh
0x180016899  cmp     rsi, rax
0x18001689c  ja      loc_180016BE9
0x1800168a2  lea     rbx, [rcx+40h]
0x1800168a6  mov     rcx, [rbx]; string
0x1800168a9  call    cs:__imp_WindowsDeleteString
0x1800168af  mov     qword ptr [rbx], 0
0x1800168b6  mov     edx, esi; length
0x1800168b8  mov     r8, rbx; string
0x1800168bb  mov     rcx, r15; sourceString
0x1800168be  call    cs:__imp_WindowsCreateString
0x1800168c4  mov     ebx, eax
0x1800168c6  xor     r15d, r15d
0x1800168c9  test    eax, eax
0x1800168cb  js      loc_180016BEE
0x1800168d1  inc     rdi
0x1800168d4  cmp     [r14+rdi*2+10h], r15w
0x1800168da  jnz     short loc_1800168D1
0x1800168dc  mov     eax, 0FFFFFFFFh
0x1800168e1  cmp     rdi, rax
0x1800168e4  ja      loc_180016BDD
0x1800168ea  lea     rbx, [r13+48h]
0x1800168ee  mov     rcx, [rbx]; string
0x1800168f1  call    cs:__imp_WindowsDeleteString
0x1800168f7  mov     [rbx], r15
0x1800168fa  mov     edx, edi; length
0x1800168fc  mov     r8, rbx; string
0x1800168ff  lea     rcx, [r14+10h]; sourceString
0x180016903  call    cs:__imp_WindowsCreateString
0x180016909  mov     ebx, eax
0x18001690b  test    eax, eax
0x18001690d  js      loc_180016BE2
0x180016913  mov     r14, [r14+8]
0x180016917  mov     rdi, r15
0x18001691a  mov     [rbp+57h+var_90], r15
0x18001691e  xorps   xmm0, xmm0
0x180016921  movups  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x180016925  movups  xmmword ptr [rbp+57h+piconinfo.hbmMask], xmm0
0x180016929  lea     rdx, [rbp+57h+piconinfo]; piconinfo
0x18001692d  mov     rcx, r14; hIcon
0x180016930  call    cs:__imp_GetIconInfo
0x180016936  test    eax, eax
0x180016938  jnz     short loc_180016947
0x18001693a  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18001693f  test    eax, eax
0x180016941  js      loc_180016BCB
0x180016947  mov     dl, r15b
0x18001694a  mov     [rbp+57h+arg_10], dl
0x18001694d  mov     rcx, [rbp+57h+piconinfo.hbmColor]; hbm
0x180016951  test    rcx, rcx
0x180016954  jz      short loc_180016970
0x180016956  lea     rdx, [rbp+57h+arg_10]; bool *
0x18001695a  call    ?_DoesBitmapHaveAlpha@@YAJPEAUHBITMAP__@@PEA_N@Z; _DoesBitmapHaveAlpha(HBITMAP__ *,bool *)
0x18001695f  mov     ebx, eax
0x180016961  test    eax, eax
0x180016963  js      loc_180016A0A
0x180016969  mov     rcx, [rbp+57h+piconinfo.hbmColor]; h
0x18001696d  mov     dl, [rbp+57h+arg_10]; int
0x180016970  xorps   xmm0, xmm0
0x180016973  cvtsi2ss xmm0, r12
0x180016978  mulss   xmm0, cs:__real@42000000
0x180016980  divss   xmm0, cs:__real@42c80000
0x180016988  cvttss2si esi, xmm0
0x18001698c  test    dl, dl
0x18001698e  jz      short loc_1800169E9
0x180016990  xorps   xmm0, xmm0
0x180016993  movups  [rbp+57h+pv], xmm0
0x180016997  movups  [rbp+57h+var_40], xmm0
0x18001699b  lea     r8, [rbp+57h+pv]; pv
0x18001699f  mov     edx, 20h ; ' '; c
0x1800169a4  call    cs:__imp_GetObjectW
0x1800169aa  test    eax, eax
0x1800169ac  jz      short loc_1800169B3
0x1800169ae  mov     ebx, r15d
0x1800169b1  jmp     short loc_1800169BE
0x1800169b3  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800169b8  mov     ebx, eax
0x1800169ba  test    eax, eax
0x1800169bc  js      short loc_180016A0A
0x1800169be  mov     eax, dword ptr [rbp+57h+pv+4]
0x1800169c1  cmp     eax, dword ptr [rbp+57h+pv+8]
0x1800169c4  jnz     short loc_1800169D8
0x1800169c6  cmp     esi, eax
0x1800169c8  jnz     short loc_1800169D8
0x1800169ca  mov     rdi, [rbp+57h+piconinfo.hbmColor]
0x1800169ce  mov     [rbp+57h+var_90], rdi
0x1800169d2  mov     [rbp+57h+piconinfo.hbmColor], r15
0x1800169d6  jmp     short loc_180016A19
0x1800169d8  lea     r8, [rbp+57h+var_90]; HBITMAP *
0x1800169dc  mov     edx, esi; unsigned int
0x1800169de  mov     rcx, [rbp+57h+piconinfo.hbmColor]; HBITMAP
0x1800169e2  call    ?_ScaleBitmap@@YAJPEAUHBITMAP__@@IPEAPEAU1@@Z; _ScaleBitmap(HBITMAP__ *,uint,HBITMAP__ * *)
0x1800169e7  jmp     short loc_180016A04
0x1800169e9  mov     [rbp+57h+arg_0.cx], esi
0x1800169ec  mov     [rbp+57h+arg_0.cy], esi
0x1800169ef  lea     rax, [rbp+57h+var_90]
0x1800169f3  mov     [rsp+0C0h+ppv], rax; HBITMAP *
0x1800169f8  lea     r9, [rbp+57h+arg_0]; struct tagSIZE *
0x1800169fc  mov     rcx, r14; hicon
0x1800169ff  call    ?CreateBitmapFromIcon@@YAJPEAUHICON__@@HHPEBUtagSIZE@@PEAPEAUHBITMAP__@@@Z; CreateBitmapFromIcon(HICON__ *,int,int,tagSIZE const *,HBITMAP__ * *)
0x180016a04  mov     rdi, [rbp+57h+var_90]
0x180016a08  mov     ebx, eax
0x180016a0a  mov     rcx, [rbp+57h+piconinfo.hbmColor]; ho
0x180016a0e  test    rcx, rcx
0x180016a11  jz      short loc_180016A19
0x180016a13  call    cs:__imp_DeleteObject
0x180016a19  mov     rcx, [rbp+57h+piconinfo.hbmMask]; ho
0x180016a1d  call    cs:__imp_DeleteObject
0x180016a23  test    ebx, ebx
0x180016a25  js      loc_180016BCB
0x180016a2b  mov     qword ptr [rbp+57h+arg_0.cx], r15
0x180016a2f  lea     rcx, [rbp+57h+arg_0]
0x180016a33  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180016a38  mov     qword ptr [rbp+57h+arg_0.cx], r15
0x180016a3c  mov     [rbp+57h+arg_8], r15
0x180016a40  lea     rcx, [rbp+57h+arg_8]
0x180016a44  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180016a49  lea     rax, [rbp+57h+arg_8]
0x180016a4d  mov     [rsp+0C0h+ppv], rax; ppv
0x180016a52  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x180016a59  mov     esi, 1
0x180016a5e  mov     r8d, esi; dwClsContext
0x180016a61  xor     edx, edx; pUnkOuter
0x180016a63  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x180016a6a  call    cs:__imp_CoCreateInstance
0x180016a70  mov     ebx, eax
0x180016a72  test    eax, eax
0x180016a74  js      loc_180016B2A
0x180016a7a  mov     [rbp+57h+var_80], r15
0x180016a7e  lea     rcx, [rbp+57h+var_80]
0x180016a82  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180016a87  lea     r9, [rbp+57h+var_80]; struct IWICBitmapSource **
0x180016a8b  mov     rdx, rdi; HBITMAP
0x180016a8e  mov     rcx, [rbp+57h+arg_8]; struct IWICImagingFactory *
0x180016a92  call    ?ConvertHBITMAPToWICBitmap@@YAJPEAUIWICImagingFactory@@PEAUHBITMAP__@@W4WICBitmapAlphaChannelOption@@PEAPEAUIWICBitmapSource@@@Z; ConvertHBITMAPToWICBitmap(IWICImagingFactory *,HBITMAP__ *,WICBitmapAlphaChannelOption,IWICBitmapSource * *)
0x180016a97  mov     ebx, eax
0x180016a99  test    eax, eax
0x180016a9b  js      short loc_180016B10
0x180016a9d  mov     [rbp+57h+var_88], r15
0x180016aa1  lea     rcx, [rbp+57h+var_88]
0x180016aa5  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180016aaa  movups  xmm0, xmmword ptr cs:GUID_WICPixelFormat32bppBGRA.Data1
0x180016ab1  movdqu  xmmword ptr [rbp+57h+piconinfo.fIcon], xmm0
0x180016ab6  lea     rax, [rbp+57h+var_88]
0x180016aba  mov     [rsp+0C0h+var_98], rax
0x180016abf  mov     dword ptr [rsp+0C0h+ppv], esi; int
0x180016ac3  lea     r9, [rbp+57h+piconinfo]
0x180016ac7  mov     rdx, [rbp+57h+var_80]
0x180016acb  mov     rcx, [rbp+57h+arg_8]
0x180016acf  call    ?GetStreamOfWICBitmapSourceWithOptions@@YAJPEAUIWICImagingFactory@@PEAUIWICBitmapSource@@AEBU_GUID@@U3@W4EncodingOptions@@PEAPEAUIStream@@@Z; GetStreamOfWICBitmapSourceWithOptions(IWICImagingFactory *,IWICBitmapSource *,_GUID const &,_GUID,EncodingOptions,IStream * *)
0x180016ad4  mov     ebx, eax
0x180016ad6  test    eax, eax
0x180016ad8  js      short loc_180016AF6
0x180016ada  mov     rcx, [rbp+57h+var_88]
0x180016ade  mov     rax, [rcx]
0x180016ae1  lea     r8, [rbp+57h+arg_0]
0x180016ae5  lea     rdx, _GUID_0000000c_0000_0000_c000_000000000046
0x180016aec  mov     rax, [rax]
0x180016aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016af4  mov     ebx, eax
0x180016af6  mov     rcx, [rbp+57h+var_88]
0x180016afa  test    rcx, rcx
0x180016afd  jz      short loc_180016B10
0x180016aff  mov     [rbp+57h+var_88], r15
0x180016b03  mov     rax, [rcx]
0x180016b06  mov     rax, [rax+10h]
0x180016b0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b0f  nop
0x180016b10  mov     rcx, [rbp+57h+var_80]
0x180016b14  test    rcx, rcx
0x180016b17  jz      short loc_180016B2A
0x180016b19  mov     [rbp+57h+var_80], r15
0x180016b1d  mov     rax, [rcx]
0x180016b20  mov     rax, [rax+10h]
0x180016b24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b29  nop
0x180016b2a  mov     rcx, [rbp+57h+arg_8]
0x180016b2e  test    rcx, rcx
0x180016b31  jz      short loc_180016B44
0x180016b33  mov     [rbp+57h+arg_8], r15
0x180016b37  mov     rax, [rcx]
0x180016b3a  mov     rax, [rax+10h]
0x180016b3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b43  nop
0x180016b44  test    ebx, ebx
0x180016b46  js      short loc_180016BB1
0x180016b48  lea     rcx, [r13+50h]
0x180016b4c  call    ?InternalRelease@?$ComPtr@UITerminalServiceSessionPickerUX@Controller@Logon@UI@Internal@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Internal::UI::Logon::Controller::ITerminalServiceSessionPickerUX>::InternalRelease(void)
0x180016b51  lea     r9, [r13+50h]
0x180016b55  lea     r8, _GUID_905a0fe1_bc53_11df_8c49_001e4fc686da
0x180016b5c  xor     edx, edx
0x180016b5e  mov     rcx, qword ptr [rbp+57h+arg_0.cx]
0x180016b62  call    cs:__imp_CreateRandomAccessStreamOverStream
0x180016b68  mov     ebx, eax
0x180016b6a  test    eax, eax
0x180016b6c  jns     short loc_180016BB1
0x180016b6e  mov     rcx, [rbp+5Fh]; this
0x180016b72  mov     r9d, eax; char *
0x180016b75  lea     r8, aPcshellShellAu_4; "pcshell\\shell\\auth\\authux\\controlle"...
0x180016b7c  mov     edx, 27h ; '''; void *
0x180016b81  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016b86  nop
0x180016b87  mov     rcx, qword ptr [rbp+57h+arg_0.cx]
0x180016b8b  test    rcx, rcx
0x180016b8e  jz      short loc_180016BA1
0x180016b90  mov     qword ptr [rbp+57h+arg_0.cx], r15
0x180016b94  mov     rax, [rcx]
0x180016b97  mov     rax, [rax+10h]
0x180016b9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ba0  nop
0x180016ba1  test    rdi, rdi
0x180016ba4  jz      short loc_180016C06
0x180016ba6  mov     rcx, rdi; ho
0x180016ba9  call    cs:__imp_DeleteObject
0x180016baf  jmp     short loc_180016C06
0x180016bb1  mov     rcx, qword ptr [rbp+57h+arg_0.cx]
0x180016bb5  test    rcx, rcx
0x180016bb8  jz      short loc_180016BCB
0x180016bba  mov     qword ptr [rbp+57h+arg_0.cx], r15
0x180016bbe  mov     rax, [rcx]
0x180016bc1  mov     rax, [rax+10h]
0x180016bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bca  nop
0x180016bcb  test    rdi, rdi
0x180016bce  jz      short loc_180016BD9
0x180016bd0  mov     rcx, rdi; ho
0x180016bd3  call    cs:__imp_DeleteObject
0x180016bd9  xor     eax, eax
0x180016bdb  jmp     short loc_180016C08
0x180016bdd  mov     ebx, 80070216h
0x180016be2  mov     edx, 1Ch
0x180016be7  jmp     short loc_180016BF3
0x180016be9  mov     ebx, 80070216h
0x180016bee  mov     edx, 1Bh; void *
0x180016bf3  mov     r9d, ebx; char *
0x180016bf6  lea     r8, aPcshellShellAu_4; "pcshell\\shell\\auth\\authux\\controlle"...
0x180016bfd  mov     rcx, [rbp+5Fh]; this
0x180016c01  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180016c06  mov     eax, ebx
0x180016c08  mov     rbx, [rsp+0C0h+arg_18]
0x180016c10  add     rsp, 90h
0x180016c17  pop     r15
0x180016c19  pop     r14
0x180016c1b  pop     r13
0x180016c1d  pop     r12
0x180016c1f  pop     rdi
0x180016c20  pop     rsi
0x180016c21  pop     rbp
0x180016c22  retn
```
