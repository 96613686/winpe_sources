# RefreshTree(_DeviceTreeData *)

- ea: `0x180006514`
- end: `0x180006723`
- name: `?RefreshTree@@YAHPEAU_DeviceTreeData@@@Z`
- size: `527`
- prototype: `__int64 __fastcall(struct _DeviceTreeData *)`
- caller_count: `3`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x180003d70`
- `0x180004114`
- `0x1800048d8`

## callees

- `0x18000312c`
- `0x180003964`
- `0x1800039b8`
- `0x180003a14`
- `0x180003c60`
- `0x180006514`

## import_xrefs

- `USER32!SetDlgItemTextW` at `0x1800066f8`
- `USER32!SetDlgItemTextW` at `0x1800066f8`
- `USER32!SetTimer` at `0x180006551`
- `USER32!SetTimer` at `0x180006551`
- `USER32!LoadCursorW` at `0x180006565`
- `USER32!LoadCursorW` at `0x180006565`
- `USER32!SendMessageW` at `0x180006589`
- `USER32!SendMessageW` at `0x1800065bc`
- `USER32!SendMessageW` at `0x18000666a`
- `USER32!SendMessageW` at `0x180006682`
- `USER32!SendMessageW` at `0x1800066a3`
- `USER32!SendMessageW` at `0x1800066ae`
- `USER32!SendMessageW` at `0x180006589`
- `USER32!SendMessageW` at `0x1800065bc`
- `USER32!SendMessageW` at `0x18000666a`
- `USER32!SendMessageW` at `0x180006682`
- `USER32!SendMessageW` at `0x1800066a3`
- `USER32!SendMessageW` at `0x1800066ae`
- `USER32!GetDlgItem` at `0x1800066bd`
- `USER32!GetDlgItem` at `0x1800066d7`
- `USER32!GetDlgItem` at `0x1800066bd`
- `USER32!GetDlgItem` at `0x1800066d7`
- `USER32!EnableWindow` at `0x1800066c8`
- `USER32!EnableWindow` at `0x1800066e2`
- `USER32!EnableWindow` at `0x1800066c8`
- `USER32!EnableWindow` at `0x1800066e2`
- `USER32!SetCursor` at `0x18000656e`
- `USER32!SetCursor` at `0x180006701`
- `USER32!SetCursor` at `0x18000656e`
- `USER32!SetCursor` at `0x180006701`
- `COMCTL32!ImageList_GetImageCount` at `0x1800065dd`
- `COMCTL32!ImageList_GetImageCount` at `0x1800065dd`
- `COMCTL32!ImageList_Remove` at `0x1800065f3`
- `COMCTL32!ImageList_Remove` at `0x1800065f3`
- `CFGMGR32!CM_Get_Child_Ex` at `0x18000660d`
- `CFGMGR32!CM_Get_Child_Ex` at `0x18000660d`

## pseudocode

```c
__int64 __fastcall RefreshTree(struct _DeviceTreeData *a1)
{
  bool v1; // zf
  HCURSOR CursorW; // rax
  HCURSOR v5; // rax
  HWND v6; // rcx
  HCURSOR v7; // r12
  __int64 v8; // rax
  unsigned int v9; // r14d
  struct _IMAGELIST *v10; // rsi
  int v11; // edi
  int ImageCount; // ebp
  struct _DeviceTreeNode *v13; // rax
  LRESULT v14; // rdi
  HWND v15; // rcx
  HWND DlgItem; // rax
  HWND v17; // rax
  DEVNODE pdnDevInst; // [rsp+60h] [rbp+8h] BYREF

  v1 = *((_BYTE *)a1 + 99) == 0;
  pdnDevInst = 0;
  if ( v1 )
  {
    CursorW = LoadCursorW(0, (LPCWSTR)0x7F02);
    v5 = SetCursor(CursorW);
    v6 = (HWND)*((_QWORD *)a1 + 1);
    *((_BYTE *)a1 + 99) = 1;
    v7 = v5;
    SendMessageW(v6, 0xBu, 0, 0);
    v8 = *((_QWORD *)a1 + 5);
    if ( v8 )
      v9 = *(_DWORD *)(v8 + 96);
    else
      v9 = 0;
    ClearRemovalList(a1);
    SendMessageW(*((HWND *)a1 + 1), 0x1101u, 0, -65536);
    RemoveChildSiblings(a1, (struct _LIST_ENTRY *)((char *)a1 + 56));
    v10 = (struct _IMAGELIST *)*((_QWORD *)a1 + 11);
    if ( v10 )
    {
      v11 = 2;
      ImageCount = ImageList_GetImageCount(*((HIMAGELIST *)a1 + 11));
      if ( ImageCount >= 2 )
      {
        do
          ImageList_Remove(v10, v11++);
        while ( v11 <= ImageCount );
      }
    }
    if ( !CM_Get_Child_Ex(&pdnDevInst, *((_DWORD *)a1 + 18), 0, 0) )
      AddChildSiblings(a1, 0, pdnDevInst, 0, 1);
    DisplayChildSiblings(a1, (struct _LIST_ENTRY *)((char *)a1 + 56), 0, 0);
    v13 = DevTreeNodeByDevNode(v9, (struct _LIST_ENTRY *)((char *)a1 + 56));
    if ( !v13 || (v14 = *((_QWORD *)v13 + 11)) == 0 )
      v14 = SendMessageW(*((HWND *)a1 + 1), 0x110Au, 0, 0);
    SendMessageW(*((HWND *)a1 + 1), 0xBu, 1u, 0);
    v15 = (HWND)*((_QWORD *)a1 + 1);
    *((_BYTE *)a1 + 99) = 0;
    if ( v14 )
    {
      SendMessageW(v15, 0x110Bu, 9u, v14);
    }
    else
    {
      SendMessageW(v15, 0x110Bu, 9u, 0);
      DlgItem = GetDlgItem(*((HWND *)a1 + 2), 305);
      EnableWindow(DlgItem, 0);
      v17 = GetDlgItem(*((HWND *)a1 + 2), 311);
      EnableWindow(v17, 0);
      SetDlgItemTextW(*((HWND *)a1 + 2), 309, &String);
    }
    SetCursor(v7);
    return 1;
  }
  else
  {
    *((_BYTE *)a1 + 100) = 1;
    SetTimer(*((HWND *)a1 + 2), 0x10E1u, 0x3E8u, 0);
    return 0;
  }
}

