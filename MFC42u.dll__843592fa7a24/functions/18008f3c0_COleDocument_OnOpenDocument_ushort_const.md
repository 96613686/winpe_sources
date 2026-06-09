# COleDocument::OnOpenDocument(ushort const *)

- ea: `0x18008f3c0`
- end: `0x18008f583`
- name: `?OnOpenDocument@COleDocument@@UEAAHPEBG@Z`
- size: `451`
- prototype: `int(COleDocument *__hidden this, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800934e0`

## callees

- `0x18000a150`
- `0x18000dfa0`
- `0x180060540`
- `0x18008f3c0`
- `0x1800d7010`

## import_xrefs

- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x18008f48a`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x18008f4b8`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x18008f48a`
- `api-ms-win-core-com-l2-1-1!StgCreateDocfile` at `0x18008f4b8`
- `api-ms-win-core-com-l2-1-1!StgIsStorageFile` at `0x18008f46d`
- `api-ms-win-core-com-l2-1-1!StgIsStorageFile` at `0x18008f46d`
- `api-ms-win-core-com-l2-1-1!StgOpenStorage` at `0x18008f4e0`
- `api-ms-win-core-com-l2-1-1!StgOpenStorage` at `0x18008f51a`
- `api-ms-win-core-com-l2-1-1!StgOpenStorage` at `0x18008f4e0`
- `api-ms-win-core-com-l2-1-1!StgOpenStorage` at `0x18008f51a`

## pseudocode

```c
__int64 __fastcall COleDocument::OnOpenDocument(struct IUnknown **this, const unsigned __int16 *a2)
{
  struct IUnknown **v4; // r14
  IStorage *v6; // rax
  HRESULT v7; // eax
  CException *v8; // rdi
  CException *v9; // [rsp+30h] [rbp-38h] BYREF
  CException *v10; // [rsp+38h] [rbp-30h] BYREF
  IStorage *ppstgOpen; // [rsp+88h] [rbp+20h] BYREF

  v4 = this + 29;
  if ( !*((_DWORD *)this + 56) && !*v4 )
    return CDocument::OnOpenDocument((CDocument *)this, a2);
  ((void (__fastcall *)(struct IUnknown **))(*this)[24].lpVtbl)(this);
  if ( a2 )
  {
    ((void (__fastcall *)(struct IUnknown **))(*this)[29].lpVtbl)(this);
    _AfxRelease(v4);
  }
  ((void (__fastcall *)(struct IUnknown **, __int64))(*this)[25].lpVtbl)(this, 1);
  try
  {
    if ( *v4 )
      goto LABEL_20;
    if ( !a2 )
      AfxThrowOleException(-2147024809);
    ppstgOpen = 0;
    if ( StgIsStorageFile(a2) == 1 )
    {
      if ( StgCreateDocfile(a2, 0x30022u, 0, &ppstgOpen) < 0 || (v6 = ppstgOpen) == 0 )
      {
        v7 = StgCreateDocfile(a2, 0x30000u, 0, &ppstgOpen);
LABEL_16:
        if ( v7 < 0 )
          AfxThrowOleException(v7);
        v6 = ppstgOpen;
      }
    }
    else if ( StgOpenStorage(a2, 0, 0x10022u, 0, 0, &ppstgOpen) < 0 || (v6 = ppstgOpen) == 0 )
    {
      v7 = StgOpenStorage(a2, 0, 0x10000u, 0, 0, &ppstgOpen);
      goto LABEL_16;
    }
    *v4 = (struct IUnknown *)v6;
LABEL_20:
    ((void (__fastcall *)(struct IUnknown **))(*this)[56].lpVtbl)(this);
    ((void (__fastcall *)(struct IUnknown **, _QWORD))(*this)[25].lpVtbl)(this, 0);
  }
  catch ( CException *v9 )
  {
    ((void (__fastcall *)(struct IUnknown **))(*this)[29].lpVtbl)(this);
    _AfxRelease(this + 29);
    if ( !a2 )
      throw;
    try
    {
      v8 = v9;
      ((void (__fastcall *)(struct IUnknown **, const unsigned __int16 *, CException *, _QWORD, int))(*this)[34].lpVtbl)(
        this,
        a2,
        v9,
        0,
        61697);
    }
    catch ( CException *v10 )
    {
      CException::Delete(v10);
      v8 = v9;
    }
    CException::Delete(v8);
  }
  return 1;
}

