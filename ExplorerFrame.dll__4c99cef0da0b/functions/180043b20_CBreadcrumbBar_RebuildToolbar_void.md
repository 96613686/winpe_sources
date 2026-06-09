# CBreadcrumbBar::_RebuildToolbar(void)

- ea: `0x180043b20`
- end: `0x180043f6a`
- name: `?_RebuildToolbar@CBreadcrumbBar@@AEAAJXZ`
- size: `1098`
- prototype: `__int64 __fastcall(CBreadcrumbBar *__hidden this)`
- caller_count: `3`
- callee_count: `13`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800424f0`
- `0x180090394`
- `0x1801021a4`

## callees

- `0x180043af0`
- `0x180043b20`
- `0x180043f70`
- `0x180045554`
- `0x1800455d8`
- `0x180047410`
- `0x180067238`
- `0x1800688b0`
- `0x180068938`
- `0x180069024`
- `0x18013f7d0`
- `0x1801406ec`
- `0x180210010`

## import_xrefs

- `SHCORE!__imp_StrRetToStrW` at `0x180043da2`
- `SHCORE!__imp_StrRetToStrW` at `0x180043da2`
- `SHELL32!SHBindToFolderIDListParent` at `0x180043d4e`
- `SHELL32!SHBindToFolderIDListParent` at `0x180043d4e`
- `SHELL32!__imp_ILClone` at `0x180043c40`
- `SHELL32!__imp_ILClone` at `0x180043ec5`
- `SHELL32!__imp_ILClone` at `0x180043c40`
- `SHELL32!__imp_ILClone` at `0x180043ec5`
- `SHELL32!__imp_ILCloneFirst` at `0x180043c86`
- `SHELL32!__imp_ILCloneFirst` at `0x180043c86`
- `SHELL32!__imp_ILCombine` at `0x180043cd0`
- `SHELL32!__imp_ILCombine` at `0x180043cd0`
- `SHELL32!__imp_ILFree` at `0x180043cea`
- `SHELL32!__imp_ILFree` at `0x180043e6d`
- `SHELL32!__imp_ILFree` at `0x180043ed8`
- `SHELL32!__imp_ILFree` at `0x180043ee1`
- `SHELL32!__imp_ILFree` at `0x180043cea`
- `SHELL32!__imp_ILFree` at `0x180043e6d`
- `SHELL32!__imp_ILFree` at `0x180043ed8`
- `SHELL32!__imp_ILFree` at `0x180043ee1`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180043ddc`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180043ddc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043eec`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043e53`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180043eec`
- `USER32!SendMessageW` at `0x180043b6e`
- `USER32!SendMessageW` at `0x180043b89`
- `USER32!SendMessageW` at `0x180043bd8`
- `USER32!SendMessageW` at `0x180043b6e`
- `USER32!SendMessageW` at `0x180043b89`
- `USER32!SendMessageW` at `0x180043bd8`
- `USER32!GetSystemMetrics` at `0x180043bb7`
- `USER32!GetSystemMetrics` at `0x180043bb7`
- `USER32!SetWindowTextW` at `0x180043e45`
- `USER32!SetWindowTextW` at `0x180043e45`
- `USER32!GetClientRect` at `0x180043ba6`
- `USER32!GetClientRect` at `0x180043ba6`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CBreadcrumbBar::_RebuildToolbar(CBreadcrumbBar *this, __int64 a2, __int64 a3)
{
  __int16 v4; // bx
  __int16 SystemMetrics; // ax
  struct _DPA *v6; // rbx
  int v7; // edi
  signed int v8; // esi
  const ITEMIDLIST *v9; // rdi
  unsigned int v10; // r15d
  const struct _ITEMID_CHILD *v11; // r12
  const ITEMIDLIST *v12; // rax
  ITEMIDLIST *v13; // r15
  __int64 v14; // rcx
  __int64 v15; // rax
  __int64 v16; // rdi
  unsigned __int64 v17; // rdx
  WCHAR *v18; // rdi
  __int64 v19; // r8
  ITEMIDLIST *v21; // rax
  LPWSTR ppsz; // [rsp+40h] [rbp-C0h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+48h] [rbp-B8h] BYREF
  void *ppv; // [rsp+50h] [rbp-B0h] BYREF
  LPCITEMIDLIST pidl; // [rsp+58h] [rbp-A8h] BYREF
  STRRET pstr; // [rsp+60h] [rbp-A0h] BYREF
  struct tagRECT Rect; // [rsp+170h] [rbp+70h] BYREF
  struct _DPA *v28; // [rsp+180h] [rbp+80h]
  WCHAR Buffer[264]; // [rsp+190h] [rbp+90h] BYREF

  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Browseui_Breadcrumb_RebuildToolbar_Start,
      a3,
      1);
  SendMessageW(*((HWND *)this + 34), 0xBu, 0, 0);
  while ( SendMessageW(*((HWND *)this + 34), 0x416u, 0, 0) )
    ;
  Rect = 0;
  GetClientRect(*((HWND *)this + 34), &Rect);
  v4 = LOWORD(Rect.bottom) - LOWORD(Rect.top);
  SystemMetrics = GetSystemMetrics(6);
  SendMessageW(*((HWND *)this + 34), 0x41Fu, 0, (unsigned __int16)(v4 - SystemMetrics) << 16);
  v6 = (struct _DPA *)*((_QWORD *)this + 32);
  *((_QWORD *)this + 32) = 0;
  v28 = v6;
  v7 = CDPA_Base<IUpdatableItemSet,CTContainer_PolicyUnOwned<IUpdatableItemSet>>::Create((char *)this + 256);
  v8 = v7 == 0 ? 0x8007000E : 0;
  if ( v6 )
  {
    DPA_DestroyCallback(v6, DPA_ReleaseObjWithSiteCB<IUpdatableItemSet>, 0);
    v28 = 0;
  }
  if ( v7 )
  {
    pidl1 = ILClone(&c_idlDesktop);
    v8 = pidl1 == 0 ? 0x8007000E : 0;
    if ( pidl1 )
    {
      v9 = (const ITEMIDLIST *)*((_QWORD *)this + 29);
      v10 = 0;
      LODWORD(ppsz) = 0;
      while ( v9 )
      {
        if ( v9->mkid.cb )
        {
          v11 = (const struct _ITEMID_CHILD *)ILCloneFirst(v9);
          if ( v11 )
          {
            v8 = CBreadcrumbBar::_AddButtonForIDList(this, pidl1, v11, 0, 1, v10, (int *)&ppsz);
            if ( v8 >= 0 )
            {
              v12 = ILCombine(pidl1, (LPCITEMIDLIST)v11);
              v13 = (ITEMIDLIST *)v12;
              if ( v12 )
              {
                v8 = 0;
                v21 = (ITEMIDLIST *)_InterlockedExchange64((volatile __int64 *)&pidl1, (__int64)ILClone(v12));
                if ( v21 )
                  ILFree(v21);
                ILFree(v13);
              }
              else
              {
                v8 = -2147024882;
              }
            }
            ILFree((LPITEMIDLIST)v11);
            v10 = (unsigned int)ppsz;
          }
          else
          {
            v8 = -2147024882;
          }
          v9 = (const ITEMIDLIST *)((char *)v9 + v9->mkid.cb);
          if ( v8 >= 0 )
            continue;
        }
        if ( v8 < 0 )
          goto LABEL_33;
        break;
      }
      v8 = CBreadcrumbBar::_AddFilterButtons(this, v10);
      if ( v8 >= 0 )
      {
        ppsz = 0;
        ppv = 0;
        pidl = 0;
        v8 = SHBindToFolderIDListParent(
               0,
               *((LPCITEMIDLIST *)this + 29),
               &GUID_000214e6_0000_0000_c000_000000000046,
               &ppv,
               &pidl);
        if ( v8 >= 0 )
        {
          memset_0(&pstr, 0, sizeof(pstr));
          v8 = (*(__int64 (__fastcall **)(void *, LPCITEMIDLIST, __int64, STRRET *))(*(_QWORD *)ppv + 88LL))(
                 ppv,
                 pidl,
                 49152,
                 &pstr);
          if ( v8 >= 0 )
            v8 = StrRetToStrW(&pstr, pidl, &ppsz);
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        }
        if ( v8 >= 0 )
        {
          LoadStringW(g_hinst, 0x3605u, Buffer, 260);
          v14 = -1;
          do
            ++v14;
          while ( Buffer[v14] );
          v15 = -1;
          do
            ++v15;
          while ( ppsz[v15] );
          v16 = v15 + v14;
          wil::make_cotaskmem_string_nothrow((wil *)&ppv, 0, v15 + v14 + 1);
          v17 = v16 + 1;
          v18 = (WCHAR *)ppv;
          StringCchPrintfW((unsigned __int16 *)ppv, v17, Buffer, ppsz);
          SetWindowTextW(*((HWND *)this + 34), v18);
          if ( v18 )
            CoTaskMemFree(v18);
        }
        if ( ppsz )
          CoTaskMemFree(ppsz);
      }
LABEL_33:
      ILFree((LPITEMIDLIST)pidl1);
    }
  }
  CBreadcrumbBar::_ShowHideTBButtons(this, -1);
  if ( (Microsoft_Windows_Shell_CoreEnableBits & 1) != 0 )
    McGenEventWrite_EventWriteTransfer(
      &Microsoft_Windows_Shell_Core_Provider_Context,
      ShellTraceId_Browseui_Breadcrumb_RebuildToolbar_Stop,
      v19,
      1);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180043b20  push    rbp
0x180043b22  push    rbx
0x180043b23  push    rsi
0x180043b24  push    rdi
0x180043b25  push    r12
0x180043b27  push    r13
0x180043b29  push    r14
0x180043b2b  push    r15
0x180043b2d  lea     rbp, [rsp-2B8h]
0x180043b35  sub     rsp, 3B8h
0x180043b3c  mov     rax, cs:__security_cookie
0x180043b43  xor     rax, rsp
0x180043b46  mov     [rbp+2F0h+var_50], rax
0x180043b4d  mov     r14, rcx
0x180043b50  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180043b57  jnz     loc_180043F21
0x180043b5d  xor     r9d, r9d; lParam
0x180043b60  xor     r8d, r8d; wParam
0x180043b63  lea     edx, [r9+0Bh]; Msg
0x180043b67  mov     rcx, [r14+110h]; hWnd
0x180043b6e  call    cs:__imp_SendMessageW
0x180043b74  xor     r13d, r13d
0x180043b77  xor     r9d, r9d; lParam
0x180043b7a  xor     r8d, r8d; wParam
0x180043b7d  mov     edx, 416h; Msg
0x180043b82  mov     rcx, [r14+110h]; hWnd
0x180043b89  call    cs:__imp_SendMessageW
0x180043b8f  test    rax, rax
0x180043b92  jnz     short loc_180043B77
0x180043b94  xorps   xmm0, xmm0
0x180043b97  movups  xmmword ptr [rbp+2F0h+Rect.left], xmm0
0x180043b9b  lea     rdx, [rbp+2F0h+Rect]; lpRect
0x180043b9f  mov     rcx, [r14+110h]; hWnd
0x180043ba6  call    cs:__imp_GetClientRect
0x180043bac  mov     ebx, [rbp+2F0h+Rect.bottom]
0x180043baf  sub     ebx, [rbp+2F0h+Rect.top]
0x180043bb2  mov     ecx, 6; nIndex
0x180043bb7  call    cs:__imp_GetSystemMetrics
0x180043bbd  sub     bx, ax
0x180043bc0  movzx   eax, bx
0x180043bc3  shl     eax, 10h
0x180043bc6  movsxd  r9, eax; lParam
0x180043bc9  xor     r8d, r8d; wParam
0x180043bcc  mov     edx, 41Fh; Msg
0x180043bd1  mov     rcx, [r14+110h]; hWnd
0x180043bd8  call    cs:__imp_SendMessageW
0x180043bde  nop
0x180043bdf  lea     rcx, [r14+100h]
0x180043be6  mov     rbx, [rcx]
0x180043be9  mov     [rcx], r13
0x180043bec  mov     [rbp+2F0h+var_270], rbx
0x180043bf3  call    ?Create@?$CDPA_Base@UIUpdatableItemSet@@V?$CTContainer_PolicyUnOwned@UIUpdatableItemSet@@@@@@QEAAHH@Z; CDPA_Base<IUpdatableItemSet,CTContainer_PolicyUnOwned<IUpdatableItemSet>>::Create(int)
0x180043bf8  mov     edi, eax
0x180043bfa  mov     ecx, eax
0x180043bfc  neg     ecx
0x180043bfe  sbb     esi, esi
0x180043c00  not     esi
0x180043c02  mov     r15d, 8007000Eh
0x180043c08  and     esi, r15d
0x180043c0b  test    rbx, rbx
0x180043c0e  jz      short loc_180043C2C
0x180043c10  xor     r8d, r8d; pData
0x180043c13  lea     rdx, ??$DPA_ReleaseObjWithSiteCB@UIUpdatableItemSet@@@@YAHPEAUIUpdatableItemSet@@PEAX@Z; pfnCB
0x180043c1a  mov     rcx, rbx; hdpa
0x180043c1d  call    DPA_DestroyCallback
0x180043c22  mov     rbx, r13
0x180043c25  mov     [rbp+2F0h+var_270], rbx
0x180043c2c  test    edi, edi
0x180043c2e  jz      loc_180043E73
0x180043c34  mov     [rsp+3F0h+pidl1], r13
0x180043c39  lea     rcx, c_idlDesktop; pidl
0x180043c40  call    cs:__imp_ILClone
0x180043c46  mov     [rsp+3F0h+pidl1], rax
0x180043c4b  mov     rcx, rax
0x180043c4e  neg     rcx
0x180043c51  sbb     esi, esi
0x180043c53  not     esi
0x180043c55  and     esi, r15d
0x180043c58  test    rax, rax
0x180043c5b  jz      loc_180043E73
0x180043c61  mov     rdi, [r14+0E8h]
0x180043c68  mov     r15d, r13d
0x180043c6b  mov     dword ptr [rsp+3F0h+ppsz], r13d
0x180043c70  test    rdi, rdi
0x180043c73  jz      loc_180043D0B
0x180043c79  cmp     [rdi], r13w
0x180043c7d  jz      loc_180043D03
0x180043c83  mov     rcx, rdi; pidl
0x180043c86  call    cs:__imp_ILCloneFirst
0x180043c8c  mov     r12, rax
0x180043c8f  test    rax, rax
0x180043c92  jz      loc_180043EB5
0x180043c98  lea     rax, [rsp+3F0h+ppsz]
0x180043c9d  mov     [rsp+3F0h+var_3C0], rax; int *
0x180043ca2  mov     [rsp+3F0h+var_3C8], r15d; int
0x180043ca7  mov     dword ptr [rsp+3F0h+ppidlLast], 1; int
0x180043caf  xor     r9d, r9d; struct IViewFilters *
0x180043cb2  mov     r8, r12; struct _ITEMID_CHILD *
0x180043cb5  mov     rdx, [rsp+3F0h+pidl1]; struct _ITEMIDLIST_ABSOLUTE *
0x180043cba  mov     rcx, r14; this
0x180043cbd  call    ?_AddButtonForIDList@CBreadcrumbBar@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEFBU_ITEMID_CHILD@@PEAUIViewFilters@@HHPEAH@Z; CBreadcrumbBar::_AddButtonForIDList(_ITEMIDLIST_ABSOLUTE const *,_ITEMID_CHILD const *,IViewFilters *,int,int,int *)
0x180043cc2  mov     esi, eax
0x180043cc4  test    eax, eax
0x180043cc6  js      short loc_180043CE7
0x180043cc8  mov     rdx, r12; pidl2
0x180043ccb  mov     rcx, [rsp+3F0h+pidl1]; pidl1
0x180043cd0  call    cs:__imp_ILCombine
0x180043cd6  mov     r15, rax
0x180043cd9  test    rax, rax
0x180043cdc  jnz     loc_180043EBF
0x180043ce2  mov     esi, 8007000Eh
0x180043ce7  mov     rcx, r12; pidl
0x180043cea  call    cs:__imp_ILFree
0x180043cf0  mov     r15d, dword ptr [rsp+3F0h+ppsz]
0x180043cf5  movzx   eax, word ptr [rdi]
0x180043cf8  add     rdi, rax
0x180043cfb  test    esi, esi
0x180043cfd  jns     loc_180043C70
0x180043d03  test    esi, esi
0x180043d05  js      loc_180043E68
0x180043d0b  mov     edx, r15d; int
0x180043d0e  mov     rcx, r14; this
0x180043d11  call    ?_AddFilterButtons@CBreadcrumbBar@@AEAAJH@Z; CBreadcrumbBar::_AddFilterButtons(int)
0x180043d16  mov     esi, eax
0x180043d18  test    eax, eax
0x180043d1a  js      loc_180043E68
0x180043d20  mov     [rsp+3F0h+ppsz], r13
0x180043d25  mov     [rsp+3F0h+ppv], r13
0x180043d2a  mov     [rsp+3F0h+pidl], r13
0x180043d2f  lea     rax, [rsp+3F0h+pidl]
0x180043d34  mov     [rsp+3F0h+ppidlLast], rax; ppidlLast
0x180043d39  lea     r9, [rsp+3F0h+ppv]; ppv
0x180043d3e  lea     r8, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x180043d45  mov     rdx, [r14+0E8h]; pidl
0x180043d4c  xor     ecx, ecx; psfRoot
0x180043d4e  call    cs:__imp_SHBindToFolderIDListParent
0x180043d54  mov     esi, eax
0x180043d56  test    eax, eax
0x180043d58  js      short loc_180043DBB
0x180043d5a  xor     edx, edx; Val
0x180043d5c  mov     r8d, 110h; Size
0x180043d62  lea     rcx, [rsp+3F0h+pstr]; void *
0x180043d67  call    memset_0
0x180043d6c  mov     rcx, [rsp+3F0h+ppv]
0x180043d71  mov     rax, [rcx]
0x180043d74  lea     r9, [rsp+3F0h+pstr]
0x180043d79  mov     r8d, 0C000h
0x180043d7f  mov     rdx, [rsp+3F0h+pidl]
0x180043d84  mov     rax, [rax+58h]
0x180043d88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043d8d  mov     esi, eax
0x180043d8f  test    eax, eax
0x180043d91  js      short loc_180043DAA
0x180043d93  lea     r8, [rsp+3F0h+ppsz]; ppsz
0x180043d98  mov     rdx, [rsp+3F0h+pidl]; pidl
0x180043d9d  lea     rcx, [rsp+3F0h+pstr]; pstr
0x180043da2  call    cs:__imp_StrRetToStrW
0x180043da8  mov     esi, eax
0x180043daa  mov     rcx, [rsp+3F0h+ppv]
0x180043daf  mov     rax, [rcx]
0x180043db2  mov     rax, [rax+10h]
0x180043db6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043dbb  test    esi, esi
0x180043dbd  js      loc_180043E5A
0x180043dc3  mov     r9d, 104h; cchBufferMax
0x180043dc9  lea     r8, [rbp+2F0h+Buffer]; lpBuffer
0x180043dd0  mov     edx, 3605h; uID
0x180043dd5  mov     rcx, cs:g_hinst; hInstance
0x180043ddc  call    cs:__imp_LoadStringW
0x180043de2  lea     rax, [rbp+2F0h+Buffer]
0x180043de9  or      rcx, 0FFFFFFFFFFFFFFFFh
0x180043ded  inc     rcx
0x180043df0  cmp     [rax+rcx*2], r13w
0x180043df5  jnz     short loc_180043DED
0x180043df7  mov     rdx, [rsp+3F0h+ppsz]
0x180043dfc  or      rax, 0FFFFFFFFFFFFFFFFh
0x180043e00  inc     rax
0x180043e03  cmp     [rdx+rax*2], r13w
0x180043e08  jnz     short loc_180043E00
0x180043e0a  lea     rdi, [rax+rcx]
0x180043e0e  lea     r8, [rdi+1]; unsigned __int64
0x180043e12  xor     edx, edx; unsigned __int16 *
0x180043e14  lea     rcx, [rsp+3F0h+ppv]; this
0x180043e19  call    ?make_cotaskmem_string_nothrow@wil@@YA@PEBG_K@Z; wil::make_cotaskmem_string_nothrow(ushort const *,unsigned __int64)
0x180043e1e  mov     r9, [rsp+3F0h+ppsz]
0x180043e23  lea     r8, [rbp+2F0h+Buffer]; unsigned __int16 *
0x180043e2a  lea     rdx, [rdi+1]; unsigned __int64
0x180043e2e  mov     rdi, [rsp+3F0h+ppv]
0x180043e33  mov     rcx, rdi; unsigned __int16 *
0x180043e36  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180043e3b  mov     rdx, rdi; lpString
0x180043e3e  mov     rcx, [r14+110h]; hWnd
0x180043e45  call    cs:__imp_SetWindowTextW
0x180043e4b  test    rdi, rdi
0x180043e4e  jz      short loc_180043E5A
0x180043e50  mov     rcx, rdi; pv
0x180043e53  call    cs:__imp_CoTaskMemFree
0x180043e59  nop
0x180043e5a  mov     rcx, [rsp+3F0h+ppsz]; pv
0x180043e5f  test    rcx, rcx
0x180043e62  jnz     loc_180043EEC
0x180043e68  mov     rcx, [rsp+3F0h+pidl1]; pidl
0x180043e6d  call    cs:__imp_ILFree
0x180043e73  or      edx, 0FFFFFFFFh; int
0x180043e76  mov     rcx, r14; this
0x180043e79  call    ?_ShowHideTBButtons@CBreadcrumbBar@@AEAAXH@Z; CBreadcrumbBar::_ShowHideTBButtons(int)
0x180043e7e  test    cs:Microsoft_Windows_Shell_CoreEnableBits, 1
0x180043e85  jnz     short loc_180043EF7
0x180043e87  test    rbx, rbx
0x180043e8a  jnz     loc_180043F4B
0x180043e90  mov     eax, esi
0x180043e92  mov     rcx, [rbp+2F0h+var_50]
0x180043e99  xor     rcx, rsp; StackCookie
0x180043e9c  call    __security_check_cookie
0x180043ea1  add     rsp, 3B8h
0x180043ea8  pop     r15
0x180043eaa  pop     r14
0x180043eac  pop     r13
0x180043eae  pop     r12
0x180043eb0  pop     rdi
0x180043eb1  pop     rsi
0x180043eb2  pop     rbx
0x180043eb3  pop     rbp
0x180043eb4  retn
0x180043eb5  mov     esi, 8007000Eh
0x180043eba  jmp     loc_180043CF5
0x180043ebf  mov     esi, r13d
0x180043ec2  mov     rcx, r15; pidl
0x180043ec5  call    cs:__imp_ILClone
0x180043ecb  xchg    rax, [rsp+3F0h+pidl1]
0x180043ed0  test    rax, rax
0x180043ed3  jz      short loc_180043EDE
0x180043ed5  mov     rcx, rax; pidl
0x180043ed8  call    cs:__imp_ILFree
0x180043ede  mov     rcx, r15; pidl
0x180043ee1  call    cs:__imp_ILFree
0x180043ee7  jmp     loc_180043CE7
0x180043eec  call    cs:__imp_CoTaskMemFree
0x180043ef2  jmp     loc_180043E68
0x180043ef7  lea     rax, [rbp+2F0h+var_270]
0x180043efe  mov     [rsp+3F0h+ppidlLast], rax
0x180043f03  mov     r9d, 1
0x180043f09  lea     rdx, ShellTraceId_Browseui_Breadcrumb_RebuildToolbar_Stop
0x180043f10  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180043f17  call    McGenEventWrite_EventWriteTransfer
0x180043f1c  jmp     loc_180043E87
0x180043f21  lea     rax, [rbp+2F0h+var_270]
0x180043f28  mov     [rsp+3F0h+ppidlLast], rax
0x180043f2d  mov     r9d, 1
0x180043f33  lea     rdx, ShellTraceId_Browseui_Breadcrumb_RebuildToolbar_Start
0x180043f3a  lea     rcx, Microsoft_Windows_Shell_Core_Provider_Context
0x180043f41  call    McGenEventWrite_EventWriteTransfer
0x180043f46  jmp     loc_180043B5D
0x180043f4b  xor     r8d, r8d; pData
0x180043f4e  lea     rdx, ?AppliesTo@CQueueItem@@UEAAJPEAUIUnknown@@@Z; pfnCB
0x180043f55  mov     rcx, rbx; hdpa
0x180043f58  call    DPA_DestroyCallback
0x180043f5d  xor     ecx, ecx; hdpa
0x180043f5f  call    DPA_Destroy
0x180043f64  jmp     loc_180043E90
```
