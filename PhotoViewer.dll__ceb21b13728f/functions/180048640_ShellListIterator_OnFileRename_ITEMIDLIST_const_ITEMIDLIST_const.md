# ShellListIterator::OnFileRename(_ITEMIDLIST const *,_ITEMIDLIST const *)

- ea: `0x180048640`
- end: `0x180048751`
- name: `?OnFileRename@ShellListIterator@@UEAAJPEFBU_ITEMIDLIST@@0@Z`
- size: `273`
- prototype: `int(ShellListIterator *__hidden this, const struct _ITEMIDLIST *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18000cb74`
- `0x180032608`
- `0x18003ed94`
- `0x1800456a0`
- `0x180048640`

## import_xrefs

- `USER32!PostMessageW` at `0x180048715`
- `USER32!PostMessageW` at `0x180048715`
- `SHELL32!SHCreateItemFromIDList` at `0x18004868b`
- `SHELL32!SHCreateItemFromIDList` at `0x1800486b5`
- `SHELL32!SHCreateItemFromIDList` at `0x18004868b`
- `SHELL32!SHCreateItemFromIDList` at `0x1800486b5`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800486ce`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x1800486ce`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004865d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004866d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180048697`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800486c1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004865d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18004866d`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x180048697`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x1800486c1`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ShellListIterator::OnFileRename(
        HWND *this,
        const struct _ITEMIDLIST *a2,
        const struct _ITEMIDLIST *a3)
{
  const ITEMIDLIST *v4; // rax
  HRESULT v6; // eax
  int v7; // edx
  HRESULT v8; // eax
  unsigned __int64 v9; // rdx
  bool v10; // r8
  ShellListIteratorNotification *v11; // rax
  unsigned int v12; // edx
  ShellListIteratorNotification *v14; // [rsp+20h] [rbp-28h] BYREF
  _BYTE v15[32]; // [rsp+28h] [rbp-20h] BYREF
  void *v16; // [rsp+58h] [rbp+10h] BYREF
  void *ppv; // [rsp+68h] [rbp+20h] BYREF

  try
  {
    v4 = a2;
    if ( !a2 )
      Base::Throw((Base *)0x80004003LL, 0);
    if ( !a3 )
      Base::Throw((Base *)0x80004003LL, (_DWORD)a2);
    ppv = 0;
    v6 = SHCreateItemFromIDList(v4, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
    if ( v6 < 0 )
      Base::Throw((Base *)(unsigned int)v6, v7);
    v16 = 0;
    v8 = SHCreateItemFromIDList(a3, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &v16);
    if ( v8 < 0 )
      Base::Throw((Base *)(unsigned int)v8, v9);
    LOBYTE(v9) = 1;
    v11 = (ShellListIteratorNotification *)BasePrivate::New((BasePrivate *)0x18, v9, v10);
    if ( v11 )
      v11 = (ShellListIteratorNotification *)ShellListIteratorNotification::ShellListIteratorNotification(
                                               v11,
                                               2,
                                               ppv,
                                               v16);
    v14 = v11;
    ATL::CAtlList<ATL::CAutoPtr<ShellListIteratorNotification>,ATL::CAutoPtrElementTraits<ShellListIteratorNotification>>::AddTail(
      this + 41,
      &v14);
    PostMessageW(this[2], 0x400u, 0, 0);
    if ( v14 )
      ShellListIteratorNotification::`scalar deleting destructor'(v14, v12);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v16);
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
  }
  catch ( Base::Exception v15 )
  {
    Base::Exception::~Exception((Base::Exception *)v15);
  }
  return 0;
}

```

## disassembly

```asm
0x180048640  mov     [rsp+arg_0], rbx
0x180048645  push    rdi
0x180048646  sub     rsp, 40h
0x18004864a  mov     rbx, r8
0x18004864d  mov     rax, rdx
0x180048650  mov     rdi, rcx
0x180048653  test    rax, rax
0x180048656  jnz     short loc_180048663
0x180048658  mov     ecx, 80004003h
0x18004865d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180048663  test    rbx, rbx
0x180048666  jnz     short loc_180048673
0x180048668  mov     ecx, 80004003h
0x18004866d  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x180048673  mov     [rsp+48h+ppv], 0
0x18004867c  lea     r8, [rsp+48h+ppv]; ppv
0x180048681  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180048688  mov     rcx, rax; pidl
0x18004868b  call    cs:__imp_SHCreateItemFromIDList
0x180048691  test    eax, eax
0x180048693  jns     short loc_18004869D
0x180048695  mov     ecx, eax
0x180048697  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18004869d  mov     [rsp+48h+arg_8], 0
0x1800486a6  lea     r8, [rsp+48h+arg_8]; ppv
0x1800486ab  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x1800486b2  mov     rcx, rbx; pidl
0x1800486b5  call    cs:__imp_SHCreateItemFromIDList
0x1800486bb  test    eax, eax
0x1800486bd  jns     short loc_1800486C7
0x1800486bf  mov     ecx, eax
0x1800486c1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x1800486c7  mov     dl, 1
0x1800486c9  mov     ecx, 18h
0x1800486ce  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x1800486d4  test    rax, rax
0x1800486d7  jz      short loc_1800486F0
0x1800486d9  mov     r9, [rsp+48h+arg_8]
0x1800486de  mov     r8, [rsp+48h+ppv]
0x1800486e3  mov     edx, 2
0x1800486e8  mov     rcx, rax
0x1800486eb  call    ??0ShellListIteratorNotification@@QEAA@W4NotifyCode@0@PEAUIShellItem@@1@Z; ShellListIteratorNotification::ShellListIteratorNotification(ShellListIteratorNotification::NotifyCode,IShellItem *,IShellItem *)
0x1800486f0  mov     [rsp+48h+var_28], rax
0x1800486f5  lea     rcx, [rdi+148h]
0x1800486fc  lea     rdx, [rsp+48h+var_28]
0x180048701  call    ?AddTail@?$CAtlList@V?$CAutoPtr@VShellListIteratorNotification@@@ATL@@V?$CAutoPtrElementTraits@VShellListIteratorNotification@@@2@@ATL@@QEAAPEAU__POSITION@@AEAV?$CAutoPtr@VShellListIteratorNotification@@@2@@Z; ATL::CAtlList<ATL::CAutoPtr<ShellListIteratorNotification>,ATL::CAutoPtrElementTraits<ShellListIteratorNotification>>::AddTail(ATL::CAutoPtr<ShellListIteratorNotification> &)
0x180048706  xor     r9d, r9d; lParam
0x180048709  xor     r8d, r8d; wParam
0x18004870c  mov     edx, 400h; Msg
0x180048711  mov     rcx, [rdi+10h]; hWnd
0x180048715  call    cs:__imp_PostMessageW
0x18004871b  nop
0x18004871c  mov     rcx, [rsp+48h+var_28]; this
0x180048721  test    rcx, rcx
0x180048724  jz      short loc_18004872C
0x180048726  call    ??_GShellListIteratorNotification@@QEAAPEAXI@Z; ShellListIteratorNotification::`scalar deleting destructor'(uint)
0x18004872b  nop
0x18004872c  lea     rcx, [rsp+48h+arg_8]
0x180048731  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180048736  nop
0x180048737  lea     rcx, [rsp+48h+ppv]
0x18004873c  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x180048741  nop
0x180048742  jmp     short $+2
0x180048744  xor     eax, eax
0x180048746  mov     rbx, [rsp+48h+arg_0]
0x18004874b  add     rsp, 40h
0x18004874f  pop     rdi
0x180048750  retn
```
