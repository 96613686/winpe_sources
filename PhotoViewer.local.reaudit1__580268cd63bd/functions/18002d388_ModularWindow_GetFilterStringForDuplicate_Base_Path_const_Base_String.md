# ModularWindow::GetFilterStringForDuplicate(Base::Path const &,Base::String *)

- ea: `0x18002d388`
- end: `0x18002d512`
- name: `?GetFilterStringForDuplicate@ModularWindow@@YAXAEBVPath@Base@@PEAVString@3@@Z`
- size: `394`
- prototype: `void __fastcall(ModularWindow *__hidden this, const struct Path *, struct Base::String *)`
- caller_count: `1`
- callee_count: `13`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18002e218`

## callees

- `0x180004908`
- `0x180004e88`
- `0x18000cb74`
- `0x180026724`
- `0x18002d388`
- `0x18002d518`
- `0x18002ddc0`
- `0x18002e5a8`
- `0x18002e8fc`
- `0x18002e970`
- `0x18002ea00`
- `0x18002ea84`
- `0x180080010`

## import_xrefs

- `ole32!PropVariantClear` at `0x18002d471`
- `ole32!PropVariantClear` at `0x18002d471`
- `SHELL32!SHCreateItemFromParsingName` at `0x18002d3bd`
- `SHELL32!SHCreateItemFromParsingName` at `0x18002d3bd`
- `SHLWAPI!PathFindExtensionW` at `0x18002d4a4`
- `SHLWAPI!PathFindExtensionW` at `0x18002d4a4`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002d43c`
- `PhotoBase!?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ` at `0x18002d43c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002d3c9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002d3f3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002d431`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002d3c9`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002d3f3`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18002d431`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall ModularWindow::GetFilterStringForDuplicate(
        PCWSTR *this,
        const struct Path *a2,
        struct Base::String *a3)
{
  HRESULT v5; // eax
  int v6; // edx
  int v7; // eax
  int v8; // edx
  int v9; // eax
  int v10; // edx
  LARGE_INTEGER hVal; // rbx
  __int64 BaseStringManager; // rax
  const unsigned __int16 *ExtensionW; // rax
  PROPVARIANT pvar; // [rsp+30h] [rbp-20h] BYREF
  void *ppv; // [rsp+70h] [rbp+20h] BYREF
  __int64 v16; // [rsp+80h] [rbp+30h] BYREF
  __int64 v17; // [rsp+88h] [rbp+38h] BYREF

  v17 = 0;
  ppv = 0;
  v5 = SHCreateItemFromParsingName(*this, 0, &GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93, &ppv);
  if ( v5 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v5, v6);
    __debugbreak();
  }
  v7 = (*(__int64 (__fastcall **)(void *, _QWORD, GUID *, __int64 *))(*(_QWORD *)ppv + 64LL))(
         ppv,
         0,
         &GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99,
         &v17);
  if ( v7 < 0 )
    Base::Throw((Base *)(unsigned int)v7, v8);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&ppv);
  memset(&pvar, 0, sizeof(pvar));
  v9 = (*(__int64 (__fastcall **)(__int64, const PROPERTYKEY *, PROPVARIANT *))(*(_QWORD *)v17 + 40LL))(
         v17,
         &PKEY_ItemTypeText,
         &pvar);
  if ( v9 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v9, v10);
    __debugbreak();
  }
  hVal = pvar.hVal;
  BaseStringManager = Base::String::GetBaseStringManager();
  ATL::CSimpleStringT<unsigned short,0>::CSimpleStringT<unsigned short,0>(&ppv, BaseStringManager);
  if ( !(unsigned __int8)((__int64 (__fastcall *)(_QWORD, _QWORD))ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad)(
                           &ppv,
                           (LARGE_INTEGER)hVal.QuadPart) )
    ((void (__fastcall *)(_QWORD, _QWORD))ATL::CSimpleStringT<unsigned short,0>::SetString)(
      &ppv,
      (LARGE_INTEGER)hVal.QuadPart);
  PropVariantClear(&pvar);
  ATL::CSimpleStringT<unsigned short,0>::operator=(a2, &ppv);
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, L"$");
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, L"*");
  ExtensionW = PathFindExtensionW(*this);
  Base::Path::Path((Base::Path *)&v16, ExtensionW);
  ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::MakeLower(&v16);
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, v16, *(unsigned int *)(v16 - 16));
  ATL::CSimpleStringT<unsigned short,0>::Append(a2, L"$");
  ATL::CStringT<unsigned short,StrTraitBase<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(a2);
  Base::String::~String((Base::String *)&v16);
  Base::String::~String((Base::String *)&ppv);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v17);
}

```

## disassembly

