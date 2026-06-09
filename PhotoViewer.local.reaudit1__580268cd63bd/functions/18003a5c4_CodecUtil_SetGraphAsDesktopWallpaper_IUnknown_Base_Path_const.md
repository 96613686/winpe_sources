# CodecUtil::SetGraphAsDesktopWallpaper(IUnknown *,Base::Path const &)

- ea: `0x18003a5c4`
- end: `0x18003a6d3`
- name: `?SetGraphAsDesktopWallpaper@CodecUtil@@YAXPEAUIUnknown@@AEBVPath@Base@@@Z`
- size: `271`
- prototype: `void(CodecUtil *__hidden this, struct IUnknown *, const struct Path *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18006f588`

## callees

- `0x18000cb74`
- `0x18002cbc0`
- `0x18003a5c4`
- `0x18007994c`
- `0x18007a024`
- `0x180080010`

## import_xrefs

- `ole32!CoCreateInstance` at `0x18003a63c`
- `ole32!CoCreateInstance` at `0x18003a63c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a5de`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a610`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a648`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a66c`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a5de`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a610`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a648`
- `PhotoBase!?Throw@Base@@YAXJ@Z` at `0x18003a66c`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
void __fastcall CodecUtil::SetGraphAsDesktopWallpaper(
        CodecUtil *this,
        struct IWICImagingFactory *a2,
        const struct Path *a3)
{
  int v4; // edx
  HRESULT Instance; // eax
  const unsigned __int16 *v6; // rdx
  LocalComLibraries *v7; // rcx
  const struct _GUID *v8; // r8
  struct IUnknown *v9; // r9
  int v10; // eax
  int v11; // edx
  struct INode **v12; // r9
  LPVOID *ppv; // [rsp+20h] [rbp-20h]
  LPVOID *ppva; // [rsp+20h] [rbp-20h]
  struct _GUID v15; // [rsp+30h] [rbp-10h] BYREF
  CodecUtilPrivate *v16; // [rsp+50h] [rbp+10h] BYREF
  struct IEngine *v17; // [rsp+60h] [rbp+20h] BYREF
  struct IEngine *v18; // [rsp+68h] [rbp+28h] BYREF

  if ( !this )
    Base::Throw((Base *)0x80004003LL, (_DWORD)a2);
  v17 = 0;
  (**(void (__fastcall ***)(CodecUtil *, GUID *, struct IEngine **))this)(
    this,
    &GUID_fdff62a4_3b50_491f_9fc3_a17b59d11066,
    &v17);
  if ( !v17 )
  {
    Base::Throw((Base *)0x80004002LL, v4);
    __debugbreak();
  }
  *(_QWORD *)&v15.Data1 = 0;
  Instance = CoCreateInstance(
               &CLSID_WICImagingFactory2,
               0,
               1u,
               &GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70,
               (LPVOID *)&v15);
  if ( Instance < 0 )
  {
    Base::Throw((Base *)(unsigned int)Instance, (_DWORD)v6);
    __debugbreak();
  }
  v16 = 0;
  v10 = LocalComLibraries::CoCreateInstance(v7, v6, v8, v9, (const struct _GUID *)ppv, (void **)&v16);
  if ( v10 < 0 )
  {
    Base::Throw((Base *)(unsigned int)v10, v11);
    __debugbreak();
  }
  v18 = 0;
  CodecUtilPrivate::CreateDesktopWallpaperGraph(v16, v17, (struct INode *)&v18, v12);
  CodecUtilPrivate::SetGraphAsDesktopWallpaperDirect(
    v16,
    v18,
    *(struct INode **)&v15.Data1,
    a2,
    (const struct Path *)ppva);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v18);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v16);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v15);
  ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(&v17);
}

