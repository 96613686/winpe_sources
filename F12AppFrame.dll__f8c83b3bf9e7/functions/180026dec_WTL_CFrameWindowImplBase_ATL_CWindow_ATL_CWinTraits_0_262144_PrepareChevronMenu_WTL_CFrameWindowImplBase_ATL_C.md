# WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<0,262144>>::PrepareChevronMenu(WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<0,262144>>::_ChevronMenuInfo &)

- ea: `0x180026dec`
- end: `0x180027177`
- name: `?PrepareChevronMenu@?$CFrameWindowImplBase@VCWindow@ATL@@V?$CWinTraits@$0A@$0EAAAA@@2@@WTL@@QEAA_NAEAU_ChevronMenuInfo@12@@Z`
- size: `907`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180027180`

## callees

- `0x180001800`
- `0x180002678`
- `0x180005e44`
- `0x180026dec`
- `0x180035010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x180026ea4`
- `KERNEL32!FreeLibrary` at `0x180026ea4`
- `KERNEL32!GetProcAddress` at `0x180026e84`
- `KERNEL32!GetProcAddress` at `0x180026e84`
- `KERNEL32!LoadLibraryExW` at `0x180026e63`
- `KERNEL32!LoadLibraryExW` at `0x180026e63`
- `KERNEL32!GetVersionExW` at `0x180026e38`
- `KERNEL32!GetVersionExW` at `0x180026e38`
- `KERNEL32!lstrlenW` at `0x1800270aa`
- `KERNEL32!lstrlenW` at `0x1800270aa`
- `USER32!SendMessageW` at `0x180026eeb`
- `USER32!SendMessageW` at `0x180026f03`
- `USER32!SendMessageW` at `0x180026f27`
- `USER32!SendMessageW` at `0x180026f77`
- `USER32!SendMessageW` at `0x180026f9d`
- `USER32!SendMessageW` at `0x18002709a`
- `USER32!SendMessageW` at `0x180026eeb`
- `USER32!SendMessageW` at `0x180026f03`
- `USER32!SendMessageW` at `0x180026f27`
- `USER32!SendMessageW` at `0x180026f77`
- `USER32!SendMessageW` at `0x180026f9d`
- `USER32!SendMessageW` at `0x18002709a`
- `USER32!GetClientRect` at `0x180026f51`
- `USER32!GetClientRect` at `0x180026f51`
- `USER32!LoadStringW` at `0x1800270d5`
- `USER32!LoadStringW` at `0x1800270d5`
- `USER32!MessageBeep` at `0x180027143`
- `USER32!MessageBeep` at `0x180027143`
- `USER32!DestroyMenu` at `0x18002713a`
- `USER32!DestroyMenu` at `0x18002713a`
- `USER32!GetMenuItemInfoW` at `0x180027038`
- `USER32!GetMenuItemInfoW` at `0x180027038`
- `USER32!GetMenuItemCount` at `0x180026fb8`
- `USER32!GetMenuItemCount` at `0x180027128`
- `USER32!GetMenuItemCount` at `0x180026fb8`
- `USER32!GetMenuItemCount` at `0x180027128`
- `USER32!AppendMenuW` at `0x180027111`
- `USER32!AppendMenuW` at `0x180027111`
- `USER32!CreatePopupMenu` at `0x180026f3a`
- `USER32!CreatePopupMenu` at `0x180026f3a`

## string_xrefs

- `0x180026e7a`: `DllGetVersion`
- `0x180026e55`: `comctl32.dll`

## pseudocode

```c
char __fastcall WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<0,262144>>::PrepareChevronMenu(
        __int64 a1,
        __int64 a2)
{
  HMODULE Library; // rax
  HMODULE v4; // rdi
  signed int Error; // ebx
  FARPROC ProcAddress; // rax
  int v7; // eax
  __int64 v8; // rcx
  HWND v9; // rdi
  HMENU v11; // rsi
  HMENU PopupMenu; // rbx
  UINT i; // r15d
  const WCHAR *dwTypeData; // r9
  UINT v15; // edx
  HMENU hSubMenu; // r8
  char v17; // r14
  _OSVERSIONINFOW *p_VersionInformation; // r12
  int StringW; // eax
  __int64 v20; // rcx
  int v21; // edx
  int v22; // [rsp+20h] [rbp-E0h]
  tagMENUITEMINFOW mii; // [rsp+30h] [rbp-D0h] BYREF
  int lParam; // [rsp+80h] [rbp-80h] BYREF
  int lParam_4; // [rsp+84h] [rbp-7Ch] BYREF
  HWND hWnd; // [rsp+A8h] [rbp-58h]
  _BYTE v27[20]; // [rsp+100h] [rbp+0h] BYREF
  LPARAM v28[2]; // [rsp+118h] [rbp+18h] BYREF
  __int128 v29; // [rsp+128h] [rbp+28h]
  struct tagRECT Rect; // [rsp+138h] [rbp+38h] BYREF
  _OSVERSIONINFOW VersionInformation; // [rsp+150h] [rbp+50h] BYREF

  VersionInformation.dwOSVersionInfoSize = 276;
  memset_0(&VersionInformation.dwMajorVersion, 0, 0x110u);
  if ( !GetVersionExW(&VersionInformation) || VersionInformation.dwMajorVersion < 6 )
    goto LABEL_11;
  *(_DWORD *)v27 = 20;
  *(_OWORD *)&v27[4] = 0;
  Library = LoadLibraryExW(L"comctl32.dll", 0, 0);
  v4 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "DllGetVersion");
    Error = ProcAddress ? ((__int64 (__fastcall *)(_BYTE *))ProcAddress)(v27) : -2147467263;
    FreeLibrary(v4);
  }
  else
  {
    Error = ATL::AtlHresultFromLastError();
  }
  if ( Error < 0 || (v7 = 128, *(_DWORD *)&v27[4] < 6u) )