```asm
0x18002d388  mov     [rsp-18h+arg_8], rbx
0x18002d38d  push    rbp
0x18002d38e  push    rsi
0x18002d38f  push    rdi
0x18002d390  mov     rbp, rsp
0x18002d393  sub     rsp, 50h
0x18002d397  mov     rdi, rdx
0x18002d39a  mov     rsi, rcx
0x18002d39d  mov     [rbp+arg_18], 0
0x18002d3a5  mov     [rbp+ppv], 0
0x18002d3ad  lea     r9, [rbp+ppv]; ppv
0x18002d3b1  lea     r8, _GUID_7e9fb0d3_919f_4307_ab2e_9b1860310c93; riid
0x18002d3b8  xor     edx, edx; pbc
0x18002d3ba  mov     rcx, [rcx]; pszPath
0x18002d3bd  call    cs:__imp_SHCreateItemFromParsingName
0x18002d3c3  test    eax, eax
0x18002d3c5  jns     short loc_18002D3D0
0x18002d3c7  mov     ecx, eax
0x18002d3c9  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002d3cf  int     3; Trap to Debugger
0x18002d3d0  mov     rcx, [rbp+ppv]
0x18002d3d4  mov     rax, [rcx]
0x18002d3d7  lea     r9, [rbp+arg_18]
0x18002d3db  lea     r8, _GUID_886d8eeb_8cf2_4446_8d02_cdba1dbdcf99
0x18002d3e2  xor     edx, edx
0x18002d3e4  mov     rax, [rax+40h]
0x18002d3e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d3ed  test    eax, eax
0x18002d3ef  jns     short loc_18002D3FA
0x18002d3f1  mov     ecx, eax
0x18002d3f3  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002d3f9  nop
0x18002d3fa  lea     rcx, [rbp+ppv]
0x18002d3fe  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002d403  xorps   xmm0, xmm0
0x18002d406  xor     eax, eax
0x18002d408  movups  xmmword ptr [rbp+pvar], xmm0
0x18002d40c  mov     qword ptr [rbp+pvar+10h], rax
0x18002d410  mov     rcx, [rbp+arg_18]
0x18002d414  mov     rax, [rcx]
0x18002d417  lea     r8, [rbp+pvar]
0x18002d41b  lea     rdx, PKEY_ItemTypeText
0x18002d422  mov     rax, [rax+28h]
0x18002d426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d42b  test    eax, eax
0x18002d42d  jns     short loc_18002D438
0x18002d42f  mov     ecx, eax
0x18002d431  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18002d437  int     3; Trap to Debugger
0x18002d438  mov     rbx, qword ptr [rbp+pvar+8]
0x18002d43c  call    cs:__imp_?GetBaseStringManager@String@Base@@SAAEAVCAtlStringMgr@ATL@@XZ; Base::String::GetBaseStringManager(void)
0x18002d442  nop
0x18002d443  mov     rdx, rax
0x18002d446  lea     rcx, [rbp+ppv]
0x18002d44a  call    ??0?$CSimpleStringT@G$0A@@ATL@@QEAA@PEAUIAtlStringMgr@1@@Z; ATL::CSimpleStringT<ushort,0>::CSimpleStringT<ushort,0>(ATL::IAtlStringMgr *)
0x18002d44f  nop
0x18002d450  mov     rdx, rbx
0x18002d453  lea     rcx, [rbp+ppv]
0x18002d457  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x18002d45c  test    al, al
0x18002d45e  jnz     short loc_18002D46D
0x18002d460  mov     rdx, rbx
0x18002d463  lea     rcx, [rbp+ppv]
0x18002d467  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18002d46c  nop
0x18002d46d  lea     rcx, [rbp+pvar]; pvar
0x18002d471  call    cs:__imp_PropVariantClear
0x18002d477  lea     rdx, [rbp+ppv]
0x18002d47b  mov     rcx, rdi
0x18002d47e  call    ??4?$CSimpleStringT@G$0A@@ATL@@QEAAAEAV01@AEBV01@@Z; ATL::CSimpleStringT<ushort,0>::operator=(ATL::CSimpleStringT<ushort,0> const &)
0x18002d483  lea     rdx, asc_18008960C; "$"
0x18002d48a  mov     rcx, rdi
0x18002d48d  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18002d492  lea     rdx, asc_180089620; "*"
0x18002d499  mov     rcx, rdi
0x18002d49c  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18002d4a1  mov     rcx, [rsi]; pszPath
0x18002d4a4  call    cs:__imp_PathFindExtensionW
0x18002d4aa  mov     rdx, rax; unsigned __int16 *
0x18002d4ad  lea     rcx, [rbp+arg_10]; this
0x18002d4b1  call    ??0Path@Base@@QEAA@PEBG@Z; Base::Path::Path(ushort const *)
0x18002d4b6  nop
0x18002d4b7  lea     rcx, [rbp+arg_10]
0x18002d4bb  call    ?MakeLower@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@QEAAAEAV12@XZ; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::MakeLower(void)
0x18002d4c0  mov     rdx, [rbp+arg_10]
0x18002d4c4  mov     r8d, [rdx-10h]
0x18002d4c8  mov     rcx, rdi
0x18002d4cb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x18002d4d0  lea     rdx, asc_18008960C; "$"
0x18002d4d7  mov     rcx, rdi
0x18002d4da  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *)
0x18002d4df  mov     rcx, rdi
0x18002d4e2  call    ?Replace@?$CStringT@GV?$StrTraitBase@GV?$ChTraitsCRT@G@ATL@@@@@ATL@@QEAAHGG@Z; ATL::CStringT<ushort,StrTraitBase<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort,ushort)
0x18002d4e7  nop
0x18002d4e8  lea     rcx, [rbp+arg_10]; this
0x18002d4ec  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002d4f1  nop
0x18002d4f2  lea     rcx, [rbp+ppv]; this
0x18002d4f6  call    ??1String@Base@@QEAA@XZ; Base::String::~String(void)
0x18002d4fb  nop
0x18002d4fc  lea     rcx, [rbp+arg_18]
0x18002d500  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18002d505  mov     rbx, [rsp+50h+arg_8]
0x18002d50a  add     rsp, 50h
0x18002d50e  pop     rdi
0x18002d50f  pop     rsi
0x18002d510  pop     rbp
0x18002d511  retn
```
