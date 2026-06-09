# CConflictFolder::_LaunchResolveConflict(tagPOINT,ISyncMgrConflict *,_ITEMIDLIST_ABSOLUTE *,ISyncMgrConflictResolveInfo *)

- ea: `0x1800374c4`
- end: `0x1800375ca`
- name: `?_LaunchResolveConflict@CConflictFolder@@AEAAJUtagPOINT@@PEAUISyncMgrConflict@@PEAU_ITEMIDLIST_ABSOLUTE@@PEAUISyncMgrConflictResolveInfo@@@Z`
- size: `262`
- prototype: `__int64 __fastcall(CConflictFolder *this, struct tagPOINT, struct ISyncMgrConflict *, const ITEMIDLIST *, struct ISyncMgrConflictResolveInfo *)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x180037a20`

## callees

- `0x18000b310`
- `0x1800133b0`
- `0x1800134dc`
- `0x180013678`
- `0x180034b28`
- `0x1800374c4`
- `0x180048520`
- `0x180048848`
- `0x180048ff4`
- `0x180053010`

## import_xrefs

- `SHELL32!SHCreateItemFromIDList` at `0x18003757f`
- `SHELL32!SHCreateItemFromIDList` at `0x18003757f`
- `USER32!DestroyWindow` at `0x1800375ae`
- `USER32!DestroyWindow` at `0x1800375ae`

## pseudocode

