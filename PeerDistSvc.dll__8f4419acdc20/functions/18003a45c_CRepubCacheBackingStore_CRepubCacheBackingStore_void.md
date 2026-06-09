# CRepubCacheBackingStore::~CRepubCacheBackingStore(void)

- ea: `0x18003a45c`
- end: `0x18003a617`
- name: `??1CRepubCacheBackingStore@@UEAA@XZ`
- size: `443`
- prototype: `void __fastcall(CRepubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `10`
- tags: `broker_com_uri`

## callers

- `0x18003ac50`

## callees

- `0x18000354c`
- `0x180008290`
- `0x18000e55c`
- `0x18000e58c`
- `0x180011db0`
- `0x180018f48`
- `0x18001edc0`
- `0x180035de8`
- `0x18003a2d4`
- `0x18003a45c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a4f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a560`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a58c`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a4f7`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a560`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18003a58c`
- `ESENT!JetTerm2` at `0x18003a48a`
- `ESENT!JetTerm2` at `0x18003a48a`

## pseudocode

```c
void __fastcall CRepubCacheBackingStore::~CRepubCacheBackingStore(CRepubCacheBackingStore *this)
{
  JET_INSTANCE v2; // rcx
  unsigned int v3; // eax

  *(_QWORD *)this = &CRepubCacheBackingStore::`vftable';
  v2 = *((_QWORD *)this + 27);
  if ( v2 != -1 )
  {
    v3 = JetTerm2(v2, 2u);
    if ( v3
      && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids, v3);
    }
    *((_QWORD *)this + 27) = -1;
  }
  std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>((__int64 (__fastcall ****)(_QWORD, __int64))this + 6385);
  *((_QWORD *)this + 6370) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 50968));
  *((_QWORD *)this + 6368) = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((CRepubCacheBackingStore *)((char *)this + 50944));
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CRepubCacheBackingStore *)((char *)this + 50824));
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CRepubCacheBackingStore *)((char *)this + 50712));
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CRepubCacheBackingStore *)((char *)this + 50600));
  *((_QWORD *)this + 6322) = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((CRepubCacheBackingStore *)((char *)this + 50576));
  std::list<SmartPointer<CRepubJetSessionContext>>::~list<SmartPointer<CRepubJetSessionContext>>((char *)this + 50552);
  *((_QWORD *)this + 6313) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 50512));
  std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>((_QWORD *)this + 6305);
  std::_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>((void **)this + 6303);
  *((_QWORD *)this + 6297) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 50384));
  std::list<unsigned short const *>::~list<unsigned short const *>((char *)this + 50288);
  `eh vector destructor iterator'((char *)this + 9080, 0x30u, 5u, (void (*)(void *))CritSec::~CritSec);
  `eh vector destructor iterator'((char *)this + 7880, 0xF0u, 5u, (void (*)(void *))CRepubFileStore::~CRepubFileStore);
  *((_QWORD *)this + 25) = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((CRepubCacheBackingStore *)((char *)this + 200));
  `eh vector destructor iterator'(
    (char *)this + 64,
    8u,
    1u,
    (void (*)(void *))SmartPointer<CCachePublication>::~SmartPointer<CCachePublication>);
  *(_QWORD *)this = &ReferenceCounted::`vftable';
}

```

## disassembly

