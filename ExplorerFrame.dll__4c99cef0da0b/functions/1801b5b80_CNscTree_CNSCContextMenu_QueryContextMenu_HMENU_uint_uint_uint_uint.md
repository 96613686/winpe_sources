# CNscTree::CNSCContextMenu::QueryContextMenu(HMENU__ *,uint,uint,uint,uint)

- ea: `0x1801b5b80`
- end: `0x1801b5d80`
- name: `?QueryContextMenu@CNSCContextMenu@CNscTree@@UEAAJPEAUHMENU__@@IIII@Z`
- size: `512`
- prototype: `int(CNscTree::CNSCContextMenu *__hidden this, HMENU, unsigned int, unsigned int, unsigned int, unsigned int)`
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x18002c1d0`
- `0x18009946c`
- `0x1801b5b80`

## import_xrefs

- `SHELL32!__imp_Shell_MergeMenus` at `0x1801b5d38`
- `SHELL32!__imp_Shell_MergeMenus` at `0x1801b5d38`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x1801b5bc3`
- `SHLWAPI!__imp_SHLoadMenuPopup` at `0x1801b5bc3`
- `USER32!SetMenuDefaultItem` at `0x1801b5d5d`
- `USER32!SetMenuDefaultItem` at `0x1801b5d5d`
- `USER32!SendMessageW` at `0x1801b5c1f`
- `USER32!SendMessageW` at `0x1801b5cd3`
- `USER32!SendMessageW` at `0x1801b5c1f`
- `USER32!SendMessageW` at `0x1801b5cd3`
- `USER32!EnableMenuItem` at `0x1801b5cec`
- `USER32!EnableMenuItem` at `0x1801b5cec`
- `USER32!DeleteMenu` at `0x1801b5c5b`
- `USER32!DeleteMenu` at `0x1801b5c70`
- `USER32!DeleteMenu` at `0x1801b5c85`
- `USER32!DeleteMenu` at `0x1801b5d16`
- `USER32!DeleteMenu` at `0x1801b5c5b`
- `USER32!DeleteMenu` at `0x1801b5c70`
- `USER32!DeleteMenu` at `0x1801b5c85`
- `USER32!DeleteMenu` at `0x1801b5d16`
- `USER32!DestroyMenu` at `0x1801b5d43`
- `USER32!DestroyMenu` at `0x1801b5d43`

## pseudocode

```c
__int64 __fastcall CNscTree::CNSCContextMenu::QueryContextMenu(
        struct _TREEITEM **this,
        HMENU a2,
        UINT a3,
        UINT a4,
        UINT uIDAdjustMax,
        char a6)
{
  struct _TREEITEM **v7; // rbx
  int IsExpandable; // r12d
  HMENU v11; // rsi
  LPARAM v12; // rcx
  int v13; // edi
  HWND v14; // rcx
  HWND v15; // rcx
  UINT v16; // ebx
  LPARAM lParam[2]; // [rsp+30h] [rbp-48h] BYREF
  __int128 v20; // [rsp+40h] [rbp-38h]
  __int128 v21; // [rsp+50h] [rbp-28h]
  __int64 v22; // [rsp+60h] [rbp-18h]

  v7 = this - 46;
  IsExpandable = CNscTree::_IsExpandable((CNscTree *)(this - 46), this[1]);
  v11 = (HMENU)SHLoadMenuPopup(g_hinst, 3400);
  if ( !v11 )
    return (unsigned int)-2147024882;
  v12 = (LPARAM)this[1];
  v13 = 0;
  if ( v12 )
  {
    if ( IsExpandable )
    {
      lParam[0] = 0;
      lParam[1] = v12;
      v14 = (HWND)v7[50];
      v20 = 0;
      v22 = 0;
      v21 = 0;
      LODWORD(lParam[0]) = 8;
      DWORD1(v20) = 32;
      if ( !(unsigned int)SendMessageW(v14, 0x113Eu, 0, (LPARAM)lParam) || (v13 = 9, (v20 & 0x20) == 0) )
        v13 = 8;
      if ( v13 == 8 )
        goto LABEL_11;
    }
    else
    {
      v13 = (*((_DWORD *)v7 + 113) & 0x800) == 0;
    }
  }
  DeleteMenu(v11, 8u, 0);
LABEL_11:
  if ( v13 == 9 || (DeleteMenu(v11, 9u, 0), v13 != 1) )
  {
    DeleteMenu(v11, 1u, 0);
    if ( v13 == 8 && (*((_DWORD *)v7 + 113) & 0x80000) == 0 )
    {
      v15 = (HWND)v7[50];
      *(_OWORD *)lParam = 0;
      v22 = 0;
      lParam[1] = (LPARAM)this[1];
      v20 = 0;
      LODWORD(lParam[0]) = 64;
      v21 = 0;
      if ( (unsigned int)SendMessageW(v15, 0x113Eu, 0, (LPARAM)lParam) )
      {
        if ( !HIDWORD(v21) )
          EnableMenuItem(v11, 8u, 3u);
      }
    }
  }
  if ( !CNscTree::_ModeSupportsOrder((CNscTree *)v7, this[1]) || v7[74] )
    DeleteMenu(v11, 0xAu, 0);
  v16 = Shell_MergeMenus(a2, v11, a3, a4, uIDAdjustMax, 7u);
  DestroyMenu(v11);
  if ( v13 && (a6 & 0x20) == 0 )
    SetMenuDefaultItem(a2, v13 + a4, 0);
  return v16 - a4;
}

```

