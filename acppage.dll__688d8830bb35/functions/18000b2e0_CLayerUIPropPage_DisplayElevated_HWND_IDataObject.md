# CLayerUIPropPage::DisplayElevated(HWND__ *,IDataObject *)

- ea: `0x18000b2e0`
- end: `0x18000b45c`
- name: `?DisplayElevated@CLayerUIPropPage@@UEAAJPEAUHWND__@@PEAUIDataObject@@@Z`
- size: `380`
- prototype: `__int64 __fastcall(CLayerUIPropPage *__hidden this, HWND, struct IDataObject *)`
- caller_count: `0`
- callee_count: `7`
- tags: ``

## callees

- `0x18000b2e0`
- `0x18000b6a8`
- `0x1800109a0`
- `0x1800109e4`
- `0x18001623a`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `USER32!SetThreadDpiAwarenessContext` at `0x18000b3fa`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b427`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b3fa`
- `USER32!SetThreadDpiAwarenessContext` at `0x18000b427`
- `SHELL32!SHParseDisplayName` at `0x18000b375`
- `SHELL32!SHParseDisplayName` at `0x18000b375`
- `SHELL32!__imp_ILFree` at `0x18000b437`
- `SHELL32!__imp_ILFree` at `0x18000b437`

## pseudocode

