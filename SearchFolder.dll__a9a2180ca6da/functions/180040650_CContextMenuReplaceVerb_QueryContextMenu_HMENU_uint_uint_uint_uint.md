# CContextMenuReplaceVerb::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x180040650`
- end: `0x1800407e2`
- name: `?QueryContextMenu@CContextMenuReplaceVerb@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `402`
- prototype: `int(CContextMenuReplaceVerb *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180006900`
- `0x1800076dc`
- `0x18003f810`
- `0x180040260`
- `0x180040650`

## import_xrefs

- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1800406ea`
- `ext-ms-win-ntuser-menu-l1-1-0!DeleteMenu` at `0x1800406ea`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoW` at `0x18004076b`
- `ext-ms-win-ntuser-menu-l1-1-0!GetMenuItemInfoW` at `0x18004076b`
- `ext-ms-win-ntuser-menu-l1-1-1!InsertMenuItemW` at `0x1800407a8`
- `ext-ms-win-ntuser-menu-l1-1-1!InsertMenuItemW` at `0x1800407a8`

## pseudocode

```c
__int64 __fastcall CContextMenuReplaceVerb::QueryContextMenu(
        CContextMenuReplaceVerb *this,
        HMENU a2,
        unsigned int a3,
        unsigned int a4,
        unsigned int a5,
        unsigned int a6)
{
  int ContextMenu; // r14d
  int i; // edi
  UINT MenuIndexForCanonicalVerb; // eax
  UINT v11; // r15d
  UINT v12; // r13d
  HMENU v13; // rcx
  __int64 v14; // rax
  UINT v15; // ecx
  struct tagMENUITEMINFOW mii; // [rsp+30h] [rbp-D0h] BYREF
  char v18; // [rsp+80h] [rbp-80h] BYREF

  ContextMenu = CContextMenuOnContextMenuArray::QueryContextMenu(this, a2, a3, a4, a5, a6);
  if ( ContextMenu >= 0 )
  {
    for ( i = 0; i < *((_DWORD *)this + 56); ++i )
    {
      MenuIndexForCanonicalVerb = GetMenuIndexForCanonicalVerb(
                                    a2,
                                    *((struct IContextMenu **)this + 11),
                                    *((_DWORD *)this + 15),
                                    *(const unsigned __int16 **)(*((_QWORD *)this + 27) + 24LL * i));
      v11 = MenuIndexForCanonicalVerb;
      if ( MenuIndexForCanonicalVerb != -1 )
        DeleteMenu(a2, MenuIndexForCanonicalVerb, 0x400u);
      v12 = GetMenuIndexForCanonicalVerb(
              *((HMENU *)this + 29),
              *((struct IContextMenu **)this + 12),
              *((_DWORD *)this + 15) + 1 + *((_DWORD *)this + 16),
              *(const unsigned __int16 **)(*((_QWORD *)this + 27) + 24LL * i + 8));
      if ( v12 != -1 )
      {
        memset_0(&mii, 0, sizeof(mii));
        v13 = (HMENU)*((_QWORD *)this + 29);
        mii.dwTypeData = (LPWSTR)&v18;
        mii.cbSize = 80;
        *(_QWORD *)&mii.fMask = 63;
        mii.cch = 200;
        if ( GetMenuItemInfoW(v13, v12, 1, &mii) )
        {
          v14 = *((_QWORD *)this + 27);
          v15 = mii.fState & 0xFFFFEFFF;
          mii.fState &= ~0x1000u;
          if ( (*(_BYTE *)(v14 + 24LL * i + 16) & 1) != 0 )
            mii.fState = v15 | 3;
          InsertMenuItemW(a2, v11, 1, &mii);
        }
      }
    }
  }
  return (unsigned int)ContextMenu;
}

```

## disassembly

```asm
0x180040650  push    rbp
0x180040652  push    rbx
0x180040653  push    rsi
0x180040654  push    rdi
0x180040655  push    r12
0x180040657  push    r13
0x180040659  push    r14
0x18004065b  push    r15
0x18004065d  lea     rbp, [rsp-128h]
0x180040665  sub     rsp, 228h
0x18004066c  mov     rax, cs:__security_cookie
0x180040673  xor     rax, rsp
0x180040676  mov     [rbp+160h+var_50], rax
0x18004067d  mov     eax, [rbp+160h+arg_28]
0x180040683  mov     rsi, rdx
0x180040686  mov     [rsp+260h+var_238], eax; unsigned int
0x18004068a  mov     rbx, rcx
0x18004068d  mov     eax, [rbp+160h+arg_20]
0x180040693  mov     [rsp+260h+var_240], eax; unsigned int
0x180040697  call    ?QueryContextMenu@CContextMenuOnContextMenuArray@@UEAAJPEAUHMENU__@@IIII@Z; CContextMenuOnContextMenuArray::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)
0x18004069c  mov     r14d, eax
0x18004069f  test    eax, eax
0x1800406a1  js      loc_1800407BC
0x1800406a7  xor     edi, edi
0x1800406a9  cmp     [rbx+0E0h], edi
0x1800406af  jle     loc_1800407BC
0x1800406b5  mov     r9, [rbx+0D8h]
0x1800406bc  mov     rcx, rsi; hmenu
0x1800406bf  mov     r8d, [rbx+3Ch]; unsigned int
0x1800406c3  mov     rdx, [rbx+58h]; struct IContextMenu *
0x1800406c7  movsxd  rax, edi
0x1800406ca  lea     r12, [rax+rax*2]
0x1800406ce  mov     r9, [r9+r12*8]; unsigned __int16 *
0x1800406d2  call    ?GetMenuIndexForCanonicalVerb@@YAIPEAUHMENU__@@PEAUIContextMenu@@IPEBG@Z; GetMenuIndexForCanonicalVerb(HMENU__ *,IContextMenu *,uint,ushort const *)
0x1800406d7  mov     r15d, eax
0x1800406da  cmp     eax, 0FFFFFFFFh
0x1800406dd  jz      short loc_1800406F0
0x1800406df  mov     r8d, 400h; uFlags
0x1800406e5  mov     edx, eax; uPosition
0x1800406e7  mov     rcx, rsi; hMenu
0x1800406ea  call    cs:__imp_DeleteMenu
0x1800406f0  mov     edx, [rbx+3Ch]
0x1800406f3  mov     r9, [rbx+0D8h]
0x1800406fa  inc     edx
0x1800406fc  mov     r8d, [rbx+40h]
0x180040700  mov     rcx, [rbx+0E8h]; hmenu
0x180040707  add     r8d, edx; unsigned int
0x18004070a  mov     rdx, [rbx+60h]; struct IContextMenu *
0x18004070e  mov     r9, [r9+r12*8+8]; unsigned __int16 *
0x180040713  call    ?GetMenuIndexForCanonicalVerb@@YAIPEAUHMENU__@@PEAUIContextMenu@@IPEBG@Z; GetMenuIndexForCanonicalVerb(HMENU__ *,IContextMenu *,uint,ushort const *)
0x180040718  mov     r13d, eax
0x18004071b  cmp     eax, 0FFFFFFFFh
0x18004071e  jz      loc_1800407AE
0x180040724  xor     edx, edx; Val
0x180040726  lea     rcx, [rsp+260h+mii]; void *
0x18004072b  lea     r8d, [rdx+50h]; Size
0x18004072f  call    memset_0
0x180040734  mov     rcx, [rbx+0E8h]; hmenu
0x18004073b  lea     rax, [rbp+160h+var_1E0]
0x18004073f  lea     r9, [rsp+260h+mii]; lpmii
0x180040744  mov     [rsp+260h+mii.dwTypeData], rax
0x180040749  mov     r8d, 1; fByPosition
0x18004074f  mov     [rsp+260h+mii.cbSize], 50h ; 'P'
0x180040757  mov     edx, r13d; item
0x18004075a  mov     qword ptr [rsp+260h+mii.fMask], 3Fh ; '?'
0x180040763  mov     [rsp+260h+mii.cch], 0C8h
0x18004076b  call    cs:__imp_GetMenuItemInfoW
0x180040771  test    eax, eax
0x180040773  jz      short loc_1800407AE
0x180040775  mov     ecx, [rsp+260h+mii.fState]
0x180040779  mov     rax, [rbx+0D8h]
0x180040780  btr     ecx, 0Ch
0x180040784  mov     [rsp+260h+mii.fState], ecx
0x180040788  test    byte ptr [rax+r12*8+10h], 1
0x18004078e  jz      short loc_180040797
0x180040790  or      ecx, 3
0x180040793  mov     [rsp+260h+mii.fState], ecx
0x180040797  lea     r9, [rsp+260h+mii]; lpmi
0x18004079c  mov     r8d, 1; fByPosition
0x1800407a2  mov     edx, r15d; item
0x1800407a5  mov     rcx, rsi; hmenu
0x1800407a8  call    cs:__imp_InsertMenuItemW
0x1800407ae  inc     edi
0x1800407b0  cmp     edi, [rbx+0E0h]
0x1800407b6  jl      loc_1800406B5
0x1800407bc  mov     eax, r14d
0x1800407bf  mov     rcx, [rbp+160h+var_50]
0x1800407c6  xor     rcx, rsp; StackCookie
0x1800407c9  call    __security_check_cookie
0x1800407ce  add     rsp, 228h
0x1800407d5  pop     r15
0x1800407d7  pop     r14
0x1800407d9  pop     r13
0x1800407db  pop     r12
0x1800407dd  pop     rdi
0x1800407de  pop     rsi
0x1800407df  pop     rbx
0x1800407e0  pop     rbp
0x1800407e1  retn
```
