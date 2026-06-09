# CKnownFoldersFilter::GetThisPCRegItemCLSID(_ITEMIDLIST_ABSOLUTE const *,_GUID *)

- ea: `0x180024744`
- end: `0x1800249cf`
- name: `?GetThisPCRegItemCLSID@CKnownFoldersFilter@@AEAAJPEBU_ITEMIDLIST_ABSOLUTE@@PEAU_GUID@@@Z`
- size: `651`
- prototype: `int(CKnownFoldersFilter *__hidden this, const struct _ITEMIDLIST_ABSOLUTE *, struct _GUID *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x1800245dc`

## callees

- `0x1800218ac`
- `0x1800235e8`
- `0x1800244dc`
- `0x180024744`
- `0x180026424`
- `0x1800340a0`
- `0x180210010`

## import_xrefs

- `SHELL32!SHGetKnownFolderIDList` at `0x1800247bd`
- `SHELL32!SHGetKnownFolderIDList` at `0x1800247bd`
- `SHELL32!SHCreateItemFromIDList` at `0x180024867`
- `SHELL32!SHCreateItemFromIDList` at `0x180024867`
- `SHELL32!__imp_ILRemoveLastID` at `0x18002492c`
- `SHELL32!__imp_ILRemoveLastID` at `0x18002492c`
- `SHELL32!__imp_ILClone` at `0x18002480b`
- `SHELL32!__imp_ILClone` at `0x18002480b`
- `SHELL32!__imp_ILIsParent` at `0x1800247f6`
- `SHELL32!__imp_ILIsParent` at `0x1800247f6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002490a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002491e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800247de`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180024831`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248b4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800248c8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002490a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002491e`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CKnownFoldersFilter::GetThisPCRegItemCLSID(
        CKnownFoldersFilter *this,
        const ITEMIDLIST *a2,
        struct _GUID *a3)
{
  const ITEMIDLIST *v5; // rcx
  unsigned int v6; // edi
  unsigned int v7; // ebx
  ITEMIDLIST *v8; // rcx
  LPITEMIDLIST v9; // rsi
  void *v10; // rcx
  unsigned int v11; // ebx
  unsigned int v12; // edi
  void **v13; // rax
  HRESULT v14; // eax
  int ItemNamespaceCLSID; // eax
  struct IShellItem *v16; // rcx
  void *v17; // rcx
  ITEMIDLIST *v18; // rcx
  void *v20; // rcx
  ITEMIDLIST *v21; // rcx
  struct IShellItem *v22; // rcx
  LPITEMIDLIST ppidl; // [rsp+28h] [rbp-18h] BYREF
  char v24; // [rsp+30h] [rbp-10h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  LPVOID pv; // [rsp+70h] [rbp+30h] BYREF
  LPCITEMIDLIST pidl1; // [rsp+78h] [rbp+38h] BYREF
  struct IShellItem *v28; // [rsp+80h] [rbp+40h] BYREF

  pv = this;
  *a3 = GUID_NULL;
  v5 = a2;
  v6 = 0;
  if ( !a2 )
    return 0;
  do
  {
    if ( !v5->mkid.cb )
      break;
    ++v6;
    v5 = (const ITEMIDLIST *)((char *)v5 + v5->mkid.cb);
  }
  while ( v5 );
  if ( v6 < 2 )
    return 0;
  pidl1 = 0;
  ppidl = 0;
  v24 = 1;
  v7 = SHGetKnownFolderIDList(&FOLDERID_ComputerFolder, 0, 0, &ppidl);
  if ( v24 )
  {
    v8 = (ITEMIDLIST *)pidl1;
    pidl1 = ppidl;
    if ( v8 )
      CoTaskMemFree(v8);
  }
  if ( (v7 & 0x80000000) != 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xEC,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\knownfolderfilter.h",
      (const char *)v7,
      (int)&pidl1);
LABEL_26:
    v21 = (ITEMIDLIST *)pidl1;
    pidl1 = 0;
    if ( v21 )
      CoTaskMemFree(v21);
    return v7;
  }
  if ( !ILIsParent(pidl1, a2, 0) )
  {
LABEL_20:
    v18 = (ITEMIDLIST *)pidl1;
    pidl1 = 0;
    if ( v18 )
      CoTaskMemFree(v18);
    return 0;
  }
  pv = 0;
  v9 = ILClone(a2);
  v7 = v9 == 0 ? 0x8007000E : 0;
  v10 = pv;
  pv = v9;
  if ( v10 )
    CoTaskMemFree(v10);
  if ( !v9 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF1,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\knownfolderfilter.h",
      (const char *)v7,
      (int)&pidl1);
