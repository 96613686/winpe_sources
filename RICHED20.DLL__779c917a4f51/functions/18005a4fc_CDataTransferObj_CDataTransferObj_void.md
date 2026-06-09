# CDataTransferObj::~CDataTransferObj(void)

- ea: `0x18005a4fc`
- end: `0x18005a595`
- name: `??1CDataTransferObj@@AEAA@XZ`
- size: `153`
- prototype: `void __fastcall(CDataTransferObj *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18005b470`

## callees

- `0x180023010`
- `0x180040054`
- `0x18004a8fc`
- `0x18005a4fc`
- `0x180092010`

## import_xrefs

- `GDI32!DeleteMetaFile` at `0x18005a581`
- `GDI32!DeleteMetaFile` at `0x18005a581`

## pseudocode

```c
void __fastcall CDataTransferObj::~CDataTransferObj(CDataTransferObj *this)
{
  struct ITxNotify *v2; // rdx
  __int64 v3; // rcx
  CNotifyMgr *v4; // rcx
  struct tagFORMATETC near **v5; // rcx
  __int64 v6; // rcx
  __int64 v7; // rcx
  HMETAFILE v8; // rcx

  *(_QWORD *)this = &CDataTransferObj::`vftable'{for `IDataObject'};
  v2 = (CDataTransferObj *)((char *)this + 8);
  v3 = *((_QWORD *)this + 7);
  *(_QWORD *)v2 = &CDataTransferObj::`vftable'{for `ITxNotify'};
  if ( v3 )
  {
    v4 = (CNotifyMgr *)(v3 + 128);
    if ( v4 )
      CNotifyMgr::Remove(v4, v2);
  }
  v5 = (struct tagFORMATETC near **)*((_QWORD *)this + 4);
  if ( v5 && v5 != &g_rgFETC )
    CW32System::FreePv(v5);
  v6 = *((_QWORD *)this + 12);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  v7 = *((_QWORD *)this + 13);
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = (HMETAFILE)*((_QWORD *)this + 15);
  if ( v8 )
    DeleteMetaFile(v8);
  CW32System::GlobalFree(*((void **)this + 14));
}

```

## disassembly

```asm
0x18005a4fc  push    rbx
0x18005a4fe  sub     rsp, 20h
0x18005a502  lea     rax, ??_7CDataTransferObj@@6BIDataObject@@@; const CDataTransferObj::`vftable'{for `IDataObject'}
0x18005a509  mov     rbx, rcx
0x18005a50c  mov     [rcx], rax
0x18005a50f  lea     rdx, [rcx+8]; struct ITxNotify *
0x18005a513  mov     rcx, [rcx+38h]
0x18005a517  lea     rax, ??_7CDataTransferObj@@6BITxNotify@@@; const CDataTransferObj::`vftable'{for `ITxNotify'}
0x18005a51e  mov     [rdx], rax
0x18005a521  test    rcx, rcx
0x18005a524  jz      short loc_18005A534
0x18005a526  add     rcx, 80h; this
0x18005a52d  jz      short loc_18005A534
0x18005a52f  call    ?Remove@CNotifyMgr@@QEAAXPEAVITxNotify@@@Z; CNotifyMgr::Remove(ITxNotify *)
0x18005a534  mov     rcx, [rbx+20h]; lpMem
0x18005a538  test    rcx, rcx
0x18005a53b  jz      short loc_18005A54E
0x18005a53d  lea     rax, ?g_rgFETC@@3PAUtagFORMATETC@@A; tagFORMATETC near * g_rgFETC
0x18005a544  cmp     rcx, rax
0x18005a547  jz      short loc_18005A54E
0x18005a549  call    ?FreePv@CW32System@@SAXPEAX@Z; CW32System::FreePv(void *)
0x18005a54e  mov     rcx, [rbx+60h]
0x18005a552  test    rcx, rcx
0x18005a555  jz      short loc_18005A563
0x18005a557  mov     rax, [rcx]
0x18005a55a  mov     rax, [rax+10h]
0x18005a55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a563  mov     rcx, [rbx+68h]
0x18005a567  test    rcx, rcx
0x18005a56a  jz      short loc_18005A578
0x18005a56c  mov     rax, [rcx]
0x18005a56f  mov     rax, [rax+10h]
0x18005a573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a578  mov     rcx, [rbx+78h]; hmf
0x18005a57c  test    rcx, rcx
0x18005a57f  jz      short loc_18005A587
0x18005a581  call    cs:__imp_DeleteMetaFile
0x18005a587  mov     rcx, [rbx+70h]; void *
0x18005a58b  add     rsp, 20h
0x18005a58f  pop     rbx
0x18005a590  jmp     ?GlobalFree@CW32System@@SAPEAXPEAX@Z; CW32System::GlobalFree(void *)
```
