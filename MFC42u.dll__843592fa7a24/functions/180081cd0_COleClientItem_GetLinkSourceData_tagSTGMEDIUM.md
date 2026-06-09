# COleClientItem::GetLinkSourceData(tagSTGMEDIUM *)

- ea: `0x180081cd0`
- end: `0x180081e8b`
- name: `?GetLinkSourceData@COleClientItem@@IEAAHPEAUtagSTGMEDIUM@@@Z`
- size: `443`
- prototype: `__int64 __fastcall(COleClientItem *__hidden this, struct tagSTGMEDIUM *)`
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1800863b0`

## callees

- `0x18000dfa0`
- `0x18002d800`
- `0x18002da20`
- `0x180081cd0`
- `0x18009cf3c`
- `0x1800d1fe0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180081d6d`
- `api-ms-win-core-com-l1-1-0!CreateStreamOnHGlobal` at `0x180081d6d`
- `OLE32!OleSaveToStream` at `0x180081dc0`
- `OLE32!OleSaveToStream` at `0x180081dc0`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x180081e31`
- `api-ms-win-core-com-l2-1-1!WriteClassStm` at `0x180081e31`

## pseudocode

```c
__int64 __fastcall COleClientItem::GetLinkSourceData(struct IUnknown **this, struct tagSTGMEDIUM *a2)
{
  struct IUnknown *Interface; // rax
  struct IUnknown *v5; // r14
  __int64 v6; // rax
  int v7; // ebx
  __int64 result; // rax
  HRESULT v9; // ebx
  struct IUnknown *v10; // rcx
  int v11; // ebx
  HRESULT v12; // eax
  HBITMAP v13; // rcx
  int v14; // ebx
  LPSTREAM ppstm; // [rsp+30h] [rbp-30h] BYREF
  LPPERSISTSTREAM pPStm; // [rsp+38h] [rbp-28h] BYREF
  IID rclsid; // [rsp+40h] [rbp-20h] BYREF

  pPStm = 0;
  Interface = _AfxQueryInterface(this[9], &IID_IOleLink);
  v5 = Interface;
  if ( !Interface )
  {
    v6 = ((__int64 (__fastcall *)(struct IUnknown **))(*this)[50].lpVtbl)(this);
    if ( !v6 )
      AfxThrowInvalidArgException();
    if ( !(*(unsigned int (__fastcall **)(__int64, __int64, __int64, LPPERSISTSTREAM *))(*(_QWORD *)v6 + 32LL))(
            v6,
            4,
            3,
            &pPStm) )
      goto LABEL_5;
    return 0;
  }
  v7 = ((__int64 (__fastcall *)(struct IUnknown *, LPPERSISTSTREAM *))Interface->lpVtbl[2].QueryInterface)(
         Interface,
         &pPStm);
  ((void (__fastcall *)(struct IUnknown *))v5->lpVtbl->Release)(v5);
  if ( v7 )
    return 0;
LABEL_5:
  ppstm = 0;
  if ( CreateStreamOnHGlobal(0, 1, &ppstm) )
  {
    ((void (__fastcall *)(LPPERSISTSTREAM))pPStm->lpVtbl->Release)(pPStm);
    AfxThrowMemoryException();
  }
  v9 = OleSaveToStream(pPStm, ppstm);
  ((void (__fastcall *)(LPPERSISTSTREAM))pPStm->lpVtbl->Release)(pPStm);
  if ( v9 )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    AfxThrowOleException(v9);
  }
  v10 = this[9];
  rclsid = 0;
  v11 = ((__int64 (__fastcall *)(struct IUnknown *, IID *))v10->lpVtbl[5].QueryInterface)(v10, &rclsid);
  if ( v11 )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    AfxThrowOleException(v11);
  }
  v12 = WriteClassStm(ppstm, &rclsid);
  v13 = (HBITMAP)ppstm;
  v14 = v12;
  if ( v12 )
  {
    ((void (__fastcall *)(LPSTREAM))ppstm->lpVtbl->Release)(ppstm);
    AfxThrowOleException(v14);
  }
  a2->tymed = 4;
  result = 1;
  a2->hBitmap = v13;
  a2->pUnkForRelease = 0;
  return result;
}

```

## disassembly

