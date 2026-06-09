# CreateNewFolder(_WIZDATA *)

- ea: `0x180053fd8`
- end: `0x180054136`
- name: `?CreateNewFolder@@YAXPEAU_WIZDATA@@@Z`
- size: `350`
- prototype: `void __fastcall(struct _WIZDATA *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180054c80`

## callees

- `0x180053d54`
- `0x180053fd8`
- `0x18005486c`
- `0x1800551a0`
- `0x1800582e0`

## import_xrefs

- `SHELL32!__imp_PathMakeUniqueName` at `0x18005408d`
- `SHELL32!__imp_PathMakeUniqueName` at `0x18005408d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005404a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180054067`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x18005404a`
- `api-ms-win-core-libraryloader-l1-2-0!LoadStringW` at `0x180054067`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005409d`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x18005409d`
- `USER32!GetDlgItem` at `0x18005400b`
- `USER32!GetDlgItem` at `0x1800540af`
- `USER32!GetDlgItem` at `0x18005400b`
- `USER32!GetDlgItem` at `0x1800540af`
- `USER32!SendMessageW` at `0x1800540fb`
- `USER32!SendMessageW` at `0x18005410f`
- `USER32!SendMessageW` at `0x1800540fb`
- `USER32!SendMessageW` at `0x18005410f`

## pseudocode

```c
void __fastcall CreateNewFolder(HWND *a1)
{
  HWND DlgItem; // rax
  struct _FILEITEMDATA *CurSel; // rax
  struct _FILEITEMDATA *v4; // rbx
  HWND v5; // rbx
  struct _ITEMIDLIST *v6; // r9
  struct _TREEITEM *v7; // rdi
  struct _TREEITEM *v8; // [rsp+30h] [rbp-2E8h] BYREF
  WCHAR Buffer[12]; // [rsp+38h] [rbp-2E0h] BYREF
  WCHAR pszLongPlate[80]; // [rsp+50h] [rbp-2C8h] BYREF
  WCHAR pszUniqueName[264]; // [rsp+F0h] [rbp-228h] BYREF

  v8 = 0;
  DlgItem = GetDlgItem(*a1, 1022);
  CurSel = GetCurSel(DlgItem, &v8);
  v4 = CurSel;
  if ( CurSel )
  {
    if ( (*(_BYTE *)CurSel & 1) != 0 )
    {
      LoadStringW(g_hinst, 0x7F4u, Buffer, 10);
      LoadStringW(g_hinst, 0x7F5u, pszLongPlate, 80);
      PathMakeUniqueName(pszUniqueName, 0x104u, Buffer, pszLongPlate, (PCWSTR)v4 + 2);
      if ( CreateDirectoryW(pszUniqueName, 0) )
      {
        v5 = GetDlgItem(*a1, 1022);
        v7 = AddItem(v5, pszUniqueName, v8, v6, 7u);
        if ( v7 )
        {
          SortFolder(v5, v8);
          SendMessageW(v5, 0x110Bu, 9u, (LPARAM)v7);
          SendMessageW(v5, 0x1141u, 0, (LPARAM)v7);
        }
      }
    }
  }
}

