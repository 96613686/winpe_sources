# SHFullIDListFromFolderAndRelativeItem

- ea: `0x1800250f0`
- end: `0x18002515f`
- name: `SHFullIDListFromFolderAndRelativeItem`
- size: `111`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800157e8`
- `0x18001b0d0`

## callees

- `0x1800250f0`
- `0x18002b228`

## import_xrefs

- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180025147`
- `api-ms-win-shell-namespace-l1-1-0!ILFree` at `0x180025147`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18002512c`
- `api-ms-win-shell-namespace-l1-1-0!ILCombine` at `0x18002512c`

## pseudocode

```c
__int64 __fastcall SHFullIDListFromFolderAndRelativeItem(__int64 a1, const ITEMIDLIST *a2, LPITEMIDLIST *a3)
{
  signed int IDList; // ebx
  LPITEMIDLIST v6; // rax
  ITEMIDLIST *v7; // rcx
  LPCITEMIDLIST pidl1; // [rsp+40h] [rbp+18h] BYREF

  *a3 = 0;
  pidl1 = 0;
  IDList = IUnknown_GetIDList(a1, &pidl1);
  if ( IDList >= 0 )
  {
    v6 = ILCombine(pidl1, a2);
    v7 = (ITEMIDLIST *)pidl1;
    *a3 = v6;
    IDList = v6 == 0 ? 0x8007000E : 0;
    ILFree(v7);
  }
  return (unsigned int)IDList;
}

```

## disassembly

```asm
0x1800250f0  mov     rax, rsp
0x1800250f3  mov     [rax+8], rbx
0x1800250f7  mov     [rax+10h], rsi
0x1800250fb  push    rdi
0x1800250fc  sub     rsp, 20h
0x180025100  mov     rsi, rdx
0x180025103  mov     qword ptr [r8], 0
0x18002510a  lea     rdx, [rax+18h]
0x18002510e  mov     qword ptr [rax+18h], 0
0x180025116  mov     rdi, r8
0x180025119  call    IUnknown_GetIDList
0x18002511e  mov     ebx, eax
0x180025120  test    eax, eax
0x180025122  js      short loc_18002514D
0x180025124  mov     rcx, [rsp+28h+pidl1]; pidl1
0x180025129  mov     rdx, rsi; pidl2
0x18002512c  call    cs:__imp_ILCombine
0x180025132  mov     rcx, [rsp+28h+pidl1]; pidl
0x180025137  mov     [rdi], rax
0x18002513a  neg     rax
0x18002513d  sbb     ebx, ebx
0x18002513f  not     ebx
0x180025141  and     ebx, 8007000Eh
0x180025147  call    cs:__imp_ILFree
0x18002514d  mov     rsi, [rsp+28h+arg_8]
0x180025152  mov     eax, ebx
0x180025154  mov     rbx, [rsp+28h+arg_0]
0x180025159  add     rsp, 20h
0x18002515d  pop     rdi
0x18002515e  retn
```
