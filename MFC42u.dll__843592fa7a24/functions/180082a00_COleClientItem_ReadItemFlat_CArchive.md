# COleClientItem::ReadItemFlat(CArchive &)

- ea: `0x180082a00`
- end: `0x180082b8a`
- name: `?ReadItemFlat@COleClientItem@@QEAAXAEAVCArchive@@@Z`
- size: `394`
- prototype: `void(COleClientItem *__hidden this, struct CArchive *)`
- caller_count: `2`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x1800827d0`
- `0x1800827f0`

## callees

- `0x18000dfa0`
- `0x18002d800`
- `0x180031340`
- `0x1800316a0`
- `0x180036ab0`
- `0x180082a00`
- `0x18009cf3c`
- `0x1800d7010`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x180082a74`
- `KERNEL32!GlobalFree` at `0x180082aa0`
- `KERNEL32!GlobalFree` at `0x180082a74`
- `KERNEL32!GlobalFree` at `0x180082aa0`
- `KERNEL32!GlobalUnlock` at `0x180082a67`
- `KERNEL32!GlobalUnlock` at `0x180082a67`
- `KERNEL32!GlobalAlloc` at `0x180082a37`
- `KERNEL32!GlobalAlloc` at `0x180082a37`
- `KERNEL32!GlobalLock` at `0x180082a4e`
- `KERNEL32!GlobalLock` at `0x180082a4e`
- `OLE32!OleLoad` at `0x180082b22`
- `OLE32!OleLoad` at `0x180082b22`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180082acb`
- `api-ms-win-core-com-l2-1-1!StgOpenStorageOnILockBytes` at `0x180082acb`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180082a91`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180082a91`

## pseudocode

```c
void __fastcall COleClientItem::ReadItemFlat(COleClientItem *this, struct CArchive *a2)
{
  unsigned int v4; // ebp
  HGLOBAL v5; // rax
  void *v6; // rdi
  void *v7; // rax
  unsigned int v8; // ebx
  ILockBytes **v9; // rbx
  HRESULT ILockBytesOnHGlobal; // ebp
  HRESULT v11; // edi
  LPLOCKBYTES v12; // rax
  IOleClientSite *v13; // rax
  unsigned int v14; // eax
  struct IUnknown *Interface; // rax
  LPVOID v16; // rcx
  SIZE_T dwBytes; // [rsp+60h] [rbp+18h] BYREF
  LPVOID ppvObj; // [rsp+68h] [rbp+20h] BYREF

  LODWORD(dwBytes) = 0;
  CArchive::operator>>(a2, &dwBytes);
  v4 = dwBytes;
  v5 = GlobalAlloc(0x2002u, (unsigned int)dwBytes);
  v6 = v5;
  if ( !v5 )
    AfxThrowMemoryException();
  v7 = GlobalLock(v5);
  v8 = CArchive::Read(a2, v7, v4);
  GlobalUnlock(v6);
  if ( v8 != v4 )
  {
    GlobalFree(v6);
    AfxThrowArchiveException(3, 0);
  }
  v9 = (ILockBytes **)((char *)this + 112);
  ILockBytesOnHGlobal = CreateILockBytesOnHGlobal(v6, 1, (LPLOCKBYTES *)this + 14);
  if ( ILockBytesOnHGlobal )
  {
    GlobalFree(v6);
    AfxThrowOleException(ILockBytesOnHGlobal);
  }
  v11 = StgOpenStorageOnILockBytes(*v9, 0, 0x12u, 0, 0, (IStorage **)this + 13);
  if ( v11 )
  {
    ((void (__fastcall *)(ILockBytes *))(*v9)->lpVtbl->Release)(*v9);
    *v9 = 0;
    AfxThrowOleException(v11);
  }
  v12 = *(LPLOCKBYTES *)this;
  ppvObj = 0;
  v13 = (IOleClientSite *)((__int64 (__fastcall *)(COleClientItem *))v12[50].lpVtbl)(this);
  v14 = OleLoad(*((LPSTORAGE *)this + 13), &IID_IUnknown, v13, &ppvObj);
  (*(void (__fastcall **)(COleClientItem *, _QWORD))(*(_QWORD *)this + 416LL))(this, v14);
  Interface = _AfxQueryInterface((struct IUnknown *)ppvObj, &IID_IOleObject);
  v16 = ppvObj;
  *((_QWORD *)this + 9) = Interface;
  (*(void (__fastcall **)(LPVOID))(*(_QWORD *)v16 + 16LL))(v16);
  if ( !*((_QWORD *)this + 9) )
    AfxThrowOleException(-2147024882);
}

