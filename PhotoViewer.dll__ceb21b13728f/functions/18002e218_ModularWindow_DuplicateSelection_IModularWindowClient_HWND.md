# ModularWindow::DuplicateSelection(IModularWindowClient *,HWND__ *)

- ea: `0x18002e218`
- end: `0x18002e4ff`
- name: `?DuplicateSelection@ModularWindow@@YAXPEAUIModularWindowClient@@PEAUHWND__@@@Z`
- size: `743`
- prototype: `void __fastcall(ModularWindow *__hidden this, struct IModularWindowClient *, HWND)`
- caller_count: `1`
- callee_count: `22`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180046df0`

## callees

- `0x1800037d8`
- `0x1800041a4`
- `0x180004908`
- `0x18000cb74`
- `0x180025f90`
- `0x180026724`
- `0x18002d388`
- `0x18002e218`
- `0x18002e508`
- `0x18002e5a8`
- `0x18002e6bc`
- `0x18002ea84`
- `0x18002ec48`
- `0x18002ecc8`
- `0x18002ed0c`
- `0x18002ed38`
- `0x18003df00`
- `0x180040264`
- `0x18004b0d4`
- `0x18007a710`
- `0x18007a73c`
- `0x180080010`

## import_xrefs

- `KERNEL32!CopyFileW` at `0x18002e48f`
- `KERNEL32!CopyFileW` at `0x18002e48f`
- `ADVAPI32!DuplicateEncryptionInfoFile` at `0x18002e475`
- `ADVAPI32!DuplicateEncryptionInfoFile` at `0x18002e475`
- `SHLWAPI!PathFindExtensionW` at `0x18002e355`
- `SHLWAPI!PathFindExtensionW` at `0x18002e355`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e398`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e417`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e398`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002e417`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e238`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e2aa`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e2d1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e409`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e238`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e2aa`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e2d1`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002e409`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002e499`
- `PhotoBase!?ThrowLastError@Base@@YAXXZ` at `0x18002e499`

## pseudocode

```c
// Hidden C++ exception states: #wind=13
void __fastcall ModularWindow::DuplicateSelection(ModularWindow *this, struct IModularWindowClient *a2, HWND a3)
{
  __int64 v5; // r8
  int v6; // eax
  int v7; // edx
  int v8; // eax
  int v9; // edx
  const unsigned __int16 *v10; // rax
  Base::Path *v11; // rax
  __int64 v12; // r8
  const WCHAR *v13; // rax
  const unsigned __int16 *ExtensionW; // rax
  __int64 BaseStringManager; // rax
  struct Path *v16; // r8
  __int64 v17; // r8
  __int64 v18; // rax
  int v19; // eax
  int v20; // edx
  __int64 v21; // rax
  struct Base::String *v22; // r8
  const WCHAR *v23; // rax
  const WCHAR *v24; // rax
  Base *v25; // rcx
  LPCWSTR pszPath; // [rsp+30h] [rbp-D0h] BYREF
  struct IDataObject *v27; // [rsp+38h] [rbp-C8h] BYREF
  __int64 v28; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v29; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v30[48]; // [rsp+50h] [rbp-B0h] BYREF
  int v31; // [rsp+80h] [rbp-80h] BYREF
  struct IModularWindowClient *v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  int v34; // [rsp+ACh] [rbp-54h]
  LPCWSTR DstFileName; // [rsp+B0h] [rbp-50h]
  int v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+D0h] [rbp-30h]
  __int64 v38; // [rsp+D8h] [rbp-28h]
  int v39; // [rsp+E0h] [rbp-20h]
  __int64 v40; // [rsp+E8h] [rbp-18h]
  __int64 v41; // [rsp+140h] [rbp+40h] BYREF
  const WCHAR *v42; // [rsp+150h] [rbp+50h] BYREF
  char v43; // [rsp+158h] [rbp+58h] BYREF

  if ( !this )
  {
    Base::Throw((Base *)0x80070057LL, (_DWORD)a2);
    __debugbreak();
  }
  memset_0(&v31, 0, 0x98u);
  v31 = 152;
  v32 = a2;
  Base::ResourceString::ResourceString((Base::ResourceString *)&v29, 0x1B69u);
  v38 = v29;
  v27 = 0;
  LOBYTE(v5) = 1;
  v6 = (*(__int64 (__fastcall **)(ModularWindow *, struct IDataObject **, __int64))(*(_QWORD *)this + 104LL))(
         this,
         &v27,
         v5);
  if ( v6 != -2147287038 )
  {
    if ( v6 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v6, v7);
      __debugbreak();
    }
    DragDrop::HDropData::HDropData((DragDrop::HDropData *)v30);
    v8 = DragDrop::HDropData::GetFromDataObject((DragDrop::HDropData *)v30, v27);
    if ( v8 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v8, v9);
      __debugbreak();
    }
    v10 = DragDrop::HDropData::WszFiles((DragDrop::HDropData *)v30);
    Base::Path::Path((Base::Path *)&pszPath, v10);
    Base::String::String((Base::String *)&v42, (const struct Base::String *)&pszPath);
    v11 = Base::Path::StripPath((Base::Path *)&v42);
    Base::Path::AppendExtraNull(v11);
    v13 = v42;
    if ( ((*((_DWORD *)v42 - 3) - 261) | (1 - *((_DWORD *)v42 - 2))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v42, 261, v12);
      v13 = v42;
    }
    DstFileName = v13;
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v42, 0xFFFFFFFFLL);
    v36 = 261;
    ExtensionW = PathFindExtensionW(pszPath);
    Base::Path::Path((Base::Path *)&v43, ExtensionW);
    ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v43);
    Base::Path::AppendExtraNull((Base::Path *)&v43);
    v40 = ATL::CSimpleStringT<unsigned short,0>::GetBuffer(&v43) + 2;
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v43, 0xFFFFFFFFLL);
    BaseStringManager = Base::String::GetBaseStringManager();
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v41, BaseStringManager);
    ModularWindow::GetTargetDirectoryForDuplicate((ModularWindow *)&pszPath, (const struct Path *)&v41, v16);
    v18 = v41;
    if ( ((*(_DWORD *)(v41 - 12) - 260) | (1 - *(_DWORD *)(v41 - 8))) < 0 )
    {
      ATL::CSimpleStringT<unsigned short,0>::PrepareWrite2(&v41, 260, v17);
      v18 = v41;
    }
    v37 = v18;
    ATL::CSimpleStringT<unsigned short,0>::ReleaseBuffer(&v41, 0xFFFFFFFFLL);
    v39 = 2050;
    v19 = (*(__int64 (__fastcall **)(ModularWindow *))(*(_QWORD *)this + 112LL))(this);
    if ( v19 < 0 )
    {
      Base::Throw((Base *)(unsigned int)v19, v20);
      __debugbreak();
    }
    v34 = 0;
    v21 = Base::String::GetBaseStringManager();
    ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&v28, v21);
    ModularWindow::GetFilterStringForDuplicate(&pszPath, (const struct Path *)&v28, v22);
    v33 = v28;
    if ( (unsigned int)IsolationAwareGetSaveFileNameW(&v31) )
    {
      v23 = DragDrop::HDropData::WszFiles((DragDrop::HDropData *)v30);
      DuplicateEncryptionInfoFile(v23, DstFileName, 2u, 0x80u, 0);
      v24 = DragDrop::HDropData::WszFiles((DragDrop::HDropData *)v30);
      if ( !CopyFileW(v24, DstFileName, 0) )
        Base::ThrowLastError(v25);
    }
    Base::String::~String((Base::String *)&v28);
    Base::String::~String((Base::String *)&v41);
    Base::String::~String((Base::String *)&v43);
    Base::String::~String((Base::String *)&v42);
    Base::String::~String((Base::String *)&pszPath);
    DragDrop::HDropData::~HDropData((DragDrop::HDropData *)v30);
  }
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v27);
  Base::String::~String((Base::String *)&v29);
}

