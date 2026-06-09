# CDBFolderBgMenuCB::_CreateNewAutoListForSave(IShellFolder3 *,_GUID const &,void * *)

- ea: `0x18001ef00`
- end: `0x18001f024`
- name: `?_CreateNewAutoListForSave@CDBFolderBgMenuCB@@AEAAJPEAUIShellFolder3@@AEBU_GUID@@PEAPEAX@Z`
- size: `292`
- prototype: `__int64 __fastcall(IUnknown **this, struct IUnknown *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callers

- `0x180020cf4`

## callees

- `0x180006900`
- `0x1800076dc`
- `0x180011f3c`
- `0x180013638`
- `0x18001ef00`
- `0x18001f310`
- `0x18003e5d0`
- `0x180051010`

## import_xrefs

- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18001ef51`
- `api-ms-win-shcore-comhelpers-l1-1-0!IUnknown_QueryService` at `0x18001ef51`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001efe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eff1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001efe7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001eff1`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x18001efd1`
- `api-ms-win-winrt-search-folder-l1-1-0!SHCreateAutoList` at `0x18001efd1`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
__int64 __fastcall CDBFolderBgMenuCB::_CreateNewAutoListForSave(
        IUnknown **this,
        struct IUnknown *a2,
        const struct _GUID *a3,
        void **a4)
{
  HRESULT AutoListInitFromFolderAndView; // ebx
  const struct _GUID *v8; // r8
  void *ppvOut; // [rsp+30h] [rbp-D0h] BYREF
  GUID v11; // [rsp+40h] [rbp-C0h]
  _BYTE v12[88]; // [rsp+50h] [rbp-B0h] BYREF
  LPVOID pv; // [rsp+A8h] [rbp-58h]
  LPVOID v14; // [rsp+B8h] [rbp-48h]
  void *v15[4]; // [rsp+E0h] [rbp-20h] BYREF

  *a4 = 0;
  ppvOut = 0;
  AutoListInitFromFolderAndView = IUnknown_QueryService(
                                    this[2],
                                    &IID_IFolderView,
                                    &GUID_1af3a467_214f_4298_908e_06b03e0b39f9,
                                    &ppvOut);
  if ( AutoListInitFromFolderAndView >= 0 )
  {
    memset_0(v12, 0, 0xB0u);
    v11 = FOLDERTYPEID_GenericSearchResults;
    AutoListInitFromFolderAndView = GetAutoListInitFromFolderAndView(
                                      a2,
                                      (struct IFolderView2 *)ppvOut,
                                      (struct AUTOLISTINIT *)v12);
    if ( AutoListInitFromFolderAndView >= 0 )
    {
      SafeRelease<IShellItemArray>((__int64 *)v15);
      AutoListInitFromFolderAndView = CDBFolderBgMenuCB::_GetConditionsForNewAutoList(
                                        (CDBFolderBgMenuCB *)this,
                                        (struct IShellFolder3 *)a2,
                                        v8,
                                        v15);
      if ( AutoListInitFromFolderAndView >= 0 )
        AutoListInitFromFolderAndView = SHCreateAutoList(v12, 0, &GUID_607c87f7_0696_4558_a368_de5e59cfe456, a4);
      ClearAutoListInit((struct AUTOLISTINIT *)v12);
      CoTaskMemFree(pv);
      CoTaskMemFree(v14);
    }
    (*(void (__fastcall **)(void *))(*(_QWORD *)ppvOut + 16LL))(ppvOut);
  }
  return (unsigned int)AutoListInitFromFolderAndView;
}