```asm
0x180081cd0  mov     [rsp-18h+arg_10], rbx
0x180081cd5  mov     [rsp-18h+arg_18], rsi
0x180081cda  push    rbp
0x180081cdb  push    rdi
0x180081cdc  push    r14
0x180081cde  mov     rbp, rsp
0x180081ce1  sub     rsp, 60h
0x180081ce5  mov     rax, cs:__security_cookie
0x180081cec  xor     rax, rsp
0x180081cef  mov     [rbp+var_10], rax
0x180081cf3  mov     rdi, rdx
0x180081cf6  mov     [rbp+pPStm], 0
0x180081cfe  mov     rsi, rcx
0x180081d01  lea     rdx, IID_IOleLink; struct _GUID *
0x180081d08  mov     rcx, [rcx+48h]; struct IUnknown *
0x180081d0c  call    ?_AfxQueryInterface@@YAPEAUIUnknown@@PEAU1@AEBU_GUID@@@Z; _AfxQueryInterface(IUnknown *,_GUID const &)
0x180081d11  mov     r14, rax
0x180081d14  test    rax, rax
0x180081d17  jnz     short loc_180081D8D
0x180081d19  mov     rax, [rsi]
0x180081d1c  mov     rcx, rsi
0x180081d1f  mov     rax, [rax+190h]
0x180081d26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d2b  mov     rcx, rax
0x180081d2e  test    rax, rax
0x180081d31  jnz     short loc_180081D39
0x180081d33  call    ?AfxThrowInvalidArgException@@YAXXZ; AfxThrowInvalidArgException(void)
0x180081d39  mov     rax, [rax]
0x180081d3c  lea     r9, [rbp+pPStm]
0x180081d40  mov     edx, 4
0x180081d45  mov     rax, [rax+20h]
0x180081d49  lea     r8d, [rdx-1]
0x180081d4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d52  test    eax, eax
0x180081d54  jnz     short loc_180081DB5
0x180081d56  mov     r14d, 1
0x180081d5c  mov     [rbp+ppstm], 0
0x180081d64  mov     edx, r14d; fDeleteOnRelease
0x180081d67  lea     r8, [rbp+ppstm]; ppstm
0x180081d6b  xor     ecx, ecx; hGlobal
0x180081d6d  call    cs:__imp_CreateStreamOnHGlobal
0x180081d73  mov     rcx, [rbp+pPStm]; pPStm
0x180081d77  test    eax, eax
0x180081d79  jz      short loc_180081DBC
0x180081d7b  mov     rax, [rcx]
0x180081d7e  mov     rax, [rax+10h]
0x180081d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081d87  call    ?AfxThrowMemoryException@@YAXXZ; AfxThrowMemoryException(void)
0x180081d8d  mov     rax, [rax]
0x180081d90  lea     rdx, [rbp+pPStm]
0x180081d94  mov     rcx, r14
0x180081d97  mov     rax, [rax+30h]
0x180081d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081da0  mov     rcx, [r14]
0x180081da3  mov     ebx, eax
0x180081da5  mov     rax, [rcx+10h]
0x180081da9  mov     rcx, r14
0x180081dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081db1  test    ebx, ebx
0x180081db3  jz      short loc_180081D56
0x180081db5  xor     eax, eax
0x180081db7  jmp     loc_180081E6A
0x180081dbc  mov     rdx, [rbp+ppstm]; pStm
0x180081dc0  call    cs:__imp_OleSaveToStream
0x180081dc6  mov     rcx, [rbp+pPStm]
0x180081dca  mov     ebx, eax
0x180081dcc  mov     rdx, [rcx]
0x180081dcf  mov     rax, [rdx+10h]
0x180081dd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081dd8  test    ebx, ebx
0x180081dda  jz      short loc_180081DF4
0x180081ddc  mov     rcx, [rbp+ppstm]
0x180081de0  mov     rdx, [rcx]
0x180081de3  mov     rax, [rdx+10h]
0x180081de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081dec  mov     ecx, ebx; int
0x180081dee  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x180081df4  mov     rcx, [rsi+48h]
0x180081df8  lea     rdx, [rbp+rclsid]
0x180081dfc  xorps   xmm0, xmm0
0x180081dff  movups  xmmword ptr [rbp+rclsid.Data1], xmm0
0x180081e03  mov     rax, [rcx]
0x180081e06  mov     rax, [rax+78h]
0x180081e0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e0f  mov     rcx, [rbp+ppstm]; pStm
0x180081e13  mov     ebx, eax
0x180081e15  test    eax, eax
0x180081e17  jz      short loc_180081E2D
0x180081e19  mov     rdx, [rcx]
0x180081e1c  mov     rax, [rdx+10h]
0x180081e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e25  mov     ecx, ebx; int
0x180081e27  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x180081e2d  lea     rdx, [rbp+rclsid]; rclsid
0x180081e31  call    cs:__imp_WriteClassStm
0x180081e37  mov     rcx, [rbp+ppstm]
0x180081e3b  mov     ebx, eax
0x180081e3d  test    eax, eax
0x180081e3f  jz      short loc_180081E55
0x180081e41  mov     rdx, [rcx]
0x180081e44  mov     rax, [rdx+10h]
0x180081e48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180081e4d  mov     ecx, ebx; int
0x180081e4f  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x180081e55  mov     dword ptr [rdi], 4
0x180081e5b  mov     eax, r14d
0x180081e5e  mov     [rdi+8], rcx
0x180081e62  mov     qword ptr [rdi+10h], 0
0x180081e6a  mov     rcx, [rbp+var_10]
0x180081e6e  xor     rcx, rsp; StackCookie
0x180081e71  call    __security_check_cookie
0x180081e76  lea     r11, [rsp+60h+var_s0]
0x180081e7b  mov     rbx, [r11+30h]
0x180081e7f  mov     rsi, [r11+38h]
0x180081e83  mov     rsp, r11
0x180081e86  pop     r14
0x180081e88  pop     rdi
0x180081e89  pop     rbp
0x180081e8a  retn
```
