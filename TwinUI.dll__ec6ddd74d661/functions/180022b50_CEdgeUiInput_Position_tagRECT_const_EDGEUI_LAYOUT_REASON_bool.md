# CEdgeUiInput::Position(tagRECT const *,EDGEUI_LAYOUT_REASON,bool)

- ea: `0x180022b50`
- end: `0x18002312d`
- name: `?Position@CEdgeUiInput@@UEAAJPEBUtagRECT@@W4EDGEUI_LAYOUT_REASON@@_N@Z`
- size: `1501`
- prototype: `int __high(const struct tagRECT *, enum EDGEUI_LAYOUT_REASON, bool)`
- caller_count: `0`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callees

- `0x180009dd0`
- `0x180009dfc`
- `0x180021cd8`
- `0x180022b50`
- `0x180142e10`
- `0x1803bb010`

## import_xrefs

- `USER32!SetWindowRgn` at `0x180022f54`
- `USER32!SetWindowRgn` at `0x180023087`
- `USER32!SetWindowRgn` at `0x180022f54`
- `USER32!SetWindowRgn` at `0x180023087`
- `GDI32!DeleteObject` at `0x18002309f`
- `GDI32!DeleteObject` at `0x18002309f`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180022f8a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!SetWindowPos` at `0x180022f8a`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180022fcd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!ShowWindow` at `0x180022fcd`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x180022cc5`
- `api-ms-win-rtcore-ntuser-window-l1-1-0!GetWindowRect` at `0x180022cc5`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180022deb`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x180022deb`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022bf5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800230e0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800230fa`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x180022bf5`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800230e0`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRectEmpty` at `0x1800230fa`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180022ce1`
- `api-ms-win-ntuser-rectangle-l1-1-0!EqualRect` at `0x180022ce1`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180022fb4`
- `api-ms-win-ntuser-rectangle-l1-1-0!IsRectEmpty` at `0x180022fb4`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022db3`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022f19`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022ffe`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022db3`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022f19`
- `api-ms-win-ntuser-rectangle-l1-1-0!SetRect` at `0x180022ffe`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CEdgeUiInput::Position(__int64 a1, struct tagRECT *a2, __int64 a3, char a4)
{
  CEdgeUiInput *v7; // rdi
  int v8; // r8d
  unsigned int v9; // ebx
  int v10; // r8d
  int v11; // r8d
  int v12; // r8d
  int v13; // r8d
  int v14; // r8d
  int v15; // r8d
  int v16; // r8d
  LONG v17; // r15d
  LONG top; // r13d
  LONG v19; // esi
  __int64 (__fastcall ***v20)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v21)(_QWORD, GUID *, void **); // rbx
  int v22; // eax
  int v23; // edx
  void *v24; // rcx
  __int64 (__fastcall ***v26)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v27)(_QWORD, GUID *, void **); // rbx
  int v28; // eax
  int v29; // edx
  int v30; // r9d
  void *v31; // rcx
  __int64 (__fastcall ***v32)(_QWORD, GUID *, void **); // rdi
  __int64 (__fastcall *v33)(_QWORD, GUID *, void **); // rbx
  int v34; // eax
  int left; // edx
  int right; // r9d
  _DWORD *v37; // r9
  BOOL v38; // eax
  int v39; // r8d
  int v40; // r9d
  int v41; // edx
  int yBottom; // [rsp+20h] [rbp-49h]
  int v43; // [rsp+40h] [rbp-29h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-21h] BYREF
  int v45; // [rsp+50h] [rbp-19h] BYREF
  int v46; // [rsp+54h] [rbp-15h] BYREF
  int v47; // [rsp+58h] [rbp-11h] BYREF
  struct tagRECT rc; // [rsp+60h] [rbp-9h] BYREF
  struct tagRECT Rect; // [rsp+70h] [rbp+7h] BYREF

  rc = 0;
  v7 = (CEdgeUiInput *)(a1 - 24);
  v8 = *(_DWORD *)(a1 - 24 + 136);
  v9 = 0;
  if ( !v8 )
    goto LABEL_18;
  v10 = v8 - 1;
  if ( !v10 )
    goto LABEL_18;
  v11 = v10 - 1;
  if ( !v11 )
  {
    *(_DWORD *)(a1 + 144) = (a2->bottom - a2->top) / 3;
    goto LABEL_10;
  }
  v12 = v11 - 1;
  if ( v12 )
  {
    v13 = v12 - 1;
    if ( !v13 )
    {
      ppvOut = 0;
      v46 = 0;
      v45 = 0;
      v47 = 0;
      v43 = 0;
      v32 = *(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 - 8);
      v33 = **v32;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      v34 = v33(v32, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &ppvOut);
      v9 = 0;
      if ( v34 >= 0
        && (*(int (__fastcall **)(void *, int *, int *, int *, int *))(*(_QWORD *)ppvOut + 24LL))(
             ppvOut,
             &v46,
             &v45,
             &v47,
             &v43) >= 0 )
      {
        if ( a4 )
        {
          right = a2->right;
          left = right - v47 - v46;
        }
        else
        {
          left = a2->left;
          right = v46 + a2->left + v47;
        }
        SetRect(&rc, left, a2->top, right, v45 + a2->top + v43);
      }
      goto LABEL_15;
    }
    v14 = v13 - 1;
    if ( !v14 )
    {
      ppvOut = 0;
      v43 = 0;
      v47 = 0;
      v45 = 0;
      v46 = 0;
      v26 = *(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 - 8);
      v27 = **v26;
      Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
      v28 = v27(v26, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &ppvOut);
      v9 = 0;
      if ( v28 >= 0
        && (*(int (__fastcall **)(void *, int *, int *, int *, int *))(*(_QWORD *)ppvOut + 24LL))(
             ppvOut,
             &v43,
             &v47,
             &v45,
             &v46) >= 0 )
      {
        if ( a4 )
        {
          v29 = a2->left;
          v30 = v43 + a2->left + v45;
        }
        else
        {
          v30 = a2->right;
          v29 = v30 - v45 - v43;
        }
        SetRect(&rc, v29, a2->top, v30, v47 + a2->top + v46);
      }
      goto LABEL_15;
    }
    v15 = v14 - 1;
    if ( !v15 )
      goto LABEL_18;
    v16 = v15 - 1;
    if ( !v16 )
    {
      v39 = a2->bottom - 20;
      yBottom = a2->bottom;
      if ( a4 )
      {
        v41 = a2->left;
        v40 = v41 + 20;
      }
      else
      {
        v40 = a2->right;
        v41 = v40 - 20;
      }
      SetRect(&rc, v41, v39, v40, yBottom);
      goto LABEL_18;
    }
    if ( v16 != 1 )
    {
      SetRectEmpty(&rc);
      return (unsigned int)-2147418113;
    }
LABEL_10:
    SetRectEmpty(&rc);
    v17 = a2->left;
    top = a2->top;
    v19 = a2->right;
    ppvOut = 0;
    v43 = 0;
    v46 = 0;
    v45 = 0;
    v47 = 0;
    v20 = *(__int64 (__fastcall ****)(_QWORD, GUID *, void **))(a1 - 8);
    v21 = **v20;
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(&ppvOut);
    v22 = v21(v20, &GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb, &ppvOut);
    v9 = 0;
    if ( v22 >= 0
      && (*(int (__fastcall **)(void *, int *, int *, int *, int *))(*(_QWORD *)ppvOut + 24LL))(
           ppvOut,
           &v43,
           &v46,
           &v45,
           &v47) >= 0 )
    {
      v23 = v43 + v45;
      if ( a4 )
        v19 -= v23;
      else
        v17 += v23;
    }
    rc.left = v17;
    rc.top = top;
    rc.right = v19;
    rc.bottom = top + 4;
LABEL_15:
    v24 = ppvOut;
    if ( ppvOut )
    {
      ppvOut = 0;
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
    }
    v7 = (CEdgeUiInput *)(a1 - 24);
    goto LABEL_18;
  }
  ppvOut = 0;
  v43 = 0;
  Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(&ppvOut);
  if ( IUnknown_QueryService(
         *(IUnknown **)(a1 - 8),
         (const GUID *const)&SID_EdgeUi,
         &GUID_6e6c3c52_5a5e_4b4b_a0f8_7fe12621a93e,
         &ppvOut) >= 0
    && (*(int (__fastcall **)(void *, int *))(*(_QWORD *)ppvOut + 80LL))(ppvOut, &v43) >= 0 )
  {
    Rect = *a2;
    if ( v43 )
    {
      switch ( v43 )
      {
        case 1:
          Rect.bottom = Rect.top + 1;
          break;
        case 2:
          Rect.left = Rect.right - 1;
          break;
        case 3:
          Rect.top = Rect.bottom - 1;
          break;
        default:
          SetRectEmpty(&Rect);
          break;
      }
    }
    else
    {
      Rect.right = Rect.left + 1;
    }
    rc = Rect;
  }
  v31 = ppvOut;
  if ( ppvOut )
  {
    ppvOut = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v31 + 16LL))(v31);
  }
