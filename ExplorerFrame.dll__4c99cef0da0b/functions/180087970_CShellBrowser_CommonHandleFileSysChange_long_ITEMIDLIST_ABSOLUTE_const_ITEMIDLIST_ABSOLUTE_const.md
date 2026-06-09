# CShellBrowser::_CommonHandleFileSysChange(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)

- ea: `0x180087970`
- end: `0x180087d01`
- name: `?_CommonHandleFileSysChange@CShellBrowser@@AEAAXJPEBU_ITEMIDLIST_ABSOLUTE@@0@Z`
- size: `913`
- prototype: `void(CShellBrowser *__hidden this, int, const struct _ITEMIDLIST_ABSOLUTE *, const struct _ITEMIDLIST_ABSOLUTE *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, installer_update, broker_com_uri`

## callers

- `0x1800bfbec`

## callees

- `0x180087970`
- `0x180088f44`
- `0x180096624`
- `0x1800a36c0`
- `0x1800e3408`
- `0x180100cd8`
- `0x1801ce00c`
- `0x1801d4db8`
- `0x180210010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x180087a6e`
- `SHELL32!SHCreateItemFromIDList` at `0x180087c55`
- `SHELL32!SHCreateItemFromIDList` at `0x180087a6e`
- `SHELL32!SHCreateItemFromIDList` at `0x180087c55`
- `SHELL32!__imp_ILIsEqual` at `0x180087b03`
- `SHELL32!__imp_ILIsEqual` at `0x180087b03`
- `SHELL32!__imp_ILFindChild` at `0x180087ba5`
- `SHELL32!__imp_ILFindChild` at `0x180087ba5`
- `SHELL32!__imp_ILCombine` at `0x180087bb6`
- `SHELL32!__imp_ILCombine` at `0x180087bb6`
- `SHELL32!__imp_ILFree` at `0x180087c1a`
- `SHELL32!__imp_ILFree` at `0x180087c23`
- `SHELL32!__imp_ILFree` at `0x180087cc0`
- `SHELL32!__imp_ILFree` at `0x180087c1a`
- `SHELL32!__imp_ILFree` at `0x180087c23`
- `SHELL32!__imp_ILFree` at `0x180087cc0`
- `SHELL32!__imp_SHHandleUpdateImage` at `0x180087b53`
- `SHELL32!__imp_SHHandleUpdateImage` at `0x180087b53`
- `USER32!PostMessageW` at `0x180087b82`
- `USER32!PostMessageW` at `0x180087cda`
- `USER32!PostMessageW` at `0x180087b82`
- `USER32!PostMessageW` at `0x180087cda`

## pseudocode

