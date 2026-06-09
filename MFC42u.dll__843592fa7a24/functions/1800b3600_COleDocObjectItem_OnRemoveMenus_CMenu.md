# COleDocObjectItem::OnRemoveMenus(CMenu *)

- ea: `0x1800b3600`
- end: `0x1800b368c`
- name: `?OnRemoveMenus@COleDocObjectItem@@UEAAXPEAVCMenu@@@Z`
- size: `140`
- prototype: `void __fastcall(COleDocObjectItem *__hidden this, struct CMenu *)`
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x18002cdb0`
- `0x18002da20`
- `0x180085070`
- `0x1800b3600`

## import_xrefs

- `USER32!GetMenuItemCount` at `0x1800b3615`
- `USER32!GetMenuItemCount` at `0x1800b3648`
- `USER32!GetMenuItemCount` at `0x1800b3615`
- `USER32!GetMenuItemCount` at `0x1800b3648`
- `USER32!GetSubMenu` at `0x1800b3628`
- `USER32!GetSubMenu` at `0x1800b3628`
- `USER32!DeleteMenu` at `0x1800b3659`
- `USER32!DeleteMenu` at `0x1800b3659`
- `USER32!RemoveMenu` at `0x1800b3671`
- `USER32!RemoveMenu` at `0x1800b3671`

## pseudocode

```c
void __fastcall COleDocObjectItem::OnRemoveMenus(COleDocObjectItem *this, HMENU *a2)
{
  int MenuItemCount; // eax
  UINT v5; // ebp
  HMENU SubMenu; // rax
  struct CMenu *v7; // rax
  struct CMenu *v8; // rsi
  signed int i; // edi

  MenuItemCount = GetMenuItemCount(a2[1]);
  if ( MenuItemCount )
  {
    v5 = MenuItemCount - 1;
    SubMenu = GetSubMenu(a2[1], MenuItemCount - 1);
    v7 = CMenu::FromHandle(SubMenu);
    v8 = v7;
    if ( !v7 )
      AfxThrowInvalidArgException();
    for ( i = GetMenuItemCount(*((HMENU *)v7 + 1)) - 1; i > 0; --i )
      DeleteMenu(*((HMENU *)v8 + 1), i, 0x400u);
    RemoveMenu(a2[1], v5, 0x400u);
  }
  COleClientItem::OnRemoveMenus(this, (struct CMenu *)a2);
}

```

## disassembly

```asm
0x1800b3600  push    rbx
0x1800b3602  push    rbp
0x1800b3603  push    rsi
0x1800b3604  push    rdi
0x1800b3605  push    r14
0x1800b3607  sub     rsp, 20h
0x1800b360b  mov     r14, rcx
0x1800b360e  mov     rbx, rdx
0x1800b3611  mov     rcx, [rdx+8]; hMenu
0x1800b3615  call    cs:__imp_GetMenuItemCount
0x1800b361b  test    eax, eax
0x1800b361d  jz      short loc_1800B3677
0x1800b361f  mov     rcx, [rbx+8]; hMenu
0x1800b3623  lea     ebp, [rax-1]
0x1800b3626  mov     edx, ebp; nPos
0x1800b3628  call    cs:__imp_GetSubMenu
0x1800b362e  mov     rcx, rax; HMENU
0x1800b3631  call    ?FromHandle@CMenu@@SAPEAV1@PEAUHMENU__@@@Z; CMenu::FromHandle(HMENU__ *)
0x1800b3636  mov     rsi, rax
0x1800b3639  test    rax, rax
0x1800b363c  jnz     short loc_1800B3644
0x1800b363e  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x1800b3644  mov     rcx, [rax+8]; hMenu
0x1800b3648  call    cs:__imp_GetMenuItemCount
0x1800b364e  lea     edi, [rax-1]
0x1800b3651  jmp     short loc_1800B3661
0x1800b3653  mov     rcx, [rsi+8]; hMenu
0x1800b3657  mov     edx, edi; uPosition
0x1800b3659  call    cs:__imp_DeleteMenu
0x1800b365f  dec     edi
0x1800b3661  mov     r8d, 400h; uFlags
0x1800b3667  test    edi, edi
0x1800b3669  jg      short loc_1800B3653
0x1800b366b  mov     rcx, [rbx+8]; hMenu
0x1800b366f  mov     edx, ebp; uPosition
0x1800b3671  call    cs:__imp_RemoveMenu
0x1800b3677  mov     rdx, rbx; struct CMenu *
0x1800b367a  mov     rcx, r14; this
0x1800b367d  add     rsp, 20h
0x1800b3681  pop     r14
0x1800b3683  pop     rdi
0x1800b3684  pop     rsi
0x1800b3685  pop     rbp
0x1800b3686  pop     rbx
0x1800b3687  jmp     ?OnRemoveMenus@COleClientItem@@UEAAXPEAVCMenu@@@Z; COleClientItem::OnRemoveMenus(CMenu *)
```
