# CShellBrowser::_MayTranslateAcceleratorNoMenuband(tagMSG *)

- ea: `0x180050ce8`
- end: `0x180051002`
- name: `?_MayTranslateAcceleratorNoMenuband@CShellBrowser@@AEAAJPEAUtagMSG@@@Z`
- size: `794`
- prototype: `__int64 __fastcall(CShellBrowser *__hidden this, struct tagMSG *)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, service_task`

## callers

- `0x1800507a8`

## callees

- `0x180050ce8`
- `0x180051008`
- `0x180051050`
- `0x1800510d8`
- `0x1800513b0`
- `0x1801d15b8`
- `0x1801d1bd4`
- `0x1801d4e64`
- `0x180210010`

## import_xrefs

- `SHCORE!IUnknown_QueryService` at `0x180050ebf`
- `SHCORE!IUnknown_QueryService` at `0x180050ebf`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x180050f09`
- `SHLWAPI!__imp_IUnknown_GetWindow` at `0x180050f09`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050d7b`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050dd0`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050f1a`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050f8f`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050d7b`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050dd0`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050f1a`
- `SHLWAPI!__imp_SHIsChildOrSelf` at `0x180050f8f`
- `SHLWAPI!__imp_IUnknown_TranslateAcceleratorIO` at `0x180050fbe`
- `SHLWAPI!__imp_IUnknown_TranslateAcceleratorIO` at `0x180050fbe`
- `USER32!GetFocus` at `0x180050fe6`
- `USER32!GetFocus` at `0x180050fe6`
- `USER32!GetWindowThreadProcessId` at `0x180050de3`
- `USER32!GetWindowThreadProcessId` at `0x180050df9`
- `USER32!GetWindowThreadProcessId` at `0x180050de3`
- `USER32!GetWindowThreadProcessId` at `0x180050df9`

## pseudocode

