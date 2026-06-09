# SessionFontSetManager::~SessionFontSetManager(void)

- ea: `0x18006dd6c`
- end: `0x18006ddef`
- name: `??1SessionFontSetManager@@UEAA@XZ`
- size: `131`
- prototype: `void __fastcall(SessionFontSetManager *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18006dd30`

## callees

- `0x18004ff84`
- `0x1800677b4`
- `0x18006c718`
- `0x18006dd6c`
- `0x1800a2858`
- `0x1800a4544`
- `0x1800a574c`
- `0x1800a6dd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ddc5`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006ddc5`

## pseudocode

```c
void __fastcall SessionFontSetManager::~SessionFontSetManager(SessionFontSetManager *this)
{
  ThreadpoolTimer *v1; // rdi
  bool v3; // zf

  v1 = (SessionFontSetManager *)((char *)this + 168);
  v3 = *((_QWORD *)this + 21) == 0;
  *(_QWORD *)this = &SessionFontSetManager::`vftable';
  if ( !v3 )
    ThreadpoolTimer::WaitForCompletion((struct _TP_TIMER **)this + 21);
  ComPtr<IFontCacheStorageInternal>::Deref((char *)this + 176);
  ThreadpoolTimer::~ThreadpoolTimer(v1);
  ListContainer<SessionFontSetList,SessionFontSet,ReferenceOwnershipPolicy<IUnknown>>::Clear((char *)this + 144);
  HashTableImpl::~HashTableImpl((SessionFontSetManager *)((char *)this + 104));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 48);
  ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>((char *)this + 40);
  EventSource<ComInterfaceList<SessionFontSetManager,ISessionFontSetManager>,ISessionFontSetManager>::~EventSource<ComInterfaceList<SessionFontSetManager,ISessionFontSetManager>,ISessionFontSetManager>(this);
}

```

## disassembly

```asm
0x18006dd6c  mov     [rsp+arg_0], rbx
0x18006dd71  push    rdi
0x18006dd72  sub     rsp, 20h
0x18006dd76  lea     rdi, [rcx+0A8h]
0x18006dd7d  mov     rbx, rcx
0x18006dd80  cmp     qword ptr [rdi], 0
0x18006dd84  lea     rax, ??_7SessionFontSetManager@@6B@; const SessionFontSetManager::`vftable'
0x18006dd8b  mov     [rcx], rax
0x18006dd8e  jz      short loc_18006DD98
0x18006dd90  mov     rcx, rdi; this
0x18006dd93  call    ?WaitForCompletion@ThreadpoolTimer@@QEAAX_N@Z; ThreadpoolTimer::WaitForCompletion(bool)
0x18006dd98  lea     rcx, [rbx+0B0h]
0x18006dd9f  call    ?Deref@?$ComPtr@UIFontCacheStorageInternal@@@@AEAAXXZ; ComPtr<IFontCacheStorageInternal>::Deref(void)
0x18006dda4  mov     rcx, rdi; this
0x18006dda7  call    ??1ThreadpoolTimer@@QEAA@XZ; ThreadpoolTimer::~ThreadpoolTimer(void)
0x18006ddac  lea     rcx, [rbx+90h]
0x18006ddb3  call    ?Clear@?$ListContainer@VSessionFontSetList@@VSessionFontSet@@V?$ReferenceOwnershipPolicy@UIUnknown@@@@@@QEAAXXZ; ListContainer<SessionFontSetList,SessionFontSet,ReferenceOwnershipPolicy<IUnknown>>::Clear(void)
0x18006ddb8  lea     rcx, [rbx+68h]; this
0x18006ddbc  call    ??1HashTableImpl@@QEAA@XZ; HashTableImpl::~HashTableImpl(void)
0x18006ddc1  lea     rcx, [rbx+38h]; lpCriticalSection
0x18006ddc5  call    cs:__imp_DeleteCriticalSection
0x18006ddcb  lea     rcx, [rbx+30h]
0x18006ddcf  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18006ddd4  lea     rcx, [rbx+28h]
0x18006ddd8  call    ??1?$ComPtr@UIDWriteFontFileLoader@@@@QEAA@XZ; ComPtr<IDWriteFontFileLoader>::~ComPtr<IDWriteFontFileLoader>(void)
0x18006dddd  mov     rcx, rbx
0x18006dde0  mov     rbx, [rsp+28h+arg_0]
0x18006dde5  add     rsp, 20h
0x18006dde9  pop     rdi
0x18006ddea  jmp     ??1?$EventSource@V?$ComInterfaceList@VSessionFontSetManager@@UISessionFontSetManager@@@@UISessionFontSetManager@@@@UEAA@XZ; EventSource<ComInterfaceList<SessionFontSetManager,ISessionFontSetManager>,ISessionFontSetManager>::~EventSource<ComInterfaceList<SessionFontSetManager,ISessionFontSetManager>,ISessionFontSetManager>(void)
```