LABEL_18:
  Rect = 0;
  if ( GetWindowRect(*(HWND *)(a1 + 120), &Rect) && EqualRect(&Rect, &rc) )
    return v9;
  SetWindowRgn(*(HWND *)(a1 + 120), 0, 0);
  SetWindowPos(*(HWND *)(a1 + 120), 0, rc.left, rc.top, rc.right - rc.left, rc.bottom - rc.top, 0x14u);
  if ( rc.left >= rc.right || rc.top >= rc.bottom )
  {
    v37 = (_DWORD *)(a1 + 112);
  }
  else
  {
    v37 = (_DWORD *)(a1 + 112);
    if ( (unsigned int)(*(_DWORD *)(a1 + 112) - 4) <= 3 )
    {
      ppvOut = 0;
      v9 = CEdgeUiInput::_ComputeCornerRegion(v7, rc.right - rc.left, rc.bottom - rc.top, a4, (HRGN *)&ppvOut);
      if ( (v9 & 0x80000000) == 0 && !SetWindowRgn(*(HWND *)(a1 + 120), (HRGN)ppvOut, 0) )
        DeleteObject(ppvOut);
      return v9;
    }
  }
  if ( *v37 == 8 || *v37 == 2 )
  {
    v38 = IsRectEmpty(&rc);
    ShowWindow(*(HWND *)(a1 + 120), !v38 ? 4 : 0);
  }
  return v9;
}

