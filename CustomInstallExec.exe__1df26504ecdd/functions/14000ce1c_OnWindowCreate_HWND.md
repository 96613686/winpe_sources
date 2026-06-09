# OnWindowCreate(HWND__ *)

- ea: `0x14000ce1c`
- end: `0x14000d019`
- name: `?OnWindowCreate@@YAHPEAUHWND__@@@Z`
- size: `509`
- prototype: `__int64 __fastcall(HWND hWndParent)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x14000d2f0`

## callees

- `0x14000ca7c`
- `0x14000ce1c`

## import_xrefs

- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cebd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cf3a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cfba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cebd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cf3a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!CreateWindowExW` at `0x14000cfba`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x14000cfd2`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!EnableWindow` at `0x14000cfd2`
- `COMCTL32!InitCommonControlsEx` at `0x14000ce3d`
- `COMCTL32!InitCommonControlsEx` at `0x14000ce3d`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14000cfec`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14000d002`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14000cfec`
- `ext-ms-win-ntuser-message-l1-1-0!SendMessageW` at `0x14000d002`

## pseudocode

```c
__int64 __fastcall OnWindowCreate(HWND hWndParent)
{
  HWND Window; // rax
  HWND v3; // rax
  HWND v4; // rax
  HWND v5; // rbx
  INITCOMMONCONTROLSEX v7; // [rsp+78h] [rbp+10h] BYREF

  v7.dwSize = 8;
  v7.dwICC = 16416;
  if ( !InitCommonControlsEx(&v7) )
    return 0;
  FormatLabelText();
  Window = CreateWindowExW(
             0,
             L"Static",
             (LPCWSTR)g_labelText,
             0x50000000u,
             g_labelTextCoordinate,
             Y,
             dword_140016240 - g_labelTextCoordinate,
             dword_140016244 - Y,
             hWndParent,
             0,
             g_instance,
             0);
  if ( !Window )
    return 0;
  g_textLabel = Window;
  v3 = CreateWindowExW(
         0,
         L"msctls_progress32",
         &g_title,
         0x50000000u,
         g_progressBarCoordinate,
         dword_1400162AC,
         dword_1400162B0 - g_progressBarCoordinate,
         dword_1400162B4 - dword_1400162AC,
         hWndParent,
         (HMENU)0x69,
         g_instance,
         0);
  if ( !v3 )
    return 0;
  g_progressBar = v3;
  v4 = CreateWindowExW(
         0,
         L"Button",
         &g_cancelText,
         0x50000F00u,
         g_buttonCoordinate,
         dword_14001622C,
         dword_140016230 - g_buttonCoordinate,
         dword_140016234 - dword_14001622C,
         hWndParent,
         0,
         g_instance,
         0);
  v5 = v4;
  if ( !v4 )
    return 0;
  EnableWindow(v4, 1);
  SendMessageW(g_textLabel, 0x30u, g_font, 1);
  SendMessageW(v5, 0x30u, g_font, 1);
  return 1;
}

```

## disassembly

