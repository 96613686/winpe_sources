# CNetworkItemFactory::~CNetworkItemFactory(void)

- ea: `0x180002f90`
- end: `0x18000308a`
- name: `??1CNetworkItemFactory@@QEAA@XZ`
- size: `250`
- prototype: `void __fastcall(CNetworkItemFactory *__hidden this)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, loader_planting`

## callers

- `0x1800032f0`
- `0x180003a70`

## callees

- `0x180002f90`
- `0x180003bb4`
- `0x1800052c4`
- `0x1800066e8`
- `0x1800070f4`
- `0x180007d18`
- `0x180008250`
- `0x18000b010`

## import_xrefs

- `KERNEL32!SetEvent` at `0x18000305e`
- `KERNEL32!SetEvent` at `0x18000305e`
- `KERNEL32!DeleteCriticalSection` at `0x180003068`
- `KERNEL32!DeleteCriticalSection` at `0x180003068`
- `SHELL32!__imp_ILFree` at `0x180003072`
- `SHELL32!__imp_ILFree` at `0x180003072`

## pseudocode

```c
void __fastcall CNetworkItemFactory::~CNetworkItemFactory(CNetworkItemFactory *this)
{
  CFDListener *v2; // rcx
  CProfileCache *v3; // rcx
  __int64 v4; // rcx
  LKRhash::CLKRHashTable *v5; // rcx
  void *v6; // rdi
  LKRhash::CLKRHashTable *v7; // rcx
  void *v8; // rdi
  void *v9; // rcx

  *(_QWORD *)this = &CNetworkItemFactory::`vftable';
  v2 = (CFDListener *)*((_QWORD *)this + 16);
  if ( v2 )
    CFDListener::StopNotification(v2);
  v3 = (CProfileCache *)*((_QWORD *)this + 17);
  if ( v3 )
  {
    CProfileCache::NotifyBackgroundThread(v3);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 17) + 16LL))(*((_QWORD *)this + 17));
    *((_QWORD *)this + 17) = 0;
  }
  CNetworkItemFactory::_StopAllFDQueries(this);
  v4 = *((_QWORD *)this + 16);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = (LKRhash::CLKRHashTable *)*((_QWORD *)this + 10);
  if ( v5 )
  {
    LKRhash::CLKRHashTable::Clear(v5);
    v6 = (void *)*((_QWORD *)this + 10);
    if ( v6 )
    {
      LKRhash::CLKRHashTable::~CLKRHashTable(*((LKRhash::CLKRHashTable **)this + 10));
      operator delete(v6);
    }
  }
  v7 = (LKRhash::CLKRHashTable *)*((_QWORD *)this + 11);
  if ( v7 )
  {
    LKRhash::CLKRHashTable::Clear(v7);
    v8 = (void *)*((_QWORD *)this + 11);
    if ( v8 )
    {
      LKRhash::CLKRHashTable::~CLKRHashTable(*((LKRhash::CLKRHashTable **)this + 11));
      operator delete(v8);
    }
  }
  v9 = (void *)*((_QWORD *)this + 15);
  if ( v9 )
    SetEvent(v9);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  ILFree(*((LPITEMIDLIST *)this + 9));
  _InterlockedDecrement(&g_cRefThisDll);
}

```

## disassembly

```asm
0x180002f90  mov     [rsp+arg_0], rbx
0x180002f95  push    rdi
0x180002f96  sub     rsp, 20h
0x180002f9a  mov     rbx, rcx
0x180002f9d  lea     rax, ??_7CNetworkItemFactory@@6B@; const CNetworkItemFactory::`vftable'
0x180002fa4  mov     [rcx], rax
0x180002fa7  mov     rcx, [rcx+80h]; this
0x180002fae  test    rcx, rcx
0x180002fb1  jz      short loc_180002FB8
0x180002fb3  call    ?StopNotification@CFDListener@@QEAAXXZ; CFDListener::StopNotification(void)
0x180002fb8  mov     rcx, [rbx+88h]; this
0x180002fbf  test    rcx, rcx
0x180002fc2  jz      short loc_180002FE7
0x180002fc4  call    ?NotifyBackgroundThread@CProfileCache@@QEAAXXZ; CProfileCache::NotifyBackgroundThread(void)
0x180002fc9  mov     rcx, [rbx+88h]
0x180002fd0  mov     rax, [rcx]
0x180002fd3  mov     rax, [rax+10h]
0x180002fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fdc  mov     qword ptr [rbx+88h], 0
0x180002fe7  mov     rcx, rbx; this
0x180002fea  call    ?_StopAllFDQueries@CNetworkItemFactory@@AEAAJXZ; CNetworkItemFactory::_StopAllFDQueries(void)
0x180002fef  mov     rcx, [rbx+80h]
0x180002ff6  test    rcx, rcx
0x180002ff9  jz      short loc_180003007
0x180002ffb  mov     rax, [rcx]
0x180002ffe  mov     rax, [rax+10h]
0x180003002  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003007  mov     rcx, [rbx+50h]; this
0x18000300b  test    rcx, rcx
0x18000300e  jz      short loc_18000302E
0x180003010  call    ?Clear@CLKRHashTable@LKRhash@@QEAAXXZ; LKRhash::CLKRHashTable::Clear(void)
0x180003015  mov     rdi, [rbx+50h]
0x180003019  test    rdi, rdi
0x18000301c  jz      short loc_18000302E
0x18000301e  mov     rcx, rdi; this
0x180003021  call    ??1CLKRHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRHashTable::~CLKRHashTable(void)
0x180003026  mov     rcx, rdi; lpMem
0x180003029  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18000302e  mov     rcx, [rbx+58h]; this
0x180003032  test    rcx, rcx
0x180003035  jz      short loc_180003055
0x180003037  call    ?Clear@CLKRHashTable@LKRhash@@QEAAXXZ; LKRhash::CLKRHashTable::Clear(void)
0x18000303c  mov     rdi, [rbx+58h]
0x180003040  test    rdi, rdi
0x180003043  jz      short loc_180003055
0x180003045  mov     rcx, rdi; this
0x180003048  call    ??1CLKRHashTable@LKRhash@@QEAA@XZ; LKRhash::CLKRHashTable::~CLKRHashTable(void)
0x18000304d  mov     rcx, rdi; lpMem
0x180003050  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180003055  mov     rcx, [rbx+78h]; hEvent
0x180003059  test    rcx, rcx
0x18000305c  jz      short loc_180003064
0x18000305e  call    cs:__imp_SetEvent
0x180003064  lea     rcx, [rbx+10h]; lpCriticalSection
0x180003068  call    cs:__imp_DeleteCriticalSection
0x18000306e  mov     rcx, [rbx+48h]; pidl
0x180003072  call    cs:__imp_ILFree
0x180003078  lock dec cs:?g_cRefThisDll@@3JA; long g_cRefThisDll
0x18000307f  mov     rbx, [rsp+28h+arg_0]
0x180003084  add     rsp, 20h
0x180003088  pop     rdi
0x180003089  retn
```