LABEL_11:
    v7 = 108;
  lParam = v7;
  memset_0(&lParam_4, 0, 0x7Cu);
  v8 = *(_QWORD *)(a2 + 8);
  lParam_4 = 16;
  SendMessageW(*(HWND *)v8, 0x41Cu, *(unsigned int *)(v8 + 24), (LPARAM)&lParam);
  v9 = hWnd;
  v22 = SendMessageW(hWnd, 0x418u, 0, 0);
  if ( v22 <= 0 )
    return 0;
  v11 = (HMENU)SendMessageW(v9, 0x52Eu, 0, 0);
  *(_BYTE *)(a2 + 16) = v11 != 0;
  PopupMenu = CreatePopupMenu();
  Rect = 0;
  GetClientRect(v9, &Rect);
  for ( i = 0; (int)i < v22; ++i )
  {
    *(_OWORD *)v28 = 0;
    v29 = 0;
    SendMessageW(v9, 0x417u, i, (LPARAM)v28);
    if ( (v28[1] & 8) == 0 )
    {
      *(_OWORD *)v27 = 0;
      SendMessageW(v9, 0x41Du, i, (LPARAM)v27);
      if ( *(int *)&v27[8] > Rect.right )
      {
        if ( (v28[1] & 0x100) != 0 )
        {
          if ( GetMenuItemCount(PopupMenu) <= 0 )
            continue;
          dwTypeData = 0;
          v15 = 2048;
          hSubMenu = 0;
        }
        else
        {
          v17 = v28[1] & 4;
          memset_0(&VersionInformation, 0, 0x190u);
          if ( *(_BYTE *)(a2 + 16) )
          {
            memset_0(&mii, 0, sizeof(mii));
            mii.cbSize = 80;
            mii.dwTypeData = (LPWSTR)&VersionInformation;
            mii.fMask = 20;
            mii.cch = 200;
            GetMenuItemInfoW(v11, i, 1, &mii);
            dwTypeData = mii.dwTypeData;
            hSubMenu = mii.hSubMenu;
            v15 = 17 - (v17 != 0);
          }
          else
          {
            mii.hbmpChecked = (HBITMAP)&VersionInformation;
            mii.hbmpUnchecked = (HBITMAP)200;
            mii.cbSize = 48;
            memset(&mii.fType, 0, 24);
            mii.fMask = 2;
            if ( SendMessageW(v9, 0x43Fu, SHIDWORD(v28[0]), (LPARAM)&mii) == -1
              || !lstrlenW((LPCWSTR)&VersionInformation) )
            {
              p_VersionInformation = (_OSVERSIONINFOW *)&String;
              StringW = LoadStringW(hInstance, HIDWORD(v28[0]), (LPWSTR)&VersionInformation, 200);
              v20 = 0;
              if ( StringW > 0 )
              {
                while ( 1 )
                {
                  v21 = v20 + 1;
                  if ( *((_WORD *)&VersionInformation.dwOSVersionInfoSize + v20) == 10 )
                    break;
                  v20 = (unsigned int)v21;
                  if ( v21 >= StringW )
                    goto LABEL_30;
                }
                p_VersionInformation = (_OSVERSIONINFOW *)((char *)&VersionInformation + 2 * v21);
              }
            }
            else
            {
              p_VersionInformation = &VersionInformation;
            }
LABEL_30:
            hSubMenu = (HMENU)SHIDWORD(v28[0]);
            dwTypeData = (const WCHAR *)p_VersionInformation;
            v15 = v17 == 0;
          }
        }
        AppendMenuW(PopupMenu, v15, (UINT_PTR)hSubMenu, dwTypeData);
      }
    }
  }
  if ( !GetMenuItemCount(PopupMenu) )
  {
    if ( PopupMenu )
      DestroyMenu(PopupMenu);
    MessageBeep(0xFFFFFFFF);
    return 0;
  }
  *(_QWORD *)a2 = PopupMenu;
  return 1;
}

