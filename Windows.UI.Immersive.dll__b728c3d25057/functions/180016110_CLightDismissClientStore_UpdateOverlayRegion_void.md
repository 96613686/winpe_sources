# CLightDismissClientStore::_UpdateOverlayRegion(void)

- ea: `0x180016110`
- end: `0x1800165a0`
- name: `?_UpdateOverlayRegion@CLightDismissClientStore@@AEAAJXZ`
- size: `1168`
- prototype: `__int64 __fastcall(CLightDismissClientStore *__hidden this)`
- caller_count: `8`
- callee_count: `7`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180015bcc`
- `0x180015cd0`
- `0x1800160a0`
- `0x1800165d0`
- `0x18002cca0`
- `0x180044b5c`
- `0x18007fa30`
- `0x18007fbe8`

## callees

- `0x180016110`
- `0x1800165b0`
- `0x1800176b4`
- `0x180025254`
- `0x18002e718`
- `0x180050ba0`
- `0x18007fd8c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001623c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001644d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016473`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001623c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001644d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180016473`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001646c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016492`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x18001646c`
- `api-ms-win-core-errorhandling-l1-1-0!RaiseException` at `0x180016492`
- `USER32!IsRectEmpty` at `0x180016391`
- `USER32!IsRectEmpty` at `0x180016391`
- `USER32!GetWindowRgn` at `0x18001637e`
- `USER32!GetWindowRgn` at `0x18001637e`
- `USER32!SetWindowRgn` at `0x180016585`
- `USER32!SetWindowRgn` at `0x180016585`
- `USER32!GetSystemMetrics` at `0x18001613f`
- `USER32!GetSystemMetrics` at `0x18001614c`
- `USER32!GetSystemMetrics` at `0x180016160`
- `USER32!GetSystemMetrics` at `0x180016171`
- `USER32!GetSystemMetrics` at `0x18001617e`
- `USER32!GetSystemMetrics` at `0x180016192`
- `USER32!GetSystemMetrics` at `0x1800161a5`
- `USER32!GetSystemMetrics` at `0x1800161b2`
- `USER32!GetSystemMetrics` at `0x1800161c6`
- `USER32!GetSystemMetrics` at `0x18001613f`
- `USER32!GetSystemMetrics` at `0x18001614c`
- `USER32!GetSystemMetrics` at `0x180016160`
- `USER32!GetSystemMetrics` at `0x180016171`
- `USER32!GetSystemMetrics` at `0x18001617e`
- `USER32!GetSystemMetrics` at `0x180016192`
- `USER32!GetSystemMetrics` at `0x1800161a5`
- `USER32!GetSystemMetrics` at `0x1800161b2`
- `USER32!GetSystemMetrics` at `0x1800161c6`
- `USER32!GetPropW` at `0x1800164c2`
- `USER32!GetPropW` at `0x18001653b`
- `USER32!GetPropW` at `0x1800164c2`
- `USER32!GetPropW` at `0x18001653b`
- `USER32!GetWindowRect` at `0x18001635a`
- `USER32!GetWindowRect` at `0x1800163ca`
- `USER32!GetWindowRect` at `0x18001635a`
- `USER32!GetWindowRect` at `0x1800163ca`
- `USER32!GetWindow` at `0x180016314`
- `USER32!GetWindow` at `0x1800163fc`
- `USER32!GetWindow` at `0x180016314`
- `USER32!GetWindow` at `0x1800163fc`
- `USER32!DestroyWindow` at `0x180016552`
- `USER32!DestroyWindow` at `0x180016552`
- `GDI32!CreateRectRgn` at `0x18001636a`
- `GDI32!CreateRectRgn` at `0x18001636a`
- `GDI32!OffsetRgn` at `0x1800164db`
- `GDI32!OffsetRgn` at `0x180016571`
- `GDI32!OffsetRgn` at `0x1800164db`
- `GDI32!OffsetRgn` at `0x180016571`
- `GDI32!CreateRectRgnIndirect` at `0x1800161f0`
- `GDI32!CreateRectRgnIndirect` at `0x1800164ea`
- `GDI32!CreateRectRgnIndirect` at `0x1800161f0`
- `GDI32!CreateRectRgnIndirect` at `0x1800164ea`
- `GDI32!CombineRgn` at `0x1800163ee`
- `GDI32!CombineRgn` at `0x1800163ee`

