# CPubCacheBackingStore::~CPubCacheBackingStore(void)

- ea: `0x180052c00`
- end: `0x180052d1e`
- name: `??1CPubCacheBackingStore@@UEAA@XZ`
- size: `286`
- prototype: `void __fastcall(CPubCacheBackingStore *__hidden this)`
- caller_count: `1`
- callee_count: `8`
- tags: `broker_com_uri`

## callers

- `0x180052f30`

## callees

- `0x180008290`
- `0x18000ecf4`
- `0x180018f48`
- `0x18001edc0`
- `0x180035de8`
- `0x18003a2d4`
- `0x180052b94`
- `0x180052c00`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052cc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052cfe`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052cc9`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180052cfe`
- `ESENT!JetTerm2` at `0x180052c2e`
- `ESENT!JetTerm2` at `0x180052c2e`

## pseudocode

```c
void __fastcall CPubCacheBackingStore::~CPubCacheBackingStore(CPubCacheBackingStore *this)
{
  JET_INSTANCE v2; // rcx
  unsigned int v3; // eax

  *(_QWORD *)this = &CPubCacheBackingStore::`vftable';
  v2 = *((_QWORD *)this + 33);
  if ( v2 != -1 )
  {
    v3 = JetTerm2(v2, 2u);
    if ( v3
      && WPP_GLOBAL_Control != (CHostedCacheMsgEncoding *)&WPP_GLOBAL_Control
      && (*((_BYTE *)WPP_GLOBAL_Control + 108) & 4) != 0
      && *((_BYTE *)WPP_GLOBAL_Control + 105) )
    {
      WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 12), 10, WPP_817cd87503153d87380e6127cb13644a_Traceguids, v3);
    }
    *((_QWORD *)this + 33) = -1;
  }
  std::list<std::list<unsigned short const *>>::~list<std::list<unsigned short const *>>((char *)this + 5080);
  CThreadpoolEnvironment::~CThreadpoolEnvironment((CPubCacheBackingStore *)((char *)this + 4968));
  *((_QWORD *)this + 619) = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((CPubCacheBackingStore *)((char *)this + 4952));
  std::list<SmartPointer<CRepubJetSessionContext>>::~list<SmartPointer<CRepubJetSessionContext>>((char *)this + 4928);
  *((_QWORD *)this + 610) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 4888));
  std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>((_QWORD *)this + 602);
  SmartPointer<CRepubJetSessionContext>::Release((char *)this + 3880);
  *((_QWORD *)this + 29) = &ObjectHandle::`vftable';
  ObjectHandle::CloseNoThrow((CPubCacheBackingStore *)((char *)this + 232));
  *((_QWORD *)this + 5) = &CritSec::`vftable';
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 48));
  *(_QWORD *)this = &ReferenceCounted::`vftable';
}

