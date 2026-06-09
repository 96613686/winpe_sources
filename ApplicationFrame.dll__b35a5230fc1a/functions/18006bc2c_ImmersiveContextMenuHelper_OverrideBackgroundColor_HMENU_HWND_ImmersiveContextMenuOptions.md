# ImmersiveContextMenuHelper::OverrideBackgroundColor(HMENU__ *,HWND__ *,ImmersiveContextMenuOptions)

- ea: `0x18006bc2c`
- end: `0x18006bd56`
- name: `?OverrideBackgroundColor@ImmersiveContextMenuHelper@@YAJPEAUHMENU__@@PEAUHWND__@@W4ImmersiveContextMenuOptions@@@Z`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x18006b3f8`

## callees

- `0x180041ec0`
- `0x18006bc2c`

## import_xrefs

- `UxTheme!CloseThemeData` at `0x18006bd35`
- `UxTheme!CloseThemeData` at `0x18006bd35`
- `UxTheme!OpenThemeData` at `0x18006bc98`
- `UxTheme!OpenThemeData` at `0x18006bcc1`
- `UxTheme!OpenThemeData` at `0x18006bc98`
- `UxTheme!OpenThemeData` at `0x18006bcc1`
- `UxTheme!GetThemeColor` at `0x18006bcf7`
- `UxTheme!GetThemeColor` at `0x18006bcf7`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18006bcb5`
- `ext-ms-win-ntuser-window-l1-1-0!GetParent` at `0x18006bcb5`
- `GDI32!CreateSolidBrush` at `0x18006bd0a`
- `GDI32!CreateSolidBrush` at `0x18006bd0a`
- `USER32!SetMenuInfo` at `0x18006bd1d`
- `USER32!SetMenuInfo` at `0x18006bd1d`

## pseudocode

```c
__int64 __fastcall ImmersiveContextMenuHelper::OverrideBackgroundColor(HMENU a1, HWND a2, char a3)
{
  char v3; // r15
  const wchar_t *v4; // rbp
  const WCHAR *v6; // rsi
  const WCHAR *v8; // rdx
  HTHEME v9; // rdi
  HRESULT ThemeColor; // ebx
  HWND Parent; // rax
  MENUINFO v13; // [rsp+30h] [rbp-58h] BYREF
  COLORREF color; // [rsp+A0h] [rbp+18h] BYREF

  v3 = byte_180091FF1;
  v4 = L"LightMode_ImmersiveStart::Menu";
  v13.cbSize = 40;
  v13.fMask = -2147483646;
  v6 = L"DarkMode_ImmersiveStart::Menu";
  memset(&v13.dwStyle, 0, 32);
  v8 = L"DarkMode_ImmersiveStart::Menu";
  if ( (a3 & 8) == 0 )
    v4 = L"ImmersiveStart::Menu";
  if ( !byte_180091FF1 )
    v8 = v4;
  v9 = OpenThemeData(a2, v8);
  if ( v9 )
    goto LABEL_9;
  ThemeColor = -2147418113;
  if ( !v3 )
    v6 = v4;
  Parent = GetParent(a2);
  v9 = OpenThemeData(Parent, v6);
  if ( v9 )
  {
LABEL_9:
    color = 0;
    ThemeColor = GetThemeColor(v9, 9, 0, 3802, &color);
    if ( ThemeColor >= 0 )
    {
      v13.hbrBack = CreateSolidBrush(color);
      if ( SetMenuInfo(a1, &v13) )
        ThemeColor = 0;
      else
        ThemeColor = ResultFromKnownLastError();
    }
    CloseThemeData(v9);
  }
  return (unsigned int)ThemeColor;
}

```

## disassembly

