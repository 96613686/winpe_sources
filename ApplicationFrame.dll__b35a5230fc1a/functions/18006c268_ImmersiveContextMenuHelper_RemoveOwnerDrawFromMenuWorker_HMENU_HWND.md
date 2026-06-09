# ImmersiveContextMenuHelper::_RemoveOwnerDrawFromMenuWorker(HMENU__ *,HWND__ *)

- ea: `0x18006c268`
- end: `0x18006c3cc`
- name: `?_RemoveOwnerDrawFromMenuWorker@ImmersiveContextMenuHelper@@YAXPEAUHMENU__@@PEAUHWND__@@@Z`
- size: `356`
- prototype: `void __fastcall(ImmersiveContextMenuHelper *__hidden this, HMENU, HWND)`
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config, service_task`

## callers

- `0x18006bd5c`
- `0x18006c268`

## callees

- `0x18001e260`
- `0x1800206e8`
- `0x180041ec0`
- `0x1800446fc`
- `0x18006b984`
- `0x18006c268`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18006c365`
- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18006c365`
- `USER32!GetMenuItemInfoW` at `0x18006c2b3`
- `USER32!GetMenuItemInfoW` at `0x18006c2b3`
- `USER32!SetMenuItemInfoW` at `0x18006c399`
- `USER32!SetMenuItemInfoW` at `0x18006c399`

## pseudocode

```c
void __fastcall ImmersiveContextMenuHelper::_RemoveOwnerDrawFromMenuWorker(
        ImmersiveContextMenuHelper *this,
        HMENU a2,
        HWND a3)
{
  UINT v3; // edi
  int Error; // esi
  unsigned int v7; // r9d
  struct ContextMenuRenderingData *ContextMenuDataForItem; // rax
  struct ContextMenuRenderingData *v9; // rbx
  HWND v10; // r8
  LPCWSTR lpString[4]; // [rsp+20h] [rbp-99h] BYREF
  struct tagMENUITEMINFOW mii; // [rsp+40h] [rbp-79h] BYREF
  MENUITEMINFOW v13; // [rsp+90h] [rbp-29h] BYREF

  v3 = 0;
  do
  {
    memset_0(&mii, 0, sizeof(mii));
    mii.cbSize = 80;
    mii.fMask = 422;
    if ( GetMenuItemInfoW((HMENU)this, v3, 1, &mii) )
    {
      Error = 0;
    }
    else
    {
      Error = ResultFromKnownLastError();
      if ( Error < 0 )
        goto LABEL_15;
    }
    memset_0(&v13, 0, sizeof(v13));
    v13.cbSize = 80;
    v13.fMask = 384;
    v13.fType = mii.fType & 0xFFFFFEFF;
    if ( mii.dwItemData )
    {
      ContextMenuDataForItem = ImmersiveContextMenuHelper::GetContextMenuDataForItem(
                                 (HWND)a2,
                                 (HWND)mii.dwItemData,
                                 mii.wID,
                                 v7);
      v9 = ContextMenuDataForItem;
      if ( ContextMenuDataForItem )
      {
        if ( ContextMenuDataForItem == (struct ContextMenuRenderingData *)mii.dwItemData )
        {
          v13.fMask |= 0x20u;
          v13.dwItemData = 0;
        }
        memset(lpString, 0, 24);
        if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
                    (__int64)lpString,
                    L"ImmersiveContextMenuArray_%lu-%lu",
                    mii.dwItemData,
                    mii.wID) >= 0 )
          RemovePropW((HWND)a2, lpString[0]);
        Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free((__int64)lpString);
        if ( *((_QWORD *)v9 + 4) )
        {
          v13.hbmpItem = (HBITMAP)*((_QWORD *)v9 + 4);
          *((_QWORD *)v9 + 4) = 0;
        }
      }
    }
    SetMenuItemInfoW((HMENU)this, v3, 1, &v13);
    if ( mii.hSubMenu )
      ImmersiveContextMenuHelper::_RemoveOwnerDrawFromMenuWorker((ImmersiveContextMenuHelper *)mii.hSubMenu, a2, v10);
LABEL_15:
    ++v3;
  }
  while ( Error >= 0 );
}