```

## disassembly

```asm
0x180026dec  push    rbp
0x180026dee  push    rbx
0x180026def  push    rsi
0x180026df0  push    rdi
0x180026df1  push    r12
0x180026df3  push    r13
0x180026df5  push    r14
0x180026df7  push    r15
0x180026df9  lea     rbp, [rsp-1F8h]
0x180026e01  sub     rsp, 2F8h
0x180026e08  mov     rax, cs:__security_cookie
0x180026e0f  xor     rax, rsp
0x180026e12  mov     [rbp+230h+var_50], rax
0x180026e19  mov     r13, rdx
0x180026e1c  mov     [rbp+230h+VersionInformation.dwOSVersionInfoSize], 114h
0x180026e23  xor     edx, edx; Val
0x180026e25  lea     rcx, [rbp+230h+VersionInformation.dwMajorVersion]; void *
0x180026e29  mov     r8d, 110h; Size
0x180026e2f  call    memset_0
0x180026e34  lea     rcx, [rbp+230h+VersionInformation]; lpVersionInformation
0x180026e38  call    cs:__imp_GetVersionExW
0x180026e3e  test    eax, eax
0x180026e40  jz      short loc_180026EB9
0x180026e42  cmp     [rbp+230h+VersionInformation.dwMajorVersion], 6
0x180026e46  jb      short loc_180026EB9
0x180026e48  xorps   xmm0, xmm0
0x180026e4b  mov     dword ptr [rbp+230h+var_230], 14h
0x180026e52  xor     r8d, r8d; dwFlags
0x180026e55  lea     rcx, aComctl32Dll; "comctl32.dll"
0x180026e5c  xor     edx, edx; hFile
0x180026e5e  movdqu  xmmword ptr [rbp+230h+var_230+4], xmm0
0x180026e63  call    cs:__imp_LoadLibraryExW
0x180026e69  mov     rdi, rax
0x180026e6c  test    rax, rax
0x180026e6f  jnz     short loc_180026E7A
0x180026e71  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180026e76  mov     ebx, eax
0x180026e78  jmp     short loc_180026EAA
0x180026e7a  lea     rdx, aDllgetversion; "DllGetVersion"
0x180026e81  mov     rcx, rdi; hModule
0x180026e84  call    cs:__imp_GetProcAddress
0x180026e8a  test    rax, rax
0x180026e8d  jnz     short loc_180026E96
0x180026e8f  mov     ebx, 80004001h
0x180026e94  jmp     short loc_180026EA1
0x180026e96  lea     rcx, [rbp+230h+var_230]
0x180026e9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026e9f  mov     ebx, eax
0x180026ea1  mov     rcx, rdi; hLibModule
0x180026ea4  call    cs:__imp_FreeLibrary
0x180026eaa  test    ebx, ebx
0x180026eac  js      short loc_180026EB9
0x180026eae  cmp     dword ptr [rbp+230h+var_230+4], 6
0x180026eb2  mov     eax, 80h
0x180026eb7  jnb     short loc_180026EBE
0x180026eb9  mov     eax, 6Ch ; 'l'
0x180026ebe  xor     edx, edx; Val
0x180026ec0  mov     [rbp+230h+lParam], eax
0x180026ec3  lea     rcx, [rbp+230h+lParam+4]; void *
0x180026ec7  lea     r8d, [rdx+7Ch]; Size
0x180026ecb  call    memset_0
0x180026ed0  mov     rcx, [r13+8]
0x180026ed4  lea     r9, [rbp+230h+lParam]; lParam
0x180026ed8  mov     [rbp+230h+lParam+4], 10h
0x180026edf  mov     edx, 41Ch; Msg
0x180026ee4  mov     r8d, [rcx+18h]; wParam
0x180026ee8  mov     rcx, [rcx]; hWnd
0x180026eeb  call    cs:__imp_SendMessageW
0x180026ef1  mov     rdi, [rbp+230h+hWnd]
0x180026ef5  xor     r9d, r9d; lParam
0x180026ef8  mov     rcx, rdi; hWnd
0x180026efb  xor     r8d, r8d; wParam
0x180026efe  mov     edx, 418h; Msg
0x180026f03  call    cs:__imp_SendMessageW
0x180026f09  mov     qword ptr [rsp+330h+var_310], rax
0x180026f0e  test    eax, eax
0x180026f10  jg      short loc_180026F19
0x180026f12  xor     al, al
0x180026f14  jmp     loc_180027154
0x180026f19  xor     r9d, r9d; lParam
0x180026f1c  xor     r8d, r8d; wParam
0x180026f1f  mov     edx, 52Eh; Msg
0x180026f24  mov     rcx, rdi; hWnd
0x180026f27  call    cs:__imp_SendMessageW
0x180026f2d  test    rax, rax
0x180026f30  mov     rsi, rax
0x180026f33  setnz   al
0x180026f36  mov     [r13+10h], al
0x180026f3a  call    cs:__imp_CreatePopupMenu
0x180026f40  xorps   xmm0, xmm0
0x180026f43  lea     rdx, [rbp+230h+Rect]; lpRect
0x180026f47  mov     rcx, rdi; hWnd
0x180026f4a  mov     rbx, rax
0x180026f4d  movups  xmmword ptr [rbp+230h+Rect.left], xmm0
0x180026f51  call    cs:__imp_GetClientRect
0x180026f57  xor     r15d, r15d
0x180026f5a  xorps   xmm0, xmm0
0x180026f5d  mov     r8d, r15d; wParam
0x180026f60  lea     r9, [rbp+230h+var_218]; lParam
0x180026f64  mov     r14d, r15d
0x180026f67  mov     edx, 417h; Msg
0x180026f6c  mov     rcx, rdi; hWnd
0x180026f6f  movups  xmmword ptr [rbp+230h+var_218], xmm0
0x180026f73  movups  [rbp+230h+var_208], xmm0
0x180026f77  call    cs:__imp_SendMessageW
0x180026f7d  test    byte ptr [rbp+230h+var_218+8], 8
0x180026f81  jnz     loc_180027117
0x180026f87  xorps   xmm0, xmm0
0x180026f8a  lea     r9, [rbp+230h+var_230]; lParam
0x180026f8e  mov     r8d, r14d; wParam
0x180026f91  mov     edx, 41Dh; Msg
0x180026f96  mov     rcx, rdi; hWnd
0x180026f99  movups  xmmword ptr [rbp+230h+var_230], xmm0
0x180026f9d  call    cs:__imp_SendMessageW
0x180026fa3  mov     eax, [rbp+230h+Rect.right]
0x180026fa6  cmp     dword ptr [rbp+230h+var_230+8], eax
0x180026fa9  jle     loc_180027117
0x180026faf  test    byte ptr [rbp+230h+var_218+9], 1
0x180026fb3  jz      short loc_180026FD6
0x180026fb5  mov     rcx, rbx; hMenu
0x180026fb8  call    cs:__imp_GetMenuItemCount
0x180026fbe  test    eax, eax
0x180026fc0  jle     loc_180027117
0x180026fc6  xor     r9d, r9d
0x180026fc9  mov     edx, 800h
0x180026fce  xor     r8d, r8d
0x180026fd1  jmp     loc_18002710E
0x180026fd6  mov     r14b, byte ptr [rbp+230h+var_218+8]
0x180026fda  lea     rcx, [rbp+230h+VersionInformation]; void *
0x180026fde  xor     edx, edx; Val
0x180026fe0  mov     r8d, 190h; Size
0x180026fe6  and     r14b, 4
0x180026fea  call    memset_0
0x180026fef  cmp     byte ptr [r13+10h], 0
0x180026ff4  jz      short loc_180027055
0x180026ff6  xor     edx, edx; Val
0x180026ff8  lea     rcx, [rsp+330h+mii]; void *
0x180026ffd  lea     r8d, [rdx+50h]; Size
0x180027001  call    memset_0
0x180027006  lea     rax, [rbp+230h+VersionInformation]
0x18002700a  mov     [rsp+330h+mii.cbSize], 50h ; 'P'
0x180027012  lea     r9, [rsp+330h+mii]; lpmii
0x180027017  mov     [rsp+330h+mii.dwTypeData], rax
0x18002701c  mov     r8d, 1; fByPosition
0x180027022  mov     [rsp+330h+mii.fMask], 14h
0x18002702a  mov     edx, r15d; item
0x18002702d  mov     [rsp+330h+mii.cch], 0C8h
0x180027035  mov     rcx, rsi; hmenu
0x180027038  call    cs:__imp_GetMenuItemInfoW
0x18002703e  mov     r9, [rsp+330h+mii.dwTypeData]
0x180027043  neg     r14b
0x180027046  mov     r8, [rsp+330h+mii.hSubMenu]
0x18002704b  sbb     edx, edx
0x18002704d  add     edx, 11h
0x180027050  jmp     loc_18002710E
0x180027055  movsxd  r8, dword ptr [rbp+230h+var_218+4]; wParam
0x180027059  lea     rax, [rbp+230h+VersionInformation]
0x18002705d  xorps   xmm0, xmm0
0x180027060  mov     [rsp+330h+mii.hbmpChecked], rax
0x180027065  lea     r9, [rsp+330h+mii]; lParam
0x18002706a  mov     [rsp+330h+mii.hSubMenu], 0
0x180027073  mov     edx, 43Fh; Msg
0x180027078  mov     [rsp+330h+mii.hbmpUnchecked], 0C8h
0x180027081  mov     rcx, rdi; hWnd
0x180027084  mov     [rsp+330h+mii.cbSize], 30h ; '0'
0x18002708c  movdqu  xmmword ptr [rsp+330h+mii.fType], xmm0
0x180027092  mov     [rsp+330h+mii.fMask], 2
0x18002709a  call    cs:__imp_SendMessageW
0x1800270a0  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800270a4  jz      short loc_1800270BA
0x1800270a6  lea     rcx, [rbp+230h+VersionInformation]; lpString
0x1800270aa  call    cs:__imp_lstrlenW
0x1800270b0  test    eax, eax
0x1800270b2  jz      short loc_1800270BA
0x1800270b4  lea     r12, [rbp+230h+VersionInformation]
0x1800270b8  jmp     short loc_1800270FF
0x1800270ba  mov     edx, dword ptr [rbp+230h+var_218+4]; uID
0x1800270bd  lea     r8, [rbp+230h+VersionInformation]; lpBuffer
0x1800270c1  mov     rcx, cs:hInstance; hInstance
0x1800270c8  lea     r12, String
0x1800270cf  mov     r9d, 0C8h; cchBufferMax
0x1800270d5  call    cs:__imp_LoadStringW
0x1800270db  xor     ecx, ecx
0x1800270dd  test    eax, eax
0x1800270df  jle     short loc_1800270FF
0x1800270e1  cmp     word ptr [rbp+rcx*2+230h+VersionInformation.dwOSVersionInfoSize], 0Ah
0x1800270e7  lea     edx, [rcx+1]
0x1800270ea  jz      short loc_1800270F4
0x1800270ec  mov     ecx, edx
0x1800270ee  cmp     edx, eax
0x1800270f0  jl      short loc_1800270E1
0x1800270f2  jmp     short loc_1800270FF
0x1800270f4  movsxd  rax, edx
0x1800270f7  lea     r12, [rbp+230h+VersionInformation]
0x1800270fb  lea     r12, [r12+rax*2]
0x1800270ff  movsxd  r8, dword ptr [rbp+230h+var_218+4]; uIDNewItem
0x180027103  xor     edx, edx
0x180027105  test    r14b, r14b
0x180027108  mov     r9, r12; lpNewItem
0x18002710b  setz    dl; uFlags
0x18002710e  mov     rcx, rbx; hMenu
0x180027111  call    cs:__imp_AppendMenuW
0x180027117  inc     r15d
0x18002711a  cmp     r15d, [rsp+330h+var_310]
0x18002711f  jl      loc_180026F5A
0x180027125  mov     rcx, rbx; hMenu
0x180027128  call    cs:__imp_GetMenuItemCount
0x18002712e  test    eax, eax
0x180027130  jnz     short loc_18002714E
0x180027132  test    rbx, rbx
0x180027135  jz      short loc_180027140
0x180027137  mov     rcx, rbx; hMenu
0x18002713a  call    cs:__imp_DestroyMenu
0x180027140  or      ecx, 0FFFFFFFFh; uType
0x180027143  call    cs:__imp_MessageBeep
0x180027149  jmp     loc_180026F12
0x18002714e  mov     [r13+0], rbx
0x180027152  mov     al, 1
0x180027154  mov     rcx, [rbp+230h+var_50]
0x18002715b  xor     rcx, rsp; StackCookie
0x18002715e  call    __security_check_cookie
0x180027163  add     rsp, 2F8h
0x18002716a  pop     r15
0x18002716c  pop     r14
0x18002716e  pop     r13
0x180027170  pop     r12
0x180027172  pop     rdi
0x180027173  pop     rsi
0x180027174  pop     rbx
0x180027175  pop     rbp
0x180027176  retn
```