```

## disassembly

```asm
0x180082a00  mov     rax, rsp
0x180082a03  mov     [rax+8], rbx
0x180082a07  mov     [rax+10h], rbp
0x180082a0b  push    rsi
0x180082a0c  push    rdi
0x180082a0d  push    r14
0x180082a0f  sub     rsp, 30h
0x180082a13  mov     rbx, rdx
0x180082a16  mov     dword ptr [rax+18h], 0
0x180082a1d  mov     rsi, rcx
0x180082a20  lea     rdx, [rax+18h]
0x180082a24  mov     rcx, rbx
0x180082a27  call    ??5CArchive@@QEAAAEAV0@AEAM@Z; CArchive::operator>>(float &)
0x180082a2c  mov     ebp, dword ptr [rsp+48h+dwBytes]
0x180082a30  mov     ecx, 2002h; uFlags
0x180082a35  mov     edx, ebp; dwBytes
0x180082a37  call    cs:__imp_GlobalAlloc
0x180082a3d  mov     rdi, rax
0x180082a40  test    rax, rax
0x180082a43  jnz     short loc_180082A4B
0x180082a45  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
0x180082a4b  mov     rcx, rdi; hMem
0x180082a4e  call    cs:__imp_GlobalLock
0x180082a54  mov     r8d, ebp; unsigned int
0x180082a57  mov     rcx, rbx; this
0x180082a5a  mov     rdx, rax; void *
0x180082a5d  call    ?Read@CArchive@@QEAAIPEAXI@Z; CArchive::Read(void *,uint)
0x180082a62  mov     rcx, rdi; hMem
0x180082a65  mov     ebx, eax
0x180082a67  call    cs:__imp_GlobalUnlock
0x180082a6d  mov     rcx, rdi; hMem
0x180082a70  cmp     ebx, ebp
0x180082a72  jz      short loc_180082A85
0x180082a74  call    cs:__imp_GlobalFree
0x180082a7a  xor     edx, edx; unsigned __int16 *
0x180082a7c  lea     ecx, [rdx+3]; int
0x180082a7f  call    ?AfxThrowArchiveException@@YAXHPEBG@Z; AfxThrowArchiveException(int,ushort const *)
0x180082a85  lea     rbx, [rsi+70h]
0x180082a89  mov     edx, 1; fDeleteOnRelease
0x180082a8e  mov     r8, rbx; pplkbyt
0x180082a91  call    cs:__imp_CreateILockBytesOnHGlobal
0x180082a97  mov     ebp, eax
0x180082a99  test    eax, eax
0x180082a9b  jz      short loc_180082AAE
0x180082a9d  mov     rcx, rdi; hMem
0x180082aa0  call    cs:__imp_GlobalFree
0x180082aa6  mov     ecx, ebp; int
0x180082aa8  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x180082aae  mov     rcx, [rbx]; plkbyt
0x180082ab1  lea     r14, [rsi+68h]
0x180082ab5  xor     r9d, r9d; snbExclude
0x180082ab8  mov     [rsp+48h+ppstgOpen], r14; ppstgOpen
0x180082abd  xor     edx, edx; pstgPriority
0x180082abf  mov     [rsp+48h+reserved], 0; reserved
0x180082ac7  lea     r8d, [r9+12h]; grfMode
0x180082acb  call    cs:__imp_StgOpenStorageOnILockBytes
0x180082ad1  mov     edi, eax
0x180082ad3  test    eax, eax
0x180082ad5  jz      short loc_180082AF5
0x180082ad7  mov     rcx, [rbx]
0x180082ada  mov     rdx, [rcx]
0x180082add  mov     rax, [rdx+10h]
0x180082ae1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082ae6  mov     ecx, edi; int
0x180082ae8  mov     qword ptr [rbx], 0
0x180082aef  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x180082af5  mov     rax, [rsi]
0x180082af8  mov     rcx, rsi
0x180082afb  mov     [rsp+48h+ppvObj], 0
0x180082b04  mov     rax, [rax+190h]
0x180082b0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b10  mov     rcx, [r14]; pStg
0x180082b13  lea     r9, [rsp+48h+ppvObj]; ppvObj
0x180082b18  mov     r8, rax; pClientSite
0x180082b1b  lea     rdx, IID_IUnknown; riid
0x180082b22  call    cs:__imp_OleLoad
0x180082b28  mov     rcx, [rsi]
0x180082b2b  mov     edx, eax
0x180082b2d  mov     r8, [rcx+1A0h]
0x180082b34  mov     rcx, rsi
0x180082b37  mov     rax, r8
0x180082b3a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b3f  mov     rcx, [rsp+48h+ppvObj]; struct IUnknown *
0x180082b44  lea     rdx, IID_IOleObject; struct _GUID *
0x180082b4b  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x180082b50  mov     rcx, [rsp+48h+ppvObj]
0x180082b55  mov     [rsi+48h], rax
0x180082b59  mov     rax, [rcx]
0x180082b5c  mov     rax, [rax+10h]
0x180082b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082b65  cmp     qword ptr [rsi+48h], 0
0x180082b6a  jnz     short loc_180082B77
0x180082b6c  mov     ecx, 8007000Eh; int
0x180082b71  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x180082b77  mov     rbx, [rsp+48h+arg_0]
0x180082b7c  mov     rbp, [rsp+48h+arg_8]
0x180082b81  add     rsp, 30h
0x180082b85  pop     r14
0x180082b87  pop     rdi
0x180082b88  pop     rsi
0x180082b89  retn
```
