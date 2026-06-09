# CTieringEngineLib::~CTieringEngineLib(void)

- ea: `0x140005504`
- end: `0x1400055e6`
- name: `??1CTieringEngineLib@@QEAA@XZ`
- size: `226`
- prototype: `void __fastcall(CTieringEngineLib *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x140003e38`
- `0x1400046d4`

## callees

- `0x14000510c`
- `0x1400051c8`
- `0x140005504`

## import_xrefs

- `msvcrt!free` at `0x1400055a4`
- `msvcrt!free` at `0x1400055a4`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005573`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400055d9`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005561`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005573`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140005585`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400055d9`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140005525`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x140005525`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14000551b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWorkCallbacks` at `0x14000551b`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140005539`
- `api-ms-win-core-threadpool-l1-2-0!WaitForThreadpoolWaitCallbacks` at `0x140005539`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140005543`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140005597`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140005543`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWait` at `0x140005597`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140005552`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpool` at `0x140005552`

## pseudocode

```c
void __fastcall CTieringEngineLib::~CTieringEngineLib(CTieringEngineLib *this)
{
  struct _TP_WORK *v2; // rcx
  struct _TP_WAIT *v3; // rcx
  struct _TP_POOL *v4; // rcx
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx
  struct _TP_WAIT *v8; // rcx
  void *v9; // rcx

  v2 = (struct _TP_WORK *)*((_QWORD *)this + 13);
  if ( v2 )
  {
    WaitForThreadpoolWorkCallbacks(v2, 1);
    CloseThreadpoolWork(*((PTP_WORK *)this + 13));
  }
  v3 = (struct _TP_WAIT *)*((_QWORD *)this + 14);
  if ( v3 )
  {
    WaitForThreadpoolWaitCallbacks(v3, 1);
    CloseThreadpoolWait(*((PTP_WAIT *)this + 14));
  }
  v4 = (struct _TP_POOL *)*((_QWORD *)this + 12);
  if ( v4 )
    CloseThreadpool(v4);
  v5 = (void *)*((_QWORD *)this + 15);
  if ( v5 )
    CloseHandle(v5);
  v6 = (void *)*((_QWORD *)this + 16);
  if ( v6 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 27);
  if ( v7 )
    CloseHandle(v7);
  v8 = (struct _TP_WAIT *)*((_QWORD *)this + 51);
  if ( v8 )
    CloseThreadpoolWait(v8);
  free(*((void **)this + 49));
  *((_QWORD *)this + 49) = 0;
  ATL::CAtlMap<unsigned long,CTieredVolume *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CTieredVolume *>>::~CAtlMap<unsigned long,CTieredVolume *,ATL::CElementTraits<unsigned long>,ATL::CElementTraits<CTieredVolume *>>((char *)this + 312);
  ATL::CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>::~CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>((char *)this + 240);
  v9 = (void *)*((_QWORD *)this + 25);
  if ( v9 )
    CloseHandle(v9);
}

```

## disassembly

```asm
0x140005504  push    rbx
0x140005506  sub     rsp, 20h
0x14000550a  mov     rbx, rcx
0x14000550d  mov     rcx, [rcx+68h]; pwk
0x140005511  test    rcx, rcx
0x140005514  jz      short loc_14000552B
0x140005516  mov     edx, 1; fCancelPendingCallbacks
0x14000551b  call    cs:__imp_WaitForThreadpoolWorkCallbacks
0x140005521  mov     rcx, [rbx+68h]; pwk
0x140005525  call    cs:__imp_CloseThreadpoolWork
0x14000552b  mov     rcx, [rbx+70h]; pwa
0x14000552f  test    rcx, rcx
0x140005532  jz      short loc_140005549
0x140005534  mov     edx, 1; fCancelPendingCallbacks
0x140005539  call    cs:__imp_WaitForThreadpoolWaitCallbacks
0x14000553f  mov     rcx, [rbx+70h]; pwa
0x140005543  call    cs:__imp_CloseThreadpoolWait
0x140005549  mov     rcx, [rbx+60h]; ptpp
0x14000554d  test    rcx, rcx
0x140005550  jz      short loc_140005558
0x140005552  call    cs:__imp_CloseThreadpool
0x140005558  mov     rcx, [rbx+78h]; hObject
0x14000555c  test    rcx, rcx
0x14000555f  jz      short loc_140005567
0x140005561  call    cs:__imp_CloseHandle
0x140005567  mov     rcx, [rbx+80h]; hObject
0x14000556e  test    rcx, rcx
0x140005571  jz      short loc_140005579
0x140005573  call    cs:__imp_CloseHandle
0x140005579  mov     rcx, [rbx+0D8h]; hObject
0x140005580  test    rcx, rcx
0x140005583  jz      short loc_14000558B
0x140005585  call    cs:__imp_CloseHandle
0x14000558b  mov     rcx, [rbx+198h]; pwa
0x140005592  test    rcx, rcx
0x140005595  jz      short loc_14000559D
0x140005597  call    cs:__imp_CloseThreadpoolWait
0x14000559d  mov     rcx, [rbx+188h]; Block
0x1400055a4  call    cs:__imp_free
0x1400055aa  mov     qword ptr [rbx+188h], 0
0x1400055b5  lea     rcx, [rbx+138h]
0x1400055bc  call    ??1?$CAtlMap@KPEAVCTieredVolume@@V?$CElementTraits@K@ATL@@V?$CElementTraits@PEAVCTieredVolume@@@3@@ATL@@QEAA@XZ; ATL::CAtlMap<ulong,CTieredVolume *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CTieredVolume *>>::~CAtlMap<ulong,CTieredVolume *,ATL::CElementTraits<ulong>,ATL::CElementTraits<CTieredVolume *>>(void)
0x1400055c1  lea     rcx, [rbx+0F0h]
0x1400055c8  call    ??1?$CAtlMap@U_GUID@@PEAVCTieredVolume@@V?$CElementTraits@U_GUID@@@ATL@@V?$CElementTraits@PEAVCTieredVolume@@@4@@ATL@@QEAA@XZ; ATL::CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>::~CAtlMap<_GUID,CTieredVolume *,ATL::CElementTraits<_GUID>,ATL::CElementTraits<CTieredVolume *>>(void)
0x1400055cd  mov     rcx, [rbx+0C8h]; hObject
0x1400055d4  test    rcx, rcx
0x1400055d7  jz      short loc_1400055E0
0x1400055d9  call    cs:__imp_CloseHandle
0x1400055df  nop
0x1400055e0  add     rsp, 20h
0x1400055e4  pop     rbx
0x1400055e5  retn
```
