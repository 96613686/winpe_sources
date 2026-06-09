# Windows::Internal::CharmWindowTrait::CreatePopupWindow(ulong,ushort const *,ulong,HWND__ *,HMONITOR__ *,POPUP_OPTIONS)

- ea: `0x18009aa94`
- end: `0x18009ac4a`
- name: `?CreatePopupWindow@CharmWindowTrait@Internal@Windows@@QEAAPEAUHWND__@@KPEBGKPEAU4@PEAUHMONITOR__@@W4POPUP_OPTIONS@@@Z`
- size: `438`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x18008d3d0`

## callees

- `0x18002ebe0`
- `0x18004882c`
- `0x180051524`
- `0x180098030`
- `0x18009aa94`

## import_xrefs

- `USER32!CreateWindowInBandEx` at `0x18009abc1`
- `USER32!CreateWindowInBandEx` at `0x18009abc1`
- `USER32!RegisterClassW` at `0x18009ab17`
- `USER32!RegisterClassW` at `0x18009ab17`
- `USER32!LoadCursorW` at `0x18009aaf6`
- `USER32!LoadCursorW` at `0x18009aaf6`
- `USER32!SendMessageW` at `0x18009ac25`
- `USER32!SendMessageW` at `0x18009ac25`
- `USER32!SetWindowCompositionAttribute` at `0x18009ac0e`
- `USER32!SetWindowCompositionAttribute` at `0x18009ac0e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
HWND __fastcall Windows::Internal::CharmWindowTrait::CreatePopupWindow(
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
0x18009aa94  mov     [rsp-8+arg_8], rbx
0x18009aa99  mov     [rsp-8+arg_10], rsi
0x18009aa9e  push    rbp
0x18009aa9f  push    rdi
0x18009aaa0  push    r13
0x18009aaa2  push    r14
0x18009aaa4  push    r15
0x18009aaa6  lea     rbp, [rsp-1Fh]
0x18009aaab  sub     rsp, 0E0h
0x18009aab2  mov     r14d, r9d
0x18009aab5  mov     r15, r8
0x18009aab8  mov     ebx, edx
0x18009aaba  mov     rdi, rcx
0x18009aabd  mov     eax, [rbp+3Fh+arg_30]
0x18009aac0  mov     [rcx+8], eax
0x18009aac3  xor     edx, edx; Val
0x18009aac5  lea     r8d, [rdx+48h]; Size
0x18009aac9  lea     rcx, [rbp+3Fh+WndClass]; void *
0x18009aacd  call    memset_0
0x18009aad2  mov     [rbp+3Fh+WndClass.style], 208h
0x18009aad9  lea     rax, ?NoUIAWindowProc@@YA_JPEAUHWND__@@I_K_J@Z; NoUIAWindowProc(HWND__ *,uint,unsigned __int64,__int64)
0x18009aae0  mov     [rbp+3Fh+WndClass.lpfnWndProc], rax
0x18009aae4  lea     rax, __ImageBase
0x18009aaeb  mov     [rbp+3Fh+WndClass.hInstance], rax
0x18009aaef  mov     edx, 7F00h; lpCursorName
0x18009aaf4  xor     ecx, ecx; hInstance
0x18009aaf6  call    cs:__imp_LoadCursorW
0x18009aafc  mov     [rbp+3Fh+WndClass.hCursor], rax
0x18009ab00  mov     [rbp+3Fh+WndClass.hbrBackground], 6
0x18009ab08  lea     r13, aShellCharmwind_0; "Shell_CharmWindow"
0x18009ab0f  mov     [rbp+3Fh+WndClass.lpszClassName], r13
0x18009ab13  lea     rcx, [rbp+3Fh+WndClass]; lpWndClass
0x18009ab17  call    cs:__imp_RegisterClassW
0x18009ab1d  mov     esi, ebx
0x18009ab1f  btr     esi, 15h
0x18009ab23  test    dword ptr [rdi+8], 100h
0x18009ab2a  cmovz   esi, ebx
0x18009ab2d  mov     rcx, [rbp+3Fh+arg_28]; HMONITOR
0x18009ab31  call    ?DUIGetScaleFactorForMonitor@@YA?AW4DEVICE_SCALE_FACTOR@@PEAUHMONITOR__@@@Z; DUIGetScaleFactorForMonitor(HMONITOR__ *)
0x18009ab36  lea     rcx, ??_7CharmWindowPositionTrait@Internal@Windows@@6B@; const Windows::Internal::CharmWindowPositionTrait::`vftable'
0x18009ab3d  mov     [rbp+3Fh+var_90], rcx
0x18009ab41  mov     ecx, [rdi+0Ch]
0x18009ab44  mov     dword ptr [rbp+3Fh+var_88], ecx
0x18009ab47  mov     r8d, eax
0x18009ab4a  lea     rdx, [rbp+3Fh+arg_0]; enum DEVICE_SCALE_FACTOR
0x18009ab4e  lea     rcx, [rbp+3Fh+var_90]; this
0x18009ab52  call    ?MaxSize@CharmWindowPositionTrait@Internal@Windows@@UEBA?AUtagSIZE@@W4DEVICE_SCALE_FACTOR@@@Z; Windows::Internal::CharmWindowPositionTrait::MaxSize(DEVICE_SCALE_FACTOR)
0x18009ab57  mov     edx, [rax]
0x18009ab59  test    byte ptr [rdi+8], 4
0x18009ab5d  jz      short loc_18009AB66
0x18009ab5f  xor     eax, eax
0x18009ab61  lea     ecx, [rax+1]
0x18009ab64  jmp     short loc_18009AB6E
0x18009ab66  mov     eax, 1
0x18009ab6b  lea     ecx, [rax+0Ch]
0x18009ab6e  mov     [rsp+100h+var_98], eax
0x18009ab72  mov     [rsp+100h+var_A0], ecx
0x18009ab76  mov     [rsp+100h+var_A8], 0
0x18009ab7f  lea     rax, __ImageBase
0x18009ab86  mov     [rsp+100h+var_B0], rax
0x18009ab8b  mov     [rsp+100h+var_B8], 0
0x18009ab94  mov     [rsp+100h+var_C0], 0
0x18009ab9d  mov     [rsp+100h+var_C8], 258h
0x18009aba5  mov     [rsp+100h+var_D0], edx
0x18009aba9  mov     eax, 80000000h
0x18009abae  mov     [rsp+100h+var_D8], eax
0x18009abb2  mov     [rsp+100h+var_E0], eax
0x18009abb6  mov     r9d, r14d
0x18009abb9  mov     r8, r15
0x18009abbc  mov     rdx, r13
0x18009abbf  mov     ecx, esi
0x18009abc1  call    cs:__imp_CreateWindowInBandEx
0x18009abc7  mov     rbx, rax
0x18009abca  test    rax, rax
0x18009abcd  jz      short loc_18009AC2B
0x18009abcf  test    dword ptr [rdi+8], 4000h
0x18009abd6  jz      short loc_18009ABE2
0x18009abd8  mov     rdx, rax; HWND
0x18009abdb  mov     cl, 1; bool
0x18009abdd  call    ?SetIhmRequireTouchInEditField@@YA_N_NPEAUHWND__@@@Z; SetIhmRequireTouchInEditField(bool,HWND__ *)
0x18009abe2  test    byte ptr [rdi+8], 4
0x18009abe6  jz      short loc_18009AC14
0x18009abe8  mov     [rbp+3Fh+arg_30], 1
0x18009abef  mov     [rbp+3Fh+var_90], 11h
0x18009abf7  lea     rax, [rbp+3Fh+arg_30]
0x18009abfb  mov     [rbp+3Fh+var_88], rax
0x18009abff  mov     [rbp+3Fh+var_80], 4
0x18009ac07  lea     rdx, [rbp+3Fh+var_90]
0x18009ac0b  mov     rcx, rbx
0x18009ac0e  call    cs:__imp_SetWindowCompositionAttribute
0x18009ac14  xor     r9d, r9d; lParam
0x18009ac17  mov     edx, 127h; Msg
0x18009ac1c  mov     r8d, 30001h; wParam
0x18009ac22  mov     rcx, rbx; hWnd
0x18009ac25  call    cs:__imp_SendMessageW
0x18009ac2b  mov     rax, rbx
0x18009ac2e  lea     r11, [rsp+100h+var_20]
0x18009ac36  mov     rbx, [r11+38h]
0x18009ac3a  mov     rsi, [r11+40h]
0x18009ac3e  mov     rsp, r11
0x18009ac41  pop     r15
0x18009ac43  pop     r14
0x18009ac45  pop     r13
0x18009ac47  pop     rdi
0x18009ac48  pop     rbp
0x18009ac49  retn
```