LABEL_24:
    v20 = pv;
    pv = 0;
    if ( v20 )
      CoTaskMemFree(v20);
    goto LABEL_26;
  }
  v11 = 0;
  v12 = v6 - 2;
  if ( v12 )
  {
    do
    {
      ILRemoveLastID((LPITEMIDLIST)pv);
      ++v11;
    }
    while ( v11 < v12 );
  }
  v28 = 0;
  v13 = (void **)IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(&v28);
  v14 = SHCreateItemFromIDList((LPCITEMIDLIST)pv, &GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe, v13);
  v7 = v14;
  if ( v14 >= 0 )
  {
    ItemNamespaceCLSID = GetItemNamespaceCLSID(v28, a3);
    v7 = ItemNamespaceCLSID;
    if ( ItemNamespaceCLSID >= 0 )
    {
      v16 = v28;
      if ( v28 )
      {
        v28 = 0;
        ((void (__fastcall *)(struct IShellItem *))v16->lpVtbl->Release)(v16);
      }
      v17 = pv;
      pv = 0;
      if ( v17 )
        CoTaskMemFree(v17);
      goto LABEL_20;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xF9,
      (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\knownfolderfilter.h",
      (const char *)(unsigned int)ItemNamespaceCLSID,
      (int)&pidl1);
    v22 = v28;
    if ( v28 )
    {
      v28 = 0;
      ((void (__fastcall *)(struct IShellItem *))v22->lpVtbl->Release)(v22);
    }
    goto LABEL_24;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0xF8,
    (unsigned int)"onecoreuap\\internal\\shell\\inc\\private\\knownfolderfilter.h",
    (const char *)(unsigned int)v14,
    (int)&pidl1);
  Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(&v28);
  wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &pv,
    0);
  wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>::reset(
    &pidl1,
    0);
  return v7;
}

