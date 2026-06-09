# CPicture::~CPicture(void)

- ea: `0x18002d51c`
- end: `0x18002d65c`
- name: `??1CPicture@@QEAA@XZ`
- size: `320`
- prototype: `void __fastcall(CPicture *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18002d4d0`

## callees

- `0x18002d51c`
- `0x18002d664`
- `0x18002d6cc`
- `0x18002d720`
- `0x1800ce010`

## import_xrefs

- `GDI32!DeleteMetaFile` at `0x18002d63b`
- `GDI32!DeleteMetaFile` at `0x18002d63b`
- `GDI32!DeleteObject` at `0x18002d646`
- `GDI32!DeleteObject` at `0x18002d651`
- `GDI32!DeleteObject` at `0x18002d646`
- `GDI32!DeleteObject` at `0x18002d651`
- `GDI32!DeleteEnhMetaFile` at `0x18002d5fc`
- `GDI32!DeleteEnhMetaFile` at `0x18002d5fc`
- `USER32!DestroyIcon` at `0x18002d62c`
- `USER32!DestroyIcon` at `0x18002d62c`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall CPicture::~CPicture(CPicture *this)
{
  ISimpleBinding *m_qbndData; // rcx
  CGdiCustodian *m_pcstOwn; // rcx
  HBITMAP__ *m_hbmpXor; // rcx
  HBITMAP__ *m_hbmpAnd; // rcx

  this->IPicture::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPicture'};
  this->IPicture2::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPicture2'};
  this->IPictureDisp::IDispatch::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPictureDisp'};
  this->IPersistStream::IPersist::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IPersistStream'};
  this->IConnectionPointContainer::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IConnectionPointContainer'};
  this->IMarshal::IUnknown::lpVtbl = (struct IUnknownVtbl *)CPicture::`vftable'{for `IMarshal'};
  m_qbndData = this->m_qbndData;
  if ( m_qbndData )
  {
    ((void (__fastcall *)(ISimpleBinding *))m_qbndData->lpVtbl[1].QueryInterface)(m_qbndData);
    ((void (__fastcall *)(ISimpleBinding *))this->m_qbndData->lpVtbl->Release)(this->m_qbndData);
  }
  m_pcstOwn = this->m_pcstOwn;
  if ( m_pcstOwn )
    ((void (__fastcall *)(CGdiCustodian *))m_pcstOwn->lpVtbl->Release)(m_pcstOwn);
  if ( (*((_BYTE *)this + 144) & 2) != 0 )
  {
    switch ( this->m_pic.picType )
    {
      case 2u:
        DeleteMetaFile(this->m_pic.wmf.hmeta);
        break;
      case 3u:
        DestroyIcon(this->m_pic.icon.hicon);
        break;
      case 4u:
        DeleteEnhMetaFile(this->m_pic.emf.hemf);
        break;
    }
  }
  m_hbmpXor = this->m_hbmpXor;
  if ( m_hbmpXor )
    DeleteObject(m_hbmpXor);
  m_hbmpAnd = this->m_hbmpAnd;
  if ( m_hbmpAnd )
    DeleteObject(m_hbmpAnd);
  CPicture::DecPictObjs();
  _InterlockedDecrement((volatile signed __int32 *)&g_cObjs);
  CNotifyCP::~CNotifyCP(&this->m_cpNotify);
  this->m_csmOriginalFormat.lpVtbl = (struct IUnknownVtbl *)CCacheStream::`vftable';
  CCacheStream::Empty(&this->m_csmOriginalFormat);
}

```

## disassembly

```asm
0x18002d51c  push    rbx
0x18002d51e  sub     rsp, 20h
0x18002d522  mov     rbx, this
0x18002d525  lea     rax, ??_7CPicture@@6BIPicture@@@; const CPicture::`vftable'{for `IPicture'}
0x18002d52c  mov     [this], rax
0x18002d52f  lea     rax, ??_7CPicture@@6BIPicture2@@@; const CPicture::`vftable'{for `IPicture2'}
0x18002d536  mov     [this+8], rax
0x18002d53a  lea     rax, ??_7CPicture@@6BIPictureDisp@@@; const CPicture::`vftable'{for `IPictureDisp'}
0x18002d541  mov     [this+10h], rax
0x18002d545  lea     rax, ??_7CPicture@@6BIPersistStream@@@; const CPicture::`vftable'{for `IPersistStream'}
0x18002d54c  mov     [this+18h], rax
0x18002d550  lea     rax, ??_7CPicture@@6BIConnectionPointContainer@@@; const CPicture::`vftable'{for `IConnectionPointContainer'}
0x18002d557  mov     [this+20h], rax
0x18002d55b  lea     rax, ??_7CPicture@@6BIMarshal@@@; const CPicture::`vftable'{for `IMarshal'}
0x18002d562  mov     [this+28h], rax
0x18002d566  mov     this, [this+98h]
0x18002d56d  test    this, this
0x18002d570  jnz     loc_18002D604
0x18002d576  mov     this, [rbx+88h]
0x18002d57d  test    this, this
0x18002d580  jz      short loc_18002D58E
0x18002d582  mov     rax, [this]
0x18002d585  mov     rax, [rax+10h]
0x18002d589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d58e  test    byte ptr [rbx+90h], 2
0x18002d595  jnz     short loc_18002D5E6
0x18002d597  mov     this, [rbx+70h]; ho
0x18002d59b  test    this, this
0x18002d59e  jnz     loc_18002D646
0x18002d5a4  mov     this, [rbx+68h]; ho
0x18002d5a8  test    this, this
0x18002d5ab  jnz     loc_18002D651
0x18002d5b1  call    ?DecPictObjs@CPicture@@CAIXZ; CPicture::DecPictObjs(void)
0x18002d5b6  lock dec cs:?g_cObjs@@3IA; uint g_cObjs
0x18002d5bd  lea     this, [rbx+0B8h]; this
0x18002d5c4  call    ??1CNotifyCP@@QEAA@XZ; CNotifyCP::~CNotifyCP(void)
0x18002d5c9  lea     this, [rbx+0A0h]; this
0x18002d5d0  lea     rax, ??_7CCacheStream@@6B@; const CCacheStream::`vftable'
0x18002d5d7  mov     [this], rax
0x18002d5da  call    ?Empty@CCacheStream@@UEAAJXZ; CCacheStream::Empty(void)
0x18002d5df  nop
0x18002d5e0  add     rsp, 20h
0x18002d5e4  pop     rbx
0x18002d5e5  retn
0x18002d5e6  mov     ecx, [rbx+3Ch]
0x18002d5e9  sub     ecx, 2
0x18002d5ec  jz      short loc_18002D637
0x18002d5ee  sub     ecx, 1
0x18002d5f1  jz      short loc_18002D628
0x18002d5f3  cmp     ecx, 1
0x18002d5f6  jnz     short loc_18002D597
0x18002d5f8  mov     this, [rbx+40h]; hmf
0x18002d5fc  call    cs:__imp_DeleteEnhMetaFile
0x18002d602  jmp     short loc_18002D597
0x18002d604  mov     rax, [this]
0x18002d607  mov     rax, [rax+18h]
0x18002d60b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d610  mov     this, [rbx+98h]
0x18002d617  mov     rax, [this]
0x18002d61a  mov     rax, [rax+10h]
0x18002d61e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d623  jmp     loc_18002D576
0x18002d628  mov     this, [rbx+40h]; hIcon
0x18002d62c  call    cs:__imp_DestroyIcon
0x18002d632  jmp     loc_18002D597
0x18002d637  mov     this, [rbx+40h]; hmf
0x18002d63b  call    cs:__imp_DeleteMetaFile
0x18002d641  jmp     loc_18002D597
0x18002d646  call    cs:__imp_DeleteObject
0x18002d64c  jmp     loc_18002D5A4
0x18002d651  call    cs:__imp_DeleteObject
0x18002d657  jmp     loc_18002D5B1
```
