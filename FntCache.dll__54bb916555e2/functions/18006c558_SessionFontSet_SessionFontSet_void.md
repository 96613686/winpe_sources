# SessionFontSet::~SessionFontSet(void)

- ea: `0x18006c558`
- end: `0x18006c673`
- name: `??1SessionFontSet@@UEAA@XZ`
- size: `283`
- prototype: `void __fastcall(SessionFontSet *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x1800b70b0`

## callees

- `0x18004ff84`
- `0x1800677b4`
- `0x18006abbc`
- `0x18006c558`
- `0x18006c67c`
- `0x18006c6d8`
- `0x18006c6f8`
- `0x18006c718`
- `0x18009f4ac`
- `0x18009fc28`
- `0x1800a3238`
- `0x1800a6dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c643`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c64d`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c643`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006c64d`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c5ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c619`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c5ea`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c607`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18006c619`

## pseudocode

```c
void __fastcall SessionFontSet::~SessionFontSet(SessionFontSet *this, bool a2)
{
  ThreadpoolTimer *v2; // rdi
  bool v4; // zf
  void *v5; // rcx
  void *v6; // rcx
  void *v7; // rcx

  v2 = (SessionFontSet *)((char *)this + 312);
  v4 = *((_QWORD *)this + 39) == 0;
  *(_QWORD *)this = &SessionFontSet::`vftable';
  if ( !v4 )
    ThreadpoolTimer::WaitForCompletion((SessionFontSet *)((char *)this + 312), a2);
  ThreadpoolWork::WaitForCompletion((SessionFontSet *)((char *)this + 176), 1);
  std::vector<DWrite::RefString>::_Tidy((char *)this + 344);
  std::vector<DWrite::RefString>::_Tidy((char *)this + 320);
  ThreadpoolTimer::~ThreadpoolTimer(v2);
  std::vector<ComPtr<IDWriteFontFileStreamInternal>>::_Tidy((char *)this + 288);
  SessionFontSet::CacheState::~CacheState((SessionFontSet *)((char *)this + 248));
  SessionFontSet::CacheState::~CacheState((SessionFontSet *)((char *)this + 208));
  v5 = (void *)*((_QWORD *)this + 25);
  if ( v5 )
  {
    CloseHandle(v5);
    *((_QWORD *)this + 25) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 24);
  if ( v6 )
    CloseHandle(v6);
  v7 = (void *)*((_QWORD *)this + 23);
  if ( v7 )
    CloseHandle(v7);
  ThreadpoolWork::~ThreadpoolWork((SessionFontSet *)((char *)this + 176));
  Event::~Event((SessionFontSet *)((char *)this + 160));
  ComPtr<IFontCacheStorageInternal>::Deref((char *)this + 152);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 112));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 72));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 56);
  EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::~EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>(this);
}

```

## disassembly

```asm
0x18006c558  mov     [rsp+arg_0], rbx
0x18006c55d  mov     [rsp+arg_8], rsi
0x18006c562  push    rdi
0x18006c563  sub     rsp, 20h
0x18006c567  lea     rdi, [rcx+138h]
0x18006c56e  mov     rbx, rcx
0x18006c571  cmp     qword ptr [rdi], 0
0x18006c575  lea     rax, ??_7SessionFontSet@@6B@; const SessionFontSet::`vftable'
0x18006c57c  mov     [rcx], rax
0x18006c57f  jz      short loc_18006C589
0x18006c581  mov     rcx, rdi; this
0x18006c584  call    ?WaitForCompletion@ThreadpoolTimer@@QEAAX_N@Z; ThreadpoolTimer::WaitForCompletion(bool)
0x18006c589  lea     rsi, [rbx+0B0h]
0x18006c590  mov     dl, 1; bool
0x18006c592  mov     rcx, rsi; this
0x18006c595  call    ?WaitForCompletion@ThreadpoolWork@@QEAAX_N@Z; ThreadpoolWork::WaitForCompletion(bool)
0x18006c59a  lea     rcx, [rbx+158h]
0x18006c5a1  call    ?_Tidy@?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@std@@AEAAXXZ; std::vector<DWrite::RefString>::_Tidy(void)
0x18006c5a6  lea     rcx, [rbx+140h]
0x18006c5ad  call    ?_Tidy@?$vector@VRefString@DWrite@@V?$allocator@VRefString@DWrite@@@std@@@std@@AEAAXXZ; std::vector<DWrite::RefString>::_Tidy(void)
0x18006c5b2  mov     rcx, rdi; this
0x18006c5b5  call    ??1ThreadpoolTimer@@QEAA@XZ; ThreadpoolTimer::~ThreadpoolTimer(void)
0x18006c5ba  lea     rcx, [rbx+120h]
0x18006c5c1  call    ?_Tidy@?$vector@V?$ComPtr@UIDWriteFontFileStreamInternal@@@@V?$allocator@V?$ComPtr@UIDWriteFontFileStreamInternal@@@@@std@@@std@@AEAAXXZ; std::vector<ComPtr<IDWriteFontFileStreamInternal>>::_Tidy(void)
0x18006c5c6  lea     rcx, [rbx+0F8h]; this
0x18006c5cd  call    ??1CacheState@SessionFontSet@@QEAA@XZ; SessionFontSet::CacheState::~CacheState(void)
0x18006c5d2  lea     rcx, [rbx+0D0h]; this
0x18006c5d9  call    ??1CacheState@SessionFontSet@@QEAA@XZ; SessionFontSet::CacheState::~CacheState(void)
0x18006c5de  mov     rcx, [rbx+0C8h]; hObject
0x18006c5e5  test    rcx, rcx
0x18006c5e8  jz      short loc_18006C5FB
0x18006c5ea  call    cs:__imp_CloseHandle
0x18006c5f0  mov     qword ptr [rbx+0C8h], 0
0x18006c5fb  mov     rcx, [rbx+0C0h]; hObject
0x18006c602  test    rcx, rcx
0x18006c605  jz      short loc_18006C60D
0x18006c607  call    cs:__imp_CloseHandle
0x18006c60d  mov     rcx, [rbx+0B8h]; hObject
0x18006c614  test    rcx, rcx
0x18006c617  jz      short loc_18006C61F
0x18006c619  call    cs:__imp_CloseHandle
0x18006c61f  mov     rcx, rsi; this
0x18006c622  call    ??1ThreadpoolWork@@QEAA@XZ; ThreadpoolWork::~ThreadpoolWork(void)
0x18006c627  lea     rcx, [rbx+0A0h]; this
0x18006c62e  call    ??1Event@@QEAA@XZ; Event::~Event(void)
0x18006c633  lea     rcx, [rbx+98h]
0x18006c63a  call    ?Deref@?$ComPtr@UIFontCacheStorageInternal@@@@AEAAXXZ; ComPtr<IFontCacheStorageInternal>::Deref(void)
0x18006c63f  lea     rcx, [rbx+70h]; lpCriticalSection
0x18006c643  call    cs:__imp_DeleteCriticalSection
0x18006c649  lea     rcx, [rbx+48h]; lpCriticalSection
0x18006c64d  call    cs:__imp_DeleteCriticalSection
0x18006c653  lea     rcx, [rbx+38h]
0x18006c657  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18006c65c  mov     rcx, rbx
0x18006c65f  mov     rbx, [rsp+28h+arg_0]
0x18006c664  mov     rsi, [rsp+28h+arg_8]
0x18006c669  add     rsp, 20h
0x18006c66d  pop     rdi
0x18006c66e  jmp     ??1?$EventSource@V?$ComInterfaceList@VSessionFontSet@@UISessionFontSet@@@@UISessionFontSet@@@@UEAA@XZ; EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>::~EventSource<ComInterfaceList<SessionFontSet,ISessionFontSet>,ISessionFontSet>(void)
```