```

## disassembly

```asm
0x180022b50  mov     [rsp-8+arg_10], rbx
0x180022b55  push    rbp
0x180022b56  push    rsi
0x180022b57  push    rdi
0x180022b58  push    r12
0x180022b5a  push    r13
0x180022b5c  push    r14
0x180022b5e  push    r15
0x180022b60  lea     rbp, [rsp-27h]
0x180022b65  sub     rsp, 90h
0x180022b6c  mov     rax, cs:__security_cookie
0x180022b73  xor     rax, rsp
0x180022b76  mov     [rbp+57h+var_40], rax
0x180022b7a  mov     r12b, r9b
0x180022b7d  mov     rsi, rdx
0x180022b80  mov     r14, rcx
0x180022b83  xorps   xmm0, xmm0
0x180022b86  movdqu  xmmword ptr [rbp+57h+rc.left], xmm0
0x180022b8b  lea     rdi, [rcx-18h]
0x180022b8f  mov     r8d, [rdi+88h]
0x180022b96  xor     ebx, ebx
0x180022b98  test    r8d, r8d
0x180022b9b  jz      loc_180022CB6
0x180022ba1  sub     r8d, 1
0x180022ba5  jz      loc_180022CB6
0x180022bab  sub     r8d, 1
0x180022baf  jz      loc_180022F2B
0x180022bb5  sub     r8d, 1
0x180022bb9  jz      loc_180022DC5
0x180022bbf  sub     r8d, 1
0x180022bc3  jz      loc_180022E85
0x180022bc9  sub     r8d, 1
0x180022bcd  jz      loc_180022D1F
0x180022bd3  sub     r8d, 1
0x180022bd7  jz      loc_180022CB6
0x180022bdd  sub     r8d, 1
0x180022be1  jz      loc_180022FDE
0x180022be7  cmp     r8d, 1
0x180022beb  jnz     loc_1800230DC
0x180022bf1  lea     rcx, [rbp+57h+rc]; lprc
0x180022bf5  call    cs:__imp_SetRectEmpty
0x180022bfc  nop     dword ptr [rax+rax+00h]
0x180022c01  mov     r15d, [rsi]
0x180022c04  mov     r13d, [rsi+4]
0x180022c08  mov     esi, [rsi+8]
0x180022c0b  mov     [rbp+57h+ppvOut], rbx
0x180022c0f  mov     [rbp+57h+var_80], ebx
0x180022c12  mov     [rbp+57h+var_6C], ebx
0x180022c15  mov     [rbp+57h+var_70], ebx
0x180022c18  mov     [rbp+57h+var_68], ebx
0x180022c1b  mov     rdi, [r14-8]
0x180022c1f  mov     rax, [rdi]
0x180022c22  mov     rbx, [rax]
0x180022c25  lea     rcx, [rbp+57h+ppvOut]
0x180022c29  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022c2e  lea     r8, [rbp+57h+ppvOut]
0x180022c32  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x180022c39  mov     rcx, rdi
0x180022c3c  mov     rax, rbx
0x180022c3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c44  nop
0x180022c45  xor     ebx, ebx
0x180022c47  test    eax, eax
0x180022c49  js      short loc_180022C86
0x180022c4b  mov     rcx, [rbp+57h+ppvOut]
0x180022c4f  mov     rax, [rcx]
0x180022c52  lea     rdx, [rbp+57h+var_68]
0x180022c56  mov     qword ptr [rsp+0C0h+yBottom], rdx
0x180022c5b  lea     r9, [rbp+57h+var_70]
0x180022c5f  lea     r8, [rbp+57h+var_6C]
0x180022c63  lea     rdx, [rbp+57h+var_80]
0x180022c67  mov     rax, [rax+18h]
0x180022c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c70  test    eax, eax
0x180022c72  js      short loc_180022C86
0x180022c74  mov     edx, [rbp+57h+var_70]
0x180022c77  add     edx, [rbp+57h+var_80]
0x180022c7a  test    r12b, r12b
0x180022c7d  jnz     loc_180023125
0x180022c83  add     r15d, edx
0x180022c86  mov     [rbp+57h+rc.left], r15d
0x180022c8a  mov     [rbp+57h+rc.top], r13d
0x180022c8e  mov     [rbp+57h+rc.right], esi
0x180022c91  lea     eax, [r13+4]
0x180022c95  mov     [rbp+57h+rc.bottom], eax
0x180022c98  mov     rcx, [rbp+57h+ppvOut]
0x180022c9c  test    rcx, rcx
0x180022c9f  jz      short loc_180022CB2
0x180022ca1  mov     [rbp+57h+ppvOut], rbx
0x180022ca5  mov     rax, [rcx]
0x180022ca8  mov     rax, [rax+10h]
0x180022cac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022cb1  nop
0x180022cb2  lea     rdi, [r14-18h]
0x180022cb6  xorps   xmm0, xmm0
0x180022cb9  movups  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180022cbd  lea     rdx, [rbp+57h+Rect]; lpRect
0x180022cc1  mov     rcx, [r14+78h]; hWnd
0x180022cc5  call    cs:__imp_GetWindowRect
0x180022ccc  nop     dword ptr [rax+rax+00h]
0x180022cd1  test    eax, eax
0x180022cd3  jz      loc_180022F4B
0x180022cd9  lea     rdx, [rbp+57h+rc]; lprc2
0x180022cdd  lea     rcx, [rbp+57h+Rect]; lprc1
0x180022ce1  call    cs:__imp_EqualRect
0x180022ce8  nop     dword ptr [rax+rax+00h]
0x180022ced  test    eax, eax
0x180022cef  jz      loc_180022F4B
0x180022cf5  mov     eax, ebx
0x180022cf7  mov     rcx, [rbp+57h+var_40]
0x180022cfb  xor     rcx, rsp; StackCookie
0x180022cfe  call    __security_check_cookie
0x180022d03  mov     rbx, [rsp+0C0h+arg_10]
0x180022d0b  add     rsp, 90h
0x180022d12  pop     r15
0x180022d14  pop     r14
0x180022d16  pop     r13
0x180022d18  pop     r12
0x180022d1a  pop     rdi
0x180022d1b  pop     rsi
0x180022d1c  pop     rbp
0x180022d1d  retn
0x180022d1f  mov     [rbp+57h+ppvOut], rbx
0x180022d23  mov     [rbp+57h+var_80], ebx
0x180022d26  mov     [rbp+57h+var_68], ebx
0x180022d29  mov     [rbp+57h+var_70], ebx
0x180022d2c  mov     [rbp+57h+var_6C], ebx
0x180022d2f  mov     rdi, [rcx-8]
0x180022d33  mov     rax, [rdi]
0x180022d36  mov     rbx, [rax]
0x180022d39  lea     rcx, [rbp+57h+ppvOut]
0x180022d3d  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022d42  lea     r8, [rbp+57h+ppvOut]
0x180022d46  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x180022d4d  mov     rcx, rdi
0x180022d50  mov     rax, rbx
0x180022d53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d58  nop
0x180022d59  xor     ebx, ebx
0x180022d5b  test    eax, eax
0x180022d5d  js      short loc_180022DC0
0x180022d5f  mov     rcx, [rbp+57h+ppvOut]
0x180022d63  mov     rax, [rcx]
0x180022d66  lea     rdx, [rbp+57h+var_6C]
0x180022d6a  mov     qword ptr [rsp+0C0h+yBottom], rdx
0x180022d6f  lea     r9, [rbp+57h+var_70]
0x180022d73  lea     r8, [rbp+57h+var_68]
0x180022d77  lea     rdx, [rbp+57h+var_80]
0x180022d7b  mov     rax, [rax+18h]
0x180022d7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022d84  test    eax, eax
0x180022d86  js      short loc_180022DC0
0x180022d88  mov     r8d, [rsi+4]; yTop
0x180022d8c  mov     ecx, [rbp+57h+var_6C]
0x180022d8f  add     ecx, r8d
0x180022d92  add     ecx, [rbp+57h+var_68]
0x180022d95  mov     [rsp+0C0h+yBottom], ecx; yBottom
0x180022d99  lea     rcx, [rbp+57h+rc]; lprc
0x180022d9d  test    r12b, r12b
0x180022da0  jz      loc_18002300F
0x180022da6  mov     edx, [rsi]; xLeft
0x180022da8  mov     r9d, [rbp+57h+var_70]
0x180022dac  add     r9d, edx
0x180022daf  add     r9d, [rbp+57h+var_80]; xRight
0x180022db3  call    cs:__imp_SetRect
0x180022dba  nop     dword ptr [rax+rax+00h]
0x180022dbf  nop
0x180022dc0  jmp     loc_180022C98
0x180022dc5  mov     [rbp+57h+ppvOut], rbx
0x180022dc9  mov     [rbp+57h+var_80], ebx
0x180022dcc  lea     rcx, [rbp+57h+ppvOut]
0x180022dd0  call    ?InternalRelease@?$ComPtr@UIProjectCharmSession@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IProjectCharmSession>::InternalRelease(void)
0x180022dd5  lea     r9, [rbp+57h+ppvOut]; ppvOut
0x180022dd9  lea     r8, _GUID_6e6c3c52_5a5e_4b4b_a0f8_7fe12621a93e; riid
0x180022de0  lea     rdx, SID_EdgeUi; guidService
0x180022de7  mov     rcx, [r14-8]; punk
0x180022deb  call    cs:__imp_IUnknown_QueryService
0x180022df2  nop     dword ptr [rax+rax+00h]
0x180022df7  test    eax, eax
0x180022df9  js      short loc_180022E63
0x180022dfb  mov     rcx, [rbp+57h+ppvOut]
0x180022dff  mov     rax, [rcx]
0x180022e02  lea     rdx, [rbp+57h+var_80]
0x180022e06  mov     rax, [rax+50h]
0x180022e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e0f  test    eax, eax
0x180022e11  js      short loc_180022E63
0x180022e13  movups  xmm0, xmmword ptr [rsi]
0x180022e16  movdqu  xmmword ptr [rbp+57h+Rect.left], xmm0
0x180022e1b  mov     ecx, [rbp+57h+var_80]
0x180022e1e  test    ecx, ecx
0x180022e20  jz      loc_180023021
0x180022e26  sub     ecx, 1
0x180022e29  jz      loc_180023118
0x180022e2f  sub     ecx, 1
0x180022e32  jz      loc_18002310B
0x180022e38  cmp     ecx, 1
0x180022e3b  jnz     loc_1800230F6
0x180022e41  mov     eax, [rbp+57h+Rect.bottom]
0x180022e44  dec     eax
0x180022e46  mov     [rbp+57h+Rect.top], eax
0x180022e49  mov     eax, [rbp+57h+Rect.left]
0x180022e4c  mov     ecx, [rbp+57h+Rect.top]
0x180022e4f  mov     edx, [rbp+57h+Rect.right]
0x180022e52  mov     r8d, [rbp+57h+Rect.bottom]
0x180022e56  mov     [rbp+57h+rc.left], eax
0x180022e59  mov     [rbp+57h+rc.top], ecx
0x180022e5c  mov     [rbp+57h+rc.right], edx
0x180022e5f  mov     [rbp+57h+rc.bottom], r8d
0x180022e63  mov     rcx, [rbp+57h+ppvOut]
0x180022e67  test    rcx, rcx
0x180022e6a  jz      loc_180022CB6
0x180022e70  mov     [rbp+57h+ppvOut], rbx
0x180022e74  mov     rax, [rcx]
0x180022e77  mov     rax, [rax+10h]
0x180022e7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022e80  jmp     loc_180022CB6
0x180022e85  mov     [rbp+57h+ppvOut], rbx
0x180022e89  mov     [rbp+57h+var_6C], ebx
0x180022e8c  mov     [rbp+57h+var_70], ebx
0x180022e8f  mov     [rbp+57h+var_68], ebx
0x180022e92  mov     [rbp+57h+var_80], ebx
0x180022e95  mov     rdi, [rcx-8]
0x180022e99  mov     rax, [rdi]
0x180022e9c  mov     rbx, [rax]
0x180022e9f  lea     rcx, [rbp+57h+ppvOut]
0x180022ea3  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180022ea8  lea     r8, [rbp+57h+ppvOut]
0x180022eac  lea     rdx, _GUID_bd9269d0_df79_47e0_8cd2_78762eb6d1bb
0x180022eb3  mov     rcx, rdi
0x180022eb6  mov     rax, rbx
0x180022eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022ebe  nop
0x180022ebf  xor     ebx, ebx
0x180022ec1  test    eax, eax
0x180022ec3  js      short loc_180022F26
0x180022ec5  mov     rcx, [rbp+57h+ppvOut]
0x180022ec9  mov     rax, [rcx]
0x180022ecc  lea     rdx, [rbp+57h+var_80]
0x180022ed0  mov     qword ptr [rsp+0C0h+yBottom], rdx
0x180022ed5  lea     r9, [rbp+57h+var_68]
0x180022ed9  lea     r8, [rbp+57h+var_70]
0x180022edd  lea     rdx, [rbp+57h+var_6C]
0x180022ee1  mov     rax, [rax+18h]
0x180022ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022eea  test    eax, eax
0x180022eec  js      short loc_180022F26
0x180022eee  mov     r8d, [rsi+4]; yTop
0x180022ef2  mov     ecx, [rbp+57h+var_80]
0x180022ef5  add     ecx, r8d
0x180022ef8  add     ecx, [rbp+57h+var_70]
0x180022efb  mov     [rsp+0C0h+yBottom], ecx; yBottom
0x180022eff  lea     rcx, [rbp+57h+rc]; lprc
0x180022f03  test    r12b, r12b
0x180022f06  jnz     loc_1800230CA
0x180022f0c  mov     edx, [rsi]; xLeft
0x180022f0e  mov     r9d, [rbp+57h+var_68]
0x180022f12  add     r9d, edx
0x180022f15  add     r9d, [rbp+57h+var_6C]; xRight
0x180022f19  call    cs:__imp_SetRect
0x180022f20  nop     dword ptr [rax+rax+00h]
0x180022f25  nop
0x180022f26  jmp     loc_180022C98
0x180022f2b  mov     ecx, [rdx+0Ch]
0x180022f2e  sub     ecx, [rdx+4]
0x180022f31  mov     eax, 55555556h
0x180022f36  imul    ecx
0x180022f38  mov     eax, edx
0x180022f3a  shr     eax, 1Fh
0x180022f3d  add     edx, eax
0x180022f3f  mov     [r14+90h], edx
0x180022f46  jmp     loc_180022BF1
0x180022f4b  xor     r8d, r8d; bRedraw
0x180022f4e  xor     edx, edx; hRgn
0x180022f50  mov     rcx, [r14+78h]; hWnd
0x180022f54  call    cs:__imp_SetWindowRgn
0x180022f5b  nop     dword ptr [rax+rax+00h]
0x180022f60  mov     ecx, [rbp+57h+rc.bottom]
0x180022f63  mov     r9d, [rbp+57h+rc.top]; Y
0x180022f67  sub     ecx, r9d
0x180022f6a  mov     eax, [rbp+57h+rc.right]
0x180022f6d  mov     r8d, [rbp+57h+rc.left]; X
0x180022f71  sub     eax, r8d
0x180022f74  mov     [rsp+0C0h+uFlags], 14h; uFlags
0x180022f7c  mov     [rsp+0C0h+cy], ecx; cy
0x180022f80  mov     [rsp+0C0h+yBottom], eax; cx
0x180022f84  xor     edx, edx; hWndInsertAfter
0x180022f86  mov     rcx, [r14+78h]; hWnd
0x180022f8a  call    cs:__imp_SetWindowPos
0x180022f91  nop     dword ptr [rax+rax+00h]
0x180022f96  mov     edx, [rbp+57h+rc.right]
0x180022f99  cmp     [rbp+57h+rc.left], edx
0x180022f9c  jl      loc_18002302E
0x180022fa2  lea     r9, [r14+70h]
0x180022fa6  cmp     dword ptr [r9], 8
0x180022faa  jnz     loc_1800230B0
0x180022fb0  lea     rcx, [rbp+57h+rc]; lprc
0x180022fb4  call    cs:__imp_IsRectEmpty
0x180022fbb  nop     dword ptr [rax+rax+00h]
0x180022fc0  neg     eax
  ... truncated ...
```