```

## disassembly

```asm
0x180053fd8  mov     [rsp+arg_8], rbx
0x180053fdd  push    rdi
0x180053fde  sub     rsp, 310h
0x180053fe5  mov     rax, cs:__security_cookie
0x180053fec  xor     rax, rsp
0x180053fef  mov     [rsp+318h+var_18], rax
0x180053ff7  mov     rdi, rcx
0x180053ffa  mov     [rsp+318h+var_2E8], 0
0x180054003  mov     rcx, [rcx]; hDlg
0x180054006  mov     edx, 3FEh; nIDDlgItem
0x18005400b  call    cs:__imp_GetDlgItem
0x180054011  mov     rcx, rax; hWnd
0x180054014  lea     rdx, [rsp+318h+var_2E8]; struct _TREEITEM **
0x180054019  call    ?GetCurSel@@YAPEAU_FILEITEMDATA@@PEAUHWND__@@PEAPEAU_TREEITEM@@@Z; GetCurSel(HWND__ *,_TREEITEM * *)
0x18005401e  mov     rbx, rax
0x180054021  test    rax, rax
0x180054024  jz      loc_180054115
0x18005402a  test    byte ptr [rax], 1
0x18005402d  jz      loc_180054115
0x180054033  mov     rcx, cs:g_hinst; hInstance
0x18005403a  lea     r8, [rsp+318h+Buffer]; lpBuffer
0x18005403f  mov     r9d, 0Ah; cchBufferMax
0x180054045  mov     edx, 7F4h; uID
0x18005404a  call    cs:__imp_LoadStringW
0x180054050  mov     rcx, cs:g_hinst; hInstance
0x180054057  lea     r8, [rsp+318h+pszLongPlate]; lpBuffer
0x18005405c  mov     r9d, 50h ; 'P'; cchBufferMax
0x180054062  mov     edx, 7F5h; uID
0x180054067  call    cs:__imp_LoadStringW
0x18005406d  lea     rax, [rbx+4]
0x180054071  mov     edx, 104h; cchMax
0x180054076  lea     r9, [rsp+318h+pszLongPlate]; pszLongPlate
0x18005407b  mov     [rsp+318h+pszDir], rax; pszDir
0x180054080  lea     r8, [rsp+318h+Buffer]; pszTemplate
0x180054085  lea     rcx, [rsp+318h+pszUniqueName]; pszUniqueName
0x18005408d  call    cs:__imp_PathMakeUniqueName
0x180054093  xor     edx, edx; lpSecurityAttributes
0x180054095  lea     rcx, [rsp+318h+pszUniqueName]; lpPathName
0x18005409d  call    cs:__imp_CreateDirectoryW
0x1800540a3  test    eax, eax
0x1800540a5  jz      short loc_180054115
0x1800540a7  mov     rcx, [rdi]; hDlg
0x1800540aa  mov     edx, 3FEh; nIDDlgItem
0x1800540af  call    cs:__imp_GetDlgItem
0x1800540b5  mov     r8, [rsp+318h+var_2E8]; struct _TREEITEM *
0x1800540ba  lea     rdx, [rsp+318h+pszUniqueName]; unsigned __int16 *
0x1800540c2  mov     rcx, rax; hWnd
0x1800540c5  mov     dword ptr [rsp+318h+pszDir], 7; unsigned int
0x1800540cd  mov     rbx, rax
0x1800540d0  call    ?AddItem@@YAPEAU_TREEITEM@@PEAUHWND__@@PEBGPEAU1@PEFAU_ITEMIDLIST@@K@Z; AddItem(HWND__ *,ushort const *,_TREEITEM *,_ITEMIDLIST *,ulong)
0x1800540d5  mov     rdi, rax
0x1800540d8  test    rax, rax
0x1800540db  jz      short loc_180054115
0x1800540dd  mov     rdx, [rsp+318h+var_2E8]; struct _TREEITEM *
0x1800540e2  mov     rcx, rbx; HWND
0x1800540e5  call    ?SortFolder@@YAXPEAUHWND__@@PEAU_TREEITEM@@@Z; SortFolder(HWND__ *,_TREEITEM *)
0x1800540ea  mov     r9, rdi; lParam
0x1800540ed  mov     edx, 110Bh; Msg
0x1800540f2  mov     r8d, 9; wParam
0x1800540f8  mov     rcx, rbx; hWnd
0x1800540fb  call    cs:__imp_SendMessageW
0x180054101  mov     r9, rdi; lParam
0x180054104  xor     r8d, r8d; wParam
0x180054107  mov     edx, 1141h; Msg
0x18005410c  mov     rcx, rbx; hWnd
0x18005410f  call    cs:__imp_SendMessageW
0x180054115  mov     rcx, [rsp+318h+var_18]
0x18005411d  xor     rcx, rsp; StackCookie
0x180054120  call    __security_check_cookie
0x180054125  mov     rbx, [rsp+318h+arg_8]
0x18005412d  add     rsp, 310h
0x180054134  pop     rdi
0x180054135  retn
```
