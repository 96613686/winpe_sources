# ImmersiveContextMenuHelper::RemoveOwnerDrawFromMenu(HMENU__ *,HWND__ *)

- ea: `0x18006bd5c`
- end: `0x18006be22`
- name: `?RemoveOwnerDrawFromMenu@ImmersiveContextMenuHelper@@YAXPEAUHMENU__@@PEAUHWND__@@@Z`
- size: `198`
- prototype: `void __fastcall(HMENU this, HMENU hWnd, HWND)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task`

## callers

- `0x18003f930`
- `0x18006b3f8`

## callees

- `0x18001e260`
- `0x1800206e8`
- `0x18006bd5c`
- `0x18006c268`

## import_xrefs

- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18006be03`
- `ext-ms-win-ntuser-window-l1-1-0!RemovePropW` at `0x18006be03`
- `GDI32!DeleteObject` at `0x18006bdb1`
- `GDI32!DeleteObject` at `0x18006bdb1`
- `USER32!SetMenuInfo` at `0x18006bdc6`
- `USER32!SetMenuInfo` at `0x18006bdc6`
- `USER32!GetMenuInfo` at `0x18006bd9e`
- `USER32!GetMenuInfo` at `0x18006bd9e`

## pseudocode

```c
void __fastcall ImmersiveContextMenuHelper::RemoveOwnerDrawFromMenu(HMENU this, HMENU hWnd, HWND a3)
{
  LPCWSTR lpString[3]; // [rsp+20h] [rbp-40h] BYREF
  MENUINFO v6; // [rsp+38h] [rbp-28h] BYREF

  ImmersiveContextMenuHelper::_RemoveOwnerDrawFromMenuWorker((ImmersiveContextMenuHelper *)this, hWnd, a3);
  v6.cbSize = 40;
  v6.fMask = 2;
  memset(&v6.dwStyle, 0, 32);
  if ( GetMenuInfo(this, &v6) && v6.hbrBack )
  {
    DeleteObject(v6.hbrBack);
    v6.hbrBack = 0;
    SetMenuInfo(this, &v6);
  }
  memset(lpString, 0, sizeof(lpString));
  if ( (int)Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::InitializeFormat(
              (__int64)lpString,
              L"ImmersiveContextMenuArray_%lu",
              0xFFFFFFFFLL) >= 0 )
    RemovePropW((HWND)hWnd, lpString[0]);
  Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<unsigned short>>::_Free(lpString);
}

```

## disassembly

```asm
0x18006bd5c  mov     [rsp-8+arg_0], rbx
0x18006bd61  mov     [rsp-8+arg_8], rdi
0x18006bd66  push    rbp
0x18006bd67  mov     rbp, rsp
0x18006bd6a  sub     rsp, 60h
0x18006bd6e  mov     rdi, rdx
0x18006bd71  mov     rbx, rcx
0x18006bd74  call    ?_RemoveOwnerDrawFromMenuWorker@ImmersiveContextMenuHelper@@YAXPEAUHMENU__@@PEAUHWND__@@@Z; ImmersiveContextMenuHelper::_RemoveOwnerDrawFromMenuWorker(HMENU__ *,HWND__ *)
0x18006bd79  xorps   xmm0, xmm0
0x18006bd7c  mov     [rbp+var_28.cbSize], 28h ; '('
0x18006bd83  xorps   xmm1, xmm1
0x18006bd86  mov     [rbp+var_28.fMask], 2
0x18006bd8d  lea     rdx, [rbp+var_28]; LPMENUINFO
0x18006bd91  mov     rcx, rbx; HMENU
0x18006bd94  movdqu  xmmword ptr [rbp+var_28.dwStyle], xmm0
0x18006bd99  movdqu  xmmword ptr [rbp+var_28.dwContextHelpID], xmm1
0x18006bd9e  call    cs:__imp_GetMenuInfo
0x18006bda4  test    eax, eax
0x18006bda6  jz      short loc_18006BDCC
0x18006bda8  mov     rcx, [rbp+var_28.hbrBack]; ho
0x18006bdac  test    rcx, rcx
0x18006bdaf  jz      short loc_18006BDCC
0x18006bdb1  call    cs:__imp_DeleteObject
0x18006bdb7  lea     rdx, [rbp+var_28]; LPCMENUINFO
0x18006bdbb  mov     [rbp+var_28.hbrBack], 0
0x18006bdc3  mov     rcx, rbx; HMENU
0x18006bdc6  call    cs:__imp_SetMenuInfo
0x18006bdcc  or      r8d, 0FFFFFFFFh
0x18006bdd0  mov     [rbp+lpString], 0
0x18006bdd8  lea     rdx, aImmersiveconte; "ImmersiveContextMenuArray_%lu"
0x18006bddf  mov     [rbp+var_38], 0
0x18006bde7  lea     rcx, [rbp+lpString]
0x18006bdeb  mov     [rbp+var_30], 0
0x18006bdf3  call    ?InitializeFormat@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@QEAAJPEBGZZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::InitializeFormat(ushort const *,...)
0x18006bdf8  test    eax, eax
0x18006bdfa  js      short loc_18006BE09
0x18006bdfc  mov     rdx, [rbp+lpString]; lpString
0x18006be00  mov     rcx, rdi; hWnd
0x18006be03  call    cs:__imp_RemovePropW
0x18006be09  lea     rcx, [rbp+lpString]
0x18006be0d  call    ?_Free@?$NativeString@V?$CoTaskMemPolicy@G@Internal@Windows@@@Internal@Windows@@AEAAXXZ; Windows::Internal::NativeString<Windows::Internal::CoTaskMemPolicy<ushort>>::_Free(void)
0x18006be12  mov     rbx, [rsp+60h+arg_0]
0x18006be17  mov     rdi, [rsp+60h+arg_8]
0x18006be1c  add     rsp, 60h
0x18006be20  pop     rbp
0x18006be21  retn
```
