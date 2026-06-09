# WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<114229248,262400>>::PrepareChevronMenu(WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<114229248,262400>>::_ChevronMenuInfo &)

- ea: `0x1800657f0`
- end: `0x180065ade`
- name: `?PrepareChevronMenu@?$CFrameWindowImplBase@VCWindow@ATL@@V?$CWinTraits@$0GMPAAAA@$0EABAA@@2@@WTL@@QEAA_NAEAU_ChevronMenuInfo@12@@Z`
- size: `750`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180065ae4`

## callees

- `0x18003f800`
- `0x180040264`
- `0x180063464`
- `0x1800657f0`
- `0x180066358`

## import_xrefs

- `KERNEL32!lstrlenW` at `0x180065a16`
- `KERNEL32!lstrlenW` at `0x180065a16`
- `USER32!AppendMenuW` at `0x180065a7c`
- `USER32!AppendMenuW` at `0x180065a7c`
- `USER32!MessageBeep` at `0x180065aaa`
- `USER32!MessageBeep` at `0x180065aaa`
- `USER32!LoadStringW` at `0x180065a41`
- `USER32!LoadStringW` at `0x180065a41`
- `USER32!CreatePopupMenu` at `0x1800658a1`
- `USER32!CreatePopupMenu` at `0x1800658a1`
- `USER32!GetMenuItemInfoW` at `0x1800659a4`
- `USER32!GetMenuItemInfoW` at `0x1800659a4`
- `USER32!GetMenuItemCount` at `0x180065924`
- `USER32!GetMenuItemCount` at `0x180065a93`
- `USER32!GetMenuItemCount` at `0x180065924`
- `USER32!GetMenuItemCount` at `0x180065a93`
- `USER32!SendMessageW` at `0x180065852`
- `USER32!SendMessageW` at `0x18006586a`
- `USER32!SendMessageW` at `0x18006588e`
- `USER32!SendMessageW` at `0x1800658e3`
- `USER32!SendMessageW` at `0x180065909`
- `USER32!SendMessageW` at `0x180065a06`
- `USER32!SendMessageW` at `0x180065852`
- `USER32!SendMessageW` at `0x18006586a`
- `USER32!SendMessageW` at `0x18006588e`
- `USER32!SendMessageW` at `0x1800658e3`
- `USER32!SendMessageW` at `0x180065909`
- `USER32!SendMessageW` at `0x180065a06`
- `USER32!GetClientRect` at `0x1800658bd`
- `USER32!GetClientRect` at `0x1800658bd`

## pseudocode

```c
char __fastcall WTL::CFrameWindowImplBase<ATL::CWindow,ATL::CWinTraits<114229248,262400>>::PrepareChevronMenu(
        WTL::RunTimeHelper *a1,
        __int64 a2)
{
  __int64 v3; // rcx
  HWND v4; // rdi
  HMENU v6; // rsi
  UINT i; // r15d
  const WCHAR *dwTypeData; // r9
  UINT v9; // edx
  UINT_PTR hSubMenu; // r8
  char v11; // r14
  WCHAR *v12; // r12
  int StringW; // eax
  int j; // ecx
  int v15; // [rsp+20h] [rbp-E0h]
  HMENU PopupMenu; // [rsp+28h] [rbp-D8h] BYREF
  struct tagMENUITEMINFOW mii; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int lParam; // [rsp+80h] [rbp-80h] BYREF
  int lParam_4; // [rsp+84h] [rbp-7Ch] BYREF
  HWND hWnd; // [rsp+A8h] [rbp-58h]
  LPARAM v21[2]; // [rsp+100h] [rbp+0h] BYREF
  __int128 v22; // [rsp+110h] [rbp+10h]
  struct tagRECT Rect; // [rsp+120h] [rbp+20h] BYREF
  LPARAM v24[2]; // [rsp+130h] [rbp+30h] BYREF
  WCHAR String[200]; // [rsp+140h] [rbp+40h] BYREF

  lParam = WTL::RunTimeHelper::SizeOf_REBARBANDINFO(a1);
  memset_0(&lParam_4, 0, 0x7Cu);
  v3 = *(_QWORD *)(a2 + 8);
  lParam_4 = 16;
  SendMessageW(*(HWND *)v3, 0x41Cu, *(unsigned int *)(v3 + 24), (LPARAM)&lParam);
  v4 = hWnd;
  v15 = SendMessageW(hWnd, 0x418u, 0, 0);
  if ( v15 <= 0 )
    return 0;
  v6 = (HMENU)SendMessageW(v4, 0x52Eu, 0, 0);
  *(_BYTE *)(a2 + 16) = v6 != 0;
  PopupMenu = CreatePopupMenu();
  Rect = 0;
  GetClientRect(v4, &Rect);
  for ( i = 0; (int)i < v15; ++i )
  {
    *(_OWORD *)v21 = 0;
    v22 = 0;
    SendMessageW(v4, 0x417u, i, (LPARAM)v21);
    if ( (v21[1] & 8) == 0 )
    {
      *(_OWORD *)v24 = 0;
      SendMessageW(v4, 0x41Du, i, (LPARAM)v24);
      if ( SLODWORD(v24[1]) > Rect.right )
      {
        if ( (v21[1] & 0x100) != 0 )
        {
          if ( GetMenuItemCount(PopupMenu) <= 0 )
            continue;
          dwTypeData = 0;
          v9 = 2048;
          hSubMenu = 0;
        }
        else
        {
          v11 = v21[1] & 4;
          memset_0(String, 0, sizeof(String));
          if ( *(_BYTE *)(a2 + 16) )
          {
            memset_0(&mii, 0, sizeof(mii));
            mii.cbSize = 80;
            mii.dwTypeData = String;
            mii.fMask = 20;
            mii.cch = 200;
            GetMenuItemInfoW(v6, i, 1, &mii);
            dwTypeData = mii.dwTypeData;
            hSubMenu = (UINT_PTR)mii.hSubMenu;
            v9 = 17 - (v11 != 0);
          }
          else
          {
            mii.hbmpChecked = (HBITMAP)String;
            mii.hbmpUnchecked = (HBITMAP)200;
            mii.cbSize = 48;
            memset(&mii.fType, 0, 24);
            mii.fMask = 2;
            if ( SendMessageW(v4, 0x43Fu, SHIDWORD(v21[0]), (LPARAM)&mii) == -1 || !lstrlenW(String) )
            {
              v12 = (WCHAR *)&WindowName;
              StringW = LoadStringW(hInstance, HIDWORD(v21[0]), String, 200);
              for ( j = 0; j < StringW; ++j )
              {
                if ( String[j] == 10 )
                {
                  v12 = &String[j + 1];
                  break;
                }
              }
            }
            else
            {
              v12 = String;
            }
            hSubMenu = SHIDWORD(v21[0]);
            dwTypeData = v12;
            v9 = v11 == 0;
          }
        }
        AppendMenuW(PopupMenu, v9, hSubMenu, dwTypeData);
      }
    }
  }
  if ( !GetMenuItemCount(PopupMenu) )
  {
    WTL::CMenuT<0>::DestroyMenu(&PopupMenu);
    MessageBeep(0xFFFFFFFF);
    return 0;
  }
  *(_QWORD *)a2 = PopupMenu;
  return 1;
}