```

## disassembly

```asm
0x180006514  mov     [rsp+arg_8], rbx
0x180006519  mov     [rsp+arg_10], rbp
0x18000651e  push    rsi
0x18000651f  push    rdi
0x180006520  push    r12
0x180006522  push    r14
0x180006524  push    r15
0x180006526  sub     rsp, 30h
0x18000652a  cmp     byte ptr [rcx+63h], 0
0x18000652e  mov     rbx, rcx
0x180006531  mov     [rsp+58h+pdnDevInst], 0
0x180006539  jz      short loc_18000655E
0x18000653b  mov     byte ptr [rcx+64h], 1
0x18000653f  xor     r9d, r9d; lpTimerFunc
0x180006542  mov     rcx, [rcx+10h]; hWnd
0x180006546  mov     edx, 10E1h; nIDEvent
0x18000654b  mov     r8d, 3E8h; uElapse
0x180006551  call    cs:__imp_SetTimer
0x180006557  xor     eax, eax
0x180006559  jmp     loc_18000670C
0x18000655e  mov     edx, 7F02h; lpCursorName
0x180006563  xor     ecx, ecx; hInstance
0x180006565  call    cs:__imp_LoadCursorW
0x18000656b  mov     rcx, rax; hCursor
0x18000656e  call    cs:__imp_SetCursor
0x180006574  mov     rcx, [rbx+8]; hWnd
0x180006578  xor     r9d, r9d; lParam
0x18000657b  xor     r8d, r8d; wParam
0x18000657e  mov     byte ptr [rbx+63h], 1
0x180006582  mov     r12, rax
0x180006585  lea     edx, [r9+0Bh]; Msg
0x180006589  call    cs:__imp_SendMessageW
0x18000658f  mov     rax, [rbx+28h]
0x180006593  test    rax, rax
0x180006596  jz      short loc_18000659E
0x180006598  mov     r14d, [rax+60h]
0x18000659c  jmp     short loc_1800065A1
0x18000659e  xor     r14d, r14d
0x1800065a1  mov     rcx, rbx; struct _DeviceTreeData *
0x1800065a4  call    ?ClearRemovalList@@YAXPEAU_DeviceTreeData@@@Z; ClearRemovalList(_DeviceTreeData *)
0x1800065a9  mov     rcx, [rbx+8]; hWnd
0x1800065ad  mov     r9, 0FFFFFFFFFFFF0000h; lParam
0x1800065b4  xor     r8d, r8d; wParam
0x1800065b7  mov     edx, 1101h; Msg
0x1800065bc  call    cs:__imp_SendMessageW
0x1800065c2  lea     r15, [rbx+38h]
0x1800065c6  mov     rcx, rbx; struct _DeviceTreeData *
0x1800065c9  mov     rdx, r15; struct _LIST_ENTRY *
0x1800065cc  call    ?RemoveChildSiblings@@YAXPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@@Z; RemoveChildSiblings(_DeviceTreeData *,_LIST_ENTRY *)
0x1800065d1  mov     rsi, [rbx+58h]
0x1800065d5  test    rsi, rsi
0x1800065d8  jz      short loc_1800065FF
0x1800065da  mov     rcx, rsi; himl
0x1800065dd  call    cs:__imp_ImageList_GetImageCount
0x1800065e3  mov     edi, 2
0x1800065e8  mov     ebp, eax
0x1800065ea  cmp     eax, edi
0x1800065ec  jl      short loc_1800065FF
0x1800065ee  mov     edx, edi; i
0x1800065f0  mov     rcx, rsi; himl
0x1800065f3  call    cs:__imp_ImageList_Remove
0x1800065f9  inc     edi
0x1800065fb  cmp     edi, ebp
0x1800065fd  jle     short loc_1800065EE
0x1800065ff  mov     edx, [rbx+48h]; dnDevInst
0x180006602  lea     rcx, [rsp+58h+pdnDevInst]; pdnDevInst
0x180006607  xor     r9d, r9d; hMachine
0x18000660a  xor     r8d, r8d; ulFlags
0x18000660d  call    cs:__imp_CM_Get_Child_Ex
0x180006613  test    eax, eax
0x180006615  jnz     short loc_180006631
0x180006617  mov     r8d, [rsp+58h+pdnDevInst]; unsigned int
0x18000661c  xor     r9d, r9d; int
0x18000661f  xor     edx, edx; struct _DeviceTreeNode *
0x180006621  mov     [rsp+58h+var_38], 1; int
0x180006629  mov     rcx, rbx; struct _DeviceTreeData *
0x18000662c  call    ?AddChildSiblings@@YAJPEAU_DeviceTreeData@@PEAU_DeviceTreeNode@@KHH@Z; AddChildSiblings(_DeviceTreeData *,_DeviceTreeNode *,ulong,int,int)
0x180006631  xor     r9d, r9d; int
0x180006634  xor     r8d, r8d; struct _TREEITEM *
0x180006637  mov     rdx, r15; struct _LIST_ENTRY *
0x18000663a  mov     rcx, rbx; struct _DeviceTreeData *
0x18000663d  call    ?DisplayChildSiblings@@YAHPEAU_DeviceTreeData@@PEAU_LIST_ENTRY@@PEAU_TREEITEM@@H@Z; DisplayChildSiblings(_DeviceTreeData *,_LIST_ENTRY *,_TREEITEM *,int)
0x180006642  mov     rdx, r15; struct _LIST_ENTRY *
0x180006645  mov     ecx, r14d; unsigned int
0x180006648  call    ?DevTreeNodeByDevNode@@YAPEAU_DeviceTreeNode@@KPEAU_LIST_ENTRY@@@Z; DevTreeNodeByDevNode(ulong,_LIST_ENTRY *)
0x18000664d  test    rax, rax
0x180006650  jz      short loc_18000665B
0x180006652  mov     rdi, [rax+58h]
0x180006656  test    rdi, rdi
0x180006659  jnz     short loc_180006673
0x18000665b  mov     rcx, [rbx+8]; hWnd
0x18000665f  xor     r9d, r9d; lParam
0x180006662  xor     r8d, r8d; wParam
0x180006665  mov     edx, 110Ah; Msg
0x18000666a  call    cs:__imp_SendMessageW
0x180006670  mov     rdi, rax
0x180006673  mov     rcx, [rbx+8]; hWnd
0x180006677  xor     r9d, r9d; lParam
0x18000667a  lea     edx, [r9+0Bh]; Msg
0x18000667e  lea     r8d, [r9+1]; wParam
0x180006682  call    cs:__imp_SendMessageW
0x180006688  mov     rcx, [rbx+8]; hWnd
0x18000668c  mov     edx, 110Bh; Msg
0x180006691  mov     byte ptr [rbx+63h], 0
0x180006695  mov     r8d, 9; wParam
0x18000669b  test    rdi, rdi
0x18000669e  jz      short loc_1800066AB
0x1800066a0  mov     r9, rdi; lParam
0x1800066a3  call    cs:__imp_SendMessageW
0x1800066a9  jmp     short loc_1800066FE
0x1800066ab  xor     r9d, r9d; lParam
0x1800066ae  call    cs:__imp_SendMessageW
0x1800066b4  mov     rcx, [rbx+10h]; hDlg
0x1800066b8  mov     edx, 131h; nIDDlgItem
0x1800066bd  call    cs:__imp_GetDlgItem
0x1800066c3  mov     rcx, rax; hWnd
0x1800066c6  xor     edx, edx; bEnable
0x1800066c8  call    cs:__imp_EnableWindow
0x1800066ce  mov     rcx, [rbx+10h]; hDlg
0x1800066d2  mov     edx, 137h; nIDDlgItem
0x1800066d7  call    cs:__imp_GetDlgItem
0x1800066dd  mov     rcx, rax; hWnd
0x1800066e0  xor     edx, edx; bEnable
0x1800066e2  call    cs:__imp_EnableWindow
0x1800066e8  mov     rcx, [rbx+10h]; hDlg
0x1800066ec  lea     r8, String; lpString
0x1800066f3  mov     edx, 135h; nIDDlgItem
0x1800066f8  call    cs:__imp_SetDlgItemTextW
0x1800066fe  mov     rcx, r12; hCursor
0x180006701  call    cs:__imp_SetCursor
0x180006707  mov     eax, 1
0x18000670c  mov     rbx, [rsp+58h+arg_8]
0x180006711  mov     rbp, [rsp+58h+arg_10]
0x180006716  add     rsp, 30h
0x18000671a  pop     r15
0x18000671c  pop     r14
0x18000671e  pop     r12
0x180006720  pop     rdi
0x180006721  pop     rsi
0x180006722  retn
```
