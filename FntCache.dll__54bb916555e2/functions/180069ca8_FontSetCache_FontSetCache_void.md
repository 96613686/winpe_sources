# FontSetCache::~FontSetCache(void)

- ea: `0x180069ca8`
- end: `0x180069d9f`
- name: `??1FontSetCache@@UEAA@XZ`
- size: `247`
- prototype: `void __fastcall(FontSetCache *__hidden this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180068240`

## callees

- `0x180011ea0`
- `0x180028c50`
- `0x18004ff84`
- `0x180068280`
- `0x180069ca8`
- `0x18006ab6c`
- `0x18006abbc`
- `0x1800a4120`
- `0x1800a57ac`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180069ce7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180069ce7`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069d32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069d5b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069d32`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180069d5b`

## pseudocode

```c
void __fastcall FontSetCache::~FontSetCache(FontSetCache *this)
{
  FontCacheStorage *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  *(_QWORD *)this = &FontSetCache::`vftable';
  FontSetCache::StopMonitorThread(this);
  v2 = (FontCacheStorage *)*((_QWORD *)this + 32);
  if ( v2 )
    FontCacheStorage::Close(v2);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 256);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 216));
  std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Tidy((char *)this + 192);
  Event::~Event((FontSetCache *)((char *)this + 184));
  RegistryKey::Close((FontSetCache *)((char *)this + 176));
  Event::~Event((FontSetCache *)((char *)this + 160));
  Event::~Event((FontSetCache *)((char *)this + 136));
  v3 = (void *)*((_QWORD *)this + 15);
  if ( v3 )
  {
    CloseHandle(v3);
    *((_QWORD *)this + 15) = 0;
  }
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 96);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 88);
  v4 = (void *)*((_QWORD *)this + 10);
  if ( v4 )
  {
    CloseHandle(v4);
    *((_QWORD *)this + 10) = 0;
  }
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 72);
  DWrite::RefString::DecrementRef(*((struct DWrite::RefString::Data **)this + 8));
  DWrite::RefString::DecrementRef(*((struct DWrite::RefString::Data **)this + 7));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 40);
  EventSource<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>::~EventSource<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>(this);
}

```

## disassembly

```asm
0x180069ca8  mov     [rsp+arg_0], rbx
0x180069cad  push    rdi
0x180069cae  sub     rsp, 20h
0x180069cb2  lea     rax, ??_7FontSetCache@@6B@; const FontSetCache::`vftable'
0x180069cb9  mov     rbx, rcx
0x180069cbc  mov     [rcx], rax
0x180069cbf  call    ?StopMonitorThread@FontSetCache@@UEAAXXZ; FontSetCache::StopMonitorThread(void)
0x180069cc4  lea     rdi, [rbx+100h]
0x180069ccb  mov     rcx, [rdi]; this
0x180069cce  test    rcx, rcx
0x180069cd1  jz      short loc_180069CD8
0x180069cd3  call    ?Close@FontCacheStorage@@QEAAXXZ; FontCacheStorage::Close(void)
0x180069cd8  mov     rcx, rdi
0x180069cdb  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x180069ce0  lea     rcx, [rbx+0D8h]; lpCriticalSection
0x180069ce7  call    cs:__imp_DeleteCriticalSection
0x180069ced  lea     rcx, [rbx+0C0h]
0x180069cf4  call    ?_Tidy@?$vector@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@V?$allocator@V?$ScopedHandle@UFileChangeNotificationHandlePolicy@@PEAX@@@std@@@std@@AEAAXXZ; std::vector<ScopedHandle<FileChangeNotificationHandlePolicy,void *>>::_Tidy(void)
0x180069cf9  lea     rcx, [rbx+0B8h]; this
0x180069d00  call    ??1Event@@QEAA@XZ; Event::~Event(void)
0x180069d05  lea     rcx, [rbx+0B0h]; this
0x180069d0c  call    ?Close@RegistryKey@@QEAAXXZ; RegistryKey::Close(void)
0x180069d11  lea     rcx, [rbx+0A0h]; this
0x180069d18  call    ??1Event@@QEAA@XZ; Event::~Event(void)
0x180069d1d  lea     rcx, [rbx+88h]; this
0x180069d24  call    ??1Event@@QEAA@XZ; Event::~Event(void)
0x180069d29  mov     rcx, [rbx+78h]; hObject
0x180069d2d  test    rcx, rcx
0x180069d30  jz      short loc_180069D40
0x180069d32  call    cs:__imp_CloseHandle
0x180069d38  mov     qword ptr [rbx+78h], 0
0x180069d40  lea     rcx, [rbx+60h]
0x180069d44  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x180069d49  lea     rcx, [rbx+58h]
0x180069d4d  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x180069d52  mov     rcx, [rbx+50h]; hObject
0x180069d56  test    rcx, rcx
0x180069d59  jz      short loc_180069D69
0x180069d5b  call    cs:__imp_CloseHandle
0x180069d61  mov     qword ptr [rbx+50h], 0
0x180069d69  lea     rcx, [rbx+48h]
0x180069d6d  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x180069d72  mov     rcx, [rbx+40h]; struct DWrite::RefString::Data *
0x180069d76  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180069d7b  mov     rcx, [rbx+38h]; struct DWrite::RefString::Data *
0x180069d7f  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180069d84  lea     rcx, [rbx+28h]
0x180069d88  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x180069d8d  mov     rcx, rbx
0x180069d90  mov     rbx, [rsp+28h+arg_0]
0x180069d95  add     rsp, 20h
0x180069d99  pop     rdi
0x180069d9a  jmp     ??1?$EventSource@V?$ComInterfaceList@VFontSetCache@@UIFontSetCache@@@@UIFontSetCache@@@@UEAA@XZ; EventSource<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>::~EventSource<ComInterfaceList<FontSetCache,IFontSetCache>,IFontSetCache>(void)
```