```

## disassembly

```asm
0x180024744  mov     [rsp-28h+arg_18], rbx
0x180024749  mov     [rsp-28h+pv], rcx
0x18002474e  push    rbp
0x18002474f  push    rsi
0x180024750  push    rdi
0x180024751  push    r14
0x180024753  push    r15
0x180024755  mov     rbp, rsp
0x180024758  sub     rsp, 40h
0x18002475c  mov     r14, r8
0x18002475f  mov     rsi, rdx
0x180024762  movups  xmm0, xmmword ptr cs:GUID_NULL.Data1
0x180024769  movdqu  xmmword ptr [r8], xmm0
0x18002476e  mov     rcx, rdx
0x180024771  xor     r15d, r15d
0x180024774  mov     edi, r15d
0x180024777  test    rdx, rdx
0x18002477a  jz      loc_1800248CE
0x180024780  cmp     [rcx], r15w
0x180024784  jz      short loc_180024790
0x180024786  movzx   eax, word ptr [rcx]
0x180024789  inc     edi
0x18002478b  add     rcx, rax
0x18002478e  jnz     short loc_180024780
0x180024790  cmp     edi, 2
0x180024793  jb      loc_1800248CE
0x180024799  mov     [rbp+pidl1], r15
0x18002479d  lea     rax, [rbp+pidl1]
0x1800247a1  mov     [rbp+var_20], rax
0x1800247a5  mov     [rbp+ppidl], r15
0x1800247a9  mov     [rbp+var_10], 1
0x1800247ad  lea     r9, [rbp+ppidl]; ppidl
0x1800247b1  xor     r8d, r8d; hToken
0x1800247b4  xor     edx, edx; dwFlags
0x1800247b6  lea     rcx, FOLDERID_ComputerFolder; rfid
0x1800247bd  call    cs:__imp_SHGetKnownFolderIDList
0x1800247c3  mov     ebx, eax
0x1800247c5  cmp     [rbp+var_10], r15b
0x1800247c9  jz      short loc_1800247E4
0x1800247cb  mov     r8, [rbp+var_20]
0x1800247cf  mov     rcx, [r8]; pv
0x1800247d2  mov     rdx, [rbp+ppidl]
0x1800247d6  mov     [r8], rdx
0x1800247d9  test    rcx, rcx
0x1800247dc  jz      short loc_1800247E4
0x1800247de  call    cs:__imp_CoTaskMemFree
0x1800247e4  test    ebx, ebx
0x1800247e6  js      loc_18002493E
0x1800247ec  xor     r8d, r8d; fImmediate
0x1800247ef  mov     rdx, rsi; pidl2
0x1800247f2  mov     rcx, [rbp+pidl1]; pidl1
0x1800247f6  call    cs:__imp_ILIsParent
0x1800247fc  test    eax, eax
0x1800247fe  jz      loc_1800248BB
0x180024804  mov     [rbp+pv], r15
0x180024808  mov     rcx, rsi; pidl
0x18002480b  call    cs:__imp_ILClone
0x180024811  mov     rsi, rax
0x180024814  mov     rcx, rax
0x180024817  neg     rcx
0x18002481a  sbb     ebx, ebx
0x18002481c  not     ebx
0x18002481e  and     ebx, 8007000Eh
0x180024824  mov     rcx, [rbp+pv]; pv
0x180024828  mov     [rbp+pv], rax
0x18002482c  test    rcx, rcx
0x18002482f  jz      short loc_180024837
0x180024831  call    cs:__imp_CoTaskMemFree
0x180024837  test    rsi, rsi
0x18002483a  jz      loc_1800248E4
0x180024840  mov     ebx, r15d
0x180024843  add     edi, 0FFFFFFFEh
0x180024846  jnz     loc_180024928
0x18002484c  mov     [rbp+arg_10], r15
0x180024850  lea     rcx, [rbp+arg_10]
0x180024854  call    ??$IID_PPV_ARGS_Helper@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@@YAPEAPEAXV?$ComPtrRef@V?$ComPtr@UISyncRootManager@@@WRL@Microsoft@@@Details@WRL@Microsoft@@@Z; IID_PPV_ARGS_Helper<Microsoft::WRL::ComPtr<ISyncRootManager>>(Microsoft::WRL::Details::ComPtrRef<Microsoft::WRL::ComPtr<ISyncRootManager>>)
0x180024859  mov     r8, rax; ppv
0x18002485c  lea     rdx, _GUID_43826d1e_e718_42ee_bc55_a1e261c37bfe; riid
0x180024863  mov     rcx, [rbp+pv]; pidl
0x180024867  call    cs:__imp_SHCreateItemFromIDList
0x18002486d  mov     ebx, eax
0x18002486f  test    eax, eax
0x180024871  js      loc_180024990
0x180024877  mov     rdx, r14; struct _GUID *
0x18002487a  mov     rcx, [rbp+arg_10]; struct IShellItem *
0x18002487e  call    ?GetItemNamespaceCLSID@@YAJPEAUIShellItem@@PEAU_GUID@@@Z; GetItemNamespaceCLSID(IShellItem *,_GUID *)
0x180024883  mov     ebx, eax
0x180024885  test    eax, eax
0x180024887  js      loc_180024958
0x18002488d  mov     rcx, [rbp+arg_10]
0x180024891  test    rcx, rcx
0x180024894  jz      short loc_1800248A7
0x180024896  mov     [rbp+arg_10], r15
0x18002489a  mov     rax, [rcx]
0x18002489d  mov     rax, [rax+10h]
0x1800248a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248a6  nop
0x1800248a7  mov     rcx, [rbp+pv]; pv
0x1800248ab  mov     [rbp+pv], r15
0x1800248af  test    rcx, rcx
0x1800248b2  jz      short loc_1800248BB
0x1800248b4  call    cs:__imp_CoTaskMemFree
0x1800248ba  nop
0x1800248bb  mov     rcx, [rbp+pidl1]; pv
0x1800248bf  mov     [rbp+pidl1], r15
0x1800248c3  test    rcx, rcx
0x1800248c6  jz      short loc_1800248CE
0x1800248c8  call    cs:__imp_CoTaskMemFree
0x1800248ce  xor     eax, eax
0x1800248d0  mov     rbx, [rsp+40h+arg_18]
0x1800248d8  add     rsp, 40h
0x1800248dc  pop     r15
0x1800248de  pop     r14
0x1800248e0  pop     rdi
0x1800248e1  pop     rsi
0x1800248e2  pop     rbp
0x1800248e3  retn
0x1800248e4  mov     rcx, [rbp+28h]; this
0x1800248e8  mov     r9d, ebx; char *
0x1800248eb  lea     r8, aOnecoreuapInte_12; "onecoreuap\\internal\\shell\\inc\\priva"...
0x1800248f2  mov     edx, 0F1h; void *
0x1800248f7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800248fc  nop
0x1800248fd  mov     rcx, [rbp+pv]; pv
0x180024901  mov     [rbp+pv], r15
0x180024905  test    rcx, rcx
0x180024908  jz      short loc_180024911
0x18002490a  call    cs:__imp_CoTaskMemFree
0x180024910  nop
0x180024911  mov     rcx, [rbp+pidl1]; pv
0x180024915  mov     [rbp+pidl1], r15
0x180024919  test    rcx, rcx
0x18002491c  jz      short loc_180024924
0x18002491e  call    cs:__imp_CoTaskMemFree
0x180024924  mov     eax, ebx
0x180024926  jmp     short loc_1800248D0
0x180024928  mov     rcx, [rbp+pv]; pidl
0x18002492c  call    cs:__imp_ILRemoveLastID
0x180024932  inc     ebx
0x180024934  cmp     ebx, edi
0x180024936  jnb     loc_18002484C
0x18002493c  jmp     short loc_180024928
0x18002493e  mov     rcx, [rbp+28h]; this
0x180024942  mov     r9d, ebx; char *
0x180024945  lea     r8, aOnecoreuapInte_12; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18002494c  mov     edx, 0ECh; void *
0x180024951  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024956  jmp     short loc_180024911
0x180024958  mov     rcx, [rbp+28h]; this
0x18002495c  mov     r9d, ebx; char *
0x18002495f  lea     r8, aOnecoreuapInte_12; "onecoreuap\\internal\\shell\\inc\\priva"...
0x180024966  mov     edx, 0F9h; void *
0x18002496b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180024970  nop
0x180024971  mov     rcx, [rbp+arg_10]
0x180024975  test    rcx, rcx
0x180024978  jz      short loc_18002498B
0x18002497a  mov     [rbp+arg_10], r15
0x18002497e  mov     rax, [rcx]
0x180024981  mov     rax, [rax+10h]
0x180024985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002498a  nop
0x18002498b  jmp     loc_1800248FD
0x180024990  mov     rcx, [rbp+28h]; this
0x180024994  mov     r9d, ebx; char *
0x180024997  lea     r8, aOnecoreuapInte_12; "onecoreuap\\internal\\shell\\inc\\priva"...
0x18002499e  mov     edx, 0F8h; void *
0x1800249a3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800249a8  nop
0x1800249a9  lea     rcx, [rbp+arg_10]
0x1800249ad  call    ?InternalRelease@?$ComPtr@UIKnownFolderProperties@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IKnownFolderProperties>::InternalRelease(void)
0x1800249b2  nop
0x1800249b3  xor     edx, edx
0x1800249b5  lea     rcx, [rbp+pv]
0x1800249b9  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800249be  nop
0x1800249bf  xor     edx, edx
0x1800249c1  lea     rcx, [rbp+pidl1]
0x1800249c5  call    ?reset@?$unique_ptr@U_ITEMIDLIST_ABSOLUTE@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAAXPEAU_ITEMIDLIST_ABSOLUTE@@@Z; wistd::unique_ptr<_ITEMIDLIST_ABSOLUTE,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>::reset(_ITEMIDLIST_ABSOLUTE *)
0x1800249ca  jmp     loc_180024924
```
