# FontLoaderManagerBase<IDWriteFontFileLoader,3>::~FontLoaderManagerBase<IDWriteFontFileLoader,3>(void)

- ea: `0x18006f5d4`
- end: `0x18006f629`
- name: `??1?$FontLoaderManagerBase@UIDWriteFontFileLoader@@$02@@IEAA@XZ`
- size: `85`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18006f544`
- `0x18006f5c8`
- `0x1800e1c58`

## callees

- `0x180013e60`
- `0x18009d8a4`
- `0x1800ab4dc`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f603`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006f603`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void __fastcall FontLoaderManagerBase<IDWriteFontFileLoader,3>::~FontLoaderManagerBase<IDWriteFontFileLoader,3>(
        char *a1)
{
  std::_Tree<std::_Tmap_traits<FontSetRegion::FileEntry const *,unsigned int,std::less<FontSetRegion::FileEntry const *>,std::allocator<std::pair<FontSetRegion::FileEntry const * const,unsigned int>>,0>>::~_Tree<std::_Tmap_traits<FontSetRegion::FileEntry const *,unsigned int,std::less<FontSetRegion::FileEntry const *>,std::allocator<std::pair<FontSetRegion::FileEntry const * const,unsigned int>>,0>>();
  std::_Tree<std::_Tmap_traits<unsigned __int64,ComPtr<IDWriteFontFileLoader>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,ComPtr<IDWriteFontFileLoader>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,ComPtr<IDWriteFontFileLoader>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,ComPtr<IDWriteFontFileLoader>>>,0>>();
  DeleteCriticalSection((LPCRITICAL_SECTION)(a1 + 48));
  `eh vector destructor iterator'(
    a1,
    0x10u,
    3u,
    FontLoaderManagerBase<IDWriteFontFileLoader,3>::LoaderIdPair::~LoaderIdPair);
}

```

## disassembly

```asm
0x18006f5d4  mov     [rsp+arg_0], rcx
0x18006f5d9  push    rbx
0x18006f5da  sub     rsp, 20h
0x18006f5de  mov     rbx, rcx
0x18006f5e1  add     rcx, 68h ; 'h'
0x18006f5e5  mov     [rsp+28h+arg_8], rcx
0x18006f5ea  call    ??1?$_Tree@V?$_Tmap_traits@PEBUFileEntry@FontSetRegion@@IU?$less@PEBUFileEntry@FontSetRegion@@@std@@V?$allocator@U?$pair@QEBUFileEntry@FontSetRegion@@I@std@@@4@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<FontSetRegion::FileEntry const *,uint,std::less<FontSetRegion::FileEntry const *>,std::allocator<std::pair<FontSetRegion::FileEntry const * const,uint>>,0>>::~_Tree<std::_Tmap_traits<FontSetRegion::FileEntry const *,uint,std::less<FontSetRegion::FileEntry const *>,std::allocator<std::pair<FontSetRegion::FileEntry const * const,uint>>,0>>(void)
0x18006f5ef  nop
0x18006f5f0  lea     rcx, [rbx+58h]
0x18006f5f4  mov     [rsp+28h+arg_10], rcx
0x18006f5f9  call    ??1?$_Tree@V?$_Tmap_traits@_KV?$ComPtr@UIDWriteFontFileLoader@@@@U?$less@_K@std@@V?$allocator@U?$pair@$$CB_KV?$ComPtr@UIDWriteFontFileLoader@@@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<unsigned __int64,ComPtr<IDWriteFontFileLoader>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,ComPtr<IDWriteFontFileLoader>>>,0>>::~_Tree<std::_Tmap_traits<unsigned __int64,ComPtr<IDWriteFontFileLoader>,std::less<unsigned __int64>,std::allocator<std::pair<unsigned __int64 const,ComPtr<IDWriteFontFileLoader>>>,0>>(void)
0x18006f5fe  nop
0x18006f5ff  lea     rcx, [rbx+30h]; lpCriticalSection
0x18006f603  call    cs:__imp_DeleteCriticalSection
0x18006f609  nop
0x18006f60a  lea     r9, ??1LoaderIdPair@?$FontLoaderManagerBase@UIDWriteFontFileLoader@@$02@@QEAA@XZ; void (*)(void *)
0x18006f611  mov     edx, 10h; unsigned __int64
0x18006f616  lea     r8d, [rdx-0Dh]; unsigned __int64
0x18006f61a  mov     rcx, rbx; void *
0x18006f61d  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18006f622  nop
0x18006f623  add     rsp, 20h
0x18006f627  pop     rbx
0x18006f628  retn
```
