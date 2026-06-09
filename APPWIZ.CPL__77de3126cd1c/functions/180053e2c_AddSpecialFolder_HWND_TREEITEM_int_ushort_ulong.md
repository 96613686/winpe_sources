# AddSpecialFolder(HWND__ *,_TREEITEM *,int,ushort *,ulong)

- ea: `0x180053e2c`
- end: `0x180053ed9`
- name: `?AddSpecialFolder@@YAPEAU_TREEITEM@@PEAUHWND__@@PEAU1@HPEAGK@Z`
- size: `173`
- prototype: `struct _TREEITEM *__fastcall(HWND hWnd, struct _TREEITEM *, int csidl, unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800548f0`

## callees

- `0x180053d54`
- `0x180053e2c`

## import_xrefs

- `SHELL32!SHGetSpecialFolderLocation` at `0x180053e55`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180053e8b`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180053e55`
- `SHELL32!SHGetSpecialFolderLocation` at `0x180053e8b`
- `SHELL32!SHGetPathFromIDListW` at `0x180053e67`
- `SHELL32!SHGetPathFromIDListW` at `0x180053e67`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ec5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053e7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180053ec5`

## pseudocode

```c
struct _TREEITEM *__fastcall AddSpecialFolder(
        HWND hWnd,
        struct _TREEITEM *a2,
        int csidl,
        unsigned __int16 *a4,
        unsigned int a5)
{
  struct _TREEITEM *v9; // rbx
  struct _ITEMIDLIST *v10; // r9
  LPITEMIDLIST ppidl[7]; // [rsp+30h] [rbp-38h] BYREF

  ppidl[0] = 0;
  v9 = 0;
  if ( SHGetSpecialFolderLocation(hWnd, csidl, ppidl) >= 0 && SHGetPathFromIDListW(ppidl[0], a4) )
  {
    if ( csidl == 16 )
    {
      CoTaskMemFree(ppidl[0]);
      if ( SHGetSpecialFolderLocation(hWnd, 0, ppidl) < 0 )
        ppidl[0] = 0;
    }
    if ( ppidl[0] )
      v9 = AddItem(hWnd, a4, a2, v10, a5 | 4);
  }
  CoTaskMemFree(ppidl[0]);
  return v9;
}

```

## disassembly

```asm
0x180053e2c  push    rbx
0x180053e2e  push    rbp
0x180053e2f  push    rsi
0x180053e30  push    rdi
0x180053e31  push    r14
0x180053e33  sub     rsp, 40h
0x180053e37  mov     esi, r8d
0x180053e3a  mov     [rsp+68h+ppidl], 0
0x180053e43  mov     r14, rdx
0x180053e46  lea     r8, [rsp+68h+ppidl]; ppidl
0x180053e4b  mov     edx, esi; csidl
0x180053e4d  mov     rbp, r9
0x180053e50  mov     rdi, rcx
0x180053e53  xor     ebx, ebx
0x180053e55  call    cs:__imp_SHGetSpecialFolderLocation
0x180053e5b  test    eax, eax
0x180053e5d  js      short loc_180053EC0
0x180053e5f  mov     rcx, [rsp+68h+ppidl]; pidl
0x180053e64  mov     rdx, rbp; pszPath
0x180053e67  call    cs:__imp_SHGetPathFromIDListW
0x180053e6d  test    eax, eax
0x180053e6f  jz      short loc_180053EC0
0x180053e71  cmp     esi, 10h
0x180053e74  jnz     short loc_180053E9A
0x180053e76  mov     rcx, [rsp+68h+ppidl]; pv
0x180053e7b  call    cs:__imp_CoTaskMemFree
0x180053e81  lea     r8, [rsp+68h+ppidl]; ppidl
0x180053e86  xor     edx, edx; csidl
0x180053e88  mov     rcx, rdi; hwnd
0x180053e8b  call    cs:__imp_SHGetSpecialFolderLocation
0x180053e91  test    eax, eax
0x180053e93  jns     short loc_180053E9A
0x180053e95  mov     [rsp+68h+ppidl], rbx
0x180053e9a  cmp     [rsp+68h+ppidl], rbx
0x180053e9f  jz      short loc_180053EC0
0x180053ea1  mov     eax, [rsp+68h+arg_20]
0x180053ea8  mov     r8, r14; struct _TREEITEM *
0x180053eab  or      eax, 4
0x180053eae  mov     rdx, rbp; unsigned __int16 *
0x180053eb1  mov     rcx, rdi; hWnd
0x180053eb4  mov     [rsp+68h+var_48], eax; unsigned int
0x180053eb8  call    ?AddItem@@YAPEAU_TREEITEM@@PEAUHWND__@@PEBGPEAU1@PEFAU_ITEMIDLIST@@K@Z; AddItem(HWND__ *,ushort const *,_TREEITEM *,_ITEMIDLIST *,ulong)
0x180053ebd  mov     rbx, rax
0x180053ec0  mov     rcx, [rsp+68h+ppidl]; pv
0x180053ec5  call    cs:__imp_CoTaskMemFree
0x180053ecb  mov     rax, rbx
0x180053ece  add     rsp, 40h
0x180053ed2  pop     r14
0x180053ed4  pop     rdi
0x180053ed5  pop     rsi
0x180053ed6  pop     rbp
0x180053ed7  pop     rbx
0x180053ed8  retn
```