```

## disassembly

```asm
0x18002e218  push    rbp
0x18002e21a  push    rbx
0x18002e21b  push    rdi
0x18002e21c  lea     rbp, [rsp-20h]
0x18002e221  sub     rsp, 120h
0x18002e228  mov     rdi, rdx
0x18002e22b  mov     rbx, rcx
0x18002e22e  test    rcx, rcx
0x18002e231  jnz     short loc_18002E23F
0x18002e233  mov     ecx, 80070057h
0x18002e238  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002e23e  int     3; Trap to Debugger
0x18002e23f  xor     edx, edx; Val
0x18002e241  mov     r8d, 98h; Size
0x18002e247  lea     rcx, [rbp+30h+var_B0]; void *
0x18002e24b  call    memset_0
0x18002e250  mov     [rbp+30h+var_B0], 98h
0x18002e257  mov     [rbp+30h+var_A8], rdi
0x18002e25b  mov     edx, 1B69h; unsigned int
0x18002e260  lea     rcx, [rsp+130h+var_E8]; this
0x18002e265  call    ??0ResourceString@Base@@QEAA@I@Z; Base::ResourceString::ResourceString(uint)
0x18002e26a  nop
0x18002e26b  mov     rax, [rsp+130h+var_E8]
0x18002e270  mov     [rbp+30h+var_58], rax
0x18002e274  mov     [rsp+130h+var_F8], 0
0x18002e27d  mov     rax, [rbx]
0x18002e280  mov     edi, 1
0x18002e285  mov     r8b, dil
0x18002e288  lea     rdx, [rsp+130h+var_F8]
0x18002e28d  mov     rcx, rbx
0x18002e290  mov     rax, [rax+68h]
0x18002e294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e299  cmp     eax, 80030002h
0x18002e29e  jz      loc_18002E4DF
0x18002e2a4  test    eax, eax
0x18002e2a6  jns     short loc_18002E2B1
0x18002e2a8  mov     ecx, eax
0x18002e2aa  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002e2b0  int     3; Trap to Debugger
0x18002e2b1  lea     rcx, [rsp+130h+var_E0]; this
0x18002e2b6  call    ??0HDropData@DragDrop@@QEAA@XZ; DragDrop::HDropData::HDropData(void)
0x18002e2bb  nop
0x18002e2bc  mov     rdx, [rsp+130h+var_F8]; struct IDataObject *
0x18002e2c1  lea     rcx, [rsp+130h+var_E0]; this
0x18002e2c6  call    ?GetFromDataObject@HDropData@DragDrop@@QEAAJPEAUIDataObject@@@Z; DragDrop::HDropData::GetFromDataObject(IDataObject *)
0x18002e2cb  test    eax, eax
0x18002e2cd  jns     short loc_18002E2D8
0x18002e2cf  mov     ecx, eax
0x18002e2d1  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002e2d7  int     3; Trap to Debugger
0x18002e2d8  lea     rcx, [rsp+130h+var_E0]; this
0x18002e2dd  call    ?WszFiles@HDropData@DragDrop@@QEBAPEBGXZ; DragDrop::HDropData::WszFiles(void)
0x18002e2e2  mov     rdx, rax; unsigned __int16 *
0x18002e2e5  lea     rcx, [rsp+130h+pszPath]; this
0x18002e2ea  call    ??0Path@Base@@QEAA@PEBG@Z; Base::Path::Path(ushort const *)
0x18002e2ef  nop
0x18002e2f0  lea     rdx, [rsp+130h+pszPath]; struct Base::String *
0x18002e2f5  lea     rcx, [rbp+30h+arg_10]; this
0x18002e2f9  call    ??0String@Base@@QEAA@AEBV01@@Z; Base::String::String(Base::String const &)
0x18002e2fe  nop
0x18002e2ff  lea     rcx, [rbp+30h+arg_10]; this
0x18002e303  call    ?StripPath@Path@Base@@QEAAAEAV12@XZ; Base::Path::StripPath(void)
0x18002e308  mov     rcx, rax; this
0x18002e30b  call    ?AppendExtraNull@Path@Base@@QEAAAEAV12@XZ; Base::Path::AppendExtraNull(void)
0x18002e310  mov     rax, [rbp+30h+arg_10]
0x18002e314  mov     edx, edi
0x18002e316  sub     edx, [rax-8]
0x18002e319  mov     ecx, [rax-0Ch]
0x18002e31c  sub     ecx, 105h
0x18002e322  or      edx, ecx
0x18002e324  jge     short loc_18002E338
0x18002e326  mov     edx, 105h
0x18002e32b  lea     rcx, [rbp+30h+arg_10]
0x18002e32f  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002e334  mov     rax, [rbp+30h+arg_10]
0x18002e338  mov     [rbp+30h+DstFileName], rax
0x18002e33c  or      edx, 0FFFFFFFFh
0x18002e33f  lea     rcx, [rbp+30h+arg_10]
0x18002e343  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e348  nop
0x18002e349  mov     [rbp+30h+var_78], 105h
0x18002e350  mov     rcx, [rsp+130h+pszPath]; pszPath
0x18002e355  call    cs:__imp_PathFindExtensionW
0x18002e35b  mov     rdx, rax; unsigned __int16 *
0x18002e35e  lea     rcx, [rbp+30h+arg_18]; this
0x18002e362  call    ??0Path@Base@@QEAA@PEBG@Z; Base::Path::Path(ushort const *)
0x18002e367  nop
0x18002e368  lea     rcx, [rbp+30h+arg_18]
0x18002e36c  call    ?MakeLower@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x18002e371  lea     rcx, [rbp+30h+arg_18]; this
0x18002e375  call    ?AppendExtraNull@Path@Base@@QEAAAEAV12@XZ; Base::Path::AppendExtraNull(void)
0x18002e37a  lea     rcx, [rbp+30h+arg_18]
0x18002e37e  call    ?GetBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAPEAGXZ; ATL::CSimpleStringT<ushort,0>::GetBuffer(void)
0x18002e383  add     rax, 2
0x18002e387  mov     [rbp+30h+var_48], rax
0x18002e38b  or      edx, 0FFFFFFFFh
0x18002e38e  lea     rcx, [rbp+30h+arg_18]
0x18002e392  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e397  nop
0x18002e398  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002e39e  nop
0x18002e39f  mov     rdx, rax
0x18002e3a2  lea     rcx, [rbp+30h+arg_0]
0x18002e3a6  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002e3ab  nop
0x18002e3ac  lea     rdx, [rbp+30h+arg_0]; struct Path *
0x18002e3b0  lea     rcx, [rsp+130h+pszPath]; this
0x18002e3b5  call    ?GetTargetDirectoryForDuplicate@ModularWindow@@YAXAEBVPath@Base@@PEAV23@@Z; ModularWindow::GetTargetDirectoryForDuplicate(Base::Path const &,Base::Path *)
0x18002e3ba  mov     rax, [rbp+30h+arg_0]
0x18002e3be  sub     edi, [rax-8]
0x18002e3c1  mov     ecx, [rax-0Ch]
0x18002e3c4  mov     edx, 104h
0x18002e3c9  sub     ecx, edx
0x18002e3cb  or      edi, ecx
0x18002e3cd  jge     short loc_18002E3DC
0x18002e3cf  lea     rcx, [rbp+30h+arg_0]
0x18002e3d3  call    ?PrepareWrite2@?$CSimpleStringT@G$0A@@ATL@@AEAAXH@Z; ATL::CSimpleStringT<ushort,0>::PrepareWrite2(int)
0x18002e3d8  mov     rax, [rbp+30h+arg_0]
0x18002e3dc  mov     [rbp+30h+var_60], rax
0x18002e3e0  or      edx, 0FFFFFFFFh
0x18002e3e3  lea     rcx, [rbp+30h+arg_0]
0x18002e3e7  call    ?ReleaseBuffer@?$CSimpleStringT@G$0A@@ATL@@QEAAXH@Z; ATL::CSimpleStringT<ushort,0>::ReleaseBuffer(int)
0x18002e3ec  nop
0x18002e3ed  mov     [rbp+30h+var_50], 802h
0x18002e3f4  mov     rax, [rbx]
0x18002e3f7  mov     rcx, rbx
0x18002e3fa  mov     rax, [rax+70h]
0x18002e3fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002e403  test    eax, eax
0x18002e405  jns     short loc_18002E410
0x18002e407  mov     ecx, eax
0x18002e409  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002e40f  int     3; Trap to Debugger
0x18002e410  mov     [rbp+30h+var_84], 0
0x18002e417  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002e41d  nop
0x18002e41e  mov     rdx, rax
0x18002e421  lea     rcx, [rsp+130h+var_F0]
0x18002e426  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002e42b  nop
0x18002e42c  lea     rdx, [rsp+130h+var_F0]; struct Path *
0x18002e431  lea     rcx, [rsp+130h+pszPath]; this
0x18002e436  call    ?GetFilterStringForDuplicate@ModularWindow@@YAXAEBVPath@Base@@PEAVString@3@@Z; ModularWindow::GetFilterStringForDuplicate(Base::Path const &,Base::String *)
0x18002e43b  mov     rax, [rsp+130h+var_F0]
0x18002e440  mov     [rbp+30h+var_98], rax
0x18002e444  lea     rcx, [rbp+30h+var_B0]
0x18002e448  call    IsolationAwareGetSaveFileNameW
0x18002e44d  test    eax, eax
0x18002e44f  jz      short loc_18002E4A0
0x18002e451  lea     rcx, [rsp+130h+var_E0]; this
0x18002e456  call    ?WszFiles@HDropData@DragDrop@@QEBAPEBGXZ; DragDrop::HDropData::WszFiles(void)
0x18002e45b  mov     rcx, rax; SrcFileName
0x18002e45e  mov     [rsp+130h+lpSecurityAttributes], 0; lpSecurityAttributes
0x18002e467  mov     r9d, 80h; dwAttributes
0x18002e46d  lea     r8d, [r9-7Eh]; dwCreationDistribution
0x18002e471  mov     rdx, [rbp+30h+DstFileName]; DstFileName
0x18002e475  call    cs:__imp_DuplicateEncryptionInfoFile
0x18002e47b  lea     rcx, [rsp+130h+var_E0]; this
0x18002e480  call    ?WszFiles@HDropData@DragDrop@@QEBAPEBGXZ; DragDrop::HDropData::WszFiles(void)
0x18002e485  xor     r8d, r8d; bFailIfExists
0x18002e488  mov     rdx, [rbp+30h+DstFileName]; lpNewFileName
0x18002e48c  mov     rcx, rax; lpExistingFileName
0x18002e48f  call    cs:__imp_CopyFileW
0x18002e495  test    eax, eax
0x18002e497  jnz     short loc_18002E4A0
0x18002e499  call    cs:__imp_?ThrowLastError@Base@@YAXXZ; Base::ThrowLastError(void)
0x18002e49f  nop
0x18002e4a0  lea     rcx, [rsp+130h+var_F0]; this
0x18002e4a5  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e4aa  nop
0x18002e4ab  lea     rcx, [rbp+30h+arg_0]; this
0x18002e4af  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e4b4  nop
0x18002e4b5  lea     rcx, [rbp+30h+arg_18]; this
0x18002e4b9  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e4be  nop
0x18002e4bf  lea     rcx, [rbp+30h+arg_10]; this
0x18002e4c3  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e4c8  nop
0x18002e4c9  lea     rcx, [rsp+130h+pszPath]; this
0x18002e4ce  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e4d3  nop
0x18002e4d4  lea     rcx, [rsp+130h+var_E0]; this
0x18002e4d9  call    ??1HDropData@DragDrop@@QEAA@XZ; DragDrop::HDropData::~HDropData(void)
0x18002e4de  nop
0x18002e4df  lea     rcx, [rsp+130h+var_F8]
0x18002e4e4  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002e4e9  nop
0x18002e4ea  lea     rcx, [rsp+130h+var_E8]; this
0x18002e4ef  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002e4f4  add     rsp, 120h
0x18002e4fb  pop     rdi
0x18002e4fc  pop     rbx
0x18002e4fd  pop     rbp
0x18002e4fe  retn
```