```

## disassembly

```asm
0x18003a5c4  mov     [rsp-8+arg_8], rbx
0x18003a5c9  push    rbp
0x18003a5ca  mov     rbp, rsp
0x18003a5cd  sub     rsp, 40h
0x18003a5d1  mov     rbx, rdx
0x18003a5d4  test    rcx, rcx
0x18003a5d7  jnz     short loc_18003A5E5
0x18003a5d9  mov     ecx, 80004003h
0x18003a5de  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a5e4  nop
0x18003a5e5  mov     [rbp+arg_10], 0
0x18003a5ed  mov     rax, [rcx]
0x18003a5f0  lea     r8, [rbp+arg_10]
0x18003a5f4  lea     rdx, _GUID_fdff62a4_3b50_491f_9fc3_a17b59d11066
0x18003a5fb  mov     rax, [rax]
0x18003a5fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003a603  nop
0x18003a604  cmp     [rbp+arg_10], 0
0x18003a609  jnz     short loc_18003A617
0x18003a60b  mov     ecx, 80004002h
0x18003a610  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a616  int     3; Trap to Debugger
0x18003a617  mov     qword ptr [rbp+var_10.Data1], 0
0x18003a61f  lea     rax, [rbp+var_10]
0x18003a623  mov     [rsp+40h+ppv], rax; struct Path *
0x18003a628  lea     r9, _GUID_ec5ec8a9_c395_4314_9c77_54d7a935ff70; riid
0x18003a62f  xor     edx, edx; pUnkOuter
0x18003a631  lea     r8d, [rdx+1]; dwClsContext
0x18003a635  lea     rcx, CLSID_WICImagingFactory2; rclsid
0x18003a63c  call    cs:__imp_CoCreateInstance
0x18003a642  test    eax, eax
0x18003a644  jns     short loc_18003A64F
0x18003a646  mov     ecx, eax
0x18003a648  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a64e  int     3; Trap to Debugger
0x18003a64f  mov     [rbp+arg_0], 0
0x18003a657  lea     rax, [rbp+arg_0]
0x18003a65b  mov     [rsp+40h+var_18], rax; void **
0x18003a660  call    ?CoCreateInstance@LocalComLibraries@@QEAAJPEBGAEBU_GUID@@PEAUIUnknown@@1PEAPEAX@Z; LocalComLibraries::CoCreateInstance(ushort const *,_GUID const &,IUnknown *,_GUID const &,void * *)
0x18003a665  nop
0x18003a666  test    eax, eax
0x18003a668  jns     short loc_18003A673
0x18003a66a  mov     ecx, eax
0x18003a66c  call    cs:__imp_?Throw@Base@@YAXJ@Z; Base::Throw(long)
0x18003a672  int     3; Trap to Debugger
0x18003a673  mov     [rbp+arg_18], 0
0x18003a67b  lea     r8, [rbp+arg_18]; struct INode *
0x18003a67f  mov     rdx, [rbp+arg_10]; struct IEngine *
0x18003a683  mov     rcx, [rbp+arg_0]; this
0x18003a687  call    ?CreateDesktopWallpaperGraph@CodecUtilPrivate@@YAXPEAUIEngine@@PEAUINode@@PEAPEAU3@@Z; CodecUtilPrivate::CreateDesktopWallpaperGraph(IEngine *,INode *,INode * *)
0x18003a68c  mov     r9, rbx; struct IWICImagingFactory *
0x18003a68f  mov     r8, qword ptr [rbp+var_10.Data1]; struct INode *
0x18003a693  mov     rdx, [rbp+arg_18]; struct IEngine *
0x18003a697  mov     rcx, [rbp+arg_0]; this
0x18003a69b  call    ?SetGraphAsDesktopWallpaperDirect@CodecUtilPrivate@@YAXPEAUIEngine@@PEAUINode@@PEAUIWICImagingFactory@@AEBVPath@Base@@@Z; CodecUtilPrivate::SetGraphAsDesktopWallpaperDirect(IEngine *,INode *,IWICImagingFactory *,Base::Path const &)
0x18003a6a0  nop
0x18003a6a1  lea     rcx, [rbp+arg_18]
0x18003a6a5  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003a6aa  nop
0x18003a6ab  lea     rcx, [rbp+arg_0]
0x18003a6af  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003a6b4  nop
0x18003a6b5  lea     rcx, [rbp+var_10]
0x18003a6b9  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003a6be  nop
0x18003a6bf  lea     rcx, [rbp+arg_10]
0x18003a6c3  call    ??1?$CComPtrBase@UIFreeThreadedItemContainer@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IFreeThreadedItemContainer>::~CComPtrBase<IFreeThreadedItemContainer>(void)
0x18003a6c8  mov     rbx, [rsp+40h+arg_8]
0x18003a6cd  add     rsp, 40h
0x18003a6d1  pop     rbp
0x18003a6d2  retn
```