```c
__int64 __fastcall CConflictFolder::_LaunchResolveConflict(
        CConflictFolder *this,
        struct tagPOINT a2,
        struct ISyncMgrConflict *a3,
        const ITEMIDLIST *a4,
        struct ISyncMgrConflictResolveInfo *a5)
{
  int v6; // ebx
  struct ISyncMgrConflictResolveInfo *v8; // rsi
  struct ISyncMgrConflictResolveInfo v9; // rax
  int v10; // eax
  void **v11; // rax
  struct IShellItem *v12; // rax
  int v14; // [rsp+30h] [rbp-10h] BYREF
  HWND hWnd; // [rsp+38h] [rbp-8h] BYREF
  CConflictFolder *v16; // [rsp+60h] [rbp+20h] BYREF

  v16 = this;
  v6 = 0;
  hWnd = 0;
  if ( Stub_EnsureUniqueStubWithParent((HWND)this, (const struct _ITEMIDLIST_ABSOLUTE *)a4, (int)a3, a2, &hWnd) )
  {
    v8 = a5;
    ((void (__fastcall *)(struct ISyncMgrConflictResolveInfo *, _QWORD))a5->lpVtbl->SetPresenterNextStep)(a5, 0);
    v9.lpVtbl = v8->lpVtbl;
    v14 = 0;
    LODWORD(v16) = 0;
    v6 = ((__int64 (__fastcall *)(struct ISyncMgrConflictResolveInfo *, int *, CConflictFolder **))v9.lpVtbl->GetPresenterChoice)(
           v8,
           &v14,
           &v16);
    if ( v6 < 0
      || (!(_DWORD)v16 ? (v10 = ResolveConflictWithUI(hWnd, a3, v8)) : (v10 = AutoResolveConflict(hWnd, a3, v8)),
          v6 = v10,
          v10 < 0) )
    {
      ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(&v16);
      v11 = (void **)ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(&v16);
      SHCreateItemFromIDList(a4, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v11);
      v12 = (struct IShellItem *)ATL::CComPtrBase<ISyncMgrConflictResolveInfo>::operator->((__int64)&v16);
      v6 = ConfirmConflictShellItemMissing(hWnd, v6, v12, v8);
      ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>((__int64)&v16);
    }
    DestroyWindow(hWnd);
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x1800374c4  mov     r11, rsp
0x1800374c7  mov     [r11+10h], rbx
0x1800374cb  mov     [r11+18h], rsi
0x1800374cf  mov     [r11+8], rcx
0x1800374d3  push    rbp
0x1800374d4  push    r14
0x1800374d6  push    r15
0x1800374d8  mov     rbp, rsp
0x1800374db  sub     rsp, 40h
0x1800374df  mov     r15, r9
0x1800374e2  lea     rax, [rbp+hWnd]
0x1800374e6  mov     r9, rdx; struct tagPOINT
0x1800374e9  mov     [r11-38h], rax
0x1800374ed  xor     ebx, ebx
0x1800374ef  mov     rdx, r15; struct _ITEMIDLIST_ABSOLUTE *
0x1800374f2  mov     r14, r8
0x1800374f5  mov     [rbp+hWnd], rbx
0x1800374f9  call    ?Stub_EnsureUniqueStubWithParent@@YAHPEAUHWND__@@PEBU_ITEMIDLIST_ABSOLUTE@@HUtagPOINT@@PEAPEAU1@@Z; Stub_EnsureUniqueStubWithParent(HWND__ *,_ITEMIDLIST_ABSOLUTE const *,int,tagPOINT,HWND__ * *)
0x1800374fe  test    eax, eax
0x180037500  jz      loc_1800375B4
0x180037506  mov     rsi, [rbp+arg_20]
0x18003750a  xor     edx, edx
0x18003750c  mov     rcx, rsi
0x18003750f  mov     rax, [rsi]
0x180037512  mov     rax, [rax+40h]
0x180037516  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003751b  mov     rax, [rsi]
0x18003751e  lea     r8, [rbp+arg_0]
0x180037522  lea     rdx, [rbp+var_10]
0x180037526  mov     [rbp+var_10], ebx
0x180037529  mov     rcx, rsi
0x18003752c  mov     dword ptr [rbp+arg_0], ebx
0x18003752f  mov     rax, [rax+28h]
0x180037533  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180037538  mov     ebx, eax
0x18003753a  test    eax, eax
0x18003753c  js      short loc_180037560
0x18003753e  cmp     dword ptr [rbp+arg_0], 0
0x180037542  mov     r8, rsi; struct ISyncMgrConflictResolveInfo *
0x180037545  mov     rcx, [rbp+hWnd]; HWND
0x180037549  mov     rdx, r14; struct ISyncMgrConflict *
0x18003754c  jz      short loc_180037555
0x18003754e  call    _AutoResolveConflict
0x180037553  jmp     short loc_18003755A
0x180037555  call    _ResolveConflictWithUI
0x18003755a  mov     ebx, eax
0x18003755c  test    eax, eax
0x18003755e  jns     short loc_1800375AA
0x180037560  lea     rcx, [rbp+arg_0]; void *
0x180037564  call    ??0?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::CComPtr<IDefaultExtractIconInit>(void)
0x180037569  lea     rcx, [rbp+arg_0]; void *
0x18003756d  call    ??I?$CComPtrBase@UISyncClientFolderItemCache@@@ATL@@QEAAPEAPEAUISyncClientFolderItemCache@@XZ; ATL::CComPtrBase<ISyncClientFolderItemCache>::operator&(void)
0x180037572  mov     r8, rax; ppv
0x180037575  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18003757c  mov     rcx, r15; pidl
0x18003757f  call    cs:__imp_SHCreateItemFromIDList
0x180037585  lea     rcx, [rbp+arg_0]
0x180037589  call    ??C?$CComPtrBase@UISyncMgrConflictResolveInfo@@@ATL@@QEBAPEAV?$_NoAddRefReleaseOnCComPtr@UISyncMgrConflictResolveInfo@@@1@XZ; ATL::CComPtrBase<ISyncMgrConflictResolveInfo>::operator->(void)
0x18003758e  mov     rcx, [rbp+hWnd]; HWND
0x180037592  mov     r8, rax; struct IShellItem *
0x180037595  mov     r9, rsi; struct ISyncMgrConflictResolveInfo *
0x180037598  mov     edx, ebx; int
0x18003759a  call    ?ConfirmConflictShellItemMissing@@YAJPEAUHWND__@@JPEAUIShellItem@@PEAUISyncMgrConflictResolveInfo@@@Z; ConfirmConflictShellItemMissing(HWND__ *,long,IShellItem *,ISyncMgrConflictResolveInfo *)
0x18003759f  lea     rcx, [rbp+arg_0]
0x1800375a3  mov     ebx, eax
0x1800375a5  call    ??1?$CComPtr@UIDefaultExtractIconInit@@@ATL@@QEAA@XZ; ATL::CComPtr<IDefaultExtractIconInit>::~CComPtr<IDefaultExtractIconInit>(void)
0x1800375aa  mov     rcx, [rbp+hWnd]; hWnd
0x1800375ae  call    cs:__imp_DestroyWindow
0x1800375b4  mov     rsi, [rsp+40h+arg_10]
0x1800375b9  mov     eax, ebx
0x1800375bb  mov     rbx, [rsp+40h+arg_8]
0x1800375c0  add     rsp, 40h
0x1800375c4  pop     r15
0x1800375c6  pop     r14
0x1800375c8  pop     rbp
0x1800375c9  retn
```