```c
__int64 __fastcall CShellBrowser::_MayTranslateAcceleratorNoMenuband(HWND *this, struct tagMSG *a2)
{
  int HasToolbarFocus; // r15d
  int IsExplorerFrameFocused; // eax
  int v6; // r14d
  unsigned int v7; // edx
  HWND v8; // rcx
  IUnknown *Focus; // rax
  HWND v10; // rcx
  int v11; // eax
  const struct _GUID *v12; // rdx
  DWORD WindowThreadProcessId; // esi
  DWORD v14; // eax
  struct IUnknown *v16; // rcx
  int v17; // esi
  HWND v18; // rcx
  IUnknown *punk; // [rsp+68h] [rbp+38h] BYREF
  void *ppvOut; // [rsp+70h] [rbp+40h] BYREF
  HWND phwnd; // [rsp+78h] [rbp+48h] BYREF

  if ( a2->message - 256 > 9 )
    return 1;
  HasToolbarFocus = CShellBrowser::_HasToolbarFocus((CShellBrowser *)this);
  IsExplorerFrameFocused = CShellBrowser::_IsExplorerFrameFocused((CShellBrowser *)this);
  v6 = IsExplorerFrameFocused;
  if ( HasToolbarFocus )
  {
    v11 = IUnknown_TranslateAcceleratorIO(*((_QWORD *)this[94] + 6 * *((int *)this + 216)), a2);
  }
  else
  {
    if ( IsExplorerFrameFocused )
      goto LABEL_13;
    v7 = *((_DWORD *)this + 216);
    if ( v7 != -1 && (unsigned int)CShellBrowser::_TBWindowHasFocus((CShellBrowser *)this, v7) )
      CShellBrowser::_FixToolbarFocus((CShellBrowser *)this);
    v8 = this[52];
    if ( !v8 )
      goto LABEL_13;
    punk = 0;
    if ( (*(int (__fastcall **)(HWND, IUnknown **))(*(_QWORD *)v8 + 24LL))(v8, &punk) < 0 )
    {
      Focus = (IUnknown *)GetFocus();
      punk = Focus;
    }
    else
    {
      Focus = punk;
    }
    if ( !(unsigned int)SHIsChildOrSelf(Focus, a2->hwnd)
      && !(*(unsigned int (__fastcall **)(HWND, struct tagMSG *))(*(_QWORD *)this[52] + 40LL))(this[52], a2) )
    {
      return 0;
    }
    v10 = this[145];
    if ( !v10 )
      goto LABEL_13;
    v11 = (*(__int64 (__fastcall **)(HWND, struct tagMSG *))(*(_QWORD *)v10 + 72LL))(v10, a2);
  }
  if ( !v11 )
    return 0;
LABEL_13:
  if ( (unsigned int)SHIsChildOrSelf(this[41], a2->hwnd) )
  {
    v16 = (struct IUnknown *)this[52];
    punk = 0;
    if ( !v16
      || !(unsigned int)_QITest(v16, v12)
      || (*(int (__fastcall **)(HWND, IUnknown **))(*(_QWORD *)this[52] + 24LL))(this[52], &punk) < 0
      || (unsigned int)SHIsChildOrSelf(punk, a2->hwnd) )
    {
      ppvOut = 0;
      if ( IUnknown_QueryService(
             (IUnknown *)((unsigned __int64)(this + 2) & -(__int64)(this != 0)),
             &GUID_3dec5f26_8322_497c_b1a9_d76f2646b3cc,
             &GUID_6d5140c1_7436_11ce_8034_00aa006009fa,
             &ppvOut) < 0 )
        goto LABEL_19;
      punk = 0;
      v17 = 0;
      if ( (*(int (__fastcall **)(void *, SID *, GUID *, IUnknown **))(*(_QWORD *)ppvOut + 24LL))(
             ppvOut,
             &SID_SNavBar,
             &GUID_00000000_0000_0000_c000_000000000046,
             &punk) >= 0 )
      {
        phwnd = 0;
        if ( IUnknown_GetWindow(punk, &phwnd) >= 0 )
          LOBYTE(v17) = (unsigned int)SHIsChildOrSelf(phwnd, a2->hwnd) == 0;
        ((void (__fastcall *)(IUnknown *))punk->lpVtbl->Release)(punk);
      }
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
      if ( !v17 )
        goto LABEL_19;
    }
  }
  WindowThreadProcessId = GetWindowThreadProcessId(this[41], 0);
  v14 = a2->hwnd ? GetWindowThreadProcessId(a2->hwnd, 0) : 0;
  if ( WindowThreadProcessId != v14 )
  {
LABEL_19:
    if ( HasToolbarFocus || v6 )
    {
      v18 = this[52];
      if ( v18 )
      {
        if ( !(*(unsigned int (__fastcall **)(HWND, struct tagMSG *))(*(_QWORD *)v18 + 40LL))(v18, a2) )
          return 0;
      }
    }
    return 1;
  }
  if ( !(unsigned int)IsVK_TABCycler(a2) )
  {
    if ( (*((unsigned int (__fastcall **)(char *, struct tagMSG *, _QWORD))this[2] + 10))((char *)this + 16, a2, 0) )
      goto LABEL_19;
    return 0;
  }
  return CShellBrowser::_CycleFocus((CShellBrowser *)this, a2);
}

```

## disassembly

