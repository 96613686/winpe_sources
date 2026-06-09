# StartAddress

- ea: `0x10006cb8`
- end: `0x10006e0d`
- name: `StartAddress`
- size: `341`
- prototype: `DWORD __stdcall(LPVOID lpThreadParameter)`
- caller_count: `0`
- callee_count: `3`
- tags: `loader_planting, installer_update`

## callees

- `0x10006cb8`
- `0x1000ad15`
- `0x1000da66`

## import_xrefs

- `USER32!RegisterClassW` at `0x10006cfc`
- `USER32!RegisterClassW` at `0x10006cfc`
- `USER32!UnregisterClassW` at `0x10006dff`
- `USER32!UnregisterClassW` at `0x10006dff`
- `USER32!CreateWindowExW` at `0x10006d5c`
- `USER32!CreateWindowExW` at `0x10006d5c`
- `USER32!IsDialogMessageW` at `0x10006db4`
- `USER32!IsDialogMessageW` at `0x10006db4`
- `USER32!DispatchMessageW` at `0x10006dcc`
- `USER32!DispatchMessageW` at `0x10006dcc`
- `USER32!TranslateMessage` at `0x10006dc2`
- `USER32!TranslateMessage` at `0x10006dc2`
- `USER32!GetMessageW` at `0x10006dd9`
- `USER32!GetMessageW` at `0x10006dd9`
- `KERNEL32!GetLastError` at `0x10006d07`
- `KERNEL32!GetLastError` at `0x10006d66`
- `KERNEL32!GetLastError` at `0x10006d07`
- `KERNEL32!GetLastError` at `0x10006d66`
- `KERNEL32!SetEvent` at `0x10006da0`
- `KERNEL32!SetEvent` at `0x10006da0`

## string_xrefs