```asm
0x18003a45c  mov     [rsp+arg_0], rbx
0x18003a461  mov     [rsp+arg_8], rsi
0x18003a466  push    rdi
0x18003a467  sub     rsp, 20h
0x18003a46b  mov     rbx, rcx
0x18003a46e  lea     rax, ??_7CRepubCacheBackingStore@@6B@; const CRepubCacheBackingStore::`vftable'
0x18003a475  mov     [rcx], rax
0x18003a478  mov     rcx, [rcx+0D8h]; instance
0x18003a47f  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18003a483  jz      short loc_18003A4D6
0x18003a485  mov     edx, 2; grbit
0x18003a48a  call    cs:__imp_JetTerm2
0x18003a490  test    eax, eax
0x18003a492  jz      short loc_18003A4CB
0x18003a494  lea     rdx, WPP_GLOBAL_Control
0x18003a49b  mov     rcx, cs:WPP_GLOBAL_Control
0x18003a4a2  cmp     rcx, rdx
0x18003a4a5  jz      short loc_18003A4CB
0x18003a4a7  test    byte ptr [rcx+6Ch], 4
0x18003a4ab  jz      short loc_18003A4CB
0x18003a4ad  cmp     byte ptr [rcx+69h], 1
0x18003a4b1  jb      short loc_18003A4CB
0x18003a4b3  mov     edx, 0Ah
0x18003a4b8  mov     r9d, eax
0x18003a4bb  lea     r8, WPP_7d87e40345b03e83e066e32b017ea1af_Traceguids
0x18003a4c2  mov     rcx, [rcx+60h]
0x18003a4c6  call    WPP_SF_d
0x18003a4cb  mov     qword ptr [rbx+0D8h], 0FFFFFFFFFFFFFFFFh
0x18003a4d6  lea     rcx, [rbx+0C788h]
0x18003a4dd  call    ??1?$auto_ptr@VCRepubCacheMigrateWorkItem@@@std@@QEAA@XZ; std::auto_ptr<CRepubCacheMigrateWorkItem>::~auto_ptr<CRepubCacheMigrateWorkItem>(void)
0x18003a4e2  lea     rdi, ??_7CritSec@@6B@; const CritSec::`vftable'
0x18003a4e9  mov     [rbx+0C710h], rdi
0x18003a4f0  lea     rcx, [rbx+0C718h]; lpCriticalSection
0x18003a4f7  call    cs:__imp_DeleteCriticalSection
0x18003a4fd  lea     rcx, [rbx+0C700h]; this
0x18003a504  lea     rsi, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x18003a50b  mov     [rcx], rsi
0x18003a50e  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x18003a513  lea     rcx, [rbx+0C688h]; this
0x18003a51a  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18003a51f  lea     rcx, [rbx+0C618h]; this
0x18003a526  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18003a52b  lea     rcx, [rbx+0C5A8h]; this
0x18003a532  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x18003a537  lea     rcx, [rbx+0C590h]; this
0x18003a53e  mov     [rcx], rsi
0x18003a541  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x18003a546  lea     rcx, [rbx+0C578h]
0x18003a54d  call    ??1?$list@V?$SmartPointer@VCRepubJetSessionContext@@@@V?$allocator@V?$SmartPointer@VCRepubJetSessionContext@@@@@std@@@std@@QEAA@XZ; std::list<SmartPointer<CRepubJetSessionContext>>::~list<SmartPointer<CRepubJetSessionContext>>(void)
0x18003a552  mov     [rbx+0C548h], rdi
0x18003a559  lea     rcx, [rbx+0C550h]; lpCriticalSection
0x18003a560  call    cs:__imp_DeleteCriticalSection
0x18003a566  lea     rcx, [rbx+0C508h]
0x18003a56d  call    ??1?$_Hash@V?$_Hset_traits@_KV?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@_K@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(void)
0x18003a572  lea     rcx, [rbx+0C4F8h]
0x18003a579  call    ??1?$_Tree@V?$_Tmap_traits@PEAXPEAVCTnoDecompressor@@U?$less@PEAX@std@@V?$allocator@U?$pair@QEAXPEAVCTnoDecompressor@@@std@@@3@$0A@@std@@@std@@QEAA@XZ; std::_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>::~_Tree<std::_Tmap_traits<void *,CTnoDecompressor *,std::less<void *>,std::allocator<std::pair<void * const,CTnoDecompressor *>>,0>>(void)
0x18003a57e  mov     [rbx+0C4C8h], rdi
0x18003a585  lea     rcx, [rbx+0C4D0h]; lpCriticalSection
0x18003a58c  call    cs:__imp_DeleteCriticalSection
0x18003a592  lea     rcx, [rbx+0C470h]
0x18003a599  call    ??1?$list@PEBGV?$allocator@PEBG@std@@@std@@QEAA@XZ; std::list<ushort const *>::~list<ushort const *>(void)
0x18003a59e  lea     rcx, [rbx+2378h]; void *
0x18003a5a5  lea     r9, ??1CritSec@@UEAA@XZ; void (*)(void *)
0x18003a5ac  mov     edi, 5
0x18003a5b1  mov     r8d, edi; unsigned __int64
0x18003a5b4  lea     edx, [rdi+2Bh]; unsigned __int64
0x18003a5b7  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003a5bc  lea     rcx, [rbx+1EC8h]; void *
0x18003a5c3  lea     r9, ??1CRepubFileStore@@QEAA@XZ; void (*)(void *)
0x18003a5ca  mov     r8d, edi; unsigned __int64
0x18003a5cd  mov     edx, 0F0h; unsigned __int64
0x18003a5d2  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003a5d7  lea     rcx, [rbx+0C8h]; this
0x18003a5de  mov     [rcx], rsi
0x18003a5e1  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x18003a5e6  lea     rcx, [rbx+40h]; void *
0x18003a5ea  lea     r9, ??1?$SmartPointer@VCCachePublication@@@@QEAA@XZ; void (*)(void *)
0x18003a5f1  lea     edx, [rdi+3]; unsigned __int64
0x18003a5f4  lea     r8d, [rdi-4]; unsigned __int64
0x18003a5f8  call    ??_M@YAXPEAX_K1P6AX0@Z@Z; `eh vector destructor iterator'(void *,unsigned __int64,unsigned __int64,void (*)(void *))
0x18003a5fd  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x18003a604  mov     [rbx], rax
0x18003a607  mov     rbx, [rsp+28h+arg_0]
0x18003a60c  mov     rsi, [rsp+28h+arg_8]
0x18003a611  add     rsp, 20h
0x18003a615  pop     rdi
0x18003a616  retn
```
