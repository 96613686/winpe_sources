# CSessionObject::~CSessionObject(void)

- ea: `0x180066270`
- end: `0x1800663a6`
- name: `??1CSessionObject@@QEAA@XZ`
- size: `310`
- prototype: `void __fastcall(CSessionObject *__hidden this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18005995c`

## callees

- `0x18001d178`
- `0x18005620c`
- `0x180066270`
- `0x180066b84`
- `0x18006c808`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066292`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006629f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800662ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800662b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066315`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066337`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006634c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066292`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006629f`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800662ac`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x1800662b9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066315`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180066337`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18006634c`

## pseudocode

```c
void __fastcall CSessionObject::~CSessionObject(CSessionObject *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx

  if ( !g_fShutDownAll )
    CSessionObject::EmptyLists(this);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 22);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 23);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 25);
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 24);
  v2 = (void *)*((_QWORD *)this + 20);
  if ( v2 )
    operator delete(v2);
  v3 = (void *)*((_QWORD *)this + 21);
  if ( v3 )
    operator delete(v3);
  v4 = (void *)*((_QWORD *)this + 80);
  if ( v4 )
    operator delete(v4);
  *((_QWORD *)this + 178) = &UTLink<CUserServer *>::`vftable';
  *((_QWORD *)this + 164) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)this + 33);
  CRWLock::~CRWLock((CSessionObject *)((char *)this + 1152));
  *((_QWORD *)this + 137) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1104));
  *((_QWORD *)this + 130) = &CSemExclusive::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 1048));
  *((_QWORD *)this + 106) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 102) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 98) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 94) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 90) = &UTStaticList<CPartnerPair *>::`vftable';
  *((_QWORD *)this + 86) = &UTStaticList<CPartnerPair *>::`vftable';
  CCompactIndexManager::~CCompactIndexManager((CSessionObject *)((char *)this + 408));
  CCompactIndexManager::~CCompactIndexManager((CSessionObject *)((char *)this + 176));
}

```

## disassembly

```asm
0x180066270  mov     [rsp+arg_0], rbx
0x180066275  push    rdi
0x180066276  sub     rsp, 20h
0x18006627a  mov     rbx, rcx
0x18006627d  cmp     cs:?g_fShutDownAll@@3HA, 0; int g_fShutDownAll
0x180066284  jnz     short loc_18006628B
0x180066286  call    ?EmptyLists@CSessionObject@@AEAAXXZ; CSessionObject::EmptyLists(void)
0x18006628b  lea     rcx, [rbx+370h]; lpCriticalSection
0x180066292  call    cs:__imp_DeleteCriticalSection
0x180066298  lea     rcx, [rbx+398h]; lpCriticalSection
0x18006629f  call    cs:__imp_DeleteCriticalSection
0x1800662a5  lea     rcx, [rbx+3E8h]; lpCriticalSection
0x1800662ac  call    cs:__imp_DeleteCriticalSection
0x1800662b2  lea     rcx, [rbx+3C0h]; lpCriticalSection
0x1800662b9  call    cs:__imp_DeleteCriticalSection
0x1800662bf  mov     rcx, [rbx+0A0h]; Block
0x1800662c6  test    rcx, rcx
0x1800662c9  jz      short loc_1800662D0
0x1800662cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800662d0  mov     rcx, [rbx+0A8h]; Block
0x1800662d7  test    rcx, rcx
0x1800662da  jz      short loc_1800662E1
0x1800662dc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800662e1  mov     rcx, [rbx+280h]; Block
0x1800662e8  test    rcx, rcx
0x1800662eb  jz      short loc_1800662F2
0x1800662ed  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800662f2  lea     rax, ??_7?$UTLink@PEAVCUserServer@@@@6B@; const UTLink<CUserServer *>::`vftable'
0x1800662f9  mov     [rbx+590h], rax
0x180066300  lea     rdi, ??_7CSemExclusive@@6B@; const CSemExclusive::`vftable'
0x180066307  mov     [rbx+520h], rdi
0x18006630e  lea     rcx, [rbx+528h]; lpCriticalSection
0x180066315  call    cs:__imp_DeleteCriticalSection
0x18006631b  nop
0x18006631c  lea     rcx, [rbx+480h]; this
0x180066323  call    ??1CRWLock@@QEAA@XZ; CRWLock::~CRWLock(void)
0x180066328  nop
0x180066329  mov     [rbx+448h], rdi
0x180066330  lea     rcx, [rbx+450h]; lpCriticalSection
0x180066337  call    cs:__imp_DeleteCriticalSection
0x18006633d  nop
0x18006633e  mov     [rbx+410h], rdi
0x180066345  lea     rcx, [rbx+418h]; lpCriticalSection
0x18006634c  call    cs:__imp_DeleteCriticalSection
0x180066352  nop
0x180066353  lea     rax, ??_7?$UTStaticList@PEAVCPartnerPair@@@@6B@; const UTStaticList<CPartnerPair *>::`vftable'
0x18006635a  mov     [rbx+350h], rax
0x180066361  mov     [rbx+330h], rax
0x180066368  mov     [rbx+310h], rax
0x18006636f  mov     [rbx+2F0h], rax
0x180066376  mov     [rbx+2D0h], rax
0x18006637d  mov     [rbx+2B0h], rax
0x180066384  lea     rcx, [rbx+198h]; this
0x18006638b  call    ??1CCompactIndexManager@@QEAA@XZ; CCompactIndexManager::~CCompactIndexManager(void)
0x180066390  lea     rcx, [rbx+0B0h]; this
0x180066397  mov     rbx, [rsp+28h+arg_0]
0x18006639c  add     rsp, 20h
0x1800663a0  pop     rdi
0x1800663a1  jmp     ??1CCompactIndexManager@@QEAA@XZ; CCompactIndexManager::~CCompactIndexManager(void)
```
