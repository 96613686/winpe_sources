# FontCache::~FontCache(void)

- ea: `0x180068184`
- end: `0x1800681d7`
- name: `??1FontCache@@UEAA@XZ`
- size: `83`
- prototype: `void __fastcall(FontCache *__hidden this)`
- caller_count: `3`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800a55fc`
- `0x1800a5a8c`
- `0x1800b5cb0`

## callees

- `0x180028c50`
- `0x18004ff84`
- `0x1800680b0`
- `0x18006abbc`
- `0x1800a5860`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800681b2`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800681b2`

## pseudocode

```c
void __fastcall FontCache::~FontCache(FontCache *this)
{
  *(_QWORD *)this = &FontCache::`vftable';
  FontCache::FlushAndClose(this);
  Event::~Event((FontCache *)((char *)this + 112));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 64));
  DWrite::RefString::DecrementRef(*((struct DWrite::RefString::Data **)this + 6));
  DWrite::RefString::DecrementRef(*((struct DWrite::RefString::Data **)this + 5));
  EventSource<ComInterfaceList<FontCache,IFontCache,IFontCacheInternal>,IFontCacheInternal>::~EventSource<ComInterfaceList<FontCache,IFontCache,IFontCacheInternal>,IFontCacheInternal>(this);
}

```

## disassembly

```asm
0x180068184  push    rbx
0x180068186  sub     rsp, 20h
0x18006818a  lea     rax, ??_7FontCache@@6B@; const FontCache::`vftable'
0x180068191  mov     rbx, rcx
0x180068194  mov     [rcx], rax
0x180068197  call    ?FlushAndClose@FontCache@@UEAAJXZ; FontCache::FlushAndClose(void)
0x18006819c  lea     rcx, [rbx+70h]; this
0x1800681a0  call    ??1Event@@QEAA@XZ; Event::~Event(void)
0x1800681a5  lea     rcx, [rbx+68h]
0x1800681a9  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x1800681ae  lea     rcx, [rbx+40h]; lpCriticalSection
0x1800681b2  call    cs:__imp_DeleteCriticalSection
0x1800681b8  mov     rcx, [rbx+30h]; struct DWrite::RefString::Data *
0x1800681bc  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800681c1  mov     rcx, [rbx+28h]; struct DWrite::RefString::Data *
0x1800681c5  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x1800681ca  mov     rcx, rbx
0x1800681cd  add     rsp, 20h
0x1800681d1  pop     rbx
0x1800681d2  jmp     ??1?$EventSource@V?$ComInterfaceList@VFontCache@@UIFontCache@@UIFontCacheInternal@@@@UIFontCacheInternal@@@@UEAA@XZ; EventSource<ComInterfaceList<FontCache,IFontCache,IFontCacheInternal>,IFontCacheInternal>::~EventSource<ComInterfaceList<FontCache,IFontCache,IFontCacheInternal>,IFontCacheInternal>(void)
```