```

## disassembly

```asm
0x18006c268  push    rbp
0x18006c26a  push    rbx
0x18006c26b  push    rsi
0x18006c26c  push    rdi
0x18006c26d  push    r13
0x18006c26f  push    r14
0x18006c271  push    r15
0x18006c273  lea     rbp, [rsp-27h]
0x18006c278  sub     rsp, 0E0h
0x18006c27f  xor     edi, edi
0x18006c281  mov     r14, rdx
0x18006c284  mov     r15, rcx
0x18006c287  lea     r13d, [rdi+50h]
0x18006c28b  mov     r8, r13; Size
0x18006c28e  lea     rcx, [rbp+57h+mii]; void *
0x18006c292  xor     edx, edx; Val
0x18006c294  call    memset_0
0x18006c299  lea     r9, [rbp+57h+mii]; lpmii
0x18006c29d  mov     [rbp+57h+mii.cbSize], r13d
0x18006c2a1  mov     r8d, 1; fByPosition
0x18006c2a7  mov     [rbp+57h+mii.fMask], 1A6h
0x18006c2ae  mov     edx, edi; item
0x18006c2b0  mov     rcx, r15; hmenu
0x18006c2b3  call    cs:__imp_GetMenuItemInfoW
0x18006c2b9  test    eax, eax
0x18006c2bb  jz      short loc_18006C2C1
0x18006c2bd  xor     esi, esi
0x18006c2bf  jmp     short loc_18006C2D0
0x18006c2c1  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x18006c2c6  mov     esi, eax
0x18006c2c8  test    eax, eax
0x18006c2ca  js      loc_18006C3B0
0x18006c2d0  mov     r8, r13; Size
0x18006c2d3  lea     rcx, [rbp+57h+var_80]; void *
0x18006c2d7  xor     edx, edx; Val
0x18006c2d9  call    memset_0
0x18006c2de  mov     ecx, [rbp+57h+mii.fType]
0x18006c2e1  mov     rdx, [rbp+57h+mii.dwItemData]; HWND
0x18006c2e5  btr     ecx, 8
0x18006c2e9  mov     [rbp+57h+var_80.cbSize], r13d
0x18006c2ed  mov     [rbp+57h+var_80.fMask], 180h
0x18006c2f4  mov     [rbp+57h+var_80.fType], ecx
0x18006c2f7  test    rdx, rdx
0x18006c2fa  jz      loc_18006C38A
0x18006c300  mov     r8d, [rbp+57h+mii.wID]; unsigned __int64
0x18006c304  mov     rcx, r14; hWnd
0x18006c307  call    ?GetContextMenuDataForItem@ImmersiveContextMenuHelper@@YAPEAUContextMenuRenderingData@@PEAUHWND__@@_KI@Z; ImmersiveContextMenuHelper::GetContextMenuDataForItem(HWND__ *,unsigned __int64,uint)
0x18006c30c  mov     rbx, rax
0x18006c30f  test    rax, rax
0x18006c312  jz      short loc_18006C38A
0x18006c314  mov     r8, [rbp+57h+mii.dwItemData]
0x18006c318  cmp     rax, r8
0x18006c31b  jnz     short loc_18006C329
0x18006c31d  or      [rbp+57h+var_80.fMask], 20h
0x18006c321  mov     [rbp+57h+var_80.dwItemData], 0
0x18006c329  mov     r9d, [rbp+57h+mii.wID]
0x18006c32d  lea     rdx, aImmersiveconte_0; "ImmersiveContextMenuArray_%lu-%lu"
0x18006c334  lea     rcx, [rsp+110h+lpString]
0x18006c339  mov     [rsp+110h+lpString], 0
0x18006c342  mov     [rsp+110h+var_E8], 0
0x18006c34b  mov     [rsp+110h+var_E0], 0
0x18006c354  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18006c359  test    eax, eax
0x18006c35b  js      short loc_18006C36B
0x18006c35d  mov     rdx, [rsp+110h+lpString]; lpString
0x18006c362  mov     rcx, r14; hWnd
0x18006c365  call    cs:__imp_RemovePropW
0x18006c36b  lea     rcx, [rsp+110h+lpString]
0x18006c370  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006c375  mov     rax, [rbx+20h]
0x18006c379  test    rax, rax
0x18006c37c  jz      short loc_18006C38A
0x18006c37e  mov     [rbp+57h+var_80.hbmpItem], rax
0x18006c382  mov     qword ptr [rbx+20h], 0
0x18006c38a  lea     r9, [rbp+57h+var_80]; lpmii
0x18006c38e  mov     r8d, 1; fByPositon
0x18006c394  mov     edx, edi; item
0x18006c396  mov     rcx, r15; hmenu
0x18006c399  call    cs:__imp_SetMenuItemInfoW
0x18006c39f  mov     rcx, [rbp+57h+mii.hSubMenu]; this
0x18006c3a3  test    rcx, rcx
0x18006c3a6  jz      short loc_18006C3B0
0x18006c3a8  mov     rdx, r14; HMENU
0x18006c3ab  call    ?_RemoveOwnerDrawFromMenuWorker@ImmersiveContextMenuHelper@@YAXPEAUHMENU__@@PEAUHWND__@@@Z; ImmersiveContextMenuHelper::_RemoveOwnerDrawFromMenuWorker(HMENU__ *,HWND__ *)
0x18006c3b0  inc     edi
0x18006c3b2  test    esi, esi
0x18006c3b4  jns     loc_18006C28B
0x18006c3ba  add     rsp, 0E0h
0x18006c3c1  pop     r15
0x18006c3c3  pop     r14
0x18006c3c5  pop     r13
0x18006c3c7  pop     rdi
0x18006c3c8  pop     rsi
0x18006c3c9  pop     rbx
0x18006c3ca  pop     rbp
0x18006c3cb  retn
```