- `0x10006d2b`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\test.cpp`
- `0x10006d8a`: `d:\a\_work\1\s\src\ext\ca\wixca\dll\test.cpp`
- `0x10006d94`: `Failed to create window.`

## pseudocode

```c
DWORD __stdcall StartAddress(LPVOID lpThreadParameter)
{
  unsigned int v1; // esi
  signed int v2; // eax
  bool v3; // sf
  HWND Window; // eax
  signed int LastError; // eax
  bool v6; // sf
  int MessageW; // eax
  void *v9; // [esp-4h] [ebp-50h]
  WNDCLASSW WndClass; // [esp+8h] [ebp-44h] BYREF
  struct tagMSG hDlg; // [esp+30h] [ebp-1Ch] BYREF

  WndClass.lpfnWndProc = (WNDPROC)sub_10006E0D;
  WndClass.lpszClassName = L"WixCaMessageWindow";
  memset(&hDlg, 0, sizeof(hDlg));
  v1 = 0;
  WndClass.style = 0;
  WndClass.cbClsExtra = 0;
  WndClass.cbWndExtra = 0;
  WndClass.hInstance = (HINSTANCE)*((_DWORD *)lpThreadParameter + 1);
  memset(&WndClass.hIcon, 0, 16);
  if ( RegisterClassW(&WndClass) )
  {
    Window = CreateWindowExW(
               0x80u,
               WndClass.lpszClassName,
               0,
               0x90000000,
               0x80000000,
               8,
               0,
               0,
               0,
               0,
               *((HINSTANCE *)lpThreadParameter + 1),
               0);
    if ( Window )
    {
      v9 = *(void **)lpThreadParameter;
      *((_DWORD *)lpThreadParameter + 2) = Window;
      SetEvent(v9);
      while ( 1 )
      {
        MessageW = GetMessageW(&hDlg, 0, 0, 0);
        if ( !MessageW )
          break;
        if ( MessageW == -1 )
        {
          v1 = -2147418113;
          sub_1000DA66(-2147418113, "Unexpected return value from message pump.");
          break;
        }
        if ( !IsDialogMessageW(hDlg.hwnd, &hDlg) )
        {
          TranslateMessage(&hDlg);
          DispatchMessageW(&hDlg);
        }
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      v6 = LastError < 0;
      if ( LastError > 0 )
      {
        v1 = (unsigned __int16)LastError | 0x80070000;
        v6 = 1;
      }
      if ( !v6 )
        v1 = -2147467259;
      nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\test.cpp", 219, v1);
      sub_1000DA66(v1, "Failed to create window.");
    }
  }
  else
  {
    v2 = GetLastError();
    v1 = v2;
    v3 = v2 < 0;
    if ( v2 > 0 )
    {
      v1 = (unsigned __int16)v2 | 0x80070000;
      v3 = 1;
    }
    if ( !v3 )
      v1 = -2147467259;
    nullsub_1("d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca\\dll\\test.cpp", 212, v1);
    sub_1000DA66(v1, "Failed to register window.");
  }
  UnregisterClassW(L"WixCaMessageWindow", *((HINSTANCE *)lpThreadParameter + 1));
  return v1;
}

```

## disassembly

```asm
0x10006cb8  push    ebp
0x10006cb9  mov     ebp, esp
0x10006cbb  sub     esp, 44h
0x10006cbe  push    esi
0x10006cbf  push    edi
0x10006cc0  push    7
0x10006cc2  xor     eax, eax
0x10006cc4  mov     [ebp+WndClass.lpfnWndProc], offset sub_10006E0D
0x10006ccb  pop     ecx
0x10006ccc  lea     edi, [ebp+hDlg]
0x10006ccf  mov     [ebp+WndClass.lpszClassName], offset ClassName; "WixCaMessageWindow" ...
0x10006cd6  rep stosd
0x10006cd8  mov     edi, [ebp+lpThreadParameter]
0x10006cdb  xor     esi, esi
0x10006cdd  mov     [ebp+WndClass.style], esi
0x10006ce0  mov     [ebp+WndClass.cbClsExtra], esi
0x10006ce3  mov     [ebp+WndClass.cbWndExtra], esi
0x10006ce6  mov     eax, [edi+4]
0x10006ce9  mov     [ebp+WndClass.hInstance], eax
0x10006cec  lea     eax, [ebp+WndClass]
0x10006cef  push    eax; lpWndClass
0x10006cf0  mov     [ebp+WndClass.hIcon], esi
0x10006cf3  mov     [ebp+WndClass.hCursor], esi
0x10006cf6  mov     [ebp+WndClass.hbrBackground], esi
0x10006cf9  mov     [ebp+WndClass.lpszMenuName], esi
0x10006cfc  call    ds:RegisterClassW
0x10006d02  test    ax, ax
0x10006d05  jnz     short loc_10006D3F
0x10006d07  call    ds:GetLastError
0x10006d0d  mov     esi, eax
0x10006d0f  test    esi, esi
0x10006d11  jle     short loc_10006D1E
0x10006d13  movzx   esi, si
0x10006d16  or      esi, 80070000h
0x10006d1c  test    esi, esi
0x10006d1e  js      short loc_10006D25
0x10006d20  mov     esi, 80004005h
0x10006d25  push    esi
0x10006d26  push    0D4h
0x10006d2b  push    offset aDAWork1SSrcExt_4; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10006d30  call    nullsub_1
0x10006d35  push    offset aFailedToRegist_3; "Failed to register window."
0x10006d3a  jmp     loc_10006DEF
0x10006d3f  push    esi; lpParam
0x10006d40  push    dword ptr [edi+4]; hInstance
0x10006d43  push    esi; hMenu
0x10006d44  push    esi; hWndParent
0x10006d45  push    esi; nHeight
0x10006d46  push    esi; nWidth
0x10006d47  push    8; Y
0x10006d49  push    80000000h; X
0x10006d4e  push    90000000h; dwStyle
0x10006d53  push    esi; lpWindowName
0x10006d54  push    [ebp+WndClass.lpszClassName]; lpClassName
0x10006d57  push    80h; dwExStyle
0x10006d5c  call    ds:CreateWindowExW
0x10006d62  test    eax, eax
0x10006d64  jnz     short loc_10006D9B
0x10006d66  call    ds:GetLastError
0x10006d6c  mov     esi, eax
0x10006d6e  test    esi, esi
0x10006d70  jle     short loc_10006D7D
0x10006d72  movzx   esi, si
0x10006d75  or      esi, 80070000h
0x10006d7b  test    esi, esi
0x10006d7d  js      short loc_10006D84
0x10006d7f  mov     esi, 80004005h
0x10006d84  push    esi
0x10006d85  push    0DBh
0x10006d8a  push    offset aDAWork1SSrcExt_4; "d:\\a\\_work\\1\\s\\src\\ext\\ca\\wixca"...
0x10006d8f  call    nullsub_1
0x10006d94  push    offset aFailedToCreate_8; "Failed to create window."
0x10006d99  jmp     short loc_10006DEF
0x10006d9b  push    dword ptr [edi]; hEvent
0x10006d9d  mov     [edi+8], eax
0x10006da0  call    ds:SetEvent
0x10006da6  jmp     short loc_10006DD2
0x10006da8  cmp     eax, 0FFFFFFFFh
0x10006dab  jz      short loc_10006DE5
0x10006dad  lea     eax, [ebp+hDlg]
0x10006db0  push    eax; lpMsg
0x10006db1  push    dword ptr [ebp+hDlg]; hDlg
0x10006db4  call    ds:IsDialogMessageW
0x10006dba  test    eax, eax
0x10006dbc  jnz     short loc_10006DD2
0x10006dbe  lea     eax, [ebp+hDlg]
0x10006dc1  push    eax; lpMsg
0x10006dc2  call    ds:TranslateMessage
0x10006dc8  lea     eax, [ebp+hDlg]
0x10006dcb  push    eax; lpMsg
0x10006dcc  call    ds:DispatchMessageW
0x10006dd2  push    esi; wMsgFilterMax
0x10006dd3  push    esi; wMsgFilterMin
0x10006dd4  push    esi; hWnd
0x10006dd5  lea     eax, [ebp+hDlg]
0x10006dd8  push    eax; lpMsg
0x10006dd9  call    ds:GetMessageW
0x10006ddf  test    eax, eax
0x10006de1  jnz     short loc_10006DA8
0x10006de3  jmp     short loc_10006DF7
0x10006de5  mov     esi, 8000FFFFh
0x10006dea  push    offset aUnexpectedRetu_0; "Unexpected return value from message pu"...
0x10006def  push    esi
0x10006df0  call    sub_1000DA66
0x10006df5  pop     ecx
0x10006df6  pop     ecx
0x10006df7  push    dword ptr [edi+4]; hInstance
0x10006dfa  push    offset ClassName; "WixCaMessageWindow"
0x10006dff  call    ds:UnregisterClassW
0x10006e05  pop     edi
0x10006e06  mov     eax, esi
0x10006e08  pop     esi
0x10006e09  leave
0x10006e0a  retn    4
```