```c
void __fastcall CShellBrowser::_CommonHandleFileSysChange(
        HWND *this,
        int a2,
        const struct _ITEMIDLIST_ABSOLUTE *a3,
        const struct _ITEMIDLIST_ABSOLUTE *a4)
{
  const ITEMIDLIST *v8; // rdi
  HWND v9; // rdx
  void *v10; // rcx
  const ITEMIDLIST *PicturesLibraryPidl; // rax
  __int64 v12; // rdx
  HWND v13; // rcx
  void (*v14)(void); // rax
  HWND v15; // rcx
  int updated; // eax
  const ITEMIDLIST *v17; // rax
  const struct _ITEMIDLIST_ABSOLUTE *v18; // rax
  ITEMIDLIST *v19; // r13
  struct _ITEMIDLIST_ABSOLUTE *v20; // rax
  const struct _ITEMIDLIST_RELATIVE *v21; // r14
  ITEMIDLIST *v22; // rdi
  __int64 v23; // [rsp+30h] [rbp-18h] BYREF
  void *ppv; // [rsp+38h] [rbp-10h] BYREF
  struct IShellItem *v25; // [rsp+90h] [rbp+48h] BYREF

  CShellBrowser::_HandleFileSysChange((CShellBrowser *)this, a2, a3, a4);
  if ( this[63] )
    return;
  v8 = (const ITEMIDLIST *)this[50];
  if ( !v8 )
    v8 = (const ITEMIDLIST *)this[49];
  if ( a2 == 1 )
  {
LABEL_36:
    v17 = ILFindChild((LPITEMIDLIST)a3, v8);
    if ( v17 )
    {
      v18 = (const struct _ITEMIDLIST_ABSOLUTE *)ILCombine((LPCITEMIDLIST)a4, v17);
      v19 = (ITEMIDLIST *)v18;
      if ( v18 )
      {
        v20 = _SimpleToReal(v18);
        v21 = v20;
        if ( v20 )
        {
          if ( !(unsigned int)ILIsEqualIncludingHiddenEx(v20, v8, 0xFFFFFFFFLL)
            && SHGetAttributesWithBindCtx(0, v21, 0, 0x20000000u) )
          {
            (*((void (__fastcall **)(char *, const struct _ITEMIDLIST_RELATIVE *, __int64))this[2] + 11))(
              (char *)this + 16,
              v21,
              1073741825);
          }
          ILFree((LPITEMIDLIST)v21);
        }
        ILFree(v19);
      }
    }
    goto LABEL_44;
  }
  if ( a2 == 32 || a2 == 64 || a2 == 128 || a2 == 256 )
  {
    v12 = 5;
    goto LABEL_35;
  }
  if ( a2 != 0x2000 )
  {
    if ( a2 == 0x8000 )
    {
      updated = SHHandleUpdateImage((LPCITEMIDLIST)a4);
      if ( updated == -1 || updated == *((_DWORD *)this + 181) )
        *((_DWORD *)this + 181) = -1;
      PostMessageW(this[41], 0x424u, 0, 0);
      return;
    }
    if ( a2 != 0x20000 )
    {
      if ( a2 != 0x4000000 )
        return;
      if ( *(_DWORD *)((char *)a3 + 2) == 15 )
      {
        v15 = this[150];
        if ( !v15 )
          return;
        v14 = *(void (**)(void))(*(_QWORD *)v15 + 72LL);
        goto LABEL_54;
      }
      if ( *(_DWORD *)((char *)a3 + 2) == 16 )
      {
        v13 = this[150];
        if ( !v13 )
          return;
        v14 = *(void (**)(void))(*(_QWORD *)v13 + 80LL);
        goto LABEL_54;
      }
      if ( *(_DWORD *)((char *)a3 + 2) != 22 )
      {
        if ( *(_DWORD *)((char *)a3 + 2) == 23 )
        {
          if ( this[145] )
          {
            if ( this[48] )
            {
              ppv = 0;
              if ( SHCreateItemFromIDList((LPCITEMIDLIST)a4, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv) >= 0 )
              {
                v9 = this[48];
                LODWORD(v25) = 0;
                if ( !(*(unsigned int (__fastcall **)(void *, HWND, __int64, struct IShellItem **))(*(_QWORD *)ppv + 56LL))(
                        ppv,
                        v9,
                        805306368,
                        &v25) )
                {
                  v23 = 0;
                  if ( (*((int (__fastcall **)(char *, SID *, GUID *, __int64 *))this[5] + 3))(
                         (char *)this + 40,
                         &SID_StatusBar,
                         &GUID_6b353825_c58b_4f03_aec4_8de179122661,
                         &v23) >= 0 )
                  {
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 40LL))(v23);
                    (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
                  }
                }
                v10 = ppv;
LABEL_53:
                v14 = *(void (**)(void))(*(_QWORD *)v10 + 16LL);
LABEL_54:
                v14();
                return;
              }
            }
          }
        }
        return;
      }
      PicturesLibraryPidl = (const ITEMIDLIST *)GetPicturesLibraryPidl();
      if ( !ILIsEqual(PicturesLibraryPidl, (LPCITEMIDLIST)a4) )
        return;
      v12 = 11;
LABEL_35:
      CShellBrowser::_InvalidateRibbonCommandSet(this, v12);
      return;
    }
    goto LABEL_36;
  }
LABEL_44:
  if ( (unsigned int)ILIsEqualIncludingHiddenEx(v8, a3, 0xFFFFFFFFLL) )
  {
    v25 = 0;
    if ( SHCreateItemFromIDList(v8, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&v25) >= 0 )
    {
      if ( (unsigned int)_NavigateOnUpdate(v25) )
      {
        if ( a2 == 0x2000 )
        {
          (*((void (__fastcall **)(char *, const ITEMIDLIST *, __int64))this[2] + 11))(
            (char *)this + 16,
            v8,
            1073741825);
        }
        else
        {
          v22 = (ITEMIDLIST *)_SimpleToReal(a4);
          if ( v22 )
          {
            (*((void (__fastcall **)(char *, ITEMIDLIST *, __int64))this[2] + 11))((char *)this + 16, v22, 1073741825);
            ILFree(v22);
          }
        }
      }
      else
      {
        PostMessageW(this[41], 0x420u, 0, 0);
      }
      v10 = v25;
      goto LABEL_53;
    }
  }
}

```

