# CSearchHomeFolder::_SetScopeAndSubQueries(IShellItem *,IFolderWithSearchRoot *)

- ea: `0x180026470`
- end: `0x180026564`
- name: `?_SetScopeAndSubQueries@CSearchHomeFolder@@AEAAJPEAUIShellItem@@PEAUIFolderWithSearchRoot@@@Z`
- size: `244`
- prototype: `int(CSearchHomeFolder *__hidden this, struct IShellItem *, struct IFolderWithSearchRoot *)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180025da0`

## callees

- `0x180025fac`
- `0x180026470`
- `0x180051010`

## import_xrefs

- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x1800264e9`
- `SHELL32!SHCreateShellItemArrayFromShellItem` at `0x1800264e9`
- `SHELL32!SHGetIDListFromObject` at `0x18002650a`
- `SHELL32!SHGetIDListFromObject` at `0x18002650a`
- `SHELL32!__imp_ILFree` at `0x180026553`
- `SHELL32!__imp_ILFree` at `0x180026553`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeFromIDListsEx` at `0x180026543`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateScopeFromIDListsEx` at `0x180026543`

## pseudocode

```c
__int64 __fastcall CSearchHomeFolder::_SetScopeAndSubQueries(
        CSearchHomeFolder *this,
        struct IShellItem *a2,
        struct IFolderWithSearchRoot *a3)
{
  void **v3; // rsi
  char *v4; // rbp
  HRESULT v6; // ebx
  LPITEMIDLIST ppidl; // [rsp+80h] [rbp+18h] BYREF

  v3 = (void **)((char *)this + 104);
  v4 = (char *)this + 112;
  if ( !a3
    || (v6 = 0,
        (*(int (__fastcall **)(struct IFolderWithSearchRoot *, __int64, _QWORD, char *, char *))(*(_QWORD *)a3 + 24LL))(
          a3,
          2,
          0,
          (char *)this + 112,
          (char *)this + 104) < 0) )
  {
    LODWORD(ppidl) = 0;
    if ( (int)IsAutoList(a2, (IBindCtx *)a2, (int *)&ppidl) >= 0 && (_DWORD)ppidl )
    {
      return (unsigned int)SHCreateShellItemArrayFromShellItem(a2, &GUID_b63ea76d_1f85_456f_a19c_48159efa858b, v3);
    }
    else
    {
      ppidl = 0;
      v6 = SHGetIDListFromObject((IUnknown *)a2, &ppidl);
      if ( v6 >= 0 )
      {
        v6 = SHCreateScopeFromIDListsEx(1, &ppidl, 1, 2, 0, &GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798, v4);
        ILFree(ppidl);
      }
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x180026470  push    rbx
0x180026472  push    rbp
0x180026473  push    rsi
0x180026474  push    rdi
0x180026475  sub     rsp, 48h
0x180026479  lea     rsi, [rcx+68h]
0x18002647d  mov     r10, r8
0x180026480  lea     rbp, [rcx+70h]
0x180026484  mov     rdi, rdx
0x180026487  test    r8, r8
0x18002648a  jz      short loc_1800264B3
0x18002648c  mov     rax, [r8]
0x18002648f  xor     ebx, ebx
0x180026491  mov     r9, rbp
0x180026494  mov     [rsp+68h+var_48], rsi
0x180026499  xor     r8d, r8d
0x18002649c  mov     rcx, r10
0x18002649f  mov     rax, [rax+18h]
0x1800264a3  lea     edx, [rbx+2]
0x1800264a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264ab  test    eax, eax
0x1800264ad  jns     loc_180026559
0x1800264b3  lea     r8, [rsp+68h+ppidl]; int *
0x1800264bb  mov     dword ptr [rsp+68h+ppidl], 0
0x1800264c6  mov     rcx, rdi; struct IShellItem *
0x1800264c9  call    ?IsAutoList@@YAJPEAUIShellItem@@PEAUICompositionProcessor@@PEAH@Z; IsAutoList(IShellItem *,ICompositionProcessor *,int *)
0x1800264ce  test    eax, eax
0x1800264d0  js      short loc_1800264F3
0x1800264d2  cmp     dword ptr [rsp+68h+ppidl], 0
0x1800264da  jz      short loc_1800264F3
0x1800264dc  mov     r8, rsi; ppv
0x1800264df  lea     rdx, _GUID_b63ea76d_1f85_456f_a19c_48159efa858b; riid
0x1800264e6  mov     rcx, rdi; psi
0x1800264e9  call    cs:__imp_SHCreateShellItemArrayFromShellItem
0x1800264ef  mov     ebx, eax
0x1800264f1  jmp     short loc_180026559
0x1800264f3  lea     rdx, [rsp+68h+ppidl]; ppidl
0x1800264fb  mov     [rsp+68h+ppidl], 0
0x180026507  mov     rcx, rdi; punk
0x18002650a  call    cs:__imp_SHGetIDListFromObject
0x180026510  mov     ebx, eax
0x180026512  test    eax, eax
0x180026514  js      short loc_180026559
0x180026516  mov     ecx, 1
0x18002651b  mov     [rsp+68h+var_38], rbp
0x180026520  lea     rax, _GUID_655d1685_2bfd_4f7f_ad22_5ab61c8d8798
0x180026527  mov     r8d, ecx
0x18002652a  mov     [rsp+68h+var_40], rax
0x18002652f  lea     rdx, [rsp+68h+ppidl]
0x180026537  mov     dword ptr [rsp+68h+var_48], 0
0x18002653f  lea     r9d, [rcx+1]
0x180026543  call    cs:__imp_SHCreateScopeFromIDListsEx
0x180026549  mov     rcx, [rsp+68h+ppidl]; pidl
0x180026551  mov     ebx, eax
0x180026553  call    cs:__imp_ILFree
0x180026559  mov     eax, ebx
0x18002655b  add     rsp, 48h
0x18002655f  pop     rdi
0x180026560  pop     rsi
0x180026561  pop     rbp
0x180026562  pop     rbx
0x180026563  retn
```
