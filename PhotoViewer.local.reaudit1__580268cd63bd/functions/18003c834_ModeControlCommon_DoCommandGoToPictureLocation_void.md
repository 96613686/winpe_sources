# ModeControlCommon::DoCommandGoToPictureLocation(void)

- ea: `0x18003c834`
- end: `0x18003c8f1`
- name: `?DoCommandGoToPictureLocation@ModeControlCommon@@AEAAXXZ`
- size: `189`
- prototype: `void __fastcall(ModeControlCommon *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x180027efc`

## callees

- `0x18000cb74`
- `0x18003c834`
- `0x18003c9c4`
- `0x180080010`

## import_xrefs

- `ole32!CoTaskMemFree` at `0x18003c8ca`
- `ole32!CoTaskMemFree` at `0x18003c8ca`
- `SHELL32!SHGetIDListFromObject` at `0x18003c894`
- `SHELL32!SHGetIDListFromObject` at `0x18003c894`
- `SHELL32!SHOpenFolderAndSelectItems` at `0x18003c8b3`
- `SHELL32!SHOpenFolderAndSelectItems` at `0x18003c8b3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c858`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c87d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c8a0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c8bf`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c858`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c87d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c8a0`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003c8bf`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
void __fastcall ModeControlCommon::DoCommandGoToPictureLocation(ModeControlCommon *this)
{
  int v1; // edx
  int v2; // eax
  int v3; // edx
  HRESULT v4; // eax
  int v5; // edx
  HRESULT v6; // eax
  int v7; // edx
  LPITEMIDLIST ppidl; // [rsp+38h] [rbp+18h] BYREF
  IUnknown *punk; // [rsp+40h] [rbp+20h] BYREF
  __int64 v10; // [rsp+48h] [rbp+28h] BYREF

  ATL::CComQIPtr<IEaselControl,&__s_GUID const _GUID_9ec7fdc9_f499_4b8f_8ee0_1935d1e82ff8>::CComQIPtr<IEaselControl,&__s_GUID const _GUID_9ec7fdc9_f499_4b8f_8ee0_1935d1e82ff8>(
    &v10,
    this);
  if ( !v10 )
  {
    Base::Throw((Base *)0x80004005LL, v1);
    __debugbreak();
  }
  punk = 0;
  v2 = (*(__int64 (__fastcall **)(__int64, IUnknown **))(*(_QWORD *)v10 + 72LL))(v10, &punk);
  if ( v2 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v2, v3);
    __debugbreak();
  }
  ppidl = 0;
  v4 = SHGetIDListFromObject(punk, &ppidl);
  if ( v4 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v4, v5);
    __debugbreak();
  }
  v6 = SHOpenFolderAndSelectItems(ppidl, 0, 0, 0);
  if ( v6 < 0 )
    Base::Throw((Base *)(unsigned int)v6, v7);
  CoTaskMemFree(ppidl);
  ppidl = 0;
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&punk);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v10);
}

```

## disassembly

```asm
0x18003c834  push    rbp
0x18003c836  mov     rbp, rsp
0x18003c839  sub     rsp, 20h
0x18003c83d  mov     rdx, rcx
0x18003c840  lea     rcx, [rbp+arg_18]
0x18003c844  call    ??0?$CComQIPtr@VIEaselControl@@$1?_GUID_9ec7fdc9_f499_4b8f_8ee0_1935d1e82ff8@@3U__s_GUID@@B@ATL@@QEAA@PEAUIUnknown@@@Z; ATL::CComQIPtr<IEaselControl,&__s_GUID const _GUID_9ec7fdc9_f499_4b8f_8ee0_1935d1e82ff8>::CComQIPtr<IEaselControl,&__s_GUID const _GUID_9ec7fdc9_f499_4b8f_8ee0_1935d1e82ff8>(IUnknown *)
0x18003c849  nop
0x18003c84a  mov     rcx, [rbp+arg_18]
0x18003c84e  test    rcx, rcx
0x18003c851  jnz     short loc_18003C85F
0x18003c853  mov     ecx, 80004005h
0x18003c858  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003c85e  int     3; Trap to Debugger
0x18003c85f  mov     [rbp+punk], 0
0x18003c867  mov     rax, [rcx]
0x18003c86a  lea     rdx, [rbp+punk]
0x18003c86e  mov     rax, [rax+48h]
0x18003c872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c877  test    eax, eax
0x18003c879  jns     short loc_18003C884
0x18003c87b  mov     ecx, eax
0x18003c87d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003c883  int     3; Trap to Debugger
0x18003c884  mov     [rbp+ppidl], 0
0x18003c88c  lea     rdx, [rbp+ppidl]; ppidl
0x18003c890  mov     rcx, [rbp+punk]; punk
0x18003c894  call    cs:__imp_SHGetIDListFromObject
0x18003c89a  test    eax, eax
0x18003c89c  jns     short loc_18003C8A7
0x18003c89e  mov     ecx, eax
0x18003c8a0  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003c8a6  int     3; Trap to Debugger
0x18003c8a7  xor     r9d, r9d; dwFlags
0x18003c8aa  xor     r8d, r8d; apidl
0x18003c8ad  xor     edx, edx; cidl
0x18003c8af  mov     rcx, [rbp+ppidl]; pidlFolder
0x18003c8b3  call    cs:__imp_SHOpenFolderAndSelectItems
0x18003c8b9  test    eax, eax
0x18003c8bb  jns     short loc_18003C8C6
0x18003c8bd  mov     ecx, eax
0x18003c8bf  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003c8c5  nop
0x18003c8c6  mov     rcx, [rbp+ppidl]; pv
0x18003c8ca  call    cs:__imp_CoTaskMemFree
0x18003c8d0  mov     [rbp+ppidl], 0
0x18003c8d8  lea     rcx, [rbp+punk]
0x18003c8dc  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003c8e1  nop
0x18003c8e2  lea     rcx, [rbp+arg_18]
0x18003c8e6  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003c8eb  add     rsp, 20h
0x18003c8ef  pop     rbp
0x18003c8f0  retn
```
