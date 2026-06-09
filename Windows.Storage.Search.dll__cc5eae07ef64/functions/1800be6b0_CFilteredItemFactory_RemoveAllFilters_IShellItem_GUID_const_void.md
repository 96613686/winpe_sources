# CFilteredItemFactory::RemoveAllFilters(IShellItem *,_GUID const &,void * *)

- ea: `0x1800be6b0`
- end: `0x1800be7bb`
- name: `?RemoveAllFilters@CFilteredItemFactory@@UEAAJPEAUIShellItem@@AEBU_GUID@@PEAPEAX@Z`
- size: `267`
- prototype: `int(CFilteredItemFactory *__hidden this, struct IShellItem *, const struct _GUID *, void **)`
- caller_count: `0`
- callee_count: `5`
- tags: `loader_planting`

## callees

- `0x180043bcc`
- `0x180077c98`
- `0x1800bc130`
- `0x1800be6b0`
- `0x1800ea010`

## import_xrefs

- `Windows.Storage!ILFree` at `0x1800be75b`
- `Windows.Storage!ILFree` at `0x1800be7a0`
- `Windows.Storage!ILFree` at `0x1800be75b`
- `Windows.Storage!ILFree` at `0x1800be7a0`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800be6e4`
- `Windows.Storage!SHGetIDListFromObject` at `0x1800be6e4`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800be74f`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800be794`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800be74f`
- `Windows.Storage!SHCreateItemFromIDList` at `0x1800be794`

## pseudocode

```c
__int64 __fastcall CFilteredItemFactory::RemoveAllFilters(
        CFilteredItemFactory *this,
        IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT NonFilteredRoot; // ebx
  struct IShellItemVtbl *lpVtbl; // rax
  LPCITEMIDLIST pidl; // [rsp+30h] [rbp-10h] BYREF
  __int64 v11; // [rsp+38h] [rbp-8h] BYREF
  LPITEMIDLIST ppidl; // [rsp+78h] [rbp+38h] BYREF

  *a4 = 0;
  ppidl = 0;
  NonFilteredRoot = SHGetIDListFromObject(a2, &ppidl);
  if ( NonFilteredRoot >= 0 )
  {
    lpVtbl = (struct IShellItemVtbl *)a2->lpVtbl;
    v11 = 0;
    if ( ((int (__fastcall *)(IUnknown *, _QWORD, const GUID *, GUID *, __int64 *))lpVtbl->BindToHandler)(
           a2,
           0,
           &BHID_SFObject,
           &GUID_711b2cfd_93d1_422b_bdf4_69be923f2449,
           &v11) < 0 )
    {
      if ( (unsigned int)ILRemoveHiddenID(ppidl, 3203334160LL) )
        ILExpungeRemovedHiddenIDs(ppidl);
      NonFilteredRoot = SHCreateItemFromIDList(ppidl, a3, a4);
    }
    else
    {
      pidl = 0;
      NonFilteredRoot = GetNonFilteredRoot(
                          (const struct _ITEMIDLIST_ABSOLUTE *)ppidl,
                          0,
                          (struct _ITEMIDLIST_ABSOLUTE **)&pidl);
      if ( NonFilteredRoot >= 0 )
      {
        NonFilteredRoot = SHCreateItemFromIDList(pidl, a3, a4);
        ILFree((LPITEMIDLIST)pidl);
      }
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
    }
    ILFree(ppidl);
  }
  return (unsigned int)NonFilteredRoot;
}

```

## disassembly

```asm
0x1800be6b0  mov     [rsp-18h+arg_0], rbx
0x1800be6b5  mov     [rsp-18h+arg_8], rsi
0x1800be6ba  push    rbp
0x1800be6bb  push    rdi
0x1800be6bc  push    r14
0x1800be6be  mov     rbp, rsp
0x1800be6c1  sub     rsp, 40h
0x1800be6c5  mov     r14, rdx
0x1800be6c8  mov     qword ptr [r9], 0
0x1800be6cf  mov     rcx, r14; punk
0x1800be6d2  mov     [rbp+ppidl], 0
0x1800be6da  lea     rdx, [rbp+ppidl]; ppidl
0x1800be6de  mov     rdi, r9
0x1800be6e1  mov     rsi, r8
0x1800be6e4  call    cs:__imp_SHGetIDListFromObject
0x1800be6ea  mov     ebx, eax
0x1800be6ec  test    eax, eax
0x1800be6ee  js      loc_1800BE7A6
0x1800be6f4  mov     rax, [r14]
0x1800be6f7  lea     rcx, [rbp+var_8]
0x1800be6fb  mov     [rsp+40h+var_20], rcx
0x1800be700  lea     r9, _GUID_711b2cfd_93d1_422b_bdf4_69be923f2449
0x1800be707  lea     r8, BHID_SFObject
0x1800be70e  mov     [rbp+var_8], 0
0x1800be716  xor     edx, edx
0x1800be718  mov     rcx, r14
0x1800be71b  mov     rax, [rax+18h]
0x1800be71f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be724  mov     rcx, [rbp+ppidl]; struct _ITEMIDLIST_ABSOLUTE *
0x1800be728  test    eax, eax
0x1800be72a  js      short loc_1800BE773
0x1800be72c  lea     r8, [rbp+pidl]; struct _ITEMIDLIST_ABSOLUTE **
0x1800be730  mov     [rbp+pidl], 0
0x1800be738  xor     edx, edx; int
0x1800be73a  call    ?GetNonFilteredRoot@@YAJPEBU_ITEMIDLIST_ABSOLUTE@@HPEAPEAU1@@Z; GetNonFilteredRoot(_ITEMIDLIST_ABSOLUTE const *,int,_ITEMIDLIST_ABSOLUTE * *)
0x1800be73f  mov     ebx, eax
0x1800be741  test    eax, eax
0x1800be743  js      short loc_1800BE761
0x1800be745  mov     rcx, [rbp+pidl]; pidl
0x1800be749  mov     r8, rdi; ppv
0x1800be74c  mov     rdx, rsi; riid
0x1800be74f  call    cs:__imp_SHCreateItemFromIDList
0x1800be755  mov     rcx, [rbp+pidl]; pidl
0x1800be759  mov     ebx, eax
0x1800be75b  call    cs:__imp_ILFree
0x1800be761  mov     rcx, [rbp+var_8]
0x1800be765  mov     rax, [rcx]
0x1800be768  mov     rax, [rax+10h]
0x1800be76c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800be771  jmp     short loc_1800BE79C
0x1800be773  mov     edx, 0BEEF0010h
0x1800be778  call    ILRemoveHiddenID
0x1800be77d  test    eax, eax
0x1800be77f  jz      short loc_1800BE78A
0x1800be781  mov     rcx, [rbp+ppidl]
0x1800be785  call    ILExpungeRemovedHiddenIDs
0x1800be78a  mov     rcx, [rbp+ppidl]; pidl
0x1800be78e  mov     r8, rdi; ppv
0x1800be791  mov     rdx, rsi; riid
0x1800be794  call    cs:__imp_SHCreateItemFromIDList
0x1800be79a  mov     ebx, eax
0x1800be79c  mov     rcx, [rbp+ppidl]; pidl
0x1800be7a0  call    cs:__imp_ILFree
0x1800be7a6  mov     rsi, [rsp+40h+arg_8]
0x1800be7ab  mov     eax, ebx
0x1800be7ad  mov     rbx, [rsp+40h+arg_0]
0x1800be7b2  add     rsp, 40h
0x1800be7b6  pop     r14
0x1800be7b8  pop     rdi
0x1800be7b9  pop     rbp
0x1800be7ba  retn
```