```

## disassembly

```asm
0x1800657f0  push    rbp
0x1800657f2  push    rbx
0x1800657f3  push    rsi
0x1800657f4  push    rdi
0x1800657f5  push    r12
0x1800657f7  push    r13
0x1800657f9  push    r14
0x1800657fb  push    r15
0x1800657fd  lea     rbp, [rsp-1E8h]
0x180065805  sub     rsp, 2E8h
0x18006580c  mov     rax, cs:__security_cookie
0x180065813  xor     rax, rsp
0x180065816  mov     [rbp+220h+var_50], rax
0x18006581d  mov     r13, rdx
0x180065820  call    ?SizeOf_REBARBANDINFO@RunTimeHelper@WTL@@YAIXZ; WTL::RunTimeHelper::SizeOf_REBARBANDINFO(void)
0x180065825  xor     edx, edx; Val
0x180065827  mov     dword ptr [rbp+220h+lParam], eax
0x18006582a  lea     rcx, [rbp+220h+lParam+4]; void *
0x18006582e  lea     r8d, [rdx+7Ch]; Size
0x180065832  call    memset_0
0x180065837  mov     rcx, [r13+8]
0x18006583b  lea     r9, [rbp+220h+lParam]; lParam
0x18006583f  mov     dword ptr [rbp+220h+lParam+4], 10h
0x180065846  mov     edx, 41Ch; Msg
0x18006584b  mov     r8d, [rcx+18h]; wParam
0x18006584f  mov     rcx, [rcx]; hWnd
0x180065852  call    cs:__imp_SendMessageW
0x180065858  mov     rdi, [rbp+220h+hWnd]
0x18006585c  xor     r9d, r9d; lParam
0x18006585f  mov     rcx, rdi; hWnd
0x180065862  xor     r8d, r8d; wParam
0x180065865  mov     edx, 418h; Msg
0x18006586a  call    cs:__imp_SendMessageW
0x180065870  mov     [rsp+320h+var_300], rax
0x180065875  test    eax, eax
0x180065877  jg      short loc_180065880
0x180065879  xor     al, al
0x18006587b  jmp     loc_180065ABB
0x180065880  xor     r9d, r9d; lParam
0x180065883  xor     r8d, r8d; wParam
0x180065886  mov     edx, 52Eh; Msg
0x18006588b  mov     rcx, rdi; hWnd
0x18006588e  call    cs:__imp_SendMessageW
0x180065894  test    rax, rax
0x180065897  mov     rsi, rax
0x18006589a  setnz   al
0x18006589d  mov     [r13+10h], al
0x1800658a1  call    cs:__imp_CreatePopupMenu
0x1800658a7  xorps   xmm0, xmm0
0x1800658aa  lea     rdx, [rbp+220h+Rect]; lpRect
0x1800658ae  mov     rcx, rdi; hWnd
0x1800658b1  mov     [rsp+320h+var_2F8], rax
0x1800658b6  movups  xmmword ptr [rbp+220h+Rect.left], xmm0
0x1800658ba  mov     rbx, rax
0x1800658bd  call    cs:__imp_GetClientRect
0x1800658c3  xor     r15d, r15d
0x1800658c6  xorps   xmm0, xmm0
0x1800658c9  mov     r8d, r15d; wParam
0x1800658cc  lea     r9, [rbp+220h+var_220]; lParam
0x1800658d0  mov     r14d, r15d
0x1800658d3  mov     edx, 417h; Msg
0x1800658d8  mov     rcx, rdi; hWnd
0x1800658db  movups  xmmword ptr [rbp+220h+var_220], xmm0
0x1800658df  movups  [rbp+220h+var_210], xmm0
0x1800658e3  call    cs:__imp_SendMessageW
0x1800658e9  test    byte ptr [rbp+220h+var_220+8], 8
0x1800658ed  jnz     loc_180065A82
0x1800658f3  xorps   xmm0, xmm0
0x1800658f6  lea     r9, [rbp+220h+var_1F0]; lParam
0x1800658fa  mov     r8d, r14d; wParam
0x1800658fd  mov     edx, 41Dh; Msg
0x180065902  mov     rcx, rdi; hWnd
0x180065905  movups  xmmword ptr [rbp+220h+var_1F0], xmm0
0x180065909  call    cs:__imp_SendMessageW
0x18006590f  mov     eax, [rbp+220h+Rect.right]
0x180065912  cmp     dword ptr [rbp+220h+var_1F0+8], eax
0x180065915  jle     loc_180065A82
0x18006591b  test    byte ptr [rbp+220h+var_220+9], 1
0x18006591f  jz      short loc_180065942
0x180065921  mov     rcx, rbx; hMenu
0x180065924  call    cs:__imp_GetMenuItemCount
0x18006592a  test    eax, eax
0x18006592c  jle     loc_180065A82
0x180065932  xor     r9d, r9d
0x180065935  mov     edx, 800h
0x18006593a  xor     r8d, r8d
0x18006593d  jmp     loc_180065A79
0x180065942  mov     r14b, byte ptr [rbp+220h+var_220+8]
0x180065946  lea     rcx, [rbp+220h+String]; void *
0x18006594a  xor     edx, edx; Val
0x18006594c  mov     r8d, 190h; Size
0x180065952  and     r14b, 4
0x180065956  call    memset_0
0x18006595b  cmp     byte ptr [r13+10h], 0
0x180065960  jz      short loc_1800659C1
0x180065962  xor     edx, edx; Val
0x180065964  lea     rcx, [rsp+320h+mii]; void *
0x180065969  lea     r8d, [rdx+50h]; Size
0x18006596d  call    memset_0
0x180065972  lea     rax, [rbp+220h+String]
0x180065976  mov     [rsp+320h+mii.cbSize], 50h ; 'P'
0x18006597e  lea     r9, [rsp+320h+mii]; lpmii
0x180065983  mov     [rsp+320h+mii.dwTypeData], rax
0x180065988  mov     r8d, 1; fByPosition
0x18006598e  mov     [rsp+320h+mii.fMask], 14h
0x180065996  mov     edx, r15d; item
0x180065999  mov     [rsp+320h+mii.cch], 0C8h
0x1800659a1  mov     rcx, rsi; hmenu
0x1800659a4  call    cs:__imp_GetMenuItemInfoW
0x1800659aa  mov     r9, [rsp+320h+mii.dwTypeData]
0x1800659af  neg     r14b
0x1800659b2  mov     r8, [rsp+320h+mii.hSubMenu]
0x1800659b7  sbb     edx, edx
0x1800659b9  add     edx, 11h
0x1800659bc  jmp     loc_180065A79
0x1800659c1  movsxd  r8, dword ptr [rbp+220h+var_220+4]; wParam
0x1800659c5  lea     rax, [rbp+220h+String]
0x1800659c9  xorps   xmm0, xmm0
0x1800659cc  mov     [rsp+320h+mii.hbmpChecked], rax
0x1800659d1  lea     r9, [rsp+320h+mii]; lParam
0x1800659d6  mov     [rsp+320h+mii.hSubMenu], 0
0x1800659df  mov     edx, 43Fh; Msg
0x1800659e4  mov     [rsp+320h+mii.hbmpUnchecked], 0C8h
0x1800659ed  mov     rcx, rdi; hWnd
0x1800659f0  mov     [rsp+320h+mii.cbSize], 30h ; '0'
0x1800659f8  movdqu  xmmword ptr [rsp+320h+mii.fType], xmm0
0x1800659fe  mov     [rsp+320h+mii.fMask], 2
0x180065a06  call    cs:__imp_SendMessageW
0x180065a0c  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180065a10  jz      short loc_180065A26
0x180065a12  lea     rcx, [rbp+220h+String]; lpString
0x180065a16  call    cs:__imp_lstrlenW
0x180065a1c  test    eax, eax
0x180065a1e  jz      short loc_180065A26
0x180065a20  lea     r12, [rbp+220h+String]
0x180065a24  jmp     short loc_180065A6A
0x180065a26  mov     edx, dword ptr [rbp+220h+var_220+4]; uID
0x180065a29  lea     r8, [rbp+220h+String]; lpBuffer
0x180065a2d  mov     rcx, cs:hInstance; hInstance
0x180065a34  lea     r12, WindowName
0x180065a3b  mov     r9d, 0C8h; cchBufferMax
0x180065a41  call    cs:__imp_LoadStringW
0x180065a47  xor     ecx, ecx
0x180065a49  cmp     ecx, eax
0x180065a4b  jge     short loc_180065A6A
0x180065a4d  lea     edx, [rcx+1]
0x180065a50  movsxd  rcx, ecx
0x180065a53  cmp     [rbp+rcx*2+220h+String], 0Ah
0x180065a59  jz      short loc_180065A5F
0x180065a5b  mov     ecx, edx
0x180065a5d  jmp     short loc_180065A49
0x180065a5f  movsxd  rax, edx
0x180065a62  lea     r12, [rbp+220h+String]
0x180065a66  lea     r12, [r12+rax*2]
0x180065a6a  movsxd  r8, dword ptr [rbp+220h+var_220+4]; uIDNewItem
0x180065a6e  xor     edx, edx
0x180065a70  test    r14b, r14b
0x180065a73  mov     r9, r12; lpNewItem
0x180065a76  setz    dl; uFlags
0x180065a79  mov     rcx, rbx; hMenu
0x180065a7c  call    cs:__imp_AppendMenuW
0x180065a82  inc     r15d
0x180065a85  cmp     r15d, dword ptr [rsp+320h+var_300]
0x180065a8a  jl      loc_1800658C6
0x180065a90  mov     rcx, rbx; hMenu
0x180065a93  call    cs:__imp_GetMenuItemCount
0x180065a99  test    eax, eax
0x180065a9b  jnz     short loc_180065AB5
0x180065a9d  lea     rcx, [rsp+320h+var_2F8]
0x180065aa2  call    ?DestroyMenu@?$CMenuT@$0A@@WTL@@QEAAHXZ; WTL::CMenuT<0>::DestroyMenu(void)
0x180065aa7  or      ecx, 0FFFFFFFFh; uType
0x180065aaa  call    cs:__imp_MessageBeep
0x180065ab0  jmp     loc_180065879
0x180065ab5  mov     [r13+0], rbx
0x180065ab9  mov     al, 1
0x180065abb  mov     rcx, [rbp+220h+var_50]
0x180065ac2  xor     rcx, rsp; StackCookie
0x180065ac5  call    __security_check_cookie
0x180065aca  add     rsp, 2E8h
0x180065ad1  pop     r15
0x180065ad3  pop     r14
0x180065ad5  pop     r13
0x180065ad7  pop     r12
0x180065ad9  pop     rdi
0x180065ada  pop     rsi
0x180065adb  pop     rbx
0x180065adc  pop     rbp
0x180065add  retn
```
