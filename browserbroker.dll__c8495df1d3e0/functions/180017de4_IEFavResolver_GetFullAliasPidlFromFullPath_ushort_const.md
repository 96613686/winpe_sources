# IEFavResolver::GetFullAliasPidlFromFullPath(ushort const *)

- ea: `0x180017de4`
- end: `0x180017e47`
- name: `?GetFullAliasPidlFromFullPath@IEFavResolver@@AEAAPEFAU_ITEMIDLIST@@PEBG@Z`
- size: `99`
- prototype: `struct _ITEMIDLIST *(IEFavResolver *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180016fa8`

## callees

- `0x180017de4`

## import_xrefs

- `ext-ms-win-shell-shell32-l1-2-1!ILCreateFromPathW` at `0x180017dfb`
- `ext-ms-win-shell-shell32-l1-2-1!ILCreateFromPathW` at `0x180017dfb`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180017e2e`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180017e2e`
- `api-ms-win-shell-namespace-l1-1-0!ILFindChild` at `0x180017e10`
- `api-ms-win-shell-namespace-l1-1-0!ILFindChild` at `0x180017e10`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180017e22`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x180017e22`

## pseudocode

```c
LPITEMIDLIST __fastcall IEFavResolver::GetFullAliasPidlFromFullPath(IEFavResolver *this, const unsigned __int16 *a2)
{
  LPITEMIDLIST v3; // rdi
  const ITEMIDLIST *v4; // rax
  ITEMIDLIST *v5; // rbx
  const ITEMIDLIST *v6; // rax

  v3 = 0;
  v4 = ILCreateFromPathW(a2);
  v5 = (ITEMIDLIST *)v4;
  if ( v4 )
  {
    v6 = ILFindChild(*((LPITEMIDLIST *)this + 4), v4);
    if ( v6 )
      v3 = ILCombine(*((LPCITEMIDLIST *)this + 5), v6);
    ILFree(v5);
  }
  return v3;
}

```

## disassembly

```asm
0x180017de4  mov     [rsp+arg_0], rbx
0x180017de9  mov     [rsp+arg_8], rsi
0x180017dee  push    rdi
0x180017def  sub     rsp, 20h
0x180017df3  mov     rsi, rcx
0x180017df6  xor     edi, edi
0x180017df8  mov     rcx, rdx; pszPath
0x180017dfb  call    cs:__imp_ILCreateFromPathW
0x180017e01  mov     rbx, rax
0x180017e04  test    rax, rax
0x180017e07  jz      short loc_180017E34
0x180017e09  mov     rcx, [rsi+20h]; pidlParent
0x180017e0d  mov     rdx, rax; pidlChild
0x180017e10  call    cs:__imp_ILFindChild
0x180017e16  test    rax, rax
0x180017e19  jz      short loc_180017E2B
0x180017e1b  mov     rcx, [rsi+28h]; pidl1
0x180017e1f  mov     rdx, rax; pidl2
0x180017e22  call    cs:__imp_ILCombine
0x180017e28  mov     rdi, rax
0x180017e2b  mov     rcx, rbx; pidl
0x180017e2e  call    cs:__imp_ILFree
0x180017e34  mov     rbx, [rsp+28h+arg_0]
0x180017e39  mov     rax, rdi
0x180017e3c  mov     rsi, [rsp+28h+arg_8]
0x180017e41  add     rsp, 20h
0x180017e45  pop     rdi
0x180017e46  retn
```