## pseudocode

```c
__int64 __fastcall CLightDismissClientStore::_UpdateOverlayRegion(CLightDismissClientStore *this)
{
  int SystemMetrics; // ebx
  int v3; // eax
  int v4; // ecx
  int v5; // ebx
  int v6; // eax
  int v7; // ecx
  int v8; // ebx
  int v9; // eax
  int v10; // ecx
  unsigned __int64 v11; // rdx
  signed int Overlay; // ebx
  __int64 v13; // rdi
  unsigned __int64 i; // r8
  __int64 v15; // rax
  signed int v16; // eax
  bool v18; // zf
  __int64 v19; // rcx
  HWND v20; // rcx
  __int64 j; // r14
  HWND v22; // rdi
  HWND Window; // r15
  HWND v24; // rdi
  HRGN RectRgn; // rax
  HRGN v26; // rax
  int v27; // edx
  int v28; // ecx
  HWND PropW; // r14
  int LastError; // eax
  int v31; // eax
  HRGN v32; // r14
  int v33; // eax
  HRGN v34; // r8
  __int64 v35; // [rsp+28h] [rbp-31h]
  void **v36; // [rsp+30h] [rbp-29h] BYREF
  HRGN hrgnSrc1; // [rsp+38h] [rbp-21h]
  void **v38; // [rsp+40h] [rbp-19h] BYREF
  HRGN hrgn; // [rsp+48h] [rbp-11h]
  void **v40; // [rsp+50h] [rbp-9h] BYREF
  HRGN hrgnSrc2; // [rsp+58h] [rbp-1h]
  struct tagRECT Rect; // [rsp+60h] [rbp+7h] BYREF
  RECT rect; // [rsp+70h] [rbp+17h] BYREF

  rect = 0;
  SystemMetrics = GetSystemMetrics(77);
  v3 = GetSystemMetrics(76);
  v4 = 76;
  if ( v3 >= SystemMetrics )
    v4 = 77;
  rect.left = GetSystemMetrics(v4);
  rect.top = rect.left;
  v5 = GetSystemMetrics(79);
  v6 = GetSystemMetrics(78);
  v7 = 78;
  if ( v6 <= v5 )
    v7 = 79;
  rect.right = rect.left + GetSystemMetrics(v7);
  v8 = GetSystemMetrics(79);
  v9 = GetSystemMetrics(78);
  v10 = 78;
  if ( v9 <= v8 )
    v10 = 79;
  rect.bottom = rect.top + GetSystemMetrics(v10);
  hrgnSrc1 = CreateRectRgnIndirect(&rect);
  v36 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
  if ( hrgnSrc1 )
  {
    v11 = *((_QWORD *)this + 12);
    Overlay = 0;
    v13 = 0;
    if ( v11 )
    {
      for ( i = 0; i < v11; ++i )
      {
        v15 = *(_QWORD *)(*((_QWORD *)this + 11) + 8 * i);
        if ( v15 )
        {
          do
          {
            v18 = (*(_BYTE *)v15 & 2) == 0;
            v19 = v15;
            v15 = *(_QWORD *)(v15 + 56);
            if ( v18 )
              v19 = v13;
            v13 = v19;
          }
          while ( v15 );
          if ( v19 )
            break;
        }
      }
    }
    v20 = (HWND)*((_QWORD *)this + 4);
    if ( !v13 )
    {
      if ( v20 )
      {
        DestroyWindow(v20);
        *((_QWORD *)this + 4) = 0;
      }
      goto LABEL_35;
    }
    if ( !v20 )
      Overlay = CLightDismissClientStore::_CreateOverlay(this);
    if ( *((_DWORD *)this + 39) )
    {
      if ( Overlay < 0 )
        goto LABEL_19;
      goto LABEL_35;
    }
    if ( Overlay < 0 )
      goto LABEL_19;
    for ( j = v13; *(_QWORD *)(j + 56); j = *(_QWORD *)(j + 56) )
      ;
    v22 = *(HWND *)(v13 + 8);
    Window = GetWindow(v22, 4u);
    if ( !Window )
      Window = (HWND)GetPropW(v22, L"Shell_Logical_Owner_Window_Prop");
    v24 = *(HWND *)(j + 8);
    if ( !v24 )
    {
LABEL_35:
      if ( *((_QWORD *)this + 4) )
      {
        OffsetRgn(hrgnSrc1, -rect.left, -rect.top);
        v33 = SetWindowRgn(*((HWND *)this + 4), hrgnSrc1, 1);
        v34 = hrgnSrc1;
        if ( v33 )
          v34 = 0;
        hrgnSrc1 = v34;
      }
      CLightDismissClientStore::_UpdateOverlayVisibility(this);
      goto LABEL_19;
    }
    while ( 1 )
    {
      if ( v24 == Window )
        goto LABEL_35;
      Rect = 0;
      GetWindowRect(v24, &Rect);
      RectRgn = CreateRectRgn(0, 0, 0, 0);
      v38 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      hrgn = RectRgn;
      if ( (unsigned int)GetWindowRgn(v24, RectRgn) > 1 )
        break;
      if ( IsRectEmpty(&Rect) )
        goto LABEL_40;
      v32 = CreateRectRgnIndirect(&Rect);
      v26 = hrgn;
      if ( v32 != hrgn )
      {
        Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::Close(&v38);
        v26 = v32;
      }
LABEL_41:
      hrgn = 0;
      v38 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      v40 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      hrgnSrc2 = v26;
      if ( v26 )
      {
        Rect = 0;
        GetWindowRect(v24, &Rect);
        if ( (Microsoft_Windows_WindowsUIImmersiveEnableBits & 1) != 0 )
        {
          LODWORD(v35) = Rect.bottom;
          McTemplateU0dddd_EventWriteTransfer(v28, v27, Rect.left, Rect.top, Rect.right, v35, v36);
        }
        CombineRgn(hrgnSrc1, hrgnSrc1, hrgnSrc2, 4);
      }
      PropW = GetWindow(v24, 4u);
      if ( !PropW )
        PropW = (HWND)GetPropW(v24, L"Shell_Logical_Owner_Window_Prop");
      v40 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
      if ( hrgnSrc2 )
      {
        if ( !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(&v40) )
        {
          LastError = GetLastError();
          if ( LastError > 0 )
            LastError = (unsigned __int16)LastError | 0x80070000;
          RaiseException(LastError, 1u, 0, 0);
          __debugbreak();
        }
        hrgnSrc2 = 0;
      }
      if ( !PropW )
        goto LABEL_35;
      v24 = PropW;
    }
    OffsetRgn(hrgn, Rect.left, Rect.top);
LABEL_40:
    v26 = hrgn;
    goto LABEL_41;
  }
  v16 = GetLastError();
  Overlay = v16;
  if ( v16 > 0 )
    Overlay = (unsigned __int16)v16 | 0x80070000;
  if ( Overlay >= 0 )
    Overlay = -2147467259;
LABEL_19:
  v36 = &Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable';
  if ( hrgnSrc1
    && !(unsigned __int8)Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(&v36) )
  {
    v31 = GetLastError();
    if ( v31 > 0 )
      v31 = (unsigned __int16)v31 | 0x80070000;
    RaiseException(v31, 1u, 0, 0);
    __debugbreak();
  }
  return (unsigned int)Overlay;
}

```