```asm
0x14000ce1c  mov     rax, rsp
0x14000ce1f  mov     [rax+8], rbx
0x14000ce23  push    rsi
0x14000ce24  sub     rsp, 60h
0x14000ce28  mov     rbx, rcx
0x14000ce2b  mov     dword ptr [rax+10h], 8
0x14000ce32  lea     rcx, [rax+10h]; picce
0x14000ce36  mov     dword ptr [rax+14h], 4020h
0x14000ce3d  call    cs:__imp_InitCommonControlsEx
0x14000ce43  test    eax, eax
0x14000ce45  jz      loc_14000D00C
0x14000ce4b  call    ?FormatLabelText@@YAXXZ; FormatLabelText(void)
0x14000ce50  mov     r9d, cs:?g_labelTextCoordinate@@3UtagRECT@@A; tagRECT g_labelTextCoordinate
0x14000ce57  mov     esi, 50000000h
0x14000ce5c  mov     rdx, cs:?g_instance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_instance
0x14000ce63  mov     r10d, cs:Y
0x14000ce6a  mov     ecx, cs:dword_140016244
0x14000ce70  mov     eax, cs:dword_140016240
0x14000ce76  sub     ecx, r10d
0x14000ce79  mov     r8, cs:?g_labelText@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@A; lpWindowName
0x14000ce80  sub     eax, r9d
0x14000ce83  mov     [rsp+68h+lpParam], 0; lpParam
0x14000ce8c  mov     [rsp+68h+hInstance], rdx; hInstance
0x14000ce91  lea     rdx, ClassName; "Static"
0x14000ce98  mov     [rsp+68h+hMenu], 0; hMenu
0x14000cea1  mov     [rsp+68h+hWndParent], rbx; hWndParent
0x14000cea6  mov     [rsp+68h+nHeight], ecx; nHeight
0x14000ceaa  xor     ecx, ecx; dwExStyle
0x14000ceac  mov     [rsp+68h+nWidth], eax; nWidth
0x14000ceb0  mov     [rsp+68h+Y], r10d; Y
0x14000ceb5  mov     [rsp+68h+X], r9d; X
0x14000ceba  mov     r9d, esi; dwStyle
0x14000cebd  call    cs:__imp_CreateWindowExW
0x14000cec3  test    rax, rax
0x14000cec6  jz      loc_14000D00C
0x14000cecc  mov     edx, cs:?g_progressBarCoordinate@@3UtagRECT@@A; tagRECT g_progressBarCoordinate
0x14000ced2  mov     r9d, esi; dwStyle
0x14000ced5  mov     r8d, cs:dword_1400162B4
0x14000cedc  mov     r10d, cs:dword_1400162AC
0x14000cee3  sub     r8d, r10d
0x14000cee6  mov     ecx, cs:dword_1400162B0
0x14000ceec  mov     [rsp+68h+lpParam], 0; lpParam
0x14000cef5  sub     ecx, edx
0x14000cef7  mov     cs:?g_textLabel@@3PEAUHWND__@@EA, rax; HWND__ * g_textLabel
0x14000cefe  mov     rax, cs:?g_instance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_instance
0x14000cf05  mov     [rsp+68h+hInstance], rax; hInstance
0x14000cf0a  mov     [rsp+68h+hMenu], 69h ; 'i'; hMenu
0x14000cf13  mov     [rsp+68h+hWndParent], rbx; hWndParent
0x14000cf18  mov     [rsp+68h+nHeight], r8d; nHeight
0x14000cf1d  lea     r8, ?g_title@@3PAGA; lpWindowName
0x14000cf24  mov     [rsp+68h+nWidth], ecx; nWidth
0x14000cf28  xor     ecx, ecx; dwExStyle
0x14000cf2a  mov     [rsp+68h+Y], r10d; Y
0x14000cf2f  mov     [rsp+68h+X], edx; X
0x14000cf33  lea     rdx, aMsctlsProgress; "msctls_progress32"
0x14000cf3a  call    cs:__imp_CreateWindowExW
0x14000cf40  test    rax, rax
0x14000cf43  jz      loc_14000D00C
0x14000cf49  mov     r9d, cs:dword_14001622C
0x14000cf50  mov     edx, cs:?g_buttonCoordinate@@3UtagRECT@@A; tagRECT g_buttonCoordinate
0x14000cf56  mov     r8d, cs:dword_140016234
0x14000cf5d  mov     ecx, cs:dword_140016230
0x14000cf63  sub     r8d, r9d
0x14000cf66  mov     [rsp+68h+lpParam], 0; lpParam
0x14000cf6f  sub     ecx, edx
0x14000cf71  mov     cs:?g_progressBar@@3PEAUHWND__@@EA, rax; HWND__ * g_progressBar
0x14000cf78  mov     rax, cs:?g_instance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_instance
0x14000cf7f  mov     [rsp+68h+hInstance], rax; hInstance
0x14000cf84  mov     [rsp+68h+hMenu], 0; hMenu
0x14000cf8d  mov     [rsp+68h+hWndParent], rbx; hWndParent
0x14000cf92  mov     [rsp+68h+nHeight], r8d; nHeight
0x14000cf97  lea     r8, ?g_cancelText@@3PAGA; lpWindowName
0x14000cf9e  mov     [rsp+68h+nWidth], ecx; nWidth
0x14000cfa2  xor     ecx, ecx; dwExStyle
0x14000cfa4  mov     [rsp+68h+Y], r9d; Y
0x14000cfa9  mov     r9d, 50000F00h; dwStyle
0x14000cfaf  mov     [rsp+68h+X], edx; X
0x14000cfb3  lea     rdx, aButton; "Button"
0x14000cfba  call    cs:__imp_CreateWindowExW
0x14000cfc0  mov     rbx, rax
0x14000cfc3  test    rax, rax
0x14000cfc6  jz      short loc_14000D00C
0x14000cfc8  mov     esi, 1
0x14000cfcd  mov     rcx, rax; hWnd
0x14000cfd0  mov     edx, esi; bEnable
0x14000cfd2  call    cs:__imp_EnableWindow
0x14000cfd8  mov     r8, cs:?g_font@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHFONT__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wParam
0x14000cfdf  lea     edx, [rsi+2Fh]; Msg
0x14000cfe2  mov     rcx, cs:?g_textLabel@@3PEAUHWND__@@EA; hWnd
0x14000cfe9  mov     r9d, esi; lParam
0x14000cfec  call    cs:__imp_SendMessageW
0x14000cff2  mov     r8, cs:?g_font@@3V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAUHFONT__@@P6AHPEAX@Z$1?DeleteObject@@YAH0@ZU?$integral_constant@_K$0A@@wistd@@PEAU1@PEAU1@$0A@$$T@details@wil@@@details@wil@@@wil@@A; wParam
0x14000cff9  lea     edx, [rsi+2Fh]; Msg
0x14000cffc  mov     r9d, esi; lParam
0x14000cfff  mov     rcx, rbx; hWnd
0x14000d002  call    cs:__imp_SendMessageW
0x14000d008  mov     eax, esi
0x14000d00a  jmp     short loc_14000D00E
0x14000d00c  xor     eax, eax
0x14000d00e  mov     rbx, [rsp+68h+arg_0]
0x14000d013  add     rsp, 60h
0x14000d017  pop     rsi
0x14000d018  retn
```
