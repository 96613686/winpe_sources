# COleClientItem::GetEmbeddedItemData(tagSTGMEDIUM *)

- ea: `0x180081770`
- end: `0x180081881`
- name: `?GetEmbeddedItemData@COleClientItem@@IEAAXPEAUtagSTGMEDIUM@@@Z`
- size: `273`
- prototype: `void __fastcall(COleClientItem *__hidden this, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1800863b0`

## callees

- `0x18000dfa0`
- `0x180081770`
- `0x18009cf3c`
- `0x1800d7010`

## import_xrefs

- `OLE32!OleSave` at `0x180081815`
- `OLE32!OleSave` at `0x180081815`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800817c6`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfileOnILockBytes` at `0x1800817c6`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180081799`
- `api-ms-win-core-com-l2-1-1!CreateILockBytesOnHGlobal` at `0x180081799`

## pseudocode

```c
void __fastcall COleClientItem::GetEmbeddedItemData(struct IUnknown **this, struct tagSTGMEDIUM *a2)
{
  HRESULT v4; // eax
  HRESULT v5; // ebx
  IPersistStorage *Interface; // rbx
  HRESULT v7; // esi
  ILockBytes *plkbyt; // [rsp+40h] [rbp+18h] BYREF
  IStorage *ppstgOpen; // [rsp+48h] [rbp+20h] BYREF

  plkbyt = 0;
  v4 = CreateILockBytesOnHGlobal(0, 1, &plkbyt);
  if ( v4 )
    AfxThrowOleException(v4);
  ppstgOpen = 0;
  v5 = StgCreateDocfileOnILockBytes(plkbyt, 0x1012u, 0, &ppstgOpen);
  if ( v5 )
  {
    ((void (__fastcall *)(ILockBytes *))plkbyt->lpVtbl->Release)(plkbyt);
    AfxThrowOleException(v5);
  }
  ((void (__fastcall *)(ILockBytes *))plkbyt->lpVtbl->Release)(plkbyt);
  Interface = (IPersistStorage *)_AfxQueryInterface(this[9], &IID_IPersistStorage);
  v7 = OleSave(Interface, ppstgOpen, 0);
  ((void (__fastcall *)(IPersistStorage *, _QWORD))Interface->lpVtbl->SaveCompleted)(Interface, 0);
  ((void (__fastcall *)(IPersistStorage *))Interface->lpVtbl->Release)(Interface);
  if ( v7 )
  {
    ((void (__fastcall *)(IStorage *))ppstgOpen->lpVtbl->Release)(ppstgOpen);
    AfxThrowOleException(v7);
  }
  a2->hBitmap = (HBITMAP)ppstgOpen;
  a2->tymed = 8;
  a2->pUnkForRelease = 0;
}

```

## disassembly

```asm
0x180081770  mov     rax, rsp
0x180081773  mov     [rax+8], rbx
0x180081777  mov     [rax+10h], rsi
0x18008177b  push    rdi
0x18008177c  sub     rsp, 20h
0x180081780  mov     rdi, rdx
0x180081783  mov     qword ptr [rax+18h], 0
0x18008178b  mov     rsi, rcx
0x18008178e  lea     r8, [rax+18h]; pplkbyt
0x180081792  mov     edx, 1; fDeleteOnRelease
0x180081797  xor     ecx, ecx; hGlobal
0x180081799  call    cs:__imp_CreateILockBytesOnHGlobal
0x18008179f  test    eax, eax
0x1800817a1  jz      short loc_1800817AB
0x1800817a3  mov     ecx, eax; int
0x1800817a5  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x1800817ab  mov     rcx, [rsp+28h+plkbyt]; plkbyt
0x1800817b0  lea     r9, [rsp+28h+ppstgOpen]; ppstgOpen
0x1800817b5  xor     r8d, r8d; reserved
0x1800817b8  mov     [rsp+28h+ppstgOpen], 0
0x1800817c1  mov     edx, 1012h; grfMode
0x1800817c6  call    cs:__imp_StgCreateDocfileOnILockBytes
0x1800817cc  mov     rcx, [rsp+28h+plkbyt]
0x1800817d1  mov     ebx, eax
0x1800817d3  test    eax, eax
0x1800817d5  jz      short loc_1800817EB
0x1800817d7  mov     rdx, [rcx]
0x1800817da  mov     rax, [rdx+10h]
0x1800817de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817e3  mov     ecx, ebx; int
0x1800817e5  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x1800817eb  mov     rax, [rcx]
0x1800817ee  mov     rax, [rax+10h]
0x1800817f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800817f7  mov     rcx, [rsi+48h]; struct IUnknown *
0x1800817fb  lea     rdx, IID_IPersistStorage; struct _GUID *
0x180081802  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x180081807  mov     rdx, [rsp+28h+ppstgOpen]; pStg
0x18008180c  xor     r8d, r8d; fSameAsLoad
0x18008180f  mov     rcx, rax; pPS
0x180081812  mov     rbx, rax
0x180081815  call    cs:__imp_OleSave
0x18008181b  mov     rcx, [rbx]
0x18008181e  xor     edx, edx
0x180081820  mov     esi, eax
0x180081822  mov     rax, [rcx+40h]
0x180081826  mov     rcx, rbx
0x180081829  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008182e  mov     rcx, [rbx]
0x180081831  mov     rax, [rcx+10h]
0x180081835  mov     rcx, rbx
0x180081838  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008183d  test    esi, esi
0x18008183f  jz      short loc_18008185A
0x180081841  mov     rcx, [rsp+28h+ppstgOpen]
0x180081846  mov     rax, [rcx]
0x180081849  mov     rax, [rax+10h]
0x18008184d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081852  mov     ecx, esi; int
0x180081854  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x18008185a  mov     rax, [rsp+28h+ppstgOpen]
0x18008185f  mov     rbx, [rsp+28h+arg_0]
0x180081864  mov     rsi, [rsp+28h+arg_8]
0x180081869  mov     [rdi+8], rax
0x18008186d  mov     dword ptr [rdi], 8
0x180081873  mov     qword ptr [rdi+10h], 0
0x18008187b  add     rsp, 20h
0x18008187f  pop     rdi
0x180081880  retn
```