```c
__int64 __fastcall CLayerUIPropPage::DisplayElevated(CLayerUIPropPage *this, HWND a2, struct IDataObject *a3)
{
  HRESULT v6; // edi
  unsigned int v7; // r8d
  __int64 v8; // rax
  __int64 v9; // rbx
  LPITEMIDLIST ppidl; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v12; // [rsp+38h] [rbp-C8h] BYREF
  PROPSHEETHEADERW_V2 v13; // [rsp+40h] [rbp-C0h] BYREF
  unsigned __int16 v14[400]; // [rsp+A0h] [rbp-60h] BYREF

  ppidl = 0;
  v12 = 0;
  memset_0(&v13, 0, sizeof(v13));
  *((_DWORD *)this + 147) = 1;
  v6 = (*(__int64 (__fastcall **)(char *, _QWORD, struct IDataObject *, _QWORD))(*((_QWORD *)this + 1) + 24LL))(
         (char *)this + 8,
         0,
         a3,
         0);
  if ( v6 >= 0 )
  {
    v6 = SHParseDisplayName((PCWSTR)this + 20, 0, &ppidl, 0, 0);
    if ( v6 >= 0 )
    {
      if ( GetCaptionFromPidl(ppidl, v14, v7) < 0 )
        v14[0] = 0;
      v13.hInstance = g_hInstance;
      v13.dwSize = 96;
      v13.pszCaption = v14;
      v13.hwndParent = a2;
      v13.ppsp = (LPCPROPSHEETPAGEW)&v12;
      v8 = *((_QWORD *)this + 2);
      v13.dwFlags = 33554433;
      v6 = (*(__int64 (__fastcall **)(char *, __int64 (__fastcall *)(struct _PSP *, __int64), PROPSHEETHEADERW_V2 *))(v8 + 24))(
             (char *)this + 16,
             AddPropSheetPage,
             &v13);
      if ( v6 >= 0 )
      {
        v9 = SetThreadDpiAwarenessContext(-4);
        EnableDpiScaledPadding(1);
        v6 = 0;
        if ( PropertySheetW(&v13) < 0 )
          v6 = -2147467259;
        SetThreadDpiAwarenessContext(v9);
      }
    }
  }
  if ( ppidl )
    ILFree(ppidl);
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18000b2e0  push    rbp
0x18000b2e2  push    rbx
0x18000b2e3  push    rsi
0x18000b2e4  push    rdi
0x18000b2e5  push    r14
0x18000b2e7  lea     rbp, [rsp-2D0h]
0x18000b2ef  sub     rsp, 3D0h
0x18000b2f6  mov     rax, cs:__security_cookie
0x18000b2fd  xor     rax, rsp
0x18000b300  mov     [rbp+2F0h+var_30], rax
0x18000b307  mov     r14, rdx
0x18000b30a  mov     [rsp+3F0h+ppidl], 0
0x18000b313  xor     edx, edx; Val
0x18000b315  mov     [rsp+3F0h+var_3B8], 0
0x18000b31e  mov     rbx, r8
0x18000b321  mov     rsi, rcx
0x18000b324  lea     rcx, [rsp+3F0h+var_3B0]; void *
0x18000b329  lea     r8d, [rdx+60h]; Size
0x18000b32d  call    memset_0
0x18000b332  lea     rcx, [rsi+8]
0x18000b336  mov     dword ptr [rsi+24Ch], 1
0x18000b340  mov     rax, [rcx]
0x18000b343  xor     r9d, r9d
0x18000b346  mov     r8, rbx
0x18000b349  xor     edx, edx
0x18000b34b  mov     rax, [rax+18h]
0x18000b34f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b354  mov     edi, eax
0x18000b356  test    eax, eax
0x18000b358  js      loc_18000B42D
0x18000b35e  lea     rcx, [rsi+28h]; pszName
0x18000b362  mov     [rsp+3F0h+psfgaoOut], 0; psfgaoOut
0x18000b36b  xor     r9d, r9d; sfgaoIn
0x18000b36e  lea     r8, [rsp+3F0h+ppidl]; ppidl
0x18000b373  xor     edx, edx; pbc
0x18000b375  call    cs:__imp_SHParseDisplayName
0x18000b37b  mov     edi, eax
0x18000b37d  test    eax, eax
0x18000b37f  js      loc_18000B42D
0x18000b385  mov     rcx, [rsp+3F0h+ppidl]; struct _ITEMIDLIST *
0x18000b38a  lea     rdx, [rbp+2F0h+var_350]; unsigned __int16 *
0x18000b38e  call    ?GetCaptionFromPidl@@YAJPEFAU_ITEMIDLIST@@PEAGK@Z; GetCaptionFromPidl(_ITEMIDLIST *,ushort *,ulong)
0x18000b393  test    eax, eax
0x18000b395  jns     short loc_18000B39D
0x18000b397  xor     eax, eax
0x18000b399  mov     [rbp+2F0h+var_350], ax
0x18000b39d  mov     rax, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x18000b3a4  lea     rcx, [rsi+10h]
0x18000b3a8  mov     [rsp+3F0h+var_3B0.hInstance], rax
0x18000b3ad  lea     r8, [rsp+3F0h+var_3B0]
0x18000b3b2  lea     rax, [rbp+2F0h+var_350]
0x18000b3b6  mov     [rsp+3F0h+var_3B0.dwSize], 60h ; '`'
0x18000b3be  mov     [rsp+3F0h+var_3B0.pszCaption], rax
0x18000b3c3  lea     rdx, ?AddPropSheetPage@@YAHPEAU_PSP@@_J@Z; AddPropSheetPage(_PSP *,__int64)
0x18000b3ca  lea     rax, [rsp+3F0h+var_3B8]
0x18000b3cf  mov     [rsp+3F0h+var_3B0.hwndParent], r14
0x18000b3d4  mov     qword ptr [rsp+3F0h+var_3B0.38h], rax
0x18000b3d9  mov     rax, [rcx]
0x18000b3dc  mov     [rsp+3F0h+var_3B0.dwFlags], 2000001h
0x18000b3e4  mov     rax, [rax+18h]
0x18000b3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b3ed  mov     edi, eax
0x18000b3ef  test    eax, eax
0x18000b3f1  js      short loc_18000B42D
0x18000b3f3  mov     rcx, 0FFFFFFFFFFFFFFFCh
0x18000b3fa  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000b400  mov     ecx, 1
0x18000b405  mov     rbx, rax
0x18000b408  call    EnableDpiScaledPadding
0x18000b40d  lea     rcx, [rsp+3F0h+var_3B0]; LPCPROPSHEETHEADERW
0x18000b412  call    PropertySheetW
0x18000b417  xor     edi, edi
0x18000b419  mov     ecx, 80004005h
0x18000b41e  test    rax, rax
0x18000b421  cmovs   edi, ecx
0x18000b424  mov     rcx, rbx
0x18000b427  call    cs:__imp_SetThreadDpiAwarenessContext
0x18000b42d  mov     rcx, [rsp+3F0h+ppidl]; pidl
0x18000b432  test    rcx, rcx
0x18000b435  jz      short loc_18000B43D
0x18000b437  call    cs:__imp_ILFree
0x18000b43d  mov     eax, edi
0x18000b43f  mov     rcx, [rbp+2F0h+var_30]
0x18000b446  xor     rcx, rsp; StackCookie
0x18000b449  call    __security_check_cookie
0x18000b44e  add     rsp, 3D0h
0x18000b455  pop     r14
0x18000b457  pop     rdi
0x18000b458  pop     rsi
0x18000b459  pop     rbx
0x18000b45a  pop     rbp
0x18000b45b  retn
```