## disassembly

```asm
0x180016110  push    rbp
0x180016112  push    rbx
0x180016113  push    rsi
0x180016114  push    r12
0x180016116  lea     rbp, [rsp-3Fh]
0x18001611b  sub     rsp, 98h
0x180016122  mov     rax, cs:__security_cookie
0x180016129  xor     rax, rsp
0x18001612c  mov     [rbp+57h+var_30], rax
0x180016130  mov     rsi, rcx
0x180016133  xorps   xmm0, xmm0
0x180016136  mov     ecx, 4Dh ; 'M'; nIndex
0x18001613b  movups  xmmword ptr [rbp+57h+rect.left], xmm0
0x18001613f  call    cs:__imp_GetSystemMetrics
0x180016145  mov     ecx, 4Ch ; 'L'; nIndex
0x18001614a  mov     ebx, eax
0x18001614c  call    cs:__imp_GetSystemMetrics
0x180016152  mov     ecx, 4Ch ; 'L'
0x180016157  cmp     eax, ebx
0x180016159  jl      short loc_180016160
0x18001615b  mov     ecx, 4Dh ; 'M'; nIndex
0x180016160  call    cs:__imp_GetSystemMetrics
0x180016166  mov     ecx, 4Fh ; 'O'; nIndex
0x18001616b  mov     [rbp+57h+rect.left], eax
0x18001616e  mov     [rbp+57h+rect.top], eax
0x180016171  call    cs:__imp_GetSystemMetrics
0x180016177  mov     ecx, 4Eh ; 'N'; nIndex
0x18001617c  mov     ebx, eax
0x18001617e  call    cs:__imp_GetSystemMetrics
0x180016184  mov     ecx, 4Eh ; 'N'
0x180016189  cmp     eax, ebx
0x18001618b  jg      short loc_180016192
0x18001618d  mov     ecx, 4Fh ; 'O'; nIndex
0x180016192  call    cs:__imp_GetSystemMetrics
0x180016198  mov     ecx, eax
0x18001619a  add     ecx, [rbp+57h+rect.left]
0x18001619d  mov     [rbp+57h+rect.right], ecx
0x1800161a0  mov     ecx, 4Fh ; 'O'; nIndex
0x1800161a5  call    cs:__imp_GetSystemMetrics
0x1800161ab  mov     ecx, 4Eh ; 'N'; nIndex
0x1800161b0  mov     ebx, eax
0x1800161b2  call    cs:__imp_GetSystemMetrics
0x1800161b8  mov     ecx, 4Eh ; 'N'
0x1800161bd  cmp     eax, ebx
0x1800161bf  jg      short loc_1800161C6
0x1800161c1  mov     ecx, 4Fh ; 'O'; nIndex
0x1800161c6  call    cs:__imp_GetSystemMetrics
0x1800161cc  mov     ecx, eax
0x1800161ce  mov     [rsp+0B0h+arg_8], rdi
0x1800161d6  add     ecx, [rbp+57h+rect.top]
0x1800161d9  mov     [rbp+57h+rect.bottom], ecx
0x1800161dc  lea     rcx, [rbp+57h+rect]; lprect
0x1800161e0  mov     [rsp+0B0h+arg_10], r14
0x1800161e8  mov     [rsp+0B0h+var_20], r15
0x1800161f0  call    cs:__imp_CreateRectRgnIndirect
0x1800161f6  mov     [rbp+57h+hrgnSrc1], rax
0x1800161fa  lea     r12, ??_7?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::`vftable'
0x180016201  mov     [rbp+57h+var_80], r12
0x180016205  test    rax, rax
0x180016208  jz      short loc_18001623C
0x18001620a  mov     rdx, [rsi+60h]
0x18001620e  xor     ebx, ebx
0x180016210  xor     edi, edi
0x180016212  test    rdx, rdx
0x180016215  jz      loc_1800162CF
0x18001621b  mov     r9, [rsi+58h]
0x18001621f  xor     r8d, r8d
0x180016222  mov     rax, [r9+r8*8]
0x180016226  test    rax, rax
0x180016229  jnz     loc_1800162B0
0x18001622f  inc     r8
0x180016232  cmp     r8, rdx
0x180016235  jb      short loc_180016222
0x180016237  jmp     loc_1800162CF
0x18001623c  call    cs:__imp_GetLastError
0x180016242  mov     ebx, eax
0x180016244  test    eax, eax
0x180016246  jg      loc_18001643F
0x18001624c  test    ebx, ebx
0x18001624e  mov     eax, 80004005h
0x180016253  cmovns  ebx, eax
0x180016256  jmp     short loc_180016260
0x180016258  test    ebx, ebx
0x18001625a  jns     loc_18001632F
0x180016260  cmp     [rbp+57h+hrgnSrc1], 0
0x180016265  mov     [rbp+57h+var_80], r12
0x180016269  jz      short loc_18001627C
0x18001626b  lea     rcx, [rbp+57h+var_80]
0x18001626f  call    ?InternalClose@?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(void)
0x180016274  test    al, al
0x180016276  jz      loc_180016473
0x18001627c  mov     r15, [rsp+0B0h+var_20]
0x180016284  mov     eax, ebx
0x180016286  mov     r14, [rsp+0B0h+arg_10]
0x18001628e  mov     rdi, [rsp+0B0h+arg_8]
0x180016296  mov     rcx, [rbp+57h+var_30]
0x18001629a  xor     rcx, rsp; StackCookie
0x18001629d  call    __security_check_cookie
0x1800162a2  add     rsp, 98h
0x1800162a9  pop     r12
0x1800162ab  pop     rsi
0x1800162ac  pop     rbx
0x1800162ad  pop     rbp
0x1800162ae  retn
0x1800162b0  test    byte ptr [rax], 2
0x1800162b3  mov     rcx, rax
0x1800162b6  mov     rax, [rax+38h]
0x1800162ba  cmovz   rcx, rdi
0x1800162be  mov     rdi, rcx
0x1800162c1  test    rax, rax
0x1800162c4  jnz     short loc_1800162B0
0x1800162c6  test    rcx, rcx
0x1800162c9  jz      loc_18001622F
0x1800162cf  mov     rcx, [rsi+20h]; hWnd
0x1800162d3  test    rdi, rdi
0x1800162d6  jz      loc_180016549
0x1800162dc  test    rcx, rcx
0x1800162df  jz      loc_180016499
0x1800162e5  cmp     dword ptr [rsi+9Ch], 0
0x1800162ec  jnz     loc_180016258
0x1800162f2  test    ebx, ebx
0x1800162f4  js      loc_180016260
0x1800162fa  cmp     qword ptr [rdi+38h], 0
0x1800162ff  mov     r14, rdi
0x180016302  jnz     loc_1800164A8
0x180016308  mov     rdi, [rdi+8]
0x18001630c  mov     edx, 4; uCmd
0x180016311  mov     rcx, rdi; hWnd
0x180016314  call    cs:__imp_GetWindow
0x18001631a  mov     r15, rax
0x18001631d  test    rax, rax
0x180016320  jz      loc_1800164B8
0x180016326  mov     rdi, [r14+8]
0x18001632a  test    rdi, rdi
0x18001632d  jnz     short loc_180016347
0x18001632f  cmp     qword ptr [rsi+20h], 0
0x180016334  jnz     loc_180016561
0x18001633a  mov     rcx, rsi; this
0x18001633d  call    ?_UpdateOverlayVisibility@CLightDismissClientStore@@AEAAXXZ; CLightDismissClientStore::_UpdateOverlayVisibility(void)
0x180016342  jmp     loc_180016260
0x180016347  cmp     rdi, r15
0x18001634a  jz      short loc_18001632F
0x18001634c  xorps   xmm0, xmm0
0x18001634f  lea     rdx, [rbp+57h+Rect]; lpRect
0x180016353  mov     rcx, rdi; hWnd
0x180016356  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x18001635a  call    cs:__imp_GetWindowRect
0x180016360  xor     r9d, r9d; y2
0x180016363  xor     r8d, r8d; x2
0x180016366  xor     edx, edx; y1
0x180016368  xor     ecx, ecx; x1
0x18001636a  call    cs:__imp_CreateRectRgn
0x180016370  mov     rcx, rdi; hWnd
0x180016373  mov     [rbp+57h+var_70], r12
0x180016377  mov     rdx, rax; hRgn
0x18001637a  mov     [rbp+57h+hrgn], rax
0x18001637e  call    cs:__imp_GetWindowRgn
0x180016384  cmp     eax, 1
0x180016387  ja      loc_1800164D0
0x18001638d  lea     rcx, [rbp+57h+Rect]; lprc
0x180016391  call    cs:__imp_IsRectEmpty
0x180016397  test    eax, eax
0x180016399  jz      loc_1800164E6
0x18001639f  mov     rax, [rbp+57h+hrgn]
0x1800163a3  mov     [rbp+57h+hrgn], 0
0x1800163ab  mov     [rbp+57h+var_70], r12
0x1800163af  mov     [rbp+57h+var_60], r12
0x1800163b3  mov     [rbp+57h+hrgnSrc2], rax
0x1800163b7  test    rax, rax
0x1800163ba  jz      short loc_1800163F4
0x1800163bc  xorps   xmm0, xmm0
0x1800163bf  lea     rdx, [rbp+57h+Rect]; lpRect
0x1800163c3  mov     rcx, rdi; hWnd
0x1800163c6  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x1800163ca  call    cs:__imp_GetWindowRect
0x1800163d0  test    cs:Microsoft_Windows_WindowsUIImmersiveEnableBits, 1
0x1800163d7  jnz     loc_180016511
0x1800163dd  mov     rcx, [rbp+57h+hrgnSrc1]; hrgnDst
0x1800163e1  mov     r9d, 4; iMode
0x1800163e7  mov     r8, [rbp+57h+hrgnSrc2]; hrgnSrc2
0x1800163eb  mov     rdx, rcx; hrgnSrc1
0x1800163ee  call    cs:__imp_CombineRgn
0x1800163f4  mov     edx, 4; uCmd
0x1800163f9  mov     rcx, rdi; hWnd
0x1800163fc  call    cs:__imp_GetWindow
0x180016402  mov     r14, rax
0x180016405  test    rax, rax
0x180016408  jz      loc_180016531
0x18001640e  cmp     [rbp+57h+hrgnSrc2], 0
0x180016413  mov     [rbp+57h+var_60], r12
0x180016417  jz      short loc_18001642E
0x180016419  lea     rcx, [rbp+57h+var_60]
0x18001641d  call    ?InternalClose@?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@MEAA_NXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::InternalClose(void)
0x180016422  test    al, al
0x180016424  jz      short loc_18001644D
0x180016426  mov     [rbp+57h+hrgnSrc2], 0
0x18001642e  test    r14, r14
0x180016431  jz      loc_18001632F
0x180016437  mov     rdi, r14
0x18001643a  jmp     loc_180016347
0x18001643f  movzx   ebx, ax
0x180016442  or      ebx, 80070000h
0x180016448  jmp     loc_18001624C
0x18001644d  call    cs:__imp_GetLastError
0x180016453  test    eax, eax
0x180016455  jle     short loc_18001645F
0x180016457  movzx   eax, ax
0x18001645a  or      eax, 80070000h
0x18001645f  xor     r9d, r9d; lpArguments
0x180016462  xor     r8d, r8d; nNumberOfArguments
0x180016465  mov     edx, 1; dwExceptionFlags
0x18001646a  mov     ecx, eax; dwExceptionCode
0x18001646c  call    cs:__imp_RaiseException
0x180016472  int     3; Trap to Debugger
0x180016473  call    cs:__imp_GetLastError
0x180016479  test    eax, eax
0x18001647b  jle     short loc_180016485
0x18001647d  movzx   eax, ax
0x180016480  or      eax, 80070000h
0x180016485  xor     r9d, r9d; lpArguments
0x180016488  xor     r8d, r8d; nNumberOfArguments
0x18001648b  mov     edx, 1; dwExceptionFlags
0x180016490  mov     ecx, eax; dwExceptionCode
0x180016492  call    cs:__imp_RaiseException
0x180016498  int     3; Trap to Debugger
0x180016499  mov     rcx, rsi; this
0x18001649c  call    ?_CreateOverlay@CLightDismissClientStore@@AEAAJXZ; CLightDismissClientStore::_CreateOverlay(void)
0x1800164a1  mov     ebx, eax
0x1800164a3  jmp     loc_1800162E5
0x1800164a8  mov     r14, [r14+38h]
0x1800164ac  cmp     qword ptr [r14+38h], 0
0x1800164b1  jnz     short loc_1800164A8
0x1800164b3  jmp     loc_180016308
0x1800164b8  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x1800164bf  mov     rcx, rdi; hWnd
0x1800164c2  call    cs:__imp_GetPropW
0x1800164c8  mov     r15, rax
0x1800164cb  jmp     loc_180016326
0x1800164d0  mov     r8d, [rbp+57h+Rect.top]; y
0x1800164d4  mov     edx, [rbp+57h+Rect.left]; x
0x1800164d7  mov     rcx, [rbp+57h+hrgn]; hrgn
0x1800164db  call    cs:__imp_OffsetRgn
0x1800164e1  jmp     loc_18001639F
0x1800164e6  lea     rcx, [rbp+57h+Rect]; lprect
0x1800164ea  call    cs:__imp_CreateRectRgnIndirect
0x1800164f0  mov     r14, rax
0x1800164f3  mov     rax, [rbp+57h+hrgn]
0x1800164f7  cmp     r14, rax
0x1800164fa  jz      loc_1800163A3
0x180016500  lea     rcx, [rbp+57h+var_70]
0x180016504  call    ?Close@?$HandleT@UHRGNTraits@HandleTraits@Wrappers@WRL@Microsoft@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<Microsoft::WRL::Wrappers::HandleTraits::HRGNTraits>::Close(void)
0x180016509  mov     rax, r14
0x18001650c  jmp     loc_1800163A3
0x180016511  mov     eax, [rbp+57h+Rect.bottom]
0x180016514  mov     r9d, [rbp+57h+Rect.top]
0x180016518  mov     r8d, [rbp+57h+Rect.left]
0x18001651c  mov     dword ptr [rsp+0B0h+var_88], eax
0x180016520  mov     eax, [rbp+57h+Rect.right]
0x180016523  mov     [rsp+0B0h+var_90], eax
0x180016527  call    McTemplateU0dddd_EventWriteTransfer
0x18001652c  jmp     loc_1800163DD
0x180016531  lea     rdx, String; "Shell_Logical_Owner_Window_Prop"
0x180016538  mov     rcx, rdi; hWnd
0x18001653b  call    cs:__imp_GetPropW
0x180016541  mov     r14, rax
0x180016544  jmp     loc_18001640E
0x180016549  test    rcx, rcx
0x18001654c  jz      loc_18001632F
0x180016552  call    cs:__imp_DestroyWindow
0x180016558  mov     [rsi+20h], rbx
0x18001655c  jmp     loc_18001632F
0x180016561  mov     r8d, [rbp+57h+rect.top]
0x180016565  mov     edx, [rbp+57h+rect.left]
0x180016568  neg     r8d; y
0x18001656b  mov     rcx, [rbp+57h+hrgnSrc1]; hrgn
0x18001656f  neg     edx; x
0x180016571  call    cs:__imp_OffsetRgn
0x180016577  mov     rdx, [rbp+57h+hrgnSrc1]; hRgn
0x18001657b  mov     r8d, 1; bRedraw
0x180016581  mov     rcx, [rsi+20h]; hWnd
0x180016585  call    cs:__imp_SetWindowRgn
0x18001658b  mov     r8, [rbp+57h+hrgnSrc1]
0x18001658f  xor     edx, edx
0x180016591  test    eax, eax
0x180016593  cmovnz  r8, rdx
0x180016597  mov     [rbp+57h+hrgnSrc1], r8
0x18001659b  jmp     loc_18001633A
```
