# StateRepository::SRCacheContextCache::Add(ushort const *,SRCacheContext &)

- ea: `0x18000f5c8`
- end: `0x18000f69c`
- name: `?Add@SRCacheContextCache@StateRepository@@QEAAJPEBGAEAUSRCacheContext@@@Z`
- size: `212`
- prototype: `int(StateRepository::SRCacheContextCache *__hidden this, const unsigned __int16 *, struct SRCacheContext *)`
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18000bfac`

## callees

- `0x1800029dc`
- `0x18000940c`
- `0x18000a8d4`
- `0x18000e45c`
- `0x18000f5c8`
- `0x18000f6a4`
- `0x18000f7c0`

## string_xrefs

- `0x18000f62f`: `onecore\base\appmodel\staterepository\core\lib\srcachecontextcache.cpp`
- `0x18000f67f`: `onecore\base\appmodel\staterepository\core\lib\srcachecontextcache.cpp`

## pseudocode

```c
__int64 __fastcall StateRepository::SRCacheContextCache::Add(
        StateRepository::SRCacheContextCache *this,
        const unsigned __int16 *a2,
        struct SRCacheContext *a3)
{
  StateRepository::SRCacheContextCache *v5; // rdi
  StateRepository::CacheContextEntry *v6; // rax
  StateRepository::CacheContextEntry *v7; // rbx
  int v8; // eax
  unsigned int v9; // edx
  int v11; // [rsp+20h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]

  if ( !*(_QWORD *)a3 )
    return 0;
  v5 = StateRepository::SRCacheContextCacheSingleton::s_cache;
  v6 = (StateRepository::CacheContextEntry *)operator new(0x18u, (const struct std::nothrow_t *)&std::nothrow);
  v7 = v6;
  if ( v6 )
  {
    *(_QWORD *)v6 = 0;
    *((_QWORD *)v6 + 1) = 0;
    *((_QWORD *)v6 + 2) = 0;
    v8 = StateRepository::CacheContextEntry::Attach(v6, a3, a2);
    if ( v8 < 0 )
      wil::details::in1diag3::_Log_Hr(
        retaddr,
        (void *)0x12,
        (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontextcache.cpp",
        (const char *)(unsigned int)v8,
        v11);
    if ( (int)Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,unsigned short,Common::ContainerOperations<unsigned short,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::EnsureCapacity(
                v5,
                *((_QWORD *)v5 + 2) + 1LL) < 0 )
      StateRepository::CacheContextEntry::`scalar deleting destructor'(v7, v9);
    else
      *(_QWORD *)(*(_QWORD *)v5 + 8LL * (*((_QWORD *)v5 + 2))++) = v7;
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x11,
    (unsigned int)"onecore\\base\\appmodel\\staterepository\\core\\lib\\srcachecontextcache.cpp",
    (const char *)0x8007000ELL,
    v11);
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000f5c8  push    rbx
0x18000f5ca  push    rbp
0x18000f5cb  push    rsi
0x18000f5cc  push    rdi
0x18000f5cd  sub     rsp, 28h
0x18000f5d1  cmp     qword ptr [r8], 0
0x18000f5d5  mov     rsi, r8
0x18000f5d8  mov     rbp, rdx
0x18000f5db  jz      loc_18000F665
0x18000f5e1  mov     rdi, cs:?s_cache@SRCacheContextCacheSingleton@StateRepository@@0PEAVSRCacheContextCache@2@EA; StateRepository::SRCacheContextCache * StateRepository::SRCacheContextCacheSingleton::s_cache
0x18000f5e8  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000f5ef  mov     ecx, 18h; unsigned __int64
0x18000f5f4  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000f5f9  mov     rbx, rax
0x18000f5fc  test    rax, rax
0x18000f5ff  jz      short loc_18000F67A
0x18000f601  mov     qword ptr [rax], 0
0x18000f608  mov     r8, rbp; unsigned __int16 *
0x18000f60b  mov     rdx, rsi; struct SRCacheContext *
0x18000f60e  mov     qword ptr [rax+8], 0
0x18000f616  mov     rcx, rax; this
0x18000f619  mov     qword ptr [rax+10h], 0
0x18000f621  call    ?Attach@CacheContextEntry@StateRepository@@QEAAJAEAUSRCacheContext@@PEBG@Z; StateRepository::CacheContextEntry::Attach(SRCacheContext &,ushort const *)
0x18000f626  test    eax, eax
0x18000f628  jns     short loc_18000F643
0x18000f62a  mov     rcx, [rsp+48h]; this
0x18000f62f  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18000f636  mov     r9d, eax; char *
0x18000f639  mov     edx, 12h; void *
0x18000f63e  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000f643  mov     rdx, [rdi+10h]
0x18000f647  mov     rcx, rdi
0x18000f64a  inc     rdx
0x18000f64d  call    ?EnsureCapacity@?$Array@VCacheContextEntry@StateRepository@@V?$ContainerOperations@VCacheContextEntry@StateRepository@@V12@@Common@@GV?$ContainerOperations@GVCacheContextEntry@StateRepository@@@4@V?$ArrayOperations@VCacheContextEntry@StateRepository@@V12@@4@@Common@@QEAAJ_K@Z; Common::Array<StateRepository::CacheContextEntry,Common::ContainerOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>,ushort,Common::ContainerOperations<ushort,StateRepository::CacheContextEntry>,Common::ArrayOperations<StateRepository::CacheContextEntry,StateRepository::CacheContextEntry>>::EnsureCapacity(unsigned __int64)
0x18000f652  test    eax, eax
0x18000f654  js      short loc_18000F670
0x18000f656  mov     rcx, [rdi+10h]
0x18000f65a  mov     rax, [rdi]
0x18000f65d  mov     [rax+rcx*8], rbx
0x18000f661  inc     qword ptr [rdi+10h]
0x18000f665  xor     eax, eax
0x18000f667  add     rsp, 28h
0x18000f66b  pop     rdi
0x18000f66c  pop     rsi
0x18000f66d  pop     rbp
0x18000f66e  pop     rbx
0x18000f66f  retn
0x18000f670  mov     rcx, rbx; this
0x18000f673  call    ??_GCacheContextEntry@StateRepository@@QEAAPEAXI@Z; StateRepository::CacheContextEntry::`scalar deleting destructor'(uint)
0x18000f678  jmp     short loc_18000F665
0x18000f67a  mov     rcx, [rsp+48h]; this
0x18000f67f  lea     r8, aOnecoreBaseApp_4; "onecore\\base\\appmodel\\staterepositor"...
0x18000f686  mov     ebx, 8007000Eh
0x18000f68b  mov     edx, 11h; void *
0x18000f690  mov     r9d, ebx; char *
0x18000f693  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000f698  mov     eax, ebx
0x18000f69a  jmp     short loc_18000F667
```
