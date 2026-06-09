# InternalGdiplusShutdown(void)

- ea: `0x18009f22c`
- end: `0x18009f886`
- name: `?InternalGdiplusShutdown@@YAPEAXXZ`
- size: `1626`
- prototype: `void *(void)`
- caller_count: `2`
- callee_count: `14`
- tags: `file_ops, authz_impersonation, loader_planting`

## callers

- `0x18009e77c`
- `0x18009f1a0`

## callees

- `0x18001ec80`
- `0x180026ad0`
- `0x18002724c`
- `0x18002739c`
- `0x18009f22c`
- `0x18009f88c`
- `0x18009f8b8`
- `0x18009f92c`
- `0x18009fb94`
- `0x1800fea50`
- `0x180117e68`
- `0x180121a90`
- `0x180146d60`
- `0x180169010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009f744`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009f874`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009f744`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18009f874`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f607`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18009f607`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f644`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18009f644`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f4d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f4f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f593`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f5ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f5c9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f4d3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f4f3`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f593`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f5ae`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18009f5c9`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18009f5e1`
- `api-ms-win-core-heap-l1-1-0!HeapDestroy` at `0x18009f5e1`
- `GDI32!DeleteDC` at `0x18009f40d`
- `GDI32!DeleteDC` at `0x18009f40d`
- `GDI32!DeleteObject` at `0x18009f756`
- `GDI32!DeleteObject` at `0x18009f756`

## pseudocode

```c
void *InternalGdiplusShutdown(void)
{
  void *v0; // rsi
  unsigned int v1; // edx
  void *v2; // rbx
  unsigned int v3; // ecx
  ols *v4; // rdi
  GpFontLink *v6; // rbx
  ols *v7; // rbx

  v0 = 0;
  TraceLoggingUnregister_EventUnregister();
  if ( Globals::BackgroundThreadHandle )
    v0 = BackgroundThreadShutdown();
  if ( Globals::PathLookAside )
    (**(void (__fastcall ***)(struct GpPath *, __int64))Globals::PathLookAside)(Globals::PathLookAside, 1);
  Globals::PathLookAside = 0;
  if ( Globals::MatrixLookAside )
    GpMatrix::`scalar deleting destructor'(Globals::MatrixLookAside, v1);
  Globals::MatrixLookAside = 0;
  if ( Globals::PenLookAside )
    (**(void (__fastcall ***)(struct GpPen *, __int64))Globals::PenLookAside)(Globals::PenLookAside, 1);
  Globals::PenLookAside = 0;
  if ( Globals::DesktopDevice )
    (**(void (__fastcall ***)(GpDevice *, __int64))Globals::DesktopDevice)(Globals::DesktopDevice, 1);
  v2 = Globals::DeviceList;
  Globals::DesktopDevice = 0;
  if ( Globals::DeviceList )
  {
    GpFree(*((_QWORD *)Globals::DeviceList + 1));
    operator delete(v2, 0x10u);
  }
  Globals::DeviceList = 0;
  if ( Globals::EngineDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::EngineDriver)(Globals::EngineDriver, 1);
  Globals::EngineDriver = 0;
  if ( Globals::DesktopDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::DesktopDriver)(Globals::DesktopDriver, 1);
  Globals::DesktopDriver = 0;
  if ( Globals::GdiDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::GdiDriver)(Globals::GdiDriver, 1);
  Globals::GdiDriver = 0;
  if ( Globals::D3DDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::D3DDriver)(Globals::D3DDriver, 1);
  Globals::D3DDriver = 0;
  if ( Globals::InfoDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::InfoDriver)(Globals::InfoDriver, 1);
  Globals::InfoDriver = 0;
  if ( Globals::MetaDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::MetaDriver)(Globals::MetaDriver, 1);
  Globals::MetaDriver = 0;
  if ( Globals::DesktopSurface )
    DpBitmap::`scalar deleting destructor'(Globals::DesktopSurface, v1);
  Globals::DesktopSurface = 0;
  if ( Globals::g_pTSDriver )
    (**(void (__fastcall ***)(struct DpDriver *, __int64))Globals::g_pTSDriver)(Globals::g_pTSDriver, 1);
  Globals::g_pTSDriver = 0;
  if ( Globals::g_pTSGraphics )
  {
    GpGraphics::`scalar deleting destructor'(Globals::g_pTSGraphics, v1);
    Globals::g_pTSGraphics = 0;
  }
  if ( Globals::g_pITSClientPlayer )
  {
    (**(void (__fastcall ***)(struct IMetafilePlayer *, __int64))Globals::g_pITSClientPlayer)(
      Globals::g_pITSClientPlayer,
      1);
    Globals::g_pITSClientPlayer = 0;
  }
  if ( Globals::g_pRemoteSurface )
  {
    DpBitmap::`scalar deleting destructor'(Globals::g_pRemoteSurface, v1);
    Globals::g_pRemoteSurface = 0;
  }
  if ( Globals::DdrawHandle )
  {
    FreeLibrary(Globals::DdrawHandle);
    Globals::DdrawHandle = 0;
  }
  if ( Globals::CachedGdiRegion )
  {
    DeleteObject(Globals::CachedGdiRegion);
    Globals::CachedGdiRegion = 0;
  }
  if ( Globals::DesktopIc )
  {
    DeleteDC(Globals::DesktopIc);
    Globals::DesktopIc = 0;
  }
  if ( Globals::TextCriticalSectionInitialized )
  {
    EnterCriticalSection(&Globals::TextCriticalSection);
    if ( Globals::FontCollection )
      (**(void (__fastcall ***)(struct GpFontCollection *, __int64))Globals::FontCollection)(Globals::FontCollection, 1);
    v6 = Globals::DWriteFontLinkTable;
    Globals::FontCollection = 0;
    if ( Globals::DWriteFontLinkTable )
    {
      GpFontLink::~GpFontLink(Globals::DWriteFontLinkTable);
      operator delete(v6, 0x40u);
      Globals::DWriteFontLinkTable = 0;
    }
    LeaveCriticalSection(&Globals::TextCriticalSection);
  }
  if ( (unsigned __int64)Globals::DWriteSurrogateFontsTable - 1 <= 0xFFFFFFFFFFFFFFFDuLL )
    GpFree(Globals::DWriteSurrogateFontsTable);
  Globals::DWriteSurrogateFontsTable = (struct GpFontFamily **)-1LL;
  if ( Globals::DWriteFontCacheLastRecentlyUsedList )
    operator delete(Globals::DWriteFontCacheLastRecentlyUsedList, 0x10u);
  Globals::DWriteFontCacheLastRecentlyUsedList = 0;
  Globals::GenericSansSerifFamily = 0;
  Globals::GenericSerifFamily = 0;
  Globals::GenericMonospaceFamily = 0;
  if ( Globals::NationalDigitCache )
    IntMap<unsigned char>::`scalar deleting destructor'(Globals::NationalDigitCache);
  Globals::NationalDigitCache = 0;
  GpStringFormat::DestroyStaticObjects();
  GpFree(Globals::FontsDirW);
  Globals::FontsDirW = 0;
  GpFree(Globals::FontsDirA);
  v3 = (unsigned int)Globals::LookAsideBuffer;
  Globals::FontsDirA = 0;
  if ( Globals::LookAsideBuffer )
  {
    GpFree(Globals::LookAsideBuffer);
    Globals::LookAsideBuffer = 0;
  }
  if ( Globals::TextCriticalSectionInitialized )
  {
    DeleteCriticalSection(&Globals::TextCriticalSection);
    Globals::TextCriticalSectionInitialized = 0;
  }
  FreeCachedCodecInfo(v3);
  if ( ImagingCritSec::initialized )
  {
    DeleteCriticalSection(&ImagingCritSec::critSec);
    ImagingCritSec::initialized = 0;
  }
  v4 = qword_1801A5618;
  if ( qword_1801A5618 )
  {
    do
    {
      v7 = (ols *)*((_QWORD *)v4 + 2);
      ols::~ols(v4);
      operator delete(v4, 0x20u);
      v4 = v7;
    }
    while ( v7 );
  }
  qword_1801A5618 = 0;
  if ( Globals::g_DWriteTextAnalyzer )
  {
    (*(void (__fastcall **)(struct IDWriteTextAnalyzer *))(*(_QWORD *)Globals::g_DWriteTextAnalyzer + 16LL))(Globals::g_DWriteTextAnalyzer);
    Globals::g_DWriteTextAnalyzer = 0;
  }
  if ( Globals::g_GpFontFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 112LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontFileLoader *))(*(_QWORD *)Globals::g_GpFontFileLoader + 16LL))(Globals::g_GpFontFileLoader);
    Globals::g_GpFontFileLoader = 0;
  }
  if ( Globals::g_GpFontCollectionStreamLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionStreamLoader
                                                                 + 16LL))(Globals::g_GpFontCollectionStreamLoader);
    Globals::g_GpFontCollectionStreamLoader = 0;
  }
  if ( Globals::g_GpFontCollectionFileLoader )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 48LL))(Globals::g_DWriteFactory);
    (*(void (__fastcall **)(struct IDWriteFontCollectionLoader *))(*(_QWORD *)Globals::g_GpFontCollectionFileLoader
                                                                 + 16LL))(Globals::g_GpFontCollectionFileLoader);
    Globals::g_GpFontCollectionFileLoader = 0;
  }
  if ( Globals::g_DWriteFactory )
  {
    (*(void (__fastcall **)(struct IDWriteFactory *))(*(_QWORD *)Globals::g_DWriteFactory + 16LL))(Globals::g_DWriteFactory);
    Globals::g_DWriteFactory = 0;
  }
  if ( Globals::UniscribeDllModule )
  {
    FreeLibrary(Globals::UniscribeDllModule);
    Globals::UniscribeDllModule = 0;
  }
  if ( Globals::RuntimeInitialized )
    Globals::RuntimeInitialized = 0;
  if ( LoadLibraryCriticalSection::initialized )
  {
    DeleteCriticalSection(&LoadLibraryCriticalSection::critSec);
    LoadLibraryCriticalSection::initialized = 0;
  }
  if ( BackgroundThreadCriticalSection::initialized )
  {
    DeleteCriticalSection(&BackgroundThreadCriticalSection::critSec);
    BackgroundThreadCriticalSection::initialized = 0;
  }
  if ( GpMallocTrackingCriticalSection::initialized )
  {
    DeleteCriticalSection(&GpMallocTrackingCriticalSection::critSec);
    GpMallocTrackingCriticalSection::initialized = 0;
  }
  if ( GpRuntime::GpMemHeap )
  {
    HeapDestroy(GpRuntime::GpMemHeap);
    GpRuntime::GpMemHeap = 0;
  }
  CPUSpecificOps::Initialized = 0;
  return v0;
}

```

## disassembly

```asm
0x18009f22c  push    rbx
0x18009f22e  push    rbp
0x18009f22f  push    rsi
0x18009f230  push    rdi
0x18009f231  sub     rsp, 28h
0x18009f235  xor     ebp, ebp
0x18009f237  mov     esi, ebp
0x18009f239  call    TraceLoggingUnregister_EventUnregister
0x18009f23e  cmp     cs:?BackgroundThreadHandle@Globals@@3PEAXEA, rbp; void * Globals::BackgroundThreadHandle
0x18009f245  jnz     loc_18009F6A6
0x18009f24b  mov     rcx, cs:?PathLookAside@Globals@@3PEAVGpPath@@EA; GpPath * Globals::PathLookAside
0x18009f252  mov     edi, 1
0x18009f257  test    rcx, rcx
0x18009f25a  jnz     loc_18009F6DA
0x18009f260  mov     rcx, cs:?MatrixLookAside@Globals@@3PEAVGpMatrix@@EA; this
0x18009f267  mov     cs:?PathLookAside@Globals@@3PEAVGpPath@@EA, rbp; GpPath * Globals::PathLookAside
0x18009f26e  test    rcx, rcx
0x18009f271  jnz     loc_18009F6EC
0x18009f277  mov     rcx, cs:?PenLookAside@Globals@@3PEAVGpPen@@EA; GpPen * Globals::PenLookAside
0x18009f27e  mov     cs:?MatrixLookAside@Globals@@3PEAVGpMatrix@@EA, rbp; GpMatrix * Globals::MatrixLookAside
0x18009f285  test    rcx, rcx
0x18009f288  jnz     loc_18009F6F6
0x18009f28e  mov     rcx, cs:?DesktopDevice@Globals@@3PEAVGpDevice@@EA; GpDevice * Globals::DesktopDevice
0x18009f295  mov     cs:?PenLookAside@Globals@@3PEAVGpPen@@EA, rbp; GpPen * Globals::PenLookAside
0x18009f29c  test    rcx, rcx
0x18009f29f  jz      short loc_18009F2AE
0x18009f2a1  mov     rax, [rcx]
0x18009f2a4  mov     edx, edi
0x18009f2a6  mov     rax, [rax]
0x18009f2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f2ae  mov     rbx, cs:?DeviceList@Globals@@3PEAVGpDeviceList@@EA; GpDeviceList * Globals::DeviceList
0x18009f2b5  mov     cs:?DesktopDevice@Globals@@3PEAVGpDevice@@EA, rbp; GpDevice * Globals::DesktopDevice
0x18009f2bc  test    rbx, rbx
0x18009f2bf  jnz     loc_18009F64F
0x18009f2c5  mov     rcx, cs:?EngineDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::EngineDriver
0x18009f2cc  mov     cs:?DeviceList@Globals@@3PEAVGpDeviceList@@EA, rbp; GpDeviceList * Globals::DeviceList
0x18009f2d3  test    rcx, rcx
0x18009f2d6  jz      short loc_18009F2E5
0x18009f2d8  mov     rax, [rcx]
0x18009f2db  mov     edx, edi
0x18009f2dd  mov     rax, [rax]
0x18009f2e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f2e5  mov     rcx, cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::DesktopDriver
0x18009f2ec  mov     cs:?EngineDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::EngineDriver
0x18009f2f3  test    rcx, rcx
0x18009f2f6  jnz     loc_18009F66A
0x18009f2fc  mov     rcx, cs:?GdiDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::GdiDriver
0x18009f303  mov     cs:?DesktopDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::DesktopDriver
0x18009f30a  test    rcx, rcx
0x18009f30d  jz      short loc_18009F31C
0x18009f30f  mov     rax, [rcx]
0x18009f312  mov     edx, edi
0x18009f314  mov     rax, [rax]
0x18009f317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f31c  mov     rcx, cs:?D3DDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::D3DDriver
0x18009f323  mov     cs:?GdiDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::GdiDriver
0x18009f32a  test    rcx, rcx
0x18009f32d  jz      short loc_18009F33C
0x18009f32f  mov     rax, [rcx]
0x18009f332  mov     edx, edi
0x18009f334  mov     rax, [rax]
0x18009f337  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f33c  mov     rcx, cs:?InfoDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::InfoDriver
0x18009f343  mov     cs:?D3DDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::D3DDriver
0x18009f34a  test    rcx, rcx
0x18009f34d  jz      short loc_18009F35C
0x18009f34f  mov     rax, [rcx]
0x18009f352  mov     edx, edi
0x18009f354  mov     rax, [rax]
0x18009f357  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f35c  mov     rcx, cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::MetaDriver
0x18009f363  mov     cs:?InfoDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::InfoDriver
0x18009f36a  test    rcx, rcx
0x18009f36d  jz      short loc_18009F37C
0x18009f36f  mov     rax, [rcx]
0x18009f372  mov     edx, edi
0x18009f374  mov     rax, [rax]
0x18009f377  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f37c  mov     rcx, cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA; this
0x18009f383  mov     cs:?MetaDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::MetaDriver
0x18009f38a  test    rcx, rcx
0x18009f38d  jnz     loc_18009F68B
0x18009f393  mov     rcx, cs:?g_pTSDriver@Globals@@3PEAVDpDriver@@EA; DpDriver * Globals::g_pTSDriver
0x18009f39a  mov     cs:?DesktopSurface@Globals@@3PEAVDpBitmap@@EA, rbp; DpBitmap * Globals::DesktopSurface
0x18009f3a1  test    rcx, rcx
0x18009f3a4  jnz     loc_18009F708
0x18009f3aa  mov     rcx, cs:?g_pTSGraphics@Globals@@3PEAVGpGraphics@@EA; this
0x18009f3b1  mov     cs:?g_pTSDriver@Globals@@3PEAVDpDriver@@EA, rbp; DpDriver * Globals::g_pTSDriver
0x18009f3b8  test    rcx, rcx
0x18009f3bb  jnz     loc_18009F71A
0x18009f3c1  mov     rcx, cs:?g_pITSClientPlayer@Globals@@3PEAVIMetafilePlayer@@EA; IMetafilePlayer * Globals::g_pITSClientPlayer
0x18009f3c8  test    rcx, rcx
0x18009f3cb  jnz     loc_18009F72B
0x18009f3d1  mov     rcx, cs:?g_pRemoteSurface@Globals@@3PEAVDpBitmap@@EA; this
0x18009f3d8  test    rcx, rcx
0x18009f3db  jnz     loc_18009F695
0x18009f3e1  mov     rcx, cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA; hLibModule
0x18009f3e8  test    rcx, rcx
0x18009f3eb  jnz     loc_18009F744
0x18009f3f1  mov     rcx, cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA; ho
0x18009f3f8  test    rcx, rcx
0x18009f3fb  jnz     loc_18009F756
0x18009f401  mov     rcx, cs:?DesktopIc@Globals@@3PEAUHDC__@@EA; hdc
0x18009f408  test    rcx, rcx
0x18009f40b  jz      short loc_18009F41A
0x18009f40d  call    cs:__imp_DeleteDC
0x18009f413  mov     cs:?DesktopIc@Globals@@3PEAUHDC__@@EA, rbp; HDC__ * Globals::DesktopIc
0x18009f41a  cmp     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x18009f420  jnz     loc_18009F600
0x18009f426  mov     rcx, cs:?DWriteSurrogateFontsTable@Globals@@3PEAPEAVGpFontFamily@@EA; GpFontFamily * * Globals::DWriteSurrogateFontsTable
0x18009f42d  lea     rax, [rcx-1]
0x18009f431  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18009f435  jbe     loc_18009F789
0x18009f43b  mov     rcx, cs:?DWriteFontCacheLastRecentlyUsedList@Globals@@3PEAVGpCacheFaceRealizationList@@EA; void *
0x18009f442  mov     cs:?DWriteSurrogateFontsTable@Globals@@3PEAPEAVGpFontFamily@@EA, 0FFFFFFFFFFFFFFFFh; GpFontFamily * * Globals::DWriteSurrogateFontsTable
0x18009f44d  test    rcx, rcx
0x18009f450  jnz     loc_18009F67C
0x18009f456  mov     rcx, cs:?NationalDigitCache@Globals@@3PEAV?$IntMap@E@@EA; void *
0x18009f45d  mov     cs:?DWriteFontCacheLastRecentlyUsedList@Globals@@3PEAVGpCacheFaceRealizationList@@EA, rbp; GpCacheFaceRealizationList * Globals::DWriteFontCacheLastRecentlyUsedList
0x18009f464  mov     cs:?GenericSansSerifFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericSansSerifFamily
0x18009f46b  mov     cs:?GenericSerifFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericSerifFamily
0x18009f472  mov     cs:?GenericMonospaceFamily@Globals@@3PEAVGpFontFamily@@EA, rbp; GpFontFamily * Globals::GenericMonospaceFamily
0x18009f479  test    rcx, rcx
0x18009f47c  jnz     loc_18009F793
0x18009f482  mov     cs:?NationalDigitCache@Globals@@3PEAV?$IntMap@E@@EA, rbp; IntMap<uchar> * Globals::NationalDigitCache
0x18009f489  call    ?DestroyStaticObjects@GpStringFormat@@SAXXZ; GpStringFormat::DestroyStaticObjects(void)
0x18009f48e  mov     rcx, cs:?FontsDirW@Globals@@3PEAGEA; ushort * Globals::FontsDirW
0x18009f495  call    GpFree
0x18009f49a  mov     rcx, cs:?FontsDirA@Globals@@3PEADEA; char * Globals::FontsDirA
0x18009f4a1  mov     cs:?FontsDirW@Globals@@3PEAGEA, rbp; ushort * Globals::FontsDirW
0x18009f4a8  call    GpFree
0x18009f4ad  mov     rcx, cs:?LookAsideBuffer@Globals@@3PEAEEA; uchar * Globals::LookAsideBuffer
0x18009f4b4  mov     cs:?FontsDirA@Globals@@3PEADEA, rbp; char * Globals::FontsDirA
0x18009f4bb  test    rcx, rcx
0x18009f4be  jnz     loc_18009F79D
0x18009f4c4  cmp     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x18009f4ca  jz      short loc_18009F4DF
0x18009f4cc  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f4d3  call    cs:__imp_DeleteCriticalSection
0x18009f4d9  mov     cs:?TextCriticalSectionInitialized@Globals@@3HA, ebp; int Globals::TextCriticalSectionInitialized
0x18009f4df  call    ?FreeCachedCodecInfo@@YAXI@Z; FreeCachedCodecInfo(uint)
0x18009f4e4  cmp     cs:?initialized@ImagingCritSec@@0HA, ebp; int ImagingCritSec::initialized
0x18009f4ea  jz      short loc_18009F4FF
0x18009f4ec  lea     rcx, ?critSec@ImagingCritSec@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f4f3  call    cs:__imp_DeleteCriticalSection
0x18009f4f9  mov     cs:?initialized@ImagingCritSec@@0HA, ebp; int ImagingCritSec::initialized
0x18009f4ff  mov     rdi, cs:qword_1801A5618
0x18009f506  test    rdi, rdi
0x18009f509  jnz     loc_18009F6B3
0x18009f50f  mov     rcx, cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x18009f516  mov     cs:qword_1801A5618, rbp
0x18009f51d  test    rcx, rcx
0x18009f520  jnz     loc_18009F7AE
0x18009f526  mov     rdx, cs:?g_GpFontFileLoader@Globals@@3PEAUIDWriteFontFileLoader@@EA; IDWriteFontFileLoader * Globals::g_GpFontFileLoader
0x18009f52d  test    rdx, rdx
0x18009f530  jnz     loc_18009F7C6
0x18009f536  mov     rdx, cs:?g_GpFontCollectionStreamLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionStreamLoader
0x18009f53d  test    rdx, rdx
0x18009f540  jnz     loc_18009F7F8
0x18009f546  mov     rdx, cs:?g_GpFontCollectionFileLoader@Globals@@3PEAUIDWriteFontCollectionLoader@@EA; IDWriteFontCollectionLoader * Globals::g_GpFontCollectionFileLoader
0x18009f54d  test    rdx, rdx
0x18009f550  jnz     loc_18009F82A
0x18009f556  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18009f55d  test    rcx, rcx
0x18009f560  jnz     loc_18009F85C
0x18009f566  mov     rcx, cs:?UniscribeDllModule@Globals@@3PEAUHINSTANCE__@@EA; hLibModule
0x18009f56d  test    rcx, rcx
0x18009f570  jnz     loc_18009F874
0x18009f576  cmp     cs:?RuntimeInitialized@Globals@@3HA, ebp; int Globals::RuntimeInitialized
0x18009f57c  jz      short loc_18009F584
0x18009f57e  mov     cs:?RuntimeInitialized@Globals@@3HA, ebp; int Globals::RuntimeInitialized
0x18009f584  cmp     cs:?initialized@LoadLibraryCriticalSection@@0HA, ebp; int LoadLibraryCriticalSection::initialized
0x18009f58a  jz      short loc_18009F59F
0x18009f58c  lea     rcx, ?critSec@LoadLibraryCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f593  call    cs:__imp_DeleteCriticalSection
0x18009f599  mov     cs:?initialized@LoadLibraryCriticalSection@@0HA, ebp; int LoadLibraryCriticalSection::initialized
0x18009f59f  cmp     cs:?initialized@BackgroundThreadCriticalSection@@0HA, ebp; int BackgroundThreadCriticalSection::initialized
0x18009f5a5  jz      short loc_18009F5BA
0x18009f5a7  lea     rcx, ?critSec@BackgroundThreadCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f5ae  call    cs:__imp_DeleteCriticalSection
0x18009f5b4  mov     cs:?initialized@BackgroundThreadCriticalSection@@0HA, ebp; int BackgroundThreadCriticalSection::initialized
0x18009f5ba  cmp     cs:?initialized@GpMallocTrackingCriticalSection@@0HA, ebp; int GpMallocTrackingCriticalSection::initialized
0x18009f5c0  jz      short loc_18009F5D5
0x18009f5c2  lea     rcx, ?critSec@GpMallocTrackingCriticalSection@@0U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f5c9  call    cs:__imp_DeleteCriticalSection
0x18009f5cf  mov     cs:?initialized@GpMallocTrackingCriticalSection@@0HA, ebp; int GpMallocTrackingCriticalSection::initialized
0x18009f5d5  mov     rcx, cs:?GpMemHeap@GpRuntime@@3PEAXEA; hHeap
0x18009f5dc  test    rcx, rcx
0x18009f5df  jz      short loc_18009F5EE
0x18009f5e1  call    cs:__imp_HeapDestroy
0x18009f5e7  mov     cs:?GpMemHeap@GpRuntime@@3PEAXEA, rbp; void * GpRuntime::GpMemHeap
0x18009f5ee  mov     cs:?Initialized@CPUSpecificOps@@3HA, ebp; int CPUSpecificOps::Initialized
0x18009f5f4  mov     rax, rsi
0x18009f5f7  add     rsp, 28h
0x18009f5fb  pop     rdi
0x18009f5fc  pop     rsi
0x18009f5fd  pop     rbp
0x18009f5fe  pop     rbx
0x18009f5ff  retn
0x18009f600  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f607  call    cs:__imp_EnterCriticalSection
0x18009f60d  mov     rcx, cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA; GpInstalledFontCollection * Globals::FontCollection
0x18009f614  test    rcx, rcx
0x18009f617  jz      short loc_18009F626
0x18009f619  mov     rax, [rcx]
0x18009f61c  mov     edx, edi
0x18009f61e  mov     rax, [rax]
0x18009f621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f626  mov     rbx, cs:?DWriteFontLinkTable@Globals@@3PEAVGpFontLink@@EA; GpFontLink * Globals::DWriteFontLinkTable
0x18009f62d  mov     cs:?FontCollection@Globals@@3PEAVGpInstalledFontCollection@@EA, rbp; GpInstalledFontCollection * Globals::FontCollection
0x18009f634  test    rbx, rbx
0x18009f637  jnz     loc_18009F768
0x18009f63d  lea     rcx, ?TextCriticalSection@Globals@@3U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x18009f644  call    cs:__imp_LeaveCriticalSection
0x18009f64a  jmp     loc_18009F426
0x18009f64f  mov     rcx, [rbx+8]
0x18009f653  call    GpFree
0x18009f658  mov     edx, 10h; unsigned __int64
0x18009f65d  mov     rcx, rbx; void *
0x18009f660  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f665  jmp     loc_18009F2C5
0x18009f66a  mov     rax, [rcx]
0x18009f66d  mov     edx, edi
0x18009f66f  mov     rax, [rax]
0x18009f672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f677  jmp     loc_18009F2FC
0x18009f67c  mov     edx, 10h; unsigned __int64
0x18009f681  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f686  jmp     loc_18009F456
0x18009f68b  call    ??_GDpBitmap@@QEAAPEAXI@Z; DpBitmap::`scalar deleting destructor'(uint)
0x18009f690  jmp     loc_18009F393
0x18009f695  call    ??_GDpBitmap@@QEAAPEAXI@Z; DpBitmap::`scalar deleting destructor'(uint)
0x18009f69a  mov     cs:?g_pRemoteSurface@Globals@@3PEAVDpBitmap@@EA, rbp; DpBitmap * Globals::g_pRemoteSurface
0x18009f6a1  jmp     loc_18009F3E1
0x18009f6a6  call    ?BackgroundThreadShutdown@@YAPEAXXZ; BackgroundThreadShutdown(void)
0x18009f6ab  mov     rsi, rax
0x18009f6ae  jmp     loc_18009F24B
0x18009f6b3  mov     rbx, [rdi+10h]
0x18009f6b7  mov     rcx, rdi; this
0x18009f6ba  call    ??1ols@@QEAA@XZ; ols::~ols(void)
0x18009f6bf  mov     edx, 20h ; ' '; unsigned __int64
0x18009f6c4  mov     rcx, rdi; void *
0x18009f6c7  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f6cc  mov     rdi, rbx
0x18009f6cf  test    rbx, rbx
0x18009f6d2  jz      loc_18009F50F
0x18009f6d8  jmp     short loc_18009F6B3
0x18009f6da  mov     rdx, [rcx]
0x18009f6dd  mov     rax, [rdx]
0x18009f6e0  mov     edx, edi
0x18009f6e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f6e7  jmp     loc_18009F260
0x18009f6ec  call    ??_GGpMatrix@@QEAAPEAXI@Z; GpMatrix::`scalar deleting destructor'(uint)
0x18009f6f1  jmp     loc_18009F277
0x18009f6f6  mov     rax, [rcx]
0x18009f6f9  mov     edx, edi
0x18009f6fb  mov     rax, [rax]
0x18009f6fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f703  jmp     loc_18009F28E
0x18009f708  mov     rax, [rcx]
0x18009f70b  mov     edx, edi
0x18009f70d  mov     rax, [rax]
0x18009f710  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f715  jmp     loc_18009F3AA
0x18009f71a  call    ??_GGpGraphics@@QEAAPEAXI@Z; GpGraphics::`scalar deleting destructor'(uint)
0x18009f71f  mov     cs:?g_pTSGraphics@Globals@@3PEAVGpGraphics@@EA, rbp; GpGraphics * Globals::g_pTSGraphics
0x18009f726  jmp     loc_18009F3C1
0x18009f72b  mov     rax, [rcx]
0x18009f72e  mov     edx, edi
0x18009f730  mov     rax, [rax]
0x18009f733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f738  mov     cs:?g_pITSClientPlayer@Globals@@3PEAVIMetafilePlayer@@EA, rbp; IMetafilePlayer * Globals::g_pITSClientPlayer
0x18009f73f  jmp     loc_18009F3D1
0x18009f744  call    cs:__imp_FreeLibrary
0x18009f74a  mov     cs:?DdrawHandle@Globals@@3PEAUHINSTANCE__@@EA, rbp; HINSTANCE__ * Globals::DdrawHandle
0x18009f751  jmp     loc_18009F3F1
0x18009f756  call    cs:__imp_DeleteObject
0x18009f75c  mov     cs:?CachedGdiRegion@Globals@@3PEAUHRGN__@@EA, rbp; HRGN__ * Globals::CachedGdiRegion
0x18009f763  jmp     loc_18009F401
0x18009f768  mov     rcx, rbx; this
0x18009f76b  call    ??1GpFontLink@@QEAA@XZ; GpFontLink::~GpFontLink(void)
0x18009f770  mov     edx, 40h ; '@'; unsigned __int64
0x18009f775  mov     rcx, rbx; void *
0x18009f778  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18009f77d  mov     cs:?DWriteFontLinkTable@Globals@@3PEAVGpFontLink@@EA, rbp; GpFontLink * Globals::DWriteFontLinkTable
0x18009f784  jmp     loc_18009F63D
0x18009f789  call    GpFree
0x18009f78e  jmp     loc_18009F43B
0x18009f793  call    ??_G?$IntMap@E@@QEAAPEAXI@Z; IntMap<uchar>::`scalar deleting destructor'(uint)
0x18009f798  jmp     loc_18009F482
0x18009f79d  call    GpFree
0x18009f7a2  mov     cs:?LookAsideBuffer@Globals@@3PEAEEA, rbp; uchar * Globals::LookAsideBuffer
0x18009f7a9  jmp     loc_18009F4C4
0x18009f7ae  mov     rax, [rcx]
0x18009f7b1  mov     rax, [rax+10h]
0x18009f7b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009f7ba  mov     cs:?g_DWriteTextAnalyzer@Globals@@3PEAUIDWriteTextAnalyzer@@EA, rbp; IDWriteTextAnalyzer * Globals::g_DWriteTextAnalyzer
0x18009f7c1  jmp     loc_18009F526
0x18009f7c6  mov     rcx, cs:?g_DWriteFactory@Globals@@3PEAUIDWriteFactory@@EA; IDWriteFactory * Globals::g_DWriteFactory
0x18009f7cd  mov     rax, [rcx]
  ... truncated ...
```