```asm
0x180050ce8  mov     [rsp-28h+arg_0], rbx
0x180050ced  push    rbp
0x180050cee  push    rsi
0x180050cef  push    rdi
0x180050cf0  push    r14
0x180050cf2  push    r15
0x180050cf4  mov     rbp, rsp
0x180050cf7  sub     rsp, 30h
0x180050cfb  mov     eax, [rdx+8]
0x180050cfe  mov     rdi, rdx
0x180050d01  sub     eax, 100h
0x180050d06  mov     rbx, rcx
0x180050d09  cmp     eax, 9
0x180050d0c  ja      loc_180050E43
0x180050d12  call    ?_HasToolbarFocus@CShellBrowser@@AEAAHXZ; CShellBrowser::_HasToolbarFocus(void)
0x180050d17  mov     rcx, rbx; this
0x180050d1a  mov     r15d, eax
0x180050d1d  call    ?_IsExplorerFrameFocused@CShellBrowser@@AEAAHXZ; CShellBrowser::_IsExplorerFrameFocused(void)
0x180050d22  mov     r14d, eax
0x180050d25  test    r15d, r15d
0x180050d28  jnz     loc_180050FA2
0x180050d2e  test    eax, eax
0x180050d30  jnz     loc_180050DC6
0x180050d36  mov     edx, [rbx+360h]; unsigned int
0x180050d3c  cmp     edx, 0FFFFFFFFh
0x180050d3f  jnz     loc_180050FC9
0x180050d45  mov     rcx, [rbx+1A0h]
0x180050d4c  test    rcx, rcx
0x180050d4f  jz      short loc_180050DC6
0x180050d51  mov     [rbp+punk], 0
0x180050d59  lea     rdx, [rbp+punk]
0x180050d5d  mov     rax, [rcx]
0x180050d60  mov     rax, [rax+18h]
0x180050d64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d69  test    eax, eax
0x180050d6b  js      loc_180050FE6
0x180050d71  mov     rax, [rbp+punk]
0x180050d75  mov     rdx, [rdi]
0x180050d78  mov     rcx, rax
0x180050d7b  call    cs:__imp_SHIsChildOrSelf
0x180050d81  test    eax, eax
0x180050d83  jnz     short loc_180050DA3
0x180050d85  mov     rcx, [rbx+1A0h]
0x180050d8c  mov     rdx, rdi
0x180050d8f  mov     rax, [rcx]
0x180050d92  mov     rax, [rax+28h]
0x180050d96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050d9b  test    eax, eax
0x180050d9d  jz      loc_180050F7A
0x180050da3  mov     rcx, [rbx+488h]
0x180050daa  test    rcx, rcx
0x180050dad  jz      short loc_180050DC6
0x180050daf  mov     rax, [rcx]
0x180050db2  mov     rdx, rdi
0x180050db5  mov     rax, [rax+48h]
0x180050db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050dbe  test    eax, eax
0x180050dc0  jz      loc_180050F7A
0x180050dc6  mov     rdx, [rdi]
0x180050dc9  mov     rcx, [rbx+148h]
0x180050dd0  call    cs:__imp_SHIsChildOrSelf
0x180050dd6  test    eax, eax
0x180050dd8  jnz     short loc_180050E59
0x180050dda  mov     rcx, [rbx+148h]; hWnd
0x180050de1  xor     edx, edx; lpdwProcessId
0x180050de3  call    cs:__imp_GetWindowThreadProcessId
0x180050de9  mov     rcx, [rdi]; hWnd
0x180050dec  mov     esi, eax
0x180050dee  test    rcx, rcx
0x180050df1  jz      loc_180050F81
0x180050df7  xor     edx, edx; lpdwProcessId
0x180050df9  call    cs:__imp_GetWindowThreadProcessId
0x180050dff  cmp     esi, eax
0x180050e01  jnz     short loc_180050E31
0x180050e03  mov     rcx, rdi; struct tagMSG *
0x180050e06  call    ?IsVK_TABCycler@@YAHPEAUtagMSG@@@Z; IsVK_TABCycler(tagMSG *)
0x180050e0b  mov     rdx, rdi; struct tagMSG *
0x180050e0e  test    eax, eax
0x180050e10  jnz     loc_180050FF5
0x180050e16  lea     rcx, [rbx+10h]
0x180050e1a  xor     r8d, r8d
0x180050e1d  mov     rax, [rcx]
0x180050e20  mov     rax, [rax+50h]
0x180050e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e29  test    eax, eax
0x180050e2b  jz      loc_180050F7A
0x180050e31  test    r15d, r15d
0x180050e34  jnz     loc_180050F53
0x180050e3a  test    r14d, r14d
0x180050e3d  jnz     loc_180050F53
0x180050e43  mov     eax, 1
0x180050e48  mov     rbx, [rsp+30h+arg_0]
0x180050e4d  add     rsp, 30h
0x180050e51  pop     r15
0x180050e53  pop     r14
0x180050e55  pop     rdi
0x180050e56  pop     rsi
0x180050e57  pop     rbp
0x180050e58  retn
0x180050e59  mov     rcx, [rbx+1A0h]; struct IUnknown *
0x180050e60  mov     [rbp+punk], 0
0x180050e68  test    rcx, rcx
0x180050e6b  jz      short loc_180050E95
0x180050e6d  call    ?_QITest@@YAHPEAUIUnknown@@AEBU_GUID@@@Z; _QITest(IUnknown *,_GUID const &)
0x180050e72  test    eax, eax
0x180050e74  jz      short loc_180050E95
0x180050e76  mov     rcx, [rbx+1A0h]
0x180050e7d  lea     rdx, [rbp+punk]
0x180050e81  mov     rax, [rcx]
0x180050e84  mov     rax, [rax+18h]
0x180050e88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050e8d  test    eax, eax
0x180050e8f  jns     loc_180050F88
0x180050e95  lea     rdx, [rbx+10h]
0x180050e99  mov     [rbp+ppvOut], 0
0x180050ea1  mov     rax, rbx
0x180050ea4  lea     r9, [rbp+ppvOut]; ppvOut
0x180050ea8  neg     rax
0x180050eab  lea     r8, _GUID_6d5140c1_7436_11ce_8034_00aa006009fa; riid
0x180050eb2  sbb     rcx, rcx
0x180050eb5  and     rcx, rdx; punk
0x180050eb8  lea     rdx, _GUID_3dec5f26_8322_497c_b1a9_d76f2646b3cc; guidService
0x180050ebf  call    cs:__imp_IUnknown_QueryService
0x180050ec5  test    eax, eax
0x180050ec7  js      loc_180050E31
0x180050ecd  mov     rcx, [rbp+ppvOut]
0x180050ed1  lea     r9, [rbp+punk]
0x180050ed5  mov     [rbp+punk], 0
0x180050edd  lea     r8, _GUID_00000000_0000_0000_c000_000000000046
0x180050ee4  lea     rdx, SID_SNavBar
0x180050eeb  xor     esi, esi
0x180050eed  mov     rax, [rcx]
0x180050ef0  mov     rax, [rax+18h]
0x180050ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050ef9  test    eax, eax
0x180050efb  js      short loc_180050F36
0x180050efd  mov     rcx, [rbp+punk]; punk
0x180050f01  lea     rdx, [rbp+phwnd]; phwnd
0x180050f05  mov     [rbp+phwnd], rsi
0x180050f09  call    cs:__imp_IUnknown_GetWindow
0x180050f0f  test    eax, eax
0x180050f11  js      short loc_180050F26
0x180050f13  mov     rdx, [rdi]
0x180050f16  mov     rcx, [rbp+phwnd]
0x180050f1a  call    cs:__imp_SHIsChildOrSelf
0x180050f20  test    eax, eax
0x180050f22  setz    sil
0x180050f26  mov     rcx, [rbp+punk]
0x180050f2a  mov     rax, [rcx]
0x180050f2d  mov     rax, [rax+10h]
0x180050f31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f36  mov     rcx, [rbp+ppvOut]
0x180050f3a  mov     rax, [rcx]
0x180050f3d  mov     rax, [rax+10h]
0x180050f41  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f46  test    esi, esi
0x180050f48  jz      loc_180050E31
0x180050f4e  jmp     loc_180050DDA
0x180050f53  mov     rcx, [rbx+1A0h]
0x180050f5a  test    rcx, rcx
0x180050f5d  jz      loc_180050E43
0x180050f63  mov     rax, [rcx]
0x180050f66  mov     rdx, rdi
0x180050f69  mov     rax, [rax+28h]
0x180050f6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180050f72  test    eax, eax
0x180050f74  jnz     loc_180050E43
0x180050f7a  xor     eax, eax
0x180050f7c  jmp     loc_180050E48
0x180050f81  xor     eax, eax
0x180050f83  jmp     loc_180050DFF
0x180050f88  mov     rdx, [rdi]
0x180050f8b  mov     rcx, [rbp+punk]
0x180050f8f  call    cs:__imp_SHIsChildOrSelf
0x180050f95  test    eax, eax
0x180050f97  jz      loc_180050DDA
0x180050f9d  jmp     loc_180050E95
0x180050fa2  movsxd  rcx, dword ptr [rbx+360h]
0x180050fa9  mov     rdx, rdi
0x180050fac  lea     r8, [rcx+rcx*2]
0x180050fb0  mov     rcx, [rbx+2F0h]
0x180050fb7  add     r8, r8
0x180050fba  mov     rcx, [rcx+r8*8]
0x180050fbe  call    cs:__imp_IUnknown_TranslateAcceleratorIO
0x180050fc4  jmp     loc_180050DBE
0x180050fc9  mov     rcx, rbx; this
0x180050fcc  call    ?_TBWindowHasFocus@CShellBrowser@@AEAAHI@Z; CShellBrowser::_TBWindowHasFocus(uint)
0x180050fd1  test    eax, eax
0x180050fd3  jz      loc_180050D45
0x180050fd9  mov     rcx, rbx; this
0x180050fdc  call    ?_FixToolbarFocus@CShellBrowser@@AEAAJXZ; CShellBrowser::_FixToolbarFocus(void)
0x180050fe1  jmp     loc_180050D45
0x180050fe6  call    cs:__imp_GetFocus
0x180050fec  mov     [rbp+punk], rax
0x180050ff0  jmp     loc_180050D75
0x180050ff5  mov     rcx, rbx; this
0x180050ff8  call    ?_CycleFocus@CShellBrowser@@AEAAJPEAUtagMSG@@@Z; CShellBrowser::_CycleFocus(tagMSG *)
0x180050ffd  jmp     loc_180050E48
```
