# CSyncFolderBase::_ExecuteAction(SYNCMGR_HANDLERACTIONS,SYNCMGR_IDENTIFIER const &,_ITEMID_CHILD const *,HWND__ *,IDataObject *,IPrivSyncMgrSynchronizeInvoke *)

- ea: `0x180042fa4`
- end: `0x180043062`
- name: `?_ExecuteAction@CSyncFolderBase@@AEAAJW4SYNCMGR_HANDLERACTIONS@@AEBUSYNCMGR_IDENTIFIER@@PEFBU_ITEMID_CHILD@@PEAUHWND__@@PEAUIDataObject@@PEAUIPrivSyncMgrSynchronizeInvoke@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(__int64, unsigned int, __int64, const ITEMIDLIST *, HWND, struct IDataObject *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180043068`

## callees

- `0x180042bbc`
- `0x180042fa4`
- `0x180053010`

## import_xrefs

- `SHELL32!__imp_ILClone` at `0x180042fc9`
- `SHELL32!__imp_ILClone` at `0x180042fc9`
- `SHELL32!__imp_ILCombine` at `0x180042fd4`
- `SHELL32!__imp_ILCombine` at `0x180042fd4`
- `SHELL32!__imp_ILFree` at `0x180043009`
- `SHELL32!__imp_ILFree` at `0x180043009`
- `USER32!DestroyWindow` at `0x180043044`
- `USER32!DestroyWindow` at `0x180043044`

## pseudocode

```c
__int64 __fastcall CSyncFolderBase::_ExecuteAction(
        __int64 a1,
        unsigned int a2,
        __int64 a3,
        const ITEMIDLIST *a4,
        HWND a5,
        struct IDataObject *a6,
        __int64 a7)
{
  const ITEMIDLIST *v7; // rcx
  int UniqueStubWindow; // ebx
  struct _ITEMIDLIST_ABSOLUTE *v11; // rax
  CSyncFolderBase *v12; // rcx
  ITEMIDLIST *v13; // rdi
  HWND hWnd; // [rsp+78h] [rbp+20h] BYREF

  v7 = *(const ITEMIDLIST **)(a1 + 80);
  hWnd = 0;
  UniqueStubWindow = -2147024882;
  if ( a4 )
    v11 = (struct _ITEMIDLIST_ABSOLUTE *)ILCombine(v7, a4);
  else
    v11 = (struct _ITEMIDLIST_ABSOLUTE *)ILClone(v7);
  v13 = (ITEMIDLIST *)v11;
  if ( !v11
    || (UniqueStubWindow = CSyncFolderBase::GetUniqueStubWindow(v12, v11, a5, a6, &hWnd), ILFree(v13), UniqueStubWindow) )
  {
    if ( UniqueStubWindow == -2147467260 )
      return 0;
  }
  else
  {
    UniqueStubWindow = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, HWND, int))(*(_QWORD *)a7 + 72LL))(
                         a7,
                         a2,
                         a3,
                         hWnd,
                         1);
    if ( UniqueStubWindow < 0 )
      DestroyWindow(hWnd);
  }
  return (unsigned int)UniqueStubWindow;
}

```

## disassembly

```asm
0x180042fa4  push    rbx
0x180042fa6  push    rbp
0x180042fa7  push    rsi
0x180042fa8  push    rdi
0x180042fa9  sub     rsp, 38h
0x180042fad  mov     rcx, [rcx+50h]; pidl1
0x180042fb1  mov     rsi, r8
0x180042fb4  mov     [rsp+58h+hWnd], 0
0x180042fbd  mov     ebp, edx
0x180042fbf  mov     ebx, 8007000Eh
0x180042fc4  test    r9, r9
0x180042fc7  jnz     short loc_180042FD1
0x180042fc9  call    cs:__imp_ILClone
0x180042fcf  jmp     short loc_180042FDA
0x180042fd1  mov     rdx, r9; pidl2
0x180042fd4  call    cs:__imp_ILCombine
0x180042fda  mov     rdi, rax
0x180042fdd  test    rax, rax
0x180042fe0  jz      short loc_18004304C
0x180042fe2  mov     r9, [rsp+58h+arg_28]; struct IDataObject *
0x180042fea  lea     rax, [rsp+58h+hWnd]
0x180042fef  mov     r8, [rsp+58h+arg_20]; HWND
0x180042ff7  mov     rdx, rdi; struct _ITEMIDLIST_ABSOLUTE *
0x180042ffa  mov     [rsp+58h+var_38], rax; HWND *
0x180042fff  call    ?GetUniqueStubWindow@CSyncFolderBase@@IEBAJPEAU_ITEMIDLIST_ABSOLUTE@@PEAUHWND__@@PEAUIDataObject@@PEAPEAU3@@Z; CSyncFolderBase::GetUniqueStubWindow(_ITEMIDLIST_ABSOLUTE *,HWND__ *,IDataObject *,HWND__ * *)
0x180043004  mov     rcx, rdi; pidl
0x180043007  mov     ebx, eax
0x180043009  call    cs:__imp_ILFree
0x18004300f  test    ebx, ebx
0x180043011  jnz     short loc_18004304C
0x180043013  mov     rcx, [rsp+58h+arg_30]
0x18004301b  mov     r8, rsi
0x18004301e  mov     r9, [rsp+58h+hWnd]
0x180043023  mov     edx, ebp
0x180043025  mov     dword ptr [rsp+58h+var_38], 1
0x18004302d  mov     rax, [rcx]
0x180043030  mov     rax, [rax+48h]
0x180043034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043039  mov     ebx, eax
0x18004303b  test    eax, eax
0x18004303d  jns     short loc_180043057
0x18004303f  mov     rcx, [rsp+58h+hWnd]; hWnd
0x180043044  call    cs:__imp_DestroyWindow
0x18004304a  jmp     short loc_180043057
0x18004304c  xor     eax, eax
0x18004304e  cmp     ebx, 80004004h
0x180043054  cmovz   ebx, eax
0x180043057  mov     eax, ebx
0x180043059  add     rsp, 38h
0x18004305d  pop     rdi
0x18004305e  pop     rsi
0x18004305f  pop     rbp
0x180043060  pop     rbx
0x180043061  retn
```
