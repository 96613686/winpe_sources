# Windows::Internal::DockedCharmWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS)

- ea: `0x18009d2c8`
- end: `0x18009d486`
- name: `?CreatePopupWindow@DockedCharmWindowTrait@Internal@Windows@@QEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@@Z`
- size: `446`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180097460`

## callees

- `0x18002ebe0`
- `0x18004882c`
- `0x180051524`
- `0x180098030`
- `0x18009d2c8`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x18009d3fd`
- `USER32!CreateWindowInBandEx` at `0x18009d3fd`
- `USER32!RegisterClassW` at `0x18009d34b`
- `USER32!RegisterClassW` at `0x18009d34b`
- `USER32!LoadCursorW` at `0x18009d32a`
- `USER32!LoadCursorW` at `0x18009d32a`
- `USER32!SendMessageW` at `0x18009d461`
- `USER32!SendMessageW` at `0x18009d461`
- `USER32!SetWindowCompositionAttribute` at `0x18009d44a`
- `USER32!SetWindowCompositionAttribute` at `0x18009d44a`

## pseudocode

```c
HWND __fastcall Windows::Internal::DockedCharmWindowTrait::CreatePopupWindow(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        unsigned int a4,
        __int64 a5,
        HMONITOR a6,
        int a7)
{
  unsigned int v11; // esi
  int v12; // edx
  int v13; // eax
  int v14; // ecx
  HWND WindowInBand; // rax
  HWND v16; // rbx
  __int64 v18; // [rsp+70h] [rbp-51h] BYREF
  int *v19; // [rsp+78h] [rbp-49h]
  __int64 v20; // [rsp+80h] [rbp-41h]
  WNDCLASSW WndClass; // [rsp+90h] [rbp-31h] BYREF
  enum DEVICE_SCALE_FACTOR v22; // [rsp+110h] [rbp+4Fh] BYREF

  *(_DWORD *)(a1 + 8) = a7;
  memset_0(&WndClass, 0, sizeof(WndClass));
  WndClass.style = 520;
  WndClass.lpfnWndProc = (WNDPROC)NoUIAWindowProc;
  WndClass.hInstance = &_ImageBase;
  WndClass.hCursor = LoadCursorW(0, (LPCWSTR)0x7F00);
  WndClass.hbrBackground = (HBRUSH)6;
  WndClass.lpszClassName = L"Shell_CharmWindow";
  RegisterClassW(&WndClass);
  v11 = a2 & 0xFFDFFFFF;
  if ( (*(_DWORD *)(a1 + 8) & 0x100) == 0 )
    v11 = a2;
  DUIGetScaleFactorForMonitor(a6);
  v18 = (__int64)&Windows::Internal::CharmWindowPositionTrait::`vftable';
  LODWORD(v19) = *(_DWORD *)(a1 + 12);
  v12 = *(_DWORD *)Windows::Internal::CharmWindowPositionTrait::MaxSize(
                     (Windows::Internal::CharmWindowPositionTrait *)&v18,
                     (enum DEVICE_SCALE_FACTOR)&v22).cx;
  *(_QWORD *)(a1 + 32) = a5;
  if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
  {
    v13 = 0;
    v14 = 1;
  }
  else
  {
    v13 = 1;
    v14 = 13;
  }
  WindowInBand = (HWND)CreateWindowInBandEx(
                         v11,
                         L"Shell_CharmWindow",
                         a3,
                         a4,
                         0x80000000,
                         0x80000000,
                         v12,
                         600,
                         0,
                         0,
                         &_ImageBase,
                         0,
                         v14,
                         v13);
  v16 = WindowInBand;
  if ( WindowInBand )
  {
    if ( (*(_DWORD *)(a1 + 8) & 0x4000) != 0 )
      SetIhmRequireTouchInEditField(1, WindowInBand);
    if ( (*(_BYTE *)(a1 + 8) & 4) != 0 )
    {
      a7 = 1;
      v18 = 17;
      v19 = &a7;
      v20 = 4;
      SetWindowCompositionAttribute(v16, &v18);
    }
    SendMessageW(v16, 0x127u, 0x30001u, 0);
  }
  return v16;
}