```

## disassembly

```asm
0x18001ef00  push    rbp
0x18001ef02  push    rbx
0x18001ef03  push    rsi
0x18001ef04  push    rdi
0x18001ef05  push    r14
0x18001ef07  lea     rbp, [rsp-10h]
0x18001ef0c  sub     rsp, 110h
0x18001ef13  mov     rax, cs:__security_cookie
0x18001ef1a  xor     rax, rsp
0x18001ef1d  mov     [rbp+30h+var_30], rax
0x18001ef21  mov     qword ptr [r9], 0
0x18001ef28  lea     r8, _GUID_1af3a467_214f_4298_908e_06b03e0b39f9; riid
0x18001ef2f  mov     rsi, r9
0x18001ef32  mov     [rsp+130h+ppvOut], 0
0x18001ef3b  mov     rdi, rdx
0x18001ef3e  lea     r9, [rsp+130h+ppvOut]; ppvOut
0x18001ef43  mov     r14, rcx
0x18001ef46  lea     rdx, IID_IFolderView; guidService
0x18001ef4d  mov     rcx, [rcx+10h]; punk
0x18001ef51  call    cs:__imp_IUnknown_QueryService
0x18001ef57  mov     ebx, eax
0x18001ef59  test    eax, eax
0x18001ef5b  js      loc_18001F008
0x18001ef61  xor     edx, edx; Val
0x18001ef63  lea     rcx, [rsp+130h+var_E0]; void *
0x18001ef68  mov     r8d, 0B0h; Size
0x18001ef6e  call    memset_0
0x18001ef73  movups  xmm0, xmmword ptr cs:FOLDERTYPEID_GenericSearchResults.Data1
0x18001ef7a  mov     rdx, [rsp+130h+ppvOut]; struct IFolderView2 *
0x18001ef7f  lea     rax, [rsp+130h+var_E0]
0x18001ef84  lea     r8, [rsp+130h+var_F0]
0x18001ef89  mov     [rsp+130h+var_110], rax; struct AUTOLISTINIT *
0x18001ef8e  mov     rcx, rdi; struct IUnknown *
0x18001ef91  movdqu  [rsp+130h+var_F0], xmm0
0x18001ef97  call    GetAutoListInitFromFolderAndView
0x18001ef9c  mov     ebx, eax
0x18001ef9e  test    eax, eax
0x18001efa0  js      short loc_18001EFF7
0x18001efa2  lea     rcx, [rbp+30h+var_50]
0x18001efa6  call    ??$SafeRelease@UIShellItemArray@@@@YAXPEAPEAUIShellItemArray@@@Z; SafeRelease<IShellItemArray>(IShellItemArray * *)
0x18001efab  lea     r9, [rbp+30h+var_50]; void **
0x18001efaf  mov     rdx, rdi; struct IShellFolder3 *
0x18001efb2  mov     rcx, r14; this
0x18001efb5  call    ?_GetConditionsForNewAutoList@CDBFolderBgMenuCB@@AEAAJPEAUIShellFolder3@@AEBU_GUID@@PEAPEAX@Z; CDBFolderBgMenuCB::_GetConditionsForNewAutoList(IShellFolder3 *,_GUID const &,void * *)
0x18001efba  mov     ebx, eax
0x18001efbc  test    eax, eax
0x18001efbe  js      short loc_18001EFD9
0x18001efc0  mov     r9, rsi
0x18001efc3  lea     r8, _GUID_607c87f7_0696_4558_a368_de5e59cfe456
0x18001efca  xor     edx, edx
0x18001efcc  lea     rcx, [rsp+130h+var_E0]
0x18001efd1  call    cs:__imp_SHCreateAutoList
0x18001efd7  mov     ebx, eax
0x18001efd9  lea     rcx, [rsp+130h+var_E0]; struct AUTOLISTINIT *
0x18001efde  call    ?ClearAutoListInit@@YAXPEAUAUTOLISTINIT@@@Z; ClearAutoListInit(AUTOLISTINIT *)
0x18001efe3  mov     rcx, [rbp+30h+pv]; pv
0x18001efe7  call    cs:__imp_CoTaskMemFree
0x18001efed  mov     rcx, [rbp+30h+var_78]; pv
0x18001eff1  call    cs:__imp_CoTaskMemFree
0x18001eff7  mov     rcx, [rsp+130h+ppvOut]
0x18001effc  mov     rax, [rcx]
0x18001efff  mov     rax, [rax+10h]
0x18001f003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f008  mov     eax, ebx
0x18001f00a  mov     rcx, [rbp+30h+var_30]
0x18001f00e  xor     rcx, rsp; StackCookie
0x18001f011  call    __security_check_cookie
0x18001f016  add     rsp, 110h
0x18001f01d  pop     r14
0x18001f01f  pop     rdi
0x18001f020  pop     rsi
0x18001f021  pop     rbx
0x18001f022  pop     rbp
0x18001f023  retn
```