## disassembly

```asm
0x1801b5b80  mov     [rsp-40h+uInsert], r8d
0x1801b5b85  push    rbp
0x1801b5b86  push    rbx
0x1801b5b87  push    rsi
0x1801b5b88  push    rdi
0x1801b5b89  push    r12
0x1801b5b8b  push    r13
0x1801b5b8d  push    r14
0x1801b5b8f  push    r15
0x1801b5b91  mov     rbp, rsp
0x1801b5b94  sub     rsp, 78h
0x1801b5b98  mov     r13, rdx
0x1801b5b9b  lea     rbx, [rcx-170h]
0x1801b5ba2  mov     rdx, [rcx+8]; struct _TREEITEM *
0x1801b5ba6  mov     r15, rcx
0x1801b5ba9  mov     rcx, rbx; this
0x1801b5bac  mov     r14d, r9d
0x1801b5baf  call    ?_IsExpandable@CNscTree@@AEAAHPEAU_TREEITEM@@@Z; CNscTree::_IsExpandable(_TREEITEM *)
0x1801b5bb4  mov     rcx, cs:g_hinst
0x1801b5bbb  mov     edx, 0D48h
0x1801b5bc0  mov     r12d, eax
0x1801b5bc3  call    cs:__imp_SHLoadMenuPopup
0x1801b5bc9  mov     rsi, rax
0x1801b5bcc  test    rax, rax
0x1801b5bcf  jz      loc_1801B5D68
0x1801b5bd5  mov     rcx, [r15+8]
0x1801b5bd9  xor     edi, edi
0x1801b5bdb  test    rcx, rcx
0x1801b5bde  jz      short loc_1801B5C51
0x1801b5be0  test    r12d, r12d
0x1801b5be3  jz      short loc_1801B5C40
0x1801b5be5  xorps   xmm0, xmm0
0x1801b5be8  lea     r9, [rbp+lParam]; lParam
0x1801b5bec  movups  xmmword ptr [rbp+lParam], xmm0
0x1801b5bf0  mov     [rbp+lParam+8], rcx
0x1801b5bf4  xor     eax, eax
0x1801b5bf6  mov     rcx, [rbx+190h]; hWnd
0x1801b5bfd  xor     r8d, r8d; wParam
0x1801b5c00  movups  [rbp+var_38], xmm0
0x1801b5c04  mov     edx, 113Eh; Msg
0x1801b5c09  mov     [rbp+var_18], rax
0x1801b5c0d  movups  [rbp+var_28], xmm0
0x1801b5c11  mov     dword ptr [rbp+lParam], 8
0x1801b5c18  mov     dword ptr [rbp+var_38+4], 20h ; ' '
0x1801b5c1f  call    cs:__imp_SendMessageW
0x1801b5c25  test    eax, eax
0x1801b5c27  jz      short loc_1801B5C34
0x1801b5c29  test    byte ptr [rbp+var_38], 20h
0x1801b5c2d  mov     edi, 9
0x1801b5c32  jnz     short loc_1801B5C39
0x1801b5c34  mov     edi, 8
0x1801b5c39  cmp     edi, 8
0x1801b5c3c  jz      short loc_1801B5C61
0x1801b5c3e  jmp     short loc_1801B5C51
0x1801b5c40  test    dword ptr [rbx+1C4h], 800h
0x1801b5c4a  jnz     short loc_1801B5C51
0x1801b5c4c  mov     edi, 1
0x1801b5c51  xor     r8d, r8d; uFlags
0x1801b5c54  mov     rcx, rsi; hMenu
0x1801b5c57  lea     edx, [r8+8]; uPosition
0x1801b5c5b  call    cs:__imp_DeleteMenu
0x1801b5c61  cmp     edi, 9
0x1801b5c64  jz      short loc_1801B5C7B
0x1801b5c66  xor     r8d, r8d; uFlags
0x1801b5c69  mov     rcx, rsi; hMenu
0x1801b5c6c  lea     edx, [r8+9]; uPosition
0x1801b5c70  call    cs:__imp_DeleteMenu
0x1801b5c76  cmp     edi, 1
0x1801b5c79  jz      short loc_1801B5CF2
0x1801b5c7b  xor     r8d, r8d; uFlags
0x1801b5c7e  mov     rcx, rsi; hMenu
0x1801b5c81  lea     edx, [r8+1]; uPosition
0x1801b5c85  call    cs:__imp_DeleteMenu
0x1801b5c8b  cmp     edi, 8
0x1801b5c8e  jnz     short loc_1801B5CF2
0x1801b5c90  test    dword ptr [rbx+1C4h], 80000h
0x1801b5c9a  jnz     short loc_1801B5CF2
0x1801b5c9c  mov     rcx, [rbx+190h]; hWnd
0x1801b5ca3  lea     r9, [rbp+lParam]; lParam
0x1801b5ca7  xorps   xmm0, xmm0
0x1801b5caa  xor     eax, eax
0x1801b5cac  movups  xmmword ptr [rbp+lParam], xmm0
0x1801b5cb0  mov     [rbp+var_18], rax
0x1801b5cb4  xor     r8d, r8d; wParam
0x1801b5cb7  mov     rax, [r15+8]
0x1801b5cbb  mov     edx, 113Eh; Msg
0x1801b5cc0  mov     [rbp+lParam+8], rax
0x1801b5cc4  movups  [rbp+var_38], xmm0
0x1801b5cc8  mov     dword ptr [rbp+lParam], 40h ; '@'
0x1801b5ccf  movups  [rbp+var_28], xmm0
0x1801b5cd3  call    cs:__imp_SendMessageW
0x1801b5cd9  test    eax, eax
0x1801b5cdb  jz      short loc_1801B5CF2
0x1801b5cdd  cmp     dword ptr [rbp+var_28+0Ch], 0
0x1801b5ce1  jnz     short loc_1801B5CF2
0x1801b5ce3  mov     edx, edi; uIDEnableItem
0x1801b5ce5  lea     r8d, [rdi-5]; uEnable
0x1801b5ce9  mov     rcx, rsi; hMenu
0x1801b5cec  call    cs:__imp_EnableMenuItem
0x1801b5cf2  mov     rdx, [r15+8]; struct _TREEITEM *
0x1801b5cf6  mov     rcx, rbx; this
0x1801b5cf9  call    ?_ModeSupportsOrder@CNscTree@@AEAA_NPEAU_TREEITEM@@@Z; CNscTree::_ModeSupportsOrder(_TREEITEM *)
0x1801b5cfe  test    al, al
0x1801b5d00  jz      short loc_1801B5D0C
0x1801b5d02  cmp     qword ptr [rbx+250h], 0
0x1801b5d0a  jz      short loc_1801B5D1C
0x1801b5d0c  xor     r8d, r8d; uFlags
0x1801b5d0f  mov     rcx, rsi; hMenu
0x1801b5d12  lea     edx, [r8+0Ah]; uPosition
0x1801b5d16  call    cs:__imp_DeleteMenu
0x1801b5d1c  mov     eax, [rbp+arg_20]
0x1801b5d1f  mov     r9d, r14d; uIDAdjust
0x1801b5d22  mov     r8d, [rbp+uInsert]; uInsert
0x1801b5d26  mov     rdx, rsi; hmSrc
0x1801b5d29  mov     [rsp+78h+uFlags], 7; uFlags
0x1801b5d31  mov     rcx, r13; hmDst
0x1801b5d34  mov     [rsp+78h+uIDAdjustMax], eax; uIDAdjustMax
0x1801b5d38  call    cs:__imp_Shell_MergeMenus
0x1801b5d3e  mov     rcx, rsi; hMenu
0x1801b5d41  mov     ebx, eax
0x1801b5d43  call    cs:__imp_DestroyMenu
0x1801b5d49  test    edi, edi
0x1801b5d4b  jz      short loc_1801B5D63
0x1801b5d4d  test    byte ptr [rbp+arg_28], 20h
0x1801b5d51  jnz     short loc_1801B5D63
0x1801b5d53  lea     edx, [rdi+r14]; uItem
0x1801b5d57  xor     r8d, r8d; fByPos
0x1801b5d5a  mov     rcx, r13; hMenu
0x1801b5d5d  call    cs:__imp_SetMenuDefaultItem
0x1801b5d63  sub     ebx, r14d
0x1801b5d66  jmp     short loc_1801B5D6D
0x1801b5d68  mov     ebx, 8007000Eh
0x1801b5d6d  mov     eax, ebx
0x1801b5d6f  add     rsp, 78h
0x1801b5d73  pop     r15
0x1801b5d75  pop     r14
0x1801b5d77  pop     r13
0x1801b5d79  pop     r12
0x1801b5d7b  pop     rdi
0x1801b5d7c  pop     rsi
0x1801b5d7d  pop     rbx
0x1801b5d7e  pop     rbp
0x1801b5d7f  retn
```