```

## disassembly

```asm
0x18009d2c8  mov     [rsp-8+arg_8], rbx
0x18009d2cd  mov     [rsp-8+arg_10], rsi
0x18009d2d2  push    rbp
0x18009d2d3  push    rdi
0x18009d2d4  push    r13
0x18009d2d6  push    r14
0x18009d2d8  push    r15
0x18009d2da  lea     rbp, [rsp-1Fh]
0x18009d2df  sub     rsp, 0E0h
0x18009d2e6  mov     r14d, r9d
0x18009d2e9  mov     r15, r8
0x18009d2ec  mov     ebx, edx
0x18009d2ee  mov     rdi, rcx
0x18009d2f1  mov     eax, [rbp+3Fh+arg_30]
0x18009d2f4  mov     [rcx+8], eax
0x18009d2f7  xor     edx, edx; Val
0x18009d2f9  lea     r8d, [rdx+48h]; Size
0x18009d2fd  lea     rcx, [rbp+3Fh+WndClass]; void *
0x18009d301  call    memset_0
0x18009d306  mov     [rbp+3Fh+WndClass.style], 208h
0x18009d30d  lea     rax, ?NoUIAWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; NoUIAWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18009d314  mov     [rbp+3Fh+WndClass.lpfnWndProc], rax
0x18009d318  lea     rax, __ImageBase
0x18009d31f  mov     [rbp+3Fh+WndClass.hInstance], rax
0x18009d323  mov     edx, 7F00h; lpCursorName
0x18009d328  xor     ecx, ecx; hInstance
0x18009d32a  call    cs:__imp_LoadCursorW
0x18009d330  mov     [rbp+3Fh+WndClass.hCursor], rax
0x18009d334  mov     [rbp+3Fh+WndClass.hbrBackground], 6
0x18009d33c  lea     r13, aShellCharmwind_2; "Shell_CharmWindow"
0x18009d343  mov     [rbp+3Fh+WndClass.lpszClassName], r13
0x18009d347  lea     rcx, [rbp+3Fh+WndClass]; lpWndClass
0x18009d34b  call    cs:__imp_RegisterClassW
0x18009d351  mov     esi, ebx
0x18009d353  btr     esi, 15h
0x18009d357  test    dword ptr [rdi+8], 100h
0x18009d35e  cmovz   esi, ebx
0x18009d361  mov     rcx, [rbp+3Fh+arg_28]; HMONITOR
0x18009d365  call    ?DUIGetScaleFactorForMonitor@@YA?AW4DEVICE_SCALE_FACTOR@@PEAUHMONITOR__@@@Z; DUIGetScaleFactorForMonitor(HMONITOR__ *)
0x18009d36a  lea     rcx, ??_7CharmWindowPositionTrait@Internal@Windows@@6B@; const Windows::Internal::CharmWindowPositionTrait::`vftable'
0x18009d371  mov     [rbp+3Fh+var_90], rcx
0x18009d375  mov     ecx, [rdi+0Ch]
0x18009d378  mov     dword ptr [rbp+3Fh+var_88], ecx
0x18009d37b  mov     r8d, eax
0x18009d37e  lea     rdx, [rbp+3Fh+arg_0]; enum DEVICE_SCALE_FACTOR
0x18009d382  lea     rcx, [rbp+3Fh+var_90]; this
0x18009d386  call    ?MaxSize@CharmWindowPositionTrait@Internal@Windows@@UEBA?AUtagSIZE@@W4DEVICE_SCALE_FACTOR@@@Z; Windows::Internal::CharmWindowPositionTrait::MaxSize(DEVICE_SCALE_FACTOR)
0x18009d38b  mov     edx, [rax]
0x18009d38d  mov     rax, [rbp+3Fh+arg_20]
0x18009d391  mov     [rdi+20h], rax
0x18009d395  test    byte ptr [rdi+8], 4
0x18009d399  jz      short loc_18009D3A2
0x18009d39b  xor     eax, eax
0x18009d39d  lea     ecx, [rax+1]
0x18009d3a0  jmp     short loc_18009D3AA
0x18009d3a2  mov     eax, 1
0x18009d3a7  lea     ecx, [rax+0Ch]
0x18009d3aa  mov     [rsp+100h+var_98], eax
0x18009d3ae  mov     [rsp+100h+var_A0], ecx
0x18009d3b2  mov     [rsp+100h+var_A8], 0
0x18009d3bb  lea     rax, __ImageBase
0x18009d3c2  mov     [rsp+100h+var_B0], rax
0x18009d3c7  mov     [rsp+100h+var_B8], 0
0x18009d3d0  mov     [rsp+100h+var_C0], 0
0x18009d3d9  mov     [rsp+100h+var_C8], 258h
0x18009d3e1  mov     [rsp+100h+var_D0], edx
0x18009d3e5  mov     eax, 80000000h
0x18009d3ea  mov     [rsp+100h+var_D8], eax
0x18009d3ee  mov     [rsp+100h+var_E0], eax
0x18009d3f2  mov     r9d, r14d
0x18009d3f5  mov     r8, r15
0x18009d3f8  mov     rdx, r13
0x18009d3fb  mov     ecx, esi
0x18009d3fd  call    cs:__imp_CreateWindowInBandEx
0x18009d403  mov     rbx, rax
0x18009d406  test    rax, rax
0x18009d409  jz      short loc_18009D467
0x18009d40b  test    dword ptr [rdi+8], 4000h
0x18009d412  jz      short loc_18009D41E
0x18009d414  mov     rdx, rax; HWND
0x18009d417  mov     cl, 1; bool
0x18009d419  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x18009d41e  test    byte ptr [rdi+8], 4
0x18009d422  jz      short loc_18009D450
0x18009d424  mov     [rbp+3Fh+arg_30], 1
0x18009d42b  mov     [rbp+3Fh+var_90], 11h
0x18009d433  lea     rax, [rbp+3Fh+arg_30]
0x18009d437  mov     [rbp+3Fh+var_88], rax
0x18009d43b  mov     [rbp+3Fh+var_80], 4
0x18009d443  lea     rdx, [rbp+3Fh+var_90]
0x18009d447  mov     rcx, rbx
0x18009d44a  call    cs:__imp_SetWindowCompositionAttribute
0x18009d450  xor     r9d, r9d; lParam
0x18009d453  mov     edx, 127h; Msg
0x18009d458  mov     r8d, 30001h; wParam
0x18009d45e  mov     rcx, rbx; hWnd
0x18009d461  call    cs:__imp_SendMessageW
0x18009d467  mov     rax, rbx
0x18009d46a  lea     r11, [rsp+100h+var_20]
0x18009d472  mov     rbx, [r11+38h]
0x18009d476  mov     rsi, [r11+40h]
0x18009d47a  mov     rsp, r11
0x18009d47d  pop     r15
0x18009d47f  pop     r14
0x18009d481  pop     r13
0x18009d483  pop     rdi
0x18009d484  pop     rbp
0x18009d485  retn
```
