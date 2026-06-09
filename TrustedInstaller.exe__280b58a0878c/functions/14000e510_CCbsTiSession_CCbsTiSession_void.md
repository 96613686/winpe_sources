# CCbsTiSession::~CCbsTiSession(void)

- ea: `0x14000e510`
- end: `0x14000e632`
- name: `??1CCbsTiSession@@UEAA@XZ`
- size: `290`
- prototype: `void __fastcall(CCbsTiSession *__hidden this)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x14000ea5c`

## callees

- `0x140002674`
- `0x14000cf64`
- `0x14000e2e0`
- `0x14000e3bc`
- `0x14000e510`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e61f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e61f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e5b0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x14000e5b0`

## pseudocode

```c
void __fastcall CCbsTiSession::~CCbsTiSession(CCbsTiSession *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx
  unsigned __int64 v4; // rdx
  __int64 v5; // rcx
  __int64 v6; // rcx
  void *v7; // rcx
  __int64 v8; // rcx
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // rcx

  *(_QWORD *)this = &CCbsTiSession::`vftable';
  *((_QWORD *)this + 1) = &CCbsTiSession::`vftable'{for `CCbsIUnknownImpl<ICbsSession10,ICbsSession9,ICbsSession8,ICbsSession7,ICbsSession>'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 2) + 4LL) + 16) = &CCbsTiSession::`vftable'{for `ICbsSession10'};
  v2 = *(int *)(*((_QWORD *)this + 2) + 4LL);
  *(_DWORD *)((char *)this + v2 + 12) = v2 - 240;
  v3 = *((_QWORD *)this + 22);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 11);
  if ( v4 )
  {
    v5 = v4 + 8 + *(int *)(*(_QWORD *)(v4 + 8) + 4LL);
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  }
  v6 = *((_QWORD *)this + 5);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = (void *)*((_QWORD *)this + 13);
  if ( v7 )
    CoTaskMemFree(v7);
  v8 = *((_QWORD *)this + 18);
  if ( v8 )
    operator delete((void *)(v8 - 8), v4);
  v9 = *((_QWORD *)this + 17);
  if ( v9 )
    operator delete((void *)(v9 - 8), v4);
  v10 = *((_QWORD *)this + 19);
  if ( v10 )
    operator delete((void *)(v10 - 8), v4);
  v11 = *((_QWORD *)this + 20);
  if ( v11 )
    operator delete((void *)(v11 - 8), v4);
  TiCoreInstanceDestroyed();
  CCbsArrayBase<CCbsTiSession::LocalSource,CCbsArray<CCbsTiSession::LocalSource>>::~CCbsArrayBase<CCbsTiSession::LocalSource,CCbsArray<CCbsTiSession::LocalSource>>((char *)this + 184);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  CCbsIUnknownImpl2<ICbsServicingProcessor,ICbsSession10,ICbsSession9,ICbsSession8,ICbsSession7,ICbsSession>::~CCbsIUnknownImpl2<ICbsServicingProcessor,ICbsSession10,ICbsSession9,ICbsSession8,ICbsSession7,ICbsSession>(this);
}

