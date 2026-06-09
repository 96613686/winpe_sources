# CCbsTiSxSStore::~CCbsTiSxSStore(void)

- ea: `0x14000e6d4`
- end: `0x14000e76b`
- name: `??1CCbsTiSxSStore@@UEAA@XZ`
- size: `151`
- prototype: `void __fastcall(CCbsTiSxSStore *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x14000eae0`

## callees

- `0x14000cf64`
- `0x14000e6d4`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e732`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x14000e732`

## pseudocode

```c
void __fastcall CCbsTiSxSStore::~CCbsTiSxSStore(CCbsTiSxSStore *this)
{
  __int64 v2; // rdx
  __int64 v3; // rcx

  *(_QWORD *)this = &CCbsTiSxSStore::`vftable'{for `CCbsIUnknownImpl<ISxsStore,>'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &CCbsTiSxSStore::`vftable'{for `ISxsStore'};
  v2 = *(int *)(*((_QWORD *)this + 1) + 4LL);
  *(_DWORD *)((char *)this + v2 + 4) = v2 - 80;
  TiCoreInstanceDestroyed();
  v3 = *((_QWORD *)this + 9);
  if ( v3 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
    *((_QWORD *)this + 9) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 32));
  *(_QWORD *)this = &CCbsIUnknownImpl<ISxsStore,>::`vftable'{for `CCbsIUnknownImpl<ISxsStore,>'};
  *(_QWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 8) = &CCbsIUnknownImpl<ISxsStore,>::`vftable'{for `ISxsStore'};
  *(_DWORD *)((char *)this + *(int *)(*((_QWORD *)this + 1) + 4LL) + 4) = *(_DWORD *)(*((_QWORD *)this + 1) + 4LL) - 24;
}

```

## disassembly

```asm
0x14000e6d4  push    rbx
0x14000e6d6  sub     rsp, 20h
0x14000e6da  lea     rax, ??_7CCbsTiSxSStore@@6B?$CCbsIUnknownImpl@UISxsStore@@$$V@@@; const CCbsTiSxSStore::`vftable'{for `CCbsIUnknownImpl<ISxsStore,>'}
0x14000e6e1  mov     rbx, rcx
0x14000e6e4  mov     [rcx], rax
0x14000e6e7  mov     rax, [rcx+8]
0x14000e6eb  movsxd  rdx, dword ptr [rax+4]
0x14000e6ef  lea     rax, ??_7CCbsTiSxSStore@@6BISxsStore@@@; const CCbsTiSxSStore::`vftable'{for `ISxsStore'}
0x14000e6f6  mov     [rdx+rcx+8], rax
0x14000e6fb  mov     rax, [rcx+8]
0x14000e6ff  movsxd  rdx, dword ptr [rax+4]
0x14000e703  lea     r8d, [rdx-50h]
0x14000e707  mov     [rdx+rcx+4], r8d
0x14000e70c  call    TiCoreInstanceDestroyed
0x14000e711  mov     rcx, [rbx+48h]
0x14000e715  test    rcx, rcx
0x14000e718  jz      short loc_14000E72E
0x14000e71a  mov     rax, [rcx]
0x14000e71d  mov     rax, [rax+10h]
0x14000e721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e726  mov     qword ptr [rbx+48h], 0
0x14000e72e  lea     rcx, [rbx+20h]; lpCriticalSection
0x14000e732  call    cs:__imp_DeleteCriticalSection
0x14000e738  lea     rax, ??_7?$CCbsIUnknownImpl@UISxsStore@@$$V@@6B0@@; const CCbsIUnknownImpl<ISxsStore,>::`vftable'{for `CCbsIUnknownImpl<ISxsStore,>'}
0x14000e73f  mov     [rbx], rax
0x14000e742  mov     rax, [rbx+8]
0x14000e746  movsxd  rcx, dword ptr [rax+4]
0x14000e74a  lea     rax, ??_7?$CCbsIUnknownImpl@UISxsStore@@$$V@@6BISxsStore@@@; const CCbsIUnknownImpl<ISxsStore,>::`vftable'{for `ISxsStore'}
0x14000e751  mov     [rcx+rbx+8], rax
0x14000e756  mov     rax, [rbx+8]
0x14000e75a  movsxd  rcx, dword ptr [rax+4]
0x14000e75e  lea     edx, [rcx-18h]
0x14000e761  mov     [rcx+rbx+4], edx
0x14000e765  add     rsp, 20h
0x14000e769  pop     rbx
0x14000e76a  retn
```