```asm
0x18006bc2c  mov     rax, rsp
0x18006bc2f  mov     [rax+8], rbx
0x18006bc33  mov     [rax+10h], rbp
0x18006bc37  push    rsi
0x18006bc38  push    rdi
0x18006bc39  push    r12
0x18006bc3b  push    r14
0x18006bc3d  push    r15
0x18006bc3f  sub     rsp, 60h
0x18006bc43  mov     r15b, cs:byte_180091FF1
0x18006bc4a  lea     rbp, aLightmodeImmer; "LightMode_ImmersiveStart::Menu"
0x18006bc51  mov     r14, rdx
0x18006bc54  mov     dword ptr [rax-58h], 28h ; '('
0x18006bc5b  test    r8b, 8
0x18006bc5f  mov     dword ptr [rax-54h], 80000002h
0x18006bc66  xorps   xmm0, xmm0
0x18006bc69  lea     rsi, aDarkmodeImmers; "DarkMode_ImmersiveStart::Menu"
0x18006bc70  xorps   xmm1, xmm1
0x18006bc73  mov     r12, rcx
0x18006bc76  movdqu  xmmword ptr [rax-50h], xmm0
0x18006bc7b  mov     rdx, rsi
0x18006bc7e  mov     rcx, r14; hwnd
0x18006bc81  movdqu  xmmword ptr [rax-40h], xmm1
0x18006bc86  lea     rax, aImmersivestart; "ImmersiveStart::Menu"
0x18006bc8d  cmovz   rbp, rax
0x18006bc91  test    r15b, r15b
0x18006bc94  cmovz   rdx, rbp; pszClassList
0x18006bc98  call    cs:__imp_OpenThemeData
0x18006bc9e  mov     rdi, rax
0x18006bca1  test    rax, rax
0x18006bca4  jnz     short loc_18006BCCF
0x18006bca6  test    r15b, r15b
0x18006bca9  mov     rcx, r14; hWnd
0x18006bcac  mov     ebx, 8000FFFFh
0x18006bcb1  cmovz   rsi, rbp
0x18006bcb5  call    cs:__imp_GetParent
0x18006bcbb  mov     rcx, rax; hwnd
0x18006bcbe  mov     rdx, rsi; pszClassList
0x18006bcc1  call    cs:__imp_OpenThemeData
0x18006bcc7  mov     rdi, rax
0x18006bcca  test    rax, rax
0x18006bccd  jz      short loc_18006BD3B
0x18006bccf  xor     r8d, r8d; iStateId
0x18006bcd2  mov     [rsp+88h+color], 0
0x18006bcdd  lea     rax, [rsp+88h+color]
0x18006bce5  mov     r9d, 0EDAh; iPropId
0x18006bceb  mov     rcx, rdi; hTheme
0x18006bcee  mov     [rsp+88h+pColor], rax; pColor
0x18006bcf3  lea     edx, [r8+9]; iPartId
0x18006bcf7  call    cs:__imp_GetThemeColor
0x18006bcfd  mov     ebx, eax
0x18006bcff  test    eax, eax
0x18006bd01  js      short loc_18006BD32
0x18006bd03  mov     ecx, [rsp+88h+color]; color
0x18006bd0a  call    cs:__imp_CreateSolidBrush
0x18006bd10  lea     rdx, [rsp+88h+var_58]; LPCMENUINFO
0x18006bd15  mov     rcx, r12; HMENU
0x18006bd18  mov     [rsp+88h+var_58.hbrBack], rax
0x18006bd1d  call    cs:__imp_SetMenuInfo
0x18006bd23  test    eax, eax
0x18006bd25  jz      short loc_18006BD2B
0x18006bd27  xor     ebx, ebx
0x18006bd29  jmp     short loc_18006BD32
0x18006bd2b  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006bd30  mov     ebx, eax
0x18006bd32  mov     rcx, rdi; hTheme
0x18006bd35  call    cs:__imp_CloseThemeData
0x18006bd3b  lea     r11, [rsp+88h+var_28]
0x18006bd40  mov     eax, ebx
0x18006bd42  mov     rbx, [r11+30h]
0x18006bd46  mov     rbp, [r11+38h]
0x18006bd4a  mov     rsp, r11
0x18006bd4d  pop     r15
0x18006bd4f  pop     r14
0x18006bd51  pop     r12
0x18006bd53  pop     rdi
0x18006bd54  pop     rsi
0x18006bd55  retn
```
