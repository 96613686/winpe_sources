# ShellListManager::FoundItem(IShellFolder *,_ITEMIDLIST const *)

- ea: `0x18001f1c0`
- end: `0x18001f61f`
- name: `?FoundItem@ShellListManager@@UEAAJPEAUIShellFolder@@PEFBU_ITEMIDLIST@@@Z`
- size: `1119`
- prototype: `int(ShellListManager *__hidden this, struct IShellFolder *, const struct _ITEMIDLIST *)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180006278`
- `0x18000cb74`
- `0x18001f1c0`
- `0x180022924`
- `0x1800286a4`
- `0x180032608`
- `0x18003ed94`
- `0x1800456a0`
- `0x180080010`

## import_xrefs

- `USER32!PostMessageW` at `0x18001f446`
- `USER32!PostMessageW` at `0x18001f446`
- `ole32!CoTaskMemFree` at `0x18001f24f`
- `ole32!CoTaskMemFree` at `0x18001f3ba`
- `ole32!CoTaskMemFree` at `0x18001f4a2`
- `ole32!CoTaskMemFree` at `0x18001f4f3`
- `ole32!CoTaskMemFree` at `0x18001f5f0`
- `ole32!CoTaskMemFree` at `0x18001f60d`
- `ole32!CoTaskMemFree` at `0x18001f24f`
- `ole32!CoTaskMemFree` at `0x18001f3ba`
- `ole32!CoTaskMemFree` at `0x18001f4a2`
- `ole32!CoTaskMemFree` at `0x18001f4f3`
- `ole32!CoTaskMemFree` at `0x18001f5f0`
- `ole32!CoTaskMemFree` at `0x18001f60d`
- `SHELL32!SHCreateItemFromIDList` at `0x18001f4dc`
- `SHELL32!SHCreateItemFromIDList` at `0x18001f4dc`
- `SHELL32!SHCreateItemWithParent` at `0x18001f226`
- `SHELL32!SHCreateItemWithParent` at `0x18001f226`
- `SHELL32!SHGetIDListFromObject` at `0x18001f1f8`
- `SHELL32!SHGetIDListFromObject` at `0x18001f1f8`
- `SHELL32!SHAddToRecentDocs` at `0x18001f2ae`
- `SHELL32!SHAddToRecentDocs` at `0x18001f2ae`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18001f5c1`
- `PhotoBase!?New@BasePrivate@@YAPEAX_K_N@Z` at `0x18001f5c1`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18001f5ac`
- `PhotoBase!?BaseAtlThrow@ATL@@YAXJ@Z` at `0x18001f5ac`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001f46c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001f4bc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001f559`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001f46c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001f4bc`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18001f559`

## pseudocode

```c
// Hidden C++ exception states: #wind=13 #try_helpers=1
__int64 __fastcall ShellListManager::FoundItem(ShellListManager *this, IUnknown *a2, const struct _ITEMIDLIST *a3)
{
  const ITEMIDLIST *v5; // rdi
  HRESULT v6; // eax
  int v7; // edx
  LPCVOID v8; // rbx
  __int64 (__fastcall ***v10)(LPCVOID, GUID *, void **); // rbx
  int v11; // edx
  HRESULT v12; // ebx
  __int64 v13; // rcx
  bool v14; // bl
  __int64 v15; // r15
  unsigned __int64 v16; // r14
  unsigned __int64 v17; // rdx
  bool v18; // r8
  unsigned int v19; // edx
  ITEMIDLIST *v20; // rcx
  int v21; // eax
  int v22; // edx
  unsigned __int16 *v23; // r14
  void *v24; // rax
  LPCVOID pv; // [rsp+30h] [rbp-58h] BYREF
  unsigned __int16 *v26; // [rsp+38h] [rbp-50h] BYREF
  __int64 v27; // [rsp+40h] [rbp-48h] BYREF
  void *ppv; // [rsp+48h] [rbp-40h] BYREF
  LPITEMIDLIST ppidl; // [rsp+50h] [rbp-38h] BYREF
  _QWORD v30[3]; // [rsp+58h] [rbp-30h] BYREF
  int v31; // [rsp+90h] [rbp+8h] BYREF
  LPCITEMIDLIST pidl; // [rsp+A8h] [rbp+20h] BYREF

  if ( !*((_BYTE *)this + 2249) )
    return 2147500036LL;
  v5 = 0;
  ppidl = 0;
  v6 = SHGetIDListFromObject(a2, &ppidl);
  if ( v6 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v6, v7);
    goto LABEL_36;
  }
  pv = 0;
  if ( SHCreateItemWithParent(ppidl, 0, a3, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, (void **)&pv) >= 0 )
  {
    v31 = 0;
    if ( *((_BYTE *)this + 2248)
      && (*(int (__fastcall **)(char *, int *))(*((_QWORD *)this - 1) + 24LL))((char *)this - 8, &v31) >= 0
      && !v31 )
    {
      SHAddToRecentDocs(8u, pv);
      goto LABEL_27;
    }
    v10 = (__int64 (__fastcall ***)(LPCVOID, GUID *, void **))pv;
    v26 = 0;
    ppv = 0;
    v27 = 0;
    if ( (*(int (__fastcall **)(LPCVOID, _QWORD, const GUID *, GUID *, __int64 *))(*(_QWORD *)pv + 24LL))(
           pv,
           0,
           &BHID_SFUIObject,
           &GUID_000214f9_0000_0000_c000_000000000046,
           &v27) < 0 )
    {
      v12 = (**v10)(v10, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
      if ( v27 )
        (*(void (__fastcall **)(__int64))(*(_QWORD *)v27 + 16LL))(v27);
      while ( v12 < 0 )
      {
LABEL_38:
        Base::Throw((Base *)(unsigned int)v12, v11);
LABEL_39:
        v20 = (ITEMIDLIST *)pidl;
        if ( pidl )
        {
          v12 = SHCreateItemFromIDList(pidl, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, &ppv);
          v20 = (ITEMIDLIST *)pidl;
        }
        else
        {
          v12 = -2147467259;
        }
        CoTaskMemFree(v20);
        pidl = 0;
        ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v27);
      }
      v13 = 0;
      v30[0] = 0;
      if ( ppv )
      {
        (**(void (__fastcall ***)(void *, GUID *, _QWORD *))ppv)(ppv, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, v30);
        v13 = v30[0];
      }
      if ( v13
        && (*(int (__fastcall **)(__int64, const PROPERTYKEY *, unsigned __int16 **))(*(_QWORD *)v13 + 136LL))(
             v13,
             &PKEY_ItemType,
             &v26) >= 0
        || (v21 = (*(__int64 (__fastcall **)(void *, __int64, unsigned __int16 **))(*(_QWORD *)ppv + 40LL))(
                    ppv,
                    2147581953LL,
                    &v26),
            v21 >= 0) )
      {
        if ( v30[0] )
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v30[0] + 16LL))(v30[0]);
        if ( ppv )
          (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
        if ( !*((_BYTE *)this + 88) )
        {
          v14 = 0;
          goto LABEL_26;
        }
      }
      else
      {
        Base::Throw((Base *)(unsigned int)v21, v22);
      }
      v23 = v26;
      v14 = (SupportedFileTypes::ClassifyFile((ShellListManager *)((char *)this + 88), v26) & 1) != 0
         || (unsigned __int8)SupportedFileTypes::IsSupportedVideoFile((char *)this + 88, v23);
LABEL_26:
      CoTaskMemFree(v26);
      if ( !v14 )
        goto LABEL_4;
LABEL_27:
      v8 = pv;
      if ( pv )
      {
        v15 = *((_QWORD *)this + 10);
        v16 = *(_QWORD *)(v15 + 232);
        if ( v16 >= *(_QWORD *)(v15 + 240)
          && !(unsigned __int8)ATL::CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>::GrowBuffer(
                                 v15 + 224,
                                 v16 + 1) )
        {
          ATL::BaseAtlThrow(-2147024882);
          __debugbreak();
        }
        *(_QWORD *)(*(_QWORD *)(v15 + 224) + 8 * v16) = v8;
        (*(void (__fastcall **)(LPCVOID))(*(_QWORD *)v8 + 8LL))(v8);
        if ( ++*(_QWORD *)(v15 + 232) == 1 )
        {
          *(_QWORD *)(v15 + 416) = 0;
          LOBYTE(v17) = 1;
          v24 = BasePrivate::New((BasePrivate *)0x18, v17, v18);
          if ( v24 )
            v5 = (const ITEMIDLIST *)ShellListIteratorNotification::ShellListIteratorNotification(v24, 4, 0, 0);
          pidl = v5;
          ATL::CAtlList<ATL::CAutoPtr<ShellListIteratorNotification>,ATL::CAutoPtrElementTraits<ShellListIteratorNotification>>::AddTail(
            v15 + 368,
            &pidl);
          PostMessageW(*(HWND *)(v15 + 56), 0x400u, 0, 0);
          if ( pidl )
            ShellListIteratorNotification::`scalar deleting destructor'((ShellListIteratorNotification *)pidl, v19);
        }
        v8 = pv;
      }
      goto LABEL_5;
    }
LABEL_36:
    pidl = 0;
    v12 = (*(__int64 (__fastcall **)(__int64, LPCITEMIDLIST *))(*(_QWORD *)v27 + 32LL))(v27, &pidl);
    if ( v12 >= 0 )
      goto LABEL_39;
    CoTaskMemFree((LPVOID)pidl);
    pidl = 0;
    ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v27);
    goto LABEL_38;
  }
LABEL_4:
  v8 = pv;
LABEL_5:
  if ( v8 )
    (*(void (__fastcall **)(LPCVOID))(*(_QWORD *)v8 + 16LL))(v8);
  CoTaskMemFree(ppidl);
  return 0;
}

```

## disassembly

```asm
0x18001f1c0  mov     [rsp+arg_8], rbx
0x18001f1c5  mov     [rsp+arg_10], rsi
0x18001f1ca  push    rdi
0x18001f1cb  push    r14
0x18001f1cd  push    r15
0x18001f1cf  sub     rsp, 70h
0x18001f1d3  mov     r14, r8
0x18001f1d6  mov     rax, rdx
0x18001f1d9  mov     rsi, rcx
0x18001f1dc  cmp     byte ptr [rcx+8C9h], 0
0x18001f1e3  jz      loc_18001F460
0x18001f1e9  xor     edi, edi
0x18001f1eb  mov     [rsp+88h+ppidl], rdi
0x18001f1f0  lea     rdx, [rsp+88h+ppidl]; ppidl
0x18001f1f5  mov     rcx, rax; punk
0x18001f1f8  call    cs:__imp_SHGetIDListFromObject
0x18001f1fe  test    eax, eax
0x18001f200  js      loc_18001F46A
0x18001f206  mov     [rsp+88h+pv], rdi
0x18001f20b  lea     rax, [rsp+88h+pv]
0x18001f210  mov     [rsp+88h+ppvItem], rax; ppvItem
0x18001f215  lea     r9, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18001f21c  mov     r8, r14; pidl
0x18001f21f  xor     edx, edx; psfParent
0x18001f221  mov     rcx, [rsp+88h+ppidl]; pidlParent
0x18001f226  call    cs:__imp_SHCreateItemWithParent
0x18001f22c  test    eax, eax
0x18001f22e  jns     short loc_18001F26D
0x18001f230  mov     rbx, [rsp+88h+pv]
0x18001f235  test    rbx, rbx
0x18001f238  jz      short loc_18001F24A
0x18001f23a  mov     rax, [rbx]
0x18001f23d  mov     rcx, rbx
0x18001f240  mov     rax, [rax+10h]
0x18001f244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f249  nop
0x18001f24a  mov     rcx, [rsp+88h+ppidl]; pv
0x18001f24f  call    cs:__imp_CoTaskMemFree
0x18001f255  xor     eax, eax
0x18001f257  lea     r11, [rsp+88h+var_18]
0x18001f25c  mov     rbx, [r11+28h]
0x18001f260  mov     rsi, [r11+30h]
0x18001f264  mov     rsp, r11
0x18001f267  pop     r15
0x18001f269  pop     r14
0x18001f26b  pop     rdi
0x18001f26c  retn
0x18001f26d  mov     [rsp+88h+arg_0], edi
0x18001f274  cmp     byte ptr [rsi+8C8h], 0
0x18001f27b  jz      short loc_18001F2B9
0x18001f27d  mov     rax, [rsi-8]
0x18001f281  lea     rdx, [rsp+88h+arg_0]
0x18001f289  lea     rcx, [rsi-8]
0x18001f28d  mov     rax, [rax+18h]
0x18001f291  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f296  test    eax, eax
0x18001f298  js      short loc_18001F2B9
0x18001f29a  cmp     [rsp+88h+arg_0], 0
0x18001f2a2  jnz     short loc_18001F2B9
0x18001f2a4  mov     rdx, [rsp+88h+pv]; pv
0x18001f2a9  mov     ecx, 8; uFlags
0x18001f2ae  call    cs:__imp_SHAddToRecentDocs
0x18001f2b4  jmp     loc_18001F3C8
0x18001f2b9  mov     rbx, [rsp+88h+pv]
0x18001f2be  mov     [rsp+88h+var_50], rdi
0x18001f2c3  mov     [rsp+88h+ppv], rdi
0x18001f2c8  mov     [rsp+88h+var_48], rdi
0x18001f2cd  mov     rax, [rbx]
0x18001f2d0  lea     rcx, [rsp+88h+var_48]
0x18001f2d5  mov     [rsp+88h+ppvItem], rcx
0x18001f2da  lea     r9, _GUID_000214f9_0000_0000_c000_000000000046
0x18001f2e1  lea     r8, BHID_SFUIObject
0x18001f2e8  xor     edx, edx
0x18001f2ea  mov     rcx, rbx
0x18001f2ed  mov     rax, [rax+18h]
0x18001f2f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2f6  test    eax, eax
0x18001f2f8  jns     loc_18001F473
0x18001f2fe  mov     rax, [rbx]
0x18001f301  lea     r8, [rsp+88h+ppv]
0x18001f306  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe
0x18001f30d  mov     rcx, rbx
0x18001f310  mov     rax, [rax]
0x18001f313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f318  mov     ebx, eax
0x18001f31a  mov     rcx, [rsp+88h+var_48]
0x18001f31f  test    rcx, rcx
0x18001f322  jz      short loc_18001F331
0x18001f324  mov     rax, [rcx]
0x18001f327  mov     rax, [rax+10h]
0x18001f32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f330  nop
0x18001f331  test    ebx, ebx
0x18001f333  js      loc_18001F4BA
0x18001f339  mov     r9, [rsp+88h+ppv]
0x18001f33e  mov     rcx, rdi
0x18001f341  mov     [rsp+88h+var_30], rcx
0x18001f346  test    r9, r9
0x18001f349  jnz     loc_18001F510
0x18001f34f  test    rcx, rcx
0x18001f352  jz      loc_18001F534
0x18001f358  mov     rax, [rcx]
0x18001f35b  lea     r8, [rsp+88h+var_50]
0x18001f360  lea     rdx, PKEY_ItemType
0x18001f367  mov     rax, [rax+88h]
0x18001f36e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f373  test    eax, eax
0x18001f375  js      loc_18001F534
0x18001f37b  mov     rcx, [rsp+88h+var_30]
0x18001f380  test    rcx, rcx
0x18001f383  jz      short loc_18001F392
0x18001f385  mov     rax, [rcx]
0x18001f388  mov     rax, [rax+10h]
0x18001f38c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f391  nop
0x18001f392  mov     rcx, [rsp+88h+ppv]
0x18001f397  test    rcx, rcx
0x18001f39a  jz      short loc_18001F3A9
0x18001f39c  mov     rax, [rcx]
0x18001f39f  mov     rax, [rax+10h]
0x18001f3a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3a8  nop
0x18001f3a9  cmp     byte ptr [rsi+58h], 0
0x18001f3ad  jnz     loc_18001F560
0x18001f3b3  xor     bl, bl
0x18001f3b5  mov     rcx, [rsp+88h+var_50]; pv
0x18001f3ba  call    cs:__imp_CoTaskMemFree
0x18001f3c0  test    bl, bl
0x18001f3c2  jz      loc_18001F230
0x18001f3c8  mov     rbx, [rsp+88h+pv]
0x18001f3cd  test    rbx, rbx
0x18001f3d0  jz      short loc_18001F416
0x18001f3d2  mov     r15, [rsi+50h]
0x18001f3d6  lea     rsi, [r15+0E0h]
0x18001f3dd  mov     r14, [rsi+8]
0x18001f3e1  cmp     r14, [rsi+10h]
0x18001f3e5  jnb     loc_18001F593
0x18001f3eb  mov     rax, [rsi]
0x18001f3ee  mov     [rax+r14*8], rbx
0x18001f3f2  mov     rax, [rbx]
0x18001f3f5  mov     rcx, rbx
0x18001f3f8  mov     rax, [rax+8]
0x18001f3fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f401  nop
0x18001f402  inc     qword ptr [rsi+8]
0x18001f406  cmp     qword ptr [rsi+8], 1
0x18001f40b  jz      loc_18001F5B3
0x18001f411  mov     rbx, [rsp+88h+pv]
0x18001f416  jmp     loc_18001F235
0x18001f41b  mov     [rsp+88h+pidl], rdi
0x18001f423  lea     rcx, [r15+170h]
0x18001f42a  lea     rdx, [rsp+88h+pidl]
0x18001f432  call    ?AddTail@?$CAtlList@V?$CAutoPtr@VShellListIteratorNotification@@@ATL@@V?$CAutoPtrElementTraits@VShellListIteratorNotification@@@2@@ATL@@QEAAPEAU__POSITION@@AEAV?$CAutoPtr@VShellListIteratorNotification@@@2@@Z; ATL::CAtlList<ATL::CAutoPtr<ShellListIteratorNotification>,ATL::CAutoPtrElementTraits<ShellListIteratorNotification>>::AddTail(ATL::CAutoPtr<ShellListIteratorNotification> &)
0x18001f437  xor     r9d, r9d; lParam
0x18001f43a  xor     r8d, r8d; wParam
0x18001f43d  mov     edx, 400h; Msg
0x18001f442  mov     rcx, [r15+38h]; hWnd
0x18001f446  call    cs:__imp_PostMessageW
0x18001f44c  mov     rcx, [rsp+88h+pidl]; this
0x18001f454  test    rcx, rcx
0x18001f457  jz      short loc_18001F411
0x18001f459  call    ??_GShellListIteratorNotification@@QEAAPEAXI@Z; ShellListIteratorNotification::`scalar deleting destructor'(uint)
0x18001f45e  jmp     short loc_18001F411
0x18001f460  mov     eax, 80004004h
0x18001f465  jmp     loc_18001F257
0x18001f46a  mov     ecx, eax
0x18001f46c  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001f472  nop
0x18001f473  mov     [rsp+88h+pidl], rdi
0x18001f47b  mov     rcx, [rsp+88h+var_48]
0x18001f480  mov     rax, [rcx]
0x18001f483  lea     rdx, [rsp+88h+pidl]
0x18001f48b  mov     rax, [rax+20h]
0x18001f48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f494  mov     ebx, eax
0x18001f496  test    eax, eax
0x18001f498  jns     short loc_18001F4C3
0x18001f49a  mov     rcx, [rsp+88h+pidl]; pv
0x18001f4a2  call    cs:__imp_CoTaskMemFree
0x18001f4a8  mov     [rsp+88h+pidl], rdi
0x18001f4b0  lea     rcx, [rsp+88h+var_48]
0x18001f4b5  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001f4ba  mov     ecx, ebx
0x18001f4bc  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001f4c2  nop
0x18001f4c3  mov     rcx, [rsp+88h+pidl]; pv
0x18001f4cb  test    rcx, rcx
0x18001f4ce  jz      short loc_18001F4EE
0x18001f4d0  lea     r8, [rsp+88h+ppv]; ppv
0x18001f4d5  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x18001f4dc  call    cs:__imp_SHCreateItemFromIDList
0x18001f4e2  mov     ebx, eax
0x18001f4e4  mov     rcx, [rsp+88h+pidl]
0x18001f4ec  jmp     short loc_18001F4F3
0x18001f4ee  mov     ebx, 80004005h
0x18001f4f3  call    cs:__imp_CoTaskMemFree
0x18001f4f9  mov     [rsp+88h+pidl], rdi
0x18001f501  lea     rcx, [rsp+88h+var_48]
0x18001f506  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001f50b  jmp     loc_18001F331
0x18001f510  mov     rax, [r9]
0x18001f513  lea     r8, [rsp+88h+var_30]
0x18001f518  lea     rdx, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93
0x18001f51f  mov     rcx, r9
0x18001f522  mov     rax, [rax]
0x18001f525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f52a  mov     rcx, [rsp+88h+var_30]
0x18001f52f  jmp     loc_18001F34F
0x18001f534  mov     rcx, [rsp+88h+ppv]
0x18001f539  mov     rax, [rcx]
0x18001f53c  lea     r8, [rsp+88h+var_50]
0x18001f541  mov     edx, 80018001h
0x18001f546  mov     rax, [rax+28h]
0x18001f54a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f54f  test    eax, eax
0x18001f551  jns     loc_18001F37B
0x18001f557  mov     ecx, eax
0x18001f559  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18001f55f  nop
0x18001f560  mov     r14, [rsp+88h+var_50]
0x18001f565  mov     rdx, r14; unsigned __int16 *
0x18001f568  lea     rcx, [rsi+58h]; this
0x18001f56c  call    ?ClassifyFile@SupportedFileTypes@@AEBAKPEBG@Z; SupportedFileTypes::ClassifyFile(ushort const *)
0x18001f571  test    al, 1
0x18001f573  jnz     short loc_18001F58C
0x18001f575  mov     rdx, r14
0x18001f578  lea     rcx, [rsi+58h]
0x18001f57c  call    ?IsSupportedVideoFile@SupportedFileTypes@@QEBA_NPEBGW4ContextOfSupportedFile@1@@Z; SupportedFileTypes::IsSupportedVideoFile(ushort const *,SupportedFileTypes::ContextOfSupportedFile)
0x18001f581  test    al, al
0x18001f583  jnz     short loc_18001F58C
0x18001f585  xor     bl, bl
0x18001f587  jmp     loc_18001F3B5
0x18001f58c  mov     bl, 1
0x18001f58e  jmp     loc_18001F3B5
0x18001f593  lea     rdx, [r14+1]
0x18001f597  mov     rcx, rsi
0x18001f59a  call    ?GrowBuffer@?$CAtlArray@V?$CComQIPtr@UIShellItem@@$1?_GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe@@3U__s_GUID@@B@ATL@@V?$CComQIPtrElementTraits@UIShellItem@@$1?_GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe@@3U__s_GUID@@B@2@@ATL@@AEAA_N_K@Z; ATL::CAtlArray<ATL::CComQIPtr<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>,ATL::CComQIPtrElementTraits<IShellItem,&__s_GUID const _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe>>::GrowBuffer(unsigned __int64)
0x18001f59f  test    al, al
0x18001f5a1  jnz     loc_18001F3EB
0x18001f5a7  mov     ecx, 8007000Eh
0x18001f5ac  call    cs:__imp_?BaseAtlThrow@ATL@@YAXJ@Z; ATL::BaseAtlThrow(long)
0x18001f5b2  int     3; Trap to Debugger
0x18001f5b3  mov     [r15+1A0h], rdi
0x18001f5ba  mov     dl, 1
0x18001f5bc  mov     ecx, 18h
0x18001f5c1  call    cs:__imp_?New@BasePrivate@@YAPEAX_K_N@Z; BasePrivate::New(unsigned __int64,bool)
0x18001f5c7  test    rax, rax
0x18001f5ca  jz      loc_18001F41B
0x18001f5d0  xor     r9d, r9d
0x18001f5d3  xor     r8d, r8d
0x18001f5d6  mov     edx, 4
0x18001f5db  mov     rcx, rax
0x18001f5de  call    ??0ShellListIteratorNotification@@QEAA@W4NotifyCode@0@PEAUIShellItem@@1@Z; ShellListIteratorNotification::ShellListIteratorNotification(ShellListIteratorNotification::NotifyCode,IShellItem *,IShellItem *)
0x18001f5e3  mov     rdi, rax
0x18001f5e6  jmp     loc_18001F41B
0x18001f5eb  mov     rcx, [rsp+88h+var_50]; pv
0x18001f5f0  call    cs:__imp_CoTaskMemFree
0x18001f5f6  xor     edi, edi
0x18001f5f8  mov     [rsp+88h+var_50], rdi
0x18001f5fd  lea     rcx, [rsp+88h+pv]
0x18001f602  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18001f607  nop
0x18001f608  mov     rcx, [rsp+88h+ppidl]; pv
0x18001f60d  call    cs:__imp_CoTaskMemFree
0x18001f613  mov     eax, dword ptr [rsp+88h+pidl]
0x18001f61a  jmp     loc_18001F257
```
