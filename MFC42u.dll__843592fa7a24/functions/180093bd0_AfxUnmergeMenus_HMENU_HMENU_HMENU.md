# AfxUnmergeMenus(HMENU__ *,HMENU__ *,HMENU__ *)

- ea: `0x180093bd0`
- end: `0x180093c9c`
- name: `?AfxUnmergeMenus@@YAXPEAUHMENU__@@00@Z`
- size: `204`
- prototype: `void __fastcall(HMENU hMenu, HMENU, HMENU)`
- caller_count: `4`
- callee_count: `1`
- tags: ``

## callers

- `0x180085070`
- `0x180091e20`
- `0x1800b29e0`
- `0x1800b9f90`

## callees

- `0x180093bd0`

## import_xrefs

- `USER32!GetMenuItemCount` at `0x180093bed`
- `USER32!GetMenuItemCount` at `0x180093bf9`
- `USER32!GetMenuItemCount` at `0x180093c1e`
- `USER32!GetMenuItemCount` at `0x180093bed`
- `USER32!GetMenuItemCount` at `0x180093bf9`
- `USER32!GetMenuItemCount` at `0x180093c1e`
- `USER32!GetSubMenu` at `0x180093c08`
- `USER32!GetSubMenu` at `0x180093c31`
- `USER32!GetSubMenu` at `0x180093c62`
- `USER32!GetSubMenu` at `0x180093c08`
- `USER32!GetSubMenu` at `0x180093c31`
- `USER32!GetSubMenu` at `0x180093c62`
- `USER32!RemoveMenu` at `0x180093c4b`
- `USER32!RemoveMenu` at `0x180093c7c`
- `USER32!RemoveMenu` at `0x180093c4b`
- `USER32!RemoveMenu` at `0x180093c7c`

## pseudocode

```c
void __fastcall AfxUnmergeMenus(HMENU hMenu, HMENU a2, HMENU a3)
{
  int MenuItemCount; // r13d
  int v7; // edi
  HMENU SubMenu; // rax
  HMENU v9; // rsi
  int v10; // ebp
  signed int i; // ebx
  int j; // ebx

  MenuItemCount = GetMenuItemCount(a2);
  v7 = GetMenuItemCount(hMenu);
LABEL_14:
  while ( --v7 >= 0 )
  {
    SubMenu = GetSubMenu(hMenu, v7);
    v9 = SubMenu;
    if ( SubMenu )
    {
      if ( a3 )
      {
        v10 = GetMenuItemCount(SubMenu);
        for ( i = 0; i < v10; ++i )
        {
          if ( GetSubMenu(v9, i) == a3 )
          {
            RemoveMenu(v9, i, 0x400u);
            a3 = 0;
            goto LABEL_14;
          }
        }
      }
      else
      {
        for ( j = 0; j < MenuItemCount; ++j )
        {
          if ( GetSubMenu(a2, j) == v9 )
          {
            RemoveMenu(hMenu, v7, 0x400u);
            goto LABEL_14;
          }
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180093bd0  push    rbx
0x180093bd2  push    rbp
0x180093bd3  push    rsi
0x180093bd4  push    rdi
0x180093bd5  push    r12
0x180093bd7  push    r13
0x180093bd9  push    r14
0x180093bdb  push    r15
0x180093bdd  sub     rsp, 28h
0x180093be1  mov     r15, rcx
0x180093be4  mov     r14, r8
0x180093be7  mov     rcx, rdx; hMenu
0x180093bea  mov     r12, rdx
0x180093bed  call    cs:__imp_GetMenuItemCount
0x180093bf3  mov     rcx, r15; hMenu
0x180093bf6  mov     r13d, eax
0x180093bf9  call    cs:__imp_GetMenuItemCount
0x180093bff  mov     edi, eax
0x180093c01  jmp     short loc_180093C82
0x180093c03  mov     edx, edi; nPos
0x180093c05  mov     rcx, r15; hMenu
0x180093c08  call    cs:__imp_GetSubMenu
0x180093c0e  mov     rsi, rax
0x180093c11  test    rax, rax
0x180093c14  jz      short loc_180093C82
0x180093c16  test    r14, r14
0x180093c19  jz      short loc_180093C56
0x180093c1b  mov     rcx, rax; hMenu
0x180093c1e  call    cs:__imp_GetMenuItemCount
0x180093c24  mov     ebp, eax
0x180093c26  xor     ebx, ebx
0x180093c28  cmp     ebx, ebp
0x180093c2a  jge     short loc_180093C82
0x180093c2c  mov     edx, ebx; nPos
0x180093c2e  mov     rcx, rsi; hMenu
0x180093c31  call    cs:__imp_GetSubMenu
0x180093c37  cmp     rax, r14
0x180093c3a  jz      short loc_180093C40
0x180093c3c  inc     ebx
0x180093c3e  jmp     short loc_180093C28
0x180093c40  mov     r8d, 400h; uFlags
0x180093c46  mov     edx, ebx; uPosition
0x180093c48  mov     rcx, rsi; hMenu
0x180093c4b  call    cs:__imp_RemoveMenu
0x180093c51  xor     r14d, r14d
0x180093c54  jmp     short loc_180093C82
0x180093c56  xor     ebx, ebx
0x180093c58  cmp     ebx, r13d
0x180093c5b  jge     short loc_180093C82
0x180093c5d  mov     edx, ebx; nPos
0x180093c5f  mov     rcx, r12; hMenu
0x180093c62  call    cs:__imp_GetSubMenu
0x180093c68  cmp     rax, rsi
0x180093c6b  jz      short loc_180093C71
0x180093c6d  inc     ebx
0x180093c6f  jmp     short loc_180093C58
0x180093c71  mov     r8d, 400h; uFlags
0x180093c77  mov     edx, edi; uPosition
0x180093c79  mov     rcx, r15; hMenu
0x180093c7c  call    cs:__imp_RemoveMenu
0x180093c82  sub     edi, 1
0x180093c85  jns     loc_180093C03
0x180093c8b  add     rsp, 28h
0x180093c8f  pop     r15
0x180093c91  pop     r14
0x180093c93  pop     r13
0x180093c95  pop     r12
0x180093c97  pop     rdi
0x180093c98  pop     rsi
0x180093c99  pop     rbp
0x180093c9a  pop     rbx
0x180093c9b  retn
```
