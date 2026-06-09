# CNetworkExplorerInfoBar::CreateMenu(HMENU__ * *)

- ea: `0x1800093b0`
- end: `0x180009495`
- name: `?CreateMenu@CNetworkExplorerInfoBar@@UEAAJPEAPEAUHMENU__@@@Z`
- size: `229`
- prototype: `__int64 __fastcall(CNetworkExplorerInfoBar *__hidden this, HMENU *)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x1800093b0`
- `0x18000e428`
- `0x18000e538`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009443`
- `USER32!GetSubMenu` at `0x180009415`
- `USER32!GetSubMenu` at `0x180009415`
- `USER32!RemoveMenu` at `0x180009429`
- `USER32!RemoveMenu` at `0x180009429`
- `USER32!DestroyMenu` at `0x180009432`
- `USER32!DestroyMenu` at `0x180009432`
- `USER32!LoadMenuW` at `0x180009402`
- `USER32!LoadMenuW` at `0x180009402`

## pseudocode

```c
__int64 __fastcall CNetworkExplorerInfoBar::CreateMenu(CNetworkExplorerInfoBar *this, HMENU *a2)
{
  int v3; // r8d
  int v5; // r8d
  unsigned int v6; // ebx
  unsigned int v7; // esi
  HMENU MenuW; // rax
  HMENU v9; // rbx
  HMENU SubMenu; // rdi
  unsigned int v11; // edx
  signed int LastError; // eax

  *a2 = 0;
  v3 = *((_DWORD *)this + 3);
  if ( v3 )
  {
    v5 = v3 - 1;
    if ( v5 && (unsigned int)(v5 - 1) >= 2 )
      return (unsigned int)-2147467259;
    v7 = 2004;
  }
  else
  {
    v7 = 2003;
  }
  MenuW = LoadMenuW(g_hInst, (LPCWSTR)v7);
  v9 = MenuW;
  if ( MenuW )
  {
    SubMenu = GetSubMenu(MenuW, 0);
    RemoveMenu(v9, 0, 0x400u);
    DestroyMenu(v9);
    if ( SubMenu )
    {
      v6 = 0;
LABEL_14:
      if ( v7 != 2003 && (*((_QWORD *)this + 3) || (int)LoadShieldBitmap((HBITMAP *)this + 3) >= 0) )
        SetMenuItemBitmap(SubMenu, v11, *((HBITMAP *)this + 3));
      *a2 = SubMenu;
      return v6;
    }
  }
  else
  {
    SubMenu = 0;
  }
  LastError = GetLastError();
  v6 = LastError;
  if ( LastError > 0 )
    v6 = (unsigned __int16)LastError | 0x80070000;
  if ( (v6 & 0x80000000) == 0 )
    goto LABEL_14;
  return v6;
}

```

## disassembly

```asm
0x1800093b0  push    rbx
0x1800093b2  push    rbp
0x1800093b3  push    rsi
0x1800093b4  push    rdi
0x1800093b5  push    r14
0x1800093b7  sub     rsp, 20h
0x1800093bb  mov     qword ptr [rdx], 0
0x1800093c2  mov     r14, rdx
0x1800093c5  mov     r8d, [rcx+0Ch]
0x1800093c9  mov     rbp, rcx
0x1800093cc  test    r8d, r8d
0x1800093cf  jz      short loc_1800093F4
0x1800093d1  sub     r8d, 1
0x1800093d5  jz      short loc_1800093ED
0x1800093d7  sub     r8d, 1
0x1800093db  jz      short loc_1800093ED
0x1800093dd  cmp     r8d, 1
0x1800093e1  jz      short loc_1800093ED
0x1800093e3  mov     ebx, 80004005h
0x1800093e8  jmp     loc_180009488
0x1800093ed  mov     esi, 7D4h
0x1800093f2  jmp     short loc_1800093F9
0x1800093f4  mov     esi, 7D3h
0x1800093f9  mov     rcx, cs:?g_hInst@@3PEAUHINSTANCE__@@EA; hInstance
0x180009400  mov     edx, esi; lpMenuName
0x180009402  call    cs:__imp_LoadMenuW
0x180009408  mov     rbx, rax
0x18000940b  test    rax, rax
0x18000940e  jz      short loc_180009441
0x180009410  xor     edx, edx; nPos
0x180009412  mov     rcx, rax; hMenu
0x180009415  call    cs:__imp_GetSubMenu
0x18000941b  xor     edx, edx; uPosition
0x18000941d  mov     r8d, 400h; uFlags
0x180009423  mov     rcx, rbx; hMenu
0x180009426  mov     rdi, rax
0x180009429  call    cs:__imp_RemoveMenu
0x18000942f  mov     rcx, rbx; hMenu
0x180009432  call    cs:__imp_DestroyMenu
0x180009438  test    rdi, rdi
0x18000943b  jz      short loc_180009443
0x18000943d  xor     ebx, ebx
0x18000943f  jmp     short loc_18000945C
0x180009441  xor     edi, edi
0x180009443  call    cs:__imp_GetLastError
0x180009449  mov     ebx, eax
0x18000944b  test    eax, eax
0x18000944d  jle     short loc_180009458
0x18000944f  movzx   ebx, ax
0x180009452  or      ebx, 80070000h
0x180009458  test    ebx, ebx
0x18000945a  js      short loc_180009488
0x18000945c  cmp     esi, 7D3h
0x180009462  jz      short loc_180009485
0x180009464  lea     rsi, [rbp+18h]
0x180009468  cmp     qword ptr [rsi], 0
0x18000946c  jnz     short loc_18000947A
0x18000946e  mov     rcx, rsi; HBITMAP *
0x180009471  call    ?LoadShieldBitmap@@YAJPEAPEAUHBITMAP__@@@Z; LoadShieldBitmap(HBITMAP__ * *)
0x180009476  test    eax, eax
0x180009478  js      short loc_180009485
0x18000947a  mov     r8, [rsi]; HBITMAP
0x18000947d  mov     rcx, rdi; hmenu
0x180009480  call    ?SetMenuItemBitmap@@YAXPEAUHMENU__@@IPEAUHBITMAP__@@@Z; SetMenuItemBitmap(HMENU__ *,uint,HBITMAP__ *)
0x180009485  mov     [r14], rdi
0x180009488  mov     eax, ebx
0x18000948a  add     rsp, 20h
0x18000948e  pop     r14
0x180009490  pop     rdi
0x180009491  pop     rsi
0x180009492  pop     rbp
0x180009493  pop     rbx
0x180009494  retn
```
