# CDefClient::~CDefClient(void)

- ea: `0x18007ffe4`
- end: `0x180080100`
- name: `??1CDefClient@@AEAA@XZ`
- size: `284`
- prototype: `void __fastcall(CDefClient *this)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x18007c614`

## callees

- `0x18007b750`
- `0x18007b868`
- `0x18007d314`
- `0x18007f260`
- `0x18007ffe4`
- `0x1800ce010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800800cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800800cc`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180080038`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180080081`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180080038`
- `api-ms-win-core-atoms-l1-1-0!GlobalDeleteAtom` at `0x180080081`
- `USER32!IsWindow` at `0x1800800e3`
- `USER32!IsWindow` at `0x1800800e3`
- `USER32!DestroyWindow` at `0x1800800f1`
- `USER32!DestroyWindow` at `0x1800800f1`

## pseudocode

```c
void __fastcall CDefClient::~CDefClient(CDefClient *this)
{
  CDefClient *m_pdoc; // rsi
  CDefClient *v3; // rcx
  CDefClient *i; // rdi
  ATOM m_aItem; // cx
  CDDEServer *m_psrvrParent; // rcx
  ATOM v7; // cx
  ILockBytes *m_plkbytNative; // rcx
  IStorage *m_pstgNative; // rcx
  tagDVTARGETDEVICE *m_ptd; // r8

  m_pdoc = this->m_pdoc;
  CDefClient::ReleaseObjPtrs(this);
  v3 = this->m_pdoc;
  if ( v3 )
  {
    if ( m_pdoc != this )
    {
      ((void (__fastcall *)(IUnknown *))v3->m_pUnkOuter->lpVtbl->Release)(v3->m_pUnkOuter);
      goto LABEL_14;
    }
  }
  else if ( m_pdoc != this )
  {
    goto LABEL_14;
  }
  for ( i = this->m_lpNextItem; i; i = i->m_lpNextItem )
  {
    m_aItem = i->m_aItem;
    if ( m_aItem >= 0xC000u )
      GlobalDeleteAtom(m_aItem);
    CDefClient::DeleteAdviseInfo(i);
  }
  if ( this->m_fRunningInSDI )
  {
    m_psrvrParent = this->m_psrvrParent;
    if ( m_psrvrParent )
    {
      if ( CDDEServer::QueryRevokeClassFactory(m_psrvrParent) )
        CDDEServer::Revoke(this->m_psrvrParent);
    }
  }
LABEL_14:
  v7 = this->m_aItem;
  if ( v7 >= 0xC000u )
    GlobalDeleteAtom(v7);
  m_plkbytNative = this->m_plkbytNative;
  if ( m_plkbytNative )
    ((void (__fastcall *)(ILockBytes *))m_plkbytNative->lpVtbl->Release)(m_plkbytNative);
  m_pstgNative = this->m_pstgNative;
  if ( m_pstgNative )
    ((void (__fastcall *)(IStorage *))m_pstgNative->lpVtbl->Release)(m_pstgNative);
  m_ptd = this->m_ptd;
  if ( m_ptd )
    HeapFree(g_hHeap, 0, m_ptd);
  CDefClient::DeleteAdviseInfo(this);
  if ( m_pdoc == this )
  {
    if ( IsWindow(this->m_hwnd) )
      DestroyWindow(this->m_hwnd);
  }
}

```

## disassembly

```asm
0x18007ffe4  push    rbx
0x18007ffe6  push    rbp
0x18007ffe7  push    rsi
0x18007ffe8  push    rdi
0x18007ffe9  sub     rsp, 28h
0x18007ffed  mov     rsi, [this+110h]
0x18007fff4  mov     rbx, this
0x18007fff7  call    ?ReleaseObjPtrs@CDefClient@@QEAAJXZ; CDefClient::ReleaseObjPtrs(void)
0x18007fffc  mov     this, [rbx+110h]
0x180080003  mov     ebp, 0C000h
0x180080008  test    this, this
0x18008000b  jz      short loc_180080024
0x18008000d  cmp     rsi, rbx
0x180080010  jz      short loc_180080029
0x180080012  mov     this, [this+38h]
0x180080016  mov     rax, [this]
0x180080019  mov     rax, [rax+10h]
0x18008001d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180080022  jmp     short loc_180080078
0x180080024  cmp     rsi, rbx
0x180080027  jnz     short loc_180080078
0x180080029  mov     rdi, [rbx+68h]
0x18008002d  jmp     short loc_18008004A
0x18008002f  movzx   ecx, word ptr [rdi+5Ch]; nAtom
0x180080033  cmp     cx, bp
0x180080036  jb      short loc_18008003E
0x180080038  call    cs:__imp_GlobalDeleteAtom
0x18008003e  mov     this, rdi; this
0x180080041  call    ?DeleteAdviseInfo@CDefClient@@QEAAXXZ; CDefClient::DeleteAdviseInfo(void)
0x180080046  mov     rdi, [rdi+68h]
0x18008004a  test    rdi, rdi
0x18008004d  jnz     short loc_18008002F
0x18008004f  cmp     [rbx+0E0h], edi
0x180080055  jz      short loc_180080078
0x180080057  mov     this, [rbx+0E8h]; this
0x18008005e  test    this, this
0x180080061  jz      short loc_180080078
0x180080063  call    ?QueryRevokeClassFactory@CDDEServer@@QEAAHXZ; CDDEServer::QueryRevokeClassFactory(void)
0x180080068  test    eax, eax
0x18008006a  jz      short loc_180080078
0x18008006c  mov     this, [rbx+0E8h]; this
0x180080073  call    ?Revoke@CDDEServer@@QEAAJXZ; CDDEServer::Revoke(void)
0x180080078  movzx   ecx, word ptr [rbx+5Ch]; nAtom
0x18008007c  cmp     cx, bp
0x18008007f  jb      short loc_180080087
0x180080081  call    cs:__imp_GlobalDeleteAtom
0x180080087  mov     this, [rbx+0D0h]
0x18008008e  test    this, this
0x180080091  jz      short loc_18008009F
0x180080093  mov     rax, [this]
0x180080096  mov     rax, [rax+10h]
0x18008009a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008009f  mov     this, [rbx+0D8h]
0x1800800a6  test    this, this
0x1800800a9  jz      short loc_1800800B7
0x1800800ab  mov     rax, [this]
0x1800800ae  mov     rax, [rax+10h]
0x1800800b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800800b7  mov     r8, [rbx+0F0h]; lpMem
0x1800800be  test    r8, r8
0x1800800c1  jz      short loc_1800800D2
0x1800800c3  mov     this, cs:?g_hHeap@@3QEAXEA; hHeap
0x1800800ca  xor     edx, edx; dwFlags
0x1800800cc  call    cs:__imp_HeapFree
0x1800800d2  mov     this, rbx; this
0x1800800d5  call    ?DeleteAdviseInfo@CDefClient@@QEAAXXZ; CDefClient::DeleteAdviseInfo(void)
0x1800800da  cmp     rsi, rbx
0x1800800dd  jnz     short loc_1800800F7
0x1800800df  mov     this, [rbx+78h]; hWnd
0x1800800e3  call    cs:__imp_IsWindow
0x1800800e9  test    eax, eax
0x1800800eb  jz      short loc_1800800F7
0x1800800ed  mov     this, [rbx+78h]; hWnd
0x1800800f1  call    cs:__imp_DestroyWindow
0x1800800f7  add     rsp, 28h
0x1800800fb  pop     rdi
0x1800800fc  pop     rsi
0x1800800fd  pop     rbp
0x1800800fe  pop     rbx
0x1800800ff  retn
```
