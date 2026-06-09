# CNavigateButton::Navigate(ushort const *,ushort const *,IUnknown *,bool)

- ea: `0x18000a278`
- end: `0x18000a492`
- name: `?Navigate@CNavigateButton@@SAXPEBG0PEAUIUnknown@@_N@Z`
- size: `538`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, struct IUnknown *, unsigned __int8)`
- caller_count: `1`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000aa38`

## callees

- `0x18000a140`
- `0x18000a278`
- `0x18000a83c`
- `0x18000b710`
- `0x18000c010`

## import_xrefs

- `SHELL32!SHBindToObject` at `0x18000a37a`
- `SHELL32!SHBindToObject` at `0x18000a37a`
- `SHELL32!SHParseDisplayName` at `0x18000a33e`
- `SHELL32!SHParseDisplayName` at `0x18000a33e`
- `SHELL32!__imp_ILClone` at `0x18000a40d`
- `SHELL32!__imp_ILClone` at `0x18000a40d`
- `SHELL32!__imp_ILCombine` at `0x18000a3cc`
- `SHELL32!__imp_ILCombine` at `0x18000a3cc`
- `SHELL32!__imp_ILFree` at `0x18000a3ea`
- `SHELL32!__imp_ILFree` at `0x18000a42f`
- `SHELL32!__imp_ILFree` at `0x18000a45a`
- `SHELL32!__imp_ILFree` at `0x18000a3ea`
- `SHELL32!__imp_ILFree` at `0x18000a42f`
- `SHELL32!__imp_ILFree` at `0x18000a45a`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a2ce`
- `SHLWAPI!__imp_IUnknown_QueryService` at `0x18000a2ce`

## pseudocode

```c
void __fastcall CNavigateButton::Navigate(
        const unsigned __int16 *a1,
        const unsigned __int16 *a2,
        struct IUnknown *a3,
        unsigned __int8 a4)
{
  int v4; // r15d
  unsigned int v7; // r8d
  char v8; // al
  char v9; // si
  HRESULT CplRoot; // eax
  HRESULT v11; // ebx
  ITEMIDLIST *v12; // rdi
  LPITEMIDLIST ppidl; // [rsp+40h] [rbp-C0h] BYREF
  void *ppvOut; // [rsp+48h] [rbp-B8h] BYREF
  LPCITEMIDLIST pidl2; // [rsp+50h] [rbp-B0h] BYREF
  void *ppv; // [rsp+58h] [rbp-A8h] BYREF
  WCHAR pszName[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = a4;
  ppvOut = 0;
  if ( IUnknown_QueryService(
         a3,
         (const GUID *const)&SID_STopLevelBrowser,
         &GUID_000214e2_0000_0000_c000_000000000046,
         &ppvOut) < 0 )
    return;
  ppidl = 0;
  if ( !a1 || (v8 = 1, !*a1) )
    v8 = 0;
  if ( !a2 || (v9 = 1, !*a2) )
    v9 = 0;
  if ( !v8 )
  {
    CplRoot = CNavigateButton::GetCplRoot((struct IShellBrowser *)ppvOut, &ppidl);
LABEL_12:
    v11 = CplRoot;
    goto LABEL_13;
  }
  v11 = TranslateCplCanonicalName(a1, pszName, v7);
  if ( v11 >= 0 )
  {
    CplRoot = SHParseDisplayName(pszName, 0, &ppidl, 0, 0);
    goto LABEL_12;
  }
LABEL_13:
  v12 = 0;
  if ( v11 >= 0 )
  {
    if ( v9 )
    {
      ppv = 0;
      v11 = SHBindToObject(0, ppidl, 0, &GUID_000214e6_0000_0000_c000_000000000046, &ppv);
      if ( v11 >= 0 )
      {
        pidl2 = 0;
        v11 = (*(__int64 (__fastcall **)(void *, _QWORD, _QWORD, const unsigned __int16 *, _QWORD, LPCITEMIDLIST *, _QWORD))(*(_QWORD *)ppv + 24LL))(
                ppv,
                0,
                0,
                a2,
                0,
                &pidl2,
                0);
        if ( v11 >= 0 )
        {
          v12 = ILCombine(ppidl, pidl2);
          v11 = v12 == 0 ? 0x8007000E : 0;
          ILFree((LPITEMIDLIST)pidl2);
        }
        (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
      }
    }
    else if ( ppidl )
    {
      v12 = ILClone(ppidl);
      v11 = v12 == 0 ? 0x8007000E : 0;
    }
    else
    {
      v11 = -2147024809;
    }
  }
  ILFree(ppidl);
  if ( v11 >= 0 )
  {
    (*(void (__fastcall **)(void *, ITEMIDLIST *, _QWORD))(*(_QWORD *)ppvOut + 88LL))(
      ppvOut,
      v12,
      (unsigned int)((v4 << 30) + 1));
    ILFree(v12);
  }
  (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
}

```

## disassembly

```asm
0x18000a278  push    rbp
0x18000a27a  push    rbx
0x18000a27b  push    rsi
0x18000a27c  push    rdi
0x18000a27d  push    r12
0x18000a27f  push    r14
0x18000a281  push    r15
0x18000a283  lea     rbp, [rsp-180h]
0x18000a28b  sub     rsp, 280h
0x18000a292  mov     rax, cs:__security_cookie
0x18000a299  xor     rax, rsp
0x18000a29c  mov     [rbp+1B0h+var_40], rax
0x18000a2a3  mov     rax, r8
0x18000a2a6  movzx   r15d, r9b
0x18000a2aa  mov     r14, rdx
0x18000a2ad  lea     r9, [rsp+2B0h+ppvOut]; ppvOut
0x18000a2b2  mov     rbx, rcx
0x18000a2b5  lea     r8, _GUID_000214e2_0000_0000_c000_000000000046; riid
0x18000a2bc  xor     r12d, r12d
0x18000a2bf  lea     rdx, SID_STopLevelBrowser; guidService
0x18000a2c6  mov     rcx, rax; punk
0x18000a2c9  mov     [rsp+2B0h+ppvOut], r12
0x18000a2ce  call    cs:__imp_IUnknown_QueryService
0x18000a2d4  test    eax, eax
0x18000a2d6  js      loc_18000A471
0x18000a2dc  mov     [rsp+2B0h+ppidl], r12
0x18000a2e1  test    rbx, rbx
0x18000a2e4  jz      short loc_18000A2EE
0x18000a2e6  mov     al, 1
0x18000a2e8  cmp     [rbx], r12w
0x18000a2ec  jnz     short loc_18000A2F1
0x18000a2ee  mov     al, r12b
0x18000a2f1  test    r14, r14
0x18000a2f4  jz      short loc_18000A2FF
0x18000a2f6  mov     sil, 1
0x18000a2f9  cmp     [r14], r12w
0x18000a2fd  jnz     short loc_18000A302
0x18000a2ff  mov     sil, r12b
0x18000a302  test    al, al
0x18000a304  jnz     short loc_18000A317
0x18000a306  mov     rcx, [rsp+2B0h+ppvOut]; struct IShellBrowser *
0x18000a30b  lea     rdx, [rsp+2B0h+ppidl]; struct _ITEMIDLIST **
0x18000a310  call    ?GetCplRoot@CNavigateButton@@CAJPEAUIShellBrowser@@PEAPEFAU_ITEMIDLIST@@@Z; CNavigateButton::GetCplRoot(IShellBrowser *,_ITEMIDLIST * *)
0x18000a315  jmp     short loc_18000A344
0x18000a317  lea     rdx, [rsp+2B0h+pszName]; unsigned __int16 *
0x18000a31c  mov     rcx, rbx; unsigned __int16 *
0x18000a31f  call    ?TranslateCplCanonicalName@@YAJPEBGPEAGI@Z; TranslateCplCanonicalName(ushort const *,ushort *,uint)
0x18000a324  mov     ebx, eax
0x18000a326  test    eax, eax
0x18000a328  js      short loc_18000A346
0x18000a32a  xor     r9d, r9d; sfgaoIn
0x18000a32d  mov     [rsp+2B0h+psfgaoOut], r12; psfgaoOut
0x18000a332  lea     r8, [rsp+2B0h+ppidl]; ppidl
0x18000a337  xor     edx, edx; pbc
0x18000a339  lea     rcx, [rsp+2B0h+pszName]; pszName
0x18000a33e  call    cs:__imp_SHParseDisplayName
0x18000a344  mov     ebx, eax
0x18000a346  mov     rdi, r12
0x18000a349  test    ebx, ebx
0x18000a34b  js      loc_18000A42A
0x18000a351  test    sil, sil
0x18000a354  jz      loc_18000A403
0x18000a35a  mov     rdx, [rsp+2B0h+ppidl]; pidl
0x18000a35f  lea     rax, [rsp+2B0h+ppv]
0x18000a364  lea     r9, _GUID_000214e6_0000_0000_c000_000000000046; riid
0x18000a36b  mov     [rsp+2B0h+psfgaoOut], rax; ppv
0x18000a370  xor     r8d, r8d; pbc
0x18000a373  mov     [rsp+2B0h+ppv], r12
0x18000a378  xor     ecx, ecx; psf
0x18000a37a  call    cs:__imp_SHBindToObject
0x18000a380  mov     ebx, eax
0x18000a382  test    eax, eax
0x18000a384  js      loc_18000A42A
0x18000a38a  mov     rcx, [rsp+2B0h+ppv]
0x18000a38f  lea     rdx, [rsp+2B0h+pidl2]
0x18000a394  mov     [rsp+2B0h+pidl2], r12
0x18000a399  mov     r9, r14
0x18000a39c  mov     [rsp+2B0h+var_280], r12
0x18000a3a1  xor     r8d, r8d
0x18000a3a4  mov     [rsp+2B0h+var_288], rdx
0x18000a3a9  xor     edx, edx
0x18000a3ab  mov     rax, [rcx]
0x18000a3ae  mov     [rsp+2B0h+psfgaoOut], r12
0x18000a3b3  mov     rax, [rax+18h]
0x18000a3b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a3bc  mov     ebx, eax
0x18000a3be  test    eax, eax
0x18000a3c0  js      short loc_18000A3F0
0x18000a3c2  mov     rdx, [rsp+2B0h+pidl2]; pidl2
0x18000a3c7  mov     rcx, [rsp+2B0h+ppidl]; pidl1
0x18000a3cc  call    cs:__imp_ILCombine
0x18000a3d2  mov     rcx, rax
0x18000a3d5  mov     rdi, rax
0x18000a3d8  neg     rcx
0x18000a3db  mov     rcx, [rsp+2B0h+pidl2]; pidl
0x18000a3e0  sbb     ebx, ebx
0x18000a3e2  not     ebx
0x18000a3e4  and     ebx, 8007000Eh
0x18000a3ea  call    cs:__imp_ILFree
0x18000a3f0  mov     rcx, [rsp+2B0h+ppv]
0x18000a3f5  mov     rdx, [rcx]
0x18000a3f8  mov     rax, [rdx+10h]
0x18000a3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a401  jmp     short loc_18000A42A
0x18000a403  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18000a408  test    rcx, rcx
0x18000a40b  jz      short loc_18000A425
0x18000a40d  call    cs:__imp_ILClone
0x18000a413  mov     rdi, rax
0x18000a416  neg     rax
0x18000a419  sbb     ebx, ebx
0x18000a41b  not     ebx
0x18000a41d  and     ebx, 8007000Eh
0x18000a423  jmp     short loc_18000A42A
0x18000a425  mov     ebx, 80070057h
0x18000a42a  mov     rcx, [rsp+2B0h+ppidl]; pidl
0x18000a42f  call    cs:__imp_ILFree
0x18000a435  test    ebx, ebx
0x18000a437  js      short loc_18000A460
0x18000a439  mov     rcx, [rsp+2B0h+ppvOut]
0x18000a43e  mov     r8d, r15d
0x18000a441  shl     r8d, 1Eh
0x18000a445  mov     rdx, rdi
0x18000a448  inc     r8d
0x18000a44b  mov     rax, [rcx]
0x18000a44e  mov     rax, [rax+58h]
0x18000a452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a457  mov     rcx, rdi; pidl
0x18000a45a  call    cs:__imp_ILFree
0x18000a460  mov     rcx, [rsp+2B0h+ppvOut]
0x18000a465  mov     rax, [rcx]
0x18000a468  mov     rax, [rax+10h]
0x18000a46c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a471  mov     rcx, [rbp+1B0h+var_40]
0x18000a478  xor     rcx, rsp; StackCookie
0x18000a47b  call    __security_check_cookie
0x18000a480  add     rsp, 280h
0x18000a487  pop     r15
0x18000a489  pop     r14
0x18000a48b  pop     r12
0x18000a48d  pop     rdi
0x18000a48e  pop     rsi
0x18000a48f  pop     rbx
0x18000a490  pop     rbp
0x18000a491  retn
```
