# COleServerItem::GetLinkSourceData(tagSTGMEDIUM *)

- ea: `0x18009ab30`
- end: `0x18009ac46`
- name: `?GetLinkSourceData@COleServerItem@@QEAAHPEAUtagSTGMEDIUM@@@Z`
- size: `278`
- prototype: `__int64 __fastcall(COleServerItem *__hidden this, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18009a750`

## callees

- `0x18000dfa0`
- `0x18002d800`
- `0x18002da20`
- `0x18009ab30`
- `0x18009b130`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009ab97`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x18009ab97`
- `OLE32!OleSaveToStream` at `0x18009abbb`
- `OLE32!OleSaveToStream` at `0x18009abbb`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x18009abfe`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x18009abfe`

## pseudocode

```c
__int64 __fastcall COleServerItem::GetLinkSourceData(COleServerItem *this, struct tagSTGMEDIUM *a2)
{
  struct IOleObject *OleObject; // rax
  __int64 result; // rax
  HRESULT v6; // esi
  HRESULT v7; // eax
  HBITMAP v8; // rcx
  int v9; // edi
  LPSTREAM ppstm; // [rsp+60h] [rbp+30h] BYREF
  LPPERSISTSTREAM pPStm; // [rsp+68h] [rbp+38h] BYREF

  OleObject = COleServerItem::GetOleObject(this);
  if ( !OleObject )
    AfxThrowInvalidArgException();
  pPStm = 0;
  if ( ((unsigned int (__fastcall *)(struct IOleObject *, __int64, __int64, LPPERSISTSTREAM *))OleObject->lpVtbl->GetMoniker)(
         OleObject,
         4,
         3,
         &pPStm) )
  {
    return 0;
  }
  ppstm = 0;
  if ( CreateStreamOnHGlobal(0, 1, &ppstm) )
  {
    ((void (__fastcall *)(LPPERSISTSTREAM))pPStm->lpVtbl->Release)(pPStm);
    AfxThrowMemoryException();
  }
  v6 = OleSaveToStream(pPStm, ppstm);
  ((void (__fastcall *)(LPPERSISTSTREAM))pPStm->lpVtbl->Release)(pPStm);
  if ( v6 )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    AfxThrowOleException(v6);
  }
  v7 = WriteClassStm(ppstm, (const IID *const)(*(_QWORD *)(*((_QWORD *)this + 8) + 256LL) + 76LL));
  v8 = (HBITMAP)ppstm;
  v9 = v7;
  if ( v7 )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    AfxThrowOleException(v9);
  }
  a2->tymed = 4;
  result = 1;
  a2->hBitmap = v8;
  a2->pUnkForRelease = 0;
  return result;
}

```

## disassembly

```asm
0x18009ab30  mov     [rsp-18h+arg_0], rbx
0x18009ab35  push    rbp
0x18009ab36  push    rsi
0x18009ab37  push    rdi
0x18009ab38  mov     rbp, rsp
0x18009ab3b  sub     rsp, 30h
0x18009ab3f  mov     rbx, rdx
0x18009ab42  mov     rdi, rcx
0x18009ab45  call    ?GetOleObject@COleServerItem@@QEAAPEAUIOleObject@@XZ; COleServerItem::GetOleObject(void)
0x18009ab4a  mov     rcx, rax
0x18009ab4d  test    rax, rax
0x18009ab50  jnz     short loc_18009AB58
0x18009ab52  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x18009ab58  mov     [rbp+pPStm], 0
0x18009ab60  lea     r9, [rbp+pPStm]
0x18009ab64  mov     rax, [rax]
0x18009ab67  mov     edx, 4
0x18009ab6c  mov     rax, [rax+40h]
0x18009ab70  lea     r8d, [rdx-1]
0x18009ab74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ab79  test    eax, eax
0x18009ab7b  jz      short loc_18009AB84
0x18009ab7d  xor     eax, eax
0x18009ab7f  jmp     loc_18009AC39
0x18009ab84  lea     r8, [rbp+ppstm]; ppstm
0x18009ab88  mov     [rbp+ppstm], 0
0x18009ab90  mov     edx, 1; fDeleteOnRelease
0x18009ab95  xor     ecx, ecx; hGlobal
0x18009ab97  call    cs:__imp_CreateStreamOnHGlobal
0x18009ab9d  mov     rcx, [rbp+pPStm]; pPStm
0x18009aba1  test    eax, eax
0x18009aba3  jz      short loc_18009ABB7
0x18009aba5  mov     rax, [rcx]
0x18009aba8  mov     rax, [rax+10h]
0x18009abac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009abb1  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
0x18009abb7  mov     rdx, [rbp+ppstm]; pStm
0x18009abbb  call    cs:__imp_OleSaveToStream
0x18009abc1  mov     rcx, [rbp+pPStm]
0x18009abc5  mov     esi, eax
0x18009abc7  mov     rdx, [rcx]
0x18009abca  mov     rax, [rdx+10h]
0x18009abce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009abd3  mov     rcx, [rbp+ppstm]; pStm
0x18009abd7  test    esi, esi
0x18009abd9  jz      short loc_18009ABEF
0x18009abdb  mov     rdx, [rcx]
0x18009abde  mov     rax, [rdx+10h]
0x18009abe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009abe7  mov     ecx, esi; int
0x18009abe9  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x18009abef  mov     rax, [rdi+40h]
0x18009abf3  mov     rdx, [rax+100h]
0x18009abfa  add     rdx, 4Ch ; 'L'; rclsid
0x18009abfe  call    cs:__imp_WriteClassStm
0x18009ac04  mov     rcx, [rbp+ppstm]
0x18009ac08  mov     edi, eax
0x18009ac0a  test    eax, eax
0x18009ac0c  jz      short loc_18009AC22
0x18009ac0e  mov     rdx, [rcx]
0x18009ac11  mov     rax, [rdx+10h]
0x18009ac15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009ac1a  mov     ecx, edi; int
0x18009ac1c  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x18009ac22  mov     dword ptr [rbx], 4
0x18009ac28  mov     eax, 1
0x18009ac2d  mov     [rbx+8], rcx
0x18009ac31  mov     qword ptr [rbx+10h], 0
0x18009ac39  mov     rbx, [rsp+30h+arg_0]
0x18009ac3e  add     rsp, 30h
0x18009ac42  pop     rdi
0x18009ac43  pop     rsi
0x18009ac44  pop     rbp
0x18009ac45  retn
```