```

## disassembly

```asm
0x14000e510  push    rbx
0x14000e512  sub     rsp, 20h
0x14000e516  lea     rax, ??_7CCbsTiSession@@6B@; const CCbsTiSession::`vftable'
0x14000e51d  mov     rbx, rcx
0x14000e520  mov     [rcx], rax
0x14000e523  lea     rax, ??_7CCbsTiSession@@6B?$CCbsIUnknownImpl@UICbsSession10@@UICbsSession9@@UICbsSession8@@UICbsSession7@@UICbsSession@@@@@; const CCbsTiSession::`vftable'{for `CCbsIUnknownImpl<ICbsSession10,ICbsSession9,ICbsSession8,ICbsSession7,ICbsSession>'}
0x14000e52a  mov     [rcx+8], rax
0x14000e52e  mov     rax, [rcx+10h]
0x14000e532  movsxd  rdx, dword ptr [rax+4]
0x14000e536  lea     rax, ??_7CCbsTiSession@@6BICbsSession10@@@; const CCbsTiSession::`vftable'{for `ICbsSession10'}
0x14000e53d  mov     [rdx+rcx+10h], rax
0x14000e542  mov     rax, [rcx+10h]
0x14000e546  movsxd  rdx, dword ptr [rax+4]
0x14000e54a  lea     r8d, [rdx-0F0h]
0x14000e551  mov     [rdx+rcx+0Ch], r8d
0x14000e556  mov     rcx, [rcx+0B0h]
0x14000e55d  test    rcx, rcx
0x14000e560  jz      short loc_14000E56E
0x14000e562  mov     rax, [rcx]
0x14000e565  mov     rax, [rax+10h]
0x14000e569  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e56e  mov     rdx, [rbx+58h]
0x14000e572  test    rdx, rdx
0x14000e575  jz      short loc_14000E592
0x14000e577  mov     rax, [rdx+8]
0x14000e57b  add     rdx, 8
0x14000e57f  movsxd  rcx, dword ptr [rax+4]
0x14000e583  add     rcx, rdx
0x14000e586  mov     rax, [rcx]
0x14000e589  mov     rax, [rax+10h]
0x14000e58d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e592  mov     rcx, [rbx+28h]
0x14000e596  test    rcx, rcx
0x14000e599  jz      short loc_14000E5A7
0x14000e59b  mov     rax, [rcx]
0x14000e59e  mov     rax, [rax+10h]
0x14000e5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5a7  mov     rcx, [rbx+68h]; pv
0x14000e5ab  test    rcx, rcx
0x14000e5ae  jz      short loc_14000E5B6
0x14000e5b0  call    cs:__imp_CoTaskMemFree
0x14000e5b6  mov     rcx, [rbx+90h]
0x14000e5bd  test    rcx, rcx
0x14000e5c0  jz      short loc_14000E5CB
0x14000e5c2  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14000e5c6  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e5cb  mov     rcx, [rbx+88h]
0x14000e5d2  test    rcx, rcx
0x14000e5d5  jz      short loc_14000E5E0
0x14000e5d7  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14000e5db  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e5e0  mov     rcx, [rbx+98h]
0x14000e5e7  test    rcx, rcx
0x14000e5ea  jz      short loc_14000E5F5
0x14000e5ec  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14000e5f0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e5f5  mov     rcx, [rbx+0A0h]
0x14000e5fc  test    rcx, rcx
0x14000e5ff  jz      short loc_14000E60A
0x14000e601  add     rcx, 0FFFFFFFFFFFFFFF8h; void *
0x14000e605  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x14000e60a  call    TiCoreInstanceDestroyed
0x14000e60f  lea     rcx, [rbx+0B8h]
0x14000e616  call    ??1?$CCbsArrayBase@ULocalSource@CCbsTiSession@@V?$CCbsArray@ULocalSource@CCbsTiSession@@@@@@MEAA@XZ; CCbsArrayBase<CCbsTiSession::LocalSource,CCbsArray<CCbsTiSession::LocalSource>>::~CCbsArrayBase<CCbsTiSession::LocalSource,CCbsArray<CCbsTiSession::LocalSource>>(void)
0x14000e61b  lea     rcx, [rbx+30h]; lpCriticalSection
0x14000e61f  call    cs:__imp_DeleteCriticalSection
0x14000e625  mov     rcx, rbx
0x14000e628  add     rsp, 20h
0x14000e62c  pop     rbx
0x14000e62d  jmp     ??1?$CCbsIUnknownImpl2@UICbsServicingProcessor@@UICbsSession10@@UICbsSession9@@UICbsSession8@@UICbsSession7@@UICbsSession@@@@UEAA@XZ; CCbsIUnknownImpl2<ICbsServicingProcessor,ICbsSession10,ICbsSession9,ICbsSession8,ICbsSession7,ICbsSession>::~CCbsIUnknownImpl2<ICbsServicingProcessor,ICbsSession10,ICbsSession9,ICbsSession8,ICbsSession7,ICbsSession>(void)
```