```

## disassembly

```asm
0x18008f3c0  mov     [rsp+arg_8], rdx
0x18008f3c5  mov     [rsp+arg_0], rcx
0x18008f3ca  push    rbx
0x18008f3cb  push    rsi
0x18008f3cc  push    rdi
0x18008f3cd  push    r14
0x18008f3cf  sub     rsp, 48h
0x18008f3d3  mov     rdi, rdx
0x18008f3d6  mov     rbx, rcx
0x18008f3d9  lea     r14, [rcx+0E8h]
0x18008f3e0  cmp     dword ptr [rcx+0E0h], 0
0x18008f3e7  jnz     short loc_18008F3F9
0x18008f3e9  cmp     qword ptr [r14], 0
0x18008f3ed  jnz     short loc_18008F3F9
0x18008f3ef  call    ?OnOpenDocument@CDocument@@UEAAHPEBG@Z; CDocument::OnOpenDocument(ushort const *)
0x18008f3f4  jmp     loc_18008F579
0x18008f3f9  mov     rax, [rcx]
0x18008f3fc  mov     rax, [rax+0C0h]
0x18008f403  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f408  test    rdi, rdi
0x18008f40b  jz      short loc_18008F427
0x18008f40d  mov     rax, [rbx]
0x18008f410  mov     rcx, rbx
0x18008f413  mov     rax, [rax+0E8h]
0x18008f41a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f41f  mov     rcx, r14; struct IUnknown **
0x18008f422  call    ?_AfxRelease@@YAKPEAPEAUIUnknown@@@Z; _AfxRelease(IUnknown * *)
0x18008f427  mov     rax, [rbx]
0x18008f42a  mov     esi, 1
0x18008f42f  mov     edx, esi
0x18008f431  mov     rcx, rbx
0x18008f434  mov     rax, [rax+0C8h]
0x18008f43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f440  mov     [rsp+68h+arg_10], 0
0x18008f44b  cmp     qword ptr [r14], 0
0x18008f44f  jnz     loc_18008F536
0x18008f455  test    rdi, rdi
0x18008f458  jz      loc_18008F565
0x18008f45e  mov     [rsp+68h+ppstgOpen], 0
0x18008f46a  mov     rcx, rdi; pwcsName
0x18008f46d  call    cs:__imp_StgIsStorageFile
0x18008f473  mov     rcx, rdi; pwcsName
0x18008f476  cmp     eax, esi
0x18008f478  jnz     short loc_18008F4C0
0x18008f47a  lea     r9, [rsp+68h+ppstgOpen]; ppstgOpen
0x18008f482  xor     r8d, r8d; reserved
0x18008f485  mov     edx, 30022h; grfMode
0x18008f48a  call    cs:__imp_StgCreateDocfile
0x18008f490  test    eax, eax
0x18008f492  js      short loc_18008F4A5
0x18008f494  mov     rax, [rsp+68h+ppstgOpen]
0x18008f49c  test    rax, rax
0x18008f49f  jnz     loc_18008F533
0x18008f4a5  lea     r9, [rsp+68h+ppstgOpen]; ppstgOpen
0x18008f4ad  xor     r8d, r8d; reserved
0x18008f4b0  mov     edx, 30000h; grfMode
0x18008f4b5  mov     rcx, rdi; pwcsName
0x18008f4b8  call    cs:__imp_StgCreateDocfile
0x18008f4be  jmp     short loc_18008F520
0x18008f4c0  lea     rax, [rsp+68h+ppstgOpen]
0x18008f4c8  mov     [rsp+68h+var_40], rax; ppstgOpen
0x18008f4cd  mov     [rsp+68h+reserved], 0; reserved
0x18008f4d5  xor     r9d, r9d; snbExclude
0x18008f4d8  xor     edx, edx; pstgPriority
0x18008f4da  mov     r8d, 10022h; grfMode
0x18008f4e0  call    cs:__imp_StgOpenStorage
0x18008f4e6  test    eax, eax
0x18008f4e8  js      short loc_18008F4F7
0x18008f4ea  mov     rax, [rsp+68h+ppstgOpen]
0x18008f4f2  test    rax, rax
0x18008f4f5  jnz     short loc_18008F533
0x18008f4f7  lea     rax, [rsp+68h+ppstgOpen]
0x18008f4ff  mov     [rsp+68h+var_40], rax; ppstgOpen
0x18008f504  mov     [rsp+68h+reserved], 0; reserved
0x18008f50c  xor     r9d, r9d; snbExclude
0x18008f50f  xor     edx, edx; pstgPriority
0x18008f511  mov     r8d, 10000h; grfMode
0x18008f517  mov     rcx, rdi; pwcsName
0x18008f51a  call    cs:__imp_StgOpenStorage
0x18008f520  test    eax, eax
0x18008f522  jns     short loc_18008F52B
0x18008f524  mov     ecx, eax; int
0x18008f526  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x18008f52b  mov     rax, [rsp+68h+ppstgOpen]
0x18008f533  mov     [r14], rax
0x18008f536  mov     rax, [rbx]
0x18008f539  mov     rcx, rbx
0x18008f53c  mov     rax, [rax+1C0h]
0x18008f543  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f548  mov     rax, [rbx]
0x18008f54b  xor     edx, edx
0x18008f54d  mov     rcx, rbx
0x18008f550  mov     rax, [rax+0C8h]
0x18008f557  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008f55c  mov     [rsp+68h+arg_10], esi
0x18008f563  jmp     short loc_18008F577
0x18008f565  mov     ecx, 80070057h; int
0x18008f56a  call    ?AfxThrowOleException@@YAXJ@Z; AfxThrowOleException(long)
0x18008f570  mov     esi, [rsp+68h+arg_10]
0x18008f577  mov     eax, esi
0x18008f579  add     rsp, 48h
0x18008f57d  pop     r14
0x18008f57f  pop     rdi
0x18008f580  pop     rsi
0x18008f581  pop     rbx
0x18008f582  retn
```