## disassembly

```asm
0x180087970  push    rbp
0x180087972  push    rbx
0x180087973  push    rsi
0x180087974  push    rdi
0x180087975  push    r12
0x180087977  push    r13
0x180087979  push    r14
0x18008797b  push    r15
0x18008797d  mov     rbp, rsp
0x180087980  sub     rsp, 48h
0x180087984  mov     r15, r9
0x180087987  mov     rsi, r8
0x18008798a  mov     r12d, edx
0x18008798d  mov     rbx, rcx
0x180087990  call    ?_HandleFileSysChange@CShellBrowser@@AEAAXJPEBU_ITEMIDLIST_ABSOLUTE@@0@Z; CShellBrowser::_HandleFileSysChange(long,_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *)
0x180087995  xor     r14d, r14d
0x180087998  cmp     [rbx+1F8h], r14
0x18008799f  jnz     loc_180087CF0
0x1800879a5  mov     rdi, [rbx+190h]
0x1800879ac  test    rdi, rdi
0x1800879af  jnz     short loc_1800879B8
0x1800879b1  mov     rdi, [rbx+188h]
0x1800879b8  mov     ecx, r12d
0x1800879bb  sub     ecx, 1
0x1800879be  jz      loc_180087B9F
0x1800879c4  sub     ecx, 1Fh
0x1800879c7  jz      loc_180087B8D
0x1800879cd  sub     ecx, 20h ; ' '
0x1800879d0  jz      loc_180087B8D
0x1800879d6  sub     ecx, 40h ; '@'
0x1800879d9  jz      loc_180087B8D
0x1800879df  sub     ecx, 80h
0x1800879e5  jz      loc_180087B8D
0x1800879eb  sub     ecx, 1F00h
0x1800879f1  jz      loc_180087C2C
0x1800879f7  sub     ecx, 6000h
0x1800879fd  jz      loc_180087B50
0x180087a03  sub     ecx, 18000h
0x180087a09  jz      loc_180087B9F
0x180087a0f  cmp     ecx, 3FE0000h
0x180087a15  jnz     loc_180087CF0
0x180087a1b  mov     ecx, [rsi+2]
0x180087a1e  sub     ecx, 0Fh
0x180087a21  jz      loc_180087B34
0x180087a27  sub     ecx, 1
0x180087a2a  jz      loc_180087B18
0x180087a30  sub     ecx, 6
0x180087a33  jz      loc_180087AF8
0x180087a39  cmp     ecx, 1
0x180087a3c  jnz     loc_180087CF0
0x180087a42  cmp     [rbx+488h], r14
0x180087a49  jz      loc_180087CF0
0x180087a4f  cmp     [rbx+180h], r14
0x180087a56  jz      loc_180087CF0
0x180087a5c  lea     r8, [rbp+ppv]; ppv
0x180087a60  mov     [rbp+ppv], r14
0x180087a64  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180087a6b  mov     rcx, r15; pidl
0x180087a6e  call    cs:__imp_SHCreateItemFromIDList
0x180087a74  test    eax, eax
0x180087a76  js      loc_180087CF0
0x180087a7c  mov     rcx, [rbp+ppv]
0x180087a80  lea     r9, [rbp+arg_0]
0x180087a84  mov     rdx, [rbx+180h]
0x180087a8b  mov     r8d, 30000000h
0x180087a91  mov     dword ptr [rbp+arg_0], r14d
0x180087a95  mov     rax, [rcx]
0x180087a98  mov     rax, [rax+38h]
0x180087a9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087aa1  test    eax, eax
0x180087aa3  jnz     short loc_180087AEF
0x180087aa5  lea     rcx, [rbx+28h]
0x180087aa9  mov     [rbp+var_18], r14
0x180087aad  mov     rax, [rcx]
0x180087ab0  lea     r9, [rbp+var_18]
0x180087ab4  lea     r8, _GUID_6b353825_c58b_4f03_aec4_8de179122661
0x180087abb  lea     rdx, SID_StatusBar
0x180087ac2  mov     rax, [rax+18h]
0x180087ac6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087acb  test    eax, eax
0x180087acd  js      short loc_180087AEF
0x180087acf  mov     rcx, [rbp+var_18]
0x180087ad3  mov     rax, [rcx]
0x180087ad6  mov     rax, [rax+28h]
0x180087ada  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087adf  mov     rcx, [rbp+var_18]
0x180087ae3  mov     rax, [rcx]
0x180087ae6  mov     rax, [rax+10h]
0x180087aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087aef  mov     rcx, [rbp+ppv]
0x180087af3  jmp     loc_180087CE4
0x180087af8  call    GetPicturesLibraryPidl
0x180087afd  mov     rcx, rax; pidl1
0x180087b00  mov     rdx, r15; pidl2
0x180087b03  call    cs:__imp_ILIsEqual
0x180087b09  test    eax, eax
0x180087b0b  jz      loc_180087CF0
0x180087b11  mov     edx, 0Bh
0x180087b16  jmp     short loc_180087B92
0x180087b18  mov     rcx, [rbx+4B0h]
0x180087b1f  test    rcx, rcx
0x180087b22  jz      loc_180087CF0
0x180087b28  mov     rax, [rcx]
0x180087b2b  mov     rax, [rax+50h]
0x180087b2f  jmp     loc_180087CEB
0x180087b34  mov     rcx, [rbx+4B0h]
0x180087b3b  test    rcx, rcx
0x180087b3e  jz      loc_180087CF0
0x180087b44  mov     rax, [rcx]
0x180087b47  mov     rax, [rax+48h]
0x180087b4b  jmp     loc_180087CEB
0x180087b50  mov     rcx, r15; pidlExtra
0x180087b53  call    cs:__imp_SHHandleUpdateImage
0x180087b59  cmp     eax, 0FFFFFFFFh
0x180087b5c  jz      short loc_180087B66
0x180087b5e  cmp     eax, [rbx+2D4h]
0x180087b64  jnz     short loc_180087B70
0x180087b66  mov     dword ptr [rbx+2D4h], 0FFFFFFFFh
0x180087b70  mov     rcx, [rbx+148h]; hWnd
0x180087b77  xor     r9d, r9d; lParam
0x180087b7a  xor     r8d, r8d; wParam
0x180087b7d  mov     edx, 424h; Msg
0x180087b82  call    cs:__imp_PostMessageW
0x180087b88  jmp     loc_180087CF0
0x180087b8d  mov     edx, 5
0x180087b92  mov     rcx, rbx
0x180087b95  call    ?_InvalidateRibbonCommandSet@CShellBrowser@@AEAAXW4COMMAND_SET@@@Z; CShellBrowser::_InvalidateRibbonCommandSet(COMMAND_SET)
0x180087b9a  jmp     loc_180087CF0
0x180087b9f  mov     rdx, rdi; pidlChild
0x180087ba2  mov     rcx, rsi; pidlParent
0x180087ba5  call    cs:__imp_ILFindChild
0x180087bab  test    rax, rax
0x180087bae  jz      short loc_180087C2C
0x180087bb0  mov     rdx, rax; pidl2
0x180087bb3  mov     rcx, r15; pidl1
0x180087bb6  call    cs:__imp_ILCombine
0x180087bbc  mov     r13, rax
0x180087bbf  test    rax, rax
0x180087bc2  jz      short loc_180087C2C
0x180087bc4  mov     rcx, rax; struct _ITEMIDLIST_ABSOLUTE *
0x180087bc7  call    ?_SimpleToReal@@YAPEAU_ITEMIDLIST_ABSOLUTE@@PEBU1@@Z; _SimpleToReal(_ITEMIDLIST_ABSOLUTE const *)
0x180087bcc  mov     r14, rax
0x180087bcf  test    rax, rax
0x180087bd2  jz      short loc_180087C20
0x180087bd4  or      r8d, 0FFFFFFFFh
0x180087bd8  mov     rdx, rdi
0x180087bdb  mov     rcx, rax
0x180087bde  call    ?ILIsEqualIncludingHiddenEx@@YAHPEBU_ITEMIDLIST_ABSOLUTE@@0W4IIEIHE@@@Z; ILIsEqualIncludingHiddenEx(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,IIEIHE)
0x180087be3  test    eax, eax
0x180087be5  jnz     short loc_180087C17
0x180087be7  mov     r9d, 20000000h; unsigned int
0x180087bed  xor     r8d, r8d; struct IBindCtx *
0x180087bf0  mov     rdx, r14; struct _ITEMIDLIST_RELATIVE *
0x180087bf3  xor     ecx, ecx; struct IShellFolder *
0x180087bf5  call    ?SHGetAttributesWithBindCtx@@YAKPEAUIShellFolder@@PEFBU_ITEMIDLIST_RELATIVE@@PEAUIBindCtx@@K@Z; SHGetAttributesWithBindCtx(IShellFolder *,_ITEMIDLIST_RELATIVE const *,IBindCtx *,ulong)
0x180087bfa  test    eax, eax
0x180087bfc  jz      short loc_180087C17
0x180087bfe  lea     rcx, [rbx+10h]
0x180087c02  mov     r8d, 40000001h
0x180087c08  mov     rax, [rcx]
0x180087c0b  mov     rdx, r14
0x180087c0e  mov     rax, [rax+58h]
0x180087c12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087c17  mov     rcx, r14; pidl
0x180087c1a  call    cs:__imp_ILFree
0x180087c20  mov     rcx, r13; pidl
0x180087c23  call    cs:__imp_ILFree
0x180087c29  xor     r14d, r14d
0x180087c2c  or      r8d, 0FFFFFFFFh
0x180087c30  mov     rdx, rsi
0x180087c33  mov     rcx, rdi
0x180087c36  call    ?ILIsEqualIncludingHiddenEx@@YAHPEBU_ITEMIDLIST_ABSOLUTE@@0W4IIEIHE@@@Z; ILIsEqualIncludingHiddenEx(_ITEMIDLIST_ABSOLUTE const *,_ITEMIDLIST_ABSOLUTE const *,IIEIHE)
0x180087c3b  test    eax, eax
0x180087c3d  jz      loc_180087CF0
0x180087c43  lea     r8, [rbp+arg_0]; ppv
0x180087c47  mov     [rbp+arg_0], r14
0x180087c4b  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180087c52  mov     rcx, rdi; pidl
0x180087c55  call    cs:__imp_SHCreateItemFromIDList
0x180087c5b  test    eax, eax
0x180087c5d  js      loc_180087CF0
0x180087c63  mov     rcx, [rbp+arg_0]; struct IShellItem *
0x180087c67  call    ?_NavigateOnUpdate@@YAHPEAUIShellItem@@@Z; _NavigateOnUpdate(IShellItem *)
0x180087c6c  test    eax, eax
0x180087c6e  jz      short loc_180087CC8
0x180087c70  cmp     r12d, 2000h
0x180087c77  jnz     short loc_180087C94
0x180087c79  lea     rcx, [rbx+10h]
0x180087c7d  mov     r8d, 40000001h
0x180087c83  mov     rax, [rcx]
0x180087c86  mov     rdx, rdi
0x180087c89  mov     rax, [rax+58h]
0x180087c8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087c92  jmp     short loc_180087CE0
0x180087c94  mov     rcx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x180087c97  call    ?_SimpleToReal@@YAPEAU_ITEMIDLIST_ABSOLUTE@@PEBU1@@Z; _SimpleToReal(_ITEMIDLIST_ABSOLUTE const *)
0x180087c9c  mov     rdi, rax
0x180087c9f  test    rax, rax
0x180087ca2  jz      short loc_180087CE0
0x180087ca4  lea     rcx, [rbx+10h]
0x180087ca8  mov     r8d, 40000001h
0x180087cae  mov     rdx, [rcx]
0x180087cb1  mov     rax, [rdx+58h]
0x180087cb5  mov     rdx, rdi
0x180087cb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087cbd  mov     rcx, rdi; pidl
0x180087cc0  call    cs:__imp_ILFree
0x180087cc6  jmp     short loc_180087CE0
0x180087cc8  mov     rcx, [rbx+148h]; hWnd
0x180087ccf  xor     r9d, r9d; lParam
0x180087cd2  xor     r8d, r8d; wParam
0x180087cd5  mov     edx, 420h; Msg
0x180087cda  call    cs:__imp_PostMessageW
0x180087ce0  mov     rcx, [rbp+arg_0]
0x180087ce4  mov     rax, [rcx]
0x180087ce7  mov     rax, [rax+10h]
0x180087ceb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180087cf0  add     rsp, 48h
0x180087cf4  pop     r15
0x180087cf6  pop     r14
0x180087cf8  pop     r13
0x180087cfa  pop     r12
0x180087cfc  pop     rdi
0x180087cfd  pop     rsi
0x180087cfe  pop     rbx
0x180087cff  pop     rbp
0x180087d00  retn
```