```

## disassembly

```asm
0x180052c00  mov     [rsp+arg_0], rbx
0x180052c05  mov     [rsp+arg_8], rsi
0x180052c0a  push    rdi
0x180052c0b  sub     rsp, 20h
0x180052c0f  lea     rax, ??_7CPubCacheBackingStore@@6B@; const CPubCacheBackingStore::`vftable'
0x180052c16  mov     rbx, rcx
0x180052c19  mov     [rcx], rax
0x180052c1c  mov     rcx, [rcx+108h]; instance
0x180052c23  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x180052c27  jz      short loc_180052C7A
0x180052c29  mov     edx, 2; grbit
0x180052c2e  call    cs:__imp_JetTerm2
0x180052c34  test    eax, eax
0x180052c36  jz      short loc_180052C6F
0x180052c38  mov     rcx, cs:WPP_GLOBAL_Control
0x180052c3f  lea     rdx, WPP_GLOBAL_Control
0x180052c46  cmp     rcx, rdx
0x180052c49  jz      short loc_180052C6F
0x180052c4b  test    byte ptr [rcx+6Ch], 4
0x180052c4f  jz      short loc_180052C6F
0x180052c51  cmp     byte ptr [rcx+69h], 1
0x180052c55  jb      short loc_180052C6F
0x180052c57  mov     rcx, [rcx+60h]
0x180052c5b  lea     r8, WPP_817cd87503153d87380e6127cb13644a_Traceguids
0x180052c62  mov     edx, 0Ah
0x180052c67  mov     r9d, eax
0x180052c6a  call    WPP_SF_d
0x180052c6f  mov     qword ptr [rbx+108h], 0FFFFFFFFFFFFFFFFh
0x180052c7a  lea     rcx, [rbx+13D8h]
0x180052c81  call    ??1?$list@V?$list@PEBGV?$allocator@PEBG@std@@@std@@V?$allocator@V?$list@PEBGV?$allocator@PEBG@std@@@std@@@2@@std@@QEAA@XZ; std::list<std::list<ushort const *>>::~list<std::list<ushort const *>>(void)
0x180052c86  lea     rcx, [rbx+1368h]; this
0x180052c8d  call    ??1CThreadpoolEnvironment@@UEAA@XZ; CThreadpoolEnvironment::~CThreadpoolEnvironment(void)
0x180052c92  lea     rcx, [rbx+1358h]; this
0x180052c99  lea     rsi, ??_7ObjectHandle@@6B@; const ObjectHandle::`vftable'
0x180052ca0  mov     [rcx], rsi
0x180052ca3  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x180052ca8  lea     rcx, [rbx+1340h]
0x180052caf  call    ??1?$list@V?$SmartPointer@VCRepubJetSessionContext@@@@V?$allocator@V?$SmartPointer@VCRepubJetSessionContext@@@@@std@@@std@@QEAA@XZ; std::list<SmartPointer<CRepubJetSessionContext>>::~list<SmartPointer<CRepubJetSessionContext>>(void)
0x180052cb4  lea     rdi, ??_7CritSec@@6B@; const CritSec::`vftable'
0x180052cbb  lea     rcx, [rbx+1318h]; lpCriticalSection
0x180052cc2  mov     [rbx+1310h], rdi
0x180052cc9  call    cs:__imp_DeleteCriticalSection
0x180052ccf  lea     rcx, [rbx+12D0h]
0x180052cd6  call    ??1?$_Hash@V?$_Hset_traits@_KV?$hash_compare@_KU?$less@_K@std@@@stdext@@V?$allocator@_K@std@@$0A@@stdext@@@std@@QEAA@XZ; std::_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>::~_Hash<stdext::_Hset_traits<unsigned __int64,stdext::hash_compare<unsigned __int64,std::less<unsigned __int64>>,std::allocator<unsigned __int64>,0>>(void)
0x180052cdb  lea     rcx, [rbx+0F28h]
0x180052ce2  call    ?Release@?$SmartPointer@VCRepubJetSessionContext@@@@IEAAXXZ; SmartPointer<CRepubJetSessionContext>::Release(void)
0x180052ce7  lea     rcx, [rbx+0E8h]; this
0x180052cee  mov     [rcx], rsi
0x180052cf1  call    ?CloseNoThrow@ObjectHandle@@IEAAKXZ; ObjectHandle::CloseNoThrow(void)
0x180052cf6  lea     rcx, [rbx+30h]; lpCriticalSection
0x180052cfa  mov     [rbx+28h], rdi
0x180052cfe  call    cs:__imp_DeleteCriticalSection
0x180052d04  mov     rsi, [rsp+28h+arg_8]
0x180052d09  lea     rax, ??_7ReferenceCounted@@6B@; const ReferenceCounted::`vftable'
0x180052d10  mov     [rbx], rax
0x180052d13  mov     rbx, [rsp+28h+arg_0]
0x180052d18  add     rsp, 20h
0x180052d1c  pop     rdi
0x180052d1d  retn
```
